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
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="001bc-102">Geordnete Verarbeitung von Nachrichten im Single-Parallelitätsmodus</span><span class="sxs-lookup"><span data-stu-id="001bc-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="001bc-103">WCF gibt keine Garantie für die Reihenfolge, in der Nachrichten verarbeitet werden, es sei denn, der zugrunde liegende Kanal ist Sitzungs basiert.</span><span class="sxs-lookup"><span data-stu-id="001bc-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="001bc-104">Beispielsweise kann ein WCF-Dienst, der msmqinputchannel verwendet, bei dem es sich nicht um einen Sitzungs basierten Kanal handelt, Nachrichten in der richtigen Reihenfolge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="001bc-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="001bc-105">Es gibt einige Situationen, in denen ein Entwickler möglicherweise das Verarbeitungs Verhalten in der Bestellung, aber keine Sitzungen verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="001bc-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="001bc-106">In diesem Thema wird beschrieben, wie Sie dieses Verhalten konfigurieren, wenn ein Dienst im Single-Parallelitätsmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="001bc-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="001bc-107">Verarbeiten von Nachrichten in der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="001bc-107">In-order Message Processing</span></span>  
 <span data-ttu-id="001bc-108"><xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> wurde ein neues Attribut mit dem Namen <xref:System.ServiceModel.ServiceBehaviorAttribute> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="001bc-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="001bc-109">Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> auf true<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> und <xref:System.ServiceModel.ConcurrencyMode.Single> auf  festgelegt ist, werden an den Dienst gesendete Nachrichten in der normalen Reihenfolge verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="001bc-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="001bc-110">Der folgende Codeausschnitt veranschaulicht, wie diese Attribute festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="001bc-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="001bc-111">Wenn <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> auf einen anderen Wert festgelegt ist, wird <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="001bc-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="001bc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="001bc-112">See also</span></span>

- [<span data-ttu-id="001bc-113">Sitzungen, Instanzerstellung und Parallelität</span><span class="sxs-lookup"><span data-stu-id="001bc-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
- [<span data-ttu-id="001bc-114">Parallelität</span><span class="sxs-lookup"><span data-stu-id="001bc-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
