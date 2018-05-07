---
title: Transaktive Warteschlangen
ms.date: 03/30/2017
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
ms.openlocfilehash: b125158a113079d87eb6926393d5a2b5fe326824
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="transacted-queues"></a>Transaktive Warteschlangen
Dieses Beispiel zeigt die Vorgehensweise beim Integrieren von Warteschlangen und Transaktionen in Windows Workflow Foundation (WF), zuverlässige und skalierbare Dienste zu erstellen. Ein <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` wird im clientworkflow verwendet, zum Senden der Nachricht an eine Warteschlange unter einer Transaktion mithilfe der <xref:System.ServiceModel.NetMsmqBinding>. Ein <xref:System.ServiceModel.Activities.TransactedReceiveScope> wird auf dem Server verwendet, um Meldungen von der Warteschlange zu empfangen und den Zustand des Workflows unter der gleichen Transaktion zu aktualisieren.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive> und inhaltsbasierte Korrelation.  
  
## <a name="discussion"></a>Diskussion  
 Zur Veranschaulichung der in diesem Beispiel behandelten Funktionen wird ein `RewardsPoints`-Workflowdienst erstellt, der die für ein bestimmtes Konto verdienten und verwendeten Punkte nachverfolgt. Der Client verwendet <xref:System.Activities.WorkflowInvoker>, um das Übermitteln unterschiedlicher Anforderungen an die Warteschlange zu simulieren. Zum Bereitstellen einer Meldung für eine Warteschlange unter einer Transaktion kann die <xref:System.ServiceModel.Activities.Send>-Aktivität im <xref:System.Activities.Statements.TransactionScope.Body%2A> eines <xref:System.Activities.Statements.TransactionScope> platziert werden. In diesem Beispiel wird zuerst der Client und dann der Server ausgeführt, um zu veranschaulichen, wie in der Warteschlange befindliche Meldungen die Client- und Serveranwendungen entkoppeln können.  
  
 Sobald der Client abgeschlossen wurde, wird der Dienst konfiguriert und gehostet. Sobald er geöffnet wird, fängt er an, die Meldungen zu verarbeiten, die bereits in der Warteschlange platziert wurden. Jede Meldung wird unter der gleichen Servertransaktion empfangen und verarbeitet. In diesem Beispiel ist die erste empfangene Meldung eine `CreateAccount`-Anforderung, die die Instanz erstellt und die Inhaltskorrelation auf Grundlage des Kontonamens initialisiert, der als Teil der Anforderungsmeldung übergeben wurde. Zum Modellieren der Art des Dienstes, die Sie unter realen Bedingungen erwarten können, werden die folgenden beiden <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivitäten, die die `AddPoints`-Meldung und die `UsePoints`-Meldung verarbeiten, in parallelen Verzweigungen in eine `while`-Schleife eingefügt, damit diese Meldungen immer wieder in beliebiger Reihenfolge verarbeitet werden können.  
  
 <xref:System.Activities.Statements.TransactionScope> und <xref:System.ServiceModel.Activities.TransactedReceiveScope> weisen jeweils am Ende ihrer Bereiche einen impliziten Persistenzpunkt auf. Die Verwendung dieser Aktivitäten in [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in Kombination mit Warteschlangen ist daher eine zuverlässige Möglichkeit, um den Workflow von einem konsistenten Zustand in den nächsten zu verschieben und gleichzeitig sicherzustellen, dass keine Meldungen verloren gehen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Installieren und konfigurieren Sie MSMQ. Finden Sie unter [Installieren von Message Queuing](http://go.microsoft.com/fwlink/?LinkId=178526) Details.  
  
2.  Stellen Sie sicher, dass MSDTC ausgeführt wird, indem Sie den folgenden Befehl in einer Befehlszeile ausführen. `net start msdtc`  
  
3.  Kompilieren Sie das Projekt, und öffnen Sie die ausführbare Datei, oder öffnen Sie das Projekt in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und wählen Sie eine Startoption im Debugmenü aus. Zuerst wird die Warteschlange erstellt; anschließend wird der Client ausgeführt, und Meldungen werden an die Warteschlange übermittelt. Schließlich wird der Dienst gestartet, und die Meldungen werden verarbeitet. Zum Beenden des Programms drücken Sie die EINGABETASTE.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`
