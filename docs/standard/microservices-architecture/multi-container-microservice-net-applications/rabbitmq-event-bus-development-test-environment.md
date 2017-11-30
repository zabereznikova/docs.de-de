---
title: "Implementieren eine Ereignisbus mit RabbitMQ für die Umgebung für Entwicklungs- oder Testserver"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren eine Ereignisbus mit RabbitMQ für die Umgebung für Entwicklungs- oder Testserver"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="832a5-104">Implementieren eine Ereignisbus mit RabbitMQ für die Umgebung für Entwicklungs- oder Testserver</span><span class="sxs-lookup"><span data-stu-id="832a5-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="832a5-105">Es sollten zunächst besagt, dass Ihr benutzerdefiniertes Ereignisbus basierend auf RabbitMQ in einem Container ausgeführt wird, wie die eShopOnContainers-Anwendung erstellen, es nur für Entwicklungs- und testumgebungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="832a5-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="832a5-106">Sie sollten nicht für Ihre produktionsumgebung verwendet, wenn Sie ihn als Teil einer produktionsbereite Servicebus erstellen.</span><span class="sxs-lookup"><span data-stu-id="832a5-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="832a5-107">Eine einfache benutzerdefinierte Ereignisbus produktionsbereite viele Funktionen fehlen möglicherweise, die ein kommerziellen Servicebus verfügt.</span><span class="sxs-lookup"><span data-stu-id="832a5-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="832a5-108">Die benutzerdefinierte eShopOnContainers-Implementierung von einem Ereignisbus ist im Grunde eine Bibliothek mithilfe der RabbitMQ-API.</span><span class="sxs-lookup"><span data-stu-id="832a5-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="832a5-109">Die Implementierung ermöglicht Microservices Ereignisse abonnieren, Veröffentlichen von Ereignissen und Empfangen von Ereignissen, wie in Abbildung 8-21 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="832a5-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="832a5-110">**Abbildung 8-21.**</span><span class="sxs-lookup"><span data-stu-id="832a5-110">**Figure 8-21.**</span></span> <span data-ttu-id="832a5-111">RabbitMQ-Implementierung von einem Ereignisbus</span><span class="sxs-lookup"><span data-stu-id="832a5-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="832a5-112">Im Code implementiert die EventBusRabbitMQ-Klasse die generische IEventBus-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="832a5-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="832a5-113">Dies basiert auf Abhängigkeitsinjektion, damit Sie von dieser Version Dev/Test auf eine Produktionsversion austauschen können.</span><span class="sxs-lookup"><span data-stu-id="832a5-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="832a5-114">Die RabbitMQ Implementierung eine Beispiel-Dev/Test-Ereignisbus ist Standardcode.</span><span class="sxs-lookup"><span data-stu-id="832a5-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="832a5-115">Er verfügt über die Verbindung mit dem Server RabbitMQ behandeln und Code für die Veröffentlichung von einem Nachrichtenereignis an die Warteschlangen bieten.</span><span class="sxs-lookup"><span data-stu-id="832a5-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="832a5-116">Es muss auch ein Wörterbuch von Auflistungen der Ereignishandler für jeden Ereignistyp Integration implementieren; Diese Ereignistypen können eine andere Instanziierung und verschiedenen Abonnements für jeden Empfänger Microservice verfügen, wie in Abbildung 8-21 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="832a5-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="832a5-117">Implementieren eine einfache Methode mit RabbitMQ veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="832a5-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="832a5-118">Der folgende Code ist Teil der eShopOnContainers Ereignis nachrichtenbusimplementierung für RabbitMQ, damit Sie in der Regel nicht benötigen, es zu codieren, es sei denn, Sie Verbesserungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="832a5-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="832a5-119">Der Code Ruft eine Verbindung und Kanal zu RabbitMQ, erstellt eine Nachricht und veröffentlicht dann die Nachricht in die Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="832a5-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="832a5-120">Die [tatsächlichen Code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) der veröffentlichen Methode in der Anwendung eShopOnContainers verbessert, indem eine [Polly](https://github.com/App-vNext/Polly) wiederholungsrichtlinie auf, die die Aufgabe eine bestimmte Anzahl von Malen wiederholt wird, für den Fall, dass der Container RabbitMQ ist nicht bereit.</span><span class="sxs-lookup"><span data-stu-id="832a5-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="832a5-121">Dies kann auftreten, wenn verfassen Docker-Container; wird gestartet z. B. Starten des Containers RabbitMQ möglicherweise langsamer als die anderen Container.</span><span class="sxs-lookup"><span data-stu-id="832a5-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="832a5-122">Wie bereits erwähnt, sind viele mögliche Konfigurationen in RabbitMQ, damit dieser Code nur für Entwicklungs-und testumgebungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="832a5-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="832a5-123">Die Implementierung des Codes Abonnement mit der RabbitMQ-API</span><span class="sxs-lookup"><span data-stu-id="832a5-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="832a5-124">Als mit dem Code veröffentlichen ist der folgende Code eine Vereinfachung der Teil der Ereignis-nachrichtenbusimplementierung für RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="832a5-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="832a5-125">Erneut aus, in der Regel nicht müssen Sie es ändern, es sei denn, Sie sind es verbessern.</span><span class="sxs-lookup"><span data-stu-id="832a5-125">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

<span data-ttu-id="832a5-126">Jeder Ereignis hat einen zugehörigen Kanal zu RabbitMQ Ereignisse entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="832a5-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="832a5-127">Sie können dann so viele Ereignishandler pro Kanal und den Ereignistyp nach Bedarf verwenden.</span><span class="sxs-lookup"><span data-stu-id="832a5-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="832a5-128">Subscribe-Methode akzeptiert ein IIntegrationEventHandler-Objekt, das wie eine Rückrufmethode in der aktuellen Microservice ist, sowie die verwandte IntegrationEvent-Objekt.</span><span class="sxs-lookup"><span data-stu-id="832a5-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="832a5-129">Der Code fügt dann diesem Ereignishandler zur Liste der Ereignishandler, die jeden Ereignistyp Integration pro Client Microservice aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="832a5-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="832a5-130">Wenn Clientcode nicht auf das Ereignis abonniert wurde, erstellt der Code einen Kanal für das Ereignis des Typs an, damit sie Ereignisse in einem Push-Format als RabbitMQ empfangen kann, wenn das Ereignis aus jeder andere Dienst veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="832a5-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="832a5-131">[Vorherigen] (Integration-Ereignis-Basis-Microservice-communications.md) [weiter] (Abonnieren events.md)</span><span class="sxs-lookup"><span data-stu-id="832a5-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
