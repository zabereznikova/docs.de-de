---
title: Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über neue Optionen zum Implementieren von Hintergrundtasks in Microservices in .NET Core mit IHostedService und BackgroundService
ms.date: 01/13/2021
ms.openlocfilehash: 26bc06c4a63cddcd32bf7da705f6258fab8eaafa
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188802"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="4aa1b-103">Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse</span><span class="sxs-lookup"><span data-stu-id="4aa1b-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="4aa1b-104">Hintergrundaufgaben und geplante Aufträge können in jeder beliebigen Anwendung eingesetzt werden, unabhängig davon, ob diese auf einer Microservicearchitektur basiert.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-104">Background tasks and scheduled jobs are something you might need to use in any application, whether or not it follows the microservices architecture pattern.</span></span> <span data-ttu-id="4aa1b-105">Der Unterschied bei Verwendung einer Microservicearchitektur besteht darin, dass Sie die Hintergrundaufgabe in einem separaten Hostingprozess oder -container implementieren können, damit Sie diesen je nach Bedarf hoch- oder herunterskalieren können.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-105">The difference when using a microservices architecture is that you can implement the background task in a separate process/container for hosting so you can scale it down/up based on your need.</span></span>

<span data-ttu-id="4aa1b-106">In .NET werden diese Tasks als *gehostete Dienste* bezeichnet, da sie Dienste oder Logiken darstellen, die in einem Host, einer Anwendung oder einem Microservice gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-106">From a generic point of view, in .NET we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="4aa1b-107">Beachten Sie, dass in diesem Fall der gehostete Dienst einfach einer Klasse mit der Logik des Hintergrundtasks entspricht.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="4aa1b-108">Seit .NET Core 2.0 stellt das Framework die neue Schnittstelle <xref:Microsoft.Extensions.Hosting.IHostedService> bereit, mit der Sie gehostete Dienste einfach implementieren können.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="4aa1b-109">Die Grundidee besteht darin, mehrere Hintergrundtasks (gehostete Dienste) zu registrieren, die neben dem Host oder Webhost im Hintergrund ausgeführt werden (s. Abbildung 6-26).</span><span class="sxs-lookup"><span data-stu-id="4aa1b-109">The basic idea is that you can register multiple background tasks (hosted services) that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![Diagramm mit einem Vergleich von ASP.NET Core IWebHost und .NET Core IHost.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

<span data-ttu-id="4aa1b-111">**Abbildung 6-26**.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-111">**Figure 6-26**.</span></span> <span data-ttu-id="4aa1b-112">Verwenden von IHostedService mit Host und WebHost</span><span class="sxs-lookup"><span data-stu-id="4aa1b-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="4aa1b-113">ASP.NET Core 1.x und 2.x unterstützen `IWebHost` für Hintergrundprozesse in Web-Apps.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-113">ASP.NET Core 1.x and 2.x support `IWebHost` for background processes in web apps.</span></span> <span data-ttu-id="4aa1b-114">.NET Core-Versionen ab 2.1 unterstützen `IHost` für Hintergrundprozesse mit einfachen Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-114">.NET Core 2.1 and later versions support `IHost` for background processes with plain console apps.</span></span> <span data-ttu-id="4aa1b-115">Beachten Sie den Unterschied zwischen `WebHost` und `Host`.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-115">Note the difference made between `WebHost` and `Host`.</span></span>

<span data-ttu-id="4aa1b-116">`WebHost` (eine Basisklasse, die `IWebHost` implementiert) ist in ASP.NET Core 2.0 das Infrastrukturartefakt, mit dem Sie HTTP-Serverfunktionen für Ihren Prozess (z. B. Implementieren einer MVC-Webanwendung oder eines Web-API-Diensts) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-116">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as when you're implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="4aa1b-117">Diese Klasse enthält in ASP.NET Core alle neuen Infrastrukturfunktionen, sodass Sie u. a. die Abhängigkeitsinjektion verwenden und in Anforderungspipelines Middleware einfügen können.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-117">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, and similar.</span></span> <span data-ttu-id="4aa1b-118">Der `WebHost` verwendet genau diese `IHostedServices` für Hintergrundaufgaben.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-118">The `WebHost` uses these very same `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="4aa1b-119">`Host` (Basisklasse, die `IHost` implementiert) wurde in .NET Core 2.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-119">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="4aa1b-120">Mit `Host` können Sie eine ähnliche Infrastruktur wie mit `WebHost` (Dependency Injection, gehostete Dienste usw.) verwenden. Der Unterschied besteht darin, dass Sie einen einfacheren und schlankeren Prozess für den Host verwenden und auf Verknüpfungen mit MVC, einer Web-API oder HTTP-Serverfunktionen verzichten.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-120">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="4aa1b-121">Sie können daher entweder einen spezialisierten Hostprozess mit `IHost` erstellen, um ausschließlich gehostete Dienste (beispielsweise einen Microservice zum Hosten von `IHostedServices`) zu verarbeiten, oder aber einen vorhandenen ASP.NET Core-`WebHost` wie eine ASP.NET Core-Web-API oder eine MVC-Anwendung erweitern.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-121">Therefore, you can choose and either create a specialized host-process with `IHost` to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span>

<span data-ttu-id="4aa1b-122">Je nach Geschäfts- und Skalierbarkeitsanforderungen hat jeder Ansatz seine Vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-122">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="4aa1b-123">Zusammengefasst heißt das: Falls Ihre Hintergrundtasks nichts mit HTTP (`IWebHost`) zu tun haben, sollten Sie `IHost` verwenden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-123">The bottom line is basically that if your background tasks have nothing to do with HTTP (`IWebHost`) you should use `IHost`.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="4aa1b-124">Registrieren von gehosteten Diensten in WebHost oder Host</span><span class="sxs-lookup"><span data-stu-id="4aa1b-124">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="4aa1b-125">Im Folgenden wird die `IHostedService`-Schnittstelle ausführlicher behandelt, da sie für `WebHost` oder `Host` auf ähnliche Weise verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-125">Let's drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span>

<span data-ttu-id="4aa1b-126">SignalR ist ein Beispiel für ein Artefakt, das gehostete Dienste verwendet. Sie können den Dienst aber auch für einfachere Aufgaben verwenden. Hierzu zählt etwa Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4aa1b-126">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

- <span data-ttu-id="4aa1b-127">ein Hintergrundtask, der eine Datenbank abruft und nach Änderungen sucht</span><span class="sxs-lookup"><span data-stu-id="4aa1b-127">A background task polling a database looking for changes.</span></span>
- <span data-ttu-id="4aa1b-128">ein geplanter Task, der einen Cache regelmäßig aktualisiert</span><span class="sxs-lookup"><span data-stu-id="4aa1b-128">A scheduled task updating some cache periodically.</span></span>
- <span data-ttu-id="4aa1b-129">eine Implementierung von QueueBackgroundWorkItem, durch die ein Task in einem Hintergrundthread ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="4aa1b-129">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
- <span data-ttu-id="4aa1b-130">das Verarbeiten von Nachrichten aus einer Nachrichtenwarteschlange im Hintergrund einer Webanwendung, während allgemeine Dienste wie `ILogger` gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-130">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
- <span data-ttu-id="4aa1b-131">ein Hintergrundtask, der mit `Task.Run()` gestartet wird</span><span class="sxs-lookup"><span data-stu-id="4aa1b-131">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="4aa1b-132">Sie können im Grunde jede dieser Aktionen in eine Hintergrundaufgabe auslagern, die `IHostedService` implementiert.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-132">You can basically offload any of those actions to a background task that implements `IHostedService`.</span></span>

<span data-ttu-id="4aa1b-133">Sie können `WebHost`- oder `Host`-Klassen eine oder mehrere `IHostedServices`-Schnittstellen hinzufügen, indem Sie sie über die <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>-Erweiterungsmethode in einer `WebHost`-Klasse von ASP.NET Core (oder in einer `Host`-Klasse in .NET Core 2.1 und höher) registrieren.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-133">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> extension method in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="4aa1b-134">Dabei müssen Sie die gehosteten Dienste in der bekannten `ConfigureServices()`-Methode der `Startup`-Klasse registrieren, was im folgenden Codeausschnitt einer typischen ASP.NET-WebHost-Klasse demonstriert wird.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-134">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddHostedService<GracePeriodManagerService>();
    services.AddHostedService<MyHostedServiceB>();
    services.AddHostedService<MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="4aa1b-135">Der Code für den gehosteten Dienst `GracePeriodManagerService` entspricht dem Code aus dem Microservice für Bestellungen in eShopOnContainers. Bei den anderen beiden Diensten handelt es sich hingegen nur um zwei zusätzliche Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-135">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="4aa1b-136">Die Ausführung des `IHostedService`-Hintergrundtasks wird mit der Lebensdauer der Anwendung (also des Hosts oder des Microservices) koordiniert.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-136">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="4aa1b-137">Die Tasks werden registriert, wenn die Anwendung gestartet und eine ordnungsgemäße Aktion ausgeführt oder wenn die Anwendung beendet wird und dabei Ressourcen bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-137">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="4aa1b-138">Ohne die Nutzung von `IHostedService` ließe sich ein Hintergrundthread erstellen, in dem ein beliebiger Task ausgeführt werden könnte.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-138">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="4aa1b-139">Zum Beendigungszeitpunkt der Anwendung würde der Thread dann einfach beendet werden, und ordnungsgemäße Aktionen zur Bereinigung von Ressourcen könnten nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-139">The difference is precisely at the app's shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="4aa1b-140">Die IHostedService-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4aa1b-140">The IHostedService interface</span></span>

<span data-ttu-id="4aa1b-141">Beim Registrieren einer `IHostedService`-Schnittstelle ruft .NET die Methoden `StartAsync()` und `StopAsync()` des Typs `IHostedService` beim Anwendungsstart und -stopp auf.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-141">When you register an `IHostedService`, .NET will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="4aa1b-142">Weitere Informationen finden Sie unter [Schnittstelle „IHostedService“](/aspnet/core/fundamentals/host/hosted-services?tabs=visual-studio&view=aspnetcore-3.1#ihostedservice-interface).</span><span class="sxs-lookup"><span data-stu-id="4aa1b-142">For more details, refer [IHostedService interface](/aspnet/core/fundamentals/host/hosted-services?tabs=visual-studio&view=aspnetcore-3.1#ihostedservice-interface)</span></span>

<span data-ttu-id="4aa1b-143">Sie können mehrere Implementierungen von IHostedService erstellen und wie zuvor gezeigt in der `ConfigureService()`-Methode des Dependency Injection-Containers registrieren.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-143">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="4aa1b-144">Alle gehosteten Dienste werden zusammen mit der Anwendung und dem Microservice gestartet und beendet.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-144">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="4aa1b-145">Als Entwickler sind Sie dafür verantwortlich, die Beendigungsaktion Ihrer Dienste zu verarbeiten, wenn die `StopAsync()`-Methode vom Host ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-145">As a developer, you are responsible for handling the stopping action of your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="4aa1b-146">Implementieren von IHostedService mit einer eigenen Klasse für gehostete Dienste, die von der Basisklasse BackgroundService abgeleitet wird</span><span class="sxs-lookup"><span data-stu-id="4aa1b-146">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="4aa1b-147">Sie haben die Möglichkeit, eine eigene Klasse für gehostete Dienste neu zu erstellen und `IHostedService` zu implementieren, was im Fall von .NET Core 2.0 und höher sogar unumgänglich ist.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-147">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0 and later.</span></span>

<span data-ttu-id="4aa1b-148">Da allerdings die meisten Hintergrundtasks ähnliche Anforderungen an die Verwaltung von Abbruchtoken und an weitere typische Vorgänge stellen, gibt es hierfür die praktische abstrakte Basisklasse `BackgroundService` (verfügbar ab NET Core 2.1), von der eigene Klassen abgeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-148">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="4aa1b-149">Diese Klasse fasst die wesentlichen Aufgaben zusammen, die zum Einrichten der Hintergrundtasks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-149">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="4aa1b-150">Im folgenden Codeausschnitt ist die in .NET implementierte abstrakte Basisklasse BackgroundService zu sehen.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-150">The next code is the abstract BackgroundService base class as implemented in .NET.</span></span>

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

<span data-ttu-id="4aa1b-151">Wenn Sie eine Klasse aus der oben gezeigten abstrakten Basisklasse ableiten, müssen Sie dank der vererbten Implementierung nur die `ExecuteAsync()`-Methode in Ihrer eigenen Klasse für gehostete Dienste implementieren. Dies wird im folgenden vereinfachten Codeausschnitt aus eShopOnContainers demonstriert, in dem eine Datenbank abgerufen und Integrationsereignisse bei Bedarf im Ereignisbus veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-151">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

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
        // Constructor's parameters validations...
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
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

<span data-ttu-id="4aa1b-152">Im Fall von eShopOnContainers wird eine Anwendungsmethode ausgeführt, durch die eine Datenbanktabelle abgefragt wird. Diese sucht nach Bestellungen mit einem bestimmten Zustand. Beim Übernehmen von Änderungen werden Integrationsereignisse über den Ereignisbus veröffentlicht (im Hintergrund kann RabbitMQ oder Azure Service Bus verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="4aa1b-152">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="4aa1b-153">Sie könnten allerdings auch andere Geschäftshintergrundtasks ausführen.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-153">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="4aa1b-154">Standardmäßig wird für das Abbruchtoken ein Zeitlimit von 5 Sekunden festgelegt, obwohl der Wert beim Erstellen von `WebHost` mithilfe der Erweiterung `UseShutdownTimeout` von `IWebHostBuilder` geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-154">By default, the cancellation token is set with a 5 seconds timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="4aa1b-155">Der Dienst muss also innerhalb von fünf Sekunden beendet werden, da er ansonsten sofort beendet wird.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-155">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="4aa1b-156">Im Folgenden Codeausschnitt wird dieses Zeitlimit geändert und auf 10 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-156">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="4aa1b-157">Zusammenfassendes Klassendiagramm</span><span class="sxs-lookup"><span data-stu-id="4aa1b-157">Summary class diagram</span></span>

<span data-ttu-id="4aa1b-158">In der folgenden Abbildung werden zusammenfassend die Klassen und Schnittstellen dargestellt, die an der Implementierung von IHostedService beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-158">The following image shows a visual summary of the classes and interfaces involved when implementing IHostedServices.</span></span>

![Diagramm, das zeigt, dass IWebHost und IHost zahlreiche Dienste hosten können.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

<span data-ttu-id="4aa1b-160">**Abbildung 6-27**.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-160">**Figure 6-27**.</span></span> <span data-ttu-id="4aa1b-161">Klassendiagramm mit mehreren Klassen und Schnittstellen, die mit IHostedService in Verbindung stehen</span><span class="sxs-lookup"><span data-stu-id="4aa1b-161">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

<span data-ttu-id="4aa1b-162">Klassendiagramm: IWebHost und IHost können viele Dienste hosten, die von BackgroundService erben, der IHostedService implementiert.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-162">Class diagram: IWebHost and IHost can host many services, which inherit from BackgroundService, which implements IHostedService.</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="4aa1b-163">Überlegungen zur Bereitstellung und wesentliche Erkenntnisse</span><span class="sxs-lookup"><span data-stu-id="4aa1b-163">Deployment considerations and takeaways</span></span>

<span data-ttu-id="4aa1b-164">Sie sollten beachten, dass die konkrete Bereitstellung der ASP.NET Core-Klasse `WebHost` oder der .NET Core-Klasse `Host` sich auf Ihre finale Lösung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-164">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET `Host` might impact the final solution.</span></span> <span data-ttu-id="4aa1b-165">Wenn Sie `WebHost` beispielsweise auf IIS oder in der regulären Azure App Service-Lösung bereitstellen, kann der Host durch den Neustart eines Anwendungspools heruntergefahren werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-165">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="4aa1b-166">Wenn Sie den Host jedoch als Container in einem Orchestrator wie Kubernetes bereitstellen, können Sie die zugesicherte Anzahl der aktiven Hostinstanzen anpassen.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-166">But if you are deploying your host as a container into an orchestrator like Kubernetes, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="4aa1b-167">Darüber hinaus ist es empfehlenswert, sich mit anderen cloudbasierten Lösungen wie Azure Functions zu befassen, die speziell für derartige Szenarios entworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-167">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="4aa1b-168">Wenn Sie möchten, dass der Dienst permanent ausgeführt und auf einer Windows Server-Instanz bereitgestellt wird, verwenden Sie einen Windows-Dienst.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-168">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="4aa1b-169">Auch wenn eine `WebHost`-Instanz in einem Anwendungspool bereitgestellt würde, müssten andere Szenarios wie das Leeren oder nochmalige Auffüllen des speicherinternen Anwendungscaches berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-169">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application's in-memory cache that would be still applicable.</span></span>

<span data-ttu-id="4aa1b-170">Die `IHostedService`-Schnittstelle bietet eine einfache Möglichkeit, Hintergrundtasks in einer ASP.NET Core-Webanwendung ( ab .NET 2.0 Core) oder in einem Prozess oder Host zu starten (ab .NET Core 2.1 mit `IHost`).</span><span class="sxs-lookup"><span data-stu-id="4aa1b-170">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0 and later versions) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="4aa1b-171">Ihr Hauptvorteil besteht darin, dass Sie bei einem ordnungsgemäßen Abbruch den Code Ihrer Hintergrundaufgaben bereinigen können, wenn der Host heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="4aa1b-171">Its main benefit is the opportunity you get with the graceful cancellation to clean-up the code of your background tasks when the host itself is shutting down.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4aa1b-172">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4aa1b-172">Additional resources</span></span>

- <span data-ttu-id="4aa1b-173">**Erstellen eines geplanten Tasks in ASP.NET Core/Standard 2.0** </span><span class="sxs-lookup"><span data-stu-id="4aa1b-173">**Building a scheduled task in ASP.NET Core/Standard 2.0** </span></span>\
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- <span data-ttu-id="4aa1b-174">**Implementieren von IHostedService in ASP.NET Core 2.0** </span><span class="sxs-lookup"><span data-stu-id="4aa1b-174">**Implementing IHostedService in ASP.NET Core 2.0** </span></span>\
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- <span data-ttu-id="4aa1b-175">**GenericHost-Beispiel mithilfe von ASP.NET Core 2.1** </span><span class="sxs-lookup"><span data-stu-id="4aa1b-175">**GenericHost Sample using ASP.NET Core 2.1** </span></span>\
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

> [!div class="step-by-step"]
> <span data-ttu-id="4aa1b-176">[Zurück](test-aspnet-core-services-web-apps.md)
> [Weiter](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="4aa1b-176">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>
