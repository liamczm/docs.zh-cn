---
title: 扩展 WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 24ad74f04a3ac31d0b0d0d87f0d74f88c0521f50
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803700"
---
# <a name="extending-wcf"></a>扩展 WCF
Windows Communication Foundation (WCF)，可修改和扩展运行的时组件，以便能够准确地控制和扩展基于服务的应用程序。 本节中的主题深入探讨了有关扩展性体系结构的内容。 有关基本编程的详细信息，请参阅[基本 WCF 编程](../../../../docs/framework/wcf/basic-wcf-programming.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [扩展 ServiceHost 和服务模块层](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 服务模型层负责从基础通道拉取传入的消息，将它们翻译成应用程序代码形式的方法调用，并将结果发送回调用方。  服务模型扩展将修改或实现执行或通信行为，功能包括调度程序功能、自定义行为、消息和参数侦听以及其他扩展性功能。  
  
 [扩展绑定](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 绑定是描述连接到终结点所需的通信详细信息的对象。 绑定扩展或自定义绑定实现了支持应用程序功能所需的自定义通信功能。  
  
 [扩展通道层](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 通道层位于服务模型层的下方并且负责客户端和服务之间的消息交换。 通道扩展可以实现新的协议功能，例如安全性。 通道扩展也可以传输功能，例如实现新的网络传输以传送 SOAP 消息。  
  
 [扩展安全性](../../../../docs/framework/wcf/extending/extending-security.md)  
 在 WCF 中的安全包含的传输安全 （完整性、 保密性和身份验证），访问控制 （授权） 和审核。 类中找到`IdentityModel`命名空间由 WCF 用于访问控制。 了解安全体系结构使您可以创建自定义声明类型，以便容纳自定义访问控制系统。  
  
 [扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 WCF 元数据系统是一组类和表示实现基于服务的应用程序所需的元数据的接口。 修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。  
  
 [扩展编码器和序列化程序](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 编码器和序列化程序将数据从一种形式转换成另一种形式。 本节中的主题讨论如何扩展已提供的类以满足特殊需求。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>相关章节  
 [基本 WCF 编程](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [WCF 功能详细信息](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [指南与最佳做法](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
