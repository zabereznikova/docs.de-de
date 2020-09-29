---
title: Implementieren ereignisbasierter Kommunikation zwischen Microservices (Integrationsereignisse)
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über Integrationsereignisse zum Implementieren ereignisbasierter Kommunikation zwischen Microservices
ms.date: 10/02/2018
ms.openlocfilehash: a778acba3e17b084840b77d903533f9180ca01d9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152532"
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementieren ereignisbasierter Kommunikation zwischen Microservices (Integrationsereignisse)

Wie bereits erwähnt, veröffentlicht ein Microservice bei Verwendung ereignisbasierter Kommunikation ein Ereignis, wenn etwas Nennenswertes geschieht, beispielsweise wenn eine Geschäftseinheit aktualisiert wird. Andere Microservices abonnieren diese Ereignisse. Wenn ein Microservice ein Ereignis empfängt, kann er die eigenen Geschäftseinheiten aktualisieren, was dazu führen kann, dass weitere Ereignisse veröffentlicht werden. Das ist die Grundidee des Konzepts der letztlichen Konsistenz. Dieses System des Veröffentlichens/Abonnierens erfolgt in der Regel über die Implementierung eines Ereignisbusses. Der Ereignisbus kann als Schnittstelle ausgelegt sein, die die API enthält, die zum Abonnieren von Ereignissen, zum Kündigen des Abonnements von Ereignissen sowie zum Veröffentlichen von Ereignissen erforderlich ist. Er kann auch über eine oder mehrere Implementierungen verfügen, die auf prozessübergreifender Kommunikation oder Messaging-Kommunikation beruhen. Beispiele hierfür sind Nachrichtenwarteschlangen oder Service Busse, die die asynchrone Kommunikation und ein auf Veröffentlichen/Abonnieren basierendes Modell unterstützen.

Sie können Ereignisse verwenden, um Geschäftstransaktionen zu implementieren, die sich über mehrere Dienste erstrecken. Dadurch werden diese Dienste im Laufe der Zeit konsistent. Eine letztendlich konsistente Transaktion besteht aus einer Reihe von verteilten Aktionen. Bei jeder Aktion aktualisiert der Microservice eine Geschäftseinheit und veröffentlicht ein Ereignis, das die nächste Aktion auslöst. In Abbildung 6-18 unten wird ein PriceUpdated-Ereignis gezeigt, das über einen Ereignisbus veröffentlicht wurde, sodass die Preisaktualisierung in den Warenkorb und an andere Microservices weitergegeben wird.

![Diagramm der asynchronen, ereignisgesteuerten Kommunikation mit einem Ereignisbus.](./media/integration-event-based-microservice-communications/event-driven-communication.png)

**Abbildung 6-18**. Ereignisgesteuerte Kommunikation basierend auf einem Ereignisbus

In diesem Abschnitt wird beschrieben, wie Sie diese Art von Kommunikation mit .NET mithilfe einer generischen Ereignisbusschnittstelle implementieren können (siehe Abbildung 6-18). Es gibt mehrere mögliche Implementierungen, bei denen jeweils eine andere Technologie oder Infrastruktur wie RabbitMQ, Azure Service Bus oder ein anderer Drittanbieter-Open Source- oder kommerzieller Servicebus zum Einsatz kommt.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Verwendung von Nachrichtenbrokern und Dienstbussen für Produktionssysteme

Wie im Abschnitt über die Architektur bereits erwähnt, haben Sie bei der Implementierung des abstrakten Ereignisbusses die Wahl zwischen verschiedenen Messaging-Technologien. Diese Technologien werden jedoch auf unterschiedlichen Ebenen eingesetzt. So setzt der Nachrichtenbrokertransport RabbitMQ beispielsweise im Vergleich zu kommerziellen Produkten wie Azure Service Bus, NServiceBus, MassTransit oder Brighter auf einer unteren Ebene an. Die meisten dieser Produkte können zusätzlich zu RabbitMQ oder Azure Service Bus verwendet werden. Die Auswahl des Produkts hängt davon ab, wie viele Features und wie viel standardmäßige Skalierbarkeit Sie für Ihre Anwendung benötigen.

Für die Implementierung von nur einem Ereignisbus-Proof-of-Concepts für die Entwicklungsumgebung wie im eShopOnContainers-Beispiel ist eine einfache Implementierung zusätzlich zu einer als Container ausgeführten RabbitMQ-Installation möglicherweise ausreichend. Für unternehmenskritische Systeme und Produktionssysteme, für die eine hohe Skalierbarkeit erforderlich ist, sollten Sie jedoch Azure Service Bus testen und verwenden.

Wenn Sie allgemeine Abstraktionen und umfangreichere Features wie [Sagas](https://docs.particular.net/nservicebus/sagas/) für Prozesse mit langer Ausführungsdauer benötigen, die eine verteilte Entwicklung erleichtern, lohnt es sich, andere kommerzielle und Open-Source-Service Busse wie NServiceBus, MassTransit und Brighter zu testen. In diesem Fall sind die zu verwendenden Abstraktionen und die zu verwendende API diejenigen, die von diesen allgemeinen Service Bussen bereitgestellt werden, und nicht Ihre eigenen Abstraktionen (wie die [unter eShopOnContainers bereitgestellten einfachen Ereignisbusabstraktionen](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)). Zu diesem Zweck können Sie die [geforkten eShopOnContainers mithilfe von NServiceBus](https://go.particular.net/eShopOnContainers) (zusätzliches abgeleitetes Beispiel, durch Particular Software implementiert) untersuchen.

Natürlich können Sie auch Ihre eigenen Service Bus-Features auf Grundlage spezifischer Technologien wie RabbitMQ und Docker erstellen. Der hierzu erforderliche Mehraufwand ist für benutzerdefinierte Unternehmensanwendungen wahrscheinlich zu kostspielig.

Als Erinnerung: Die im eShopOnContainers-Beispiel vorgestellten Beispielereignisbus-Abstraktionen und -Implementierungen sind nur als Proof of Concept zu verwenden. Wenn Sie sich für eine asynchrone und ereignisgesteuerte Kommunikation entschieden haben, wählen Sie (wie in diesem Abschnitt erläutert) das Servicebusprodukt aus, das Ihren Anforderungen an die Produktion am besten entspricht.

## <a name="integration-events"></a>Integrationsereignisse

Integrationsereignisse werden zum Synchronisieren des Domänenstatus über mehrere Microservices oder externe Systeme hinweg verwendet. Dabei werden Integrationsereignisse außerhalb des Microservices veröffentlicht. Wenn ein Ereignis bei mehreren Empfängermicroservices (bei allen Microservices, die das Integrationsereignis abonniert haben) veröffentlicht wird, wird das Ereignis vom entsprechenden Ereignishandler des jeweiligen Empfängermicroservices verarbeitet.

Bei einem Integrationsereignis handelt es sich im Wesentlichen um eine Klasse zum Speichern von Daten wie im folgenden Beispiel:

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

Die Integrationsereignisse können auf der Anwendungsebene eines Microservices definiert werden, sodass sie von anderen Microservices entkoppelt sind. Dies ist in gewisser Weise mit der Definition von ViewModels im Server und im Client vergleichbar. Es wird davon abgeraten, eine Bibliothek mit Integrationsereignissen in mehreren Microservices zu nutzen, da dadurch diese Microservices mit einer Datenbibliothek mit Einzelereignisdefinitionen gekoppelt werden. Das sollten Sie aus demselben Grund vermeiden, aus dem Sie auch nicht ein Domänenmodell in mehreren Microservices nutzen: Microservices müssen absolut autonom sein.

Es gibt nur sehr wenige Arten von Bibliotheken, die Sie in mehreren Microservices nutzen können. Eine Art sind Bibliotheken, bei denen es sich wie bei der [Ereignisbusclient-API](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus) wie in eShopOnContainers um endgültige Anwendungsblöcke handelt. Eine andere Art sind Bibliotheken, die Tools bilden, die auch als NuGet-Komponenten gemeinsam genutzt werden können wie etwa JSON-Serialisierungsmodule.

## <a name="the-event-bus"></a>Der Ereignisbus

Ein Ereignisbus ermöglicht eine auf Veröffentlichen/Abonnieren basierende Kommunikation zwischen Microservices, ohne dass sich die Komponenten ausdrücklich berücksichtigen müssen (siehe Abbildung 6-19).

![Ein Diagramm, das das grundlegende Veröffentlichen/Abonnieren-Muster zeigt.](./media/integration-event-based-microservice-communications/publish-subscribe-basics.png)

**Abbildung 6-19**. Veröffentlichen/Abonnieren mit einem Ereignisbus

Das obige Diagramm zeigt, dass Microservice A ein Ereignis im Ereignisbus veröffentlicht, der dieses an die abonnierenden Microservices B und C verteilt, ohne dass der Herausgeber die Abonnenten kennen muss. Der Ereignisbus steht in Zusammenhang mit dem Observer-Muster und dem Publish-Subscribe-Muster.

### <a name="observer-pattern"></a>Observer-Muster

Beim [Observer-Muster](https://en.wikipedia.org/wiki/Observer_pattern) versorgt das primäre Objekt (als „Observable“ bezeichnet) andere interessierte Objekte (als „Observer“ bezeichnet) mit wichtigen Informationen (Ereignissen).

### <a name="publishsubscribe-pubsub-pattern"></a>Muster „Veröffentlichen/Abonnieren“

Das [Muster „Veröffentlichen/Abonnieren“](/previous-versions/msp-n-p/ff649664(v=pandp.10)) dient demselben Zweck wie das Beobachtermuster: andere Dienste sollen über bestimmte Ereignisse informiert werden. Es gibt jedoch einen wichtigen Unterschied zwischen dem Observer-Muster und dem Pub/Sub-Muster. Beim Beobachtermuster erfolgt die Übertragung direkt vom Beobachtbaren an die Beobachter, d. h. sie „kennen“ sich. Beim Pub/Sub-Muster gibt es jedoch eine dritte Komponente, den Broker oder Nachrichtenbroker bzw. Ereignisbus, den sowohl der Herausgeber als auch der Abonnent kennt. Wenn Sie also das Pub/Sub-Muster verwenden, sind Herausgeber und Abonnenten dank dem erwähnten Ereignisbus oder Nachrichtenbroker präzise entkoppelt.

### <a name="the-middleman-or-event-bus"></a>Der Vermittler oder Ereignisbus

Wie erzielen Sie Anonymität zwischen Herausgeber und Abonnent? Eine einfache Möglichkeit besteht darin, die gesamte Kommunikation einem Vermittler zu überlassen. Ein Ereignisbus ist ein solcher Vermittler.

Ein Ereignisbus besteht in der Regel aus zwei Teilen:

- aus der Abstraktion oder Schnittstelle

- aus einer oder mehreren Implementierungen

In Abbildung 6-19 wird deutlich, dass der Ereignisbus aus der Sicht der Anwendung lediglich einen Veröffentlichen/Abonnieren-Kanal darstellt. Sie können diesen asynchronen Code auf verschiedene Weisen implementieren. Er kann mehrere Implementierungen aufweisen, sodass je nach Umgebungsanforderungen (z.B. Produktions- oder Entwicklungsumgebung) zwischen diesen gewechselt werden kann.

In Abbildung 6-20 ist eine Abstraktion eines Ereignisbusses mit mehreren Implementierungen basierend auf Infrastrukturmessagingtechnologien wie RabbitMQ, Azure Service Bus oder andere Ereignis-/Nachrichtenbroker dargestellt.

![Diagramm, das das Hinzufügen einer Ereignisbus-Abstraktionsschicht zeigt.](./media/integration-event-based-microservice-communications/multiple-implementations-event-bus.png)

**Abbildung 6-20**. Mehrere Implementierungen eines Ereignisbusses

Es wird empfohlen, den Ereignisbus über eine Schnittstelle zu definieren, damit er mit verschiedenen Technologien wie RabbitMQ Azure Service Bus usw. implementiert werden kann. Wie bereits erwähnt sollten Sie eine eigene Abstraktion (die Ereignisbusschnittstelle) jedoch nur verwenden, wenn Sie grundlegende Ereignisbusfunktionen benötigen, die von Ihren Abstraktionen unterstützt werden. Wenn Sie umfangreichere Service Bus-Features benötigen, sollten Sie anstelle der eigenen Abstraktionen die API und die Abstraktionen verwenden, die von Ihrem bevorzugten kommerziellen Service Bus bereitgestellt werden.

### <a name="defining-an-event-bus-interface"></a>Definieren einer Ereignisbusschnittstelle

Zunächst werden Implementierungscode für die Ereignisbusschnittstelle und mögliche Implementierungen zu Untersuchungszwecken veranschaulicht. Die Schnittstelle sollte wie die folgende Schnittstelle allgemein und einfach gehalten sein.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);

    void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>;

    void SubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void UnsubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void Unsubscribe<T, TH>()
        where TH : IIntegrationEventHandler<T>
        where T : IntegrationEvent;
}
```

Die `Publish`-Methode ist einfach. Der Ereignisbus sendet das an ihn weitergeleitete Integrationsereignis an alle Microservices oder auch an externe Anwendungen, die dieses Ereignis abonniert haben. Diese Methode wird von dem Microservice verwendet, der das Ereignis veröffentlicht.

Die `Subscribe`-Methoden (abhängig von den Argumenten können mehrere Implementierungen verwendet werden) werden von den Microservices verwendet, die Ereignisse empfangen möchten. Diese Methode weist zwei Argumente auf. Beim ersten Argument handelt es sich um das Integrationsereignis, das abonniert werden kann (`IntegrationEvent`). Beim zweiten Argument handelt es sich um den Integrationsereignishandler (oder die Rückrufmethode) mit dem Namen `IIntegrationEventHandler<T>`. Dieses Argument wird ausgeführt, wenn der Empfängermicroservice diese Integrationsereignisnachricht empfängt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Einige Messaginglösungen, die bereit für die Produktion sind:

- **Azure Service Bus** \
  <https://docs.microsoft.com/azure/service-bus-messaging/>
  
- **NServiceBus** \
  <https://particular.net/nservicebus>
  
- **MassTransit** \
  <https://masstransit-project.com/>

> [!div class="step-by-step"]
> [Zurück](database-server-container.md)
> [Weiter](rabbitmq-event-bus-development-test-environment.md)
