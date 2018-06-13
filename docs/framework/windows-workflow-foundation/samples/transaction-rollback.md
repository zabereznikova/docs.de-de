---
title: Transaktionsrollback
ms.date: 03/30/2017
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
ms.openlocfilehash: 15333b159625f07449b0a93634a1a9a854614a57
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517156"
---
# <a name="transaction-rollback"></a>Transaktionsrollback
Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte <xref:System.Activities.NativeActivity> erstellt wird, die auf den Ambient-<xref:System.Activities.RuntimeTransactionHandle> zugreift, um die Ambient-Transaktion abzurufen und sie explizit zurückzusetzen.  
  
## <a name="sample-details"></a>Beispieldetails  
 Im Workflow wird eine Transaktion automatisch abgeschlossen, wenn der äußerste <xref:System.Activities.Statements.TransactionScope> oder <xref:System.ServiceModel.Activities.TransactedReceiveScope> abgeschlossen wird.  Eine Transaktion wird implizit zurückgesetzt, wenn eine nicht behandelte Ausnahme über die Bereichsgrenze hinausgeht. Es kann möglicherweise jedoch sinnvoll sein, explizit eine Transaktion ohne Auslösen einer Ausnahme zurückzusetzen. In diesem Fall können Sie die benutzerdefinierte Rollbackaktivität wie die in diesem Beispiel verwenden, um die Ambient-Transaktion explizit abzubrechen und einen optionalen Ausnahmegrund bereitzustellen.  
  
 Die `RollbackActivity` ist eine <xref:System.Activities.NativeActivity>, da Zugriff auf die Ausführungseigenschaften erforderlich ist, um den Ambient-<xref:System.Activities.RuntimeTransactionHandle> abzurufen. In der `Execute`-Methode wird der <xref:System.Activities.RuntimeTransactionHandle> abgerufen und überprüft, ob er `null` ist. Damit wird angegeben, dass die Aktivität ohne Ambient-Laufzeittransaktion verwendet wurde. Dann wird die Transaktion abgerufen und wieder überprüft, ob `null` vorhanden ist. Es ist möglich, einen Ambient-<xref:System.Activities.RuntimeTransactionHandle> zu bekommen, ohne eine Laufzeittransaktion zu initialisieren. Schließlich wird die Transaktion abgebrochen, indem <xref:System.Transactions.Transaction.Rollback%2A> aufgerufen und eine vom Benutzer bereitgestellte Ausnahme oder eine generische Ausnahme angegeben wird, die besagt, dass die Aktivität die Transaktion zurückgesetzt hat.  
  
 Der Beispielworkflow besteht aus einem <xref:System.Activities.Statements.TransactionScope>, dessen Text den Transaktionsstatus ausgibt, bevor und nachdem `RollbackActivity` ausgeführt wurde. Beachten Sie, dass, obwohl die Transaktion zurückgesetzt wurde, der <xref:System.Activities.Statements.TransactionScope> bis zum Abschluss ausgeführt wird und der Workflow nicht abgebrochen wird, bis der Text abgeschlossen ist. Der Workflow wird abgebrochen, da die <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>-Eigenschaft standardmäßig auf `true` festgelegt ist.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Laden Sie die Projektmappe "TransactionRollback.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Anwendung auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktionen](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)
