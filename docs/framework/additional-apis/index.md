---
title: 其他类库和 API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 049268c29946e95ca7bb194f6cae38baf8f060f6
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180260"
---
# <a name="additional-class-libraries-and-apis"></a>其他类库和 API

.NET Framework 在不断发展。 若要改善跨平台开发，并尽早引入新功能，带外 (OOB) 发布新功能。 本主题列出了我们提供了有关文档的 OOB 项目。  
  
此外，一些库面向 .NET Framework 的特定平台或实现。 例如，<xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用.NET Framework 开发的 UWP 应用。 本主题还列出了以下库。  
  
## <a name="oob-projects"></a>OOB 项目
  
| 项目 | 描述 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 提供的集合数是线程安全的，并且保证决不会更改该集合的内容。 |
| <xref:System.Net.Http.WinHttpHandler> | 基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。 |
| [System.Numerics.Vectors](https://msdn.microsoft.com/library/mt452176.aspx) | 提供可利用基于 SIMD 硬件的加速的向量类型库。| 
| <xref:System.Threading.Tasks.Dataflow> | TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。 |  

## <a name="platform-specific-libraries"></a>特定于平台的库
  
| 项目 | 描述 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | 扩展了<xref:System.Text.EncodingProvider>类，以使代码页编码可用于面向通用 Windows 平台的应用。 |  
  
## <a name="private-apis"></a>私有 API  

这些 API 支持产品基础结构，不应/不支持在代码中直接使用。  
  
| API 名称 |
| -------- |
| [System.Net.Connection 类](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList 字段](../../../docs/framework/additional-apis/m_writelist.md) |
| [System.Net.ConnectionGroup 类](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList 字段](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.Net.CoreResponseData 类](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders 字段](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [System.Net.CoreResponseData.m\_StatusCode 字段](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [System.Net.HttpWebRequest。\_AutoRedirects 字段](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.HttpWebRequest。\_CoreResponse 字段](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [System.Net.HttpWebRequest。\_HttpResponse 字段](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList 字段](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable 字段](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes 字段](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor 类](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor 类](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>请参阅

[.NET Framework 和带外版本](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
