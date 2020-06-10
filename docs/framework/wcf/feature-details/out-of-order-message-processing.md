---
title: Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7930f26cf5957158a16d65085267cf1bab2e4504
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598722"
---
# <a name="out-of-order-message-processing"></a>Verarbeiten von Nachrichten außerhalb der normalen Reihenfolge
Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden. Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>-Aktivität erwartet eine bestimmte Nachricht. Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet. Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel-Aktivität durchgeführt. Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.  Mit dem Feature für die Nachrichtenverarbeitung außerhalb der Reihenfolge in Windows Communication Foundation (WCF) können Sie einen solchen Workflow erstellen, ohne die Komplexität der in den Aktivitäten unter geclusterte parallelen Aktivitäten zu erhöhen. Die Verarbeitung von Nachrichten außerhalb der Reihenfolge wird nur für Kanäle unterstützt, die <xref:System.ServiceModel.Channels.ReceiveContext> die WCF-MSMQ-Bindungen unterstützen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [Workflowdienste](workflow-services.md)
- [Warteschlangen und zuverlässige Sitzungen](queues-and-reliable-sessions.md)
