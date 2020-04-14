---
title: SQL-Nachverfolgung
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 72bfcaac2903b3e7fa5679422ad4feaa79e93211
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243179"
---
# <a name="sql-tracking"></a>SQL-Nachverfolgung

In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter SQL-Tracking-Teilnehmer geschrieben wird, der Tracking-Datensätze in eine SQL-Datenbank schreibt. Windows Workflow Foundation (WF) bietet Workflow-Nachverfolgung, um Einblick in die Ausführung einer Workflowinstanz zu erhalten. Die Überwachungslaufzeit gibt während der Ausführung des Workflows Workflowüberwachungsdatensätze aus. Weitere Informationen zur Workflowverfolgung finden Sie unter [Workflowverfolgung und Ablaufverfolgung](../workflow-tracking-and-tracing.md).

## <a name="use-the-sample"></a>Verwenden sie des Beispiels

1. Überprüfen Sie, ob Sie SQL Server 2008, SQL Server 2008 Express oder eine höhere Version installiert haben. In den mit dem Beispiel verpackten Skripts wird davon ausgegangen, dass auf dem lokalen Computer eine SQL Express-Instanz verwendet wird. Wenn Sie eine andere Instanz verwenden, ändern Sie die datenbankbezogenen Skripts vor dem Ausführen des Beispiels.

2. Erstellen Sie die SQL Server-Nachverfolgungsdatenbank, indem Sie "Trackingsetup.cmd" im Skripteverzeichnis (\WF\Basic\Tracking\SqlTracking\CS\Scripts) ausführen. Dadurch wird eine Datenbank mit dem Namen "TrackingSample" erstellt.

   > [!NOTE]
   > Das Skript erstellt die Datenbank auf der Standardinstanz von SQL Express. Wenn Sie sie auf einer anderen Datenbankinstanz installieren möchten, bearbeiten Sie das Skript "Trackingsetup.cmd".

3. Öffnen Sie SqlTrackingSample.sln in Visual Studio 2010.

4. Drücken Sie **Strg-Umschalttaste**+**Shift**+**B,** um die Lösung zu erstellen.

5. Drücken Sie **F5**, um die Anwendung auszuführen.

   Das Browserfenster wird geöffnet und zeigt die Verzeichnisliste für die Anwendung an.

6. Klicken Sie im Browser auf "StockPriceService.xamlx".

7. Der Browser zeigt die Seite "StockPriceService" an, die die WSDL-Adresse des lokalen Diensts enthält. Kopieren Sie diese Adresse.

   Ein Beispiel für die WSDL-Adresse des lokalen Dienstes ist `http://localhost:65193/StockPriceService.xamlx?wsdl`.

8. Führen Sie mit dem Datei-Explorer den WCF-Testclient (WcfTestClient.exe) aus. Es befindet sich im *Verzeichnis Microsoft Visual Studio 10.0 - Common7-IDE*.

9. Klicken Sie im WCF-Testclient auf das Menü **Datei,** und wählen Sie **Dienst hinzufügen**aus. Fügen Sie die lokale Dienstadresse in das Textfeld ein. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.

10. Doppelklicken Sie im WCF-Testclient auf **GetStockPrice**. Dadurch wird `GetStockPrice` der Vorgang geöffnet, der `Contoso` einen Parameter annimmt, geben Sie den Wert ein, und klicken Sie auf **Invoke**.

11. Die ausgegebenen Nachverfolgungsdatensätze werden in eine SQL-Datenbank geschrieben. Um die Nachverfolgungsdatensätze anzuzeigen, öffnen Sie die Datenbank "TrackingSample" in SQL Management Studio, und navigieren Sie zu den Tabellen. Durch Ausführen einer Select-Abfrage in den Tabellen werden die Daten in den Nachverfolgungsdatensätzen angezeigt, die in den jeweiligen Tabellen gespeichert sind.

   Weitere Informationen zu SQL Server Management Studio finden Sie [unter Einführung in SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms). Laden Sie SQL Server Management Studio [hier](https://aka.ms/ssmsfullsetup)herunter .

## <a name="uninstall-the-sample"></a>Deinstallieren des Beispiels

1. Führen Sie das SkriptTrackingcleanup.cmd im Beispielverzeichnis aus ( . . . . . . . . . .*. . . . . . . . . . . . . . . .*. . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . .

    > [!NOTE]
    > "Trackingcleanup.cmd" versucht, die Datenbank in SQL Express auf dem lokalen Computer zu löschen. Wenn Sie eine andere SQL Server-Instanz verwenden, bearbeiten Sie "Trackingcleanup.cmd".

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
