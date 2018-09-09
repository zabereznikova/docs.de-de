---
title: Transaktions-Konvoi-Bereich
ms.date: 03/30/2017
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
ms.openlocfilehash: fa1da6df5ad5256665610c9b3c2df7d706cef63c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44225161"
---
# <a name="transaction-convoy-scope"></a>Transaktions-Konvoi-Bereich
Anhand dieses Beispiels wird veranschaulicht, wie ein paralleles Konvoi-Meldungsaktivitätsmuster zusammen mit einem <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwendet wird, um ein Protokoll zu modellieren, bei dem in derselben Transaktion mehrere Vorgänge in beliebiger Reihenfolge auftreten können. Des Weiteren wird veranschaulicht, wie ein <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatisch eine neue Transaktion erstellt, wenn keine Transaktion an den Server weitergegeben wird, sodass der Client keine Transaktionen verwendet.  
  
 Das Beispiel besteht aus zwei Workflowprojekten, die jeweils Client und Server darstellen. Das Clientprojekt führt einen Workflow aus, der mit dem Senden einer Meldung zur Ausführung eines Bootstrap für den Serverworkflow beginnt. Dadurch wird eine Korrelation initialisiert und ein Transaktionsbereich für den Rest der Messagingaktivitäten gestartet. Die <xref:System.Activities.Statements.Sequence>-Aktivität des Clients enthält zunächst ein <xref:System.ServiceModel.Activities.Send>- und <xref:System.ServiceModel.Activities.ReceiveReply>-Paar und darauffolgend eine <xref:System.Activities.Statements.Parallel>-Aktivität mit drei Verzweigungen. Jede Verzweigung sendet eine unidirektionale Nachricht an den Server. Die <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>-Eigenschaft der <xref:System.Activities.Statements.Parallel>-Aktivität wird auf `false` festgelegt, damit alle drei Verzweigungen abgeschlossen werden.  
  
 Der Serverworkflow ist identisch mit dem Clientworkflow, mit der Ausnahme, dass die Messagingaktivitäten an die Serverseite der Kommunikation gerichtet und in einer <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität enthalten sind, damit alle Arbeitsabläufe innerhalb derselben Transaktion ausgeführt werden. Wenn der Server die erste Nachricht empfängt, wird eine Transaktion erstellt und für den Bereich des <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Texts als Ambient-Transaktion festgelegt, damit jede Aktivität in diesem Bereich auf die Transaktion zugreifen kann. Danach werden alle empfangenen Nachrichten parallel ausgeführt. Alle empfangenen Nachrichten müssen genau einmal ausgeführt werden, wie in der Abschlussbedingung für parallele Aktivitäten festgelegt. Am Ende des <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Texts ist ein impliziter Persistenzpunkt vorhanden, und der Persistenzvorgang wird ebenfalls innerhalb derselben Transaktion ausgeführt.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "ParallelConvoySample.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Stellen Sie sicher, dass beide Projekte als Startprojekte festgelegt sind.  
  
    1.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Projektmappe, und wählen Sie **Startprojekte**.  
  
    2.  Wählen Sie **mehrere Startprojekte** und stellen Sie sicher, die Aktion für beide Projekte nastaven NA hodnotu **starten**.  
  
4.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
     Der Server gibt die Meldung `Server is running` aus, die angibt, dass der Server bereit ist.  
  
     Drücken Sie bei geöffnetem Clientkonsolenfenster eine beliebige Taste, um das Beispiel zu starten.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`