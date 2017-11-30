---
title: "Systemüberwachung"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Systemüberwachung"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a><span data-ttu-id="1a58d-104">Systemüberwachung</span><span class="sxs-lookup"><span data-stu-id="1a58d-104">Health monitoring</span></span>

<span data-ttu-id="1a58d-105">Systemüberwachung kann in der Nähe von Echtzeit Informationen über den Status von Containern und Microservices erlauben.</span><span class="sxs-lookup"><span data-stu-id="1a58d-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="1a58d-106">Systemüberwachung für zahlreiche Aspekte Microservices Betrieb von entscheidender Bedeutung ist, und ist besonders wichtig bei Orchestrators partielle Anwendungsupgrades in Phasen durchführen, wie weiter unten erläutert.</span><span class="sxs-lookup"><span data-stu-id="1a58d-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="1a58d-107">Microservices-basierte Anwendungen verwenden häufig Takte oder Integrität überprüft, um ihre Systemmonitore Planern und Orchestrators zum Nachverfolgen der Vielzahl von Diensten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1a58d-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="1a58d-108">Wenn Dienste irgendeine "Ich verwende alive" Signal bei Bedarf oder nach einem Zeitplan senden können, kann Ihre Anwendung Risiken stoßen, wenn Bereitstellen von Updates oder Fehlern zu spät einfach zu erkennen und nicht in der Lage zu kaskadierende Fehler beenden, die größere Ausfälle annehmen können.</span><span class="sxs-lookup"><span data-stu-id="1a58d-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="1a58d-109">Im typischen Modell Dienste senden Berichte über ihren Status, und diese Informationen um einen allgemeinen Überblick über den Zustand der Anwendung bereitzustellen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="1a58d-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="1a58d-110">Bei Verwendung einer Orchestrator können Sie Integritätsinformationen für Ihre Orchestrator-Cluster bereitstellen, damit der Cluster entsprechend reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="1a58d-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="1a58d-111">Wenn Sie investieren Sie in qualitativ hochwertige Clientintegritätsberichte, die für Ihre Anwendung angepasst ist, können Sie erkennen und Beheben von Problemen für die ausgeführte Anwendung wesentlich einfacher.</span><span class="sxs-lookup"><span data-stu-id="1a58d-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="1a58d-112">Implementieren die Integrität überprüft in ASP.NET Core services</span><span class="sxs-lookup"><span data-stu-id="1a58d-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="1a58d-113">Wenn Sie eine ASP.NET Core Microservice oder Web-Anwendung entwickeln, können Sie eine Bibliothek mit dem Namen HealthChecks vom Team ASP.NET verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="1a58d-114">(Ab Mai 2017 ist eine frühe Version auf GitHub verfügbar).</span><span class="sxs-lookup"><span data-stu-id="1a58d-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="1a58d-115">Diese Bibliothek ist einfach zu verwenden und bietet Funktionen, mit denen Sie überprüfen, ob eine bestimmte externe Ressource, die für Ihre Anwendung (z. B. eine SQL Server-Datenbank oder eine remote-API) benötigt ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a58d-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="1a58d-116">Wenn Sie diese Bibliothek verwenden, können Sie auch entscheiden, was es bedeutet, dass die Ressource fehlerfrei ist, wie weiter unten erläutert.</span><span class="sxs-lookup"><span data-stu-id="1a58d-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="1a58d-117">Um diese Bibliothek verwenden, müssen Sie zuerst die Bibliothek in Ihr Microservices verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="1a58d-118">Zweitens brauchen Sie eine Front-End-Anwendung, die Abfragen für die Statusberichte.</span><span class="sxs-lookup"><span data-stu-id="1a58d-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="1a58d-119">Die front-End-Anwendung ist möglicherweise eine benutzerdefinierte Berichterstellungsanwendung, oder es ist möglicherweise ein Orchestrator selbst, der entsprechend reagieren kann den Integritätsstatus.</span><span class="sxs-lookup"><span data-stu-id="1a58d-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="1a58d-120">Mithilfe der HealthChecks-Bibliothek in Ihrem Back-End-ASP.NET microservices</span><span class="sxs-lookup"><span data-stu-id="1a58d-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="1a58d-121">Sie können sehen, wie die HealthChecks-Bibliothek in der beispielanwendung eShopOnContainers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1a58d-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="1a58d-122">Um zu beginnen, müssen Sie definieren, was einen fehlerfreien Status für jede Microservice ausmacht.</span><span class="sxs-lookup"><span data-stu-id="1a58d-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="1a58d-123">In der beispielanwendung sind die Microservices fehlerfrei, wenn die Microservice API wird über HTTP und auch die zugehörige SQL Server-Datenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1a58d-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="1a58d-124">In der Zukunft werden Sie die Bibliothek HealthChecks als NuGet-Paket installieren.</span><span class="sxs-lookup"><span data-stu-id="1a58d-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="1a58d-125">Aber Verfassung dieses Dokuments herunterladen und kompilieren Sie den Code als Teil der Projektmappe werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="1a58d-126">Klonen Sie den Code unter https://github.com/aspnet/HealthChecks, und kopieren Sie die folgenden Ordnern der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="1a58d-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="1a58d-127">Src/allgemeinen</span><span class="sxs-lookup"><span data-stu-id="1a58d-127">src/common</span></span>
  - <span data-ttu-id="1a58d-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="1a58d-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="1a58d-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="1a58d-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="1a58d-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="1a58d-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="1a58d-131">Sie können auch zusätzliche Überprüfungen wie diejenigen für Azure (Microsoft.Extensions.HealthChecks.AzureStorage), aber da diese Version des eShopOnContainers keine Abhängigkeit auf Azure verwenden, Sie ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1a58d-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="1a58d-132">Sie benötigen keine der integritätsprüfungen ASP.NET, da ASP.NET Core eShopOnContainers basiert.</span><span class="sxs-lookup"><span data-stu-id="1a58d-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="1a58d-133">Abbildung 10 – 6 zeigt die HealthChecks-Bibliothek in Visual Studio bereit als ein grundlegender Baustein von jeder Microservices verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="1a58d-134">**Abbildung 10 – 6**.</span><span class="sxs-lookup"><span data-stu-id="1a58d-134">**Figure 10-6**.</span></span> <span data-ttu-id="1a58d-135">ASP.NET Core HealthChecks Bibliothek Quellcode in Visual Studio-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="1a58d-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="1a58d-136">Wie zuvor eingeführt wird, ist die erste Vorgehensweise in jedem Projekt Microservice einen Verweis auf die drei HealthChecks Bibliotheken hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="1a58d-137">Danach fügen Sie die Integrität Aktionen, die Sie in diesem Microservice ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a58d-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="1a58d-138">Diese Aktionen sind im Grunde Abhängigkeiten von anderen Microservices (HttpUrlCheck) oder Datenbanken (derzeit SqlCheck\* für SQL Server-Datenbanken).</span><span class="sxs-lookup"><span data-stu-id="1a58d-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="1a58d-139">Fügen Sie die Aktion in die Startklasse. jedes Microservice ASP.NET oder ASP.NET Web-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a58d-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="1a58d-140">Jeder Dienst oder einer Website-Anwendung sollte alle Abhängigkeiten für die HTTP- oder die Datenbank als eine AddHealthCheck Methode hinzufügen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="1a58d-141">Z. B. die MVC-Webanwendung aus eShopOnContainers hängt von vielen Diensten, daher verfügt über mehrere AddCheck-Methoden, die die integritätsprüfungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="1a58d-142">Z. B. im folgenden Codebeispiel sehen Sie wie die Katalog-Microservice eine Abhängigkeit auf der SQL Server-Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

<span data-ttu-id="1a58d-143">Die MVC-Webanwendung der eShopOnContainers hat jedoch mehrere Abhängigkeiten auf den übrigen der Microservices an.</span><span class="sxs-lookup"><span data-stu-id="1a58d-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="1a58d-144">Aus diesem Grund wird eine AddUrlCheck-Methode für jede Microservice wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1a58d-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

<span data-ttu-id="1a58d-145">Daher gebe ein Microservice keinen Status "fehlerfreien", bis alle seine Überprüfungen ebenfalls fehlerfrei sind.</span><span class="sxs-lookup"><span data-stu-id="1a58d-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="1a58d-146">Wenn die Microservice keine Abhängigkeit auf einen Dienst oder SQL Server verfügt, sollten Sie nur eine Prüfung Healthy("Ok") hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="1a58d-147">Der folgende Code stammt aus dem eShopOnContainers basket.api Microservice.</span><span class="sxs-lookup"><span data-stu-id="1a58d-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="1a58d-148">(Die Warenkorb-Microservice verwendet den Redis-Cache, aber die Bibliothek enthält noch keinen Redis Health Check-Anbieter).</span><span class="sxs-lookup"><span data-stu-id="1a58d-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="1a58d-149">Für einen Dienst oder einer Website Anwendung den Health Check-Endpunkt verfügbar machen, muss er die UseHealthChecks aktivieren (\[*Url\_für\_Integrität\_überprüft*\]) Erweiterung Methode.</span><span class="sxs-lookup"><span data-stu-id="1a58d-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="1a58d-150">Diese Methode wird an die WebHostBuilder Ebene in der main-Methode der Program-Klasse der ASP.NET Core Dienst oder einer Website Anwendung direkt nach UseKestrel wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

<span data-ttu-id="1a58d-151">Der Prozess funktioniert wie folgt: jede Microservice macht den Endpunkt HC.</span><span class="sxs-lookup"><span data-stu-id="1a58d-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="1a58d-152">Dieser Endpunkt wird von der Bibliothek HealthChecks ASP.NET Core-Middleware erstellt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="1a58d-153">Wenn es sich bei diesen Endpunkt aufgerufen wird, führt er alle integritätsprüfungen, die in der AddHealthChecks-Methode in die Startklasse konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="1a58d-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="1a58d-154">Die UseHealthChecks Methode erwartet einen Port oder einen Pfad an.</span><span class="sxs-lookup"><span data-stu-id="1a58d-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="1a58d-155">Dieser Port oder der Pfad ist der Endpunkt verwendet, um den Integritätsstatus des Diensts zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="1a58d-156">Der Katalog Microservice verwendet z. B. die HC Pfad.</span><span class="sxs-lookup"><span data-stu-id="1a58d-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="1a58d-157">Health Check-Antworten Zwischenspeichern</span><span class="sxs-lookup"><span data-stu-id="1a58d-157">Caching health check responses</span></span>

<span data-ttu-id="1a58d-158">Seit nicht dazu führen, dass ein Denial-of-Service (DoS) in Ihre Dienste möchten, oder Sie einfach keine Service Leistungseinbußen sollten durch Überprüfen von Ressourcen zu häufig können Sie cache zurückgegeben und Konfigurieren einer Cachedauer für jede integritätsprüfung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="1a58d-159">Wird standardmäßig können die Cachedauer intern auf 5 Minuten festgelegt ist, Sie jedoch ändern, Cachedauer auf jede integritätsprüfung durchgeführt werden, wie im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1a58d-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="1a58d-160">Abfragen von Ihrer Microservices Bericht zu ihrem Integritätsstatus</span><span class="sxs-lookup"><span data-stu-id="1a58d-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="1a58d-161">Wenn Sie eine integritätsprüfung konfiguriert haben, wie hier beschrieben wird, sobald die Microservice in Docker ausgeführt wird, können Sie direkt über einen Browser überprüfen, ob es fehlerfrei ist.</span><span class="sxs-lookup"><span data-stu-id="1a58d-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="1a58d-162">(Dies erfordert, dass Sie den Container Port außerhalb des Docker-Host veröffentlichen, damit Sie über "localhost" oder über die externe IP Docker-Host-Container zugreifen können.) Abbildung 10 – 7 zeigt eine Anforderung in einem Browser und die entsprechende Antwort.</span><span class="sxs-lookup"><span data-stu-id="1a58d-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="1a58d-163">**Abbildung 10 – 7**.</span><span class="sxs-lookup"><span data-stu-id="1a58d-163">**Figure 10-7**.</span></span> <span data-ttu-id="1a58d-164">Überprüfen des Integritätsstatus von einem einzigen Dienst in einem browser</span><span class="sxs-lookup"><span data-stu-id="1a58d-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="1a58d-165">In diesen Test sehen Sie, dass die catalog.api Microservice (Port 5101 ausgeführt) fehlerfrei ist HTTP-Statuscode 200 und Statusinformationen im JSON-Format zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1a58d-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="1a58d-166">Dies bedeutet auch, dass intern der Dienst auch die Integrität ihrer SQL Server-Datenbank-Abhängigkeit aktiviert und integritätsprüfung selbst als fehlerfrei gemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="1a58d-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="1a58d-167">Verwenden von watchdogs</span><span class="sxs-lookup"><span data-stu-id="1a58d-167">Using watchdogs</span></span>

<span data-ttu-id="1a58d-168">Watchdog ist einem separaten Dienst, der Überwachen der Integrität und Dienste, und melden der Integrität zu den Microservices durch Erstellen von Abfragen mit der bereits vorgestellten HealthChecks-Bibliothek laden kann.</span><span class="sxs-lookup"><span data-stu-id="1a58d-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="1a58d-169">Dies hilft zu verhindern, dass Fehler, die nicht erkannt würden, basierend auf den Überblick über einen einzelnen Dienst.</span><span class="sxs-lookup"><span data-stu-id="1a58d-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="1a58d-170">Watchdogs sind auch eine gute zum Hosten von Code, die Aktionen zur Problembehebung für bekannte Bedingungen ohne Benutzerinteraktion ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1a58d-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="1a58d-171">Das eShopOnContainers-Beispiel enthält eine Webseite, die Integritätsberichte Kontrollkästchen Beispiel zeigt, wie in Abbildung 10 – 8 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="1a58d-172">Dies ist der einfachste Watchdog, die Sie möglicherweise, da sie lediglich zeigt der Status des Microservices und Web-Anwendungen in eShopOnContainers werden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="1a58d-173">In der Regel führt Watchdog auch Aktionen aus, wenn sich in einem fehlerhaften Status erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="1a58d-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="1a58d-174">**Abbildung 10 – 8**.</span><span class="sxs-lookup"><span data-stu-id="1a58d-174">**Figure 10-8**.</span></span> <span data-ttu-id="1a58d-175">Beispielbericht Health Check in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="1a58d-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="1a58d-176">Zusammengefasst bietet die Middleware ASP.NET der ASP.NET Core HealthChecks Bibliothek einen einzelnen Health Check-Endpunkt für jede Microservice.</span><span class="sxs-lookup"><span data-stu-id="1a58d-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="1a58d-177">Alle darin definierten integritätsprüfungen auszuführen werden und gesamtintegritätsstatus je nach der alle diese Überprüfungen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1a58d-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="1a58d-178">Die Bibliothek HealthChecks ist erweiterbar, durch neue Systemdiagnosen zukünftige externer Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="1a58d-179">Beispielsweise erwarten wir, dass in Zukunft die Bibliothek integritätsprüfungen für Redis-Cache und für andere Datenbanken vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1a58d-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="1a58d-180">Die Bibliothek ermöglicht integritätsberichterstellung durch mehrere Dienst oder diese Anwendung Abhängigkeiten, und Sie können anschließend Aktionen basierend auf diesen Systemdiagnosen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="1a58d-181">Integritätsprüfungen Verwendung orchestrators</span><span class="sxs-lookup"><span data-stu-id="1a58d-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="1a58d-182">Informationen zum Überwachen der Verfügbarkeit Ihrer Microservices integritätsprüfungen Orchestrators wie Docker Containerhostclustern, Kubernetes und-Dienststrukturen in regelmäßigen Abständen durch Senden von Anforderungen an die Microservices zu testen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="1a58d-183">Wenn ein Orchestrator feststellt, dass ein Dienstcontainer fehlerhaft ist, Weiterleiten von Anforderungen an diese Instanz wird beendet.</span><span class="sxs-lookup"><span data-stu-id="1a58d-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="1a58d-184">Es erstellt auch in der Regel eine neue Instanz der betreffenden Container.</span><span class="sxs-lookup"><span data-stu-id="1a58d-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="1a58d-185">Für die Instanz, können die meisten Orchestrators Systemdiagnosen Sie Ausfallzeiten Deployments verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a58d-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="1a58d-186">Nur, wenn der Status einer Dienstcontainer/ändert fehlerfrei wird die Orchestrator routing des Datenverkehrs Dienstcontainer/Instanzen starten.</span><span class="sxs-lookup"><span data-stu-id="1a58d-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="1a58d-187">Systemüberwachung ist besonders wichtig, wenn ein Orchestrator ein Anwendungsupgrade ausführt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="1a58d-188">Einige Orchestrators (z. B. Azure Service Fabric) aktualisieren von Diensten in Phasen – sie können z. B. ein Fünftel der Cluster-Oberfläche für jedes Anwendungsupgrade aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1a58d-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="1a58d-189">Die Gruppe der Knoten, die zur gleichen Zeit aktualisiert wird als bezeichnet ein *upgradedomäne*.</span><span class="sxs-lookup"><span data-stu-id="1a58d-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="1a58d-190">Nachdem jede upgradedomäne aktualisiert wurde und für Benutzer verfügbar ist, muss dieser upgradedomäne integritätsprüfungen übergeben, bevor die Bereitstellung mit der nächsten upgradedomäne fortfährt.</span><span class="sxs-lookup"><span data-stu-id="1a58d-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="1a58d-191">Ein weiterer Aspekt der Integrität des Diensts meldet Metriken aus dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="1a58d-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="1a58d-192">Dies ist eine erweiterte Funktion von das Integritätsmodell des einige Orchestrators, wie Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="1a58d-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="1a58d-193">Metriken sind wichtig, wenn ein Orchestrator verwendet werden, da sie verwendet werden, um den Ressourcenverbrauch auszugleichen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="1a58d-194">Metriken können auch ein Indikator der Systemintegrität sein.</span><span class="sxs-lookup"><span data-stu-id="1a58d-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="1a58d-195">Angenommen, Sie möglicherweise eine Anwendung mit vielen Microservices, und jeder Instanz gibt eine Metrik der Anforderungen pro Sekunde (RPS).</span><span class="sxs-lookup"><span data-stu-id="1a58d-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="1a58d-196">Wenn ein Dienst mehr Ressourcen (Arbeitsspeicher, Prozessor, usw.) als ein anderer Dienst verwendet wird, konnte der Orchestrator-Dienstinstanzen im Cluster zu dem Versuch, sogar Ressourcenverwendung verwalten bewegen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="1a58d-197">Beachten Sie, dass bei Verwendung von Azure Service Fabric eigene darüber [Systemüberwachung Modell](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), also komplexer als einfache Systemdiagnosen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="1a58d-198">Erweiterte Überwachung: Visualisierung, Analyse und Warnungen</span><span class="sxs-lookup"><span data-stu-id="1a58d-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="1a58d-199">Der letzte Teil des Überwachung ist Visualisieren von den Datenstrom, auf die Leistung des Service reporting und warnen, wenn ein Problem festgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1a58d-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="1a58d-200">Sie können verschiedene Lösungen für dieses Aspekts der Überwachung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a58d-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="1a58d-201">Können Sie einfache benutzerdefinierte Anwendungen, die mit dem Status der Dienste, wie benutzerdefinierte Seite wurde wir gezeigt, wenn wir erläutert [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="1a58d-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="1a58d-202">Oder Sie mithilfe von Tools mit erweiterter Funktionalität wie Azure Application Insights und Operations Management Suite Warnungen basierend auf den Datenstrom von Ereignissen ausgelöst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1a58d-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="1a58d-203">Abschließend, wenn Sie die ereignisdatenströme gespeichert wurden, können Sie Microsoft Power BI oder eine Lösung eines Drittanbieters, wie Kibana oder Splunk verwenden zum Visualisieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="1a58d-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1a58d-204">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1a58d-204">Additional resources</span></span>

-   <span data-ttu-id="1a58d-205">**ASP.NET Core HealthChecks** (frühen Release) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="1a58d-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="1a58d-206">**Einführung in Service Fabric-Integritätsüberwachung**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="1a58d-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="1a58d-207">**Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="1a58d-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="1a58d-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="1a58d-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1a58d-209">[Vorherigen] (implementieren-Circuit-Breaker-pattern.md) [weiter] (.. /Secure-NET-microservices-Web-Applications/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="1a58d-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
