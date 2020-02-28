---
title: Systemüberwachung
description: Entdecken Sie eine Möglichkeit zum Implementieren der Systemüberwachung.
ms.date: 01/30/2020
ms.openlocfilehash: a91e51af66049f9774365cd56b90ab792a4dd4fc
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502682"
---
# <a name="health-monitoring"></a><span data-ttu-id="31d62-103">Systemüberwachung</span><span class="sxs-lookup"><span data-stu-id="31d62-103">Health monitoring</span></span>

<span data-ttu-id="31d62-104">Über die Systemüberwachung können Sie nahezu in Echtzeit Informationen zum Zustand Ihrer Container und Microservices erhalten.</span><span class="sxs-lookup"><span data-stu-id="31d62-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="31d62-105">Die Systemüberwachung ist für verschieden Aspekte von Betriebsmicroservices wichtig und ist von besonderer Bedeutung, wenn Orchestratoren wie im Folgenden beschrieben ein Anwendungsupgrade in Phasen ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d62-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="31d62-106">Auf einem Microservice basierende Anwendungen verwenden häufig Takte oder Integritätsüberprüfungen, damit ihre Systemmonitore, Zeitpläne und Orchestratoren die verschiedenen Dienste überwachen können.</span><span class="sxs-lookup"><span data-stu-id="31d62-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="31d62-107">Wenn Dienste auf Verlangen oder nach Zeitplan kein Signal senden können, um deutlich zu machen, dass sie noch funktionieren, können für Ihre Anwendung Risiken entstehen, wenn Sie Updates bereitstellen. Zudem kann es auch vorkommen, dass Fehler zu spät erkannt werden, wodurch kaskadierende Fehler nicht vermieden werden können, die zu größeren Ausfällen führen können.</span><span class="sxs-lookup"><span data-stu-id="31d62-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might just detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="31d62-108">Dienste in ihrer allgemeinen Form senden Zustandsberichte. Diese Informationen werden dann aggregiert, sodass eine allgemeine Übersicht zum Integritätsstatus Ihrer Anwendung erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31d62-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="31d62-109">Wenn Sie einen Orchestrator verwenden, können Sie Integritätsinformationen zum Cluster Ihrer Orchestratoren hinzufügen, damit der Cluster entsprechend agieren kann.</span><span class="sxs-lookup"><span data-stu-id="31d62-109">If you're using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="31d62-110">Wenn Sie in Integritätsberichte von hoher Qualität investieren, die an Ihre Anwendung angepasst werden, können Sie Fehler der ausgeführte Anwendung viel einfacher ermitteln und beheben.</span><span class="sxs-lookup"><span data-stu-id="31d62-110">If you invest in high-quality health reporting that's customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implement-health-checks-in-aspnet-core-services"></a><span data-ttu-id="31d62-111">Implementieren von Integritätsüberprüfungen in ASP.NET Core-Diensten</span><span class="sxs-lookup"><span data-stu-id="31d62-111">Implement health checks in ASP.NET Core services</span></span>

<span data-ttu-id="31d62-112">Beim Entwickeln eines ASP.NET Core-Microservice oder einer -Webanwendung können Sie das integrierte Feature für Integritätsprüfungen verwenden, das mit ASP.NET Core 3.1 veröffentlicht wurde ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)).</span><span class="sxs-lookup"><span data-stu-id="31d62-112">When developing an ASP.NET Core microservice or web application, you can use the built-in health checks feature that was released in ASP .NET Core 3.1 ([Microsoft.Extensions.Diagnostics.HealthChecks](https://www.nuget.org/packages/Microsoft.Extensions.Diagnostics.HealthChecks)).</span></span> <span data-ttu-id="31d62-113">Wie viele andere ASP.NET Core-Features enthalten die Integritätsprüfungen mehrere Dienste und eine Middleware.</span><span class="sxs-lookup"><span data-stu-id="31d62-113">Like many ASP.NET Core features, health checks come with a set of services and a middleware.</span></span>

<span data-ttu-id="31d62-114">Dienste und Middleware zur Überprüfung der Integrität sind einfach zu verwenden und stellen Funktionen bereit, mit denen Sie überprüfen können, ob eine beliebige externe Ressource, die für Ihre Anwendung (z. B. eine SQL Server-Datenbank oder eine Remote-API) erforderlich ist, ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="31d62-114">Health check services and middleware are easy to use and provide capabilities that let you validate if any external resource needed for your application (like a SQL Server database or a remote API) is working properly.</span></span> <span data-ttu-id="31d62-115">Wenn Sie dieses Feature verwenden, können Sie außerdem die Voraussetzungen für die Integrität der Ressource festlegen. Dies wird nachfolgend näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="31d62-115">When you use this feature, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="31d62-116">Damit Sie dieses Feature effektiv nutzen können, müssen Sie zunächst Dienste in Ihren Microservices konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31d62-116">To use this feature effectively, you need to first configure services in your microservices.</span></span> <span data-ttu-id="31d62-117">Außerdem ist eine Front-End-Anwendung erforderlich, die Integritätsberichte abfragt.</span><span class="sxs-lookup"><span data-stu-id="31d62-117">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="31d62-118">Bei dieser Front-End-Anwendung kann es sich z.B. um eine benutzerdefinierte Anwendung zur Berichterstattung oder einen Orchestrator an sich handeln, der im Hinblick auf den Integritätszustand angemessen reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="31d62-118">That front-end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="31d62-119">Verwenden des HealthChecks-Features in Ihren Back-End-ASP.NET-Microservices</span><span class="sxs-lookup"><span data-stu-id="31d62-119">Use the HealthChecks feature in your back-end ASP.NET microservices</span></span>

<span data-ttu-id="31d62-120">In diesem Abschnitt erfahren Sie, wie das HealthChecks-Feature (entsprechend der Implementierung in [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks)) in einer Web-API-Beispielanwendung für ASP.NET Core 3.1 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-120">In this section, you'll learn how the HealthChecks feature, as implemented in [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks), is used in a sample ASP.NET Core 3.1 Web API application.</span></span> <span data-ttu-id="31d62-121">Die Implementierung dieses Features in großen Microservices wie eShopOnContainers wird in einem späteren Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="31d62-121">Implementation of this feature in a large-scale microservices like the eShopOnContainers is explained in the later section.</span></span> <span data-ttu-id="31d62-122">Damit Sie beginnen können, müssen Sie definieren, was die Integritätsstatus für die einzelnen Microservices ausmacht.</span><span class="sxs-lookup"><span data-stu-id="31d62-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="31d62-123">In der Beispielanwendung funktionieren die Microservices einwandfrei, wenn über HTTP auf die Microservice-API zugegriffen werden kann und die jeweilige SQL Server-Datenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="31d62-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and its related SQL Server database is also available.</span></span>

<span data-ttu-id="31d62-124">In .NET Core 3.1 mit den integrierten APIs können Sie wie folgt die Dienste konfigurieren und eine Integritätsprüfung für den Microservice sowie die abhängige SQL Server-Datenbank hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="31d62-124">In .NET Core 3.1, with the built-in APIs, you can configure the services, add a Health Check for the microservice and its dependent SQL Server database in this way:</span></span>

```csharp
// Startup.cs from .NET Core 3.1 Web API sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
        // Add a health check for a SQL Server database
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "OrderingDB-check",
            tags: new string[] { "orderingdb" });
}
```

<span data-ttu-id="31d62-125">Im obigen Code konfiguriert die `services.AddHealthChecks()`-Methode eine einfache HTTP-Überprüfung, die den Statuscode **200** mit der Meldung „Fehlerfrei“ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="31d62-125">In the previous code, the `services.AddHealthChecks()` method configures a basic HTTP check that returns a status code **200** with “Healthy”.</span></span>  <span data-ttu-id="31d62-126">Außerdem konfiguriert die `AddCheck()`-Erweiterungsmethode eine benutzerdefinierte `SqlConnectionHealthCheck`-Klasse, mit der die Integrität der zugehörigen SQL-Datenbank-Instanz geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-126">Further, the `AddCheck()` extension method configures a custom `SqlConnectionHealthCheck` that checks the related SQL Database’s health.</span></span>

<span data-ttu-id="31d62-127">Die `AddCheck()`-Methode fügt eine neue Integritätsprüfung mit einem festgelegten Namen und der Implementierung vom Typ `IHealthCheck` hinzu.</span><span class="sxs-lookup"><span data-stu-id="31d62-127">The `AddCheck()` method adds a new health check with a specified name and the implementation of type `IHealthCheck`.</span></span> <span data-ttu-id="31d62-128">Mit der Methode „AddCheck“ können Sie mehrere Integritätsprüfungen hinzufügen, sodass ein Microservice erst einen „fehlerfreien“ Status meldet, wenn alle Prüfungen den Status „Fehlerfrei“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="31d62-128">You can add multiple Health Checks using AddCheck method, so a microservice won't provide a “healthy” status until all its checks are healthy.</span></span>

<span data-ttu-id="31d62-129">`SqlConnectionHealthCheck` ist eine benutzerdefinierte Klasse, die `IHealthCheck` implementiert, wodurch eine Verbindungszeichenfolge als Konstruktorparameter interpretiert und eine einfache Abfrage durchgeführt wird, um zu überprüfen, ob die Verbindung mit der SQL-Datenbank-Instanz erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="31d62-129">`SqlConnectionHealthCheck` is a custom class that implements `IHealthCheck`, which takes a connection string as a constructor parameter and executes a simple query to check if the connection to the SQL database is successful.</span></span> <span data-ttu-id="31d62-130">Sie gibt `HealthCheckResult.Healthy()` zurück, wenn die Abfrage erfolgreich ausgeführt wurde, und Sie gibt `FailureStatus` mit der tatsächlichen Ausnahme zurück, wenn sie fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="31d62-130">It returns `HealthCheckResult.Healthy()` if the query was executed successfully and a `FailureStatus` with the actual exception when it fails.</span></span>

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

<span data-ttu-id="31d62-131">Beachten Sie, dass `Select 1` die Abfrage ist, die im obigen Code zur Überprüfung der Integrität der Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-131">Note that in the previous code, `Select 1` is the query used to check the Health of the database.</span></span> <span data-ttu-id="31d62-132">Orchestratoren wie Kubernetes führen regelmäßig zur Überwachung der Verfügbarkeit Ihrer Microservices Integritätsüberprüfungen durch, indem sie Anforderungen senden, um die Microservices zu testen.</span><span class="sxs-lookup"><span data-stu-id="31d62-132">To monitor the availability of your microservices, orchestrators like Kubernetes periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="31d62-133">Es ist wichtig, dass Ihre Datenbankabfragen effizient sind, damit diese Vorgänge schnell durchgeführt werden können und zu keiner erhöhten Ressourcennutzung führen.</span><span class="sxs-lookup"><span data-stu-id="31d62-133">It's important to keep your database queries efficient so that these operations are quick and don’t result in a higher utilization of resources.</span></span>

<span data-ttu-id="31d62-134">Fügen Sie abschließend eine Middleware hinzu, die auf den URL-Pfad `/hc` antwortet:</span><span class="sxs-lookup"><span data-stu-id="31d62-134">Finally, add a middleware that responds to the url path `/hc`:</span></span>

```csharp
// Startup.cs from .NET Core 3.1 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
        endpoints.MapHealthChecks("/hc", new HealthCheckOptions()
        {
            Predicate = _ => true,
            ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
        });
        //...
    });
    //…
}
```

<span data-ttu-id="31d62-135">Wenn der Endpunkt `<yourmicroservice>/hc` aufgerufen wird, werden alle Integritätsüberprüfungen ausgeführt, die in der Startklasse in der `AddHealthChecks()`-Methode konfiguriert sind, und das Ergebnis wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31d62-135">When the endpoint `<yourmicroservice>/hc` is invoked, it runs all the health checks that are configured in the `AddHealthChecks()` method in the Startup class and shows the result.</span></span>

### <a name="healthchecks-implementation-in-eshoponcontainers"></a><span data-ttu-id="31d62-136">Implementieren des HealthChecks-Features in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="31d62-136">HealthChecks implementation in eShopOnContainers</span></span>

<span data-ttu-id="31d62-137">Microservices in eShopOnContainers hängen bei der Ausführung ihrer Aufgaben von mehreren Diensten ab.</span><span class="sxs-lookup"><span data-stu-id="31d62-137">Microservices in eShopOnContainers rely on multiple services to perform its task.</span></span> <span data-ttu-id="31d62-138">Der `Catalog.API`-Microservice von eShopOnContainers hängt beispielsweise von mehreren Diensten wie Azure Blob Storage, SQL Server und RabbitMQ ab.</span><span class="sxs-lookup"><span data-stu-id="31d62-138">For example, the `Catalog.API` microservice from eShopOnContainers depends on many services, such as Azure Blob Storage, SQL Server, and RabbitMQ.</span></span> <span data-ttu-id="31d62-139">Daher wurden ihm mit der `AddCheck()`-Methode mehrere Integritätsprüfungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="31d62-139">Therefore, it has several health checks added using the `AddCheck()` method.</span></span> <span data-ttu-id="31d62-140">Für jeden abhängigen Dienst definiert eine `IHealthCheck`-Implementierung, dass der zugehörige Integritätsstatus hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="31d62-140">For every dependent service, a custom `IHealthCheck` implementation that defines its respective health status needs to be added.</span></span>

<span data-ttu-id="31d62-141">Beim Open-Source-Projekt [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) wird dieses Problem mit benutzerdefinierten Implementierungen von Integritätsprüfungen für jeden dieser auf .NET Core 3.1 basierenden Unternehmensdiensten gelöst.</span><span class="sxs-lookup"><span data-stu-id="31d62-141">The open-source project [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) solves this problem by providing custom health check implementations for each of these enterprise services that are built on top of .NET Core 3.1.</span></span> <span data-ttu-id="31d62-142">Jede Integritätsprüfung steht als individuelles NuGet-Paket zur Verfügung, das dem Projekt mühelos hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31d62-142">Each health check is available as an individual NuGet package that can be easily added to the project.</span></span> <span data-ttu-id="31d62-143">In eShopOnContainers werden sie in allen enthaltenen Microservices verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d62-143">eShopOnContainers uses them extensively in all its microservices.</span></span>

<span data-ttu-id="31d62-144">Zum `Catalog.API`-Microservice wurden beispielsweise folgende NuGet-Pakete hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="31d62-144">For instance, in the `Catalog.API` microservice, the following NuGet packages were added:</span></span>

![Screenshot des NuGet-Pakets „AspNetCore.Diagnostics.HealthChecks“.](./media/monitor-app-health/aspnet-core-diagnostics-health-checks.png)

<span data-ttu-id="31d62-146">**Abbildung 8-7.**</span><span class="sxs-lookup"><span data-stu-id="31d62-146">**Figure 8-7**.</span></span> <span data-ttu-id="31d62-147">Mit AspNetCore.Diagnostics.HealthChecks in Catalog.API implementierte benutzerdefinierte Integritätsprüfungen</span><span class="sxs-lookup"><span data-stu-id="31d62-147">Custom Health Checks implemented in Catalog.API using AspNetCore.Diagnostics.HealthChecks</span></span>

<span data-ttu-id="31d62-148">Im folgenden Code werden die Implementierungen der Integritätsprüfungen für jeden abhängigen Dienst hinzugefügt, und anschließend wird die Middleware konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="31d62-148">In the following code, the health check implementations are added for each dependent service and then the middleware is configured:</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

<span data-ttu-id="31d62-149">Fügen Sie abschließend die HealthCheck-Middleware hinzu, die am Endpunkt /hc lauscht:</span><span class="sxs-lookup"><span data-stu-id="31d62-149">Finally, add the HealthCheck middleware to listen to “/hc” endpoint:</span></span>

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
}
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="31d62-150">Abfragen eines Berichts zum Integritätsstatus der Microservices</span><span class="sxs-lookup"><span data-stu-id="31d62-150">Query your microservices to report about their health status</span></span>

<span data-ttu-id="31d62-151">Wenn Sie wie in diesem Artikel beschrieben Integritätsüberprüfungen konfiguriert haben, können Sie direkt über den Browser überprüfen, ob der Microservice einwandfrei funktioniert, sobald dieser in Docker ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-151">When you've configured health checks as described in this article and you have the microservice running in Docker, you can directly check from a browser if it's healthy.</span></span> <span data-ttu-id="31d62-152">Sie müssen den Containerport im Docker-Host veröffentlichen, damit Sie über die externe Docker-Host-IP-Adresse oder `localhost` auf den Container zugreifen können, wie in Abbildung 8-8 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="31d62-152">You have to publish the container port in the Docker host, so you can access the container through the external Docker host IP or through `localhost`, as shown in figure 8-8.</span></span>

![Screenshot der von einer Integritätsprüfung zurückgegebenen JSON-Antwort.](./media/monitor-app-health/health-check-json-response.png)

<span data-ttu-id="31d62-154">**Abbildung 8-8.**</span><span class="sxs-lookup"><span data-stu-id="31d62-154">**Figure 8-8**.</span></span> <span data-ttu-id="31d62-155">Überprüfen des Integritätsstaus eines einzelnen Diensts über einen Browser</span><span class="sxs-lookup"><span data-stu-id="31d62-155">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="31d62-156">In diesem Test können Sie sehen, dass der Microservice `Catalog.API` (der auf Port 5101 ausgeführt wird) einwandfrei funktioniert, da er den HTTP-Status 200 und Statusinformationen im JSON-Format zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="31d62-156">In that test, you can see that the `Catalog.API` microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="31d62-157">Der Dienst hat die Integrität seiner SQL Server-Datenbankabhängigkeit und RabbitMQ ebenfalls überprüft, weshalb die Integritätsprüfung sich selbst als „Fehlerfrei“ meldet.</span><span class="sxs-lookup"><span data-stu-id="31d62-157">The service also checked the health of its SQL Server database dependency and RabbitMQ, so the health check reported itself as healthy.</span></span>

## <a name="use-watchdogs"></a><span data-ttu-id="31d62-158">Verwenden von Überwachungselementen</span><span class="sxs-lookup"><span data-stu-id="31d62-158">Use watchdogs</span></span>

<span data-ttu-id="31d62-159">Bei einem Überwachungselement handelt es sich um einen separaten Dienst, der die Integrität überprüfen und in mehreren Diensten geladen werden kann. Außerdem kann es Berichte zur Integrität der Microservices erstellen, indem es eine Abfrage an die bereit eingeführte `HealthChecks`-Bibliothek sendet.</span><span class="sxs-lookup"><span data-stu-id="31d62-159">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the `HealthChecks` library introduced earlier.</span></span> <span data-ttu-id="31d62-160">Dadurch können Fehler vermieden werden, die anhand der Ansicht eines einzelnen Diensts nicht ermittelt werden könnten.</span><span class="sxs-lookup"><span data-stu-id="31d62-160">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="31d62-161">Überwachungselemente eignen sich außerdem zum Hosten von Code, über den ohne Benutzerinteraktion Abhilfemaßnahmen für bekannte Bedingungen ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="31d62-161">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="31d62-162">Das eShopOnContainers-Beispiel enthält eine Webseite, auf der wie in Abbildung 8-9 dargestellt Beispielberichte zur Integritätsüberprüfung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="31d62-162">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 8-9.</span></span> <span data-ttu-id="31d62-163">Dabei handelt es sich um das einfachste Überwachungselement, da es nur den Zustand der Microservices und Webanwendungen in eShopOnContainers anzeigt.</span><span class="sxs-lookup"><span data-stu-id="31d62-163">This is the simplest watchdog you could have since it only shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="31d62-164">In der Regel führt ein Überwachungselement Aktionen aus, wenn der Status „Fehlerhaft“ ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-164">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

<span data-ttu-id="31d62-165">[AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) stellt auch das NuGet-Paket [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) bereit, das zum Anzeigen der Ergebnisse der Integritätsprüfung der konfigurierten URIs verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="31d62-165">Fortunately, [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) also provides [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) NuGet package that can be used to display the health check results from the configured URIs.</span></span>

![Screenshot des Integritätsstatus von eShopOnContainers in der Integritätsüberprüfungs-Benutzeroberfläche.](./media/monitor-app-health/health-check-status-ui.png)

<span data-ttu-id="31d62-167">**Abbildung 8-9.**</span><span class="sxs-lookup"><span data-stu-id="31d62-167">**Figure 8-9**.</span></span> <span data-ttu-id="31d62-168">Beispielbericht zur Integritätsüberprüfung in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="31d62-168">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="31d62-169">Dieser Überwachungsdienst fragt also den Endpunkt „/hc“ aller Microservices ab.</span><span class="sxs-lookup"><span data-stu-id="31d62-169">In summary, this watchdog service queries each microservice’s "/hc" endpoint.</span></span> <span data-ttu-id="31d62-170">Dadurch werden alle darin definierten Integritätsüberprüfungen ausgeführt und ein allgemeiner Integritätsstatus zurückgegeben, der von diesen Überprüfungen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="31d62-170">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span> <span data-ttu-id="31d62-171">HealthChecksUI ist mit wenigen Konfigurationseinträgen und zwei Codezeilen, die zur Datei „Startup.cs“ des Überwachungsdiensts hinzugefügt werden müssen, leicht zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="31d62-171">The HealthChecksUI is easy to consume with a few configuration entries and two lines of code that needs to be added into the Startup.cs of the watchdog service.</span></span>

<span data-ttu-id="31d62-172">Beispielkonfigurationsdatei für HealthChecksUI:</span><span class="sxs-lookup"><span data-stu-id="31d62-172">Sample configuration file for health check UI:</span></span>

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

<span data-ttu-id="31d62-173">Datei „Startup.cs“, die HealthChecksUI hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="31d62-173">Startup.cs file that adds HealthChecksUI:</span></span>

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config=> config.UIPath = “/hc-ui”);
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="31d62-174">Integritätsüberprüfungen, wenn Orchestratoren verwendet werden</span><span class="sxs-lookup"><span data-stu-id="31d62-174">Health checks when using orchestrators</span></span>

<span data-ttu-id="31d62-175">Orchestratoren wie Kubernetes und Service Fabric führen regelmäßig zur Überwachung der Verfügbarkeit Ihrer Microservices Integritätsüberprüfungen durch, indem sie Anforderungen senden, um diese Microservices zu testen.</span><span class="sxs-lookup"><span data-stu-id="31d62-175">To monitor the availability of your microservices, orchestrators like Kubernetes and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="31d62-176">Wenn ein Orchestrator ermittelt, dass ein Dienst bzw. ein Container fehlerhaft ist, leitet er keine Anforderungen mehr an diese Instanz weiter.</span><span class="sxs-lookup"><span data-stu-id="31d62-176">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="31d62-177">Außerdem erstellt er dann in der Regel eine neue Instanz dieses Containers.</span><span class="sxs-lookup"><span data-stu-id="31d62-177">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="31d62-178">Beispielsweise können die meisten Orchestratoren Integritätsüberprüfungen verwenden, um Bereitstellungen ohne Ausfallzeit zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="31d62-178">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="31d62-179">Erst wenn sich der Status des Diensts bzw. Containers in „healthy“ (OK) ändert, leitet der Orchestrator wieder Datenverkehr an die Instanzen des Diensts bzw. Containers weiter.</span><span class="sxs-lookup"><span data-stu-id="31d62-179">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="31d62-180">Die Systemüberwachung ist besonders wichtig, wenn ein Orchestrator ein Anwendungsupgrade ausführt.</span><span class="sxs-lookup"><span data-stu-id="31d62-180">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="31d62-181">Einige Orchestratoren (wie Azure Service Fabric) führen in Phasen Updates für Dienste aus. Sie aktualisieren also z.B. ein Fünftel der Clusteroberfläche für jedes Anwendungsupgrade.</span><span class="sxs-lookup"><span data-stu-id="31d62-181">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="31d62-182">Die Knoten, für die zur selben Zeit ein Upgrade ausgeführt wird, werden als *Upgradedomäne* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="31d62-182">The set of nodes that's upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="31d62-183">Wenn für alle Upgradedomänen ein Upgrade ausgeführt wurde und für die Benutzer verfügbar sind, muss diese Upgradedomäne Integritätsüberprüfungen übergeben, bevor die Bereitstellung auf die nächste Upgradedomäne verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-183">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="31d62-184">Berichtsmetriken des Diensts machen einen weiteren Aspekt der Dienstintegrität aus.</span><span class="sxs-lookup"><span data-stu-id="31d62-184">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="31d62-185">Dabei handelt es sich um eine erweiterte Funktion des Integritätsmodells einiger Orchestratoren wie Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="31d62-185">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="31d62-186">Metriken sind von Bedeutung, wenn Orchestratoren verwendet werden, da sie einen Ausgleich für die Ressourcennutzung schaffen.</span><span class="sxs-lookup"><span data-stu-id="31d62-186">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="31d62-187">Metriken können außerdem auf Systemintegrität hindeuten.</span><span class="sxs-lookup"><span data-stu-id="31d62-187">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="31d62-188">Beispielsweise kann es sein, dass Sie über eine Anwendung mit vielen Microservices verfügen, wobei jede Instanz einen Bericht zu einer „Anforderungen pro Sekunde“-Metrik erstellt.</span><span class="sxs-lookup"><span data-stu-id="31d62-188">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="31d62-189">Wenn ein Dienst mehre Ressourcen (z.B. den Arbeitsspeicher oder den Prozessor) als ein anderer Dienst verwendet, kann der Orchestrator Dienstinstanzen innerhalb des Clusters verschieben, um zu versuchen, die Ressourcenverwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="31d62-189">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="31d62-190">Beachten Sie, dass Azure Service Fabric ein eigenes [Modell zur Systemüberwachung](/azure/service-fabric/service-fabric-health-introduction) umfasst, das umfassender ist als einfache Integritätsüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="31d62-190">Note that Azure Service Fabric provides its own [Health Monitoring model](/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="31d62-191">Erweiterte Überwachung: Visualisierung, Analyse und Warnungen</span><span class="sxs-lookup"><span data-stu-id="31d62-191">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="31d62-192">Als letzter Schritt im Rahmen der Überwachung wird der Ereignisdatenstrom visualisiert, ein Bericht zur Leistung des Diensts wird erstellt, und es wird eine Warnung ausgegeben, wenn ein Problem erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="31d62-192">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="31d62-193">Sie können für diesen Bestandteil der Überwachung mehrere Lösungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d62-193">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="31d62-194">Einerseits können Sie einfache benutzerdefinierte Anwendungen verwenden, die den Status Ihrer Dienste anzeigen, z. B. die im Zusammenhang mit [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) erwähnten benutzerdefinierten Seiten.</span><span class="sxs-lookup"><span data-stu-id="31d62-194">You can use simple custom applications showing the state of your services, like the custom page shown when explaining the [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks).</span></span> <span data-ttu-id="31d62-195">Andererseits können Sie auch Tools mit erweiterten Funktionen wie [Azure Monitor](https://azure.microsoft.com/services/monitor/) verwenden, um Warnungen anhand des Datenstroms der Ereignisse auszulösen.</span><span class="sxs-lookup"><span data-stu-id="31d62-195">Or you could use more advanced tools like [Azure Monitor](https://azure.microsoft.com/services/monitor/) to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="31d62-196">Außerdem können Sie Microsoft Power BI oder andere Lösungen (z.B. Kibana oder Splunk) verwenden, um Daten zu visualisieren, wenn Sie alle Ereignisdatenströme gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="31d62-196">Finally, if you're storing all the event streams, you can use Microsoft Power BI or other solutions like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="31d62-197">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="31d62-197">Additional resources</span></span>

- <span data-ttu-id="31d62-198">**HealthChecks und HealthChecksUI für ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="31d62-198">**HealthChecks and HealthChecks UI for ASP.NET Core** </span></span>\
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- <span data-ttu-id="31d62-199">**Einführung in die Systemüberwachung mit Service Fabric** </span><span class="sxs-lookup"><span data-stu-id="31d62-199">**Introduction to Service Fabric health monitoring** </span></span>\
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- <span data-ttu-id="31d62-200">**Azure Monitor** </span><span class="sxs-lookup"><span data-stu-id="31d62-200">**Azure Monitor** </span></span>\
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
><span data-ttu-id="31d62-201">[Zurück](implement-circuit-breaker-pattern.md)
>[Weiter](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="31d62-201">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>
