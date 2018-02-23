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
# <a name="implementing-resilient-entity-framework-core-sql-connections"></a><span data-ttu-id="7ef85-104">Implementieren widerstandsfähiger Entity Framework Core-SQL-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="7ef85-104">Implementing resilient Entity Framework Core SQL connections</span></span>

<span data-ttu-id="7ef85-105">Entity Framework Core bietet bereits interne Datenbankverbindungsresilienz und Wiederholungslogik für Azure SQL DB.</span><span class="sxs-lookup"><span data-stu-id="7ef85-105">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="7ef85-106">Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede DbContext-Verbindung aktivieren, wenn Sie [robuste EF Core-Verbindungen](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) erzielen wollen.</span><span class="sxs-lookup"><span data-stu-id="7ef85-106">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have [resilient EF Core connections](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency).</span></span>

<span data-ttu-id="7ef85-107">Zum Beispiel aktiviert der folgende Code auf der EF Core-Verbindungsebene robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="7ef85-107">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

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

## <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="7ef85-108">Ausführungsstrategien und explizite Transaktionen mit „BeginTransaction“ und mehreren DbContext-Objekten</span><span class="sxs-lookup"><span data-stu-id="7ef85-108">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span>

<span data-ttu-id="7ef85-109">Wenn Wiederholungen in EF Core-Verbindungen aktiviert sind, wird jeder Vorgang, den Sie mit EF Core durchführen, zu einem individuell wiederholbaren Vorgang.</span><span class="sxs-lookup"><span data-stu-id="7ef85-109">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="7ef85-110">Jede Abfrage und jeder Aufruf von „SaveChanges“ wird als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7ef85-110">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>

<span data-ttu-id="7ef85-111">Wenn Ihr Code jedoch eine Transaktion mit „BeginTransaction“ ausführt, definieren Sie Ihre eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen. Alles innerhalb dieser Transaktion wird zurückgesetzt, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7ef85-111">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="7ef85-112">Eine Ausnahme wie die folgende wird angezeigt, wenn Sie versuchen, eine Transaktion auszuführen, wenn Sie die EF-Ausführungsstrategie verwenden (Wiederholungsrichtlinie) und mehrere Aufrufe von „SaveChanges“ von mehreren DbContext-Objekten in der Transaktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="7ef85-112">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges calls from multiple DbContexts in the transaction.</span></span>

> <span data-ttu-id="7ef85-113">System.InvalidOperationException: Die konfigurierte Ausführungsstrategie „SqlServerRetryingExecutionStrategy“ unterstützt keine vom Benutzer instanziierten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="7ef85-113">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="7ef85-114">Verwenden Sie die Ausführungsstrategie, die von „DbContext.Database.CreateExecutionStrategy()“ zurückgegeben wird, um alle Vorgänge in der Transaktion als wiederholbare Einheit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7ef85-114">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="7ef85-115">Die Lösung ist, die EF-Ausführungsstrategie mit einem Delegaten manuell aufzurufen, der alle Komponenten darstellt, die ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7ef85-115">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="7ef85-116">Die Ausführungsstrategie ruft den Delegaten erneut auf, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="7ef85-116">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="7ef85-117">Zum Beispiel zeigt der folgende Code, wie diese in „eShopOnContainers“ mit zwei verschiedenen DbContext-Objekten (\_catalogContext und IntegrationEventLogContext) implementiert wird, wenn ein Produkt aktualisiert und das Objekt „ProductPriceChangedIntegrationEvent“ gespeichert wird, das ein anderes DbContext-Objekt verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="7ef85-117">For example, the following code show how it is implemented in eShopOnContainers with two multiple DbContexts (\_catalogContext and the IntegrationEventLogContext) when updating a product and then saving the ProductPriceChangedIntegrationEvent object, which needs to use a different DbContext.</span></span>

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

<span data-ttu-id="7ef85-118">Das erste DbContext-Objekt ist \_catalogContext, das zweite befindet sich im Objekt \_integrationEventLogService.</span><span class="sxs-lookup"><span data-stu-id="7ef85-118">The first DbContext is \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="7ef85-119">Die Commitaktion wird unter Verwendung einer EF-Ausführungsstrategie für mehrere DbContext-Objekte ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7ef85-119">The Commit action is performed across multiple DbContexts using an EF execution strategy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ef85-120">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="7ef85-120">Additional resources</span></span>

-   <span data-ttu-id="7ef85-121">**Verbindungsresilienz und Abfangen von Befehlen mit Entity Framework**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span><span class="sxs-lookup"><span data-stu-id="7ef85-121">**Connection Resiliency and Command Interception with the Entity Framework**
[*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)</span></span>

-   <span data-ttu-id="7ef85-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions (Verwenden widerstandsfähiger Entity Framework Core-SQL-Verbindungen und Transaktionen)**
    <https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span><span class="sxs-lookup"><span data-stu-id="7ef85-122">**Cesar de la Torre. Using Resilient Entity Framework Core Sql Connections and Transactions**
<https://blogs.msdn.microsoft.com/cesardelatorre/2017/03/26/using-resilient-entity-framework-core-sql-connections-and-transactions-retries-with-exponential-backoff/></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7ef85-123">[Zurück] (implement-retries-exponential-backoff.md) [Weiter] (implement-custom-http-call-retries-exponential-backoff.md)</span><span class="sxs-lookup"><span data-stu-id="7ef85-123">[Previous] (implement-retries-exponential-backoff.md) [Next] (implement-custom-http-call-retries-exponential-backoff.md)</span></span>
