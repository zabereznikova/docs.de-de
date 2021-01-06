---
title: Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen
description: Erfahren Sie, wie Sie widerstandsfähige Entity Framework Core-SQL-Verbindungen implementieren. Diese Technik ist besonders wichtig, wenn Sie Azure SQL-Datenbank in der Cloud verwenden.
ms.date: 10/16/2018
ms.openlocfilehash: cae3550ce301750949b042957d5d10f0167e614c
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899560"
---
# <a name="implement-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="43939-104">Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="43939-104">Implement resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="43939-105">Entity Framework Core (EF) bietet bereits interne Datenbankverbindungsresilienz und Wiederholungslogik für Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="43939-105">For Azure SQL DB, Entity Framework (EF) Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="43939-106">Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede <xref:Microsoft.EntityFrameworkCore.DbContext>-Verbindung aktivieren, wenn Sie [robuste EF Core-Verbindungen](/ef/core/miscellaneous/connection-resiliency) erzielen wollen.</span><span class="sxs-lookup"><span data-stu-id="43939-106">But you need to enable the Entity Framework execution strategy for each <xref:Microsoft.EntityFrameworkCore.DbContext> connection if you want to have [resilient EF Core connections](/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="43939-107">Zum Beispiel aktiviert der folgende Code auf der EF Core-Verbindungsebene robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="43939-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="43939-108">Ausführungsstrategien und explizite Transaktionen mit „BeginTransaction“ und mehreren DbContext-Objekten</span><span class="sxs-lookup"><span data-stu-id="43939-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="43939-109">Wenn Wiederholungen in EF Core-Verbindungen aktiviert sind, wird jeder Vorgang, den Sie mit EF Core durchführen, zu einem individuell wiederholbaren Vorgang.</span><span class="sxs-lookup"><span data-stu-id="43939-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retryable operation.</span></span> <span data-ttu-id="43939-110">Jede Abfrage und jeder Aufruf von `SaveChanges` wird als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="43939-110">Each query and each call to `SaveChanges` will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="43939-111">Aber wenn Ihr Code eine Transaktion mit `BeginTransaction` initiiert, definieren Sie Ihre eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="43939-111">However, if your code initiates a transaction using `BeginTransaction`, you're defining your own group of operations that need to be treated as a unit.</span></span> <span data-ttu-id="43939-112">Alles innerhalb der Transaktion muss zurückgesetzt werden, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="43939-112">Everything inside the transaction has to be rolled back if a failure occurs.</span></span>

<span data-ttu-id="43939-113">Falls Sie versuchen, diese Transaktion auszuführen, wenn Sie die EF-Ausführungsstrategie verwenden (Wiederholungsrichtlinie), und Sie `SaveChanges` von mehreren DbContext-Objekten aus aufrufen, tritt eine Ausnahme ähnlich der folgenden auf:</span><span class="sxs-lookup"><span data-stu-id="43939-113">If you try to execute that transaction when using an EF execution strategy (retry policy) and you call `SaveChanges` from multiple DbContexts, you'll get an exception like this one:</span></span>

> <span data-ttu-id="43939-114">System.InvalidOperationException: Die konfigurierte Ausführungsstrategie SqlServerRetryingExecutionStrategy unterstützt keine vom Benutzer initiierten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="43939-114">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="43939-115">Verwenden Sie die Ausführungsstrategie, die von „DbContext.Database.CreateExecutionStrategy()“ zurückgegeben wird, um alle Vorgänge in der Transaktion als wiederholbare Einheit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="43939-115">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="43939-116">Die Lösung ist, die EF-Ausführungsstrategie mit einem Delegaten manuell aufzurufen, der alle Komponenten darstellt, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="43939-116">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="43939-117">Die Ausführungsstrategie ruft den Delegaten erneut auf, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="43939-117">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="43939-118">Zum Beispiel zeigt der folgende Code, wie diese in „eShopOnContainers“ mit zwei verschiedenen DbContext-Objekten (\_catalogContext und IntegrationEventLogContext) implementiert wird, wenn ein Produkt aktualisiert und das Objekt ProductPriceChangedIntegrationEvent gespeichert wird, das ein anderes DbContext-Objekt verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="43939-118">For example, the following code show how it's implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="43939-119">Der erste <xref:Microsoft.EntityFrameworkCore.DbContext> ist `_catalogContext`, und der zweite `DbContext` ist innerhalb des `_catalogIntegrationEventService`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="43939-119">The first <xref:Microsoft.EntityFrameworkCore.DbContext> is `_catalogContext` and the second `DbContext` is within the `_catalogIntegrationEventService` object.</span></span> <span data-ttu-id="43939-120">Die Commitaktion wird unter Verwendung einer EF-Ausführungsstrategie für alle `DbContext`-Objekte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43939-120">The Commit action is performed across all `DbContext` objects using an EF execution strategy.</span></span>

<span data-ttu-id="43939-121">Zum Erreichen dieses vielfachen `DbContext`-Commits verwendet `SaveEventAndCatalogContextChangesAsync` eine `ResilientTransaction`-Klasse, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="43939-121">To achieve this multiple `DbContext` commit, the `SaveEventAndCatalogContextChangesAsync` uses a `ResilientTransaction` class, as shown in the following code:</span></span>

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

<span data-ttu-id="43939-122">Die `ResilientTransaction.ExecuteAsync`-Methode beginnt im Grunde eine Transaktion aus dem übergebenen `DbContext` (`_catalogContext`) und lässt anschließend den `EventLogService` diese Transaktion verwenden, um Änderungen aus dem `IntegrationEventLogContext` zu speichern, und führt dann einen Commit der gesamten Transaktion durch.</span><span class="sxs-lookup"><span data-stu-id="43939-122">The `ResilientTransaction.ExecuteAsync` method basically begins a transaction from the passed `DbContext` (`_catalogContext`) and then makes the `EventLogService` use that transaction to save changes from the `IntegrationEventLogContext` and then commits the whole transaction.</span></span>

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
            await using var transaction = await _context.Database.BeginTransactionAsync();
            await action();
            await transaction.CommitAsync();
        });
    }
}
```

## <a name="additional-resources"></a><span data-ttu-id="43939-123">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="43939-123">Additional resources</span></span>

- <span data-ttu-id="43939-124">**Verbindungsresilienz und Abfangen von Befehlen mit Entity Framework in einer ASP.NET-MVC-Anwendung** </span><span class="sxs-lookup"><span data-stu-id="43939-124">**Connection Resiliency and Command Interception with EF in an ASP.NET MVC Application** </span></span>\
  [https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/connection-resiliency-and-command-interception-with-the-entity-framework-in-an-asp-net-mvc-application)

- <span data-ttu-id="43939-125">**Cesar de la Torre. Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen und Transaktionen** </span><span class="sxs-lookup"><span data-stu-id="43939-125">**Cesar de la Torre. Using Resilient Entity Framework Core SQL Connections and Transactions** </span></span>\
  <https://devblogs.microsoft.com/cesardelatorre/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/>

>[!div class="step-by-step"]
><span data-ttu-id="43939-126">[Zurück](implement-retries-exponential-backoff.md)
>[Weiter](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="43939-126">[Previous](implement-retries-exponential-backoff.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>
