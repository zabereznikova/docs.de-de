---
title: "Ausf&#252;hren eines Workflows in einem imperativen TransactionScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Ausf&#252;hren eines Workflows in einem imperativen TransactionScope
In diesem Beispiel wird gezeigt, wie ein Workflow mit <xref:System.Activities.WorkflowInvoker> unter einer <xref:System.Transactions.Transaction> von imperativem C\#\-Code ausgeführt wird.  
  
## Beispieldetails  
 In imperativem C\#\-Code wird der <xref:System.Transactions.TransactionScope> verwendet, um einen Satz von Aufgaben zu kapseln, die unter der gleichen Transaktion ausgeführt werden.Der <xref:System.Transactions.TransactionScope> funktioniert, indem er eine Ambient\-Transaktion erstellt und die <xref:System.Transactions.Transaction.Current%2A>\-Eigenschaft initialisiert, auf die dann von beliebigen Aufgaben zugegriffen werden kann, die in diesem Thread ausgeführt werden.  
  
 Um ein entsprechendes Verhalten im Workflow zu erhalten, muss die Laufzeit die zusätzliche Aufgabe des Initialisierens der <xref:System.Transactions.Transaction.Current%2A> übernehmen, bevor die einzelnen Aktivitäten ausgeführt werden, da ein Workflow keine Threadaffinität zwischen Aktivitäten aufrechterhält.Mit dieser Laufzeitunterstützung ist das resultierende Verhalten, dass alle Aktivitäten garantiert unter dem Kontext der Ambient\-Transaktion ausgeführt werden, der vom <xref:System.Transactions.TransactionScope> erstellt wird, wenn ein Workflow mit <xref:System.Activities.WorkflowInvoker> innerhalb eines <xref:System.Transactions.TransactionScope> ausgeführt wird.  
  
 Ein Workflow kann nur eine einzelne Ambient\-Transaktion für jede Workflowinstanz aufweisen; geschachtelte Transaktionen sind nicht verfügbar.Auch wenn der Workflow eine <xref:System.Activities.Statements.TransactionScope>\-Aktivität enthält, wird dadurch keine neue innere Transaktion erstellt.Stattdessen wird dadurch die Ambient\-Transaktion wiederverwendet, die außerhalb des Workflows erstellt wurde.  
  
 Das Beispiel beginnt einen neuen <xref:System.Transactions.Transaction.TransactionScope>, druckt die Transaktions\-ID und beginnt mit <xref:System.Activities.WorkflowInvoker> einen Workflow.Der Workflow druckt die Transaktions\-ID erneut und zeigt an, dass es sich um die gleiche Transaktion handelt, führt dann einen <xref:System.Activities.Statements.TransactionScope> aus, und wird dann beendet.Der <xref:System.Activities.WorkflowInvoker.Invoke%2A>\-Anruf bei <xref:System.Activities.WorkflowInvoker> ist synchron, damit der ursprüngliche Thread blockiert wird, bis der Workflow abgeschlossen ist.Sobald der Workflow vollständig ist, wird die Transaktion abgeschlossen und Ressourcen werden freigegeben.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ImperativeTransactionSample.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`  
  
## Siehe auch