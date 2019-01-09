---
title: Beispiele für serverloses Design - serverlose apps
description: Erfahren Sie, die Vielzahl von Szenarien, die von serverlosen Architekturen, Planung und ereignisbasierte Verarbeitung für Datei-Trigger und Stream-Prozess unterstützt werden.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: d165746ff2f03b0edc59a9284052323a0c1fd05b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149676"
---
# <a name="serverless-design-examples"></a>Serverloses Design-Beispiele

Es gibt viele Entwurfsmuster, die für vorhanden, serverlose. In diesem Abschnitt werden einige häufige Szenarien, die serverlose verwenden erfasst. Was haben alle Beispiele gemeinsam ist die grundlegende Kombination von einem Ereignis Trigger und Geschäftslogik.

## <a name="scheduling"></a>Planen von

Planen von Aufgaben ist eine allgemeine Funktion. Das folgende Diagramm zeigt eine Legacydatenbank, die keine entsprechenden integritätsprüfungen. Die Datenbank muss in regelmäßigen Abständen bereinigt werden. Die serverlose Funktion sucht nach ungültigen Daten und werden bereinigt. Der Trigger ist ein Zeitgeber, der der Code nach einem Zeitplan ausgeführt wird.

![Serverlose planen](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Befehl "und" Query Responsibility Segregation (CQRS)

Command and Query Responsibility Segregation (CQRS) ist ein Muster, das bietet verschiedene Schnittstellen für das Lesen (oder Abfrage)-Daten und Vorgänge, die Daten ändern. Es behandelt einige allgemeine Probleme. In traditionellen Systemen erstellen Read Update Delete (CRUD) basiert können Konflikte mit den gleichen Datenspeicher über große Anzahl von Lese- und Schreibvorgänge entstehen. Sperren kann häufig auftreten und sich Lesevorgänge erheblich verlangsamen. Häufig werden Daten dargestellt, wie eine Zusammensetzung aus mehrere Domänenobjekte und Lesevorgänge werden Daten aus anderen Entitäten kombinieren muss.

Befolgen von CQRS, möglicherweise ein Lesevorgang eine spezielle "vereinfachte" Entität umfassen, die modelliert Daten wie sie genutzt wird. Der Lesevorgang wird anders als die Speicherung erfolgt behandelt. Auch wenn die Datenbank einen Kontakt als Headerdatensatz mit einem untergeordneten Adressdatensatz gespeichert werden, könnten z. B. das Lesen eine Entität mit Header- und Adresseigenschaften betroffen sein. Es gibt unzählige Ansätze zum Erstellen des Modells lesen. Es kann aus Sichten materialisiert werden. Update-Vorgänge können als isolierte Ereignisse gekapselt werden, die auslösen, klicken Sie dann Updates für zwei verschiedene Modelle. Separate Modelle, die für Lese- und Schreibvorgänge vorhanden sein.

![CQRS-Beispiel](./media/cqrs-example.png)

Serverless kann das CQRS-Muster unterstützen, durch die getrennte Endpunkte bereitstellen zu können. Eine serverlose Funktion ermöglicht, Abfragen oder Lese- und eine andere serverlose Funktion oder einen Satz von Funktionen behandelt Update-Vorgänge. Eine serverlose Funktion möglicherweise auch selbst dafür verantwortlich, das lesemodell auf dem neuesten Stand, und kann ausgelöst werden, indem der Datenbank [änderungsfeed](https://docs.microsoft.com/azure/cosmos-db/change-feed). Zum Herstellen einer Verbindung zu den erforderlichen Endpunkten wird die Front-End-Entwicklung vereinfacht. Verarbeitung von Ereignissen, die auf dem Back-End verarbeitet wird. Dieses Modell kann sich auch gut für große Projekte, da auf verschiedenen Teams, die über verschiedene Vorgänge funktionieren.

## <a name="event-based-processing"></a>Ereignisbasierte Verarbeitung

In nachrichtenbasierter Systeme werden die Ereignisse in Warteschlangen oder Themen der Verleger/Abonnent zugrunde liegende häufig gesammelt. Serverlose Funktionen auf, um einen Teil der Geschäftslogik ausführen können diese Ereignisse ausgelöst werden. Ein Beispiel für ereignisbasierte Verarbeitung ist Event-Source-Systeme. Ein "Ereignis" wird ausgelöst, um eine Aufgabe als abgeschlossen zu markieren. Eine serverlose Funktion, die durch das Ereignis ausgelöst wird die entsprechende Datenbank-Dokument aktualisiert. Eine zweite serverlose Funktion kann das Ereignis verwenden, um das lesemodell für das System aktualisieren zu können. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) bietet eine Möglichkeit, Ereignisse mit Functions als Abonnenten zu integrieren.

> Ereignisse sind informationsmeldungen an. Weitere Informationen finden Sie unter [Muster "Ereignisherkunftsermittlung"](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Datei-Trigger und Transformationen

Extrahieren, Transformieren und laden (ETL) ist eine allgemeine Business-Funktion. Serverlose ist eine hervorragende Lösung für ETL, da sie Code als Teil einer Pipeline ausgelöst werden kann. Einzelne Komponenten können verschiedene Aspekte zu beheben. Eine serverlose Funktion kann die Datei herunterladen, eine andere wendet die Transformation und eine andere lädt die Daten. Der Code getestet und unabhängig voneinander bereitgestellt werden kann, zu verwalten und Skalieren bei Bedarf zu vereinfachen.

![Serverlose Datei-Trigger und Transformationen](./media/serverless-file-triggers.png)

Im Diagramm "" kalt "Speicher" enthält Daten, die im analysiert werden [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics). Alle Probleme, die in den Datenstrom Auslösen einer Azure-Funktion, um die Anomalie zu beheben.

## <a name="asynchronous-background-processing-and-messaging"></a>Asynchrone hintergrundverarbeitung und messaging

Asynchrones messaging und Verarbeitung im Hintergrund ermöglichen es Anwendungen, die Prozesse zu starten, ohne zu warten. Ein Beispiel für die asynchrone Verarbeitung ist eine OCR-app. Ein Bild wird gesendet, und zur Verarbeitung eingereiht. Scannen das Bild, um Text zu extrahieren kann Zeit in Anspruch nehmen und anschließend eine Benachrichtigung gesendet wird. Serverless kann sowohl für den Aufruf als auch für das Ergebnis in diesem Szenario verarbeiten.

## <a name="web-apps-and-apis"></a>Web-apps und APIs

Ein gängiges Szenario für serverlose Konzepte ist N-Tier-Anwendungen, am häufigsten für solche, die die UI-Ebene, in dem eine Web-app ist. Die Beliebtheit von Single-Page Applications (SPA) wurde vor kurzem surged. SPA-apps eine einzelne Seite gerendert, und verlassen sich auf die API-Aufrufe und die zurückgegebenen Daten, um die neue Benutzeroberfläche dynamisch zu rendern, ohne eine vollständige Seite erneut zu laden. Clientseitigem Rendering bietet eine wesentlich schnellere, reaktionsfähigere Anwendung für den Endbenutzer.

Serverlose Endpunkte, die durch HTTP-Aufrufe ausgelöst können verwendet werden, um die API-Anforderungen zu verarbeiten. Eine serverlose Funktion mit Informationen aus Benutzerprofilen zum Anfordern des benutzerdefinierten Werbung kann z. B. ein Ad-Dienstleistungsunternehmen aufgerufen werden. Die serverlose Funktion gibt die benutzerdefinierte Ad und der Webseite gerendert.

![Serverlose Web-API](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Data-pipeline

Serverlose Funktionen können verwendet werden, um eine Data-Pipeline zu ermöglichen. In diesem Beispiel löst eine Datei eine Funktion, um Daten in eine CSV-Datei, um Datenzeilen in einer Tabelle zu übersetzen. Die strukturierte Tabelle ermöglicht eine Power BI-Dashboards, Analysen, die dem Endbenutzer angezeigt.

![Serverloser Data pipeline](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Stream-Verarbeitung

Geräte und Sensoren generieren häufig in Echtzeit Datenströme, die verarbeitet werden müssen. Es gibt eine Reihe von Technologien, die Nachrichten und Datenströme aus aufzeichnen können [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) und [IoT Hub](https://docs.microsoft.com/azure/iot-hub) zu [Service Bus](https://docs.microsoft.com/azure/service-bus). Unabhängig vom Transport bedeutet serverlos eine ideale Methode für die Verarbeitung von Nachrichten und den Datenströmen, wie sie eintreffen. Serverless kann schnell skaliert werden, um den Bedarf an großer Datenmengen zu erfüllen. Geschäftslogik zum Analysieren der Daten und der Ausgabe in einem strukturierten Format für die Aktion und Analyse kann die serverlose Code angewendet werden.

![Serverlose Streamverarbeitung](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>API-gateway

Ein API-Gateway bietet nur einen Eintrag für Clients, und klicken Sie dann auf intelligente Weise leitet Anforderungen an Back-End-Dienste. Es ist hilfreich, um große Mengen von Diensten zu verwalten. Sie können auch versionsverwaltung und Entwicklung vereinfachen, indem Sie einfach Verbinden von Clients mit unterschiedlichen Umgebungen. Serverless kann Back-End-Skalierung der einzelnen Microservices, während der Vorlage eines einzelnen Front-End über eine API-Gateway behandeln.

![Serverlose API-gateway](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure IoT Hub-Instanz](https://docs.microsoft.com/azure/iot-hub)
* [Challenges and solutions for distributed data management (Herausforderungen und Lösungen für verteilte Datenverwaltung)](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md)
* [Entwerfen von Microservices: Identifizieren von Microservice-Grenzen](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
* [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
* [Muster "Ereignissourcing"](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
* [Implementing the Circuit Breaker pattern (Implementieren des Schaltkreisunterbrechermusters)](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md)
* [IoT Hub-Instanz](https://docs.microsoft.com/azure/iot-hub)
* [Servicebus](https://docs.microsoft.com/azure/service-bus)
* [Arbeiten mit der Unterstützung von änderungsfeeds in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Zurück](serverless-architecture-considerations.md)
>[Weiter](azure-serverless-platform.md)
