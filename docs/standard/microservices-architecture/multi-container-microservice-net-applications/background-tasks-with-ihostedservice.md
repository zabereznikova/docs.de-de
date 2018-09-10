---
title: Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 6ce9e40334e80e8bd17ce2f3d2569a1e3c39d09e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44128867"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="e7d16-103">Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse</span><span class="sxs-lookup"><span data-stu-id="e7d16-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="e7d16-104">Ab einem bestimmten Zeitpunkt müssen möglicherweise in auf Microservices basierende Anwendungen oder auch in anderen Anwendungen Hintergrundtasks und geplante Aufträge implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="e7d16-105">Die Besonderheit bei der Verwendung einer Microservicesarchitektur ist, dass Sie einen einzelnen Microserviceprozess oder -container implementieren können, um diese Hintergrundtasks zu hosten. Dadurch kann bei Bedarf eine vertikale Skalierung vorgenommen und zusätzlich sichergestellt werden, dass nur eine Instanz des Microserviceprozesses oder -containers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="e7d16-106">In .NET Core werden diese Tasks als gehostete Dienste bezeichnet, da sie Dienste oder Logiken darstellen, die in einem Host, in einer Anwendung oder in einem Microservice gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-106">From a generic point of view, in .NET Core we called these type of tasks Hosted Services, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="e7d16-107">Beachten Sie, dass in diesem Fall der gehostete Dienst einfach einer Klasse mit der Logik des Hintergrundtasks entspricht.</span><span class="sxs-lookup"><span data-stu-id="e7d16-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="e7d16-108">Seit .NET Core 2.0 stellt das Framework die neue Schnittstelle <xref:Microsoft.Extensions.Hosting.IHostedService> bereit, mit der Sie gehostete Dienste einfach implementieren können.</span><span class="sxs-lookup"><span data-stu-id="e7d16-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="e7d16-109">Die Grundidee besteht darin, mehrere Hintergrundtasks (gehostete Dienste) zu registrieren, die neben dem Host oder Webhost im Hintergrund ausgeführt werden. Dies wird in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7d16-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image below.</span></span>

![](./media/image26.png)

<span data-ttu-id="e7d16-110">**Abbildung 8-25.**</span><span class="sxs-lookup"><span data-stu-id="e7d16-110">**Figure 8-25.**</span></span> <span data-ttu-id="e7d16-111">Verwenden von IHostedService mit Host und WebHost</span><span class="sxs-lookup"><span data-stu-id="e7d16-111">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="e7d16-112">Beachten Sie den Unterschied zwischen `WebHost` und `Host`.</span><span class="sxs-lookup"><span data-stu-id="e7d16-112">Note the difference made between `WebHost` and `Host`.</span></span> <span data-ttu-id="e7d16-113">`WebHost` (eine Basisklasse, die `IWebHost` implementiert) ist in ASP.NET Core 2.0 das Infrastrukturartefakt, mit dem Sie HTTP-Serverfunktionen für Ihren Prozess (z.B. das Implementieren einer MVC-Webanwendung oder eines Web-API-Diensts) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e7d16-113">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="e7d16-114">Diese Klasse enthält in ASP.NET Core alle optimierten Infrastrukturfunktionen, mit der Sie Dependency Injection verwenden, der HTTP-Pipeline Middlewareanwendungen hinzufügen und `IHostedServices` für Hintergrundtasks nutzen können.</span><span class="sxs-lookup"><span data-stu-id="e7d16-114">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the HTTP pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="e7d16-115">`Host` (eine Basisklasse, die `IHost` implementiert) stellt jedoch in .NET Core 2.1 eine Neuerung dar.</span><span class="sxs-lookup"><span data-stu-id="e7d16-115">A `Host` (base class implementing `IHost`), however, is something new in .NET Core 2.1.</span></span> <span data-ttu-id="e7d16-116">Mit `Host` können Sie eine ähnliche Infrastruktur wie mit `WebHost` (Dependency Injection, gehostete Dienste usw.) verwenden. Der Unterschied besteht darin, dass Sie einen einfacheren und schlankeren Prozess für den Host verwenden und auf Verknüpfungen mit MVC, einer Web-API oder HTTP-Serverfunktionen verzichten.</span><span class="sxs-lookup"><span data-stu-id="e7d16-116">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="e7d16-117">Sie können daher entweder einen spezialisierten Hostprozess mit IHost erstellen, um ausschließlich gehostete Dienste (beispielsweise einen Microservice zum Hosten von `IHostedServices`) zu verarbeiten, oder aber einen vorhandenen ASP.NET Core-`WebHost` wie eine ASP.NET Core-Web-API oder eine MVC-Anwendung erweitern.</span><span class="sxs-lookup"><span data-stu-id="e7d16-117">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span> 

<span data-ttu-id="e7d16-118">Je nach Geschäfts- und Skalierbarkeitsanforderungen hat jeder Ansatz seine Vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="e7d16-118">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="e7d16-119">Falls Ihre Hintergrundtasks nichts mit HTTP (IWebHost) zu tun haben und Sie .NET Core 2.1 verwenden, wird empfohlen, IHost zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-119">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use and IHost, when available in .NET Core 2.1.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="e7d16-120">Registrieren von gehosteten Diensten in WebHost oder Host</span><span class="sxs-lookup"><span data-stu-id="e7d16-120">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="e7d16-121">Im Folgenden wird die `IHostedService`-Schnittstelle genauer beschrieben, da sie in `WebHost` und `Host` ähnlich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-121">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span> 

<span data-ttu-id="e7d16-122">SignalR ist ein Beispiel für ein Artefakt, das gehostete Dienste verwendet. Sie können den Dienst aber auch für einfachere Aufgaben verwenden. Hierzu zählt etwa Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e7d16-122">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

-   <span data-ttu-id="e7d16-123">ein Hintergrundtask, der eine Datenbank abruft und nach Änderungen sucht</span><span class="sxs-lookup"><span data-stu-id="e7d16-123">A background task polling a database looking for changes.</span></span>
-   <span data-ttu-id="e7d16-124">ein geplanter Task, der einen Cache regelmäßig aktualisiert</span><span class="sxs-lookup"><span data-stu-id="e7d16-124">A scheduled task updating some cache periodically.</span></span>
-   <span data-ttu-id="e7d16-125">eine Implementierung von QueueBackgroundWorkItem, durch die ein Task in einem Hintergrundthread ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="e7d16-125">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
-   <span data-ttu-id="e7d16-126">das Verarbeiten von Nachrichten aus einer Nachrichtenwarteschlange im Hintergrund einer Webanwendung, während allgemeine Dienste wie `ILogger` gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-126">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
-   <span data-ttu-id="e7d16-127">ein Hintergrundtask, der mit `Task.Run()` gestartet wird</span><span class="sxs-lookup"><span data-stu-id="e7d16-127">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="e7d16-128">Alle Aktionen lassen sich in einen Hintergrundtask auslagern, der auf IHostedService basiert.</span><span class="sxs-lookup"><span data-stu-id="e7d16-128">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="e7d16-129">Sie können einem `WebHost` oder `Host` ein oder mehrere `IHostedServices` hinzufügen, indem Sie sie über den standardmäßigen Dependency Injection-Vorgang in einem ASP.NET Core-`WebHost` (oder in einem `Host` in .NET Core 2.1) registrieren.</span><span class="sxs-lookup"><span data-stu-id="e7d16-129">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1).</span></span> <span data-ttu-id="e7d16-130">Dabei müssen Sie die gehosteten Dienste in der bekannten `ConfigureServices()`-Methode der `Startup`-Klasse registrieren, was im folgenden Codeausschnitt einer typischen ASP.NET-WebHost-Klasse demonstriert wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-130">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span> 

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{            
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="e7d16-131">Der Code für den gehosteten Dienst `GracePeriodManagerService` entspricht dem Code aus dem Microservice für Bestellungen in eShopOnContainers. Bei den anderen beiden Diensten handelt es sich hingegen nur um zwei zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e7d16-131">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="e7d16-132">Die Ausführung des `IHostedService`-Hintergrundtasks wird mit der Lebensdauer der Anwendung (also des Hosts oder des Microservices) koordiniert.</span><span class="sxs-lookup"><span data-stu-id="e7d16-132">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="e7d16-133">Die Tasks werden registriert, wenn die Anwendung gestartet und eine ordnungsgemäße Aktion ausgeführt oder wenn die Anwendung beendet wird und dabei Ressourcen bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-133">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="e7d16-134">Ohne die Nutzung von `IHostedService` ließe sich ein Hintergrundthread erstellen, in dem ein beliebiger Task ausgeführt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="e7d16-134">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="e7d16-135">Zum Beendigungszeitpunkt der Anwendung würde der Thread dann einfach beendet werden, und ordnungsgemäße Aktionen zur Bereinigung von Ressourcen könnten nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-135">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>


## <a name="the-ihostedservice-interface"></a><span data-ttu-id="e7d16-136">Die IHostedService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7d16-136">The IHostedService interface</span></span>

<span data-ttu-id="e7d16-137">Beim Registrieren von `IHostedService` ruft .NET Core die Methoden `StartAsync()` und `StopAsync()` des Typs `IHostedService` während des Anwendungsstarts und -stopps auf.</span><span class="sxs-lookup"><span data-stu-id="e7d16-137">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="e7d16-138">Nach dem Serverstart wird die Startmethode aufgerufen, und `IApplicationLifetime.ApplicationStarted` wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e7d16-138">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="e7d16-139">Die `IHostedService`-Schnittstelle sieht in .NET Core wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e7d16-139">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```
<span data-ttu-id="e7d16-140">Sie können mehrere Implementierungen von IHostedService erstellen und wie zuvor gezeigt in der `ConfigureService()`-Methode des Dependency Injection-Containers registrieren.</span><span class="sxs-lookup"><span data-stu-id="e7d16-140">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="e7d16-141">Alle gehosteten Dienste werden zusammen mit der Anwendung und dem Microservice gestartet und beendet.</span><span class="sxs-lookup"><span data-stu-id="e7d16-141">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="e7d16-142">Als Entwickler sind Sie dafür verantwortlich, die Beendigungsaktion Ihrer Dienste zu verarbeiten, wenn die `StopAsync()`-Methode vom Host ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-142">As a developer, you are responsible for handling the stopping action or your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="e7d16-143">Implementieren von IHostedService mit einer eigenen Klasse für gehostete Dienste, die von der Basisklasse BackgroundService abgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="e7d16-143">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="e7d16-144">Sie haben die Möglichkeit, eine eigene Klasse für gehostete Dienste neu zu erstellen und `IHostedService` zu implementieren, was im Fall von .NET Core 2.0 sogar unumgänglich ist.</span><span class="sxs-lookup"><span data-stu-id="e7d16-144">You could go ahead and create you custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span> 

<span data-ttu-id="e7d16-145">Da allerdings die meisten Hintergrundtasks ähnliche Anforderungen an die Verwaltung von Abbruchtoken und an weitere typische Vorgänge stellen, bietet .NET Core 2.1 hierfür die praktische abstrakte Basisklasse BackgroundService an, von der eigene Klassen abgeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7d16-145">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, .NET Core 2.1 will be providing a very convenient abstract base class you can derive from, named BackgroundService.</span></span>

<span data-ttu-id="e7d16-146">Diese Klasse fasst die wesentlichen Aufgaben zusammen, die zum Einrichten der Hintergrundtasks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e7d16-146">That class provides the main work needed to set up the background task.</span></span> <span data-ttu-id="e7d16-147">Beachten Sie, dass diese Klasse bereits in der Bibliothek für .NET Core 2.1 enthalten ist. Sie brauchen sie daher nicht selbst zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e7d16-147">Note that this class will come in the .NET Core 2.1 library so you don’t need to write it.</span></span>

<span data-ttu-id="e7d16-148">Noch wurde .NET Core 2.1 jedoch nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="e7d16-148">However, as of the time of this writing, .NET Core 2.1 has not been released.</span></span> <span data-ttu-id="e7d16-149">Aus diesem Grund wird in der eShopOnContainers-Anwendung, für die aktuell .NET Core 2.0 verwendet wird, nur vorübergehend diese Klasse aus dem Open Source-Repository für .NET Core 2.1 eingebunden (nur die Open Source-Lizenz ist erforderlich, eine proprietäre Lizenz wird nicht benötigt), da sie mit der aktuellen IHostedService-Schnittstelle in .NET Core 2.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="e7d16-149">Therefore, in eShopOnContainers which is currently using .NET Core 2.0, we are just temporally incorporating that class from the .NET Core 2.1 open-source repo (no need of any proprietary license other than the open-source license) because it is compatible with the current IHostedService interface in .NET Core 2.0.</span></span> <span data-ttu-id="e7d16-150">Sobald .NET Core 2.1 freigegeben wird, müssen Sie lediglich auf das richtige NuGet-Paket verweisen.</span><span class="sxs-lookup"><span data-stu-id="e7d16-150">When .NET Core 2.1 is released, you’ll just need to point to the right NuGet package.</span></span>

<span data-ttu-id="e7d16-151">Im folgenden Codeausschnitt ist die in .NET Core 2.1 implementierte abstrakte Basisklasse BackgroundService zu sehen.</span><span class="sxs-lookup"><span data-stu-id="e7d16-151">The next code is the abstract BackgroundService base class as implemented in .NET Core 2.1.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0. 
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts = 
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it, 
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }
    
    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="e7d16-152">Wenn Sie eine Klasse aus der oben gezeigten abstrakten Basisklasse ableiten, müssen Sie dank der vererbten Implementierung nur die `ExecuteAsync()`-Methode in Ihrer eigenen Klasse für gehostete Dienste implementieren. Dies wird im folgenden vereinfachten Codeausschnitt aus eShopOnContainers demonstriert, in dem eine Datenbank abgerufen und Integrationsereignisse bei Bedarf im Ereignisbus veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-152">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{        
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
        {
            //Constructor’s parameters validations...       
        }

        protected override async Task ExecuteAsync(CancellationToken stoppingToken)
        {
            _logger.LogDebug($"GracePeriodManagerService is starting.");

            stoppingToken.Register(() => 
                    _logger.LogDebug($" GracePeriod background task is stopping."));

            while (!stoppingToken.IsCancellationRequested)
            {
                _logger.LogDebug($"GracePeriod task doing background work.");

                // This eShopOnContainers method is querying a database table 
                // and publishing events into the Event Bus (RabbitMS / ServiceBus)
                CheckConfirmedGracePeriodOrders();

                await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
            }
            
            _logger.LogDebug($"GracePeriod background task is stopping.");

        }

        protected override async Task StopAsync (CancellationToken stoppingToken)
        {
               // Run your graceful clean-up actions
        }
}
```

<span data-ttu-id="e7d16-153">Im Fall von eShopOnContainers wird eine Anwendungsmethode ausgeführt, durch die eine Datenbanktabelle abgefragt wird. Diese sucht nach Bestellungen mit einem bestimmten Zustand. Beim Übernehmen von Änderungen werden Integrationsereignisse über den Ereignisbus veröffentlicht (im Hintergrund kann RabbitMQ oder Azure Service Bus verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="e7d16-153">In this specific case for eShopOnContainers, it is executing an application method which is querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span> 

<span data-ttu-id="e7d16-154">Sie könnten allerdings auch andere Geschäftshintergrundtasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7d16-154">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="e7d16-155">Standardmäßig wird für das Abbruchtoken ein Zeitlimit von 5 Sekunden festgelegt, obwohl der Wert beim Erstellen von `WebHost` mithilfe der `UseShutdownTimeout`-Erweiterung von `IWebHostBuilder` geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7d16-155">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="e7d16-156">Der Dienst muss also innerhalb von fünf Sekunden beendet werden, da er ansonsten sofort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-156">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="e7d16-157">Im Folgenden Codeausschnitt wird dieses Zeitlimit geändert und auf 10 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e7d16-157">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="e7d16-158">Zusammenfassendes Klassendiagramm</span><span class="sxs-lookup"><span data-stu-id="e7d16-158">Summary class diagram</span></span>

<span data-ttu-id="e7d16-159">In Abbildung 8-26 werden zusammenfassend die Klassen und Schnittstellen dargestellt, die an der Implementierung von IHostedService beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="e7d16-159">The following image 8-26 shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>
 
![](./media/image27.png)

<span data-ttu-id="e7d16-160">**Abbildung 8-26.**</span><span class="sxs-lookup"><span data-stu-id="e7d16-160">**Figure 8-26.**</span></span> <span data-ttu-id="e7d16-161">Klassendiagramm mit mehreren Klassen und Schnittstellen, die mit IHostedService in Verbindung stehen</span><span class="sxs-lookup"><span data-stu-id="e7d16-161">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="e7d16-162">Überlegungen zur Bereitstellung und wesentliche Erkenntnisse</span><span class="sxs-lookup"><span data-stu-id="e7d16-162">Deployment considerations and takeaways</span></span>

<span data-ttu-id="e7d16-163">Sie sollten beachten, dass die konkrete Bereitstellung von ASP.NET Core-`WebHost` oder .NET Core-`Host` Ihre finale Lösung beeinflussen kann.</span><span class="sxs-lookup"><span data-stu-id="e7d16-163">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="e7d16-164">Wenn Sie `WebHost` beispielsweise auf IIS oder in der regulären Azure App Service-Lösung bereitstellen, kann der Host durch den Neustart eines Anwendungspools heruntergefahren werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-164">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="e7d16-165">Wenn Sie den Host jedoch als Container in einem Orchestrator wie Kubernetes oder Service Fabric bereitstellen, können Sie die zugesicherte Anzahl der aktiven Hostinstanzen anpassen.</span><span class="sxs-lookup"><span data-stu-id="e7d16-165">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="e7d16-166">Darüber hinaus ist es empfehlenswert, sich mit anderen cloudbasierten Lösungen wie Azure Functions zu befassen, die speziell für derartige Szenarios entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-166">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> 

<span data-ttu-id="e7d16-167">Auch wenn `WebHost` in einem Anwendungspool bereitgestellt würde, müssten andere Szenarios wie das Leeren oder erneute Auffüllen des speicherinternen Anwendungscaches berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="e7d16-167">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="e7d16-168">Die `IHostedService`-Schnittstelle bietet eine einfache Möglichkeit, Hintergrundtasks in einer ASP.NET Core-Webanwendung (.NET 2.0 Core) oder in einem Prozess oder Host zu starten (ab .NET Core 2.1 mit `IHost`).</span><span class="sxs-lookup"><span data-stu-id="e7d16-168">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="e7d16-169">Der Hauptvorteil besteht darin, dass Sie durch einen ordnungsgemäßen Abbruch Bereinigungscode in Ihren Hintergrundtasks ausführen können, wenn der Host heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="e7d16-169">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="e7d16-170">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e7d16-170">Additional resources</span></span>

-   <span data-ttu-id="e7d16-171">**Building a scheduled task in ASP.NET Core/Standard 2.0 (Erstellen eines geplanten Tasks in ASP.NET Core/Standard 2.0)**</span><span class="sxs-lookup"><span data-stu-id="e7d16-171">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> 

    [*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   <span data-ttu-id="e7d16-172">**Implementing IHostedService in ASP.NET Core 2.0 (Implementieren von IHostedService in ASP.NET Core 2.0)**</span><span class="sxs-lookup"><span data-stu-id="e7d16-172">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> 

    [*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   <span data-ttu-id="e7d16-173">**ASP.NET Core 2.1 Hosting samples (Hostingbeispiele für ASP.NET Core 2.1)**</span><span class="sxs-lookup"><span data-stu-id="e7d16-173">**ASP.NET Core 2.1 Hosting samples**</span></span> 

    [*https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample*](https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample)

>[!div class="step-by-step"]
<span data-ttu-id="e7d16-174">[Zurück](test-aspnet-core-services-web-apps.md)
[Weiter](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="e7d16-174">[Previous](test-aspnet-core-services-web-apps.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
