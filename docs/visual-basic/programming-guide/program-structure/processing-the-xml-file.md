---
title: 处理 XML 文件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 524a54443b8f2365252f11282ca29fc492bef351
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398568"
---
# <a name="processing-the-xml-file-visual-basic"></a>处理 XML 文件 (Visual Basic)
编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。 (有关如何标记代码的信息，请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)。)ID 字符串唯一标识构造。 处理 XML 文件的程序可以使用 ID 字符串来标识对应[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]元数据/反射项目。  
  
 XML 文件不是代码的你; 的分层表示形式它是具有每个元素生成的 ID 的平面列表。  
  
 编译器在生成 ID 字符串时应遵循以下规则：  
  
-   字符串不得包含空格。  
  
-   ID 字符串的第一部分标识被标识的成员类型，单个字符后跟一个冒号。 使用以下成员类型。  
  
|字符|描述|  
|---|---|  
|N|namespace<br /><br /> 无法将文档注释添加到一个命名空间，但您可以使 CREF 引用它们，在支持的情况。|  
|T|类型： `Class`， `Module`， `Interface`， `Structure`， `Enum`， `Delegate`|  
|F|字段： `Dim`|  
|P|属性： `Property` （包括默认属性）|  
|M|方法： `Sub`， `Function`， `Declare`， `Operator`|  
|E|事件： `Event`|  
|!|错误字符串<br /><br /> 字符串的其余部分提供有关错误的信息。 Visual Basic 编译器错误的生成信息无法解析的链接。|  
  
-   第二部分`String`是开始的命名空间的根处的项的完全限定的名称。 用句点分隔的项、 其封闭类型和命名空间名称。 如果项本身的名称包含句点，它们替换为数字符号 （#）。 假定项，因此无法直接在其名称中包含数字符号。 例如，完全限定的名称`String`构造函数将是`System.String.#ctor`。  
  
-   对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。 如果没有任何自变量，则不会出现括号。 确保自变量之间用逗号分隔。 每个自变量的编码直接遵循中的编码方式[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]签名。  
  
## <a name="example"></a>示例  
 下面的代码演示如何的 ID 字符串类并生成其成员。  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
