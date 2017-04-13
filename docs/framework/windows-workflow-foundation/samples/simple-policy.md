---
title: "Einfache Richtlinie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Einfache Richtlinie
Dieses Beispiel veranschaulicht, wie eine <xref:System.Workflow.Activities.PolicyActivity>\-Aktivität in einem Workflow verwendet wird.  
  
 Der sequenzielle Workflow in diesem Beispiel wird mit einer <xref:System.Workflow.Activities.PolicyActivity>\-Aktivität erstellt.Der Workflow definiert die Felder `orderValue`, `customerType` und `discount`, die zum Definieren eines Produktrabattworkflows verwendet werden.Die in der Regeldatei definierten Regeln legen einen Rabattwert fest, der auf `orderValue` und `customerType` basiert.`orderValue` und `customerType` sind in der `SimplePolicyWorkflow`\-Klassendefinition festgelegt und können geändert werden, um das Verhalten zu ändern.Der sich ergebende Rabatt wird in der Konsole im <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted>\-Ereignishandler, der in der `SimplePolicyWorkflow`\-Klasse definiert ist, ausgegeben.  
  
### So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG\+UMSCHALT\+B drücken.  
  
3.  Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG\+F5 drücken.  
  
### So führen Sie das Beispiel aus  
  
-   Führen Sie im Eingabeaufforderungsfenster des SDK die EXE\-Datei im Ordner "SimplePolicy\\bin\\debug" aus \(bzw. im Ordner "SimplePolicy\\bin" für die Visual Basic\-Version des Beispiels\), der sich unter dem Hauptordner des Beispiels befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren:  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## Siehe auch  
 <xref:System.Workflow.Activities.Rules.RuleSet>   
 <xref:System.Workflow.Activities.PolicyActivity>   
 [Erweiterte Richtlinie](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)