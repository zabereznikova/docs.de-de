---
title: Erstellen eines einfachen datengesteuerten CRUD-Microservice
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Grundlagen der Erstellung eines einfachen CRUD-Microservice (datengesteuert) im Kontext einer Microserviceanwendung.
ms.date: 01/30/2020
ms.openlocfilehash: b72d7defed81e57e2971c5e2b53df2d86b2dc947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77502356"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="fbdf4-103">Erstellen eines einfachen datengesteuerten CRUD-Microservice</span><span class="sxs-lookup"><span data-stu-id="fbdf4-103">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="fbdf4-104">Dieser Abschnitt beschreibt das Erstellen eines einfachen Microservice, der Erstell-, Lese-, Aktualisierungs- und Löschvorgänge (CRUD) für eine Datenquelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-104">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="fbdf4-105">Entwerfen eines einfachen CRUD-Microservice</span><span class="sxs-lookup"><span data-stu-id="fbdf4-105">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="fbdf4-106">Aus Entwurfssicht ist diese Art eines Container-Microservice sehr einfach konzipiert.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-106">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="fbdf4-107">Möglicherweise ist das zu lösende Problem einfach, oder bei der Implementierung handelt es sich nur um ein Proof of Concept.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-107">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![Diagramm, das das interne Entwurfsmuster eines einfachen CRUD-Microservice zeigt.](./media/data-driven-crud-microservice/internal-design-simple-crud-microservices.png)

<span data-ttu-id="fbdf4-109">**Abbildung 6-4**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-109">**Figure 6-4**.</span></span> <span data-ttu-id="fbdf4-110">Interner Entwurf für einfache CRUD-Microservices</span><span class="sxs-lookup"><span data-stu-id="fbdf4-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="fbdf4-111">Ein Beispiel für diese Art eines einfachen datengesteuerten Service ist der Microservice Katalog aus der Beispielanwendung „eShopOnContainers“.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="fbdf4-112">Dieser Servicetyp implementiert alle seine Funktionen in einem einzigen ASP.NET Core-Web-API-Projekt, das Klassen für sein Datenmodell, seine Geschäftslogik und seinen Datenzugriffscode enthält.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="fbdf4-113">Außerdem speichert er seine zugehörigen Daten in einer Datenbank unter SQL Server (als weiterem Container für Entwicklungs- und Testzwecke), es könnte sich aber wie in Abbildung 6-5 gezeigt auch um einen beliebigen regulären SQL Server-Host handeln.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 6-5.</span></span>

![Diagramm, das einen datengesteuerten/CRUD-Microservice-Container zeigt.](./media/data-driven-crud-microservice/simple-data-driven-crud-microservice.png)

<span data-ttu-id="fbdf4-115">**Abbildung 6-5**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-115">**Figure 6-5**.</span></span> <span data-ttu-id="fbdf4-116">Einfacher datengesteuerter/CRUD-Microservice-Entwurf</span><span class="sxs-lookup"><span data-stu-id="fbdf4-116">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="fbdf4-117">Das vorherige Diagramm zeigt den logischen Katalogmicroservice, der seine Katalogdatenbank enthält, die sich im selben Docker-Host befinden kann.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-117">The previous diagram shows the logical Catalog microservice, that includes its Catalog database, which can be or not in the same Docker host.</span></span> <span data-ttu-id="fbdf4-118">Es kann sich für die Entwicklung, aber nicht für die Produktion eignen, wenn sich die Datenbank im selben Docker-Host befindet.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-118">Having the database in the same Docker host might be good for development, but not for production.</span></span> <span data-ttu-id="fbdf4-119">Wenn Sie diese Art von Service entwickeln, benötigen Sie nur [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) und eine Datenzugriffs-API oder eine ORM wie [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-119">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="fbdf4-120">Sie könnten ferner, wie im nächsten Abschnitt erläutert, automatisch [Swagger](https://swagger.io/)-Metadaten über [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) generieren, um eine Beschreibung dessen bereitzustellen, was Ihr Service umfasst.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-120">You could also generate [Swagger](https://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="fbdf4-121">Beachten Sie, dass sich die Ausführung eines Datenbankservers wie SQL Server in einem Docker-Container gut für Entwicklungsumgebungen eignet, da alle Ihre Abhängigkeiten eingerichtet werden können, ohne dass Sie eine Datenbank in der Cloud oder lokal bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-121">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="fbdf4-122">Dies ist sehr praktisch bei der Durchführung von Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-122">This is very convenient when running integration tests.</span></span> <span data-ttu-id="fbdf4-123">Allerdings wird dies für Produktionsumgebungen, die einen Datenbankserver in einem Container ausführen, nicht empfohlen, da Sie mit diesem Ansatz in der Regel keine Hochverfügbarkeit erzielen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-123">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="fbdf4-124">Für eine Produktionsumgebung in Azure empfiehlt es sich, Azure SQL DB oder eine andere Datenbanktechnologie zu verwenden, die eine Hochverfügbarkeit und Skalierbarkeit bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-124">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="fbdf4-125">Für einen NoSQL-Ansatz können Sie beispielsweise CosmosDB auswählen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-125">For example, for a NoSQL approach, you might choose CosmosDB.</span></span>

<span data-ttu-id="fbdf4-126">Und schließlich können Sie durch Bearbeiten der Dockerfile-Datei und der docker-compose.yml-Metadatendateien konfigurieren, wie das Image dieses Containers erstellt wird, d.h. welches Basisimage es verwendet und welche Entwurfseinstellungen wie interne und externe Namen sowie TCP-Ports verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-126">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span>

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="fbdf4-127">Implementieren eines einfachen CRUD-Microservice mit ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbdf4-127">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="fbdf4-128">Erstellen Sie zum Implementieren eines einfachen CRUD-Microservice mit .NET Core und Visual Studio zunächst wie in Abbildung 6-6 gezeigt ein einfaches ASP.NET Core-Web-API-Projekt (unter .NET Core, sodass es auf einem Linux-Docker-Host ausgeführt werden kann).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-128">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 6-6.</span></span>

![Screenshot von Visual Studio mit der Einrichtung des Projekts.](./media/data-driven-crud-microservice/create-asp-net-core-web-api-project.png)

<span data-ttu-id="fbdf4-130">**Abbildung 6-6**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-130">**Figure 6-6**.</span></span> <span data-ttu-id="fbdf4-131">Erstellen eines ASP.NET Core-Web-API-Projekts in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="fbdf4-131">Creating an ASP.NET Core Web API project in Visual Studio 2019</span></span>

<span data-ttu-id="fbdf4-132">Wählen Sie zuerst eine ASP.NET Core-Webanwendung und dann den API-Typ aus, um ein ASP.NET Core-Web-API-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-132">To create an ASP.NET Core Web API Project, first select an ASP.NET Core Web Application and then select the API type.</span></span> <span data-ttu-id="fbdf4-133">Nach dem Erstellen des Projekts können Sie Ihre MVC-Controller wie in jedem anderen Web-API-Projekt mit der Entity Framework-API oder einer anderen API implementieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-133">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="fbdf4-134">In einem neuen Web-API-Projekt können Sie sehen, dass die einzige Abhängigkeit im betreffenden Microservice ASP.NET Core selbst betrifft.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-134">In a new Web API project, you can see that the only dependency you have in that microservice is on ASP.NET Core itself.</span></span> <span data-ttu-id="fbdf4-135">Intern (innerhalb der Abhängigkeit *Microsoft.AspNetCore.All*) verweist diese wie in Abbildung 6-7 gezeigt auf Entity Framework und viele andere .NET Core NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-135">Internally, within the *Microsoft.AspNetCore.All* dependency, it is referencing Entity Framework and many other .NET Core NuGet packages, as shown in Figure 6-7.</span></span>

![Screenshot von VS mit den NuGet-Abhängigkeiten von Catalog.API.](./media/data-driven-crud-microservice/simple-crud-web-api-microservice-dependencies.png)

<span data-ttu-id="fbdf4-137">**Abbildung 6-7**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-137">**Figure 6-7**.</span></span> <span data-ttu-id="fbdf4-138">Abhängigkeiten in einem einfachen CRUD-Web-API-Microservice</span><span class="sxs-lookup"><span data-stu-id="fbdf4-138">Dependencies in a simple CRUD Web API microservice</span></span>

<span data-ttu-id="fbdf4-139">Das API-Projekt enthält Verweise auf das NuGet-Paket „Microsoft.AspNetCore.App“, das wiederum Verweise auf alle erforderliche Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-139">The API project includes references to the Microsoft.AspNetCore.App NuGet package, that includes references to all essential packages.</span></span> <span data-ttu-id="fbdf4-140">Einige weitere Pakete können ebenfalls enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-140">It could include some other packages as well.</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="fbdf4-141">Implementieren von CRUD-Web-API-Services mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="fbdf4-141">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="fbdf4-142">Entity Framework Core (EF Core) ist eine einfache, erweiterbare und plattformübergreifende Version der beliebten Entity Framework-Datenzugriffstechnologie.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-142">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="fbdf4-143">EF Core ist eine objektrelationale Zuordnung (ORM, Object-Relational Mapper), die .NET-Entwicklern mithilfe von .NET-Objekten das Arbeiten mit einer Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-143">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="fbdf4-144">Der Microservice Katalog verwendet EF und den SQL Server-Anbieter, da seine Datenbank in einem Container mit dem Image SQL Server for Linux Docker ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-144">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="fbdf4-145">Allerdings könnte die Datenbank in einem beliebigen SQL Server wie Windows lokal oder Azure SQL DB bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-145">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="fbdf4-146">Sie müssten lediglich die Verbindungszeichenfolge im ASP.NET Web API-Microservice ändern.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-146">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="the-data-model"></a><span data-ttu-id="fbdf4-147">Das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="fbdf4-147">The data model</span></span>

<span data-ttu-id="fbdf4-148">Bei EF Core erfolgt der Datenzugriff über ein Modell.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-148">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="fbdf4-149">Ein Modell setzt sich aus Entitätsklassen (Domänenmodell) und einem abgeleiteten Kontext (DbContext) zusammen, der eine Sitzung bei der Datenbank darstellt und Ihnen das Abfragen und Speichern von Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-149">A model is made up of (domain model) entity classes and a derived context (DbContext) that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="fbdf4-150">Mithilfe des Code-First-Ansatzes können Sie ein Modell aus einer vorhandenen Datenbank generieren, ein Modell manuell anhand Ihrer Datenbank schreiben oder mithilfe von EF-Migrationen eine Datenbank aus Ihrem Modell erstellen (hiermit wird die Entwicklung der Datenbank vereinfacht, während Ihr Modell sich im Laufe der Zeit weiterentwickelt).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-150">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model, using the code-first approach (that makes it easy to evolve the database as your model changes over time).</span></span> <span data-ttu-id="fbdf4-151">Für den Microservice Katalog verwenden wir den letztgenannten Ansatz.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-151">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="fbdf4-152">Das folgende Codebeispiel zeigt die Entitätsklasse CatalogItem. Hierbei handelt es sich um eine einfache POCO-Entitätsklasse ([Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-152">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

<span data-ttu-id="fbdf4-153">Darüber hinaus benötigen Sie einen DbContext, der eine Sitzung mit der Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-153">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="fbdf4-154">Für den Microservice Katalog wird die CatalogContext-Klasse von der DbContext-Basisklasse abgeleitet, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-154">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    { }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...
}
```

<span data-ttu-id="fbdf4-155">Zusätzliche `DbContext`-Implementierungen sind möglich.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-155">You can have additional `DbContext` implementations.</span></span> <span data-ttu-id="fbdf4-156">Im als Beispiel dienenden Catalog.API-Microservice gibt es einen zweiten `DbContext` namens `CatalogContextSeed`. Hier werden automatisch die Beispieldaten beim ersten Zugriffsversuch auf die Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-156">For example, in the sample Catalog.API microservice, there's a second `DbContext` named `CatalogContextSeed` where it automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="fbdf4-157">Diese Methode ist auch für Demodaten und automatische Testszenarios nützlich.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-157">This method is useful for demo data and for automated testing scenarios, as well.</span></span>

<span data-ttu-id="fbdf4-158">Innerhalb von `DbContext` verwenden Sie die `OnModelCreating`-Methode, um Objekt-/Datenbankentitätszuordnungen und andere [EF-Erweiterungspunkte](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/) anzupassen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-158">Within the `DbContext`, you use the `OnModelCreating` method to customize object/database entity mappings and other [EF extensibility points](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="fbdf4-159">Abfragen von Daten aus Web-API-Controllern</span><span class="sxs-lookup"><span data-stu-id="fbdf4-159">Querying data from Web API controllers</span></span>

<span data-ttu-id="fbdf4-160">Instanzen Ihrer Entitätsklassen werden üblicherweise – wie im nachstehenden Beispiel gezeigt – mit LINQ (Language Integrated Query) aus der Datenbank abgerufen:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-160">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(
        CatalogContext context,
        IOptionsSnapshot<CatalogSettings> settings,
        ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService
            ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        context.ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("items")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType(typeof(IEnumerable<CatalogItem>), (int)HttpStatusCode.OK)]
    [ProducesResponseType((int)HttpStatusCode.BadRequest)]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery]int pageSize = 10,
        [FromQuery]int pageIndex = 0,
        string ids = null)
    {
        if (!string.IsNullOrEmpty(ids))
        {
            var items = await GetItemsByIdsAsync(ids);

            if (!items.Any())
            {
                return BadRequest("ids value invalid. Must be comma-separated list of numbers");
            }

            return Ok(items);
        }

        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a><span data-ttu-id="fbdf4-161">Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="fbdf4-161">Saving data</span></span>

<span data-ttu-id="fbdf4-162">Daten werden in der Datenbank mithilfe von Instanzen Ihrer Entitätsklassen erstellt, gelöscht und geändert.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-162">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="fbdf4-163">Sie können Code wie im folgenden hartcodierten Beispiel (in diesem Fall Simulationsdaten) zu Ihren Web-API-Controllern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-163">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="fbdf4-164">Abhängigkeitseinfügung in ASP.NET Core- und Web-API-Controllern</span><span class="sxs-lookup"><span data-stu-id="fbdf4-164">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="fbdf4-165">In ASP.NET Core können Sie die vorkonfigurierte Abhängigkeitseinfügung (DI, Dependency Injection) verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-165">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="fbdf4-166">Sie müssen keinen IoC-Container (Inversion of Control) eines Drittanbieters einrichten, können aber Ihren bevorzugten IoC-Container in die ASP.NET Core-Infrastruktur einbinden, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-166">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="fbdf4-167">In diesem Fall können Sie den erforderlichen EF-DBContext oder zusätzliche Repositorys direkt über den Controller-Konstruktor einfügen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-167">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span>

<span data-ttu-id="fbdf4-168">Im obigen Beispiel für die `CatalogController`-Klasse fügen wir ein Objekt des `CatalogContext`-Typs und andere Objekte über den `CatalogController()`-Konstruktor ein.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-168">In the example above of the `CatalogController` class, we are injecting an object of `CatalogContext` type plus other objects through the `CatalogController()` constructor.</span></span>

<span data-ttu-id="fbdf4-169">Ein wichtiger Konfigurationsschritt bei der Einrichtung des Web-API-Projekts ist die Registrierung der DbContext-Klasse im IoC-Container des Diensts.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-169">An important configuration to set up in the Web API project is the DbContext class registration into the service's IoC container.</span></span> <span data-ttu-id="fbdf4-170">Hierzu rufen Sie in der Regel in der `Startup`-Klasse die `services.AddDbContext<DbContext>()`-Methode innerhalb der `ConfigureServices()`-Methode auf, wie im folgenden **vereinfachten** Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-170">You typically do so in the `Startup` class by calling the `services.AddDbContext<DbContext>()` method inside the `ConfigureServices()` method, as shown in the following **simplified** example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.MigrationsAssembly(
                typeof(Startup).GetTypeInfo().Assembly.GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...
}
```

### <a name="additional-resources"></a><span data-ttu-id="fbdf4-171">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-171">Additional resources</span></span>

- <span data-ttu-id="fbdf4-172">**Abfrage von Daten** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-172">**Querying Data** </span></span>\
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- <span data-ttu-id="fbdf4-173">**Speichern von Daten** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-173">**Saving Data** </span></span>\
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="fbdf4-174">Die von Docker-Containern verwendete DB-Verbindungszeichenfolge und die Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-174">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="fbdf4-175">Wie im folgenden Beispiel gezeigt wird, können Sie die ASP.NET Core-Einstellungen verwenden und eine ConnectionString-Eigenschaft zu Ihrer Datei settings.json hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-175">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

<span data-ttu-id="fbdf4-176">Die Datei settings.json kann Standardwerte für die ConnectionString-Eigenschaft oder für eine andere Eigenschaft enthalten.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-176">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="fbdf4-177">Diese Eigenschaften werden jedoch durch die Werte der Umgebungsvariablen überschrieben, die Sie in der Datei docker-compose.override.yml angeben, wenn Sie Docker verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-177">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file, when using Docker.</span></span>

<span data-ttu-id="fbdf4-178">Aus Ihren Dateien „docker-compose.yml“ oder „docker-compose.override.yml“ können Sie diese Umgebungsvariablen initialisieren, damit Docker sie wie in der folgenden Datei „docker-compose.override.yml“ gezeigt als Umgebungsvariablen für das Betriebssystem für Sie einrichtet. (Die Verbindungszeichenfolge und andere Zeilen in diesem Beispiel weisen einen Zeilenumbruch auf, was in Ihrer Datei jedoch nicht der Fall wäre.)</span><span class="sxs-lookup"><span data-stu-id="fbdf4-178">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog-api:
  environment:
    - ConnectionString=Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

<span data-ttu-id="fbdf4-179">Die docker-compose.yml-Dateien auf der Lösungsebene sind nicht nur flexibler als Konfigurationsdateien auf der Projekt- oder Microservice-Ebene, sondern auch sicherer, wenn Sie die in den docker-compose-Dateien deklarierten Umgebungsvariablen mit Werten überschreiben, die von Ihren Bereitstellungstools (z.B. Azure DevOps Services-Docker-Bereitstellungsaufgaben) festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-179">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure if you override the environment variables declared at the docker-compose files with values set from your deployment tools, like from Azure DevOps Services Docker deployment tasks.</span></span>

<span data-ttu-id="fbdf4-180">Abschließend können Sie diesen Wert aus Ihrem Code abrufen, indem Sie Configuration\["ConnectionString"\] verwenden, wie es in der ConfigureServices-Methode in einem Codebeispiel weiter oben gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-180">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="fbdf4-181">Allerdings kann es für Produktionsumgebungen sinnvoll sein, zusätzliche Methoden zu untersuchen, mit denen sich Geheimnisse wie die Verbindungszeichenfolgen speichern lassen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-181">However, for production environments, you might want to explore additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="fbdf4-182">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/) ist eine hervorragende Möglichkeit zum Verwalten von Anwendungsgeheimnissen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-182">An excellent way to manage application secrets is using [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="fbdf4-183">Azure Key Vault dient zum Speichern und Schützen kryptografischer und geheimer Schlüssel, die von Cloudanwendungen und -diensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-183">Azure Key Vault helps to store and safeguard cryptographic keys and secrets used by your cloud applications and services.</span></span> <span data-ttu-id="fbdf4-184">Ein Geheimnis ist etwas, das Sie streng überwachen sollten. Es handelt sich dabei z.B. um API-Schlüssel, Verbindungszeichenfolgen, Kennwörter usw. Zu dieser strengen Überwachung gehören *u.a.* die Nutzungsprotokollierung, das Festlegen der Ablaufzeit und das Verwalten des Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-184">A secret is anything you want to keep strict control of, like API keys, connection strings, passwords, etc. and strict control includes usage logging, setting expiration, managing access, *among others*.</span></span>

<span data-ttu-id="fbdf4-185">Azure Key Vault ermöglicht detaillierte Kontrolle über die Nutzung von Anwendungsgeheimnissen, ohne dass sie jemand kennen muss.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-185">Azure Key Vault allows a very detailed control level of the application secrets usage without the need to let anyone know them.</span></span> <span data-ttu-id="fbdf4-186">Die Geheimnisse können sogar ausgetauscht werden, um die Sicherheit zu erhöhen, ohne Unterbrechung der Entwicklung oder des Betriebs.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-186">The secrets can even be rotated for enhanced security without disrupting development or operations.</span></span>

<span data-ttu-id="fbdf4-187">Anwendungen müssen in der Active Directory-Instanz Ihres Unternehmens registriert sein, damit sie den Schlüsseltresor verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-187">Applications have to be registered in the organization's Active Directory, so they can use the Key Vault.</span></span>

<span data-ttu-id="fbdf4-188">Weitere Informationen finden Sie in der *Dokumentation zu Azure Key Vault*.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-188">You can check the *Key Vault Concepts documentation* for more details.</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="fbdf4-189">Implementieren einer Versionsverwaltung in ASP.NET Web-APIs</span><span class="sxs-lookup"><span data-stu-id="fbdf4-189">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="fbdf4-190">Wenn sich die Geschäftsanforderungen ändern, werden möglicherweise neue Sammlungen von Ressourcen hinzugefügt, die Beziehungen zwischen Ressourcen können sich ändern, und die Struktur der Daten in Ressourcen wird möglicherweise modifiziert.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-190">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="fbdf4-191">Es ist relativ einfach, eine Web-API zu aktualisieren, damit sie neue Anforderungen verarbeiten kann. Sie müssen jedoch die Auswirkungen berücksichtigen, die derartige Änderungen auf Clientanwendungen haben, die die Web-API nutzen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-191">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="fbdf4-192">Zwar hat der Entwickler, der eine Web-API entwirft und implementiert, die vollständige Kontrolle über diese API, er hat allerdings nicht das gleiche Maß an Kontrolle über Clientanwendungen, die möglicherweise von Drittanbietern erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-192">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="fbdf4-193">Mit der Versionsverwaltung kann eine Web-API angeben, welche Features und Ressourcen sie bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-193">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="fbdf4-194">Eine Clientanwendung kann dann Anforderungen an eine bestimmte Version eines Features oder einer Ressource senden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-194">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="fbdf4-195">Es gibt verschiedene Methoden für das Implementieren einer Versionsverwaltung:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-195">There are several approaches to implement versioning:</span></span>

- <span data-ttu-id="fbdf4-196">URI-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fbdf4-196">URI versioning</span></span>

- <span data-ttu-id="fbdf4-197">Abfragezeichenfolgen-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fbdf4-197">Query string versioning</span></span>

- <span data-ttu-id="fbdf4-198">Header-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="fbdf4-198">Header versioning</span></span>

<span data-ttu-id="fbdf4-199">Abfragezeichenfolgen- und URI-Versionsverwaltungen lassen sich am einfachsten implementieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-199">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="fbdf4-200">Die Header-Versionsverwaltung ist ein guter Ansatz.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-200">Header versioning is a good approach.</span></span> <span data-ttu-id="fbdf4-201">Allerdings ist die Header-Versionsverwaltung nicht so explizit und einfach wie die URI-Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-201">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="fbdf4-202">Da die URI-Versionsverwaltung die einfachste und expliziteste Methode ist, wird sie auch in der Beispielanwendung eShopOnContainers verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-202">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="fbdf4-203">Mit der URI-Versionsverwaltung, die auch in der Beispielanwendung eShopOnContainers verwendet wird, wird bei jeder Änderung der Web-API oder des Ressourcenschemas für jede Ressource eine Versionsnummer zum URI hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-203">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="fbdf4-204">Vorhandene URI sollten weiterhin funktionieren wie zuvor und Ressourcen zurückgeben, die dem Schema entsprechen, das mit der angeforderten Version übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-204">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="fbdf4-205">Die Version kann wie im folgenden Codebeispiel mithilfe des Route-Attributs im Web-API-Controller festgelegt werden, wodurch die Version im URI explizit wird (in diesem Fall v1).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-205">As shown in the following code example, the version can be set by using the Route attribute in the Web API controller, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="fbdf4-206">Dieser Mechanismus für die Versionsverwaltung ist einfach und richtet sich nach dem Server, der die Anforderung an den entsprechenden Endpunkt weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-206">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="fbdf4-207">Für eine komplexere Versionsverwaltung und die beste Methode bei der Verwendung von REST sollten Sie jedoch Hypermedia verwenden und [HATEOAS (Hypertext as the Engine Of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources) implementieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-207">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fbdf4-208">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-208">Additional resources</span></span>

- <span data-ttu-id="fbdf4-209">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Versionsverwaltung von RESTful-Web-APIs in ASP.NET Core leicht gemacht)**  </span><span class="sxs-lookup"><span data-stu-id="fbdf4-209">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy** </span></span>\
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- <span data-ttu-id="fbdf4-210">**Versionsverwaltung einer RESTful-Web-API** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-210">**Versioning a RESTful web API** </span></span>\
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- <span data-ttu-id="fbdf4-211">**Roy Fielding. Versioning, Hypermedia, and REST (Versionsverwaltung, Hypermedia und REST)**  </span><span class="sxs-lookup"><span data-stu-id="fbdf4-211">**Roy Fielding. Versioning, Hypermedia, and REST** </span></span>\
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="fbdf4-212">Generieren von Swagger-Beschreibungsmetadaten aus Ihrer ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="fbdf4-212">Generating Swagger description metadata from your ASP.NET Core Web API</span></span>

<span data-ttu-id="fbdf4-213">[Swagger](https://swagger.io/) ist ein häufig verwendetes Open-Source-Framework, hinter dem ein großes Ökosystem von Tools steht, die Sie beim Entwerfen, Erstellen, Dokumentieren und Nutzen Ihrer RESTful-APIs unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-213">[Swagger](https://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="fbdf4-214">Swagger wird immer mehr zum Standard für die Beschreibungsmetadaten-Domäne von APIs.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-214">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="fbdf4-215">Wie im folgenden Abschnitt erläutert wird, sollten Sie Swagger-Beschreibungsmetadaten in sämtliche Arten von Microservices integrieren, d.h. sowohl in datengesteuerte Microservices als auch in komplexere domänengesteuerte Microservices.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-215">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="fbdf4-216">Das Herzstück von Swagger ist die Swagger-Spezifikation, bei der es sich um API-Beschreibungsmetadaten in einer JSON- oder YAML-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-216">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="fbdf4-217">Die Spezifikation erstellt den RESTful-Vertrag für Ihre API und legt die Details zu allen ihren Ressourcen und Vorgängen in einem visuell lesbaren und einem maschinenlesbaren Format für einfache Entwicklungs-, Ermittlungs- und Integrationsvorgänge fest.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-217">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="fbdf4-218">Die Spezifikation bildet die Grundlage für die OpenAPI Specification (OAS) und wird in einer offenen, transparenten und vernetzten Community entwickelt, um das Definieren von RESTful-Schnittstellen zu standardisieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-218">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="fbdf4-219">Die Spezifikation definiert die Struktur, wie ein Service ermittelt werden kann und wie seine Funktionen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-219">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="fbdf4-220">Weitere Informationen, einschließlich eines Web-Editors und Beispielen für Swagger-Spezifikationen von Firmen wie Spotify, Uber, Slack und Microsoft finden Sie auf der Webseite von Swagger (<https://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-220">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<https://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="fbdf4-221">Gründe für die Verwendung von Swagger</span><span class="sxs-lookup"><span data-stu-id="fbdf4-221">Why use Swagger?</span></span>

<span data-ttu-id="fbdf4-222">Im Folgenden werden die wichtigsten Gründe für das Generieren von Swagger-Metadaten für Ihre-APIs genannt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-222">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="fbdf4-223">**Möglichkeit für andere Produkte, Ihre APIs automatisch zu nutzen und zu integrieren**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-223">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="fbdf4-224">Dutzende von Produkten und [kommerziellen Tools](https://swagger.io/commercial-tools/) sowie viele [Bibliotheken und Frameworks](https://swagger.io/open-source-integrations/) unterstützen Swagger.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-224">Dozens of products and [commercial tools](https://swagger.io/commercial-tools/) and many [libraries and frameworks](https://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="fbdf4-225">Microsoft verfügt beispielsweise über die folgenden allgemeinen Produkte und Tools, die automatisch Swagger-basierte APIs nutzen können:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-225">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

- <span data-ttu-id="fbdf4-226">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-226">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="fbdf4-227">Sie können automatisch .NET-Clientklassen für den Aufruf von Swagger generieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-227">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="fbdf4-228">Dieses Tool kann von der CLI verwendet werden und integriert auch Visual Studio für eine benutzerfreundliche Verwendung über die GUI.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-228">This tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

- <span data-ttu-id="fbdf4-229">[Microsoft Flow](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-229">[Microsoft Flow](https://flow.microsoft.com/).</span></span> <span data-ttu-id="fbdf4-230">Ermöglicht die automatische [Verwendung und Integration Ihrer API](https://flow.microsoft.com/blog/integrating-custom-api/) in einen allgemeinen Workflow von Microsoft Flow, ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-230">You can automatically [use and integrate your API](https://flow.microsoft.com/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

- <span data-ttu-id="fbdf4-231">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-231">[Microsoft PowerApps](https://powerapps.microsoft.com/).</span></span> <span data-ttu-id="fbdf4-232">Sie können automatisch Ihre API aus [mobilen PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) nutzen, die mit [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/) erstellt wurden, ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-232">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/), with no programming skills required.</span></span>

- <span data-ttu-id="fbdf4-233">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="fbdf4-233">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="fbdf4-234">Sie können automatisch [Ihre API verwenden und in eine Azure App Service Logic App integrieren](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-234">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="fbdf4-235">**Möglichkeit zum automatischen Generieren einer API-Dokumentation**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-235">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="fbdf4-236">Bei der Erstellung umfangreicher RESTful-APIs wie komplexen auf Microservices basierenden Anwendungen müssen Sie zahlreiche Endpunkte mit unterschiedlichen Datenmodellen berücksichtigen, die in den Anforderungs- und Antwortnutzlasten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-236">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="fbdf4-237">Über die richtige Dokumentation und einen gut funktionierenden API-Explorer zu verfügen (wie es mit Swagger der Fall ist), ist der Schlüssel für den Erfolg Ihrer API und deren Annahme durch die Entwickler.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-237">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="fbdf4-238">Microsoft Flow, PowerApps und Azure Logic Apps verwenden die Metadaten von Swagger, um zu verstehen, wie APIs verwendet werden und die Verbindung zu ihnen hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-238">Swagger's metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

<span data-ttu-id="fbdf4-239">Es gibt mehrere Optionen zum Automatisieren der Swagger-Metadatengenerierung für ASP.NET Core-REST-API-Anwendungen in Form von auf *swagger-ui* basierenden funktionalen API-Hilfeseiten.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-239">There are several options to automate Swagger metadata generation for ASP.NET Core REST API applications, in the form of functional API help pages, based on *swagger-ui*.</span></span>

<span data-ttu-id="fbdf4-240">Die wohl bekannteste Option ist [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), was derzeit in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) verwendet wird und in diesem Leitfaden genauer erläutert wird. Es steht aber auch [NSwag](https://github.com/RSuter/NSwag) zur Verfügung, womit Typescript- und C\#-API-Clients sowie C\#-Controller aus einer Swagger- oder OpenAPI-Spezifikation und auch durch Scannen der DLL-Datei mit [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio), die die Controller enthält, generiert werden können.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-240">Probably the best know is [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) which is currently used in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) and we'll cover in some detail in this guide but there's also the option to use [NSwag](https://github.com/RSuter/NSwag), which can generate Typescript and C\# API clients, as well as C\# controllers, from a Swagger or OpenAPI specification and even by scanning the .dll that contains the controllers, using [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="fbdf4-241">Automatisieren der API-Swagger-Metadatengenerierung mit dem Swashbuckle-NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="fbdf4-241">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="fbdf4-242">Das manuelle Generieren von Swagger-Metadaten (in einer JSON- oder YAML-Datei) kann aufwendig sein.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-242">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="fbdf4-243">Sie können jedoch die API-Ermittlung von ASP.NET Web-API-Diensten automatisieren, indem Sie das [Swashbuckle-NuGet-Paket](https://aka.ms/swashbuckledotnetcore) verwenden, um Swagger-API-Metadaten dynamisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-243">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](https://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="fbdf4-244">Swashbuckle generiert automatisch Swagger-Metadaten für Ihre ASP.NET Web-API-Projekte.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-244">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="fbdf4-245">Es unterstützt neben ASP.NET Core-Web-API-Projekten und der traditionellen ASP.NET-Web-API auch Azure API App-, Azure Mobile App- und Azure Service Fabric-Microservices auf Basis von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-245">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="fbdf4-246">Es unterstützt ferner eine einfache Web-API für Container, wie sie in der Beispielanwendung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-246">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="fbdf4-247">Swashbuckle kombiniert API Explorer und Swagger oder [swagger-ui](https://github.com/swagger-api/swagger-ui), um Ihren API-Nutzern eine umfassende Ermittlungs- und Dokumentationserfahrung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-247">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="fbdf4-248">Zusätzlich zu seiner Engine für die Swagger-Metadatengenerierung umfasst Swashbuckle auch eine eingebettete Version von swagger-ui, die nach der Installation von Swashbuckle automatisch bereitsteht.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-248">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="fbdf4-249">Dies bedeutet, dass Sie Ihre API um eine benutzerfreundliche Ermittlungs-UI ergänzen können, die es Entwicklern leichter macht, Ihre API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-249">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="fbdf4-250">Da aufgrund der automatischen Generierung nur sehr wenig Code benötigt wird und der Wartungsaufwand gering ist, können Sie sich auf die Erstellung Ihrer API konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-250">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="fbdf4-251">Abbildung 6-8 zeigt das Ergebnis für den API Explorer.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-251">The result for the API Explorer looks like Figure 6-8.</span></span>

![Screenshot des Swagger-API-Explorers mit der eShopOContainers-API.](./media/data-driven-crud-microservice/swagger-metadata-eshoponcontainers-catalog-microservice.png)

<span data-ttu-id="fbdf4-253">**Abbildung 6-8**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-253">**Figure 6-8**.</span></span> <span data-ttu-id="fbdf4-254">Swashbuckle API Explorer auf Basis von Swagger-Metadaten – Microservice Katalog von eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="fbdf4-254">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="fbdf4-255">Die von Swashbuckle generierte Dokumentation der Swagger-Benutzeroberflächen-API enthält alle veröffentlichten Aktionen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-255">The Swashbuckle generated Swagger UI API documentation includes all published actions.</span></span> <span data-ttu-id="fbdf4-256">Der API Explorer hat hierbei nicht den höchsten Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-256">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="fbdf4-257">Sobald Sie über eine Web-API verfügen, die sich selbst in Swagger-Metadaten beschreiben kann, kann Ihre API nahtlos von Swagger-basierten Tools verwendet werden, einschließlich Client-Proxy-Klassencodegeneratoren, die für eine Vielzahl von Plattformen geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-257">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="fbdf4-258">Wie bereits erwähnt wurde, generiert beispielsweise [AutoRest](https://github.com/Azure/AutoRest) automatisch .NET-Clientklassen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-258">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="fbdf4-259">Es stehen jedoch zusätzliche Tools wie [swagger-codegen](https://github.com/swagger-api/swagger-codegen) zur Verfügung, die eine automatische Codegenerierung von API-Client-Bibliotheken, Server-Stubs und Dokumentation ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-259">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="fbdf4-260">Derzeit besteht Swashbuckle aus fünf NuGet-Paketen im allgemeinen Metapaket [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) für ASP.NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-260">Currently, Swashbuckle consists of five internal NuGet packages under the high-level meta- package [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) for ASP.NET Core applications.</span></span>

<span data-ttu-id="fbdf4-261">Nachdem Sie diese NuGet-Pakete in Ihrem Web-API-Projekt installiert haben, müssen Sie Swagger wie im folgenden **vereinfachten** Code gezeigt in der Startup-Klasse konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-261">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following **simplified** code:</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new OpenApiInfo
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

<span data-ttu-id="fbdf4-262">Anschließend können Sie Ihre Anwendung starten und die folgenden JSON- und UI-Endpunkte von Swagger mit URLs wie den folgenden durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="fbdf4-262">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```console
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

<span data-ttu-id="fbdf4-263">Die von Swashbuckle generierte UI für eine URL wie `http://<your-root-url>/swagger` wurde bereits oben gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-263">You previously saw the generated UI created by Swashbuckle for a URL like `http://<your-root-url>/swagger`.</span></span> <span data-ttu-id="fbdf4-264">In Abbildung 6-9 sehen Sie nun auch, wie Sie eine beliebige API-Methode testen können.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-264">In Figure 6-9 you can also see how you can test any API method.</span></span>

![Screenshot der Swagger-Benutzeroberfläche mit verfügbaren Testtools.](./media/data-driven-crud-microservice/swashbuckle-ui-testing.png)

<span data-ttu-id="fbdf4-266">**Abbildung 6-9**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-266">**Figure 6-9**.</span></span> <span data-ttu-id="fbdf4-267">Testen einer Swashbuckle-UI mit der API-Methode Katalog/Elemente</span><span class="sxs-lookup"><span data-stu-id="fbdf4-267">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="fbdf4-268">Die Detailansicht der Swagger-Benutzeroberflächen-API zeigt ein Beispiel der Antwort an und kann zum Ausführen der tatsächlichen API verwendet werden, was hilfreich für den Entwickler ist.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-268">The Swagger UI API detail shows a sample of the response and can be used to execute the real API, which is great for developer discovery.</span></span> <span data-ttu-id="fbdf4-269">Abbildung 6-10 zeigt die JSON-Metadaten von Swagger, die vom Microservice eShopOnContainers generiert werden (den die Tools im Hintergrund verwenden), wenn Sie `http://<your-root-url>/swagger/v1/swagger.json` mit [Postman](https://www.getpostman.com/) anfordern.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-269">Figure 6-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request `http://<your-root-url>/swagger/v1/swagger.json` using [Postman](https://www.getpostman.com/).</span></span>

![Screenshot einer Postman-Beispielbenutzeroberfläche mit JSON-Metadaten von Swagger.](./media/data-driven-crud-microservice/swagger-json-metadata.png)

<span data-ttu-id="fbdf4-271">**Abbildung 6-10**.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-271">**Figure 6-10**.</span></span> <span data-ttu-id="fbdf4-272">JSON-Metadaten von Swagger</span><span class="sxs-lookup"><span data-stu-id="fbdf4-272">Swagger JSON metadata</span></span>

<span data-ttu-id="fbdf4-273">Es ist wirklich so einfach.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-273">It is that simple.</span></span> <span data-ttu-id="fbdf4-274">Und da die Generierung automatisch erfolgt, wachsen Ihre Swagger-Metadaten mit, wenn Sie weitere Funktionen zu Ihrer API hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-274">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fbdf4-275">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-275">Additional resources</span></span>

- <span data-ttu-id="fbdf4-276">**ASP.NET-Web-API-Hilfeseiten mit Swagger** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-276">**ASP.NET Web API Help Pages using Swagger** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- <span data-ttu-id="fbdf4-277">**Erste Schritte mit Swashbuckle und ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-277">**Get started with Swashbuckle and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- <span data-ttu-id="fbdf4-278">**Erste Schritte mit NSwag und ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="fbdf4-278">**Get started with NSwag and ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> <span data-ttu-id="fbdf4-279">[Zurück](microservice-application-design.md)
> [Weiter](multi-container-applications-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="fbdf4-279">[Previous](microservice-application-design.md)
[Next](multi-container-applications-docker-compose.md)</span></span>
