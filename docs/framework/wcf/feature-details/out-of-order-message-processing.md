---
title: Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7a5042e390231498de4f98abfc0e863cba199943
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248004"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="1e1c2-102">Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="1e1c2-102">Out-of-Order Message Processing</span></span>

<span data-ttu-id="1e1c2-103">Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="1e1c2-104">Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>-Aktivität erwartet eine bestimmte Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="1e1c2-105">Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="1e1c2-106">Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel-Aktivität durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="1e1c2-107">Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="1e1c2-108">Mit dem Feature für die Nachrichtenverarbeitung außerhalb der Reihenfolge in Windows Communication Foundation (WCF) können Sie einen solchen Workflow erstellen, ohne die Komplexität der in den Aktivitäten unter geclusterte parallelen Aktivitäten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="1e1c2-109">Die Verarbeitung von Nachrichten außerhalb der Reihenfolge wird nur für Kanäle unterstützt, die <xref:System.ServiceModel.Channels.ReceiveContext> die WCF-MSMQ-Bindungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="1e1c2-110">Aktivieren der Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="1e1c2-110">Enabling Out-Of-Order Message Processing</span></span>  

 <span data-ttu-id="1e1c2-111">Sie aktivieren die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge, indem Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft für WorkflowService auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="1e1c2-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="1e1c2-113">Sie können das `AllowBufferedReceive`-Attribut auch auf einen Workflowdienst in XAML anwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e1c2-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e1c2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e1c2-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="1e1c2-115">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="1e1c2-115">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="1e1c2-116">Warteschlangen und zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="1e1c2-116">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
