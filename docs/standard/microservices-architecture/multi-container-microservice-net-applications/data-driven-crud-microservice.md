---
title: Erstellen eines einfachen datengesteuerten CRUD-Microservice
description: ".NET-Microservices-Architektur für .NET-Containeranwendungen | Erstellen eines einfachen datengesteuerten CRUD-Microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: be8644e45be8db88c99332476e74c5c968764c74
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="b15b4-104">Erstellen eines einfachen datengesteuerten CRUD-Microservice</span><span class="sxs-lookup"><span data-stu-id="b15b4-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="b15b4-105">Dieser Abschnitt beschreibt das Erstellen eines einfachen Microservice, der Erstell-, Lese-, Aktualisierungs- und Löschvorgänge (CRUD) für eine Datenquelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="b15b4-106">Entwerfen eines einfachen CRUD-Microservice</span><span class="sxs-lookup"><span data-stu-id="b15b4-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="b15b4-107">Aus Entwurfssicht ist diese Art eines Container-Microservice sehr einfach konzipiert.</span><span class="sxs-lookup"><span data-stu-id="b15b4-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="b15b4-108">Möglicherweise ist das zu lösende Problem einfach, oder bei der Implementierung handelt es sich nur um ein Proof of Concept.</span><span class="sxs-lookup"><span data-stu-id="b15b4-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="b15b4-109">**Abbildung 8-4.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-109">**Figure 8-4**.</span></span> <span data-ttu-id="b15b4-110">Interner Entwurf für einfache CRUD-Microservices</span><span class="sxs-lookup"><span data-stu-id="b15b4-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="b15b4-111">Ein Beispiel für diese Art eines einfachen datengesteuerten Service ist der Microservice Katalog aus der Beispielanwendung „eShopOnContainers“.</span><span class="sxs-lookup"><span data-stu-id="b15b4-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="b15b4-112">Dieser Servicetyp implementiert alle seine Funktionen in einem einzigen ASP.NET Core-Web-API-Projekt, das Klassen für sein Datenmodell, seine Geschäftslogik und seinen Datenzugriffscode enthält.</span><span class="sxs-lookup"><span data-stu-id="b15b4-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="b15b4-113">Außerdem speichert er seine zugehörigen Daten in einer Datenbank unter SQL Server (als weiterem Container für Dev/Testzwecke), es könnte sich aber – wie in Abbildung 8-5 gezeigt – auch um einen beliebigen regulären SQL Server-Host handeln.</span><span class="sxs-lookup"><span data-stu-id="b15b4-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="b15b4-114">**Abbildung 8-5.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-114">**Figure 8-5**.</span></span> <span data-ttu-id="b15b4-115">Einfacher datengesteuerter/CRUD-Microservice-Entwurf</span><span class="sxs-lookup"><span data-stu-id="b15b4-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="b15b4-116">Wenn Sie diese Art von Service entwickeln, benötigen Sie nur [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) und eine Datenzugriffs-API oder eine ORM wie [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="b15b4-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="b15b4-117">Sie könnten ferner, wie im nächsten Abschnitt erläutert, automatisch [Swagger](http://swagger.io/)-Metadaten über [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) generieren, um eine Beschreibung dessen bereitzustellen, was Ihr Service umfasst.</span><span class="sxs-lookup"><span data-stu-id="b15b4-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="b15b4-118">Beachten Sie, dass sich die Ausführung eines Datenbankservers wie SQL Server in einem Docker-Container gut für Entwicklungsumgebungen eignet, da alle Ihre Abhängigkeiten eingerichtet werden können, ohne dass Sie eine Datenbank in der Cloud oder lokal bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="b15b4-119">Dies ist sehr praktisch bei der Durchführung von Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="b15b4-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="b15b4-120">Allerdings wird dies für Produktionsumgebungen, die einen Datenbankserver in einem Container ausführen, nicht empfohlen, da Sie mit diesem Ansatz in der Regel keine Hochverfügbarkeit erzielen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="b15b4-121">Für eine Produktionsumgebung in Azure empfiehlt es sich, Azure SQL DB oder eine andere Datenbanktechnologie zu verwenden, die eine Hochverfügbarkeit und Skalierbarkeit bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="b15b4-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="b15b4-122">Für einen NoSQL-Ansatz könnten Sie beispielsweise DocumentDB wählen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="b15b4-123">Und schließlich können Sie durch Bearbeiten der Dockerfile-Datei und der docker-compose.yml-Metadatendateien konfigurieren, wie das Image dieses Containers erstellt wird, d.h. welches Basisimage es verwendet und welche Entwurfseinstellungen wie interne und externe Namen sowie TCP-Ports verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="b15b4-124">Implementieren eines einfachen CRUD-Microservice mit ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b15b4-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="b15b4-125">Um einen einfachen CRUD-Microservice mit .NET Core und Visual Studio zu implementieren, erstellen Sie zunächst – wie in Abbildung 8-6 gezeigt – ein einfaches ASP.NET Core-Web-API-Projekt (unter .NET Core, sodass es auf einem Linux-Docker-Host ausgeführt werden kann).</span><span class="sxs-lookup"><span data-stu-id="b15b4-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="b15b4-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="b15b4-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="b15b4-127">**Abbildung 8-6.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-127">**Figure 8-6**.</span></span> <span data-ttu-id="b15b4-128">Erstellen eines ASP.NET Core-Web-API-Projekts in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b15b4-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="b15b4-129">Nach dem Erstellen des Projekts können Sie Ihre MVC-Controller wie in jedem anderen Web-API-Projekt mit der Entity Framework-API oder einer anderen API implementieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="b15b4-130">In einem neuen Web-API-Projekt können Sie sehen, dass die einzige Abhängigkeit im betreffenden Microservice ASP.NET Core selbst betrifft.</span><span class="sxs-lookup"><span data-stu-id="b15b4-130">In a new Web API project, you can see that the only dependency you have in that microservice is on ASP.NET Core itself.</span></span> <span data-ttu-id="b15b4-131">Intern, innerhalb der Abhängigkeit `Microsoft.AspNetCore.All`, verweist diese auf Entity Framework und viele andere .NET Core-NuGet-Pakete, wie Abbildung 8-7 zeigt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-131">Internally, within the `Microsoft.AspNetCore.All` dependency, it is referencing Entity Framework and many other .NET Core Nuget packages, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="b15b4-132">**Abbildung 8-7.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-132">**Figure 8-7**.</span></span> <span data-ttu-id="b15b4-133">Abhängigkeiten in einem einfachen CRUD-Web-API-Microservice</span><span class="sxs-lookup"><span data-stu-id="b15b4-133">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="b15b4-134">Implementieren von CRUD-Web-API-Services mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="b15b4-134">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="b15b4-135">Entity Framework Core (EF Core) ist eine einfache, erweiterbare und plattformübergreifende Version der beliebten Entity Framework-Datenzugriffstechnologie.</span><span class="sxs-lookup"><span data-stu-id="b15b4-135">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="b15b4-136">EF Core ist eine objektrelationale Zuordnung (ORM, Object-Relational Mapper), die .NET-Entwicklern mithilfe von .NET-Objekten das Arbeiten mit einer Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b15b4-136">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="b15b4-137">Der Microservice Katalog verwendet EF und den SQL Server-Anbieter, da seine Datenbank in einem Container mit dem Image SQL Server for Linux Docker ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b15b4-137">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="b15b4-138">Allerdings könnte die Datenbank in einem beliebigen SQL Server wie Windows lokal oder Azure SQL DB bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-138">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="b15b4-139">Sie müssten lediglich die Verbindungszeichenfolge im ASP.NET Web API-Microservice ändern.</span><span class="sxs-lookup"><span data-stu-id="b15b4-139">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>


#### <a name="the-data-model"></a><span data-ttu-id="b15b4-140">Das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="b15b4-140">The data model</span></span>

<span data-ttu-id="b15b4-141">Bei EF Core erfolgt der Datenzugriff über ein Modell.</span><span class="sxs-lookup"><span data-stu-id="b15b4-141">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="b15b4-142">Ein Modell setzt sich aus Entitätsklassen und einem abgeleiteten Kontext zusammen, der eine Sitzung bei der Datenbank darstellt und Ihnen das Abfragen und Speichern von Daten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="b15b4-142">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="b15b4-143">Sie können ein Modell aus einer vorhandenen Datenbank generieren, ein Modell manuell anhand Ihrer Datenbank schreiben oder mithilfe von EF-Migrationen eine Datenbank aus Ihrem Modell erstellen (und im Laufe der Zeit gemäß den Veränderungen Ihres Modells weiterentwickeln).</span><span class="sxs-lookup"><span data-stu-id="b15b4-143">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="b15b4-144">Für den Microservice Katalog verwenden wir den letztgenannten Ansatz.</span><span class="sxs-lookup"><span data-stu-id="b15b4-144">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="b15b4-145">Das folgende Codebeispiel zeigt die Entitätsklasse CatalogItem. Hierbei handelt es sich um eine einfache POCO-Entitätsklasse ([Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)).</span><span class="sxs-lookup"><span data-stu-id="b15b4-145">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

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

<span data-ttu-id="b15b4-146">Darüber hinaus benötigen Sie einen DbContext, der eine Sitzung mit der Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-146">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="b15b4-147">Für den Microservice Katalog wird die CatalogContext-Klasse von der DbContext-Basisklasse abgeleitet, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="b15b4-147">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

<span data-ttu-id="b15b4-148">Zusätzliche `DbContext`-Implementierungen sind möglich.</span><span class="sxs-lookup"><span data-stu-id="b15b4-148">You can have additional `DbContext` implementations.</span></span> <span data-ttu-id="b15b4-149">Im als Beispiel dienenden Catalog.API-Microservice gibt es einen zweiten `DbContext` namens `CatalogContextSeed`. Hier werden automatisch die Beispieldaten beim ersten Zugriffsversuch auf die Datenbank aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-149">For example, in the sample Catalog.API microservice, there's a second `DbContext` named `CatalogContextSeed` where it automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="b15b4-150">Diese Methode ist auch für Demodaten und automatische Testszenarios nützlich.</span><span class="sxs-lookup"><span data-stu-id="b15b4-150">This method is useful for demo data and for automated testing scenarios, as well.</span></span> <span data-ttu-id="b15b4-151">Innerhalb von `DbContext` verwenden Sie die `OnModelCreating`-Methode, um Objekt-/Datenbank-Entitätszuordnungen mit anderen [EF-Erweiterungspunkten](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/) anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-151">Within the `DbContext`, you use the `OnModelCreating` method to customize object/database entity mappings with and other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="b15b4-152">Abfragen von Daten aus Web-API-Controllern</span><span class="sxs-lookup"><span data-stu-id="b15b4-152">Querying data from Web API controllers</span></span>

<span data-ttu-id="b15b4-153">Instanzen Ihrer Entitätsklassen werden üblicherweise – wie im nachstehenden Beispiel gezeigt – mit LINQ (Language Integrated Query) aus der Datenbank abgerufen:</span><span class="sxs-lookup"><span data-stu-id="b15b4-153">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context, 
                             IOptionsSnapshot<CatalogSettings> settings,
                             ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10, 
                                           [FromQuery]int pageIndex = 0)

    {
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

##### <a name="saving-data"></a><span data-ttu-id="b15b4-154">Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="b15b4-154">Saving data</span></span>

<span data-ttu-id="b15b4-155">Daten werden in der Datenbank mithilfe von Instanzen Ihrer Entitätsklassen erstellt, gelöscht und geändert.</span><span class="sxs-lookup"><span data-stu-id="b15b4-155">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="b15b4-156">Sie können Code wie im folgenden hartcodierten Beispiel (in diesem Fall Simulationsdaten) zu Ihren Web-API-Controllern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-156">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="b15b4-157">Abhängigkeitseinfügung in ASP.NET Core- und Web-API-Controllern</span><span class="sxs-lookup"><span data-stu-id="b15b4-157">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="b15b4-158">In ASP.NET Core können Sie die vorkonfigurierte Abhängigkeitseinfügung (DI, Dependency Injection) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-158">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="b15b4-159">Sie müssen keinen IoC-Container (Inversion of Control) eines Drittanbieters einrichten, können aber Ihren bevorzugten IoC-Container in die ASP.NET Core-Infrastruktur einbinden, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="b15b4-159">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="b15b4-160">In diesem Fall können Sie den erforderlichen EF-DBContext oder zusätzliche Repositorys direkt über den Controller-Konstruktor einfügen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-160">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="b15b4-161">Im obigen Beispiel für die `CatalogController`-Klasse fügen wir ein Objekt des `CatalogContext`-Typs und andere Objekte über den `CatalogController()`-Konstruktor ein.</span><span class="sxs-lookup"><span data-stu-id="b15b4-161">In the example above of the `CatalogController` class, we are injecting an object of `CatalogContext` type plus other objects through the `CatalogController()` constructor.</span></span>

<span data-ttu-id="b15b4-162">Ein wichtiger Konfigurationsschritt bei der Einrichtung des Web-API-Projekts ist die Registrierung der DbContext-Klasse im IoC-Container des Service.</span><span class="sxs-lookup"><span data-stu-id="b15b4-162">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="b15b4-163">Hierzu rufen Sie in der Regel in der `Startup`-Klasse die `services.AddDbContext<DbContext>()`-Methode innerhalb der `ConfigureServices()`-Methode auf, wie es im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="b15b4-163">You typically do so in the `Startup` class by calling the `services.AddDbContext<DbContext>()` method inside the `ConfigureServices()` method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
                   typeof(Startup).
                    GetTypeInfo().
                     Assembly.
                      GetName().Name);

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

### <a name="additional-resources"></a><span data-ttu-id="b15b4-164">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b15b4-164">Additional resources</span></span>

-   <span data-ttu-id="b15b4-165">**Abfragen von Daten**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="b15b4-165">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="b15b4-166">**Speichern von Daten**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="b15b4-166">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="b15b4-167">Die von Docker-Containern verwendete DB-Verbindungszeichenfolge und die Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="b15b4-167">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="b15b4-168">Wie im folgenden Beispiel gezeigt wird, können Sie die ASP.NET Core-Einstellungen verwenden und eine ConnectionString-Eigenschaft zu Ihrer Datei settings.json hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="b15b4-168">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

```csharp
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

<span data-ttu-id="b15b4-169">Die Datei settings.json kann Standardwerte für die ConnectionString-Eigenschaft oder für eine andere Eigenschaft enthalten.</span><span class="sxs-lookup"><span data-stu-id="b15b4-169">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="b15b4-170">Diese Eigenschaften werden jedoch durch die Werte der Umgebungsvariablen überschrieben, die Sie in der Datei docker-compose.override.yml angeben, wenn Sie Docker verwenden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-170">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file, when using Docker.</span></span>

<span data-ttu-id="b15b4-171">Aus Ihren Dateien docker-compose.yml oder docker-compose.override.yml können Sie diese Umgebungsvariablen initialisieren, damit Docker sie – wie anhand der nachstehenden Datei docker-compose.override.yml gezeigt – als OS-Umgebungsvariablen für Sie einrichtet. (Die Verbindungszeichenfolge und andere Zeilen in diesem Beispiel weisen einen Zeilenumbruch auf, was in Ihrer eigenen Codedatei jedoch nicht der Fall wäre.)</span><span class="sxs-lookup"><span data-stu-id="b15b4-171">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own code file).</span></span>

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

<span data-ttu-id="b15b4-172">Die docker-compose.yml-Dateien auf der Lösungsebene sind nicht nur flexibler als Konfigurationsdateien auf der Projekt- oder Microservice-Ebene, sondern auch sicherer, wenn Sie die in den docker-compose-Dateien deklarierten Umgebungsvariablen mit Werten überschreiben, die von Ihren Bereitstellungstools (z.B. VSTS-Docker-Bereitstellungsaufgaben) festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-172">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more but also more secure if you override the environment variables declared at the docker-compose files with values set from your deployment tools, like from VSTS Docker deployment tasks.</span></span> 

<span data-ttu-id="b15b4-173">Abschließend können Sie diesen Wert aus Ihrem Code abrufen, indem Sie Configuration\["ConnectionString"\] verwenden, wie es in der ConfigureServices-Methode in einem Codebeispiel weiter oben gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="b15b4-173">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="b15b4-174">Allerdings kann es für Produktionsumgebungen sinnvoll sein, zusätzliche Methoden zu untersuchen, wie sich Secrets wie die Verbindungszeichenfolgen speichern lassen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-174">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="b15b4-175">In der Regel erfolgt diese Verwaltung durch den von Ihnen gewählten Orchestrator, und Sie könnten hierfür beispielsweise die [Docker Swarm-Secretverwaltung](https://docs.docker.com/engine/swarm/secrets/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-175">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="b15b4-176">Implementieren einer Versionsverwaltung in ASP.NET Web-APIs</span><span class="sxs-lookup"><span data-stu-id="b15b4-176">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="b15b4-177">Wenn sich die Geschäftsanforderungen ändern, werden möglicherweise neue Sammlungen von Ressourcen hinzugefügt, die Beziehungen zwischen Ressourcen können sich ändern, und die Struktur der Daten in Ressourcen wird möglicherweise modifiziert.</span><span class="sxs-lookup"><span data-stu-id="b15b4-177">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="b15b4-178">Es ist relativ einfach, eine Web-API zu aktualisieren, damit sie neue Anforderungen verarbeiten kann. Sie müssen jedoch die Auswirkungen berücksichtigen, die derartige Änderungen auf Clientanwendungen haben, die die Web-API nutzen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-178">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="b15b4-179">Zwar hat der Entwickler, der eine Web-API entwirft und implementiert, die vollständige Kontrolle über diese API, er hat allerdings nicht das gleiche Maß an Kontrolle über Clientanwendungen, die möglicherweise von Drittanbietern erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-179">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="b15b4-180">Mit der Versionsverwaltung kann eine Web-API angeben, welche Features und Ressourcen sie bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-180">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="b15b4-181">Eine Clientanwendung kann dann Anforderungen an eine bestimmte Version eines Features oder einer Ressource senden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-181">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="b15b4-182">Es gibt verschiedene Methoden für das Implementieren einer Versionsverwaltung:</span><span class="sxs-lookup"><span data-stu-id="b15b4-182">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="b15b4-183">URI-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="b15b4-183">URI versioning</span></span>

-   <span data-ttu-id="b15b4-184">Abfragezeichenfolgen-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="b15b4-184">Query string versioning</span></span>

-   <span data-ttu-id="b15b4-185">Header-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="b15b4-185">Header versioning</span></span>

<span data-ttu-id="b15b4-186">Abfragezeichenfolgen- und URI-Versionsverwaltungen lassen sich am einfachsten implementieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-186">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="b15b4-187">Die Header-Versionsverwaltung ist ein guter Ansatz.</span><span class="sxs-lookup"><span data-stu-id="b15b4-187">Header versioning is a good approach.</span></span> <span data-ttu-id="b15b4-188">Allerdings ist die Header-Versionsverwaltung nicht so explizit und einfach wie die URI-Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="b15b4-188">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="b15b4-189">Da die URI-Versionsverwaltung die einfachste und expliziteste Methode ist, wird sie auch in der Beispielanwendung eShopOnContainers verwendet.</span><span class="sxs-lookup"><span data-stu-id="b15b4-189">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="b15b4-190">Mit der URI-Versionsverwaltung, die auch in der Beispielanwendung eShopOnContainers verwendet wird, wird bei jeder Änderung der Web-API oder des Ressourcenschemas für jede Ressource eine Versionsnummer zum URI hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-190">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="b15b4-191">Vorhandene URI sollten weiterhin funktionieren wie zuvor und Ressourcen zurückgeben, die dem Schema entsprechen, das mit der angeforderten Version übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-191">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="b15b4-192">Wie im folgenden Codebeispiel gezeigt wird, kann die Version mit dem Route-Attribut in der Web-API festgelegt werden, durch das die Version im URI explizit wird (in diesem Fall v1).</span><span class="sxs-lookup"><span data-stu-id="b15b4-192">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="b15b4-193">Dieser Mechanismus für die Versionsverwaltung ist einfach und richtet sich nach dem Server, der die Anforderung an den entsprechenden Endpunkt weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="b15b4-193">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="b15b4-194">Für eine komplexere Versionsverwaltung und die beste Methode bei der Verwendung von REST sollten Sie jedoch Hypermedia verwenden und [HATEOAS (Hypertext as the Engine Of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources) implementieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-194">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b15b4-195">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b15b4-195">Additional resources</span></span>

-   <span data-ttu-id="b15b4-196">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="b15b4-196">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="b15b4-197">**Versionsverwaltung einer RESTful-Web-API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="b15b4-197">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="b15b4-198">**Roy Fielding. Versioning, Hypermedia, and REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="b15b4-198">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="b15b4-199">Generieren von Swagger-Beschreibungsmetadaten aus Ihrer ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="b15b4-199">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="b15b4-200">[Swagger](http://swagger.io/) ist ein häufig verwendetes Open-Source-Framework, hinter dem ein großes Ökosystem von Tools steht, die Sie beim Entwerfen, Erstellen, Dokumentieren und Nutzen Ihrer RESTful-APIs unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-200">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="b15b4-201">Swagger wird immer mehr zum Standard für die Beschreibungsmetadaten-Domäne von APIs.</span><span class="sxs-lookup"><span data-stu-id="b15b4-201">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="b15b4-202">Wie im folgenden Abschnitt erläutert wird, sollten Sie Swagger-Beschreibungsmetadaten in sämtliche Arten von Microservices integrieren, d.h. sowohl in datengesteuerte Microservices als auch in komplexere domänengesteuerte Microservices.</span><span class="sxs-lookup"><span data-stu-id="b15b4-202">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="b15b4-203">Das Herzstück von Swagger ist die Swagger-Spezifikation, bei der es sich um API-Beschreibungsmetadaten in einer JSON- oder YAML-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-203">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="b15b4-204">Die Spezifikation erstellt den RESTful-Vertrag für Ihre API und legt die Details zu allen ihren Ressourcen und Vorgängen in einem visuell lesbaren und einem maschinenlesbaren Format für einfache Entwicklungs-, Ermittlungs- und Integrationsvorgänge fest.</span><span class="sxs-lookup"><span data-stu-id="b15b4-204">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="b15b4-205">Die Spezifikation bildet die Grundlage für die OpenAPI Specification (OAS) und wird in einer offenen, transparenten und vernetzten Community entwickelt, um das Definieren von RESTful-Schnittstellen zu standardisieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-205">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="b15b4-206">Die Spezifikation definiert die Struktur, wie ein Service ermittelt werden kann und wie seine Funktionen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-206">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="b15b4-207">Weitere Informationen, einschließlich eines Web-Editors und Beispielen für Swagger-Spezifikationen von Firmen wie Spotify, Uber, Slack und Microsoft finden Sie auf der Webseite von Swagger (<http://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="b15b4-207">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="b15b4-208">Gründe für die Verwendung von Swagger</span><span class="sxs-lookup"><span data-stu-id="b15b4-208">Why use Swagger?</span></span>

<span data-ttu-id="b15b4-209">Im Folgenden werden die wichtigsten Gründe für das Generieren von Swagger-Metadaten für Ihre-APIs genannt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-209">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="b15b4-210">**Möglichkeit für andere Produkte, Ihre APIs automatisch zu nutzen und zu integrieren**.</span><span class="sxs-lookup"><span data-stu-id="b15b4-210">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="b15b4-211">Dutzende von Produkten und [kommerziellen Tools](http://swagger.io/commercial-tools/) sowie viele [Bibliotheken und Frameworks](http://swagger.io/open-source-integrations/) unterstützen Swagger.</span><span class="sxs-lookup"><span data-stu-id="b15b4-211">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="b15b4-212">Microsoft verfügt beispielsweise über die folgenden allgemeinen Produkte und Tools, die automatisch Swagger-basierte APIs nutzen können:</span><span class="sxs-lookup"><span data-stu-id="b15b4-212">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="b15b4-213">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="b15b4-213">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="b15b4-214">Sie können automatisch .NET-Clientklassen für den Aufruf von Swagger generieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-214">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="b15b4-215">Dieses Tool kann von der CLI verwendet werden und integriert auch Visual Studio für eine benutzerfreundliche Verwendung über die GUI.</span><span class="sxs-lookup"><span data-stu-id="b15b4-215">This tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="b15b4-216">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="b15b4-216">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="b15b4-217">Ermöglicht die automatische [Verwendung und Integration Ihrer API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) in einen allgemeinen Workflow von Microsoft Flow, ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b15b4-217">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="b15b4-218">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="b15b4-218">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="b15b4-219">Sie können automatisch Ihre API aus [mobilen PowerApps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) nutzen, die mit [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/) erstellt wurden, ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b15b4-219">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="b15b4-220">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="b15b4-220">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="b15b4-221">Sie können automatisch [Ihre API verwenden und in eine Azure App Service Logic App integrieren](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), ohne dass hierzu Programmierkenntnisse erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b15b4-221">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="b15b4-222">**Möglichkeit zum automatischen Generieren einer API-Dokumentation**.</span><span class="sxs-lookup"><span data-stu-id="b15b4-222">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="b15b4-223">Bei der Erstellung umfangreicher RESTful-APIs wie komplexen auf Microservices basierenden Anwendungen müssen Sie zahlreiche Endpunkte mit unterschiedlichen Datenmodellen berücksichtigen, die in den Anforderungs- und Antwortnutzlasten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-223">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="b15b4-224">Über die richtige Dokumentation und einen gut funktionierenden API-Explorer zu verfügen (wie es mit Swagger der Fall ist), ist der Schlüssel für den Erfolg Ihrer API und deren Annahme durch die Entwickler.</span><span class="sxs-lookup"><span data-stu-id="b15b4-224">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="b15b4-225">Microsoft Flow, PowerApps, and Azure Logic Apps verwenden die Metadaten von Swagger, um zu verstehen, wie APIs verwendet werden und wie die Verbindung zu ihnen hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b15b4-225">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="b15b4-226">Automatisieren der API-Swagger-Metadatengenerierung mit dem Swashbuckle-NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="b15b4-226">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="b15b4-227">Das manuelle Generieren von Swagger-Metadaten (in einer JSON- oder YAML-Datei) kann aufwendig sein.</span><span class="sxs-lookup"><span data-stu-id="b15b4-227">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="b15b4-228">Sie können jedoch die API-Ermittlung von ASP.NET Web-API-Diensten automatisieren, indem Sie das [Swashbuckle-NuGet-Paket](http://aka.ms/swashbuckledotnetcore) verwenden, um Swagger-API-Metadaten dynamisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-228">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="b15b4-229">Swashbuckle generiert automatisch Swagger-Metadaten für Ihre ASP.NET Web-API-Projekte.</span><span class="sxs-lookup"><span data-stu-id="b15b4-229">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="b15b4-230">Es unterstützt neben ASP.NET Core-Web-API-Projekten und der traditionellen ASP.NET-Web-API auch Azure API App-, Azure Mobile App- und Azure Service Fabric-Microservices auf Basis von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b15b4-230">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="b15b4-231">Es unterstützt ferner eine einfache Web-API für Container, wie sie in der Beispielanwendung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b15b4-231">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="b15b4-232">Swashbuckle kombiniert API Explorer und Swagger oder [swagger-ui](https://github.com/swagger-api/swagger-ui), um Ihren API-Nutzern eine umfassende Ermittlungs- und Dokumentationserfahrung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="b15b4-232">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="b15b4-233">Zusätzlich zu seiner Engine für die Swagger-Metadatengenerierung umfasst Swashbuckle auch eine eingebettete Version von swagger-ui, die nach der Installation von Swashbuckle automatisch bereitsteht.</span><span class="sxs-lookup"><span data-stu-id="b15b4-233">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="b15b4-234">Dies bedeutet, dass Sie Ihre API um eine benutzerfreundliche Ermittlungs-UI ergänzen können, die es Entwicklern leichter macht, Ihre API zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b15b4-234">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="b15b4-235">Da aufgrund der automatischen Generierung nur sehr wenig Code benötigt wird und der Wartungsaufwand gering ist, können Sie sich auf die Erstellung Ihrer API konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="b15b4-235">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="b15b4-236">Abbildung 8-8 zeigt das Ergebnis für den API Explorer.</span><span class="sxs-lookup"><span data-stu-id="b15b4-236">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="b15b4-237">**Abbildung 8-8.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-237">**Figure 8-8**.</span></span> <span data-ttu-id="b15b4-238">Swashbuckle API Explorer auf Basis von Swagger-Metadaten – Microservice Katalog von eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="b15b4-238">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="b15b4-239">Der API Explorer hat hierbei nicht den höchsten Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="b15b4-239">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="b15b4-240">Sobald Sie über eine Web-API verfügen, die sich selbst in Swagger-Metadaten beschreiben kann, kann Ihre API nahtlos von Swagger-basierten Tools verwendet werden, einschließlich Client-Proxy-Klassencodegeneratoren, die für eine Vielzahl von Plattformen geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="b15b4-240">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="b15b4-241">Wie bereits erwähnt wurde, generiert beispielsweise [AutoRest](https://github.com/Azure/AutoRest) automatisch .NET-Clientklassen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-241">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="b15b4-242">Es stehen jedoch zusätzliche Tools wie [swagger-codegen](https://github.com/swagger-api/swagger-codegen) zur Verfügung, die eine automatische Codegenerierung von API-Client-Bibliotheken, Server-Stubs und Dokumentation ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-242">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="b15b4-243">Derzeit besteht Swashbuckle aus zwei internen NuGet-Paketen im allgemeinen Meta-Paket [Swashbuckle.Swashbuckle.AspNetCoreSwaggerGen](https://www.nuget.org/packages/Swashbuckle.AspNetCore/) Version 1.0.0 oder höher für ASP.NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-243">Currently, Swashbuckle consists of two several internal NuGet packages under the high-level meta- package [Swashbuckle.Swashbuckle.AspNetCoreSwaggerGen](https://www.nuget.org/packages/Swashbuckle.AspNetCore/) version 1.0.0 or later for ASP.NET Core applications.</span></span>

<span data-ttu-id="b15b4-244">Nachdem Sie diese NuGet-Pakete in Ihrem Web-API-Projekt installiert haben, müssen Sie Swagger wie im folgenden Code gezeigt in der Startup-Klasse konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="b15b4-244">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

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
            options.SwaggerDoc("v1", new Swashbuckle.AspNetCore.Swagger.Info
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample",
                TermsOfService = "Terms Of Service"
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

<span data-ttu-id="b15b4-245">Anschließend können Sie Ihre Anwendung starten und die folgenden JSON- und UI-Endpunkte von Swagger mit URLs wie den folgenden durchsuchen:</span><span class="sxs-lookup"><span data-stu-id="b15b4-245">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/
```

<span data-ttu-id="b15b4-246">Die von Swashbuckle generierte UI für eine URL wie http://&lt;your-root-url&gt;/swagger/ui wurde bereits oben gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b15b4-246">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="b15b4-247">In Abbildung 8-9 sehen Sie nun auch, wie Sie eine beliebige API-Methode testen können.</span><span class="sxs-lookup"><span data-stu-id="b15b4-247">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="b15b4-248">**Abbildung 8-9.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-248">**Figure 8-9**.</span></span> <span data-ttu-id="b15b4-249">Testen einer Swashbuckle-UI mit der API-Methode Katalog/Elemente</span><span class="sxs-lookup"><span data-stu-id="b15b4-249">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="b15b4-250">Abbildung 8-10 zeigt die JSON-Metadaten von Swagger, die vom Microservice eShopOnContainers generiert wurde (den die Tools im Hintergrund verwenden), wenn Sie &lt;your-root-url&gt;/swagger/v1/swagger.json mit [Postman](https://www.getpostman.com/) anfordern.</span><span class="sxs-lookup"><span data-stu-id="b15b4-250">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="b15b4-251">**Abbildung 8-10.**</span><span class="sxs-lookup"><span data-stu-id="b15b4-251">**Figure 8-10**.</span></span> <span data-ttu-id="b15b4-252">JSON-Metadaten von Swagger</span><span class="sxs-lookup"><span data-stu-id="b15b4-252">Swagger JSON metadata</span></span>

<span data-ttu-id="b15b4-253">Es ist wirklich so einfach.</span><span class="sxs-lookup"><span data-stu-id="b15b4-253">It is that simple.</span></span> <span data-ttu-id="b15b4-254">Und da die Generierung automatisch erfolgt, wachsen Ihre Swagger-Metadaten mit, wenn Sie weitere Funktionen zu Ihrer API hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b15b4-254">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b15b4-255">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b15b4-255">Additional resources</span></span>

-   <span data-ttu-id="b15b4-256">**ASP.NET Core-Web-API-Hilfeseiten mit Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="b15b4-256">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b15b4-257">[Zurück] (microservice-application-design.md) [Weiter] (multi-container-applications-docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="b15b4-257">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
