---
title: Verwenden eines Datenbankservers, der als Container ausgeführt wird
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Verwenden eines als Container ausgeführten Datenbankservers nur für die Entwickelung Erfahren Sie den Grund.
ms.date: 10/02/2018
ms.openlocfilehash: 371d622dc39681edb0b52e723faccbf611b7797c
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568430"
---
# <a name="using-a-database-server-running-as-a-container"></a><span data-ttu-id="598f2-104">Verwenden eines Datenbankservers, der als Container ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="598f2-104">Using a database server running as a container</span></span>

<span data-ttu-id="598f2-105">Sie können Ihre Datenbanken (SQL Server, PostgreSQL, MySQL usw.) auf regulären eigenständigen Servern in lokalen Clustern oder in PaaS-Diensten in der Cloud verwenden wie etwa Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="598f2-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="598f2-106">Für Entwicklungs- und Testumgebungen ist jedoch die Ausführung der Datenbanken als Container praktisch, da keine externen Abhängigkeiten bestehen und die gesamte Anwendung einfach mit dem Befehl `docker-compose up` gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="598f2-106">However, for development and test environments, having your databases running as containers is convenient, because you do not have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="598f2-107">Die Verwendung dieser Datenbanken als Container bietet sich zudem für Integrationstests an, da die Datenbanken im Container gestartet werden und immer mit denselben Beispieldaten aufgefüllt werden, sodass Tests besser vorhersehbar sind.</span><span class="sxs-lookup"><span data-stu-id="598f2-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="598f2-108">SQL Server-Installation, die als Container mit einer microservicebezogenen Datenbank ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="598f2-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="598f2-109">In eShopOnContainers gibt es einen Container mit dem Namen „sql.data“, der in der Datei [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) definiert ist und mit dem SQL Server für Linux mit allen für Microservices benötigten SQL Server-Datenbanken ausführt wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-109">In eShopOnContainers, there is a container named sql.data defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file that runs SQL Server for Linux with all the SQL Server databases needed for the microservices.</span></span> <span data-ttu-id="598f2-110">(Sie können auch für jede Datenbank einen SQL Server-Container verwenden. Dann muss Docker jedoch mehr Speicherplatz zugewiesen werden.) Der entscheidende Punkt bei Microservices ist, dass jeder Microservice die ihm gehörenden Daten und damit die ihm gehörende SQL-Datenbank besitzt.</span><span class="sxs-lookup"><span data-stu-id="598f2-110">(You could also have one SQL Server container for each database, but that would require more memory assigned to Docker.) The important point in microservices is that each microservice owns its related data, therefore its related SQL database in this case.</span></span> <span data-ttu-id="598f2-111">Die Datenbanken können sich jedoch an einem beliebigen Ort befinden.</span><span class="sxs-lookup"><span data-stu-id="598f2-111">But the databases can be anywhere.</span></span>

<span data-ttu-id="598f2-112">Der SQL Server-Container in der Beispielanwendung wurde mit dem folgenden YAML-Code in der Datei „docker-compose.yml“ konfiguriert, die beim Ausführen des Befehls `docker-compose up` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-112">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="598f2-113">Der YAML-Code enthält konsolidierte Konfigurationsinformationen aus den allgemeinen Dateien „docker-compose.yml“ und „docker-compose.override.yml“.</span><span class="sxs-lookup"><span data-stu-id="598f2-113">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="598f2-114">(Normalerweise würden Sie die Umgebungseinstellungen von den Basisinformationen oder statischen Informationen zum SQL Server-Image trennen.)</span><span class="sxs-lookup"><span data-stu-id="598f2-114">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sql.data:
    image: microsoft/mssql-server-linux:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="598f2-115">Auf ähnliche Weise können Sie anstelle von `docker-compose` den folgenden `docker run`-Befehl zum Ausführen dieses Containers verwenden:</span><span class="sxs-lookup"><span data-stu-id="598f2-115">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```console
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d microsoft/mssql-server-linux:2017-latest
```

<span data-ttu-id="598f2-116">Wenn Sie jedoch eine Anwendung mit mehreren Containern wie eShopOnContainers bereitstellen, ist es praktischer, den Befehl `docker-compose up` zu verwenden, sodass alle für die Anwendung erforderlichen Container bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="598f2-116">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="598f2-117">Wenn Sie diesen SQL Server-Container zum ersten Mal starten, initialisiert der Container SQL Server mit dem von Ihnen angegebenen Kennwort.</span><span class="sxs-lookup"><span data-stu-id="598f2-117">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="598f2-118">Sobald SQL Server als Container ausgeführt wird, können Sie die Datenbank aktualisieren, indem Sie eine normale SQL-Verbindung herstellen wie etwa über SQL Server Management Studio, Visual Studio oder C\#-Code.</span><span class="sxs-lookup"><span data-stu-id="598f2-118">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="598f2-119">Die Anwendung eShopOnContainers initialisiert die einzelnen Microservicedatenbanken mit Beispieldaten mittels Daten-Seeding beim Starten, wie im folgenden Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="598f2-119">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="598f2-120">Die Ausführung von SQL Server als Container ist nicht nur für eine Demo nützlich, bei der Sie möglicherweise keinen Zugriff auf eine Instanz von SQL Server haben.</span><span class="sxs-lookup"><span data-stu-id="598f2-120">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="598f2-121">Sie ist wie bereits erwähnt auch für Entwicklungs- und Testumgebungen nützlich, sodass Sie problemlos Integrationstests von einem sauberen SQL Server-Image aus mit bekannten Daten durch das Seeding neuer Beispieldaten ausführen können.</span><span class="sxs-lookup"><span data-stu-id="598f2-121">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="598f2-122">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="598f2-122">Additional resources</span></span>

- <span data-ttu-id="598f2-123">**Ausführen des Docker-Images von SQL Server unter Linux, Mac oder Windows** </span><span class="sxs-lookup"><span data-stu-id="598f2-123">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker](/sql/linux/sql-server-linux-setup-docker)

- <span data-ttu-id="598f2-124">**Verbinden und Abfragen von SQL Server unter Linux mit sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="598f2-124">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
    [https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd](/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="598f2-125">Seeding mit Testdaten beim Starten von Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="598f2-125">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="598f2-126">Um der Datenbank beim Starten der Anwendung Daten hinzuzufügen, können Sie der Configure-Methode in der Startup-Klasse des Web-API-Projekts Code wie den folgenden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="598f2-126">To add data to the database when the application starts up, you can add code like the following to the Configure method in the Startup class of the Web API project:</span></span>

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

<span data-ttu-id="598f2-127">Mit dem folgenden Code in der benutzerdefinierten CatalogContextSeed-Klasse werden die Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="598f2-127">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="598f2-128">Beim Ausführen von Integrationstests ist es hilfreich, eine Methode zum Generieren von Daten zu verwenden, die den Integrationstests entsprechen.</span><span class="sxs-lookup"><span data-stu-id="598f2-128">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="598f2-129">Besonders günstig für Testumgebungen ist es, wenn alles von Grund auf neu erstellt werden kann, so auch eine Instanz von SQL Server, die in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-129">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="598f2-130">EF Core-In-Memory Database und eine als Container ausgeführte SQL Server-Instanz im Vergleich</span><span class="sxs-lookup"><span data-stu-id="598f2-130">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="598f2-131">Eine weitere gute Möglichkeit zum Ausführen von Tests stellt der Entity Framework InMemory-Datenbankanbieter dar.</span><span class="sxs-lookup"><span data-stu-id="598f2-131">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="598f2-132">Diese Konfiguration können Sie in der ConfigureServices-Methode der Startup-Klasse im Web-API-Projekt festlegen:</span><span class="sxs-lookup"><span data-stu-id="598f2-132">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="598f2-133">Diese Option hat jedoch einen Nachteil.</span><span class="sxs-lookup"><span data-stu-id="598f2-133">There is an important catch, though.</span></span> <span data-ttu-id="598f2-134">Die In-Memory Database unterstützt nur eine begrenzte Anzahl von Einschränkungen für eine bestimmte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="598f2-134">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="598f2-135">Beispielsweise möchten Sie im EF Core-Modell einen eindeutigen Index hinzufügen und einen Test schreiben, um zu prüfen, ob das Hinzufügen von identischen Werten verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-135">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="598f2-136">Bei Verwendung einer In-Memory Database können jedoch keine eindeutigen Indizes in einer Spalte verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="598f2-136">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="598f2-137">Die In-Memory Database verhält sich somit etwas anders als eine echte SQL Server-Datenbank; sie emuliert keine datenbankspezifischen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="598f2-137">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="598f2-138">Dennoch ist eine In-Memory Database zum Testen und zum Erstellen von Prototypen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="598f2-138">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="598f2-139">Wenn Sie jedoch präzise Integrationstests erstellen möchten, bei denen das Verhalten einer bestimmten Datenbankimplementierung berücksichtigt wird, müssen Sie eine echte Datenbank wie etwa SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="598f2-139">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="598f2-140">In diesem Fall ist die Ausführung von SQL Server in einem Container eine gute und im Vergleich zum EF Core InMemory-Datenbankanbieter präzisere Option.</span><span class="sxs-lookup"><span data-stu-id="598f2-140">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

### <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="598f2-141">Verwenden eines Redis-Cachediensts, der in einem Container ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="598f2-141">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="598f2-142">Redis kann insbesondere bei der Entwicklung und beim Testen sowie im Rahmen von Proof-of-Concept-Szenarios in einem Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="598f2-142">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="598f2-143">Dieses Szenario ist praktisch, da alle Abhängigkeiten in Containern ausgeführt werden können – nicht nur für lokale Entwicklungscomputer, sondern auch für die Testumgebungen in den CI/CD-Pipelines.</span><span class="sxs-lookup"><span data-stu-id="598f2-143">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="598f2-144">Wenn Sie Redis jedoch in der Produktion ausführen, sollten Sie besser eine Lösung mit hoher Verfügbarkeit wie etwa Redis Microsoft Azure verwenden, die als PaaS (Platform as a Service) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-144">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="598f2-145">Im Code müssen Sie hierzu lediglich die Verbindungszeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="598f2-145">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="598f2-146">Redis stellt ein Docker-Image mit Redis bereit.</span><span class="sxs-lookup"><span data-stu-id="598f2-146">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="598f2-147">Dieses Image ist im Docker-Hub unter der folgenden URL verfügbar:</span><span class="sxs-lookup"><span data-stu-id="598f2-147">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/_/redis/>

<span data-ttu-id="598f2-148">Ein Docker Redis-Container kann durch Ausführen des folgenden Befehls der Docker-Befehlszeilenschnittstelle in der Eingabeaufforderung direkt ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="598f2-148">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
docker run --name some-redis -d redis
```

<span data-ttu-id="598f2-149">Das Redis-Image enthält „expose:6379“ (von Redis verwendeter Port), sodass es durch die übliche Containerverknüpfung für die verknüpften Container automatisch verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="598f2-149">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="598f2-150">In eShopOnContainers verwendet der Microservice „basket.api“ einen als Container ausgeführten Redis-Cache.</span><span class="sxs-lookup"><span data-stu-id="598f2-150">In eShopOnContainers, the basket.api microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="598f2-151">Dieser „basket.data“-Container wird im Rahmen der Datei „docker-compose.yml“ mit mehreren Containern definiert, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="598f2-151">That basket.data container is defined as part of the multi-container docker-compose.yml file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="598f2-152">Dieser Code in der Datei „docker-compose.yml“ definiert einen Container mit dem Namen „basket.data“ basierend auf dem Redis-Image, und Port 6379 wird intern veröffentlicht, sodass nur andere Container, die im Docker-Host ausgeführt werden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="598f2-152">This code in the docker-compose.yml defines a container named basket.data based on the redis image and publishing the port 6379 internally, meaning that it will be accessible only from other containers running within the Docker host.</span></span>

<span data-ttu-id="598f2-153">Und schließlich wird in der Datei „docker-compose.override.yml“ im Microservice „basket.api“ für das eShopOnContainers-Beispiel die für diesen Redis-Container zu verwendende Verbindungszeichenfolge definiert:</span><span class="sxs-lookup"><span data-stu-id="598f2-153">Finally, in the docker-compose.override.yml file, the basket.api microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="598f2-154">Wie bereits erwähnt, wird der Name des Microservices „basket.data“ durch das DNS des internen Netzwerks von Docker aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="598f2-154">As mentioned before, the name of the microservice "basket.data" is resolved by docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="598f2-155">[Zurück](multi-container-applications-docker-compose.md)
>[Weiter](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="598f2-155">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
