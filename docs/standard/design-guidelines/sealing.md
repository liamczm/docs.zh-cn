---
title: 密封
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44336909"
---
# <a name="sealing"></a>密封
面向对象的框架的功能之一是开发人员可以扩展和未预料到框架设计器的方式自定义它们。 这是设计的两个电源和可扩展的危险。 在设计您的框架，它，因此是非常重要时需要，仔细设计可扩展性以及限制可扩展性时这是很危险。  
  
 密封可以防止可扩展性的强大机制。 密封类或单个成员。 密封类，可阻止用户从类继承。 密封成员可阻止用户重写特定成员。  
  
 **X DO NOT** 密封类，而无需有充分的理由要这样做。  
  
 密封类，因为您不能将可扩展性方案不是一个充分的理由。 框架用户希望从类继承的各种 nonobvious 原因，例如，添加方便成员。 请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)有关 nonobvious 原因的示例用户想要继承的类型。  
  
 密封类充分的理由包括：  
  
-   类是一个静态类。 请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。  
  
-   类继承的受保护成员中存储安全敏感机密。  
  
-   类继承许多虚拟成员和密封它们单独的成本会超过保留的未密封的类的好处。  
  
-   类是需要非常快的运行时查找的属性。 密封的属性具有比未密封的略高性能级别。 请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。  
  
 **X DO NOT** 在密封类型中声明受保护或虚拟成员。  
  
 根据定义，不能从继承密封的类型。 这意味着不能调用密封类型上受保护的成员，并且不能重写密封类型上的虚方法。  
  
 **✓ CONSIDER** 密封重写的成员。  
  
 从引入虚拟成员可能导致问题，(中所述[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)) 适用于替代，尽管到略有一定程度上。 密封替代使您可以避免这些问题从继承层次结构中该点开始。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)
