---
title: Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: a7839b60dbad7919a644c196a1c63f6bc46fb5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492944"
---
# <a name="out-of-order-message-processing"></a>Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden. Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>-Aktivität erwartet eine bestimmte Nachricht. Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet. Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel-Aktivität durchgeführt. Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.  Die außerhalb der Reihenfolge-Nachricht, die in der Windows Communication Foundation (WCF)-Funktion verarbeitet wird, können Sie einen Workflow dieser Art ganz ohne die Komplexität geschachtelter Parallel-Aktivitäten erstellen. Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge wird nur unterstützt, auf Kanäle, die Unterstützung von <xref:System.ServiceModel.Channels.ReceiveContext> wie z. B. die WCF-MSMQ-Bindungen.  
  
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
   <!—the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
