---
title: "Verarbeiten von Nachrichten au&#223;erhalb der normalen Reihenfolge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Verarbeiten von Nachrichten au&#223;erhalb der normalen Reihenfolge
Workflowdienste können davon abhängig sein, dass Nachrichten in einer bestimmten Reihenfolge gesendet werden.Ein Workflowdienst enthält eine oder mehrere <xref:System.ServiceModel.Activities.Receive>\-Aktivitäten, und jede <xref:System.ServiceModel.Activities.Receive>\-Aktivität erwartet eine bestimmte Nachricht.Ohne bestimmte Transportübermittlungsgarantien kann es vorkommen, dass von Clients gesendete Nachrichten verzögert und in einer Reihenfolge gesendet werden, die der Workflowdienst ggf. nicht erwartet.Das Implementieren eines Workflowdiensts, der das Senden von Nachrichten in einer bestimmten Reihenfolge nicht erfordert, wird normalerweise mithilfe einer Parallel\-Aktivität durchgeführt.Bei einem komplizierteren Anwendungsprotokoll würde der Workflow schnell sehr komplex werden.Mit der Funktion zur Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie einen Workflow dieser Art ganz ohne die Komplexität geschachtelter Parallel\-Aktivitäten erstellen.Die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge wird nur auf Kanälen unterstützt, die <xref:System.ServiceModel.Channele.ReceiveContext> unterstützen, z. B. die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-MSMQ\-Bindungen.  
  
## Aktivieren der Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge  
 Sie aktivieren die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge, indem Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>\-Eigenschaft für WorkflowService auf `true` festlegen.Im folgenden Codebeispiel wird veranschaulicht, wie Sie die <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A>\-Eigenschaft im Code festlegen.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
  
```  
  
 Sie können das `AllowBufferedReceive`\-Attribut auch auf einen Workflowdienst in XAML anwenden, wie im folgenden Beispiel gezeigt.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.ReceiveContext>   
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)