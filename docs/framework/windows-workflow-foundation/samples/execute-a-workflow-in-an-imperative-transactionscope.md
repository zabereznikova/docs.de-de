---
title: Ausführen eines Workflows in einem imperativen TransactionScope
ms.date: 03/30/2017
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
ms.openlocfilehash: 2744434e807664ca93b4f5bc27a1f3b89716ce87
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520169"
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>Ausführen eines Workflows in einem imperativen TransactionScope
In diesem Beispiel wird gezeigt, wie ein Workflow mit <xref:System.Activities.WorkflowInvoker> unter einer <xref:System.Transactions.Transaction> von imperativem C#-Code ausgeführt wird.  
  
## <a name="sample-details"></a>Beispieldetails  
 In imperativem C#-Code wird der <xref:System.Transactions.TransactionScope> verwendet, um einen Satz von Aufgaben zu kapseln, die unter der gleichen Transaktion ausgeführt werden. Der <xref:System.Transactions.TransactionScope> funktioniert, indem er eine Ambient-Transaktion erstellt und die <xref:System.Transactions.Transaction.Current%2A>-Eigenschaft initialisiert, auf die dann von beliebigen Aufgaben zugegriffen werden kann, die in diesem Thread ausgeführt werden.  
  
 Um ein entsprechendes Verhalten im Workflow zu erhalten, muss die Laufzeit die zusätzliche Aufgabe des Initialisierens der <xref:System.Transactions.Transaction.Current%2A> übernehmen, bevor die einzelnen Aktivitäten ausgeführt werden, da ein Workflow keine Threadaffinität zwischen Aktivitäten aufrechterhält. Mit dieser Laufzeitunterstützung ist das resultierende Verhalten, dass alle Aktivitäten garantiert unter dem Kontext der Ambient-Transaktion ausgeführt werden, der vom <xref:System.Activities.WorkflowInvoker> erstellt wird, wenn ein Workflow mit <xref:System.Transactions.TransactionScope> innerhalb eines <xref:System.Transactions.TransactionScope> ausgeführt wird.  
  
 Ein Workflow kann nur eine einzelne Ambient-Transaktion für jede Workflowinstanz aufweisen; geschachtelte Transaktionen sind nicht verfügbar. Auch wenn der Workflow eine <xref:System.Activities.Statements.TransactionScope>-Aktivität enthält, wird dadurch keine neue innere Transaktion erstellt. Stattdessen wird dadurch die Ambient-Transaktion wiederverwendet, die außerhalb des Workflows erstellt wurde.  
  
 Das Beispiel beginnt einen neuen <xref:System.Transactions.TransactionScope>, druckt die Transaktions-ID und beginnt mit <xref:System.Activities.WorkflowInvoker> einen Workflow. Der Workflow druckt die Transaktions-ID erneut und zeigt an, dass es sich um die gleiche Transaktion handelt, führt dann einen <xref:System.Activities.Statements.TransactionScope> aus, und wird dann beendet. Der <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Anruf bei <xref:System.Activities.WorkflowInvoker> ist synchron, damit der ursprüngliche Thread blockiert wird, bis der Workflow abgeschlossen ist. Sobald der Workflow vollständig ist, wird die Transaktion abgeschlossen und Ressourcen werden freigegeben.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ImperativeTransactionSample.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`