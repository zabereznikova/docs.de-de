---
title: 'Beispiele für serverloses Design: Serverlose Apps'
description: Informationen zur Vielfalt der Szenarien, die von serverlosen Architekturen unterstützt werden, von der Planung und ereignisbasierten Verarbeitung über Dateitrigger bis hin zu Streamingprozessen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3aa9b7951fd8f11a65a64c22443de7041aba7d94
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171753"
---
# <a name="serverless-design-examples"></a>Beispiele für serverloses Design

Es gibt viele Entwurfsmuster, die für serverlose Lösungen vorhanden sind. In diesem Abschnitt werden einige gängige Szenarien beschrieben, die serverlose Lösungen verwenden. Allen Beispielen gemeinsam ist die grundlegende Kombination aus Ereignistrigger und Geschäftslogik.

## <a name="scheduling"></a>Scheduling

Planungsaufgaben sind eine gängige Funktion. Die folgende Abbildung zeigt eine Legacydatenbank, die keine entsprechenden Integritätsprüfungen aufweist. Die Datenbank muss regelmäßig bereinigt werden. Die serverlose Funktion findet ungültige Daten und bereinigt sie. Der Trigger ist ein Timer, der den Code nach einem Zeitplan ausführt.

![Serverlose Planung](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Command and Query Responsibility Segregation (CQRS)

CQRS (Command and Query Responsibility Segregation) ist ein Muster, das verschiedene Schnittstellen zum Lesen (oder Abfragen) von Daten und Vorgängen bereitstellt, die Daten ändern. Dieses Muster behandelt mehrere häufige Probleme. In herkömmlichen CRUD-Systemen (Create, Read, Update, Delete – Erstellen, Lesen, Aktualisieren, Löschen) können Konflikte aufgrund einer hohen Anzahl von Lese- und Schreibvorgängen im selben Datenspeicher auftreten. Sperren treten häufig auf und verlangsamen die Lesevorgänge erheblich. Häufig werden Daten als ein Verbund mehrerer Domänenobjekte dargestellt, und Lesevorgänge müssen Daten aus verschiedenen Entitäten kombinieren.

Bei der Verwendung von CQRS kann es sich bei einem Lesevorgang um eine spezielle „flachere“ Entität handeln, die Daten so modelliert, wie sie genutzt werden. Der Lesevorgang wird anders behandelt als seine Speicherung. Obwohl die Datenbank beispielsweise einen Kontakt als Headerdatensatz mit einem untergeordneten Adressdatensatz speichern kann, kann der Lesevorgang eine Entität mit Header- und Adresseigenschaften beinhalten. Es gibt unzählige Ansätze, um das Lesemodell zu erstellen. Es kann sich aus Sichten ergeben. Aktualisierungsvorgänge können als isolierte Ereignisse gekapselt werden, die dann Updates für zwei verschiedene Modelle auslösen. Zum Lesen und Schreiben sind separate Modelle vorhanden.

![CQRS-Beispiel](./media/cqrs-example.png)

Der serverlose Ansatz kann das CQRS-Muster berücksichtigen, indem getrennte Endpunkte bereitstellt werden. Eine serverlose Funktion dient zum Verarbeiten von Abfragen oder Lesevorgängen, eine andere serverlose Funktion oder ein Satz von Funktionen verarbeitet Updatevorgänge. Eine serverlose Funktion kann auch dafür verantwortlich sein, das Lesemodell auf dem neuesten Stand zu halten, und sie kann durch den [Änderungsfeed](/azure/cosmos-db/change-feed) der Datenbank ausgelöst werden. Die Front-End-Entwicklung wird durch eine Verbindung mit den erforderlichen Endpunkten vereinfacht. Die Verarbeitung von Ereignissen erfolgt auf dem Back-End. Dieses Modell lässt sich auch gut für große Projekte skalieren, weil verschiedene Teams an unterschiedlichen Vorgängen arbeiten können.

## <a name="event-based-processing"></a>Ereignisbasierte Verarbeitung

In nachrichtenbasierten Systemen werden Ereignisse häufig in Warteschlangen oder Herausgeber-/Abonnementthemen gesammelt, um darauf zu reagieren. Diese Ereignisse können dazu führen, dass serverlose Funktionen bestimmte Geschäftslogik ausführen. Ein Beispiel für ereignisbasierte Verarbeitung sind ereignisgesteuerte Systeme. Ein „Ereignis“ wird ausgelöst, um eine Aufgabe als abgeschlossen zu markieren. Eine serverlose Funktion, die durch das-Ereignis ausgelöst wird, aktualisiert das entsprechende Datenbankdokument. Eine zweite serverlose Funktion kann das-Ereignis verwenden, um das Lesemodell für das System zu aktualisieren. [Azure Event Grid](/azure/event-grid/overview) bietet eine Möglichkeit, Ereignisse mit Funktionen als Abonnenten zu integrieren.

> Ereignisse sind Informationsmeldungen. Weitere Informationen finden Sie unter [Ereignisgesteuertes Muster](/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Dateitrigger und Transformationen

ETL (Extrahieren, Transformieren und Laden) ist eine gängige Geschäftsfunktion. Das serverlose Modell ist eine großartige Lösung für ETL, da der Code als Teil einer Pipeline ausgelöst werden kann. Einzelne Codekomponenten können verschiedene Aspekte berücksichtigen. Eine serverlose Funktion kann die Datei herunterladen, eine andere wendet die Transformation an, und eine weitere lädt die Daten. Der Code kann unabhängig getestet und bereitgestellt werden, sodass er bei Bedarf leichter verwaltet und skaliert werden kann.

![Serverlose Dateitrigger und Transformationen](./media/serverless-file-triggers.png)

In der Abbildung liefert „cool storage“ (kalter Speicher) Daten, die in [Azure Stream Analytics](/azure/stream-analytics) analysiert werden. Alle Probleme, die im Datenstrom auftreten, lösen eine Azure-Funktion aus, um die Anomalie zu verarbeiten.

## <a name="asynchronous-background-processing-and-messaging"></a>Asynchrone Hintergrundverarbeitung und Messaging

Asynchrones Messaging-und Hintergrundverarbeitung ermöglichen es Anwendungen, Prozesse zu starten, ohne warten zu müssen. Ein Beispiel für asynchrone Verarbeitung ist eine OCR-App. Ein Bild wird übermittelt und zur Verarbeitung in die Warteschlange eingereiht. Das Scannen des Bilds zum Extrahieren von Text kann einige Zeit in Anspruch nehmen. Nach Abschluss dieses Vorgangs wird eine Benachrichtigung gesendet. Das serverlose Modell kann sowohl den Aufruf als auch das Ergebnis in diesem Szenario verarbeiten.

## <a name="web-apps-and-apis"></a>Web-Apps und -APIs

Ein beliebtes Szenario für serverlose Anwendungen sind n-schichtige Anwendungen. Dies sind in den meisten Fällen Anwendungen, in denen die UI-Schicht eine Web-App ist. Die Beliebtheit von Single-Page-Anwendungen (SPA) ist in letzter Zeit stark gestiegen. SPA-Apps rendern eine einzelne Seite und verwenden dann API-Aufrufe und die zurückgegebenen Daten, um dynamisch eine neue Benutzeroberfläche zu rendern, ohne eine vollständige Seite neu zu laden. Das clientseitige Rendering bietet Endbenutzern eine viel schnellere und reaktionsfähigere Anwendung.

Serverlose Endpunkte, die durch HTTP-Aufrufe ausgelöst werden, können verwendet werden, um die API-Anforderungen zu verarbeiten. So kann beispielsweise ein Werbedienstleister eine serverlose Funktion mit Benutzerprofilinformationen aufrufen, um kundenspezifische Werbung anzufordern. Die serverlose Funktion gibt die benutzerdefinierte Werbeanzeige zurück, die von der Webseite gerendert wird.

![Serverlose Web-API](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Datenpipeline

Serverlose Funktionen können verwendet werden, um eine Datenpipeline bereitzustellen. In diesem Beispiel löst eine Datei eine Funktion aus, um Daten in einer CSV-Datei in Datenzeilen in einer Tabelle zu übersetzen. Die strukturierte Tabelle ermöglicht es, Analysen für den Endbenutzer in einem Power BI-Dashboard zu präsentieren.

![Serverlose Datenpipeline](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Datenstromverarbeitung

Geräte und Sensoren generieren häufig Datenströme, die in Echtzeit verarbeitet werden müssen. Es gibt eine Reihe von Technologien, mit denen Nachrichten und Datenströme von [Event Hubs](/azure/event-hubs/event-hubs-what-is-event-hubs) und [IoT Hub](/azure/iot-hub) bis hin zu [Service Bus](/azure/service-bus) erfasst werden können. Unabhängig vom Transport ist der serverlose Ansatz eine ideale Methode zum Verarbeiten der eingehenden Nachrichten und Datenströme. Das serverlose Modell kann schnell skaliert werden, um den Bedarf großer Datenmengen zu erfüllen. Der serverlose Code kann Geschäftslogik anwenden, um die Daten und die Ausgabe in einem strukturierten Format für Aktionen und Analysen zu analysieren.

![Serverlose Datenstromverarbeitung](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>API-Gateway

Ein API-Gateway bietet einen einzigen Einstiegspunkt für Clients und leitet dann Anforderungen intelligent an Back-End-Dienste weiter. Dies ist sinnvoll, um große Gruppen von Diensten zu verwalten. Außerdem kann es das Gateway Versionsverwaltung verarbeiten und die Entwicklung vereinfachen, indem Clients problemlos mit unterschiedlichen Umgebungen verbunden werden. Eine serverlose Lösung kann die Back-End-Skalierung einzelner Microservices verarbeiten und gleichzeitig ein einzelnes Front-End über ein API-Gateway bereitstellen.

![Serverloses API-Gateway](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Azure Event Grid](/azure/event-grid/overview)
- [Azure IoT Hub](/azure/iot-hub)
- [Challenges and solutions for distributed data management (Herausforderungen und Lösungen für verteilte Datenverwaltung)](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [Entwerfen von Microservices: Identifizieren von Microservicegrenzen](/azure/architecture/microservices/microservice-boundaries)
- [Event Hubs](/azure/event-hubs/event-hubs-what-is-event-hubs)
- [Muster „Ereignissourcing“](/azure/architecture/patterns/event-sourcing)
- [Implementing the Circuit Breaker pattern (Implementieren des Schaltkreisunterbrechermusters)](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [IoT Hub](/azure/iot-hub)
- [Service Bus](/azure/service-bus)
- [Verwenden der Unterstützung von Änderungsfeeds in Azure Cosmos DB](/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Zurück](serverless-architecture-considerations.md)
>[Weiter](azure-serverless-platform.md)
