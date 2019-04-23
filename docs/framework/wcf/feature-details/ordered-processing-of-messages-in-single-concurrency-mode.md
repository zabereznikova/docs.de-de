---
title: Geordnete Verarbeitung von Nachrichten im Single-Parallelitätsmodus
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: 785c2953e57eaf967209b0d9e52ab85a3a99c450
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229718"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Geordnete Verarbeitung von Nachrichten im Single-Parallelitätsmodus
WCF gibt keine Garantie bezüglich der Reihenfolge, in der Nachrichten verarbeitet werden, es sei denn, der zugrunde liegenden Kanal sitzungsbasierten ist.  Beispielsweise kann ein WCF-Dienst, der msmqinputchannel, der nicht um einen sitzungsbasierten Kanal ist verwendet, nicht Nachrichten nacheinander verarbeitet. Es gibt jedoch einige Situationen, in denen ein Entwickler kann die Verhalten bei der Verarbeitung in Reihenfolge nicht möchten jedoch Sitzungen verwenden. In diesem Thema wird beschrieben, wie Sie dieses Verhalten konfigurieren, wenn ein Dienst im Single-Parallelitätsmodus ausgeführt wird.  
  
## <a name="in-order-message-processing"></a>Verarbeiten von Nachrichten in der normalen Reihenfolge  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> wurde ein neues Attribut mit dem Namen <xref:System.ServiceModel.ServiceBehaviorAttribute> hinzugefügt. Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> auf true<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> und <xref:System.ServiceModel.ConcurrencyMode.Single> auf  festgelegt ist, werden an den Dienst gesendete Nachrichten in der normalen Reihenfolge verarbeitet. Der folgende Codeausschnitt veranschaulicht, wie diese Attribute festgelegt werden.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> auf einen anderen Wert festgelegt ist, wird <xref:System.InvalidOperationException> ausgelöst.  
  
## <a name="see-also"></a>Siehe auch

- [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [Parallelität](../../../../docs/framework/wcf/samples/concurrency.md)
