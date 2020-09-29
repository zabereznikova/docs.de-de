---
title: Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über neue Optionen zum Implementieren von Hintergrundtasks in Microservices in .NET Core mit IHostedService und BackgroundService
ms.date: 08/14/2020
ms.openlocfilehash: 279f9e0093deafab51e63d72dce233c8e9466a55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173353"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a>Implementieren von Hintergrundtasks in Microservices mit IHostedService und der BackgroundService-Klasse

Hintergrundaufgaben und geplante Aufträge können in jeder beliebigen Anwendung eingesetzt werden, unabhängig davon, ob diese auf einer Microservicearchitektur basiert. Der Unterschied bei Verwendung einer Microservicearchitektur besteht darin, dass Sie die Hintergrundaufgabe in einem separaten Hostingprozess oder -container implementieren können, damit Sie diesen je nach Bedarf hoch- oder herunterskalieren können.

In .NET Core werden diese Tasks als *gehostete Dienste* bezeichnet, da sie Dienste oder Logiken darstellen, die in einem Host, einer Anwendung oder einem Microservice gehostet werden. Beachten Sie, dass in diesem Fall der gehostete Dienst einfach einer Klasse mit der Logik des Hintergrundtasks entspricht.

Seit .NET Core 2.0 stellt das Framework die neue Schnittstelle <xref:Microsoft.Extensions.Hosting.IHostedService> bereit, mit der Sie gehostete Dienste einfach implementieren können. Die Grundidee besteht darin, mehrere Hintergrundtasks (gehostete Dienste) zu registrieren, die neben dem Host oder Webhost im Hintergrund ausgeführt werden (s. Abbildung 6-26).

![Diagramm mit einem Vergleich von ASP.NET Core IWebHost und .NET Core IHost.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

**Abbildung 6-26**. Verwenden von IHostedService mit Host und WebHost

ASP.NET Core 1.x und 2.x unterstützen `IWebHost` für Hintergrundprozesse in Web-Apps. .NET Core-Versionen ab 2.1 unterstützen `IHost` für Hintergrundprozesse mit einfachen Konsolenanwendungen. Beachten Sie den Unterschied zwischen `WebHost` und `Host`.

`WebHost` (eine Basisklasse, die `IWebHost` implementiert) ist in ASP.NET Core 2.0 das Infrastrukturartefakt, mit dem Sie HTTP-Serverfunktionen für Ihren Prozess (z. B. Implementieren einer MVC-Webanwendung oder eines Web-API-Diensts) bereitstellen. Diese Klasse enthält in ASP.NET Core alle neuen Infrastrukturfunktionen, sodass Sie u. a. die Abhängigkeitsinjektion verwenden und in Anforderungspipelines Middleware einfügen können. Der `WebHost` verwendet genau diese `IHostedServices` für Hintergrundaufgaben.

`Host` (Basisklasse, die `IHost` implementiert) wurde in .NET Core 2.1 eingeführt. Mit `Host` können Sie eine ähnliche Infrastruktur wie mit `WebHost` (Dependency Injection, gehostete Dienste usw.) verwenden. Der Unterschied besteht darin, dass Sie einen einfacheren und schlankeren Prozess für den Host verwenden und auf Verknüpfungen mit MVC, einer Web-API oder HTTP-Serverfunktionen verzichten.

Sie können daher entweder einen spezialisierten Hostprozess mit `IHost` erstellen, um ausschließlich gehostete Dienste (beispielsweise einen Microservice zum Hosten von `IHostedServices`) zu verarbeiten, oder aber einen vorhandenen ASP.NET Core-`WebHost` wie eine ASP.NET Core-Web-API oder eine MVC-Anwendung erweitern.

Je nach Geschäfts- und Skalierbarkeitsanforderungen hat jeder Ansatz seine Vor- und Nachteile. Zusammengefasst heißt das: Falls Ihre Hintergrundtasks nichts mit HTTP (`IWebHost`) zu tun haben, sollten Sie `IHost` verwenden.

## <a name="registering-hosted-services-in-your-webhost-or-host"></a>Registrieren von gehosteten Diensten in WebHost oder Host

Im Folgenden wird die `IHostedService`-Schnittstelle ausführlicher behandelt, da sie für `WebHost` oder `Host` auf ähnliche Weise verwendet wird.

SignalR ist ein Beispiel für ein Artefakt, das gehostete Dienste verwendet. Sie können den Dienst aber auch für einfachere Aufgaben verwenden. Hierzu zählt etwa Folgendes:

- ein Hintergrundtask, der eine Datenbank abruft und nach Änderungen sucht
- ein geplanter Task, der einen Cache regelmäßig aktualisiert
- eine Implementierung von QueueBackgroundWorkItem, durch die ein Task in einem Hintergrundthread ausgeführt werden kann
- das Verarbeiten von Nachrichten aus einer Nachrichtenwarteschlange im Hintergrund einer Webanwendung, während allgemeine Dienste wie `ILogger` gemeinsam genutzt werden.
- ein Hintergrundtask, der mit `Task.Run()` gestartet wird

Sie können im Grunde jede dieser Aktionen in eine Hintergrundaufgabe auslagern, die `IHostedService` implementiert.

Sie können einem `WebHost` oder `Host` ein oder mehrere `IHostedServices` hinzufügen, indem Sie sie über die <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> -Erweiterungsmethode in einem ASP.NET Core-`WebHost` (oder in einem `Host` in .NET Core 2.1 oder höher) registrieren. Dabei müssen Sie die gehosteten Dienste in der bekannten `ConfigureServices()`-Methode der `Startup`-Klasse registrieren, was im folgenden Codeausschnitt einer typischen ASP.NET-WebHost-Klasse demonstriert wird.

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

Der Code für den gehosteten Dienst `GracePeriodManagerService` entspricht dem Code aus dem Microservice für Bestellungen in eShopOnContainers. Bei den anderen beiden Diensten handelt es sich hingegen nur um zwei zusätzliche Beispiele.

Die Ausführung des `IHostedService`-Hintergrundtasks wird mit der Lebensdauer der Anwendung (also des Hosts oder des Microservices) koordiniert. Die Tasks werden registriert, wenn die Anwendung gestartet und eine ordnungsgemäße Aktion ausgeführt oder wenn die Anwendung beendet wird und dabei Ressourcen bereinigt werden.

Ohne die Nutzung von `IHostedService` ließe sich ein Hintergrundthread erstellen, in dem ein beliebiger Task ausgeführt werden könnte. Zum Beendigungszeitpunkt der Anwendung würde der Thread dann einfach beendet werden, und ordnungsgemäße Aktionen zur Bereinigung von Ressourcen könnten nicht ausgeführt werden.

## <a name="the-ihostedservice-interface"></a>Die IHostedService-Schnittstelle

Beim Registrieren von `IHostedService` ruft .NET Core die Methoden `StartAsync()` und `StopAsync()` des Typs `IHostedService` während des Anwendungsstarts und -stopps auf. Weitere Informationen finden Sie unter [Schnittstelle „IHostedService“](/aspnet/core/fundamentals/host/hosted-services?tabs=visual-studio&view=aspnetcore-3.1#ihostedservice-interface).

Sie können mehrere Implementierungen von IHostedService erstellen und wie zuvor gezeigt in der `ConfigureService()`-Methode des Dependency Injection-Containers registrieren. Alle gehosteten Dienste werden zusammen mit der Anwendung und dem Microservice gestartet und beendet.

Als Entwickler sind Sie dafür verantwortlich, die Beendigungsaktion Ihrer Dienste zu verarbeiten, wenn die `StopAsync()`-Methode vom Host ausgelöst wird.

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a>Implementieren von IHostedService mit einer eigenen Klasse für gehostete Dienste, die von der Basisklasse BackgroundService abgeleitet wird

Sie haben die Möglichkeit, eine eigene Klasse für gehostete Dienste neu zu erstellen und `IHostedService` zu implementieren, was im Fall von .NET Core 2.0 sogar unumgänglich ist.

Da allerdings die meisten Hintergrundtasks ähnliche Anforderungen an die Verwaltung von Abbruchtoken und an weitere typische Vorgänge stellen, gibt es hierfür die praktische abstrakte Basisklasse `BackgroundService` (verfügbar ab NET Core 2.1), von der eigene Klassen abgeleitet werden können.

Diese Klasse fasst die wesentlichen Aufgaben zusammen, die zum Einrichten der Hintergrundtasks erforderlich sind.

Im folgenden Codeausschnitt ist die in .NET Core implementierte abstrakte Basisklasse BackgroundService zu sehen.

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

Wenn Sie eine Klasse aus der oben gezeigten abstrakten Basisklasse ableiten, müssen Sie dank der vererbten Implementierung nur die `ExecuteAsync()`-Methode in Ihrer eigenen Klasse für gehostete Dienste implementieren. Dies wird im folgenden vereinfachten Codeausschnitt aus eShopOnContainers demonstriert, in dem eine Datenbank abgerufen und Integrationsereignisse bei Bedarf im Ereignisbus veröffentlicht werden.

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

Im Fall von eShopOnContainers wird eine Anwendungsmethode ausgeführt, durch die eine Datenbanktabelle abgefragt wird. Diese sucht nach Bestellungen mit einem bestimmten Zustand. Beim Übernehmen von Änderungen werden Integrationsereignisse über den Ereignisbus veröffentlicht (im Hintergrund kann RabbitMQ oder Azure Service Bus verwendet werden).

Sie könnten allerdings auch andere Geschäftshintergrundtasks ausführen.

Standardmäßig wird für das Abbruchtoken ein Zeitlimit von 5 Sekunden festgelegt, obwohl der Wert beim Erstellen von `WebHost` mithilfe der Erweiterung `UseShutdownTimeout` von `IWebHostBuilder` geändert werden kann. Der Dienst muss also innerhalb von fünf Sekunden beendet werden, da er ansonsten sofort beendet wird.

Im Folgenden Codeausschnitt wird dieses Zeitlimit geändert und auf 10 Sekunden festgelegt.

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a>Zusammenfassendes Klassendiagramm

In der folgenden Abbildung werden zusammenfassend die Klassen und Schnittstellen dargestellt, die an der Implementierung von IHostedService beteiligt sind.

![Diagramm, das zeigt, dass IWebHost und IHost zahlreiche Dienste hosten können.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

**Abbildung 6-27**. Klassendiagramm mit mehreren Klassen und Schnittstellen, die mit IHostedService in Verbindung stehen

Klassendiagramm: IWebHost und IHost können viele Dienste hosten, die von BackgroundService erben, der IHostedService implementiert.

### <a name="deployment-considerations-and-takeaways"></a>Überlegungen zur Bereitstellung und wesentliche Erkenntnisse

Sie sollten beachten, dass die konkrete Bereitstellung von ASP.NET Core-`WebHost` oder .NET Core-`Host` Ihre finale Lösung beeinflussen kann. Wenn Sie `WebHost` beispielsweise auf IIS oder in der regulären Azure App Service-Lösung bereitstellen, kann der Host durch den Neustart eines Anwendungspools heruntergefahren werden. Wenn Sie den Host jedoch als Container in einem Orchestrator wie Kubernetes bereitstellen, können Sie die zugesicherte Anzahl der aktiven Hostinstanzen anpassen. Darüber hinaus ist es empfehlenswert, sich mit anderen cloudbasierten Lösungen wie Azure Functions zu befassen, die speziell für derartige Szenarios entworfen wurden. Wenn Sie möchten, dass der Dienst permanent ausgeführt und auf einer Windows Server-Instanz bereitgestellt wird, verwenden Sie einen Windows-Dienst.

Auch wenn eine `WebHost`-Instanz in einem Anwendungspool bereitgestellt würde, müssten andere Szenarios wie das Leeren oder nochmalige Auffüllen des speicherinternen Anwendungscaches berücksichtigt werden.

Die `IHostedService`-Schnittstelle bietet eine einfache Möglichkeit, Hintergrundtasks in einer ASP.NET Core-Webanwendung ( ab .NET 2.0 Core) oder in einem Prozess oder Host zu starten (ab .NET Core 2.1 mit `IHost`). Ihr Hauptvorteil besteht darin, dass Sie bei einem ordnungsgemäßen Abbruch den Code Ihrer Hintergrundaufgaben bereinigen können, wenn der Host heruntergefahren wird.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Erstellen eines geplanten Tasks in ASP.NET Core/Standard 2.0** \
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- **Implementieren von IHostedService in ASP.NET Core 2.0** \
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- **GenericHost-Beispiel mithilfe von ASP.NET Core 2.1** \
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

> [!div class="step-by-step"]
> [Zurück](test-aspnet-core-services-web-apps.md)
> [Weiter](implement-api-gateways-with-ocelot.md)
