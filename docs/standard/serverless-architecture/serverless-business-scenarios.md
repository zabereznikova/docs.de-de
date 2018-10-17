---
title: Beispiel-Business-Szenarien und Anwendungsfälle für serverlose apps
description: Erfahren Sie durch den Zugriff auf Beispiele, in denen reichen von bildverarbeitung mobilen Back-Ends und ETL-Pipelines, serverlose Architektur mit einem praktischen Ansatz.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c38d1c6c4e04f3fa38946c97af5d94758b3ed6f7
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369961"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Serverlose Business-Szenarien und Anwendungsfälle

Es gibt viele Anwendungsfälle und Szenarien für die serverlose Anwendungen. Dieses Kapitel enthält Beispiele, in denen die verschiedenen Szenarien zu veranschaulichen. Die Szenarien umfassen die Links zu verwandten Dokumentation und in öffentlichen Quellcode-Repositorys. In die Beispielen in diesem Kapitel können Sie mit Ihren eigenen erstellen und Implementieren von serverlosen Lösungen beginnen zu können.

## <a name="analyze-and-archive-images"></a>Analysieren und Archivieren von Bildern

Dieses Beispiel veranschaulicht die serverlose Ereignisse (Event Grid), Workflows (Logik-App) und Code (Azure Functions). Es wird gezeigt, wie eine andere Ressource in diesem Fall Cognitive Services für Bildanalyse integrieren.

Eine Konsolenanwendung können Sie einen Link zu einer URL im Internet zu übergeben. Die app wird die URL als Event Grid Nachricht veröffentlicht. Abonnieren gleichzeitig eine serverlose Funktionen-app und eine Logik-app auf die Nachricht. Die serverlose Funktionen-app wird das Bild in Blob Storage serialisiert. Es werden auch Informationen in Azure Table Storage gespeichert. Die Metadaten speichert die ursprüngliche Bild-URL und den Namen des Blob-Images. Die Logik-app interagiert mit der Custom Vision-API, auf das Bild zu analysieren und erstellen Sie eine Beschriftung computergenerierte. Die Beschriftung wird in der Metadatentabelle gespeichert.

![Analysieren und Archivieren von Bildern-Architektur](./media/image-processing-example.png)

Eine separate einzelseitenanwendung (SPA) Ruft eine serverlose Funktion, um eine Liste der Bilder und Metadaten zu erhalten. Für jedes Image wird eine andere Funktion, die die Bilddaten aus dem Archiv bereitstellt. Das endgültige Ergebnis ist ein Katalog mit automatischer Untertitel.

![Automatisierte Image-Katalog](./media/automated-image-gallery.png)

Die vollständige Repository und die Anweisungen zum Erstellen der Logik-app finden Sie hier: [Event Grid "Klebstoff"](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Plattformübergreifende mobile-Client mithilfe von Xamarin.Forms und Funktionen

Erfahren Sie, wie eine einfache serverlose Azure-Funktion im Azure-Web-Portal oder in Visual Studio zu implementieren. Erstellen Sie einen Client mit Xamarin.Forms verwenden, die auf Android-, IOS- und Windows ausgeführt wird. Die Anwendung wird dann optimiert, um JavaScript Object Notation (JSON) als ein Mittel der Kommunikation zwischen dem Server und der mobilen Clients mit einer serverlosen Back-End zu verwenden.

Weitere Informationen finden Sie unter [Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-Client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generieren Sie ein Foto Mosaik mit serverlosen bilderkennung

Das Beispiel verwendet Azure Functions und Microsoft Cognitive Services Custom Vision Service, um ein Foto-Mosaik aus einem Eingabe-Image zu generieren. Das Modell wird trainiert, um Bilder zu erkennen. Wenn ein Bild hochgeladen wurde, erkennt das Bild und mit Bing zusammen, durchsucht. Das ursprüngliche Bild wird neu aufgebaut, mit den Suchergebnissen angezeigt.

![Orlando Eye Foto "und" mosaic](./media/orlando-eye-both.png)

Beispielsweise können Sie Ihr Modell mit Orlando Orientierungspunkte im Gelände, z. B. das Auge Orlando trainieren. Custom Vision erkennt ein Abbild von Orlando Auge, und die Funktion erstellt ein Foto Mosaik aus Bing-Suchergebnisse für "Orlando Eye."

Weitere Informationen finden Sie unter [Azure Functions Foto Mosaic Generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Migrieren Sie vorhandene Anwendungen in die cloud

Wie in den vorangegangenen Kapiteln erläutert wird, ist es üblich, eine N-schichtige Architektur zum Hosten Ihrer Anwendung lokal zu nutzen. Obwohl das Migrieren von Ressourcen, die "wie besehen" mithilfe von virtuellen Computern ist der ungefährlichste Pfad in die Cloud, die viele Unternehmen wählen für die Gelegenheit nutzen, um ihre Anwendungen zu gestalten. Glücklicherweise refactoring keine Bestreben "nichts" sein. In der Tat ist es möglich, migrieren Ihre app, und klicken Sie dann schrittweise Komponenten durch native Cloud-Entsprechungen ersetzen.

Die Anwendung verwendet die Proxys-Funktion von Azure Functions, um einen Endpunkt aus auf lokale Code an einen Endpunkt serverlose refactoring zu aktivieren.

![Migrationsarchitektur](./media/migration-architecture.png)

Der Proxy bietet einen einzigen API-Endpunkt, der aktualisiert wird, um einzelne Anforderungen umgeleitet wird, wie sie serverlose Funktionen in Einzelschritten verschoben werden.

Sehen Sie ein Video, das durch die gesamte Migration führt: [Lift & Shift mit serverlosen Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102). Zugriff auf den Beispielcode: [bringen Sie Ihre eigene app](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analysieren einer CSV-Datei, und fügen Sie in einer Datenbank

Extrahieren, Transformieren und laden (ETL) ist eine allgemeine Business-Funktion, die verschiedene Systeme integriert ist. Herkömmliche Ansätze umfassen häufig dedizierte FTP-Server einrichten und Bereitstellen von geplanten Aufträgen-Dateien analysieren und für die geschäftliche Verwendung zu übersetzen. Serverlose Architektur vereinfacht den Auftrag, da ein Trigger ausgelöst werden kann, wenn die Datei hochgeladen wurde. Azure Functions-Tackles-Aufgaben wie ETL, über die ideale Zusammensetzung der kleine Codeelemente, die auf ein bestimmtes Problem konzentrieren.

![ETL-Architektur](./media/csvimport.png)

Quellcode und eine praktische Übungseinheit, finden Sie unter [Importieren der CSV-Datei Lab](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Links zu verkürzen und Nachverfolgen von Metriken

Link verkürzen Sie Tools, die mit der ursprünglich geholfen, kurz gesagt URL(s) twitter-Beiträge zur Aufnahme die 140 Zeichen-Grenze. Sie verzichten zu verschiedenen Zwecken, am häufigsten zum Nachverfolgen von framebasierte Durchklicks für Analysen zu umfassen. Das Link-verkürzer-Szenario ist eine vollständig serverlosen Anwendung, die verwaltet Links und meldet die Metriken.

Azure Functions wird verwendet, um einen Single-Page Application (SPA) zu verarbeiten, mit dem Sie die lange URL einfügen und kurz-URLs zu generieren. Die URLs werden zum Nachverfolgen von z. B. Kampagnen (Vorgehensweisen) und Medien (z. B. soziale Netzwerke, denen die Links bereitgestellt werden) markiert. Der kurze Code ist in Azure Table Storage als Schlüssel, mit der langen URL als Wert gespeichert. Wenn Sie auf den kurzen Link klicken, eine andere Funktion sucht nach der langen URL sendet eine Umleitung und Informationen zum Ereignis in einer Warteschlange platziert. Eine andere Azure-Funktion verarbeitet die Warteschlange und speichert die Informationen in Azure Cosmos DB.

![Link-verkürzer-Architektur](./media/link-shortener-architecture.png)

Sie können dann ein Power BI-Dashboard, um Einblicke zu den gesammelten Daten erhalten erstellen. Auf dem Back-End bietet Application Insights wichtige Metriken. Telemetriedaten beinhaltet, wie lange es für den durchschnittlichen Benutzer umleiten dauert und wie lange es dauert, den Zugriff auf Azure-Tabellenspeicher.

![Power BI-Beispiel](./media/power-bi-example.png)

Repository-verkürzer vollständiger Link wird mit einer Anleitung ist hier verfügbar: [serverloser URL-verkürzer](https://github.com/jeremylikness/serverless-url-shortener). Informieren Sie sich über eine vereinfachte Version hier: [Azure Storage für serverlose .NET apps in wenigen Minuten](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Überprüfen Sie die Verbindung von Geräten mit dem Befehl ping

Das Beispiel besteht aus einer Azure-IoT-Hub und einer Azure-Funktion. Eine neue Nachricht auf dem IoT Hub löst die Azure-Funktion. Die serverlose Code sendet dieselbe Nachricht Inhalt an das Gerät, das sie gesendet. Das Projekt enthält alle Code und die Bereitstellung erforderliche Konfiguration für die Lösung.

Weitere Informationen finden Sie unter [Azure IoT Hub – Ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure Functions Foto Mosaic-generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Azure IoT Hub – ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [Azure-Speicher für serverlose .NET apps in wenigen Minuten](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [Bringen Sie Ihre eigene app](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [CSV-Import-lab](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Event Grid "Klebstoff"](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [Lift & Shift mit serverlosen Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102)
* [Serverloser URL-verkürzer](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
[Zurück](orchestration-patterns.md)
[Weiter](serverless-conclusion.md)