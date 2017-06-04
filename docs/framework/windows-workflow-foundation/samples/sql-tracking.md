---
title: "SQL-Nachverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# SQL-Nachverfolgung
Dieses Beispiel veranschaulicht, wie ein benutzerdefinierter SQL\-Nachverfolgungsteilnehmer, der Nachverfolgungsdatensätze in eine SQL\-Datenbank schreibt, geschrieben wird.[!INCLUDE[wf](../../../../includes/wf-md.md)] stellt die Workflownachverfolgung bereit, um einen Einblick in die Ausführung einer Workflowinstanz zu erhalten.Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Workflownachverfolgung finden Sie unter [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben.In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express\-Instanz verwendet wird.Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.  
  
2.  Erstellen Sie die SQL Server\-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis \(\\WF\\Basic\\Tracking\\SqlTracking\\CS\\Scripts\) ausführen.Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.  
  
    > [!NOTE]
    >  Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express.Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".  
  
3.  Öffnen Sie "SqlTrackingSample.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
4.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
5.  Drücken Sie F5, um die Anwendung auszuführen.  
  
     Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.  
  
6.  Klicken Sie im Browser auf "StockPriceService.xamlx".  
  
7.  Der Browser zeigt die Seite "StockPriceService" an, die die WSDL\-Adresse des lokalen Diensts enthält.Kopieren Sie diese Adresse.  
  
     Ein Beispiel für die WSDL\-Adresse des lokalen Diensts ist "http:\/\/localhost:65193\/StockPriceService.xamlx?wsdl".  
  
8.  Führen Sie mithilfe von [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] den WCF\-Testclient \(WcfTestClient.exe\) aus.Er befindet im Verzeichnis "Microsoft Visual Studio 10.0 \\Common7\\IDE".  
  
9. Klicken Sie im WCF\-Testclient auf das Menü **Datei**, und wählen Sie **Dienst hinzufügen** aus.Fügen Sie die lokale Dienstadresse in das Textfeld ein.Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
10. Doppelklicken Sie im WCF\-Testclient auf **GetStockPrice**.Dadurch wird der `GetStockPrice`\-Vorgang geöffnet, der einen Parameter verwendet; geben Sie den Wert `Contoso` ein, und klicken Sie auf **Aufrufen**.  
  
11. Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL\-Datenbank geschrieben.Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu SQL Server Management Studio finden Sie unter [Einführung in SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).SQL Server 2008 Management Studio Express kann [hier](http://go.microsoft.com/fwlink/?LinkId=180520) heruntergeladen werden.Durch Ausführen einer Select\-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.  
  
#### So installieren Sie das Beispiel aus  
  
1.  Führen Sie das Skript "Tdrackingcleanup.cmd" im Beispielverzeichnis \(\\WF\\Basic\\Tracking\\SqlTracking\) aus.  
  
    > [!NOTE]
    >  "Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen.Wenn Sie eine andere SQL Server\-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)