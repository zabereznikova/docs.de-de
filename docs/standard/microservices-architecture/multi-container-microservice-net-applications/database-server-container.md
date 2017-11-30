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
# <a name="using-a-database-server-running-as-a-container"></a>Verwenden einen Datenbankserver, die als container

Sie können Ihre Datenbanken (SQL Server, PostgreSQL, MySQL usw.) auf reguläre eigenständigen Servern in lokalen Clustern und in PaaS-Dienste in der Cloud wie Azure SQL-Datenbank verwenden. Allerdings für Entwicklungs- und testumgebungen, müssen die Datenbanken, die als Container ausgeführt ist es bequem erscheint, da Sie keine externe Abhängigkeit und einfach ausgeführt wird der Docker-verfassen Befehl wird die gesamte Anwendung gestartet. Diese Datenbanken als Container ist auch hervorragend für die Integrationstests erfolgreich, da die Datenbank im Container gestartet wird und wird immer mit den gleichen Beispieldaten aufgefüllt, damit Tests besser vorhersagbar sein können.

### <a name="sql-server-running-as-a-container-with-a-microservice-related-database"></a>SQL Server, die als Container ausgeführt werden, mit einer Datenbank Microservice bezogene

In eShopOnContainers, ist ein Container mit dem Namen sql.data definiert, der [Docker compose.yml](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/docker-compose.yml) -Datei, die SQL Server für Linux mit allen SQL Server-Datenbanken, die erforderlich sind, für die Microservices ausgeführt wird. (Sie möglicherweise auch eine SQL Server-Container für jede Datenbank, aber wäre es erforderlich, mehr Arbeitsspeicher Docker zugewiesen.) Der wichtige Punkt im Microservices ist, dass jede Microservice ihre verknüpften Daten aus diesem Grund seine zugehörige SQL-Datenbank in diesem Fall besitzt. Die Datenbanken können jedoch eine beliebige Stelle.

Container in der beispielanwendung durch folgenden Code in der Datei Docker compose.yml YAML konfiguriert ist, die ausgeführt wird, beim Ausführen von SQL-Server bilden Docker-einrichten. Beachten Sie, dass der Code YAML Konfigurationsinformationen aus dem generischen Docker-compose.yml-Datei und die Docker-compose.override.yml konsolidiert hat. (In der Regel würden Sie die umgebungseinstellungen aus der Basistabelle oder statische Informationen, die im Zusammenhang mit SQL Server-Images trennen.)

```yml
sql.data:
  image: microsoft/mssql-server-linux
  environment:
    - SA_PASSWORD=your@password
    - ACCEPT_EULA=Y
  ports:
    - "5434:1433"
```

Die folgenden "Docker run" Befehl kann diesen Container ausgeführt werden:

```
  docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD= your@password' -p 1433:1433 -d microsoft/mssql-server-linux
```

Wenn Sie eine Anwendung mit mehreren Container wie eShopOnContainers bereitstellen, es ist jedoch einfacher, verwenden Sie den Docker-verfassen Befehl, in dem sie alle erforderlichen Container für die Anwendung bereitgestellt.

Wenn Sie dieser SQL Server-Container zum ersten Mal starten, initialisiert der Container SQL Server mit dem Kennwort, das Sie bereitstellen. Wenn SQL Server als Container ausgeführt wird, können Sie die Datenbank aktualisieren, indem Herstellen einer Verbindung über eine reguläre SQL-Verbindung, z. B. von SQL Server Management Studio oder Visual Studio mit C#\# Code.

Die eShopOnContainers-Anwendung initialisiert jeder Microservice-Datenbank mit Beispieldaten seeding mit den Daten zu starten, wie im folgenden Abschnitt erläutert.

Mit SQL Server ausgeführt wird, als Container eignet sich nicht nur für die Demo möglicherweise Zugriff auf eine Instanz von SQL Server muss nicht. Wie bereits erwähnt ist es auch hervorragend für Entwicklungs- und testumgebungen, sodass können Sie problemlos Integrationstests beginnend mit einem sauberen Image von SQL Server ausführen und Daten von neuen Beispieldaten seeding bezeichnet.

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Führen Sie das Image von SQL Server-Docker unter Linux, Mac oder Windows**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker*](https://docs.microsoft.com/sql/linux/sql-server-linux-setup-docker)

-   **Verbinden und Abfragen von SQL Server on Linux mit Sqlcmd**
    [*https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd*](https://docs.microsoft.com/sql/linux/sql-server-linux-connect-and-query-sqlcmd)

### <a name="seeding-with-test-data-on-web-application-startup"></a>Das Seeding mit Testdaten beim Start der Web-Anwendung

Zum Hinzufügen von Daten in die Datenbank beim Start der Anwendung können Sie die Configure-Methode in die Startklasse des Web-API-Projekts Code wie folgt hinzufügen:

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

Der folgende Code in der benutzerdefinierten CatalogContextSeed Klasse Daten gefüllt.

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

Beim Ausführen von Integrationstests eignet sich über eine Möglichkeit zum Generieren von Daten mit Ihrer Integrationstests konsistent. Es eignet sich hervorragend für testumgebungen, wird alles, was von Grund auf neu, einschließlich einer Instanz von SQL Server ausgeführt wird, für einen Container zu erstellen.

### <a name="ef-core-inmemory-database-versus-sql-server-running-as-a-container"></a>EF Core InMemory-Datenbank im Vergleich zu SQL Server ausgeführt wird, als container

Eine andere gute Wahl, die beim Ausführen von Tests ist die Verwendung von Entity Framework InMemory-Datenbankanbieter. Sie können diese Konfiguration in der Methode ConfigureServices die Startklasse im Web-API-Projekt angeben:

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

Es ist jedoch eine wichtige Catch. Die in-Memory-Datenbank unterstützt keine viele Einschränkungen, die für eine bestimmte Datenbank spezifisch sind. Sie können z. B. einen eindeutigen Index für eine Spalte in der EF-Core-Modell hinzufügen und Schreibtest für Ihre Datenbank im Arbeitsspeicher, überprüfen Sie, dass es nicht zulässt, dass Sie einen doppelten Wert hinzufügen. Aber wenn Sie die Datenbank im Arbeitsspeicher verwenden, können nicht eindeutige Indizes für eine Spalte behandelt. Aus diesem Grund die Datenbank im Arbeitsspeicher nicht verhält sich genauso wie eine echte SQL Server-Datenbank – emuliert nicht datenbankspezifischen Einschränkungen.

Deshalb ist eine in-Memory-Datenbank immer noch nützlich für das Testen und Prototyping. Aber wenn Sie genau Integrationstests erfolgreich zu erstellen, die das Verhalten der Implementierung eines bestimmten berücksichtigen möchten, müssen Sie eine echte Datenbank wie SQL Server verwenden. Zu diesem Zweck ist das Ausführen von SQL Server in einem Container eine gute Auswahl und genauer als die EF Core InMemory-Datenbankanbieter aus.

### <a name="using-a-redis-cache-service-running-in-a-container"></a>Verwenden einen Redis Cache-Dienst in einem container

Sie können Redis für einen Container, die speziell für die Entwicklung und Tests und Szenarien Proof of Concept ausführen. Dieses Szenario eignet sich, da Sie alle Ihre Abhängigkeiten, die in Containern ausgeführt haben, können – nicht nur für Ihre lokalen Entwicklungscomputern, jedoch für Ihre testumgebungen in Pipelines CI-CD.

Beim Ausführen von Redis in der Produktion ist es jedoch besser, die für eine Lösung mit hoher Verfügbarkeit wie Microsoft Azure Redis suchen, die als eine PaaS (Platform als Dienst) ausgeführt wird. In Ihrem Code müssen Sie nur die Verbindungszeichenfolgen ändern.

Redis bietet ein Docker Bild mit Redis. Dieses Abbild ist von Docker Hub an folgender URL verfügbar:

<https://Hub.docker.com/_/redis/>

Sie können einen Container mit Docker Redis direkt ausführen, durch den folgenden Docker-CLI-Befehl an der Eingabeaufforderung ausführen:

```
  docker run --name some-redis -d redis
```

Die Redis-Image enthält verfügbar gemacht: 6379 (der Port, der von Redis verwendet wird), also standard Container verknüpfen wird automatisch zur Verfügung stellen die verknüpften Container verwendet.

In eShopOnContainers verwendet die basket.api Microservice einen Redis-Cache als Container ausgeführt. Basket.data Container wird als Teil der Datei mit mehreren Container Docker-compose.yml definiert, wie im folgenden Beispiel gezeigt:

```yml
#docker-compose.yml file
#...
  basket.data:
    image: redis
    expose:
      - "6379"
```

Dieser Code in der Docker-compose.yml definiert einen Container namens basket.data basierend auf Redis-Image und veröffentlichen den Port 6379 intern, was bedeutet, dass darauf zugreifen können nur von anderen Containern, die innerhalb des Docker-Hosts ausgeführt wird.

In der Docker-compose.override.yml-Datei definiert die basket.api Microservice für das Beispiel eShopOnContainers schließlich die Verbindungszeichenfolge, die für diesen Container Redis verwendet:

```yml
  basket.api:
    environment:
      # Other data ...
      - ConnectionString=basket.data
      - EventBusConnection=rabbitmq
```


>[!div class="step-by-step"]
[Vorherigen] (multi-container-Anwendungen-Docker-compose.md) [weiter] (Integration-Ereignis-Basis-Microservice-communications.md)
