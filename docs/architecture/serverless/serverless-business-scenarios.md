---
title: Beispiele für Geschäftsszenarien und Anwendungsfälle für serverlose Apps
description: Lernen Sie serverlose Architekturen mit einem praxisorientierten Ansatz kennen. Dazu finden Sie hier verschiedene Beispiele, die die Bildverarbeitung, die Unterstützung von Mobilgeräten bis hin zu ETL-Pipelines abdecken.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158449"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Geschäftsszenarios für serverlose Architekuren und Anwendungsfälle

Es gibt viele Anwendungsfälle und Szenarien für serverlose Anwendungen. Dieses Kapitel enthält Beispiele, die die verschiedenen Szenarien veranschaulichen. Zu den Szenarien gehören Links zu verwandter Dokumentation und öffentlichen Quellcoderepositorys. Die Beispiele in diesem Kapitel ermöglichen Ihnen den Einstieg in das Entwickeln und Implementieren von serverlosen Lösungen.

## <a name="big-data-processing"></a>Big Data-Verarbeitung

![Abbildung: MapReduce](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

In diesem Beispiel wird mit einem serverlosen Ansatz ein MapReduce-Vorgang für einen Big-Data-Datensatz durchgeführt. Darin wird die durchschnittliche Geschwindigkeit der gelben New Yorker Taxis pro Tag für das Jahr 2017 bestimmt.

[Big-Data-Verarbeitung: Serverloses MapReduce in Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a>Erstellen von serverlosen Anwendungen: Praxislab

Lesen Sie, wie Sie Funktionen nutzen, um serverseitige Logik auszuführen und serverlose Architekturen zu erstellen.

- Auswählen des besten Azure-Diensts für Ihr Unternehmen
- Erstellen von Azure Functions-Funktionen
- Verwenden von Triggern
- Verketten von Funktionen
- Workflows mit langer Laufzeit
- Überwachung
- Erstellung, Tests und Bereitstellung

[Erstellen von serverlosen Anwendungen](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a>Kundenbewertungen

In diesem Beispiel können Sie sich mit den neuen Azure Functions-Tools für C#-Klassenbibliotheken in Visual Studio vertraut machen. Sie erstellen eine Website, auf der Kunden Produktbewertungen abgeben können, die in Azure-Speicherblobs und CosmosDB gespeichert werden. Außerdem fügen Sie eine Azure Functions-Funktion hinzu, um die Kundenbewertungen automatisiert mit Azure Cognitive Services zu moderieren. Anschließend verwenden Sie eine Azure-Speicherwarteschleife, um die Website wieder von der Funktion zu entkoppeln.

[App für Kundenbewertungen mit Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a>Unterstützung für Docker-Linux-Images

In diesem Beispiel wird gezeigt, wie Sie ein `Dockerfile` erstellen, um Azure Functions-Funktionen in einem Linux-Docker-Container zu erstellen und auszuführen.

[Tutorial und Beispielprojekt: Azure Functions in benutzerdefinierten Linux-Images](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a>Dateiverarbeitung und -validierung

In diesem Beispiel wird eine Reihe von CSV-Dateien für hypothetische Kunden analysiert. Dabei wird sichergestellt, dass alle Dateien, die für ein Kundenbatch erforderlich sind, bereit sind. Anschließend wird die Struktur einer jeden Datei überprüft. Verschiedene Lösungen mithilfe von Azure Functions, Logic Apps und Durable Functions werden präsentiert.

[Dateiverarbeitung und -validierung mithilfe von Azure Functions, Logic Apps und Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a>Datenvisualisierung in Spielen

![Spieltelemetrie](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

Hier finden Sie ein Beispiel dafür, wie Entwickler eine editorinterne Lösung für die Datenvisualisierung in Spielen implementieren können. Das Unreal Engine 4 Plug-In und das Unity Plug-In verwenden dieses Beispiel als Back-End. Diese Dienstkomponente ist der Spiel-Engine gegenüber agnostisch.

[Editorinterne Telemetrievisualisierung für Spiele](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a>GraphQL

Erstellen Sie eine serverlose Funktion, die eine GraphQL-API verfügbar macht.

[Serverlose Funktionen für GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a>Reliable Edge Relay im Internet der Dinge

![IoT-Architektur](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

In diesem Beispiel wird ein neues Kommunikationsprotokoll implementiert, um eine zuverlässige Upstreamkommunikation von IoT-Geräten zu ermöglichen. So wird die Erkennung und der Abgleich von Datenlücken automatisiert.

[Reliable Edge Relay im Internet der Dinge](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a>Referenzarchitektur zu Microservices

![Referenzarchitektur](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

Mithilfe dieser Referenzarchitektur lernen Sie den Prozess der Entscheidungsfindung kennen, so wie er beim Designen, Entwickeln und Ausliefern der Rideshare-Anwendung von Relecloud (fiktives Unternehmen) abläuft. Das Beispiel enthält praxisorientierte Anleitungen für das Konfigurieren und Bereitstellen von allen Komponenten der Architektur.

[Referenzarchitektur für serverlose Microservices](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a>Migrieren von Konsolen-Apps in eine serverlose Architektur

Dieses Beispiel ist eine generische Funktion (`.csx`-Datei), mit der beliebige Konsolenanwendungen in HTTP-Webdienste in Azure Functions konvertiert werden können. Sie müssen nur die Konfigurationsdatei bearbeiten und angeben, welche Eingabeparameter als Argumente an die `.exe`-Datei übergeben werden sollen.

[Ausführen von Konsolen-Apps in Azure Functions](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a>Serverloser Ansatz für mobile Anwendungen

Azure Functions-Funktionen lassen sich einfach implementieren und verwalten. Außerdem sind sie über HTTP zugänglich. Sie stellen eine hervorragende Möglichkeit dar, eine API für eine mobile Anwendung zu implementieren. Microsoft bietet viele nützliche plattformübergreifende Tools für iOS, Android und Windows mit Xamarin an. Xamarin und Azure Functions funktionieren optimal zusammen. In diesem Artikel wird erläutert, wie Sie eine Azure Functions-Funktion zunächst im Azure-Portal oder in Visual Studio implementieren und einen plattformübergreifenden Client mit Xamarin.Forms erstellen, der unter Android, iOS und Windows ausgeführt wird.

[Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-Client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a>Serverloses Messaging

In diesem Beispiel wird gezeigt, wie Sie mit dem Auffächerungsmuster von Durable Functions eine beliebige Anzahl von Nachrichten aus verschiedenen Sitzungen oder Partitionen laden. Es gilt für Azure Service Bus, Azure Event Hubs und Azure-Speicherwarteschlangen. Im Beispiel wird außerdem eine Funktionalität hinzugefügt, mit der sich diese Nachrichten mit einer anderen Azure Functions-Funktion verarbeiten und die resultierenden Zeitdaten in eine andere Event Hubs-Instanz laden lassen. Die Daten werden anschließend in einem Analysedienst wie Azure Data Explorer erfasst.

[Erstellen und Verarbeiten von Nachrichten über Service Bus, Event Hubs und Speicherwarteschlangen mit Azure Functions](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Tutorial und Beispielprojekt: Azure Functions in benutzerdefinierten Linux-Images](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [Big-Data-Verarbeitung: Serverloses MapReduce in Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [Erstellen von serverlosen Anwendungen](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [App für Kundenbewertungen mit Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [Dateiverarbeitung und -validierung mithilfe von Azure Functions, Logic Apps und Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [Implementieren einer einfachen Azure-Funktion mit einem Xamarin.Forms-Client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [Editorinterne Telemetrievisualisierung für Spiele](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [Reliable Edge Relay im Internet der Dinge](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [Erstellen und Verarbeiten von Nachrichten über Service Bus, Event Hubs und Speicherwarteschlangen mit Azure Functions](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [Ausführen von Konsolen-Apps in Azure Functions](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [Serverlose Funktionen für GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [Referenzarchitektur für serverlose Microservices](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
>[Zurück](orchestration-patterns.md)
>[Weiter](serverless-conclusion.md)
