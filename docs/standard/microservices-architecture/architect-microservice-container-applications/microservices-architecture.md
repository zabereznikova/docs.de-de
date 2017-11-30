---
title: Microservicearchitektur
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Microservices-Architektur"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a>Microservicearchitektur

Wie der Name schon sagt, ist eine Microservices Architektur ein Ansatz zum Erstellen einer Server-Anwendung als eine Reihe von kleinen Diensten. Jeder Dienst in einem eigenen Prozess ausgeführt wird und mit anderen Prozessen, die über Protokolle wie HTTP/HTTPS, WebSockets kommuniziert oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Jedes Microservice implementiert wird, eine bestimmte End-to-End-Domäne oder Business-Funktion in einem bestimmten Kontext befindet, und jede muss autonom entwickelt und bereitgestellt werden, unabhängig. Zum Schluss sollte jede Microservice der verknüpften Domäne-Datenmodell und die Domänenlogik (Hoheit und dezentrale Data Management), die basierend auf verschiedene datenspeicherungstechnologien (SQL oder NoSQL) und anderen Programmiersprachen besitzen.

Welche Größe sollte ein Microservice werden? Beim Entwickeln einer Microservice sollte Größe nicht wichtig. Stattdessen sollte der wichtige Punkt werden Services erstellen lose gekoppelt, daher müssen Sie die Autonomie der Entwicklung, Bereitstellung und Skalierung, für jeden Dienst. Natürlich beim Identifizieren und Microservices entwerfen, sollten Sie so zu machen, so klein wie möglich, solange Sie nicht zu viele direkte Abhängigkeiten mit anderen Microservices verfügen. Wichtiger ist als die Größe der Microservice ist die interne Kohäsion, die sie benötigen und die Unabhängigkeit von anderen Diensten.

Warum eine Microservices Architektur? Kurz gesagt, stellt er langfristigen Flexibilität bereit. Microservices aktivieren besseren Verwaltbarkeit in komplexen, große und höchst flexibel skalierbaren Systemen, da Sie das Erstellen von Anwendungen, die basierend auf viele unabhängig bereitstellbare Diensten, die eine präzise und autonome Lebenszyklen aufweisen können.

Ein weiterer Vorteil kann Microservices unabhängig voneinander skalieren. Anstatt eine einzelne monolithische Anwendung, die Sie als eine Einheit skalieren müssen, können Sie stattdessen bestimmte Microservices skalieren. Auf diese Weise können Sie nur den Funktionsbereich "skalieren, die weitere Verarbeitung Power oder die Netzwerkbandbreite zur Unterstützung bei Bedarf, anstatt die Skalierung anderen Bereichen der Anwendung, die nicht skaliert werden müssen. Das bedeutet Kosten einsparen, da Sie weniger Hardware erforderlich.

![](./media/image6.png)

**Abbildung 4 bis 6**. Aufgrund eines monolithischen Bereitstellung im Vergleich zu den Microservices Ansatz

Wie in Abbildung 4 bis 6 gezeigt, kann der Microservices Ansatz agile Änderungen und schnelle Iteration der einzelnen Microservice, da Sie bestimmte, kleine Bereiche groß, skalierbare und komplexe Anwendungen ändern können.

Architektur differenzierte Microservices basierende Anwendungen ermöglicht das fortlaufende Integration und kontinuierlichen Bereitstellung Methoden. Sie beschleunigt auch Bereitstellung neue Funktionen in der Anwendung. Differenzierte Komposition von Anwendungen ermöglicht außerdem das Ausführen und Testen von Microservices isoliert, und sie autonom Beibehaltung deaktivieren Verträge dazwischen weiterentwickelt. Solange Sie nicht die Schnittstellen oder Verträge ändern, können Sie die interne Implementierung der alle Microservice ändern oder neue Funktionalität hinzufügen, ohne Unterbrechung der anderen Microservices.

Im folgenden sind wichtige Aspekte zu erfolgreich in die Produktionsphase mit einem Microservices-basierten System zu aktivieren:

-   Überwachung und Integrität überprüft der Dienste und -Infrastruktur.

-   Skalierbare Infrastruktur für die Dienste (d. h. Cloud und Orchestrators).

-   Sicherheit-Design und Implementierung auf mehreren Ebenen: Authentifizierung, Autorisierung, geheime Schlüssel Management, sichere Kommunikation usw..

-   Schnelle Anwendung Übermittlung in der Regel mit verschiedenen Teams, die verschiedene Microservices konzentrieren.

-   DevOps und CI-CD-Methoden und -Infrastruktur.

Diese sind nur die ersten drei abgedeckt oder eingeführt, die in diesem Handbuch. Die letzten beiden Punkte, die Anwendungslebenszyklus miteinander verbunden sind, finden Sie in der zusätzlichen [Docker-Anwendungslebenszyklus mit Microsoft Platform und Tools in Containern](https://aka.ms/dockerlifecycleebook) e-Book.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Mark Russinovich. Microservices: Eine Anwendung-Revolution Karten von der Cloud**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)

-   **Martin Fowler. Microservices**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)

-   **Martin Fowler. Microservice Voraussetzungen**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)

-   **Jimmy Nilsson. Aufteilen von Cloud Computing**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)

-   **Cesar de la Torre. Lebenszyklus der Docker-Anwendung mit Microsoft Platform und Tools in Containern** (herunterladbares e-Book) [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[Vorherigen] (Service-oriented-architecture.md) [weiter] (Data-Hoheit-pro-microservice.md)
