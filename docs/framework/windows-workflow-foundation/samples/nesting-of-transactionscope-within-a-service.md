---
title: Schachteln von TransactionScope innerhalb eines Diensts
ms.date: 03/30/2017
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
ms.openlocfilehash: cf73c0c2d061f1c997a8ade5d7b2bf61887915ca
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591094"
---
# <a name="nesting-of-transactionscope-within-a-service"></a>Schachteln von TransactionScope innerhalb eines Diensts
Dieses Beispiel besteht aus zwei Szenarien, in denen veranschaulicht wird, wie die <xref:System.Activities.Statements.TransactionScope>-Aktivitätsinstanzen innerhalb eines Diensts behandelt werden. Zunächst wird die Transaktion mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität initiiert, um eine neue Transaktion auf dem Client zu erstellen, und mit <xref:System.ServiceModel.Activities.TransactedReceiveScope>, um die Lebensdauer von der Transaktion auf dem Server zu empfangen und zu bewerten. Das erste Szenario innerhalb des Diensts führt eine sekundäre <xref:System.Activities.Statements.TransactionScope>-Aktivität aus, um die Schachtelung der <xref:System.Activities.Statements.TransactionScope>-Aktivitäten innerhalb des Diensts zu veranschaulichen. Das zweite Szenario veranschaulicht, wie Timeouts innerhalb der geschachtelten <xref:System.Activities.Statements.TransactionScope>-Aktivitäten beachtet werden.  
  
## <a name="client-application"></a>Clientanwendung  
 Die Clientanwendung führt einen Workflow aus, der <xref:System.Activities.Statements.TransactionScope>-Aktivität startet, die verteilte Transaktions-ID ausgibt, eine Meldung an den Server sendet, die Transaktion übertragt, die Antwort empfängt, die verteilte Transaktions-ID erneut ausgibt und den Vorgang dann abschließt. Dies wird für jedes Dienstszenario einmal ausgeführt.  
  
## <a name="server-application"></a>Serveranwendung  
 Das Serverprojekt wird in <xref:System.ServiceModel.Activities.WorkflowServiceHost> gehostet, der den Endpunkt erstellt, der eine Überwachung auf die Meldung des Clients hin übernehmen soll. Der Workflow basiert auf dem <xref:System.ServiceModel.Activities.TransactedReceiveScope>, der die übertragene Transaktion vom Client empfängt, die verteilte Transaktions-ID ausgibt und dann eine zweite <xref:System.Activities.Statements.TransactionScope>-Aktivität ausführt. Im ersten Szenario wird die Transaktion erfolgreich abgeschlossen. Im zweiten Szenario ist der Text der <xref:System.Activities.Statements.TransactionScope>-Aktivität ist eine Verzögerung mit einer Länge von fünf Sekunden, und das Timeout für die Transaktion wurde auf zwei Sekunden festgelegt. Wenn das Timeout der Transaktion erreicht wird, wird die Transaktion abgebrochen.  
  
#### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus  
  
1.  Öffnen Sie die Projektmappe "TransactionServiceExample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Um die Projektmappe zu erstellen, drücken Sie STRG + UMSCHALT + B, oder wählen Sie **Projektmappe** aus der **erstellen** Menü.  
  
3.  Nachdem der Build erfolgreich war, mit der rechten Maustaste in der Projektmappe, und wählen **Startprojekte**. Wählen Sie im Dialogfeld **mehrere Startprojekte** und sicherzustellen, dass die Aktion für beide Projekte **starten**.  
  
4.  Drücken Sie F5, oder wählen Sie **Debuggen starten** aus der **Debuggen** Menü. Alternativ drücken Sie STRG + F5, oder wählen Sie **Starten ohne Debugging** aus der **Debuggen** Menü, um ohne Debuggen auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
