---
title: FILESTREAM 数据
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: eef03d171d288cb2bc62c3aaa477a95a5ce718c3
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275101"
---
# <a name="filestream-data"></a>FILESTREAM 数据
FILESTREAM 存储特性用于 varbinary(max) 列中存储的二进制 (BLOB) 数据。 在 FILESTREAM 之前，存储二进制数据需要特殊处理。 非结构化的数据（例如文本文档、图像和视频）通常存储在数据库之外，从而使得难以管理此类数据。  
  
> [!NOTE]
>  您必须安装 .NET Framework 3.5 SP1（或更高版本）才能使用 SqlClient 处理 FILESTREAM 数据。  
  
 在 varbinary(max) 列上指定 FILESTREAM 属性可使 SQL Server 将数据存储在本地 NTFS 文件系统中，而不是存储在数据库文件中。 虽然数据是单独存储的，但您可以使用所支持的相同 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句来处理存储在数据库中的 varbinary(max) 数据。  
  
## <a name="sqlclient-support-for-filestream"></a>SqlClient 对 FILESTREAM 的支持  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] SQL Server 数据提供程序<xref:System.Data.SqlClient>，支持对 FILESTREAM 数据使用读取和写入<xref:System.Data.SqlTypes.SqlFileStream>类中定义<xref:System.Data.SqlTypes>命名空间。 `SqlFileStream` 继承自 <xref:System.IO.Stream> 类，该类提供了用于读写数据流的方法。 从流读取数据可将数据从流传输到一个数据结构，例如一个字节数组。 写入操作可将数据从该数据结构传输到一个流。  
  
### <a name="creating-the-sql-server-table"></a>创建 SQL Server 表  
 下列 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句将创建一个名为 employees 的表并插入一行数据。 启用 FILESTREAM 存储之后，你可以将此表与下面的代码示例结合使用。 SQL Server 联机丛书中的资源的链接位于本主题末尾处。  
  
```  
CREATE TABLE employees  
(  
  EmployeeId INT  NOT NULL  PRIMARY KEY,  
  Photo VARBINARY(MAX) FILESTREAM  NULL,  
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL  
  UNIQUE DEFAULT NEWID()  
)  
GO  
Insert into employees  
Values(1, 0x00, default)  
GO  
```  
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>示例：读取、覆盖和插入 FILESTREAM 数据  
 下面的示例演示如何从 FILESTREAM 读取数据。 示例代码获取文件的逻辑路径，并将 `FileAccess` 设置为 `Read`，而将 `FileOptions` 设置为 `SequentialScan`。 然后，示例代码将字节从 SqlFileStream 读入到缓存区中， 最后将这些字节写入到控制台窗口。  
  
 该示例还演示如何将数据写入 FILESTREAM（其中，所有现有的数据都将被覆盖）。 示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `Write`，而将 `FileOptions` 设置为 `SequentialScan`。 将一个单字节写入到 `SqlFileStream`，从而替换文件中的任何数据。  
  
 该示例还演示了如何通过使用 Seek 方法将数据追加到文件末尾将数据写入 FILESTREAM。 示例代码获取文件的逻辑路径，然后创建 `SqlFileStream`，并将 `FileAccess` 设置为 `ReadWrite`，而将 `FileOptions` 设置为 `SequentialScan`。 示例代码使用 Seek 方法找到文件结尾，并将一个单字节追加到现有的文件中。  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Data;  
using System.IO;  
  
namespace FileStreamTest  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");  
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for the file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Read the contents as bytes and write them to the console  
                            for (long index = 0; index < fileStream.Length; index++)  
                            {  
                                Console.WriteLine(fileStream.ReadByte());  
                            }  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file   
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        // Create the SqlFileStream  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Write a single byte to the file. This will  
                            // replace any data in the file.  
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
        }  
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
        {  
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))  
            {  
                connection.Open();  
  
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);  
  
                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);  
                command.Transaction = tran;  
  
                using (SqlDataReader reader = command.ExecuteReader())  
                {  
                    while (reader.Read())  
                    {  
                        // Get the pointer for file  
                        string path = reader.GetString(0);  
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))  
                        {  
                            // Seek to the end of the file  
                            fileStream.Seek(0, SeekOrigin.End);  
  
                            // Append a single byte   
                            fileStream.WriteByte(0x01);  
                        }  
                    }  
                }  
                tran.Commit();  
            }  
  
        }  
    }  
}
```  
  
 另一个示例，请参阅[如何存储和二进制数据提取到文件流列](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str)。  
  
## <a name="resources-in-sql-server-books-online"></a>SQL Server 联机丛书中的资源  
 FILESTREAM 的完整文档位于 SQL Server 联机丛书中的下列部分中。  
  
|主题|描述|  
|-----------|-----------------|  
|[设计和实现 FILESTREAM 存储](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)|提供指向 FILESTREAM 文档和相关主题的链接。|  
|[FILESTREAM 概述](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)|介绍何时使用 FILESTREAM 存储以及该存储如何将 SQL Server 数据库引擎与 NTFS 文件系统集成。|  
|[使用 FILESTREAM 存储入门](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)|介绍如何在 SQL Server 的实例上启用 FILESTREAM，如何创建数据库和表以存储 FILESTREAM 数据以及如何操作包含 FILESTREAM 数据的行。|  
|[在客户端应用程序中使用 FILESTREAM 存储](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)|介绍用于处理 FILESTREAM 数据的 Win32 API 函数。|  
|[FILESTREAM 与其他 SQL Server 功能](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|提供将 FILESTREAM 数据与 SQL Server 的其他功能一起使用时的注意事项、准则和限制。|  
  
## <a name="see-also"></a>请参阅  
 [SQL Server 数据类型和 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [在 ADO.NET 中检索和修改数据](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [代码访问安全性和 ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [SQL Server 二进制和大值数据](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
