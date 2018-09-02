---
title: Grundlegender TransactionScope
ms.date: 03/30/2017
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
ms.openlocfilehash: b3c673040d40ca91d8ab4a79e847d61e6f507ed1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415422"
---
# <a name="basic-transactionscope"></a>Grundlegender TransactionScope
Dieses Beispiel veranschaulicht die Schachtelung von <xref:System.Activities.Statements.TransactionScope>-Instanzen anhand von vier Szenarios. Im ersten Szenario wird die Aktivität eines Drittanbieters geschachtelt, deren Konstruktionsmethode dem Autor nicht bekannt ist. Im zweiten und dritten Szenario wird die Einhaltung von Timeouts veranschaulicht, und im letzten Szenario wird die <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>-Einstellung gezeigt.  
  
## <a name="nesting-of-transactionscopeactivity"></a>Schachteln der TransactionScopeActivity  
 Der Workflow des ersten Szenarios besteht aus einer Sequenz mit zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten und einem <xref:System.Activities.Statements.TransactionScope>-Element. Der <xref:System.Activities.Statements.TransactionScope>-Textkörper besteht aus zwei weiteren <xref:System.Activities.Statements.WriteLine>-Aktivitäten, einer benutzerdefinierten Aktivität zur Ausgabe des lokalen Bezeichners der Transaktion und einer Drittanbieteraktivität. Die Drittanbieteraktivität `TransactionScopeTest` enthält ein <xref:System.Activities.Statements.TransactionScope>-Element, was dem Workflowautor aber nicht bekannt ist. Dieses Szenario zeigt, dass <xref:System.Activities.Statements.TransactionScope>-Aktivitäten geschachtelt werden können.  
  
## <a name="time-outs"></a>Timeouts  
 Der Workflow des zweiten Szenarios ist nahezu identisch mit dem Workflow des ersten Szenarios. Die `TransactionScopeTest`-Aktivität wurde durch ein <xref:System.Activities.Statements.TransactionScope>-Element ersetzt. Der <xref:System.Activities.Statements.TransactionScope>-Textkörper ist eine Verzögerung mit einer Länge von fünf Sekunden, und das Timeout für die Transaktion wurde auf zwei Sekunden festgelegt. Das Timeout für den äußeren <xref:System.Activities.Statements.TransactionScope> ist auf zehn Sekunden festgelegt. Beachten Sie, dass der kleinste Timeoutwert des Bereichs Anwendung findet und ein Timeout der Transaktion auftritt.  
  
 Der Workflow des dritten Szenarios ist nahezu identisch mit dem Workflow des zweiten Szenarios. Die Verzögerungsaktivität wurde aus dem Textkörper des inneren <xref:System.Activities.Statements.TransactionScope> an die Position unmittelbar nach diesem Bereich im Textkörper des äußeren <xref:System.Activities.Statements.TransactionScope> verschoben. Es tritt nach wie vor ein Timeout auf, aber der Timeoutwert von zwei Sekunden im inneren <xref:System.Activities.Statements.TransactionScope> findet keine Anwendung mehr. Das Timeout tritt nach zehn Sekunden auf, wenn der Timeoutwert des äußeren <xref:System.Activities.Statements.TransactionScope> überschritten wird.  
  
## <a name="aborting-on-transaction-failure"></a>Abbrechen bei Transaktionsfehler  
 Dieser Workflow ist identisch mit dem Workflow im dritten Szenario, mit dem Unterschied, dass die Timeouts durch die <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>-Eigenschaft ersetzt wurden. Beachten Sie, dass die Flags aller inneren untergeordneten Elemente (falls festgelegt) dem äußeren <xref:System.Activities.Statements.TransactionScope> entsprechen müssen. Dies ist in diesem Szenario nicht der Fall, und beim Öffnen des Workflows wird eine Ausnahme ausgelöst.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe "BasicTransactionScopeSample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.  
  
3.  Nachdem der Build erfolgreich war, drücken Sie F5, oder wählen Sie **Debuggen starten** aus der **Debuggen** Menü. Alternativ drücken Sie STRG + F5, oder wählen Sie **Starten ohne Debugging** aus der **Debuggen** Menü, um ohne Debuggen auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`