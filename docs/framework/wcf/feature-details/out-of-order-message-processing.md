---
title: Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141400"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="5a678-102">Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="5a678-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="5a678-103">Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a678-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="5a678-104">Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>-Aktivität erwartet eine bestimmte Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5a678-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="5a678-105">Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet.</span><span class="sxs-lookup"><span data-stu-id="5a678-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="5a678-106">Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel-Aktivität durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5a678-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="5a678-107">Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.</span><span class="sxs-lookup"><span data-stu-id="5a678-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="5a678-108">Die Out-of-Order-Nachricht, die in Windows Communication Foundation (WCF)-Funktion verarbeitet wird, können Sie einen Workflow dieser Art ohne die Komplexität geschachtelter Parallel-Aktivitäten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a678-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="5a678-109">Out-of-Order-Nachrichtenverarbeitung wird nur unterstützt, auf die Kanäle, unterstützen <xref:System.ServiceModel.Channels.ReceiveContext> wie z. B. die WCF-MSMQ-Bindungen.</span><span class="sxs-lookup"><span data-stu-id="5a678-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="5a678-110">Aktivieren der Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="5a678-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="5a678-111">Sie aktivieren die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge, indem Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft für WorkflowService auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5a678-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="5a678-112">Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft im Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="5a678-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="5a678-113">Sie können das `AllowBufferedReceive`-Attribut auch auf einen Workflowdienst in XAML anwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a678-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a678-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a678-114">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="5a678-115">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="5a678-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="5a678-116">Warteschlangen und zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="5a678-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
