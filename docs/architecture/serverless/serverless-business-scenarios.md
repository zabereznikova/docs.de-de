---
title: Beispielszenarien für Geschäftsszenarien und Anwendungsfälle für Server Lose apps
description: Erfahren Sie, wie Sie sich mit einem praktischen Ansatz vertraut machen, indem Sie auf Beispiele zugreifen, die von der Bildverarbeitung zu mobilen Back-Ends und ETL-Pipelines reichen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7024a33f8a7fccd6afa51c126454afedd87cceee
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834299"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Geschäftsszenarios für serverlose Architekuren und Anwendungsfälle

Es gibt viele Anwendungsfälle und Szenarien für Server lose Anwendungen. Dieses Kapitel enthält Beispiele, die die verschiedenen Szenarien veranschaulichen. Zu den Szenarien gehören Links zu verwandten Dokumentationen und öffentlichen Quellcode-Repository. Die Beispiele in diesem Kapitel ermöglichen Ihnen den Einstieg in das entwickeln und Implementieren von Server losen Lösungen.

## <a name="analyze-and-archive-images"></a>Analysieren und Archivieren von Bildern

In diesem Beispiel werden Server lose Ereignisse (Event Grid), Workflows (Logik-APP) und Code (Azure Functions) veranschaulicht. Außerdem wird gezeigt, wie Sie in eine andere Ressource integrieren, in diesem Fall Cognitive Services für die Bildanalyse.

Eine Konsolenanwendung ermöglicht Ihnen das Übergeben eines Links an eine URL im Web. Die App veröffentlicht die URL als Event Grid-Nachricht. Parallel dazu wird die Nachricht von einer Server losen Funktions-APP und einer Logik-App abonniert. Die Server lose Funktions-APP serialisiert das Image in BLOB Storage. Außerdem werden Informationen in Azure Table Storage gespeichert. Die Metadaten speichern die ursprüngliche Bild-URL und den Namen des BLOB-Bilds. Die Logik-App interagiert mit der Custom Vision-API, um das Image zu analysieren und eine vom computergenerierte Beschriftung zu erstellen. Die Beschriftung wird in der Metadatentabelle gespeichert.

![Analysieren und Archivieren von Images](./media/image-processing-example.png)

Eine separate Single-Page-Anwendung (Spa) Ruft eine Server lose Funktion auf, um eine Liste von Bildern und Metadaten zu erhalten. Für jedes Image wird eine andere Funktion aufgerufen, die die Bilddaten aus dem Archiv übermittelt. Das Endergebnis ist ein Katalog mit automatischen Beschriftungen.

![Automatisierter Image Katalog](./media/automated-image-gallery.png)

Das vollständige Repository und Anweisungen zum Erstellen der Logik-App finden Sie hier: [Event Grid-Kleber](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Plattformübergreifender mobiler Client mit xamarin. Forms und Functions

Erfahren Sie, wie Sie eine einfache Server lose Azure-Funktion im Azure-Webportal oder in Visual Studio implementieren. Erstellen Sie einen Client mit xamarin. Forms, der unter Android, IOS und Windows ausgeführt wird. Die Anwendung wird dann für die Verwendung von JavaScript Object Notation (JSON) als Kommunikationsmedium zwischen dem Server und den mobilen Clients mit einem Server losen Back-End verfeinert.

Weitere Informationen finden Sie unter [Implementieren einer einfachen Azure-Funktion mit einem xamarin. Forms-Client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Foto-Mosaik mit Server loser Bild Erkennung generieren

Das Beispiel verwendet Azure Functions und Microsoft Cognitive Services Custom Vision Service, um ein Photo-Mosaik aus einem Eingabebild zu generieren. Das Modell wird trainiert, um Bilder zu erkennen. Wenn ein Bild hochgeladen wird, wird das Bild erkannt und mit dem Suchvorgang gesucht. Das ursprüngliche Bild wird mithilfe der Suchergebnisse neu zusammengesetzt.

![Orlando Eye Photo und Mosaic](./media/orlando-eye-both.png)

Beispielsweise können Sie Ihr Modell mit Orlando-, z. b. dem Orlando Eye, Schulen. Custom Vision erkennt ein Bild von Orlando Eye, und die Funktion erstellt ein Foto-Mosaik, das aus den Suchergebnissen von Suchergebnissen für "Orlando Eye" besteht.

Weitere Informationen finden Sie unter [Azure Functions Photo Mosaic Generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migrieren einer vorhandenen Anwendung in die Cloud

Wie bereits in den vorherigen Kapiteln erläutert, ist es üblich, eine N-Tier-Architektur zu nutzen, um Ihre Anwendung lokal zu hosten. Obwohl das Migrieren von Ressourcen "wie immer" mit virtuellen Computern der am wenigsten riskante Weg zur Cloud ist, entscheiden sich viele Unternehmen für die Umgestaltung Ihrer Anwendungen. Glücklicherweise muss das Refactoring keinen "All-or-Nothing"-Aufwand haben. Tatsächlich ist es möglich, Ihre APP zu migrieren, und dann Komponenten durch die native Cloud-Entsprechung zu ersetzen.

Die Anwendung verwendet die Proxys von Azure Functions, um das Refactoring eines Endpunkts aus dem Legacy lokalen Code zu einem Server losen Endpunkt zu ermöglichen.

![Migrations Architektur](./media/migration-architecture.png)

Der Proxy stellt einen einzelnen API-Endpunkt bereit, der aktualisiert wird, um einzelne Anforderungen umzuleiten, wenn Sie in Server lose Funktionen verschoben werden.

Sie können sich ein Video ansehen, das die gesamte Migration durchläuft: [Lift & Shift mit Server losen Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102). Greifen Sie auf den Beispielcode zu: [Bringen Sie Ihre eigene APP](https://github.com/JeremyLikness/bring-own-app-connect-17)ein.

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Eine CSV-Datei analysieren und in eine Datenbank einfügen

Extrahieren, Transformieren und laden (ETL) ist eine gängige Geschäftsfunktion, die verschiedene Systeme integriert. Herkömmliche Ansätze umfassen häufig das Einrichten dedizierter FTP-Server und die anschließende Bereitstellung geplanter Aufträge, um Dateien zu analysieren und für die geschäftliche Verwendung zu übersetzen. Durch die Server lose Architektur wird die Aufgabe vereinfacht, da ein Trigger ausgelöst werden kann, wenn die Datei hochgeladen wird. Azure Functions behandelt Aufgaben wie ETL durch die ideale Komposition von kleinen Code teilen, die sich auf ein bestimmtes Problem konzentrieren.

![Screenshot, der den CSV-Prozess für die CSV-Verarbeitung anzeigt.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Informationen zu Quellcode und praktischen Übungseinheiten finden Sie unter [CSV-Import-Lab](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Kürzen von Links und verfolgen von Metriken

Die Tools zum Verkürzen von Links trugen ursprünglich dazu bei, URLs in kurzen Twitter-Beiträgen zu codieren, um den Grenzwert von 140 Zeichen Sie wurden zu mehreren Verwendungsmöglichkeiten erweitert, meistens zum Nachverfolgen von Click-through-Vorgängen für Analysezwecke. Das linkshortener-Szenario ist eine vollständig Server lose Anwendung zum Verwalten von Verknüpfungen und Berichts Metriken.

Azure Functions wird für eine Single-Page-Anwendung (Spa) verwendet, mit der Sie die Long-URL einfügen und kurze URLs generieren können. Die URLs werden gekennzeichnet, um Dinge wie Kampagnen (Themen) und Medien (z. b. soziale Netzwerke, an die die Links gesendet werden) nachverfolgen zu können. Der kurze Code wird in Azure Table Storage als Schlüssel gespeichert, wobei die Long-URL den Wert hat. Wenn Sie auf den Kurzlink klicken, wird von einer anderen Funktion die Long-URL nachgeschlagen, eine Umleitung gesendet und Informationen über das Ereignis in einer Warteschlange abgelegt. Eine andere Azure-Funktion verarbeitet die Warteschlange und platziert die Informationen in Azure Cosmos DB.

![Link Kürzel-Architektur](./media/link-shortener-architecture.png)

Sie können dann ein Power BI Dashboard erstellen, um Einblicke in die gesammelten Daten zu sammeln. Im Back-End stellt Application Insights wichtige Metriken bereit. Die Telemetrie umfasst, wie lange es dauert, bis der durchschnittliche Benutzer umgeleitet wird und wie lange der Zugriff auf Azure Table Storage dauert.

![Power BI Beispiel](./media/power-bi-example.png)

Das vollständige Link-verkürzer-Repository mit Anweisungen finden Sie hier: [Server loser URL-Kürzel](https://github.com/jeremylikness/serverless-url-shortener). Informationen zu einer vereinfachten Version finden Sie hier: [Azure Storage für Server lose .net-apps in wenigen Minuten](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Überprüfen der Geräte Konnektivität per Ping

Das Beispiel besteht aus einer Azure IOT Hub und einer Azure-Funktion. Eine neue Nachricht im IOT Hub löst die Azure-Funktion aus. Der Server lose Code sendet denselben Nachrichten Inhalt zurück an das Gerät, von dem das Gerät gesendet wurde. Das Projekt verfügt über den gesamten Code und die Bereitstellungs Konfiguration, die für die Lösung erforderlich sind.

Weitere Informationen finden Sie unter [Azure IOT Hub Ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure Functions Photo-Mosaik Generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Azure IOT Hub Ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [Azure Storage für Server lose .net-apps in wenigen Minuten](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
* [Bring your own App](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [CSV-Import-Lab](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Event Grid-Kleber](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Implementieren einer einfachen Azure-Funktion mit einem xamarin. Forms-Client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [Lift & Shift mit Server losen Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102)
* [Server loser URL-Kürzel](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Zurück](orchestration-patterns.md)
>[Weiter](serverless-conclusion.md)
