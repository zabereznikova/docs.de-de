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
# <a name="use-a-database-server-running-as-a-container"></a>Verwenden eines als Container ausgeführten Datenbankservers

Sie können Ihre Datenbanken (SQL Server, PostgreSQL, MySQL usw.) auf regulären eigenständigen Servern in lokalen Clustern oder in PaaS-Diensten in der Cloud verwenden wie etwa Azure SQL DB. Für Entwicklungs- und Testumgebungen ist jedoch die Ausführung Ihrer Datenbanken als Container praktisch, da keine externen Abhängigkeiten bestehen und die gesamte Anwendung einfach mit dem Befehl `docker-compose up` gestartet werden kann. Die Verwendung dieser Datenbanken als Container bietet sich zudem für Integrationstests an, da die Datenbanken im Container gestartet werden und immer mit denselben Beispieldaten aufgefüllt werden, sodass Tests besser vorhersehbar sind.

## <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server-Installation, die als Container mit einer microservicebezogenen Datenbank ausgeführt wird

In eShopOnContainers gibt es einen Container mit dem Namen `sqldata` (gemäß Definition in der Datei [docker-compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml)), in dem eine SQL Server für Linux-Instanz mit den SQL-Datenbanken für alle Microservices ausgeführt wird, die eine benötigen.

Ein wichtiger Punkt bei Microservices ist, dass jeder Microservice seine zugehörigen Daten besitzt und daher eine eigene Datenbank haben sollte. Die Datenbanken können sich jedoch an einem beliebigen Ort befinden. In diesem Fall befinden sie sich alle im selben Container, um den Arbeitsspeicherbedarf von Docker so gering wie möglich zu halten. Denken Sie daran, dass dies eine Lösung ist, die für die Entwicklung und vielleicht Tests geeignet ist, aber nicht für die Produktion.

Der SQL Server-Container in der Beispielanwendung wurde mit dem folgenden YAML-Code in der Datei „docker-compose.yml“ konfiguriert, die beim Ausführen des Befehls `docker-compose up` ausgeführt wird. Der YAML-Code enthält konsolidierte Konfigurationsinformationen aus den allgemeinen Dateien „docker-compose.yml“ und „docker-compose.override.yml“. (Normalerweise würden Sie die Umgebungseinstellungen von den Basisinformationen oder statischen Informationen zum SQL Server-Image trennen.)

```yml
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"
```

Auf ähnliche Weise können Sie anstelle von `docker-compose` den folgenden `docker run`-Befehl zum Ausführen dieses Containers verwenden:

```powershell
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Pass@word' -p 5433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
```

Wenn Sie jedoch eine Anwendung mit mehreren Containern wie eShopOnContainers bereitstellen, ist es praktischer, den Befehl `docker-compose up` zu verwenden, sodass alle für die Anwendung erforderlichen Container bereitgestellt werden.

Wenn Sie diesen SQL Server-Container zum ersten Mal starten, initialisiert der Container SQL Server mit dem von Ihnen angegebenen Kennwort. Sobald SQL Server als Container ausgeführt wird, können Sie die Datenbank aktualisieren, indem Sie eine normale SQL-Verbindung herstellen wie etwa über SQL Server Management Studio, Visual Studio oder C\#-Code.

Die Anwendung eShopOnContainers initialisiert die einzelnen Microservicedatenbanken mit Beispieldaten mittels Daten-Seeding beim Starten, wie im folgenden Abschnitt erläutert.

Die Ausführung von SQL Server als Container ist nicht nur für eine Demo nützlich, bei der Sie möglicherweise keinen Zugriff auf eine Instanz von SQL Server haben. Sie ist wie bereits erwähnt auch für Entwicklungs- und Testumgebungen nützlich, sodass Sie problemlos Integrationstests von einem sauberen SQL Server-Image aus mit bekannten Daten durch das Seeding neuer Beispieldaten ausführen können.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Ausführen des Docker-Images von SQL Serverunter Linux, Mac oder Windows** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker>

- **Verbinden und Abfragen von SQL Server unter Linux mit sqlcmd** \
  <https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd>

## <a name="seeding-with-test-data-on-web-application-startup"></a>Seeding mit Testdaten beim Starten von Webanwendungen

Um der Datenbank beim Starten der Anwendung Daten hinzuzufügen, können Sie der `Main`-Methode in der `Program`-Klasse des Web-API-Projekts Code wie den folgenden hinzufügen:

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

Es gibt einen wichtigen Vorbehalt beim Anwenden von Migrationen und Seeding einer Datenbank während des Containerstarts. Da der Datenbankserver möglicherweise aus beliebigen Gründen nicht verfügbar ist, müssen Wiederholungsversuche erfolgen, während Sie darauf warten, dass der Server verfügbar ist. Diese Wiederholungslogik wird von der Erweiterungsmethode `MigrateDbContext()` verarbeitet, wie der folgende Code zeigt:

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

Mit dem folgenden Code in der benutzerdefinierten CatalogContextSeed-Klasse werden die Daten aufgefüllt.

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

Beim Ausführen von Integrationstests ist es hilfreich, eine Methode zum Generieren von Daten zu verwenden, die den Integrationstests entsprechen. Besonders günstig für Testumgebungen ist es, wenn alles von Grund auf neu erstellt werden kann, so auch eine Instanz von SQL Server, die in einem Container ausgeführt wird.

## <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>EF Core-In-Memory Database und eine als Container ausgeführte SQL Server-Instanz im Vergleich

Eine weitere gute Möglichkeit zum Ausführen von Tests stellt der Entity Framework InMemory-Datenbankanbieter dar. Diese Konfiguration können Sie in der ConfigureServices-Methode der Startup-Klasse im Web-API-Projekt festlegen:

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

Diese Option hat jedoch einen Nachteil. Die In-Memory Database unterstützt nur eine begrenzte Anzahl von Einschränkungen für eine bestimmte Datenbank. Beispielsweise möchten Sie im EF Core-Modell einen eindeutigen Index hinzufügen und einen Test schreiben, um zu prüfen, ob das Hinzufügen von identischen Werten verhindert wird. Bei Verwendung einer In-Memory Database können jedoch keine eindeutigen Indizes in einer Spalte verarbeitet werden. Die In-Memory Database verhält sich somit etwas anders als eine echte SQL Server-Datenbank; sie emuliert keine datenbankspezifischen Einschränkungen.

Dennoch ist eine In-Memory Database zum Testen und zum Erstellen von Prototypen hilfreich. Wenn Sie jedoch präzise Integrationstests erstellen möchten, bei denen das Verhalten einer bestimmten Datenbankimplementierung berücksichtigt wird, müssen Sie eine echte Datenbank wie etwa SQL Server verwenden. In diesem Fall ist die Ausführung von SQL Server in einem Container eine gute und im Vergleich zum EF Core InMemory-Datenbankanbieter präzisere Option.

## <a name="using-a-redis-cache-service-running-in-a-container"></a>Verwenden eines Redis-Cachediensts, der in einem Container ausgeführt wird

Redis kann insbesondere bei der Entwicklung und beim Testen sowie im Rahmen von Proof-of-Concept-Szenarios in einem Container ausgeführt werden. Dieses Szenario ist praktisch, da alle Abhängigkeiten in Containern ausgeführt werden können – nicht nur für lokale Entwicklungscomputer, sondern auch für die Testumgebungen in den CI/CD-Pipelines.

Wenn Sie Redis jedoch in der Produktion ausführen, sollten Sie besser eine Lösung mit hoher Verfügbarkeit wie etwa Redis Microsoft Azure verwenden, die als PaaS (Platform as a Service) ausgeführt wird. Im Code müssen Sie hierzu lediglich die Verbindungszeichenfolgen ändern.

Redis stellt ein Docker-Image mit Redis bereit. Dieses Image ist im Docker-Hub unter der folgenden URL verfügbar:

<https://hub.docker.com/_/redis/>

Ein Docker Redis-Container kann durch Ausführen des folgenden Befehls der Docker-Befehlszeilenschnittstelle in der Eingabeaufforderung direkt ausgeführt werden:

```console
docker run --name some-redis -d redis
```

Das Redis-Image enthält „expose:6379“ (von Redis verwendeter Port), sodass es durch die übliche Containerverknüpfung für die verknüpften Container automatisch verfügbar wird.

In eShopOnContainers verwendet der Microservice `basket-api` einen als Container ausgeführten Redis-Cache. Dieser Container namens `basketdata` wird als Teil der Datei *docker-compose.yml* mit mehreren Containern definiert, wie das folgende Beispiel zeigt:

```yml
#docker-compose.yml file
#...
  basketdata:
    image: redis
    expose:
      - "6379"
```

Dieser Code in der Datei „docker-compose.yml“ definiert einen Container mit dem Namen `basketdata` basierend auf dem Redis-Image. Port 6379 wird intern veröffentlicht. Das bedeutet, dass nur andere Container, die im Docker-Host ausgeführt werden, darauf zugreifen können.

Und schließlich wird in der Datei *docker-compose.override.yml* im Microservice `basket-api` für das eShopOnContainers-Beispiel die für diesen Redis-Container zu verwendende Verbindungszeichenfolge definiert:

```yml
  basket-api:
    environment:
      # Other data ...
      - ConnectionString=basketdata
      - EventBusConnection=rabbitmq
```

Wie bereits erwähnt, wird der Name des Microservices `basketdata` durch das DNS des internen Netzwerks von Docker aufgelöst.

>[!div class="step-by-step"]
>[Zurück](multi-container-applications-docker-compose.md)
>[Weiter](integration-event-based-microservice-communications.md)
