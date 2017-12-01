---
title: Implementieren robuste Entity Framework Core-SQL-Verbindungen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Implementieren robuste Entity Framework Core-SQL-Verbindungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8600625c2022d69ebaa2645c2a8159a848b12ff0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementieren robuste Entity Framework Core-SQL-Verbindungen

Für Azure SQL-Datenbank bietet Entity Framework Core bereits interne Datenbank Connection Resiliency und Wiederholungslogik. Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede DbContext-Verbindung zu aktivieren, wenn Sie möchten [robusten EF Core Verbindungen](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).

Der folgende Code auf der Verbindungsebene EF Core ermöglicht z. B. robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 5,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Ausführungsstrategien und explizite Transaktionen mit BeginTransaction und mehrere DbContexts

Wenn Wiederholungen in EF Core Verbindungen aktiviert sind, wird jeden Vorgang, die Sie mit EF Core ausführen eigener wiederholbar Vorgang. Jede Abfrage und jeder Aufruf von SaveChanges werden als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.

Jedoch, wenn Ihr Code eine Transaktion mit BeginTransaction initiiert wird, definieren Sie eine eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen – alles innerhalb der Transaktion wurde ein Rollback ausgeführt zurück, wenn ein Fehler auftritt. Eine Ausnahme wie im folgenden sehen, wenn Sie versuchen, diese Transaktion ausgeführt werden, wenn eine EF Ausführungsstrategie (wiederholungsrichtlinie) verwenden, und mehrere SaveChanges-Aufrufe aus mehreren DbContexts in der Transaktion fügen.

> System.InvalidOperationException: Die konfigurierte Ausführungsstrategie 'SqlServerRetryingExecutionStrategy' unterstützt keine vom Benutzer initiierten Transaktionen. Verwenden Sie die Ausführungsstrategie "DbContext.Database.CreateExecutionStrategy()" zurückgegebene, um alle Vorgänge in der Transaktion als Einheit mit möglichem auszuführen.

Die Lösung besteht darin, manuell aufrufen Ausführungsstrategie EF mit einen Delegaten, die alle Elemente darstellt, die ausgeführt werden muss. Um ein vorübergehender Fehler auftritt, wird die Ausführungsstrategie den Delegaten erneut aufrufen. Z. B. der folgende Code zeigt, wie er im eShopOnContainers mit zwei implementiert wird mehrere DbContexts (\_CatalogContext und die IntegrationEventLogContext) beim Aktualisieren einer Produkt- und speichern Sie dann die ProductPriceChangedIntegrationEvent-Objekt, das einer anderen DbContext verwenden muss.

```csharp
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem
    productToUpdate)
{
    // Other code ...
    // Update current product
    catalogItem = productToUpdate;

    // Use of an EF Core resiliency strategy when using multiple DbContexts
    // within an explicit transaction
    // See:
    // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
    var strategy = _catalogContext.Database.CreateExecutionStrategy();
    await strategy.ExecuteAsync(async () =>
    {
        // Achieving atomicity between original Catalog database operation and the
        // IntegrationEventLog thanks to a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
            _catalogContext.CatalogItems.Update(catalogItem);
            await _catalogContext.SaveChangesAsync();
            // Save to EventLog only if product price changed
            if (raiseProductPriceChangedEvent)
            await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
            transaction.Commit();
        }
    });
}
```

Ist die erste DbContext \_CatalogContext und das zweite ist ' DbContext ' innerhalb der \_IntegrationEventLogService-Objekt. Der Commitvorgang wird über mehrere DbContexts mithilfe einer EF Ausführungsstrategie ausgeführt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Verbindungsresilienz und Abfangen der Befehl mit dem Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Verwenden von robusten Entity Framework Core-Sql-Verbindungen und Transaktionen**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Vorherigen] (implementieren-Wiederholungen-exponentiellen-backoff.md) [weiter] (Implement-custom-http-call-retries-exponential-backoff.md)
