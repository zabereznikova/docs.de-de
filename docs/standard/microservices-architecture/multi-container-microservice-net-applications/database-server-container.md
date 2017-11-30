---
title: Verwenden einen Datenbankserver, die als container
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Verwenden einen Datenbankserver, die als container"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7e5f33c4e7edf9d0d4551c5125976fcb8fda392f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="94bea-104">Verwenden einen Datenbankserver, die als container</span><span class="sxs-lookup"><span data-stu-id="94bea-104">Using a database server running as a container</span></span>

<span data-ttu-id="94bea-105">Sie können Ihre Datenbanken (SQL Server, PostgreSQL, MySQL usw.) auf reguläre eigenständigen Servern in lokalen Clustern und in PaaS-Dienste in der Cloud wie Azure SQL-Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="94bea-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="94bea-106">Allerdings für Entwicklungs- und testumgebungen, müssen die Datenbanken, die als Container ausgeführt ist es bequem erscheint, da Sie keine externe Abhängigkeit und einfach ausgeführt wird der Docker-verfassen Befehl wird die gesamte Anwendung gestartet.</span><span class="sxs-lookup"><span data-stu-id="94bea-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency, and simply running the docker-compose command starts the whole application.</span></span> <span data-ttu-id="94bea-107">Diese Datenbanken als Container ist auch hervorragend für die Integrationstests erfolgreich, da die Datenbank im Container gestartet wird und wird immer mit den gleichen Beispieldaten aufgefüllt, damit Tests besser vorhersagbar sein können.</span><span class="sxs-lookup"><span data-stu-id="94bea-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="94bea-108">SQL Server, die als Container ausgeführt werden, mit einer Datenbank Microservice bezogene</span><span class="sxs-lookup"><span data-stu-id="94bea-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="94bea-109">In eShopOnContainers, ist ein Container mit dem Namen sql.data definiert, der [Docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) -Datei, die SQL Server für Linux mit allen SQL Server-Datenbanken, die erforderlich sind, für die Microservices ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94bea-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="94bea-110">(Sie möglicherweise auch eine SQL Server-Container für jede Datenbank, aber wäre es erforderlich, mehr Arbeitsspeicher Docker zugewiesen.) Der wichtige Punkt im Microservices ist, dass jede Microservice ihre verknüpften Daten aus diesem Grund seine zugehörige SQL-Datenbank in diesem Fall besitzt.</span><span class="sxs-lookup"><span data-stu-id="94bea-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="94bea-111">Die Datenbanken können jedoch eine beliebige Stelle.</span><span class="sxs-lookup"><span data-stu-id="94bea-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="94bea-112">Container in der beispielanwendung durch folgenden Code in der Datei Docker compose.yml YAML konfiguriert ist, die ausgeführt wird, beim Ausführen von SQL-Server bilden Docker-einrichten.</span><span class="sxs-lookup"><span data-stu-id="94bea-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run docker-compose up.</span></span> <span data-ttu-id="94bea-113">Beachten Sie, dass der Code YAML Konfigurationsinformationen aus dem generischen Docker-compose.yml-Datei und die Docker-compose.override.yml konsolidiert hat.</span><span class="sxs-lookup"><span data-stu-id="94bea-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="94bea-114">(In der Regel würden Sie die umgebungseinstellungen aus der Basistabelle oder statische Informationen, die im Zusammenhang mit SQL Server-Images trennen.)</span><span class="sxs-lookup"><span data-stu-id="94bea-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

<span data-ttu-id="94bea-115">Die folgenden "Docker run" Befehl kann diesen Container ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="94bea-115">The following docker run command can run that container:</span></span>

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

<span data-ttu-id="94bea-116">Wenn Sie eine Anwendung mit mehreren Container wie eShopOnContainers bereitstellen, es ist jedoch einfacher, verwenden Sie den Docker-verfassen Befehl, in dem sie alle erforderlichen Container für die Anwendung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="94bea-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the docker-compose up command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="94bea-117">Wenn Sie dieser SQL Server-Container zum ersten Mal starten, initialisiert der Container SQL Server mit dem Kennwort, das Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="94bea-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="94bea-118">Wenn SQL Server als Container ausgeführt wird, können Sie die Datenbank aktualisieren, indem Herstellen einer Verbindung über eine reguläre SQL-Verbindung, z. B. von SQL Server Management Studio oder Visual Studio mit C#\# Code.</span><span class="sxs-lookup"><span data-stu-id="94bea-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="94bea-119">Die eShopOnContainers-Anwendung initialisiert jeder Microservice-Datenbank mit Beispieldaten seeding mit den Daten zu starten, wie im folgenden Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="94bea-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="94bea-120">Mit SQL Server ausgeführt wird, als Container eignet sich nicht nur für die Demo möglicherweise Zugriff auf eine Instanz von SQL Server muss nicht.</span><span class="sxs-lookup"><span data-stu-id="94bea-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="94bea-121">Wie bereits erwähnt ist es auch hervorragend für Entwicklungs- und testumgebungen, sodass können Sie problemlos Integrationstests beginnend mit einem sauberen Image von SQL Server ausführen und Daten von neuen Beispieldaten seeding bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="94bea-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="94bea-122">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="94bea-122">Additional resources</span></span>

-   <span data-ttu-id="94bea-123">**Führen Sie das Image von SQL Server-Docker unter Linux, Mac oder Windows**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span><span class="sxs-lookup"><span data-stu-id="94bea-123">**Run the SQL Server Docker image on Linux, Mac, or Windows**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)</span></span>

-   <span data-ttu-id="94bea-124">**Verbinden und Abfragen von SQL Server on Linux mit Sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="94bea-124">**Connect and query SQL Server on Linux with sqlcmd**
[*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)</span></span>

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="94bea-125">Das Seeding mit Testdaten beim Start der Web-Anwendung</span><span class="sxs-lookup"><span data-stu-id="94bea-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="94bea-126">Zum Hinzufügen von Daten in die Datenbank beim Start der Anwendung können Sie die Configure-Methode in die Startklasse des Web-API-Projekts Code wie folgt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="94bea-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code...
    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure code...
        // Seed data through our custom class
        CatalogContextSeed.SeedAsync(app)
            .Wait();
        // Other Configure code...
    }
}
```

<span data-ttu-id="94bea-127">Der folgende Code in der benutzerdefinierten CatalogContextSeed Klasse Daten gefüllt.</span><span class="sxs-lookup"><span data-stu-id="94bea-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

```csharp
public class CatalogContextSeed
{
    public static async Task SeedAsync(IApplicationBuilder applicationBuilder)
    {
        var context = (CatalogContext)applicationBuilder
            .ApplicationServices.GetService(typeof(CatalogContext));
        using (context)
        {
            context.Database.Migrate();
            if (!context.CatalogBrands.Any())
            {
                context.CatalogBrands.AddRange(
                    GetPreconfiguredCatalogBrands());
                await context.SaveChangesAsync();
            }
            if (!context.CatalogTypes.Any())
            {
                context.CatalogTypes.AddRange(
                    GetPreconfiguredCatalogTypes());
                await context.SaveChangesAsync();
            }
        }
    }

    static IEnumerable<CatalogBrand> GetPreconfiguredCatalogBrands()
    {
        return new List<CatalogBrand>()
       {
           new CatalogBrand() { Brand = "Azure"},
           new CatalogBrand() { Brand = ".NET" },
           new CatalogBrand() { Brand = "Visual Studio" },
           new CatalogBrand() { Brand = "SQL Server" }
       };
    }

    static IEnumerable<CatalogType> GetPreconfiguredCatalogTypes()
    {
        return new List<CatalogType>()
        {
            new CatalogType() { Type = "Mug"},
            new CatalogType() { Type = "T-Shirt" },
            new CatalogType() { Type = "Backpack" },
            new CatalogType() { Type = "USB Memory Stick" }
        };
    }
}
```

<span data-ttu-id="94bea-128">Beim Ausführen von Integrationstests eignet sich über eine Möglichkeit zum Generieren von Daten mit Ihrer Integrationstests konsistent.</span><span class="sxs-lookup"><span data-stu-id="94bea-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="94bea-129">Es eignet sich hervorragend für testumgebungen, wird alles, was von Grund auf neu, einschließlich einer Instanz von SQL Server ausgeführt wird, für einen Container zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="94bea-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="94bea-130">EF Core InMemory-Datenbank im Vergleich zu SQL Server ausgeführt wird, als container</span><span class="sxs-lookup"><span data-stu-id="94bea-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="94bea-131">Eine andere gute Wahl, die beim Ausführen von Tests ist die Verwendung von Entity Framework InMemory-Datenbankanbieter.</span><span class="sxs-lookup"><span data-stu-id="94bea-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="94bea-132">Sie können diese Konfiguration in der Methode ConfigureServices die Startklasse im Web-API-Projekt angeben:</span><span class="sxs-lookup"><span data-stu-id="94bea-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

```csharp
public class Startup
{
    // Other Startup code ...
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddSingleton<IConfiguration>(Configuration);
        // DbContext using an InMemory database provider
        services.AddDbContext<CatalogContext>(opt => opt.UseInMemoryDatabase());
        //(Alternative: DbContext using a SQL Server provider
        //services.AddDbContext<CatalogContext>(c =>
        //{
            // c.UseSqlServer(Configuration["ConnectionString"]);
            //
        //});
    }
  
    // Other Startup code ...

}
```

<span data-ttu-id="94bea-133">Es ist jedoch eine wichtige Catch.</span><span class="sxs-lookup"><span data-stu-id="94bea-133">There is an important catch, though.</span></span> <span data-ttu-id="94bea-134">Die in-Memory-Datenbank unterstützt keine viele Einschränkungen, die für eine bestimmte Datenbank spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="94bea-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="94bea-135">Sie können z. B. einen eindeutigen Index für eine Spalte in der EF-Core-Modell hinzufügen und Schreibtest für Ihre Datenbank im Arbeitsspeicher, überprüfen Sie, dass es nicht zulässt, dass Sie einen doppelten Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="94bea-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="94bea-136">Aber wenn Sie die Datenbank im Arbeitsspeicher verwenden, können nicht eindeutige Indizes für eine Spalte behandelt.</span><span class="sxs-lookup"><span data-stu-id="94bea-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="94bea-137">Aus diesem Grund die Datenbank im Arbeitsspeicher nicht verhält sich genauso wie eine echte SQL Server-Datenbank – emuliert nicht datenbankspezifischen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="94bea-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="94bea-138">Deshalb ist eine in-Memory-Datenbank immer noch nützlich für das Testen und Prototyping.</span><span class="sxs-lookup"><span data-stu-id="94bea-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="94bea-139">Aber wenn Sie genau Integrationstests erfolgreich zu erstellen, die das Verhalten der Implementierung eines bestimmten berücksichtigen möchten, müssen Sie eine echte Datenbank wie SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="94bea-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="94bea-140">Zu diesem Zweck ist das Ausführen von SQL Server in einem Container eine gute Auswahl und genauer als die EF Core InMemory-Datenbankanbieter aus.</span><span class="sxs-lookup"><span data-stu-id="94bea-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="94bea-141">Verwenden einen Redis Cache-Dienst in einem container</span><span class="sxs-lookup"><span data-stu-id="94bea-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="94bea-142">Sie können Redis für einen Container, die speziell für die Entwicklung und Tests und Szenarien Proof of Concept ausführen.</span><span class="sxs-lookup"><span data-stu-id="94bea-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="94bea-143">Dieses Szenario eignet sich, da Sie alle Ihre Abhängigkeiten, die in Containern ausgeführt haben, können – nicht nur für Ihre lokalen Entwicklungscomputern, jedoch für Ihre testumgebungen in Pipelines CI-CD.</span><span class="sxs-lookup"><span data-stu-id="94bea-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="94bea-144">Beim Ausführen von Redis in der Produktion ist es jedoch besser, die für eine Lösung mit hoher Verfügbarkeit wie Microsoft Azure Redis suchen, die als eine PaaS (Platform als Dienst) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94bea-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="94bea-145">In Ihrem Code müssen Sie nur die Verbindungszeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="94bea-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="94bea-146">Redis bietet ein Docker Bild mit Redis.</span><span class="sxs-lookup"><span data-stu-id="94bea-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="94bea-147">Dieses Abbild ist von Docker Hub an folgender URL verfügbar:</span><span class="sxs-lookup"><span data-stu-id="94bea-147">That image is available from Docker Hub at this URL:</span></span>

<span data-ttu-id="94bea-148"><https://Hub.docker.com/_/redis/></span><span class="sxs-lookup"><span data-stu-id="94bea-148"><https://hub.docker.com/_/redis/></span></span>

<span data-ttu-id="94bea-149">Sie können einen Container mit Docker Redis direkt ausführen, durch den folgenden Docker-CLI-Befehl an der Eingabeaufforderung ausführen:</span><span class="sxs-lookup"><span data-stu-id="94bea-149">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```
  docker run --name some-redis -d redis
```

<span data-ttu-id="94bea-150">Die Redis-Image enthält verfügbar gemacht: 6379 (der Port, der von Redis verwendet wird), also standard Container verknüpfen wird automatisch zur Verfügung stellen die verknüpften Container verwendet.</span><span class="sxs-lookup"><span data-stu-id="94bea-150">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="94bea-151">In eShopOnContainers verwendet die basket.api Microservice einen Redis-Cache als Container ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="94bea-151">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="94bea-152">Basket.data Container wird als Teil der Datei mit mehreren Container Docker-compose.yml definiert, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="94bea-152">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="94bea-153">Dieser Code in der Docker-compose.yml definiert einen Container namens basket.data basierend auf Redis-Image und veröffentlichen den Port 6379 intern, was bedeutet, dass darauf zugreifen können nur von anderen Containern, die innerhalb des Docker-Hosts ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94bea-153">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="94bea-154">In der Docker-compose.override.yml-Datei definiert die basket.api Microservice für das Beispiel eShopOnContainers schließlich die Verbindungszeichenfolge, die für diesen Container Redis verwendet:</span><span class="sxs-lookup"><span data-stu-id="94bea-154">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
<span data-ttu-id="94bea-155">[Vorherigen] (multi-container-Anwendungen-Docker-compose.md) [weiter] (Integration-Ereignis-Basis-Microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="94bea-155">[Previous] (multi-container-applications-docker-compose.md) [Next] (integration-event-based-microservice-communications.md)</span></span>
