---
title: "Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen"
description: ".NET-Microservicesarchitektur für .NET-Containeranwendungen | Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b37d2c5683aff44165d0330c8d42fc881effbb76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a>Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen

Entity Framework Core bietet bereits interne Datenbankverbindungsresilienz und Wiederholungslogik für Azure SQL DB. Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede DbContext-Verbindung aktivieren, wenn Sie [robuste EF Core-Verbindungen](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) erzielen wollen.

Zum Beispiel aktiviert der folgende Code auf der EF Core-Verbindungsebene robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Ausführungsstrategien und explizite Transaktionen mit „BeginTransaction“ und mehreren DbContext-Objekten

Wenn Wiederholungen in EF Core-Verbindungen aktiviert sind, wird jeder Vorgang, den Sie mit EF Core durchführen, zu einem individuell wiederholbaren Vorgang. Jede Abfrage und jeder Aufruf von „SaveChanges“ wird als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.

Wenn Ihr Code jedoch eine Transaktion mit „BeginTransaction“ ausführt, definieren Sie Ihre eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen. Alles innerhalb dieser Transaktion wird zurückgesetzt, wenn ein Fehler auftritt. Eine Ausnahme wie die folgende wird angezeigt, wenn Sie versuchen, eine Transaktion auszuführen, wenn Sie die EF-Ausführungsstrategie verwenden (Wiederholungsrichtlinie) und mehrere Aufrufe von „SaveChanges“ von mehreren DbContext-Objekten in der Transaktion enthalten.

> System.InvalidOperationException: Die konfigurierte Ausführungsstrategie „SqlServerRetryingExecutionStrategy“ unterstützt keine vom Benutzer instanziierten Transaktionen. Verwenden Sie die Ausführungsstrategie, die von „DbContext.Database.CreateExecutionStrategy()“ zurückgegeben wird, um alle Vorgänge in der Transaktion als wiederholbare Einheit auszuführen.

Die Lösung ist, die EF-Ausführungsstrategie mit einem Delegaten manuell aufzurufen, der alle Komponenten darstellt, die ausgeführt werden müssen. Die Ausführungsstrategie ruft den Delegaten erneut auf, wenn ein vorübergehender Fehler auftritt. Zum Beispiel zeigt der folgende Code, wie diese in „eShopOnContainers“ mit zwei verschiedenen DbContext-Objekten (\_catalogContext und IntegrationEventLogContext) implementiert wird, wenn ein Produkt aktualisiert und das Objekt „ProductPriceChangedIntegrationEvent“ gespeichert wird, das ein anderes DbContext-Objekt verwenden muss.

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

Das erste DbContext-Objekt ist \_catalogContext, das zweite befindet sich im Objekt \_integrationEventLogService. Die Commitaktion wird unter Verwendung einer EF-Ausführungsstrategie für mehrere DbContext-Objekte ausgeführt.

## <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Verbindungsresilienz und Abfangen von Befehlen mit Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions (Verwenden widerstandsfähiger Entity Framework Core-SQL-Verbindungen und Transaktionen)**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>


>[!div class="step-by-step"]
[Zurück] (implement-retries-exponential-backoff.md) [Weiter] (implement-custom-http-call-retries-exponential-backoff.md)
