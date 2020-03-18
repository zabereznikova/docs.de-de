---
title: Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen
description: Erfahren Sie, wie Sie widerstandsfähige Entity Framework Core-SQL-Verbindungen implementieren. Diese Technik ist besonders wichtig, wenn Sie Azure SQL-Datenbank in der Cloud verwenden.
ms.date: 10/16/2018
ms.openlocfilehash: 7a047edca21d63a451e90f407b23f3358d461330
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78241064"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a>Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen

Entity Framework Core (EF) bietet bereits interne Datenbankverbindungsresilienz und Wiederholungslogik für Azure SQL DB. Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede <xref:Microsoft.EntityFrameworkCore.DbContext>-Verbindung aktivieren, wenn Sie [robuste EF Core-Verbindungen](/ef/core/miscellaneous/connection-resiliency) erzielen wollen.

Zum Beispiel aktiviert der folgende Code auf der EF Core-Verbindungsebene robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    // Other code ...
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        // ...
        services.AddDbContext<CatalogContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
            {
                sqlOptions.EnableRetryOnFailure(
                maxRetryCount: 10,
                maxRetryDelay: TimeSpan.FromSeconds(30),
                errorNumbersToAdd: null);
            });
        });
    }
//...
}
```

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Ausführungsstrategien und explizite Transaktionen mit „BeginTransaction“ und mehreren DbContext-Objekten

Wenn Wiederholungen in EF Core-Verbindungen aktiviert sind, wird jeder Vorgang, den Sie mit EF Core durchführen, zu einem individuell wiederholbaren Vorgang. Jede Abfrage und jeder Aufruf von `SaveChanges` wird als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.

Aber wenn Ihr Code eine Transaktion mit `BeginTransaction` initiiert, definieren Sie Ihre eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen. Alles innerhalb der Transaktion muss zurückgesetzt werden, wenn ein Fehler auftritt.

Falls Sie versuchen, diese Transaktion auszuführen, wenn Sie die EF-Ausführungsstrategie verwenden (Wiederholungsrichtlinie), und Sie `SaveChanges` von mehreren DbContext-Objekten aus aufrufen, tritt eine Ausnahme ähnlich der folgenden auf:

> System.InvalidOperationException: Die konfigurierte Ausführungsstrategie SqlServerRetryingExecutionStrategy unterstützt keine vom Benutzer initiierten Transaktionen. Verwenden Sie die Ausführungsstrategie, die von „DbContext.Database.CreateExecutionStrategy()“ zurückgegeben wird, um alle Vorgänge in der Transaktion als wiederholbare Einheit auszuführen.

Die Lösung ist, die EF-Ausführungsstrategie mit einem Delegaten manuell aufzurufen, der alle Komponenten darstellt, die ausgeführt werden müssen. Die Ausführungsstrategie ruft den Delegaten erneut auf, wenn ein vorübergehender Fehler auftritt. Zum Beispiel zeigt der folgende Code, wie diese in „eShopOnContainers“ mit zwei verschiedenen DbContext-Objekten (\_catalogContext und IntegrationEventLogContext) implementiert wird, wenn ein Produkt aktualisiert und das Objekt ProductPriceChangedIntegrationEvent gespeichert wird, das ein anderes DbContext-Objekt verwenden muss.

```csharp
public async Task<IActionResult> UpdateProduct(
    [FromBody]CatalogItem productToUpdate)
{
    // Other code ...

    var oldPrice = catalogItem.Price;
    var raiseProductPriceChangedEvent = oldPrice != productToUpdate.Price;

    // Update current product
    catalogItem = productToUpdate;

    // Save product's data and publish integration event through the Event Bus
    // if price has changed
    if (raiseProductPriceChangedEvent)
    {
        //Create Integration Event to be published through the Event Bus
        var priceChangedEvent = new ProductPriceChangedIntegrationEvent(
          catalogItem.Id, productToUpdate.Price, oldPrice);

       // Achieving atomicity between original Catalog database operation and the
       // IntegrationEventLog thanks to a local transaction
       await _catalogIntegrationEventService.SaveEventAndCatalogContextChangesAsync(
           priceChangedEvent);

       // Publish through the Event Bus and mark the saved event as published
       await _catalogIntegrationEventService.PublishThroughEventBusAsync(
           priceChangedEvent);
    }
    // Just save the updated product because the Product's Price hasn't changed.
    else
    {
        await _catalogContext.SaveChangesAsync();
    }
}
```

Der erste <xref:Microsoft.EntityFrameworkCore.DbContext> ist `_catalogContext`, und der zweite `DbContext` ist innerhalb des `_catalogIntegrationEventService`-Objekts. Die Commitaktion wird unter Verwendung einer EF-Ausführungsstrategie für alle `DbContext`-Objekte ausgeführt.

Zum Erreichen dieses vielfachen `DbContext`-Commits verwendet `SaveEventAndCatalogContextChangesAsync` eine `ResilientTransaction`-Klasse, wie im folgenden Code gezeigt:

```csharp
public class CatalogIntegrationEventService : ICatalogIntegrationEventService
{
    //…
    public async Task SaveEventAndCatalogContextChangesAsync(
        IntegrationEvent evt)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        await ResilientTransaction.New(_catalogContext).ExecuteAsync(async () =>
        {
            // Achieving atomicity between original catalog database
            // operation and the IntegrationEventLog thanks to a local transaction
            await _catalogContext.SaveChangesAsync();
            await _eventLogService.SaveEventAsync(evt,
                _catalogContext.Database.CurrentTransaction.GetDbTransaction());
        });
    }
}
```

Die `ResilientTransaction.ExecuteAsync`-Methode beginnt im Grunde eine Transaktion aus dem übergebenen `DbContext` (`_catalogContext`) und lässt anschließend den `EventLogService` diese Transaktion verwenden, um Änderungen aus dem `IntegrationEventLogContext` zu speichern, und führt dann einen Commit der gesamten Transaktion durch.

```csharp
public class ResilientTransaction
{
    private DbContext _context;
    private ResilientTransaction(DbContext context) =>
        _context = context ?? throw new ArgumentNullException(nameof(context));

    public static ResilientTransaction New (DbContext context) =>
        new ResilientTransaction(context);

    public async Task ExecuteAsync(Func<Task> action)
    {
        // Use of an EF Core resiliency strategy when using multiple DbContexts
        // within an explicit BeginTransaction():
        // https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
        var strategy = _context.Database.CreateExecutionStrategy();
        await strategy.ExecuteAsync(async () =>
        {
            using (var transaction = _context.Database.BeginTransaction())
            {
                await action();
                transaction.Commit();
            }
        });
    }
}
```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Verbindungsresilienz und Abfangen von Befehlen mit Entity Framework in einer ASP.NET-MVC-Anwendung** \
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- **Cesar de la Torre. Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen und Transaktionen** \
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
>[Zurück](implement-retries-exponential-backoff.md)
>[Weiter](use-httpclientfactory-to-implement-resilient-http-requests.md)
