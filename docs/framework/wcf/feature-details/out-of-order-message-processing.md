---
title: Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701241"
---
# <a name="out-of-order-message-processing"></a>Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden. Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>-Aktivität erwartet eine bestimmte Nachricht. Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet. Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel-Aktivität durchgeführt. Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.  Die Out-of-Order-Nachricht, die in Windows Communication Foundation (WCF)-Funktion verarbeitet wird, können Sie einen Workflow dieser Art ohne die Komplexität geschachtelter Parallel-Aktivitäten zu erstellen. Out-of-Order-Nachrichtenverarbeitung wird nur unterstützt, auf die Kanäle, unterstützen <xref:System.ServiceModel.Channels.ReceiveContext> wie z. B. die WCF-MSMQ-Bindungen.  
  
## <a name="enabling-out-of-order-message-processing"></a>Aktivieren der Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge  
 Sie aktivieren die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge, indem Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft für WorkflowService auf `true` festlegen. Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>-Eigenschaft im Code festlegen.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 Sie können das `AllowBufferedReceive`-Attribut auch auf einen Workflowdienst in XAML anwenden, wie im folgenden Beispiel gezeigt.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
