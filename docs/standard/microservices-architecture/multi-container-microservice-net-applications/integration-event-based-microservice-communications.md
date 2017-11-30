---
title: Implementieren des ereignisbasierten Kommunikation zwischen Microservices (integrationsereignisse)
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren des ereignisbasierten Kommunikation zwischen Microservices (integrationsereignisse)"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e438607ab3549d63b89bef6af64c6723a4cac950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementieren des ereignisbasierten Kommunikation zwischen Microservices (integrationsereignisse)

Wie oben beschrieben, bei der Verwendung des ereignisbasierten Kommunikation, veröffentlicht ein Microservice ein Ereignis, wenn etwas relevante Fall z. B. wenn es sich um eine Geschäftseinheit aktualisiert. Diese Ereignisse abonnieren, andere Microservices. Wenn ein Microservice ein Ereignis empfängt, können sie eigene Geschäftseinheiten aktualisieren, die weitere Ereignisse, die zu veröffentlichenden verursachen könnten. Dieses Veröffentlichen/Abonnieren-Systems erfolgt in der Regel über eine Implementierung von einem Ereignisbus. Die Ereignisbus kann als eine Schnittstelle mit der-API benötigt, um Ihr Abonnement auf Ereignisse und zum Veröffentlichen von Ereignissen entworfen werden. Sie können auch veranlassen, dass eine oder mehrere Implementierungen basierend auf einer Inter-process oder messaging-Kommunikation, z. B. eine Nachrichtenwarteschlange oder einen Servicebus, der asynchrone Kommunikation und ein Veröffentlichen/Abonnieren-Modell unterstützt.

Ereignisse können Geschäftstransaktionen implementieren, die mehrere Dienste umfassen die letztliche Konsistenz zwischen diesen Diensten enthält. Eine letztendlich konsistente Transaktion besteht aus einer Reihe von verteilten Aktionen. Bei jeder Aktion die Microservice eine Geschäftseinheit aktualisiert und veröffentlicht ein Ereignis, das die nächste Aktion ausgelöst.

![](./media/image19.PNG)

**Abbildung 8 – 18**. Ereignisgesteuerte Kommunikation basierend auf einer-Ereignisbus

In diesem Abschnitt wird beschrieben, wie Sie diese Art von Kommunikation mit .NET implementieren können, mithilfe einer generischen Bus Ereignisschnittstelle, wie in Abbildung 8-18 dargestellt. Es gibt mehrere mögliche Implementierungen, jeweils eine andere Technologie oder ein z. B. RabbitMQ, Azure Service Bus, oder eine beliebige andere open Source-Drittanbieter- oder kommerziellen Servicebus-Infrastruktur verwenden.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Mithilfe der Nachricht Brokern und Dienste Bussen für Produktionssysteme

Wie in der Architektur Abschnitt erwähnt, können Sie mehrere Messagingtechnologien für die Implementierung Ihrer abstrakte Ereignisbus auswählen. Aber diese Technologien sind auf unterschiedlichen Ebenen. Beispielsweise ist RabbitMQ ein Broker Messagingtransport auf einer niedrigeren Ebene als kommerziellen Produkten, wie etwa Azure Service Bus, NServiceBus, MassTransit oder Brighter. Die meisten dieser Produkte können zusätzlich RabbitMQ oder Azure Service Bus arbeiten. Die Auswahl des Produkts, hängt davon ab, wie viele Funktionen und wie viel Out-of-the-Box-Skalierbarkeit, die Sie für Ihre Anwendung benötigen.

Für die Implementierung nur ein Ereignis Bus Proof-of-Concept für Ihre Entwicklungsumgebung, wie im Beispiel eShopOnContainers kann eine einfache Implementierung oberhalb RabbitMQ ausgeführt, die als Container ausreichend sein. Aber für unternehmenswichtige und Produktionssysteme, die hohe Skalierbarkeit benötigen, empfiehlt zum Auswerten und Azure Service Fabric verwenden. Wenn Sie die allgemeine Abstraktionen benötigen und umfangreichere Funktionen wie [Sagas](https://docs.particular.net/nservicebus/sagas/) für lang andauernde Prozesse, die verteilte Entwicklung einfacher, andere kommerzielle und Open-Source-Dienst-Bussen wie NServiceBus MassTransit, stellen und Helleren werden ausgewertet. Natürlich Sie immer eigene Servicebus-Features auf unterer Betriebsebene Technologien wie RabbitMQ und Docker erstellen, aber die Arbeit erforderlich, um das Rad neu zu erfinden ist möglicherweise für eine benutzerdefinierte Enterprise-Anwendung zu kostenintensiv.

Wie bereits erwähnt wurde: die Beispiel-Ereignis Bus Speicherabstraktionen und die Implementierung, die in der Stichprobe eShopOnContainers präsentiert dienen nur als ein Proof of Concept verwendet werden soll. Nachdem Sie entschieden haben, dass Sie asynchrone und ereignisgesteuerte Kommunikation verfügen, wie im aktuellen Abschnitt erläutert möchten, sollten Sie das Servicebus-Produkt auswählen, das Ihren Anforderungen am besten entspricht.

## <a name="integration-events"></a>-Integrationsereignisse

Integrationsereignisse dienen zum Domänenstatus synchron über mehrere Microservices oder externen Systemen zu schalten. Dies erfolgt durch integrationsereignisse außerhalb der Microservice veröffentlichen. Wenn ein Ereignis an mehrere Empfänger Microservices (um so viele Microservices wie das Integration Ereignis abonniert werden) veröffentlicht wird, behandelt in jeder Empfänger Microservice der passenden Ereignishandler das Ereignis an.

Ein Ereignis für die Integration ist im Grunde eine Daten-Betrieb-Klasse, wie im folgenden Beispiel:

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

Die Integration-Ereignisklasse kann einfach sein; Beispielsweise kann es eine GUID für ihre-ID enthalten.

Die integrationsereignisse können auf der Ebene des einzelnen Microservice definiert werden, damit sie von anderen Microservices, auf eine Weise vergleichbar sein, um wie ViewModels, auf dem Server und Client definiert werden entkoppelt werden. Was wird nicht empfohlen wird eine allgemeine Integration Ereignisse über mehrere Microservices bibliothekfreigabe; auf diese Weise würde diese Microservices mit einer einzelnen Definition Daten ereignisbibliothek Kopplung. Sie sollten keine nachholen, dem Grund, dass Sie keine allgemeine Domänenmodell für mehrere Microservices gemeinsam verwenden möchten: Microservices muss vollständig autonome sein.

Es sind nur einige Arten von Bibliotheken, die Sie für Microservices freigeben sollte. Eine der Bibliotheken, die endgültige Anwendungsblöcke, z. B. sind ist die [-Ereignisbus-Client-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), wie im eShopOnContainers. Ein weiterer Vorteil ist die Bibliotheken, die Tools zu bilden, die auch als NuGet-Komponenten, wie JSON-Serialisierungsprogramme freigegeben werden konnte.

## <a name="the-event-bus"></a>Den-Ereignisbus

Ein Ereignisbus ermöglicht Veröffentlichen/Abonnieren-Stil Kommunikation zwischen Microservices, ohne dass die Komponenten explizit voneinander, bekannt sein, wie in Abbildung 8-19 gezeigt.

![](./media/image20.png)

**Abbildung 8-19**. Grundlagen der mit einem Ereignisbus veröffentlichen/abonnieren

Die Ereignisbus bezieht sich auf das Muster "Beobachter" und das Veröffentlichen-Abonnieren-Muster.

### <a name="observer-pattern"></a>Muster "Beobachter"

In der ["Beobachter" Muster](https://en.wikipedia.org/wiki/Observer_pattern), Ihr primäre Objekt (bekannt als die Observable-Objekt) benachrichtigt anderen betroffenen Objekten (bekannt als Beobachter) mit relevanten Informationen (Ereignisse).

### <a name="publish-subscribe-pubsub-pattern"></a>(Pub/Sub) veröffentlichen-abonnieren-Muster 

Der Zweck der [Pub/Sub-Muster](https://msdn.microsoft.com/en-us/library/ff649664.aspx) ist identisch mit dem Muster "Beobachter": andere Dienste zu benachrichtigen, wenn bestimmte Ereignisse stattfinden soll. Es gibt jedoch ein wichtiger semantische Unterschied zwischen der "Beobachter" und Pub/Sub-Muster. In das Muster für Pub/Sub befindet sich der Fokus auf Übertragen von Nachrichten. Im Gegensatz dazu in das Muster "Beobachter" kennt die Observable-Objekt nicht, genau das, die sie nicht erhalten hat, die Ereignisse erstellt werden. Das heißt, weiß die Observable-Objekt (dem Herausgeber) nicht, sind die Observer-Objekte (Abonnenten).

### <a name="the-middleman-or-event-bus"></a>Der Bus Zwischenhandel oder Ereignis 

Wie erzielen Sie Anonymität zwischen Verleger und Abonnent? Eine einfache Möglichkeit darin, eine Zwischenhandel, die gesamte Kommunikation erledigen können. Ein-Ereignisbus ist eine solche Zwischenhandel.

Ein-Ereignisbus besteht in der Regel zwei Teilen:

-   Die Abstraktion oder Schnittstelle.

-   Eine oder mehrere Implementierungen.

In Abbildung 8-19 können Sie sehen, wie aus einer Anwendung der Sicht, die Ereignisbus keine Daten mehr als ein Pub/Sub-Kanal ist. Die Möglichkeit, die Sie implementieren, diese asynchrone Kommunikation kann variieren. Es kann mehrere Implementierungen verfügen, sodass Sie zwischen ihnen, je nach den umgebungsanforderungen (z. B. Produktion im Vergleich zu entwicklungsumgebungen) austauschen können.

In Abbildung 8 – 20 können Sie eine Abstraktion einer Ereignisbus mit mehrere Implementierungen basierend auf Infrastruktur messaging Technologien wie RabbitMQ, Azure Service Bus oder andere Service Bus: NServiceBus, MassTransit usw. anzeigen.

![](./media/image21.png)

**Abbildung 8: 20.** Mehrere Implementierungen einer-Ereignisbus

Allerdings ist hervorgehoben zuvor Abstraktionen (Bus Ereignisschnittstelle) mit nur möglich, wenn Sie grundlegende Ereignis Bus Funktionen durch Ihre Abstraktionen unterstützt benötigen. Wenn Sie umfangreichere Servicebus-Features benötigen, sollten Sie wahrscheinlich die API von bevorzugten Servicebus-statt eigene Abstraktionen verwenden.

### <a name="defining-an-event-bus-interface"></a>Definieren eine Ereignis-Bus-Schnittstelle

Beginnen wir mit einigen Implementierungscode für Bus Ereignisschnittstelle und mögliche Implementierungen zu durchsuchen. Die Schnittstelle sollte generischen und unkompliziert, wie die folgende Schnittstelle sein.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);
    void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T: IntegrationEvent;

    void Unsubscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent;
}
```

Die Veröffentlichungsmethode ist einfach. Die Ereignisbus wird das an sie übergebene werden, um alle auf das Ereignis abonniert Microservice Integration-Ereignis übermittelt. Diese Methode wird von der Microservice verwendet, der das Ereignis veröffentlicht wird.

Subscribe-Methode wird von der Microservices verwendet, die Ereignisse empfangen werden sollen. Diese Methode besteht aus zwei Teilen. Das erste ist die Integration-Ereignis (IntegrationEvent) abonnieren. Der zweite Teil ist die Integration Ereignishandler (oder eine Rückrufmethode) aufgerufen werden (IIntegrationEventHandler&lt;T&gt;) Wenn die Microservice empfängt diese ereignismeldung Integration.


>[!div class="step-by-step"]
[Vorherigen] (Datenbank-Server-container.md) [weiter] (Rabbitmq-event-bus-development-test-environment.md)
