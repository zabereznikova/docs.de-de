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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="af92c-104">Implementieren robuste Entity Framework Core-SQL-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="af92c-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="af92c-105">Für Azure SQL-Datenbank bietet Entity Framework Core bereits interne Datenbank Connection Resiliency und Wiederholungslogik.</span><span class="sxs-lookup"><span data-stu-id="af92c-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="af92c-106">Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede DbContext-Verbindung zu aktivieren, wenn Sie möchten [robusten EF Core Verbindungen](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span><span class="sxs-lookup"><span data-stu-id="af92c-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="af92c-107">Der folgende Code auf der Verbindungsebene EF Core ermöglicht z. B. robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="af92c-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="af92c-108">Ausführungsstrategien und explizite Transaktionen mit BeginTransaction und mehrere DbContexts</span><span class="sxs-lookup"><span data-stu-id="af92c-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="af92c-109">Wenn Wiederholungen in EF Core Verbindungen aktiviert sind, wird jeden Vorgang, die Sie mit EF Core ausführen eigener wiederholbar Vorgang.</span><span class="sxs-lookup"><span data-stu-id="af92c-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="af92c-110">Jede Abfrage und jeder Aufruf von SaveChanges werden als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="af92c-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="af92c-111">Jedoch, wenn Ihr Code eine Transaktion mit BeginTransaction initiiert wird, definieren Sie eine eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen – alles innerhalb der Transaktion wurde ein Rollback ausgeführt zurück, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="af92c-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="af92c-112">Eine Ausnahme wie im folgenden sehen, wenn Sie versuchen, diese Transaktion ausgeführt werden, wenn eine EF Ausführungsstrategie (wiederholungsrichtlinie) verwenden, und mehrere SaveChanges-Aufrufe aus mehreren DbContexts in der Transaktion fügen.</span><span class="sxs-lookup"><span data-stu-id="af92c-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="af92c-113">System.InvalidOperationException: Die konfigurierte Ausführungsstrategie 'SqlServerRetryingExecutionStrategy' unterstützt keine vom Benutzer initiierten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="af92c-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="af92c-114">Verwenden Sie die Ausführungsstrategie "DbContext.Database.CreateExecutionStrategy()" zurückgegebene, um alle Vorgänge in der Transaktion als Einheit mit möglichem auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af92c-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="af92c-115">Die Lösung besteht darin, manuell aufrufen Ausführungsstrategie EF mit einen Delegaten, die alle Elemente darstellt, die ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="af92c-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="af92c-116">Um ein vorübergehender Fehler auftritt, wird die Ausführungsstrategie den Delegaten erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="af92c-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="af92c-117">Z. B. der folgende Code zeigt, wie er im eShopOnContainers mit zwei implementiert wird mehrere DbContexts (\_CatalogContext und die IntegrationEventLogContext) beim Aktualisieren einer Produkt- und speichern Sie dann die ProductPriceChangedIntegrationEvent-Objekt, das einer anderen DbContext verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="af92c-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="af92c-118">Ist die erste DbContext \_CatalogContext und das zweite ist ' DbContext ' innerhalb der \_IntegrationEventLogService-Objekt.</span><span class="sxs-lookup"><span data-stu-id="af92c-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="af92c-119">Der Commitvorgang wird über mehrere DbContexts mithilfe einer EF Ausführungsstrategie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="af92c-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="af92c-120">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="af92c-120">Additional resources</span></span>

-   <span data-ttu-id="af92c-121">**Verbindungsresilienz und Abfangen der Befehl mit dem Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="af92c-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="af92c-122">**Cesar de la Torre. Verwenden von robusten Entity Framework Core-Sql-Verbindungen und Transaktionen**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="af92c-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="af92c-123">[Vorherigen] (implementieren-Wiederholungen-exponentiellen-backoff.md) [weiter] (Implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="af92c-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
