---
title: Asynchrone nachrichtenbasierte Kommunikation
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Asynchrone nachrichtenbasierte Kommunikation"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df39771295d12e122edbe27e91cd899e3318e301
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="asynchronous-message-based-communication"></a>Asynchrone nachrichtenbasierte Kommunikation

Asynchrones messaging und ereignisgesteuerte Kommunikation sind entscheidend, bei der Weitergabe von Änderungen über mehrere Microservices und ihre verknüpften Domänenmodelle. Wie weiter oben in der Erläuterung Microservices und Kontexte begrenzt (BCs) erwähnt, können Modelle (Benutzer, Kunde, Produkt, Konto usw.) verschiedene Bedeutungen für verschiedene Microservices oder BCs bedeuten. Das bedeutet, dass beim Auftreten von Änderungen Abstimmen von Änderungen über die verschiedenen Modelle in irgendeiner Weise erforderlich. Eine Lösung ist die letztliche Konsistenz und ereignisgesteuerte Kommunikation basierend auf asynchrones messaging.

Bei der Verwendung von messaging kommunizieren Prozesse Nachrichtenaustausch asynchron. Ein Client stellt einen Befehl oder eine Anforderung an einen Dienst durch Senden einer Nachricht. Wenn der Dienst Antworten muss, sendet er eine andere Meldung zurück an den Client. Da eine nachrichtenbasierte Kommunikation ist, nimmt der Client an, dass die Antwort nicht sofort empfangen werden und möglicherweise gibt es keine Antwort überhaupt.

Eine Nachricht wird durch einen Header (z. B. Kennung oder Sicherheitsinformationen Metadaten) und einen Text verfasst. Nachrichten werden in der Regel über asynchrone Protokolle wie AMQP gesendet.

Die bevorzugte Infrastruktur für diese Art der Kommunikation in der Microservices-Community ist eine einfache nachrichtenbroker, dem unterscheidet, die große Brokern und Orchestrators in SOA verwendet wird. In einem einfachen nachrichtenbroker ist die Infrastruktur in der Regel "dumb," nur als ein nachrichtenbroker, mit für einfache Implementierungen, z. B. RabbitMQ oder einen skalierbaren Servicebus in der Cloud wie Azure Service Bus fungiert. In diesem Szenario die meisten "Intelligenz" weiterhin lebt in die Endpunkte, die erzeugt und Nachrichten zu nutzen, d. h. in der Microservices.

Eine andere Regel, Sie versuchen sollten, die folgen, so weit wie möglich, ist, zur Verwendung nur asynchrones messaging zwischen den internen Diensten, und verwenden Sie die synchrone Kommunikation (z. B. HTTP) nur über die Client-apps auf die Front-End-Dienste (API-Gateways sowie die erste Ebene der Microservices).

Es gibt zwei Arten von asynchronen messaging-Kommunikation: einzelnen Empfänger meldungsbasierte Kommunikation und mehrere Empfänger nachrichtenbasierte Kommunikation. In den folgenden Abschnitten bieten wir die Einzelheiten zu diesen.

## <a name="single-receiver-message-based-communication"></a>Single-Empfänger meldungsbasierte Kommunikation 

Asynchrone Kommunikation mit einem einzelnen Empfänger nachrichtenbasierte bedeutet, dass es Punkt-Kommunikation, die mit genau einem der Consumer eine Nachricht übermittelt werden, ist, die das Lesen aus dem Kanal und die Nachricht wird nur einmal verarbeitet. Es gibt jedoch spezielle Situationen. Beispielsweise konnte in einem Cloud-System, die versucht, automatisch nach Fehlern wiederherstellen, die gleiche Nachricht mehrere Male gesendet werden. Aufgrund eines Netzwerk- oder andere Fehler der Client muss, damit ein Wiederholungsversuch sendende von Nachrichten werden, und der Server hat einen Vorgang, um Idempotent sein, um auf eine bestimmte Nachricht nur einmal verarbeiten implementieren.

Single-Empfänger meldungsbasierte Kommunikation eignet sich besonders gut für das Senden von asynchrone Befehle aus einem Microservice zu einem anderen wie in Abbildung 4 – 18 dargestellt, die diesen Ansatz veranschaulicht.

Wenn Sie anfangen, meldungsbasierte Kommunikation (entweder mit Befehle oder Ereignisse) senden, sollten Sie das Mischen von meldungsbasierte Kommunikation mit einer synchronen HTTP-Kommunikation.

![](./media/image18.PNG)

**Abbildung 4 – 18**. Eine einzelne Microservice Empfang einer asynchronen

Beachten Sie, wenn die Befehle von Clientanwendungen stammen, aber als HTTP-synchrone Befehle implementiert werden können. Sie sollten nachrichtenbasierte Befehle verwenden, wenn Sie eine bessere Skalierbarkeit benötigen oder wenn Sie bereits in einem nachrichtenbasierte Geschäftsprozess.

## <a name="multiple-receivers-message-based-communication"></a>Mehrere Empfänger meldungsbasierte Kommunikation 

Als einen noch flexibleren Ansatz können Sie auch einen Veröffentlichungs-/Abonnementmechanismus verwenden möchten, damit die Kommunikation vom Absender an zusätzliche Abonnenten Microservices oder externe Anwendungen zur Verfügung stehen. Daher hilft Ihnen, befolgen die [öffnen/schließen Prinzip](https://en.wikipedia.org/wiki/Open/closed_principle) in den sendenden Dienst. Auf diese Weise können zusätzliche Abonnenten in der Zukunft ohne die Notwendigkeit, ändern Sie den Absender-Dienst hinzugefügt werden.

Wenn Sie eine Veröffentlichen/Abonnieren-Kommunikation verwenden, verwenden Sie möglicherweise eine Ereignisschnittstelle Bus, Veröffentlichen von Ereignissen an alle Abonnenten.

## <a name="asynchronous-event-driven-communication"></a>Asynchrone Kommunikation mit ereignisgesteuerte

Bei Verwendung asynchronen ereignisgesteuerte Kommunikation veröffentlicht ein Microservice ein Integration-Ereignis, wenn etwas innerhalb seiner Domäne passiert und einem anderen Microservice kennen sollten, wie eine Preisänderung in einer Product Catalog Microservice muss. Zusätzliche Microservices abonnieren die Ereignisse, damit sie asynchron empfangen können. In diesem Fall können der Empfänger ihrer eigenen Domänenentitäten aktualisieren dadurch weitere integrationsereignisse veröffentlicht werden können. Dieses Veröffentlichen/Abonnieren-Systems erfolgt in der Regel über eine Implementierung von einem Ereignisbus. Als eine Abstraktion oder einer Schnittstelle, mit der API, die zum Abonnieren und Kündigen von Ereignissen und zum Veröffentlichen von Ereignissen erforderlich ist, kann der-Ereignisbus entworfen werden. Der Ereignisbus kann auch ein oder mehrere Implementierungen auf Grundlage alle Broker Inter-process und messaging, z. B. eine Nachrichtenwarteschlange oder Servicebus, die asynchrone Kommunikation und ein Veröffentlichen/Abonnieren-Modell unterstützt.

Wenn ein System eventuellen Konsistenz durch integrationsereignisse verursachten verwendet wird, wird empfohlen, dass dieser Ansatz für den Endbenutzer vollständig deaktivieren vorgenommen werden. Das System sollten keinen Ansatz verwenden, der integrationsereignisse wie SignalR oder Abruf Systeme vom Client imitiert. Der Endbenutzer und der Geschäftseigentümer müssen explizit eventuellen Konsistenz im System zu nutzen, und beachten Sie, dass in vielen Fällen das Unternehmen keine Probleme bei diesem Ansatz haben, als es explizit ist.

Wie zuvor erwähnt die [Herausforderungen und Lösungen für distributed Data Management](#challenges-and-solutions-for-distributed-data-management) Abschnitt können Sie integrationsereignisse Geschäftsaufgaben implementieren, die mehrere Microservices umfassen. Daher müssen Sie die letztliche Konsistenz zwischen diesen Diensten. Eine letztendlich konsistente Transaktion besteht aus einer Auflistung von verteilten Aktionen. Bei jeder Aktion verknüpften Microservice aktualisiert eine Entität "Domain" und veröffentlicht ein anderes Integration-Ereignis, das die nächste Aktion innerhalb derselben Geschäftsaufgabe von End-to-End-auslöst.

Ein wichtiger Aspekt ist, dass Sie möglicherweise mit mehreren Microservices zu kommunizieren, die das gleiche Ereignis abonnieren möchten. Voraussetzung hierfür ist, Sie veröffentlichen/abonnieren verwenden, können auf der Grundlage messaging ereignisgesteuerte Kommunikation, wie in Abbildung 4-19 gezeigt. Dieser Mechanismus Veröffentlichen/Abonnieren steht nicht exklusiv für die Microservice-Architektur. Es ist ähnlich wie bei [Kontexten begrenzt, die den](http://martinfowler.com/bliki/BoundedContext.html) in DDD kommunizieren soll, oder auf die Möglichkeit, die Sie übertragen, Updates aus der Datenbank mit Schreibzugriff in der schreibgeschützten Datenbank in der [Befehl und Abfrage Verantwortung Segregation (CQRS)](http://martinfowler.com/bliki/CQRS.html)Architekturmuster. Das Ziel ist eventuellen Konsistenz zwischen mehreren Datenquellen in Ihrem verteilten System haben.

![](./media/image19.png)

**Abbildung 4-19**. Asynchrone ereignisgesteuerte Nachrichtenkommunikation

Ihre Implementierung bestimmen, welches Protokoll für eine ereignisgesteuerte, die meldungsbasierte Kommunikation verwendet. [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) zuverlässige warteschlangenkommunikation erreichen können.

Wenn Sie einen Ereignisbus verwenden, möglicherweise möchten eine Abstraktionsebene (z. B. eine Ereignisschnittstelle Bus) basierend auf eine ähnliche Implementierung in Klassen mit der API-Code aus einem nachrichtenbroker wie verwenden [RabbitMQ](https://www.rabbitmq.com/) oder einen Servicebus wie [Azure Servicebus mit Themen](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). Möglicherweise möchten alternativ einen Servicebus auf höherer Ebene, wie NServiceBus, MassTransit oder Brighter verwenden, um Ihre-Ereignisbus zu formulieren und Veröffentlichen/Abonnieren-Systems.

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>Ein Hinweis zu messaging Technologien für Produktionssysteme

Die Messagingtechnologien verfügbar für die Implementierung Ihrer abstrakte Ereignisbus sind auf unterschiedlichen Ebenen. Z. B. sit-Produkte wie RabbitMQ (messaging Broker Transport) und Azure Service Bus auf einer niedrigeren Ebene als andere Produkte wie NServiceBus, MassTransit oder Brighter, die auf RabbitMQ und Azure Service Bus arbeiten kann. Ihre Wahl hängt wie viele umfangreiche Funktionen in der Anwendungsebene und der Out-of-Box-Skalierbarkeit für Ihre Anwendung benötigten ab. Für die Implementierung gerade ein Proof of Concept Ereignisbus für Ihre Entwicklungsumgebung an, wie es in der Stichprobe eShopOnContainers geschehen kann eine einfache Implementierung über RabbitMQ auf einem Docker-Container ausgeführt ausreichend sein.

Beachten Sie jedoch bei unternehmenswichtigen und Produktionssystemen, die hyper-Skalierbarkeit benötigen Sie möglicherweise Azure Service Bus auswerten möchten. Für allgemeine Abstraktionen und Funktionen, die die Entwicklung von verteilten Anwendungen zu vereinfachen, wird empfohlen, dass Sie andere kommerzielle und Open-Source-Service-Bussen, z. B. NServiceBus, MassTransit und Brighter auswerten. Natürlich können Sie eigene Servicebus Funktionen auf niedrigerer Ebene Technologien wie RabbitMQ und Docker erstellen. Aber, dass Aufgaben, die die Arbeit möglicherweise zu viel für eine benutzerdefinierte Enterprise-Anwendung.

## <a name="resiliently-publishing-to-the-event-bus"></a>Bei veröffentlichen den-Ereignisbus

Eine Herausforderung beim Implementieren einer ereignisgesteuerten Architektur über mehrere Microservices wird erklärt, wie Status in der ursprünglichen Microservice automatisch aktualisiert wird, während der Veröffentlichung je in der Ereignisbus irgendwie basierend auf seiner verwandten Integration-Ereignis Transaktionen. Es folgen einige Möglichkeiten, um dies zu erreichen zwar möglicherweise auch zusätzliche Ansätze.

-   Verwenden eine (DTC-basiert) Transaktionswarteschlange wie MSMQ. (Dies ist jedoch ein älterer Ansatz.)

-   Mit [Transaktionsprotokoll Mining](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Unter Verwendung des vollständigen [Ereignis Sourcing](https://msdn.microsoft.com/en-us/library/dn589792.aspx) Muster.

-   Mithilfe der [Postausgang Muster](http://gistlabs.com/2014/05/the-outbox/): eine Transaktionsdatenbank-Tabelle als eine Warteschlange, die die Basis für eine Ereignis-Ersteller-Komponente, die das Ereignis zu erstellen und veröffentlichen.

Zusätzliche Themen, die bei Verwendung der asynchronen Kommunikation Nachricht Idempotenz und die Nachricht der Deduplizierung werden berücksichtigen. In diesen Themen finden Sie im Abschnitt [Implementieren des ereignisbasierten Kommunikation zwischen Microservices (integrationsereignisse)](#implementing_event_based_comms_microserv) weiter unten in diesem Handbuch.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Ereignis Driven Messaging**
    [*http://soapatterns.org/design\_Muster-Ereignis\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Veröffentlichen/Abonnieren-Kanal**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **Udi Dahan. Es wird erläutert CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Befehls- und Abfragen Responsibility Segregation (CQRS)**
    [*https://docs.microsoft.com/azure/architecture/patterns/cqrs*](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

-   **Kommunikation zwischen Kontexten begrenzt**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)

-   **Eventuelle Konsistenz**
    [*https://en.wikipedia.org/wiki/Eventual\_Konsistenz*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Jimmy Bogard. Umgestaltung für Stabilität: Auswerten Kopplung**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)


>[!div class="step-by-step"]
[Vorherigen] (Kommunikation-in-Microservice-architecture.md) [weiter] (verwalten-Microservice-apis.md)
