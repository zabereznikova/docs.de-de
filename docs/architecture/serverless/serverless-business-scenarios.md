---
title: Beispiele für Geschäftsszenarien und Anwendungsfälle für serverlose Apps
description: Lernen Sie serverlose Architekturen mit einem praktischen Ansatz kennen, indem Sie auf Beispiele zugreifen, die von der Bildverarbeitung bis hin zu Mobile-Back-Ends und ETL-Pipelines reichen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76787893"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Geschäftsszenarios für serverlose Architekuren und Anwendungsfälle

Es gibt viele Anwendungsfälle und Szenarien für serverlose Anwendungen. Dieses Kapitel enthält Beispiele, die die verschiedenen Szenarien veranschaulichen. Zu den Szenarien gehören Links zu verwandter Dokumentation und öffentlichen Quellcoderepositorys. Die Beispiele in diesem Kapitel ermöglichen Ihnen den Einstieg in das Entwickeln und Implementieren von serverlosen Lösungen.

## <a name="analyze-and-archive-images"></a>Analysieren und Archivieren von Bildern

In diesem Beispiel werden serverlose Ereignisse (Event Grid), Workflows (Logik-App) und Code (Azure Functions) veranschaulicht. Außerdem wird gezeigt, wie Sie die Integration in eine andere Ressource ausführen, in diesem Fall Cognitive Services für Bildanalyse.

Eine Konsolenanwendung ermöglicht Ihnen das Übergeben eines Links an eine URL im Web. Die App veröffentlicht die URL als Event Grid-Nachricht. Parallel dazu wird die Nachricht von einer serverlosen Funktions-App und einer Logik-App abonniert. Die serverlose Funktions-App serialisiert das Bild im Blobspeicher. Außerdem werden Informationen in Azure Table Storage gespeichert. In den Metadaten werden die ursprüngliche Bild-URL und der Name des Blobbilds gespeichert. Die Logik-App interagiert mit der Custom Vision-API, um das Bild zu analysieren und eine computergenerierte Beschriftung zu erstellen. Die Beschriftung wird in der Metadatentabelle gespeichert.

![Architektur für das Analysieren und Archivieren von Bildern](./media/image-processing-example.png)

Eine separate Single-Page-Anwendung (SPA) ruft eine serverlose Funktion auf, um eine Liste von Bildern und Metadaten abzurufen. Für jedes Bild wird eine andere Funktion aufgerufen, die die Bilddaten aus dem Archiv übermittelt. Das Endergebnis ist ein Katalog mit automatischen Beschriftungen.

![Automatisierter Bildkatalog](./media/automated-image-gallery.png)

Das vollständige Repository und Anleitungen zum Erstellen der Logik-App finden Sie hier: [Event Grid-Verbindung](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Plattformübergreifender mobiler Client, der Xamarin.Forms und Funktionen verwendet

Erfahren Sie, wie Sie eine einfache serverlose Azure-Funktion im Azure-Webportal oder in Visual Studio implementieren. Erstellen Sie einen Client mit Xamarin.Forms, der unter Android, iOS und Windows ausgeführt wird. Die Anwendung wird dann verfeinert, um JavaScript Object Notation (JSON) als Kommunikationsmedium zwischen dem Server und den mobilen Clients mit einem serverlosen Back-End zu verwenden.

Weitere Informationen finden Sie unter [Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-Client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generieren eines Fotomosaiks mit serverloser Bilderkennung

Das Beispiel verwendet Azure Functions und Custom Vision Service von Microsoft Cognitive Services, um ein Photomosaik aus einem Eingabebild zu generieren. Das Modell wurde trainiert, um Bilder zu erkennen. Wenn ein Bild hochgeladen wird, wird das Bild erkannt und mit Bing gesucht. Das ursprüngliche Bild wird mithilfe der Suchergebnisse neu zusammengesetzt.

![Foto und Mosaik von Orlando Eye](./media/orlando-eye-both.png)

Beispielsweise können Sie Ihr Modell mit Wahrzeichen aus Orlando (Florida, USA) trainieren, etwa mit dem Riesenrad Orlando Eye. Custom Vision erkennt ein Bild des Riesenrads Orlando Eye, und die Funktion erstellt ein Fotomosaik, das aus den Ergebnissen der Bing-Bildersuche für „Orlando Eye“ besteht.

Weitere Informationen finden Sie unter [Azure Functions-Fotomosaikgenerator](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migrieren einer vorhandenen Anwendung in die Cloud

Wie bereits in vorherigen Kapiteln erläutert, ist es üblich, eine n-schichtige Architektur zu nutzen, um Ihre Anwendung lokal zu hosten. Obwohl das „unveränderte“ Migrieren von Ressourcen mithilfe virtueller Computer der am wenigsten riskante Weg in die Cloud ist, entscheiden sich viele Unternehmen für ein Refactoring ihrer Anwendungen. Glücklicherweise muss dieses Refactoring kein Unterfangen der Art „Alles oder Nichts“ sein. Tatsächlich ist es möglich, Ihre App zu migrieren und dann stückweise Komponenten durch native Gegenstücke aus der Cloud zu ersetzen.

Die Anwendung verwendet die Proxyfunktion von Azure Functions, um das Refactoring eines Endpunkts aus dem lokalen Legacycode in einen serverlosen Endpunkt zu ermöglichen.

![Migrationsarchitektur](./media/migration-architecture.png)

Der Proxy stellt einen einzelnen API-Endpunkt bereit, der aktualisiert wird, um einzelne Anforderungen umzuleiten, wenn Sie in serverlose Funktionen verschoben werden.

Sie können sich ein Video ansehen, das die gesamte Migration schrittweise durchläuft: [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102) („Lift and Shift“ mit serverlosen Azure-Funktionen). Greifen Sie auf den Beispielcode zu: [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analysieren einer CSV-Datei und Einfügen in eine Datenbank

ETL (Extrahieren, Transformieren und Laden) ist eine gängige Geschäftsfunktion, die verschiedene Systeme integriert. Herkömmliche Ansätze umfassen häufig das Einrichten dedizierter FTP-Server und die anschließende Bereitstellung geplanter Aufträge, um Dateien zu analysieren und für die geschäftliche Verwendung zu übersetzen. Durch die serverlose Architektur wird diese Aufgabe vereinfacht, da ein Trigger ausgelöst werden kann, wenn die Datei hochgeladen wird. Azure Functions löst Aufgaben wie ETL durch die ideale Zusammensetzung aus kleinen Codeabschnitten, die sich auf ein bestimmtes Problem konzentrieren.

![Screenshot, der den CSV-Analyseprozess zeigt.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Quellcode und ein Praxislab finden Sie unter [CSV-Importlab](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Kürzen von Links und Nachverfolgen von Metriken

Tools zum Kürzen von Links trugen ursprünglich dazu bei, URLs in kurzen Twitter-Beiträgen zu codieren, um den Grenzwert von 140 Zeichen zu unterstützen. Sie werden inzwischen für eine Vielzahl von Verwendungsmöglichkeiten eingesetzt, vor allem zur Nachverfolgung von Click-Through-Vorgängen für Analysen. Das Szenario für die Kürzung von Links ist eine vollständig serverlose Anwendung zum Verwalten von Links, die auch Metriken bereitstellt.

Azure Functions wird für eine Single-Page-Anwendung (SPA) verwendet, mit der Sie die lange URL einfügen und kurze URLs generieren können. Die URLs werden gekennzeichnet, um Dinge wie Kampagnen (Themen) und Medien (z.B. soziale Netzwerke, in denen die Links gepostet werden) nachverfolgen zu können. Der kurze Code wird in Azure Table Storage als Schlüssel gespeichert, wobei die lange URL den Wert darstellt. Wenn Sie auf den kurzen Link klicken, schlägt eine andere Funktion die lange URL nach, sendet eine Umleitung und speichert Informationen zum Ereignis in einer Warteschlange. Eine andere Azure-Funktion verarbeitet die Warteschlange und platziert die Informationen in Azure Cosmos DB.

![Architektur der Linkkürzung](./media/link-shortener-architecture.png)

Sie können dann ein Power BI-Dashboard erstellen, um Einblicke in die erfassten Daten zu erhalten. Im Back-End stellt Application Insights wichtige Metriken bereit. Die Telemetrie umfasst beispielsweise Angaben dazu, wie lange es dauert, bis der durchschnittliche Benutzer umgeleitet wird, und wie lange der Zugriff auf Azure Table Storage dauert.

![Power BI-Beispiel](./media/power-bi-example.png)

Das vollständige Repository für die Linkkürzung mit Anleitungen finden Sie hier: [Serverlose URL-Kürzung](https://github.com/jeremylikness/serverless-url-shortener). Informationen zu einer vereinfachten Version finden Sie hier: [Azure Storage für serverlose .NET-Apps in wenigen Minuten](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Überprüfen der Gerätekonnektivität mit Ping

Das Beispiel besteht aus einem Azure IoT Hub und einer Azure-Funktion. Eine neue Nachricht im IoT Hub löst die Azure-Funktion aus. Der serverlose Code sendet denselben Nachrichteninhalt zurück an das Gerät, von dem er gesendet wurde. Das Projekt verfügt über den gesamten für die Lösung erforderlichen Code und die Bereitstellungskonfiguration.

Weitere Informationen finden Sie unter [Azure IoT Hub – Ping](https://github.com/Azure-Samples/iot-hub-node-ping).

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Azure Functions-Fotomosaikgenerator](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)
- [Azure IoT Hub – Ping](https://github.com/Azure-Samples/iot-hub-node-ping)
- [Azure Storage für serverlose .NET-Apps in wenigen Minuten](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [CSV-Importlab](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [Event Grid-Verbindung](https://github.com/JeremyLikness/Event-Grid-Glue)
- [Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-Client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [„Lift and Shift“ mit serverlosen Azure-Funktionen](https://channel9.msdn.com/Events/Connect/2017/E102)
- [Serverlose URL-Kürzung](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Zurück](orchestration-patterns.md)
>[Weiter](serverless-conclusion.md)
