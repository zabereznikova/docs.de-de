---
title: Geordnete Verarbeitung von Nachrichten im Single-Parallelitätsmodus
ms.date: 03/30/2017
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
ms.openlocfilehash: ecabb9a6e838b0137c538d76c554646356ea87f5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991503"
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Geordnete Verarbeitung von Nachrichten im Single-Parallelitätsmodus
WCF gibt keine Garantie für die Reihenfolge, in der Nachrichten verarbeitet werden, es sei denn, der zugrunde liegende Kanal ist Sitzungs basiert.  Beispielsweise kann ein WCF-Dienst, der msmqinputchannel verwendet, bei dem es sich nicht um einen Sitzungs basierten Kanal handelt, Nachrichten in der richtigen Reihenfolge verarbeiten. Es gibt einige Situationen, in denen ein Entwickler möglicherweise das Verarbeitungs Verhalten in der Bestellung, aber keine Sitzungen verwenden möchte. In diesem Thema wird beschrieben, wie Sie dieses Verhalten konfigurieren, wenn ein Dienst im Single-Parallelitätsmodus ausgeführt wird.  
  
## <a name="in-order-message-processing"></a>Verarbeiten von Nachrichten in der normalen Reihenfolge  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> wurde ein neues Attribut mit dem Namen <xref:System.ServiceModel.ServiceBehaviorAttribute> hinzugefügt. Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> auf true<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> und <xref:System.ServiceModel.ConcurrencyMode.Single> auf  festgelegt ist, werden an den Dienst gesendete Nachrichten in der normalen Reihenfolge verarbeitet. Der folgende Codeausschnitt veranschaulicht, wie diese Attribute festgelegt werden.  
  
```csharp
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
