---
title: SQL-Nachverfolgung
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: c1bb4492695df3ff803dff893de24453d7c03dfb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715563"
---
# <a name="sql-tracking"></a>SQL-Nachverfolgung
Dieses Beispiel zeigt, wie ein benutzerdefinierter SQL-nach Verfolgungs Teilnehmer geschrieben wird, der nach Verfolgungs Datensätze in eine SQL-Datenbank schreibt. Windows Workflow Foundation (WF) bietet eine Workflow Überwachung, um Einblick in die Ausführung einer Workflow Instanz zu erhalten. Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus. Weitere Informationen zur Workflow Nachverfolgung finden Sie unter [Workflow Verfolgung und Ablauf](../workflow-tracking-and-tracing.md)Verfolgung.

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben. In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express-Instanz verwendet wird. Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.

2. Erstellen Sie die SQL Server-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis (\WF\Basic\Tracking\SqlTracking\CS\Scripts) ausführen. Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.

    > [!NOTE]
    > Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express. Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".

3. Öffnen Sie sqltrackingsample. sln in Visual Studio 2010.

4. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.

5. Drücken Sie F5, um die Anwendung auszuführen.

     Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.

6. Klicken Sie im Browser auf "StockPriceService.xamlx".

7. Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält. Kopieren Sie diese Adresse.

     Ein Beispiel für die WSDL-Adresse des lokalen Dienstanbieter ist `http://localhost:65193/StockPriceService.xamlx?wsdl`.

8. Führen Sie im Datei-Explorer den WCF-Test Client (WcfTestClient. exe) aus. Er befindet im Verzeichnis "Microsoft Visual Studio 10.0 \Common7\IDE".

9. Klicken Sie im WCF-Test Client auf das Menü **Datei** , und wählen Sie **Dienst hinzufügen**aus. Fügen Sie die lokale Dienstadresse in das Textfeld ein. Klicken Sie auf **OK** , um das Dialogfeld zu schließen.

10. Doppelklicken Sie im WCF-Test Client auf **getstockprice**. Dadurch wird der `GetStockPrice` Vorgang geöffnet, der einen Parameter annimmt, geben Sie den Wert `Contoso` ein, und klicken Sie auf **aufrufen**.

11. Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL-Datenbank geschrieben. Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen. Weitere Informationen zu SQL Server Management Studio finden Sie unter [Introducing SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645). SQL Server 2008 Management Studio Express kann [hier](https://go.microsoft.com/fwlink/?LinkId=180520)heruntergeladen werden. Durch Ausführen einer Select-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.

#### <a name="to-uninstall-the-sample"></a>So installieren Sie das Beispiel aus

1. Führen Sie das Skript "Tdrackingcleanup.cmd" im Beispielverzeichnis (\WF\Basic\Tracking\SqlTracking) aus.

    > [!NOTE]
    > "Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen. Wenn Sie eine andere SQL Server-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungs Beispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
