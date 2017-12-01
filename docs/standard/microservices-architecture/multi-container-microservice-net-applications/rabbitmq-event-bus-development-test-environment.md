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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementieren eine Ereignisbus mit RabbitMQ für die Umgebung für Entwicklungs- oder Testserver

Es sollten zunächst besagt, dass Ihr benutzerdefiniertes Ereignisbus basierend auf RabbitMQ in einem Container ausgeführt wird, wie die eShopOnContainers-Anwendung erstellen, es nur für Entwicklungs- und testumgebungen verwendet werden soll. Sie sollten nicht für Ihre produktionsumgebung verwendet, wenn Sie ihn als Teil einer produktionsbereite Servicebus erstellen. Eine einfache benutzerdefinierte Ereignisbus produktionsbereite viele Funktionen fehlen möglicherweise, die ein kommerziellen Servicebus verfügt.

Die benutzerdefinierte eShopOnContainers-Implementierung von einem Ereignisbus ist im Grunde eine Bibliothek mithilfe der RabbitMQ-API. Die Implementierung ermöglicht Microservices Ereignisse abonnieren, Veröffentlichen von Ereignissen und Empfangen von Ereignissen, wie in Abbildung 8-21 dargestellt.

![](./media/image22.png)

**Abbildung 8-21.** RabbitMQ-Implementierung von einem Ereignisbus

Im Code implementiert die EventBusRabbitMQ-Klasse die generische IEventBus-Schnittstelle. Dies basiert auf Abhängigkeitsinjektion, damit Sie von dieser Version Dev/Test auf eine Produktionsversion austauschen können.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

Die RabbitMQ Implementierung eine Beispiel-Dev/Test-Ereignisbus ist Standardcode. Er verfügt über die Verbindung mit dem Server RabbitMQ behandeln und Code für die Veröffentlichung von einem Nachrichtenereignis an die Warteschlangen bieten. Es muss auch ein Wörterbuch von Auflistungen der Ereignishandler für jeden Ereignistyp Integration implementieren; Diese Ereignistypen können eine andere Instanziierung und verschiedenen Abonnements für jeden Empfänger Microservice verfügen, wie in Abbildung 8-21 dargestellt.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementieren eine einfache Methode mit RabbitMQ veröffentlichen

Der folgende Code ist Teil der eShopOnContainers Ereignis nachrichtenbusimplementierung für RabbitMQ, damit Sie in der Regel nicht benötigen, es zu codieren, es sei denn, Sie Verbesserungen vornehmen. Der Code Ruft eine Verbindung und Kanal zu RabbitMQ, erstellt eine Nachricht und veröffentlicht dann die Nachricht in die Warteschlange.

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

Die [tatsächlichen Code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) der veröffentlichen Methode in der Anwendung eShopOnContainers verbessert, indem eine [Polly](https://github.com/App-vNext/Polly) wiederholungsrichtlinie auf, die die Aufgabe eine bestimmte Anzahl von Malen wiederholt wird, für den Fall, dass der Container RabbitMQ ist nicht bereit. Dies kann auftreten, wenn verfassen Docker-Container; wird gestartet z. B. Starten des Containers RabbitMQ möglicherweise langsamer als die anderen Container.

Wie bereits erwähnt, sind viele mögliche Konfigurationen in RabbitMQ, damit dieser Code nur für Entwicklungs-und testumgebungen verwendet werden soll.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Die Implementierung des Codes Abonnement mit der RabbitMQ-API

Als mit dem Code veröffentlichen ist der folgende Code eine Vereinfachung der Teil der Ereignis-nachrichtenbusimplementierung für RabbitMQ. Erneut aus, in der Regel nicht müssen Sie es ändern, es sei denn, Sie sind es verbessern.

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

Jeder Ereignis hat einen zugehörigen Kanal zu RabbitMQ Ereignisse entnommen werden. Sie können dann so viele Ereignishandler pro Kanal und den Ereignistyp nach Bedarf verwenden.

Subscribe-Methode akzeptiert ein IIntegrationEventHandler-Objekt, das wie eine Rückrufmethode in der aktuellen Microservice ist, sowie die verwandte IntegrationEvent-Objekt. Der Code fügt dann diesem Ereignishandler zur Liste der Ereignishandler, die jeden Ereignistyp Integration pro Client Microservice aufweisen kann. Wenn Clientcode nicht auf das Ereignis abonniert wurde, erstellt der Code einen Kanal für das Ereignis des Typs an, damit sie Ereignisse in einem Push-Format als RabbitMQ empfangen kann, wenn das Ereignis aus jeder andere Dienst veröffentlicht wird.


>[!div class="step-by-step"]
[Vorherigen] (Integration-Ereignis-Basis-Microservice-communications.md) [weiter] (Abonnieren events.md)
