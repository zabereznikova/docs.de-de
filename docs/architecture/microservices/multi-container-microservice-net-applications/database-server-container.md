---
title: Verwenden eines als Container ausgeführten Datenbankservers
description: Informationen zur Bedeutung der Verwendung eines als Container ausgeführten Datenbankservers, der ausschließlich für die Entwicklung, jedoch auf keinen Fall in der Produktion zum Einsatz kommen darf
ms.date: 01/30/2020
ms.openlocfilehash: 0cbc933003aac10970814378c27e88b5cb0ddbe5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628526"
---
# <a name="use-a-database-server-running-as-a-container"></a><span data-ttu-id="0b548-104">Verwenden eines als Container ausgeführten Datenbankservers</span><span class="sxs-lookup"><span data-stu-id="0b548-104">Use a database server running as a container</span></span>

<span data-ttu-id="0b548-105">Sie können Ihre Datenbanken (SQL Server, PostgreSQL, MySQL usw.) auf regulären eigenständigen Servern in lokalen Clustern oder in PaaS-Diensten in der Cloud verwenden wie etwa Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="0b548-105">You can have your databases (SQL Server, PostgreSQL, MySQL, etc.) on regular standalone servers, in on-premises clusters, or in PaaS services in the cloud like Azure SQL DB.</span></span> <span data-ttu-id="0b548-106">Für Entwicklungs- und Testumgebungen ist jedoch die Ausführung Ihrer Datenbanken als Container praktisch, da keine externen Abhängigkeiten bestehen und die gesamte Anwendung einfach mit dem Befehl `docker-compose up` gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b548-106">However, for development and test environments, having your databases running as containers is convenient, because you don't have any external dependency and simply running the `docker-compose up` command starts the whole application.</span></span> <span data-ttu-id="0b548-107">Die Verwendung dieser Datenbanken als Container bietet sich zudem für Integrationstests an, da die Datenbanken im Container gestartet werden und immer mit denselben Beispieldaten aufgefüllt werden, sodass Tests besser vorhersehbar sind.</span><span class="sxs-lookup"><span data-stu-id="0b548-107">Having those databases as containers is also great for integration tests, because the database is started in the container and is always populated with the same sample data, so tests can be more predictable.</span></span>

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a><span data-ttu-id="0b548-108">SQL Server-Installation, die als Container mit einer microservicebezogenen Datenbank ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0b548-108">SQL Server running as a container with a microservice-related database</span></span>

<span data-ttu-id="0b548-109">In eShopOnContainers gibt es einen Container mit dem Namen `sqldata` (gemäß Definition in der Datei [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml)), in dem eine SQL Server für Linux-Instanz mit den SQL-Datenbanken für alle Microservices ausgeführt wird, die eine benötigen.</span><span class="sxs-lookup"><span data-stu-id="0b548-109">In eShopOnContainers, there's a container named `sqldata`, as defined in the [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) file, that runs a SQL Server for Linux instance with the SQL databases for all microservices that need one.</span></span>

<span data-ttu-id="0b548-110">Ein wichtiger Punkt bei Microservices ist, dass jeder Microservice seine zugehörigen Daten besitzt und daher eine eigene Datenbank haben sollte.</span><span class="sxs-lookup"><span data-stu-id="0b548-110">A key point in microservices is that each microservice owns its related data, so it should have its own database.</span></span> <span data-ttu-id="0b548-111">Die Datenbanken können sich jedoch an einem beliebigen Ort befinden.</span><span class="sxs-lookup"><span data-stu-id="0b548-111">However, the databases can be anywhere.</span></span> <span data-ttu-id="0b548-112">In diesem Fall befinden sie sich alle im selben Container, um den Arbeitsspeicherbedarf von Docker so gering wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="0b548-112">In this case, they are all in the same container to keep Docker memory requirements as low as possible.</span></span> <span data-ttu-id="0b548-113">Denken Sie daran, dass dies eine Lösung ist, die für die Entwicklung und vielleicht Tests geeignet ist, aber nicht für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="0b548-113">Keep in mind that this is a good-enough solution for development and, perhaps, testing but not for production.</span></span>

<span data-ttu-id="0b548-114">Der SQL Server-Container in der Beispielanwendung wurde mit dem folgenden YAML-Code in der Datei „docker-compose.yml“ konfiguriert, die beim Ausführen des Befehls `docker-compose up` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b548-114">The SQL Server container in the sample application is configured with the following YAML code in the docker-compose.yml file, which is executed when you run `docker-compose up`.</span></span> <span data-ttu-id="0b548-115">Der YAML-Code enthält konsolidierte Konfigurationsinformationen aus den allgemeinen Dateien „docker-compose.yml“ und „docker-compose.override.yml“.</span><span class="sxs-lookup"><span data-stu-id="0b548-115">Note that the YAML code has consolidated configuration information from the generic docker-compose.yml file and the docker-compose.override.yml file.</span></span> <span data-ttu-id="0b548-116">(Normalerweise würden Sie die Umgebungseinstellungen von den Basisinformationen oder statischen Informationen zum SQL Server-Image trennen.)</span><span class="sxs-lookup"><span data-stu-id="0b548-116">(Usually you would separate the environment settings from the base or static information related to the SQL Server image.)</span></span>

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

<span data-ttu-id="0b548-117">Auf ähnliche Weise können Sie anstelle von `docker-compose` den folgenden `docker run`-Befehl zum Ausführen dieses Containers verwenden:</span><span class="sxs-lookup"><span data-stu-id="0b548-117">In a similar way, instead of using `docker-compose`, the following `docker run` command can run that container:</span></span>

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

<span data-ttu-id="0b548-118">Wenn Sie jedoch eine Anwendung mit mehreren Containern wie eShopOnContainers bereitstellen, ist es praktischer, den Befehl `docker-compose up` zu verwenden, sodass alle für die Anwendung erforderlichen Container bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b548-118">However, if you are deploying a multi-container application like eShopOnContainers, it is more convenient to use the `docker-compose up` command so that it deploys all the required containers for the application.</span></span>

<span data-ttu-id="0b548-119">Wenn Sie diesen SQL Server-Container zum ersten Mal starten, initialisiert der Container SQL Server mit dem von Ihnen angegebenen Kennwort.</span><span class="sxs-lookup"><span data-stu-id="0b548-119">When you start this SQL Server container for the first time, the container initializes SQL Server with the password that you provide.</span></span> <span data-ttu-id="0b548-120">Sobald SQL Server als Container ausgeführt wird, können Sie die Datenbank aktualisieren, indem Sie eine normale SQL-Verbindung herstellen wie etwa über SQL Server Management Studio, Visual Studio oder C\#-Code.</span><span class="sxs-lookup"><span data-stu-id="0b548-120">Once SQL Server is running as a container, you can update the database by connecting through any regular SQL connection, such as from SQL Server Management Studio, Visual Studio, or C\# code.</span></span>

<span data-ttu-id="0b548-121">Die Anwendung eShopOnContainers initialisiert die einzelnen Microservicedatenbanken mit Beispieldaten mittels Daten-Seeding beim Starten, wie im folgenden Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="0b548-121">The eShopOnContainers application initializes each microservice database with sample data by seeding it with data on startup, as explained in the following section.</span></span>

<span data-ttu-id="0b548-122">Die Ausführung von SQL Server als Container ist nicht nur für eine Demo nützlich, bei der Sie möglicherweise keinen Zugriff auf eine Instanz von SQL Server haben.</span><span class="sxs-lookup"><span data-stu-id="0b548-122">Having SQL Server running as a container is not just useful for a demo where you might not have access to an instance of SQL Server.</span></span> <span data-ttu-id="0b548-123">Sie ist wie bereits erwähnt auch für Entwicklungs- und Testumgebungen nützlich, sodass Sie problemlos Integrationstests von einem sauberen SQL Server-Image aus mit bekannten Daten durch das Seeding neuer Beispieldaten ausführen können.</span><span class="sxs-lookup"><span data-stu-id="0b548-123">As noted, it is also great for development and testing environments so that you can easily run integration tests starting from a clean SQL Server image and known data by seeding new sample data.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0b548-124">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0b548-124">Additional resources</span></span>

- <span data-ttu-id="0b548-125">**Ausführen des Docker-Images von SQL Serverunter Linux, Mac oder Windows** </span><span class="sxs-lookup"><span data-stu-id="0b548-125">**Run the SQL Server Docker image on Linux, Mac, or Windows** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- <span data-ttu-id="0b548-126">**Verbinden und Abfragen von SQL Server unter Linux mit sqlcmd** </span><span class="sxs-lookup"><span data-stu-id="0b548-126">**Connect and query SQL Server on Linux with sqlcmd** </span></span>\
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a><span data-ttu-id="0b548-127">Seeding mit Testdaten beim Starten von Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="0b548-127">Seeding with test data on Web application startup</span></span>

<span data-ttu-id="0b548-128">Um der Datenbank beim Starten der Anwendung Daten hinzuzufügen, können Sie der `Main`-Methode in der `Program`-Klasse des Web-API-Projekts Code wie den folgenden hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0b548-128">To add data to the database when the application starts up, you can add code like the following to the `Main` method in the `Program` class of the Web API project:</span></span>

```csharp
public static int Main(string[] args)
{
    var configuration = GetConfiguration();

    Log.Logger = CreateSerilogLogger(configuration);

    try
    {
        Log.Information("Configuring web host ({ApplicationContext})...", AppName);
        var host = CreateHostBuilder(configuration, args);

        Log.Information("Applying migrations ({ApplicationContext})...", AppName);
        host.MigrateDbContext<CatalogContext>((context, services) =>
        {
            var env = services.GetService<IWebHostEnvironment>();
            var settings = services.GetService<IOptions<CatalogSettings>>();
            var logger = services.GetService<ILogger<CatalogContextSeed>>();

            new CatalogContextSeed()
                .SeedAsync(context, env, settings, logger)
                .Wait();
        })
        .MigrateDbContext<IntegrationEventLogContext>((_, __) => { });

        Log.Information("Starting web host ({ApplicationContext})...", AppName);
        host.Run();

        return 0;
    }
    catch (Exception ex)
    {
        Log.Fatal(ex, "Program terminated unexpectedly ({ApplicationContext})!", AppName);
        return 1;
    }
    finally
    {
        Log.CloseAndFlush();
    }
}
```

<span data-ttu-id="0b548-129">Es gibt einen wichtigen Vorbehalt beim Anwenden von Migrationen und Seeding einer Datenbank während des Containerstarts.</span><span class="sxs-lookup"><span data-stu-id="0b548-129">There's an important caveat when applying migrations and seeding a database during container startup.</span></span> <span data-ttu-id="0b548-130">Da der Datenbankserver möglicherweise aus beliebigen Gründen nicht verfügbar ist, müssen Wiederholungsversuche erfolgen, während Sie darauf warten, dass der Server verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b548-130">Since the database server might not be available for whatever reason, you must handle retries while waiting for the server to be available.</span></span> <span data-ttu-id="0b548-131">Diese Wiederholungslogik wird von der Erweiterungsmethode `MigrateDbContext()` verarbeitet, wie der folgende Code zeigt:</span><span class="sxs-lookup"><span data-stu-id="0b548-131">This retry logic is handled by the `MigrateDbContext()` extension method, as shown in the following code:</span></span>

```cs
public static IWebHost MigrateDbContext<TContext>(
    this IWebHost host,
    Action<TContext,
    IServiceProvider> seeder)
      where TContext : DbContext
{
    var underK8s = host.IsInKubernetes();

    using (var scope = host.Services.CreateScope())
    {
        var services = scope.ServiceProvider;

        var logger = services.GetRequiredService<ILogger<TContext>>();

        var context = services.GetService<TContext>();

        try
        {
            logger.LogInformation("Migrating database associated with context {DbContextName}", typeof(TContext).Name);

            if (underK8s)
            {
                InvokeSeeder(seeder, context, services);
            }
            else
            {
                var retry = Policy.Handle<SqlException>()
                    .WaitAndRetry(new TimeSpan[]
                    {
                    TimeSpan.FromSeconds(3),
                    TimeSpan.FromSeconds(5),
                    TimeSpan.FromSeconds(8),
                    });

                //if the sql server container is not created on run docker compose this
                //migration can't fail for network related exception. The retry options for DbContext only
                //apply to transient exceptions
                // Note that this is NOT applied when running some orchestrators (let the orchestrator to recreate the failing service)
                retry.Execute(() => InvokeSeeder(seeder, context, services));
            }

            logger.LogInformation("Migrated database associated with context {DbContextName}", typeof(TContext).Name);
        }
        catch (Exception ex)
        {
            logger.LogError(ex, "An error occurred while migrating the database used on context {DbContextName}", typeof(TContext).Name);
            if (underK8s)
            {
                throw;          // Rethrow under k8s because we rely on k8s to re-run the pod
            }
        }
    }

    return host;
}
```

<span data-ttu-id="0b548-132">Mit dem folgenden Code in der benutzerdefinierten CatalogContextSeed-Klasse werden die Daten aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0b548-132">The following code in the custom CatalogContextSeed class populates the data.</span></span>

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

<span data-ttu-id="0b548-133">Beim Ausführen von Integrationstests ist es hilfreich, eine Methode zum Generieren von Daten zu verwenden, die den Integrationstests entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0b548-133">When you run integration tests, having a way to generate data consistent with your integration tests is useful.</span></span> <span data-ttu-id="0b548-134">Besonders günstig für Testumgebungen ist es, wenn alles von Grund auf neu erstellt werden kann, so auch eine Instanz von SQL Server, die in einem Container ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b548-134">Being able to create everything from scratch, including an instance of SQL Server running on a container, is great for test environments.</span></span>

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a><span data-ttu-id="0b548-135">EF Core-In-Memory Database und eine als Container ausgeführte SQL Server-Instanz im Vergleich</span><span class="sxs-lookup"><span data-stu-id="0b548-135">EF Core InMemory database versus SQL Server running as a container</span></span>

<span data-ttu-id="0b548-136">Eine weitere gute Möglichkeit zum Ausführen von Tests stellt der Entity Framework InMemory-Datenbankanbieter dar.</span><span class="sxs-lookup"><span data-stu-id="0b548-136">Another good choice when running tests is to use the Entity Framework InMemory database provider.</span></span> <span data-ttu-id="0b548-137">Diese Konfiguration können Sie in der ConfigureServices-Methode der Startup-Klasse im Web-API-Projekt festlegen:</span><span class="sxs-lookup"><span data-stu-id="0b548-137">You can specify that configuration in the ConfigureServices method of the Startup class in your Web API project:</span></span>

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

<span data-ttu-id="0b548-138">Diese Option hat jedoch einen Nachteil.</span><span class="sxs-lookup"><span data-stu-id="0b548-138">There is an important catch, though.</span></span> <span data-ttu-id="0b548-139">Die In-Memory Database unterstützt nur eine begrenzte Anzahl von Einschränkungen für eine bestimmte Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0b548-139">The in-memory database does not support many constraints that are specific to a particular database.</span></span> <span data-ttu-id="0b548-140">Beispielsweise möchten Sie im EF Core-Modell einen eindeutigen Index hinzufügen und einen Test schreiben, um zu prüfen, ob das Hinzufügen von identischen Werten verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="0b548-140">For instance, you might add a unique index on a column in your EF Core model and write a test against your in-memory database to check that it does not let you add a duplicate value.</span></span> <span data-ttu-id="0b548-141">Bei Verwendung einer In-Memory Database können jedoch keine eindeutigen Indizes in einer Spalte verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0b548-141">But when you are using the in-memory database, you cannot handle unique indexes on a column.</span></span> <span data-ttu-id="0b548-142">Die In-Memory Database verhält sich somit etwas anders als eine echte SQL Server-Datenbank; sie emuliert keine datenbankspezifischen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="0b548-142">Therefore, the in-memory database does not behave exactly the same as a real SQL Server database—it does not emulate database-specific constraints.</span></span>

<span data-ttu-id="0b548-143">Dennoch ist eine In-Memory Database zum Testen und zum Erstellen von Prototypen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="0b548-143">Even so, an in-memory database is still useful for testing and prototyping.</span></span> <span data-ttu-id="0b548-144">Wenn Sie jedoch präzise Integrationstests erstellen möchten, bei denen das Verhalten einer bestimmten Datenbankimplementierung berücksichtigt wird, müssen Sie eine echte Datenbank wie etwa SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b548-144">But if you want to create accurate integration tests that take into account the behavior of a specific database implementation, you need to use a real database like SQL Server.</span></span> <span data-ttu-id="0b548-145">In diesem Fall ist die Ausführung von SQL Server in einem Container eine gute und im Vergleich zum EF Core InMemory-Datenbankanbieter präzisere Option.</span><span class="sxs-lookup"><span data-stu-id="0b548-145">For that purpose, running SQL Server in a container is a great choice and more accurate than the EF Core InMemory database provider.</span></span>

## <a name="using-a-redis-cache-service-running-in-a-container"></a><span data-ttu-id="0b548-146">Verwenden eines Redis-Cachediensts, der in einem Container ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0b548-146">Using a Redis cache service running in a container</span></span>

<span data-ttu-id="0b548-147">Redis kann insbesondere bei der Entwicklung und beim Testen sowie im Rahmen von Proof-of-Concept-Szenarios in einem Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0b548-147">You can run Redis on a container, especially for development and testing and for proof-of-concept scenarios.</span></span> <span data-ttu-id="0b548-148">Dieses Szenario ist praktisch, da alle Abhängigkeiten in Containern ausgeführt werden können – nicht nur für lokale Entwicklungscomputer, sondern auch für die Testumgebungen in den CI/CD-Pipelines.</span><span class="sxs-lookup"><span data-stu-id="0b548-148">This scenario is convenient, because you can have all your dependencies running on containers—not just for your local development machines, but for your testing environments in your CI/CD pipelines.</span></span>

<span data-ttu-id="0b548-149">Wenn Sie Redis jedoch in der Produktion ausführen, sollten Sie besser eine Lösung mit hoher Verfügbarkeit wie etwa Redis Microsoft Azure verwenden, die als PaaS (Platform as a Service) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b548-149">However, when you run Redis in production, it is better to look for a high-availability solution like Redis Microsoft Azure, which runs as a PaaS (Platform as a Service).</span></span> <span data-ttu-id="0b548-150">Im Code müssen Sie hierzu lediglich die Verbindungszeichenfolgen ändern.</span><span class="sxs-lookup"><span data-stu-id="0b548-150">In your code, you just need to change your connection strings.</span></span>

<span data-ttu-id="0b548-151">Redis stellt ein Docker-Image mit Redis bereit.</span><span class="sxs-lookup"><span data-stu-id="0b548-151">Redis provides a Docker image with Redis.</span></span> <span data-ttu-id="0b548-152">Dieses Image ist im Docker-Hub unter der folgenden URL verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0b548-152">That image is available from Docker Hub at this URL:</span></span>

<https://hub.docker.com/_/redis/>

<span data-ttu-id="0b548-153">Ein Docker Redis-Container kann durch Ausführen des folgenden Befehls der Docker-Befehlszeilenschnittstelle in der Eingabeaufforderung direkt ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="0b548-153">You can directly run a Docker Redis container by executing the following Docker CLI command in your command prompt:</span></span>

```console
docker run --name some-redis -d redis
```

<span data-ttu-id="0b548-154">Das Redis-Image enthält „expose:6379“ (von Redis verwendeter Port), sodass es durch die übliche Containerverknüpfung für die verknüpften Container automatisch verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="0b548-154">The Redis image includes expose:6379 (the port used by Redis), so standard container linking will make it automatically available to the linked containers.</span></span>

<span data-ttu-id="0b548-155">In eShopOnContainers verwendet der Microservice `basket-api` einen als Container ausgeführten Redis-Cache.</span><span class="sxs-lookup"><span data-stu-id="0b548-155">In eShopOnContainers, the `basket-api` microservice uses a Redis cache running as a container.</span></span> <span data-ttu-id="0b548-156">Dieser Container namens `basketdata` wird als Teil der Datei *docker-compose.yml* mit mehreren Containern definiert, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="0b548-156">That `basketdata` container is defined as part of the multi-container *docker-compose.yml* file, as shown in the following example:</span></span>

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

<span data-ttu-id="0b548-157">Dieser Code in der Datei „docker-compose.yml“ definiert einen Container mit dem Namen `basketdata` basierend auf dem Redis-Image. Port 6379 wird intern veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="0b548-157">This code in the docker-compose.yml defines a container named `basketdata` based on the redis image and publishing the port 6379 internally.</span></span> <span data-ttu-id="0b548-158">Das bedeutet, dass nur andere Container, die im Docker-Host ausgeführt werden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0b548-158">This means that it will only be accessible from other containers running within the Docker host.</span></span>

<span data-ttu-id="0b548-159">Und schließlich wird in der Datei *docker-compose.override.yml* im Microservice `basket-api` für das eShopOnContainers-Beispiel die für diesen Redis-Container zu verwendende Verbindungszeichenfolge definiert:</span><span class="sxs-lookup"><span data-stu-id="0b548-159">Finally, in the *docker-compose.override.yml* file, the `basket-api` microservice for the eShopOnContainers sample defines the connection string to use for that Redis container:</span></span>

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

<span data-ttu-id="0b548-160">Wie bereits erwähnt, wird der Name des Microservices `basketdata` durch das DNS des internen Netzwerks von Docker aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="0b548-160">As mentioned before, the name of the microservice `basketdata` is resolved by Docker's internal network DNS.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0b548-161">[Zurück](multi-container-applications-docker-compose.md)
>[Weiter](integration-event-based-microservice-communications.md)</span><span class="sxs-lookup"><span data-stu-id="0b548-161">[Previous](multi-container-applications-docker-compose.md)
[Next](integration-event-based-microservice-communications.md)</span></span>
