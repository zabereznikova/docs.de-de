---
title: Server lose Designbeispiele-Server Lose apps
description: Informieren Sie sich über die Vielzahl von Szenarien, die von Server losen Architekturen unterstützt werden, von der Planung und ereignisbasierten Verarbeitung bis hin zu Datei Triggern und streamprozessen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: f7d3ec50608848b725d813ae2a9ee59ae9532ef3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522350"
---
# <a name="serverless-design-examples"></a>Beispiele für serverloses Design

Es gibt viele Entwurfsmuster, die für Server lose vorhanden sind. In diesem Abschnitt werden einige gängige Szenarien beschrieben, die Server lose verwenden. Alle Beispiele sind häufig die grundlegende Kombination aus Ereignis Triggern und Geschäftslogik.

## <a name="scheduling"></a>Planungen

Planungsaufgaben sind eine gängige Funktion. Das folgende Diagramm zeigt eine Legacy Datenbank, die keine geeigneten Integritätsprüfungen hat. Die Datenbank muss regelmäßig bereinigt werden. Die Server lose Funktion findet ungültige Daten und bereinigt Sie. Der Trigger ist ein Timer, der den Code nach einem Zeitplan ausführt.

![Server lose Planung](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Command and Query Responsibility Segregation (cqrs)

Command and Query Responsibility Segregation (cqrs) ist ein Muster, das verschiedene Schnittstellen zum Lesen (oder Abfragen) von Daten und Vorgängen bereitstellt, die Daten ändern. Es werden verschiedene häufige Probleme behandelt. In herkömmlichen CRUD-Systemen (Create Read Update Delete) können Konflikte aufgrund einer hohen Anzahl von Lese-und Schreibvorgängen im selben Datenspeicher auftreten. Sperren können häufig auftreten und die Lesevorgänge erheblich verlangsamen. Häufig werden Daten als zusammengesetzte mehrerer Domänen Objekte dargestellt, und Lesevorgänge müssen Daten aus verschiedenen Entitäten kombinieren.

Mithilfe von cqrs kann ein Lesevorgang eine spezielle "vereinfachte" Entität enthalten, die Daten auf die gleiche Weise modelliert. Der Lesevorgang wird anders behandelt, als wie er gespeichert wird. Obwohl die Datenbank z. b. einen Kontakt als Header Daten Satz mit einem untergeordneten Adressdaten Satz speichert, kann der Lesevorgang eine Entität mit den Header-und Adress Eigenschaften einschließen. Es gibt unzählige Ansätze zum Erstellen des Lese Modells. Sie kann aus Sichten materialisiert werden. Aktualisierungs Vorgänge können als isolierte Ereignisse gekapselt werden, die dann Updates für zwei verschiedene Modelle auslöst. Zum Lesen und schreiben sind separate Modelle vorhanden.

![Cqrs-Beispiel](./media/cqrs-example.png)

Serverless kann das cqrs-Muster erfüllen, indem die getrennten Endpunkte bereitgestellt werden. Eine Server lose Funktion dient zum Verarbeiten von Abfragen oder Lesevorgängen, und eine andere Server lose Funktion oder ein Satz von Funktionen verarbeitet Update Vorgänge. Eine Server lose Funktion kann auch dafür verantwortlich sein, das lesemodell auf dem neuesten Stand zu halten, und kann durch den [Änderungs Feed](https://docs.microsoft.com/azure/cosmos-db/change-feed)der Datenbank ausgelöst werden. Die Front-End-Entwicklung wird vereinfacht, um eine Verbindung mit den erforderlichen Endpunkten herzustellen. Die Verarbeitung von Ereignissen wird auf dem Back-End behandelt. Dieses Modell lässt sich auch gut für große Projekte skalieren, da verschiedene Teams an unterschiedlichen Vorgängen arbeiten können.

## <a name="event-based-processing"></a>Ereignisbasierte Verarbeitung

In Nachrichten basierten Systemen werden Ereignisse häufig in Warteschlangen oder Herausgeber-/abonneasethemen gesammelt, um zu reagieren. Diese Ereignisse können dazu führen, dass Server lose Funktionen eine Geschäftslogik ausführen. Ein Beispiel für die ereignisbasierte Verarbeitung sind systemeigene Systeme. Ein "Ereignis" wird ausgelöst, um einen Task als "Fertig" zu markieren. Eine Server lose Funktion, die durch das-Ereignis ausgelöst wird, aktualisiert das entsprechende Datenbankdokument. Eine zweite Server lose Funktion kann das-Ereignis verwenden, um das Lese Modell für das System zu aktualisieren. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) bietet eine Möglichkeit, Ereignisse in Funktionen als Abonnenten zu integrieren.

> Ereignisse sind Informationsmeldungen. Weitere Informationen finden Sie unter [Event Sourcing Pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Datei Trigger und Transformationen

Extrahieren, Transformieren und laden (ETL) ist eine gängige Geschäftsfunktion. Serverless ist eine großartige Lösung für ETL, da der Code als Teil einer Pipeline ausgelöst werden kann. Einzelne Code Komponenten können verschiedene Aspekte berücksichtigen. Eine Server lose Funktion kann die Datei herunterladen, eine andere wendet die Transformation an, und ein anderer lädt die Daten. Der Code kann unabhängig getestet und bereitgestellt werden, sodass er bei Bedarf leichter gewartet und skaliert werden kann.

![Server lose Datei Trigger und Transformationen](./media/serverless-file-triggers.png)

Im Diagramm stellt "cool Storage" Daten bereit, die in [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics)analysiert werden. Alle Probleme, die im Datenstrom auftreten, lösen eine Azure-Funktion aus, um die Anomalie zu beheben.

## <a name="asynchronous-background-processing-and-messaging"></a>Asynchrone Hintergrundverarbeitung und Messaging

Asynchrone Messaging-und Hintergrundverarbeitung ermöglichen es Anwendungen, Prozesse zu starten, ohne zu warten. Ein Beispiel für die asynchrone Verarbeitung ist eine OCR-app. Ein Bild wird übermittelt und zur Verarbeitung in die Warteschlange eingereiht. Das Scannen des Bilds zum Extrahieren von Text kann einige Zeit in Anspruch nehmen, und nach Abschluss des Vorgangs wird eine Benachrichtigung gesendet. Serverless kann sowohl den Aufruf als auch das Ergebnis in diesem Szenario verarbeiten.

## <a name="web-apps-and-apis"></a>Web-Apps und APIs

Ein beliebtes Szenario für Server lose Anwendungen sind N-Tier-Anwendungen, in den meisten Fällen, in denen die UI-Schicht eine Web-App ist. Die Beliebtheit von Single-Page-Anwendungen (Single Page Applications, Spa) wurde kürzlich überschritten. Spa-apps rendereine einzelne Seite und dann auf API-Aufrufe und die zurückgegebenen Daten, um die neue Benutzeroberfläche dynamisch zu renaden, ohne eine vollständige Seite erneut zu laden Das Client seitige Rendering bietet den Endbenutzern eine viel schnellere und reaktionsfähigere Anwendung.

Server lose Endpunkte, die durch http-Aufrufe ausgelöst werden, können verwendet werden, um die API-Anforderungen zu verarbeiten. Ein Ad Services-Unternehmen kann z. b. eine Server lose Funktion mit Benutzerprofil Informationen anrufen, um eine benutzerdefinierte Werbung anzufordern. Die Server lose Funktion gibt das benutzerdefinierte Ad zurück, das von der Webseite gerendert wird.

![Server lose Web-API](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Daten Pipeline

Server lose Funktionen können verwendet werden, um eine Daten Pipeline zu vereinfachen. In diesem Beispiel löst eine Datei eine Funktion aus, um Daten in einer CSV-Datei in Daten Zeilen in einer Tabelle zu übersetzen. Die strukturierte Tabelle ermöglicht einem Power BI Dashboard das präsentieren von Analysen für den Endbenutzer.

![Server lose Daten Pipeline](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Streamverarbeitung

Geräte und Sensoren generieren häufig Datenströme, die in Echtzeit verarbeitet werden müssen. Es gibt eine Reihe von Technologien, mit denen Nachrichten und Datenströme von [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) erfasst und [IOT Hub](https://docs.microsoft.com/azure/iot-hub) [Service Bus](https://docs.microsoft.com/azure/service-bus)werden können. Unabhängig vom Transport ist Server lose eine ideale Methode zum Verarbeiten der Nachrichten und Datenströme, die Sie erhalten. Serverless kann schnell skaliert werden, um die Nachfrage großer Datenmengen zu erfüllen. Der Server lose Code kann Geschäftslogik anwenden, um die Daten und die Ausgabe in einem strukturierten Format für Aktionen und Analysen zu analysieren.

![Server lose Datenstrom Verarbeitung](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>API-Gateway

Ein API-Gateway bietet einen einzigen Einstiegspunkt für Clients und leitet dann Intelligent Anforderungen an Back-End-Dienste weiter. Es ist nützlich, große Gruppen von Diensten zu verwalten. Außerdem kann es die Versionsverwaltung verarbeiten und die Entwicklung vereinfachen, indem Clients problemlos mit unterschiedlichen Umgebungen verbunden werden. Serverless kann die Back-End-Skalierung einzelner mikrodienste verarbeiten und gleichzeitig ein einzelnes Front-End über ein API-Gateway darstellen.

![Server Loses API-Gateway](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Challenges and solutions for distributed data management (Herausforderungen und Lösungen für verteilte Datenverwaltung)](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [Entwerfen von-Webdiensten: Ermitteln von Grenzen von Grenzen](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
- [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
- [Muster für Ereignis Beschaffung](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
- [Implementing the Circuit Breaker pattern (Implementieren des Schaltkreisunterbrechermusters)](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Service Bus](https://docs.microsoft.com/azure/service-bus)
- [Arbeiten mit der Unterstützung von Änderungs Feeds in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Zurück](serverless-architecture-considerations.md)
>[Weiter](azure-serverless-platform.md)
