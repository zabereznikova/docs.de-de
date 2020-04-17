---
title: Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Verwenden von RabbitMQ zum Implementieren eines Ereignisbusmessagings für Integrationsereignisse für die Entwicklung oder für Testumgebungen
ms.date: 10/02/2018
ms.openlocfilehash: 12e37fabfe915b4d2089d27f7852528a9a037d3c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988296"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="02c6d-103">Implementieren eines Ereignisbusses mit RabbitMQ für die Entwicklung oder für Testumgebungen</span><span class="sxs-lookup"><span data-stu-id="02c6d-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="02c6d-104">Wenn Sie den benutzerdefinierten Ereignisbus basierend auf RabbitMQ erstellen, das in einem Container ausgeführt wird, so wie bei der eShopOnContainers-Anwendung, sollte er nur für Entwicklungszwecke und Testumgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02c6d-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="02c6d-105">Sie sollten ihn nicht für Ihre Produktionsumgebung verwenden, es sei denn, Sie erstellen ihn als Teil eines produktionsbereiten Service Busses.</span><span class="sxs-lookup"><span data-stu-id="02c6d-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="02c6d-106">Einem einfachen benutzerdefinierten Ereignisbus fehlen ggf. viele produktionsbereite wichtige Features, über die ein kommerzieller Service Bus verfügt.</span><span class="sxs-lookup"><span data-stu-id="02c6d-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="02c6d-107">Eine der benutzerdefinierten Ereignisbusimplementierungen in eShopOnContainers ist im Grunde eine Bibliothek, die die RabbitMQ-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="02c6d-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="02c6d-108">(Es gibt eine andere Implementierung, die auf Azure Service Bus basiert.)</span><span class="sxs-lookup"><span data-stu-id="02c6d-108">(There's another implementation based on Azure Service Bus.)</span></span>

<span data-ttu-id="02c6d-109">Aufgrund der Implementierung von Ereignisbussen mit RabbitMQ können Microservices, wie in Abbildung 6-21 dargestellt, Ereignisse abonnieren, veröffentlichen und empfangen.</span><span class="sxs-lookup"><span data-stu-id="02c6d-109">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![Diagramm, das RabbitMQ zwischen Nachrichtenabsender und Nachrichtenempfänger zeigt.](./media/rabbitmq-event-bus-development-test-environment/rabbitmq-implementation.png)

<span data-ttu-id="02c6d-111">**Abbildung 6-21**.</span><span class="sxs-lookup"><span data-stu-id="02c6d-111">**Figure 6-21.**</span></span> <span data-ttu-id="02c6d-112">RabbitMQ-Implementierung eines Ereignisbusses</span><span class="sxs-lookup"><span data-stu-id="02c6d-112">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="02c6d-113">RabbitMQ fungiert als Mittler zwischen dem Nachrichtenverleger und den Abonnenten, um die Verteilung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="02c6d-113">RabbitMQ functions as an intermediary between message publisher and subscribers, to handle distribution.</span></span> <span data-ttu-id="02c6d-114">Die EventBusRabbitMQ-Klasse implementiert im Code die generische IEventBus-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="02c6d-114">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="02c6d-115">Dies basiert auf Abhängigkeitsinjektion, damit Sie von dieser Dev/Test-Version auf eine Produktionsversion umstellen können.</span><span class="sxs-lookup"><span data-stu-id="02c6d-115">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="02c6d-116">Die RabbitMQ-Implementierung eines Beispiel-Dev/Test-Ereignisbusses ist Standardcode.</span><span class="sxs-lookup"><span data-stu-id="02c6d-116">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="02c6d-117">Er muss die Verbindung mit dem RabbitMQ-Server verwalten und Code für die Veröffentlichung von eines Nachrichtenereignisses in den Warteschlangen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="02c6d-117">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="02c6d-118">Darüber hinaus muss er ein Wörterbuch von Sammlungen der Integrationsereignishandler für jeden Ereignistyp implementieren. Diese Ereignistypen können, wie in Abbildung 6-21 dargestellt, eine unterschiedliche Instanziierung haben und verschiedene Abonnements für jeden Empfängermicroservice.</span><span class="sxs-lookup"><span data-stu-id="02c6d-118">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="02c6d-119">Implementieren einer einfachen Publish-Methode mit RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="02c6d-119">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="02c6d-120">Der folgende Code ist eine ***vereinfachte*** Version einer Ereignisbusimplementierung für RabbitMQ, um das gesamte Szenario vorzustellen.</span><span class="sxs-lookup"><span data-stu-id="02c6d-120">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="02c6d-121">Die Verbindung wird nicht wirklich so hergestellt.</span><span class="sxs-lookup"><span data-stu-id="02c6d-121">You don't really handle the connection this way.</span></span> <span data-ttu-id="02c6d-122">Eine vollständige Implementierung finden Sie im tatsächlichen Code im Repository [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).</span><span class="sxs-lookup"><span data-stu-id="02c6d-122">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="02c6d-123">Der [tatsächliche Code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) der Publish-Methode in der Anwendung „eShopOnContainers“ wird mithilfe der [Polly](https://github.com/App-vNext/Polly)-Wiederholungsrichtlinie verbessert, die die Aufgabe eine bestimmte Anzahl von Malen wiederholt, falls der RabbitMQ-Container noch nicht bereit ist.</span><span class="sxs-lookup"><span data-stu-id="02c6d-123">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="02c6d-124">Dies kann auftreten, wenn die Container mithilfe von „docker-compose“ gestartet werden. Ein RabbitMQ-Container startet z.B. möglicherweise langsamer als die anderen Container.</span><span class="sxs-lookup"><span data-stu-id="02c6d-124">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="02c6d-125">Wie bereits erwähnt, gibt es viele mögliche Konfigurationen in RabbitMQ. Daher sollte dieser Code nur für Entwicklungs- und Testumgebungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02c6d-125">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="02c6d-126">Implementieren des Abonnementcodes mit der RabbitMQ-API</span><span class="sxs-lookup"><span data-stu-id="02c6d-126">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="02c6d-127">So wie bei dem Publish-Code ist der folgende eine Vereinfachung eines Teils der Ereignisbusimplementierung für RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="02c6d-127">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="02c6d-128">Wie gesagt müssen Sie ihn normalerweise nicht ändern, es sei denn, Sie nehmen Verbesserungen vor.</span><span class="sxs-lookup"><span data-stu-id="02c6d-128">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();

        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

<span data-ttu-id="02c6d-129">Jeder Ereignistyp hat einen zugehörigen Kanal, über den Ereignisse von RabbitMQ abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="02c6d-129">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="02c6d-130">In jedem Kanal und Ereignistyp können so viele Ereignishandler vorhanden sein wie nötig.</span><span class="sxs-lookup"><span data-stu-id="02c6d-130">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="02c6d-131">Die Subscribe-Methode akzeptiert ein IIntegrationEventHandler-Objekt, das einer Rückrufmethode im aktuellen Microservice ähnelt, sowie ein zugehöriges IntegrationEvent-Objekt.</span><span class="sxs-lookup"><span data-stu-id="02c6d-131">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="02c6d-132">Der Code fügt diesen Ereignishandler dann zur Liste der Ereignishandler hinzu, über die jeder Integrationsereignistyp pro Clientmicroservice verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="02c6d-132">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="02c6d-133">Wenn der Clientcode noch nicht von dem Ereignis abonniert wurde, erstellt er einen Kanal für den Ereignistyp, um Ereignisse im Push-Format von RabbitMQ empfangen zu können, wenn das Ereignis in einem anderen Dienst veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="02c6d-133">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

<span data-ttu-id="02c6d-134">Wie bereits erwähnt verfügt der in eShopOnContainers implementierte Ereignisbus nur über einen Bildungszweck, da er nur die Hauptszenarios verarbeitet und nicht für die Produktion bereit ist.</span><span class="sxs-lookup"><span data-stu-id="02c6d-134">As mentioned above, the event bus implemented in eShopOnContainers has only and educational purpose, since it only handles the main scenarios, so it's not ready for production.</span></span>

<span data-ttu-id="02c6d-135">Lesen Sie für Produktionsszenarios die zusätzlichen nachfolgenden Ressourcen für RabbitMQ und den Abschnitt [Implementieren ereignisbasierter Kommunikation zwischen Microservices](./integration-event-based-microservice-communications.md#additional-resources).</span><span class="sxs-lookup"><span data-stu-id="02c6d-135">For production scenarios check the additional resources below, specific for RabbitMQ, and the [Implementing event-based communication between microservices](./integration-event-based-microservice-communications.md#additional-resources) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02c6d-136">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="02c6d-136">Additional resources</span></span>

<span data-ttu-id="02c6d-137">Eine Lösung mit Support für RabbitMQ, die für die Produktion bereit ist.</span><span class="sxs-lookup"><span data-stu-id="02c6d-137">A production-ready solutions with support for RabbitMQ.</span></span>

- <span data-ttu-id="02c6d-138">**EasyNetQ:** Open Source .NET API-Client für RabbitMQ </span><span class="sxs-lookup"><span data-stu-id="02c6d-138">**EasyNetQ** - Open Source .NET API client for RabbitMQ </span></span>\
  <http://easynetq.com/>

- <span data-ttu-id="02c6d-139">**MassTransit** </span><span class="sxs-lookup"><span data-stu-id="02c6d-139">**MassTransit** </span></span>\
  <https://masstransit-project.com/>
  
> [!div class="step-by-step"]
> <span data-ttu-id="02c6d-140">[Zurück](integration-event-based-microservice-communications.md)
> [Weiter](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="02c6d-140">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>
