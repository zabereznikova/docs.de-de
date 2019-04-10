---
title: Dokumentgenehmigungsprozess
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: dfc2e0a12d053733823427ac50066b1e4a0f97aa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318467"
---
# <a name="document-approval-process"></a>Dokumentgenehmigungsprozess
Dieses Beispiel veranschaulicht die Verwendung von vielen Features von Windows Workflow Foundation (WF) und Windows Communication Foundation (WCF) miteinander aus. Zusammen implementieren sie ein Szenario für einen Dokumentgenehmigungsprozess. Eine Clientanwendung kann Dokumente zur Genehmigung senden und Dokumente genehmigen. Es ist eine Genehmigungs-Manager-Anwendung vorhanden, um die Kommunikation zwischen Clients zu unterstützen und die Regeln für den Genehmigungsprozess umzusetzen. Der Genehmigungsprozess ist ein Workflow, der mehrere Genehmigungsarten ausführen kann. Es sind Aktivitäten vorhanden, mit denen ein Einzelgenehmigungsprozess, ein Quorumgenehmigungsprozess (Prozentsatz aller Genehmiger) und ein komplexer Genehmigungsprozess, der aus einer Abfolge einer Quorumgenehmigung und einer Einzelgenehmigung besteht, abgerufen werden.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a>Beispieldetails  
 Die folgende Grafik veranschaulicht genehmigungsprozessworkflows Dokument:  
  
 ![Workflow für den Prozess zur Genehmigung von Dokumenten](./media/document-approval-process/document-approval-process.jpg)  
  
 Aus Sicht des Clients funktioniert der Genehmigungsprozess wie folgt:  
  
1. Ein Client wird ein Benutzer im Genehmigungsprozesssystem.  
  
2. Ein WCF-Client sendet an einen WCF-Dienst, der von der Genehmigungs-Manager-Anwendung gehostet wird.  
  
3. Dem Client wird eine eindeutige Benutzer-ID zurückgegeben. Der Client kann jetzt an Genehmigungsprozessen teilnehmen.  
  
4. Sobald der Client teilnimmt, kann er ein Dokument zur Genehmigung durch den Einzelgenehmigungs-, Quorumgenehmigungs- oder komplexen Genehmigungsprozess senden.  
  
5. Durch Klicken auf eine Schaltfläche in der Clientoberfläche wird eine Workflowinstanz in einem Workflowdiensthost gestartet.  
  
6. Der Workflow sendet eine Genehmigungsanforderung an die Genehmigungs-Manager-Anwendung.  
  
7. Der Workflow-Manager startet seinerseits einen Workflow, der einen Genehmigungsprozess darstellt.  
  
8. Sobald der Manager-Genehmigungsworkflow ausgeführt wird, werden die Ergebnisse an den Client zurückgesendet.  
  
9. Der Client zeigt die Ergebnisse an.  
  
10. Ein Client kann eine Genehmigungsanforderung empfangen und zu jedem Zeitpunkt auf die Anforderung antworten.  
  
11. Ein auf dem Client gehosteter WCF-Dienst kann eine genehmigungsanforderung von der Genehmigungs-Manager-Anwendung empfangen.  
  
12. Die Dokumentinformationen werden zum Review auf dem Client dargestellt.  
  
13. Der Benutzer kann das Dokument genehmigen oder ablehnen.  
  
14. Ein WCF-Client wird verwendet, um eine genehmigungsantwort an die Genehmigungs-Manager-Anwendung zu senden.  
  
 Aus Sicht der Genehmigungs-Manager-Anwendung funktioniert der Genehmigungsprozess wie folgt:  
  
1. Ein Client fordert an, am Genehmigungsprozesssystem teilzunehmen.  
  
2. Ein WCF-Dienst auf der Genehmigungs-Manager empfängt eine Anforderung zum Teil des genehmigungsprozesssystems zu werden.  
  
3. Für den Client wird eine eindeutige ID generiert. Die Benutzerinformationen werden in einer Datenbank gespeichert.  
  
4. Die eindeutige ID wird an den Benutzer zurückgesendet.  
  
5. Es wird eine Genehmigungsanforderung empfangen. Der Genehmigungs-Manager führt einen Genehmigungsprozess aus.  
  
6. Der Genehmigungs-Manager empfängt eine Genehmigungsanforderung, wodurch ein neuer Workflow gestartet wird.  
  
7. Abhängig vom Typ der Anforderung (einfach, Quorum oder komplex) wird eine andere Aktivität ausgeführt.  
  
8. Zum Senden der Genehmigungsanforderung an den Client zum Review und zum Empfangen der Antwort werden Sende- und Empfangsaktivitäten mit Korrelation verwendet.  
  
9. Das Ergebnis des Genehmigungsprozessworkflows wird an den Client gesendet.  
  
## <a name="using-the-sample"></a>Verwenden des Beispiels  
  
##### <a name="to-set-up-the-database"></a>So richten Sie die Datenbank ein  
  
1. Navigieren Sie aus einer Visual Studio 2010-Eingabeaufforderung mit Administratorberechtigungen zum Ordner DocumentApprovalProcess, und führen Sie Setup.cmd aus.  
  
##### <a name="to-set-up-the-application"></a>So richten Sie die Anwendung ein  
  
1. Öffnen Sie mit Visual Studio 2010 die DocumentApprovalProcess.sln-Projektmappendatei.  
  
2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3. Um die Projektmappe auszuführen, starten Sie die Genehmigungs-Manager-Anwendung per Rechtsklick auf das ApprovalManager-Projekt in der **Projektmappen-Explorer** und auf **Debuggen**->**starten**  neue Instanz von mit der rechten Maustaste.  
  
     Warten Sie auf die Bestätigung des Managers, dass dieser bereit ist.  
  
##### <a name="to-run-the-single-approval-scenario"></a>So führen Sie das Einzelgenehmigungsszenario aus  
  
1. Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.  
  
2. Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.  
  
3. Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie zwei Instanzen von ApprovalClient.exe aus.  
  
4. Klicken Sie auf **ermitteln**, warten Sie, bis die **abonnieren** Schaltfläche ist aktiviert.  
  
5. Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**. Verwenden Sie für einen Client `UserType1` und für den anderen den Typ `UserType2`.  
  
6. Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein. Klicken Sie auf **Genehmigung anfordern**.  
  
7. Im `UserType2`-Client wird ein Dokument, das auf Genehmigung wartet, angezeigt. Wählen Sie ihn, und drücken Sie die **genehmigen** oder **ablehnen**. Die Ergebnisse werden im `UserType1`-Client angezeigt.  
  
##### <a name="to-run-the-quorum-approval-scenario"></a>So führen Sie das Quorumgenehmigungsszenario aus  
  
1. Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.  
  
2. Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.  
  
3. Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie drei Instanzen von ApprovalClient.exe aus.  
  
4. Klicken Sie auf **ermitteln**, warten Sie, bis die **abonnieren** Schaltfläche ist aktiviert.  
  
5. Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**. Verwenden Sie für einen Client `UserType1` und für die anderen den Typ `UserType2`.  
  
6. Wählen Sie im `UserType1`-Client den Quorumgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein. Klicken Sie auf **Genehmigung anfordern**. Hierdurch wird angefordert, dass die beiden `UserType2`-Clients das Dokument genehmigen oder ablehnen. Während beide `UserType2`-Clients antworten müssen, muss nur ein Client das Dokument genehmigen, damit es genehmigt wird.  
  
7. In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt. Wählen Sie ihn, und drücken Sie die **genehmigen** oder **ablehnen**. Die Ergebnisse werden im `UserType1`-Client angezeigt.  
  
##### <a name="to-run-the-complex-approval-scenario"></a>So führen Sie das komplexe Genehmigungsszenario aus  
  
1. Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.  
  
2. Navigieren Sie zum Verzeichnis, das die Projektmappe enthält.  
  
3. Navigieren Sie zum Ordner ApprovalClient\Bin\Debug, und führen Sie vier Instanzen von ApprovalClient.exe aus.  
  
4. Klicken Sie auf **ermitteln**, warten Sie, bis die **abonnieren** Schaltfläche ist aktiviert.  
  
5. Geben Sie einen Benutzernamen ein, und klicken Sie auf **abonnieren**. Verwenden Sie für einen Client `UserType1`, für zwei Clients `UserType2` und für den vierten Client `UserType3`.  
  
6. Wählen Sie im `UserType1`-Client den Einzelgenehmigungstyp im Dropdownmenü aus, und geben Sie einen Dokumentnamen und -inhalt ein. Klicken Sie auf **Genehmigung anfordern**.  
  
7. In den `UserType2`-Clients wird ein Dokument, das auf Genehmigung wartet, angezeigt. Wählen Sie ihn, und drücken Sie die **genehmigen**, das Dokument wird zum Übergeben der `UserType3` Client.  
  
     Wenn das Dokument vom ersten `UserType2`-Quorum genehmigt wird, wird das Dokument an den `UserType3`-Client übergeben.  
  
8. Genehmigen Sie das Dokument im `UserType3`-Client, oder lehnen Sie es ab. Die Ergebnisse werden im `UserType1`-Client angezeigt.  
  
##### <a name="to-clean-up"></a>So führen Sie eine Bereinigung durch  
  
1. Klicken Sie an einer Visual Studio 2010-Eingabeaufforderung navigieren Sie zum Ordner DocumentApprovalProcess, und führen Sie "Cleanup.cmd" aus.
