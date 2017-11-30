---
title: Erstellen einer einfachen datengesteuerte CRUD-microservice
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Erstellen einer einfachen datengesteuerte CRUD-microservice"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b814d344f2c78e7cf57f9e2896cf1d6b52db38d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a><span data-ttu-id="5786f-104">Erstellen einer einfachen datengesteuerte CRUD-microservice</span><span class="sxs-lookup"><span data-stu-id="5786f-104">Creating a simple data-driven CRUD microservice</span></span>

<span data-ttu-id="5786f-105">Dieser Abschnitt beschreibt wie die Erstellung eine einfachen Microservice, der ausführt erstellen, lesen, Update- und Löschvorgänge (CRUD) für eine Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="5786f-105">This section outlines how to create a simple microservice that performs create, read, update, and delete (CRUD) operations on a data source.</span></span>

## <a name="designing-a-simple-crud-microservice"></a><span data-ttu-id="5786f-106">Entwerfen eine einfache CRUD-microservice</span><span class="sxs-lookup"><span data-stu-id="5786f-106">Designing a simple CRUD microservice</span></span>

<span data-ttu-id="5786f-107">Aus Sicht des ein Entwurf ist diese Art von Datenvolumes Microservice sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="5786f-107">From a design point of view, this type of containerized microservice is very simple.</span></span> <span data-ttu-id="5786f-108">Möglicherweise das Problem zu lösen einfach ist oder die Implementierung ist möglicherweise nur ein Proof of Concept.</span><span class="sxs-lookup"><span data-stu-id="5786f-108">Perhaps the problem to solve is simple, or perhaps the implementation is only a proof of concept.</span></span>

![](./media/image4.png)

<span data-ttu-id="5786f-109">**Abbildung 8-4**.</span><span class="sxs-lookup"><span data-stu-id="5786f-109">**Figure 8-4**.</span></span> <span data-ttu-id="5786f-110">Interne Entwurf für einfache CRUD-microservices</span><span class="sxs-lookup"><span data-stu-id="5786f-110">Internal design for simple CRUD microservices</span></span>

<span data-ttu-id="5786f-111">Ein Beispiel für diese Art von einfachen Datenlaufwerk-Dienst ist der Katalog Microservice aus der eShopOnContainers-beispielanwendung.</span><span class="sxs-lookup"><span data-stu-id="5786f-111">An example of this kind of simple data-drive service is the catalog microservice from the eShopOnContainers sample application.</span></span> <span data-ttu-id="5786f-112">Dieser Typ des Diensts implementiert alle seine Funktionalität in einem einzelnen ASP.NET Core Web-API-Projekt, das Klassen für das zugeordnete Datenmodell, die Geschäftslogik und seine Datenzugriffscode enthält.</span><span class="sxs-lookup"><span data-stu-id="5786f-112">This type of service implements all its functionality in a single ASP.NET Core Web API project that includes classes for its data model, its business logic, and its data access code.</span></span> <span data-ttu-id="5786f-113">Außerdem speichert ihre verknüpften Daten in einer Datenbank in SQL Server (als einen anderen Container für Dev/Testzwecke) ausgeführt, aber unter Umständen liegen auch alle regulären SQL Server-Host, wie in Abbildung 8 – 5 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5786f-113">It also stores its related data in a database running in SQL Server (as another container for dev/test purposes), but could also be any regular SQL Server host, as shown in Figure 8-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="5786f-114">**Abbildung 8 – 5**.</span><span class="sxs-lookup"><span data-stu-id="5786f-114">**Figure 8-5**.</span></span> <span data-ttu-id="5786f-115">Einfache Data-driven/CRUD-Microservice Entwurf</span><span class="sxs-lookup"><span data-stu-id="5786f-115">Simple data-driven/CRUD microservice design</span></span>

<span data-ttu-id="5786f-116">Wenn Sie diese Art von Dienst entwickeln, müssen Sie nur [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) und wie eine Datenzugriffs-API oder ORM- [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span><span class="sxs-lookup"><span data-stu-id="5786f-116">When you are developing this kind of service, you only need [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) and a data-access API or ORM like [Entity Framework Core](https://docs.microsoft.com/ef/core/index).</span></span> <span data-ttu-id="5786f-117">Sie können auch generieren [Swagger](http://swagger.io/) Metadaten automatisch über [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) zu beschreiben, was Ihren Dienst anbietet, wie im nächsten Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="5786f-117">You could also generate [Swagger](http://swagger.io/) metadata automatically through [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) to provide a description of what your service offers, as explained in the next section.</span></span>

<span data-ttu-id="5786f-118">Beachten Sie, dass ausführen, einen Datenbankserver, z. B. SQL Server in einem Docker-Container für entwicklungsumgebungen, schwerwiegend sind, da Sie alle Ihre Abhängigkeiten, einrichten aufweisen darf und ohne eine Datenbank in der Cloud oder lokal bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5786f-118">Note that running a database server like SQL Server within a Docker container is great for development environments, because you can have all your dependencies up and running without needing to provision a database in the cloud or on-premises.</span></span> <span data-ttu-id="5786f-119">Dies ist sehr praktisch, wenn Integration ausgeführt testet.</span><span class="sxs-lookup"><span data-stu-id="5786f-119">This is very convenient when running integration tests.</span></span> <span data-ttu-id="5786f-120">Allerdings ist für produktionsumgebungen, die eine Datenbank in einem Container ausführen nicht empfohlen, da Sie hohen Verfügbarkeit mit diesen Ansatz in der Regel nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="5786f-120">However, for production environments, running a database server in a container is not recommended, because you usually do not get high availability with that approach.</span></span> <span data-ttu-id="5786f-121">Für eine produktionsumgebung in Azure empfiehlt es sich die Verwendung von Azure SQL-Datenbank oder eine andere datenbanktechnologie, die hohe Verfügbarkeit und hoher Skalierbarkeit bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="5786f-121">For a production environment in Azure, it is recommended that you use Azure SQL DB or any other database technology that can provide high availability and high scalability.</span></span> <span data-ttu-id="5786f-122">Beispielsweise können Sie für einen NoSQL-Ansatz DocumentDB auswählen.</span><span class="sxs-lookup"><span data-stu-id="5786f-122">For example, for a NoSQL approach, you might choose DocumentDB.</span></span>

<span data-ttu-id="5786f-123">Schließlich können Sie durch Bearbeiten der dockerfile-Datei und Docker-compose.yml-Metadatendateien, erstellen das Image dieses Containers konfigurieren – welche Basisimage es verwenden, sowie Einstellungen wie z. B. interne und externe Namen und TCP-Ports zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="5786f-123">Finally, by editing the Dockerfile and docker-compose.yml metadata files, you can configure how the image of this container will be created—what base image it will use, plus design settings such as internal and external names and TCP ports.</span></span> 

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a><span data-ttu-id="5786f-124">Implementieren eine einfache CRUD-Microservice mit ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5786f-124">Implementing a simple CRUD microservice with ASP.NET Core</span></span>

<span data-ttu-id="5786f-125">Um eine einfache CRUD-Microservice mit .NET Core und Visual Studio zu implementieren, zunächst erstellen Sie ein einfaches ASP.NET Core Web-API-Projekt (ausgeführt .NET Core, damit es auf einem Linux-Docker-Host ausgeführt werden kann), als Abbildung 8 – 6.</span><span class="sxs-lookup"><span data-stu-id="5786f-125">To implement a simple CRUD microservice using .NET Core and Visual Studio, you start by creating a simple ASP.NET Core Web API project (running on .NET Core so it can run on a Linux Docker host), as shown in Figure 8-6.</span></span>

  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------
  <span data-ttu-id="5786f-126">![](./media/image6.png)   ![](./media/image7.png)</span><span class="sxs-lookup"><span data-stu-id="5786f-126">![](./media/image6.png)   ![](./media/image7.png)</span></span>
  ------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------

<span data-ttu-id="5786f-127">**Abbildung 8 – 6**.</span><span class="sxs-lookup"><span data-stu-id="5786f-127">**Figure 8-6**.</span></span> <span data-ttu-id="5786f-128">Erstellen ein ASP.NET Core Web-API-Projekt in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5786f-128">Creating an ASP.NET Core Web API project in Visual Studio</span></span>

<span data-ttu-id="5786f-129">Nach dem Erstellen des Projekts, können Sie die MVC-Controller implementieren, wie in jedem anderen Web-API-Projekt mit dem Entity Framework-API oder anderen-API.</span><span class="sxs-lookup"><span data-stu-id="5786f-129">After creating the project, you can implement your MVC controllers as you would in any other Web API project, using the Entity Framework API or other API.</span></span> <span data-ttu-id="5786f-130">EShopOnContainers.Catalog.API im Projekt können Sie sehen, die wichtigsten Abhängigkeiten für diese Microservice nur ASP.NET Core selbst, Entity Framework und Swashbuckle, wie in Abbildung 8 – 7 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5786f-130">In the eShopOnContainers.Catalog.API project, you can see that the main dependencies for that microservice are just ASP.NET Core itself, Entity Framework, and Swashbuckle, as shown in Figure 8-7.</span></span>

![](./media/image8.PNG)

<span data-ttu-id="5786f-131">**Abbildung 8 – 7**.</span><span class="sxs-lookup"><span data-stu-id="5786f-131">**Figure 8-7**.</span></span> <span data-ttu-id="5786f-132">Abhängigkeiten in eine einfache CRUD-Web-API-microservice</span><span class="sxs-lookup"><span data-stu-id="5786f-132">Dependencies in a simple CRUD Web API microservice</span></span>

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a><span data-ttu-id="5786f-133">Implementieren von CRUD-Web-API-Diensten mit Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="5786f-133">Implementing CRUD Web API services with Entity Framework Core</span></span>

<span data-ttu-id="5786f-134">Entity Framework (EF) Core ist eine einfache, die erweiterbar sind, und plattformübergreifende-Version des beliebten Entity Framework-Daten zugreifen, Technologie.</span><span class="sxs-lookup"><span data-stu-id="5786f-134">Entity Framework (EF) Core is a lightweight, extensible, and cross-platform version of the popular Entity Framework data access technology.</span></span> <span data-ttu-id="5786f-135">EF Core handelt es sich um eine objektrelationale Mapper (ORM), die .NET Entwicklern mit einer Datenbank mithilfe von .NET Objekten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5786f-135">EF Core is an object-relational mapper (ORM) that enables .NET developers to work with a database using .NET objects.</span></span>

<span data-ttu-id="5786f-136">Der Katalog Microservice verwendet EF und SQL Server-Anbieter, weil die Datenbank in einem Container mit dem SQL Server für Linux-Docker-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5786f-136">The catalog microservice uses EF and the SQL Server provider because its database is running in a container with the SQL Server for Linux Docker image.</span></span> <span data-ttu-id="5786f-137">Allerdings kann die Datenbank in SQL Server, z. B. Windows on-Premises oder Azure SQL-Datenbank bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5786f-137">However, the database could be deployed into any SQL Server, such as Windows on-premises or Azure SQL DB.</span></span> <span data-ttu-id="5786f-138">Das einzige gewünschten ändern, ist die Verbindungszeichenfolge in der ASP.NET Web API Microservice.</span><span class="sxs-lookup"><span data-stu-id="5786f-138">The only thing you would need to change is the connection string in the ASP.NET Web API microservice.</span></span>

#### <a name="add-entity-framework-core-to-your-dependencies"></a><span data-ttu-id="5786f-139">Fügen Sie Entity Framework Core hinzu, um Ihre Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="5786f-139">Add Entity Framework Core to your dependencies</span></span>

<span data-ttu-id="5786f-140">Sie können das NuGet-Paket für den Datenbankanbieter installieren, in diesem Fall SQL Server, von innerhalb der Visual Studio-IDE oder mit der NuGet-Konsole verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5786f-140">You can install the NuGet package for the database provider you want to use, in this case SQL Server, from within the Visual Studio IDE or with the NuGet console.</span></span> <span data-ttu-id="5786f-141">Verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="5786f-141">Use the following command:</span></span>

```
  Install-Package Microsoft.EntityFrameworkCore.SqlServer
```

#### <a name="the-data-model"></a><span data-ttu-id="5786f-142">Das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="5786f-142">The data model</span></span>

<span data-ttu-id="5786f-143">Datenzugriff erfolgt mit EF-Kern mithilfe eines Modells.</span><span class="sxs-lookup"><span data-stu-id="5786f-143">With EF Core, data access is performed by using a model.</span></span> <span data-ttu-id="5786f-144">Ein Modell besteht aus der Entitätsklasse und an einem abgeleiteten Kontext, der eine Sitzung mit der Datenbank, sodass Sie Abfragen und Speichern von Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="5786f-144">A model is made up of entity classes and a derived context that represents a session with the database, allowing you to query and save data.</span></span> <span data-ttu-id="5786f-145">Sie können Generieren eines Modells aus einer vorhandenen Datenbank, manuell ein Modell, um Ihre Datenbank zu entsprechen, code und EF-Migrationen verwenden, um eine Datenbank aus dem Modell erstellen (und entwickeln sie, während das Modell im Zeitverlauf ändert).</span><span class="sxs-lookup"><span data-stu-id="5786f-145">You can generate a model from an existing database, manually code a model to match your database, or use EF migrations to create a database from your model (and evolve it as your model changes over time).</span></span> <span data-ttu-id="5786f-146">Für den Katalog Microservice verwenden wir den letzten Ansatz.</span><span class="sxs-lookup"><span data-stu-id="5786f-146">For the catalog microservice we are using the last approach.</span></span> <span data-ttu-id="5786f-147">Sehen Sie ein Beispiel für die Entitätsklasse CatalogItem im folgenden Codebeispiel wird eine einfache Plain Old-CLR-Objekt ist ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) Entitätsklasse.</span><span class="sxs-lookup"><span data-stu-id="5786f-147">You can see an example of the CatalogItem entity class in the following code example, which is a simple Plain Old CLR Object ([POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)) entity class.</span></span>

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public CatalogItem() { }
}
```

<span data-ttu-id="5786f-148">Darüber hinaus benötigen Sie ein ' DbContext ', die eine Sitzung mit der Datenbank darstellt.</span><span class="sxs-lookup"><span data-stu-id="5786f-148">You also need a DbContext that represents a session with the database.</span></span> <span data-ttu-id="5786f-149">Für den Katalog Microservice wird die CatalogContext-Klasse von der Basisklasse von ' DbContext ' abgeleitet, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5786f-149">For the catalog microservice, the CatalogContext class derives from the DbContext base class, as shown in the following example:</span></span>

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

<span data-ttu-id="5786f-150">Die Implementierung von ' DbContext ' kann kein zusätzlichen Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="5786f-150">You can have additional code in the DbContext implementation.</span></span> <span data-ttu-id="5786f-151">Beispielsweise haben in der beispielanwendung wir eine OnModelCreating-Methode in der CatalogContext-Klasse, die automatisch die Beispieldaten beim ersten versucht wird auffüllen, auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5786f-151">For example, in the sample application, we have an OnModelCreating method in the CatalogContext class that automatically populates the sample data the first time it tries to access the database.</span></span> <span data-ttu-id="5786f-152">Diese Methode ist nützlich für Demodaten.</span><span class="sxs-lookup"><span data-stu-id="5786f-152">This method is useful for demo data.</span></span> <span data-ttu-id="5786f-153">Sie können auch die OnModelCreating-Methode verwenden, zum Anpassen der Objekt-Datenbank Entität Zuordnungen mit vielen anderen [EF Erweiterungspunkte](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span><span class="sxs-lookup"><span data-stu-id="5786f-153">You can also use the OnModelCreating method to customize object/database entity mappings with many other [EF extensibility points](https://blogs.msdn.microsoft.com/dotnet/2016/09/29/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).</span></span>

<span data-ttu-id="5786f-154">Sie können weitere Details zu OnModelCreating in der [Implementieren der Infrastruktur Persistenzebene mit Entity Framework Core](#implementing_infrastructure_persistence) Abschnitt weiter unten in diesem Buch.</span><span class="sxs-lookup"><span data-stu-id="5786f-154">You can see further details about OnModelCreating in the [Implementing the infrastructure-persistence layer with Entity Framework Core](#implementing_infrastructure_persistence) section later in this book.</span></span>

##### <a name="querying-data-from-web-api-controllers"></a><span data-ttu-id="5786f-155">Abfragen von Daten aus der Web-API-Controller</span><span class="sxs-lookup"><span data-stu-id="5786f-155">Querying data from Web API controllers</span></span>

<span data-ttu-id="5786f-156">Instanzen von die Entitätsklassen werden in der Regel mit Language Integrated Query (LINQ), aus der Datenbank abgerufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5786f-156">Instances of your entity classes are typically retrieved from the database using Language Integrated Query (LINQ), as shown in the following example:</span></span>

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
        _catalogIntegrationEventService = catalogIntegrationEventService ??
           throw new ArgumentNullException(nameof(catalogIntegrationEventService));
        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
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

##### <a name="saving-data"></a><span data-ttu-id="5786f-157">Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="5786f-157">Saving data</span></span>

<span data-ttu-id="5786f-158">Daten werden erstellt, gelöscht und mit Instanzen von Klassen für die Entitäten in der Datenbank geändert.</span><span class="sxs-lookup"><span data-stu-id="5786f-158">Data is created, deleted, and modified in the database using instances of your entity classes.</span></span> <span data-ttu-id="5786f-159">Sie können Code wie im folgenden hartcodierte Beispiel (in diesem Fall simulierten Daten) auf Ihre Web-API-Controller hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5786f-159">You could add code like the following hard-coded example (mock data, in this case) to your Web API controllers.</span></span>

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
   Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a><span data-ttu-id="5786f-160">Abhängigkeitsinjektion in ASP.NET Core und Web-API-Controller</span><span class="sxs-lookup"><span data-stu-id="5786f-160">Dependency Injection in ASP.NET Core and Web API controllers</span></span>

<span data-ttu-id="5786f-161">Verwenden Sie in ASP.NET Core (Dependency Injection, DI) ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5786f-161">In ASP.NET Core you can use Dependency Injection (DI) out of the box.</span></span> <span data-ttu-id="5786f-162">Sie müssen nicht Einrichten einer Drittanbieter-Inversion of Control (IoC) Container, obwohl Sie Ihre bevorzugten IoC-Container in ASP.NET Core-Infrastruktur eingebunden werden können, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="5786f-162">You do not need to set up a third-party Inversion of Control (IoC) container, although you can plug your preferred IoC container into the ASP.NET Core infrastructure if you want.</span></span> <span data-ttu-id="5786f-163">In diesem Fall bedeutet dies, dass Sie die erforderlichen EF DBContext oder zusätzliche Repositorys über die Controller-Konstruktor direkt einfügen können.</span><span class="sxs-lookup"><span data-stu-id="5786f-163">In this case, it means that you can directly inject the required EF DBContext or additional repositories through the controller constructor.</span></span> <span data-ttu-id="5786f-164">Im obigen Beispiel der CatalogController-Klasse werden wir ein Objekt des Typs CatalogContext sowie andere Objekte über den Konstruktor CatalogController injiziert.</span><span class="sxs-lookup"><span data-stu-id="5786f-164">In the example above of the CatalogController class, we are injecting an object of CatalogContext type plus other objects through the CatalogController constructor.</span></span>

<span data-ttu-id="5786f-165">Eine wichtige Konfiguration in der Web-API-Projekt eingerichtet ist, die Registrierung des DbContext-Klasse in den Dienst IoC-Container.</span><span class="sxs-lookup"><span data-stu-id="5786f-165">An important configuration to set up in the Web API project is the DbContext class registration into the service’s IoC container.</span></span> <span data-ttu-id="5786f-166">Sie dazu in der Regel die Startklasse. durch Aufrufen von Diensten. AddDbContext Methode innerhalb der ConfigureServices-Methode, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="5786f-166">You typically do so in the Startup class by calling the services.AddDbContext method inside the ConfigureServices method, as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
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

### <a name="additional-resources"></a><span data-ttu-id="5786f-167">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5786f-167">Additional resources</span></span>

-   <span data-ttu-id="5786f-168">**Abfragen von Daten**
    [*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span><span class="sxs-lookup"><span data-stu-id="5786f-168">**Querying Data**
[*https://docs.microsoft.com/ef/core/querying/index*](https://docs.microsoft.com/ef/core/querying/index)</span></span>

-   <span data-ttu-id="5786f-169">**Speichern von Daten**
    [*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span><span class="sxs-lookup"><span data-stu-id="5786f-169">**Saving Data**
[*https://docs.microsoft.com/ef/core/saving/index*](https://docs.microsoft.com/ef/core/saving/index)</span></span>

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a><span data-ttu-id="5786f-170">Die von Docker-Containern verwendet DB-Verbindungs-Zeichenfolge und Umgebung Variablen</span><span class="sxs-lookup"><span data-stu-id="5786f-170">The DB connection string and environment variables used by Docker containers</span></span>

<span data-ttu-id="5786f-171">Sie können ASP.NET Core Einstellungen verwendet und eine ConnectionString-Eigenschaft der settings.json-Datei wie im folgenden Beispiel gezeigt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5786f-171">You can use the ASP.NET Core settings and add a ConnectionString property to your settings.json file as shown in the following example:</span></span>

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

<span data-ttu-id="5786f-172">Die Datei settings.json kann Standardwerte für die ConnectionString-Eigenschaft oder eine andere Eigenschaft haben.</span><span class="sxs-lookup"><span data-stu-id="5786f-172">The settings.json file can have default values for the ConnectionString property or for any other property.</span></span> <span data-ttu-id="5786f-173">Diese Eigenschaften werden jedoch mithilfe der Werte der Umgebungsvariablen überschrieben werden, die Sie in der Docker-compose.override.yml-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="5786f-173">However, those properties will be overridden by the values of environment variables that you specify in the docker-compose.override.yml file.</span></span>

<span data-ttu-id="5786f-174">Aus Docker compose.yml oder Docker compose.override.yml Dateien können Sie diese Umgebungsvariablen zu initialisieren, damit diese Docker sie als OS-Umgebungsvariablen für Sie eingerichtet wird wie gezeigt in der folgenden Docker-compose.override.yml-Datei (die Verbindung Zeichenfolge und andere Zeilen in diesem Beispiel zu umschließen, aber es würde nicht in eine eigene Datei umschließen).</span><span class="sxs-lookup"><span data-stu-id="5786f-174">From your docker-compose.yml or docker-compose.override.yml files, you can initialize those environment variables so that Docker will set them up as OS environment variables for you, as shown in the following docker-compose.override.yml file (the connection string and other lines wrap in this example, but it would not wrap in your own file).</span></span>

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    - ExternalCatalogBaseUrl=http://10.0.75.1:5101
    #- ExternalCatalogBaseUrl=http://dockerhoststaging.westus.cloudapp.azure.com:5101
  
  ports:
    - "5101:5101"
```

<span data-ttu-id="5786f-175">Die Docker-compose.yml-Dateien auf Projektmappenebene können nicht nur flexibler als Konfigurationsdateien auf das Projekt oder Microservice allerdings auch mehr Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="5786f-175">The docker-compose.yml files at the solution level are not only more flexible than configuration files at the project or microservice level, but also more secure.</span></span> <span data-ttu-id="5786f-176">Beachten Sie, dass die Docker-Images, die Sie pro Microservice build enthalten nicht die Docker-compose.yml Dateien, nur die Binärdateien und Konfigurationsdateien für jede Microservice, einschließlich der dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="5786f-176">Consider that the Docker images that you build per microservice do not contain the docker-compose.yml files, only binary files and configuration files for each microservice, including the Dockerfile.</span></span> <span data-ttu-id="5786f-177">Aber die Docker-compose.yml-Datei wird nicht zusammen mit der Anwendung bereitgestellt. Es wird nur zum Zeitpunkt der Bereitstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5786f-177">But the docker-compose.yml file is not deployed along with your application; it is used only at deployment time.</span></span> <span data-ttu-id="5786f-178">Daher ist die platzieren Umgebungswerte für Variablen in die Docker-compose.yml-Dateien (auch ohne das Verschlüsseln der Werte) eine höhere Sicherheit als überführen diese Werte in den normalen NET-Konfigurationsdateien, die mit Ihrem Code bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5786f-178">Therefore, placing environment variables values in those docker-compose.yml files (even without encrypting the values) is more secure than placing those values in regular .NET configuration files that are deployed with your code.</span></span>

<span data-ttu-id="5786f-179">Sie können schließlich den Wert aus dem Code abrufen, mithilfe der Konfiguration\["ConnectionString"\], wie in der ConfigureServices-Methode in einer früheren Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5786f-179">Finally, you can get that value from your code by using Configuration\["ConnectionString"\], as shown in the ConfigureServices method in an earlier code example.</span></span>

<span data-ttu-id="5786f-180">Allerdings kann für produktionsumgebungen zu Explorer zusätzliche Methoden zum Speichern von geheimen Schlüsseln wie die Verbindungszeichenfolgen sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="5786f-180">However, for production environments, you might want to explorer additional ways on how to store secrets like the connection strings.</span></span> <span data-ttu-id="5786f-181">In der Regel, die verwaltet werden durch die ausgewählte Orchestrator, wie Sie tun können [Docker Containerhostclustern geheime Schlüssel Management](https://docs.docker.com/engine/swarm/secrets/).</span><span class="sxs-lookup"><span data-stu-id="5786f-181">Usually that will be managed by your chosen orchestrator, like you can do with [Docker Swarm secrets management](https://docs.docker.com/engine/swarm/secrets/).</span></span>

### <a name="implementing-versioning-in-aspnet-web-apis"></a><span data-ttu-id="5786f-182">Implementieren von versionsverwaltung in ASP.NET Web-APIs</span><span class="sxs-lookup"><span data-stu-id="5786f-182">Implementing versioning in ASP.NET Web APIs</span></span>

<span data-ttu-id="5786f-183">Wie die geschäftsanforderungen ändern, neue Sammlungen von Ressourcen hinzugefügt werden, ändert sich möglicherweise die Beziehungen zwischen Ressourcen und die Struktur der Daten in Ressourcen möglicherweise geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5786f-183">As business requirements change, new collections of resources may be added, the relationships between resources might change, and the structure of the data in resources might be amended.</span></span> <span data-ttu-id="5786f-184">Aktualisieren einer Web-API, um neue Anforderungen zu verarbeiten ist ein relativ einfacher Vorgang jedoch berücksichtigen Sie die Auswirkungen, die solche Änderungen auf Clientanwendungen, die Nutzung der Web-API haben.</span><span class="sxs-lookup"><span data-stu-id="5786f-184">Updating a Web API to handle new requirements is a relatively straightforward process, but you must consider the effects that such changes will have on client applications consuming the Web API.</span></span> <span data-ttu-id="5786f-185">Obwohl der Entwickler entwerfen und implementieren eine Web-API die vollständige Kontrolle über diese API hat, hat der Entwickler nicht das gleiche Maß an Kontrolle über Clientanwendungen, die vom Drittanbieter Organisationen Remote erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5786f-185">Although the developer designing and implementing a Web API has full control over that API, the developer does not have the same degree of control over client applications that might be built by third party organizations operating remotely.</span></span>

<span data-ttu-id="5786f-186">Versionsverwaltung ermöglicht eine Web-API, um anzugeben, die Funktionen und Ressourcen, die sie verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="5786f-186">Versioning enables a Web API to indicate the features and resources that it exposes.</span></span> <span data-ttu-id="5786f-187">Eine Clientanwendung kann Anforderungen an eine bestimmte Version einer Funktion oder die Ressource dann senden.</span><span class="sxs-lookup"><span data-stu-id="5786f-187">A client application can then submit requests to a specific version of a feature or resource.</span></span> <span data-ttu-id="5786f-188">Es gibt verschiedene Methoden zum Implementieren einer versionsverwaltung:</span><span class="sxs-lookup"><span data-stu-id="5786f-188">There are several approaches to implement versioning:</span></span>

-   <span data-ttu-id="5786f-189">URI-versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5786f-189">URI versioning</span></span>

-   <span data-ttu-id="5786f-190">Abfrage Zeichenfolge versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5786f-190">Query string versioning</span></span>

-   <span data-ttu-id="5786f-191">Header-versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5786f-191">Header versioning</span></span>

<span data-ttu-id="5786f-192">Abfragezeichenfolge und URI Versioning sind die am einfachsten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="5786f-192">Query string and URI versioning are the simplest to implement.</span></span> <span data-ttu-id="5786f-193">Header-versionsverwaltung ist ein guter Ansatz.</span><span class="sxs-lookup"><span data-stu-id="5786f-193">Header versioning is a good approach.</span></span> <span data-ttu-id="5786f-194">Allerdings Header versionsverwaltung nicht als explizite und einfach wie das URI-versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="5786f-194">However, header versioning not as explicit and straightforward as URI versioning.</span></span> <span data-ttu-id="5786f-195">Da URL versionsverwaltung die einfachste und explizitesten ist, verwendet die beispielanwendung eShopOnContainers URI Versioning.</span><span class="sxs-lookup"><span data-stu-id="5786f-195">Because URL versioning is the simplest and most explicit, the eShopOnContainers sample application uses URI versioning.</span></span>

<span data-ttu-id="5786f-196">Mit URI-versionsverwaltung verwendet werden, wie in der beispielanwendung eShopOnContainers bei jedem Ändern der Web-API oder das Schema von Ressourcen ändern, fügen Sie eine Versionsnummer an den URI für jede Ressource hinzu.</span><span class="sxs-lookup"><span data-stu-id="5786f-196">With URI versioning, as in the eShopOnContainers sample application, each time you modify the Web API or change the schema of resources, you add a version number to the URI for each resource.</span></span> <span data-ttu-id="5786f-197">Vorhandene URIs sollte weiterhin funktionieren wie zuvor, Zurückgeben von Ressourcen, die entsprechen dem Schema die angeforderte Version entspricht.</span><span class="sxs-lookup"><span data-stu-id="5786f-197">Existing URIs should continue to operate as before, returning resources that conform to the schema that matches the requested version.</span></span>

<span data-ttu-id="5786f-198">Wie im folgenden Codebeispiel wird gezeigt, kann die Version mit der Route-Attribut in der Web-API, wodurch die Version in den URI explizit festgelegt werden (in diesem Fall v1).</span><span class="sxs-lookup"><span data-stu-id="5786f-198">As shown in the following code example, the version can be set by using the Route attribute in the Web API, which makes the version explicit in the URI (v1 in this case).</span></span>

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

<span data-ttu-id="5786f-199">Dieser Mechanismus für die Versionskontrolle ist einfach und richtet sich nach dem Server die Anforderung an den entsprechenden Endpunkt weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="5786f-199">This versioning mechanism is simple and depends on the server routing the request to the appropriate endpoint.</span></span> <span data-ttu-id="5786f-200">Allerdings für eine komplexere versionsverwaltung und die beste Methode, wenn Sie REST verwenden, verwenden Sie Hypermedia und implementieren [HATEOAS (Hypertext als Modul Anwendungsstatus)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span><span class="sxs-lookup"><span data-stu-id="5786f-200">However, for a more sophisticated versioning and the best method when using REST, you should use hypermedia and implement [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#using-the-hateoas-approach-to-enable-navigation-to-related-resources).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5786f-201">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5786f-201">Additional resources</span></span>

-   <span data-ttu-id="5786f-202">**Scott Hanselman. ASP.NET Core RESTful-Web-API-versionsverwaltung lassen sich einfach**
    [*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span><span class="sxs-lookup"><span data-stu-id="5786f-202">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
[*http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx*](http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx)</span></span>

-   <span data-ttu-id="5786f-203">**Eine RESTful-Web-API-versionsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="5786f-203">**Versioning a RESTful web API**</span></span>

    [<span data-ttu-id="5786f-204">*https://docs.Microsoft.com/Azure/Architecture/Best-Practices/API-Design#Versioning-a-RESTful-Web-API*</span><span class="sxs-lookup"><span data-stu-id="5786f-204">*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   <span data-ttu-id="5786f-205">**Roy Fielding. Versionsverwaltung, Hypermedia und REST**
    [*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span><span class="sxs-lookup"><span data-stu-id="5786f-205">**Roy Fielding. Versioning, Hypermedia, and REST**
[*https://www.infoq.com/articles/roy-fielding-on-versioning*](https://www.infoq.com/articles/roy-fielding-on-versioning)</span></span>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a><span data-ttu-id="5786f-206">Generieren von Swagger-Metadaten mit Beschreibung von Ihrer Web-API von ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5786f-206">Generating Swagger description metadata from your ASP.NET Core Web API</span></span> 

<span data-ttu-id="5786f-207">[Swagger](http://swagger.io/) ist eine häufig verwendete open Source-Framework durch eine große Ökosystem von Tools, mit dem Sie gesichert, Entwurf, Build, Dokument und Ihre Rest-APIs nutzen.</span><span class="sxs-lookup"><span data-stu-id="5786f-207">[Swagger](http://swagger.io/) is a commonly used open source framework backed by a large ecosystem of tools that helps you design, build, document, and consume your RESTful APIs.</span></span> <span data-ttu-id="5786f-208">Der Standard für die APIs Beschreibung Metadaten-Domäne wird zunehmend.</span><span class="sxs-lookup"><span data-stu-id="5786f-208">It is becoming the standard for the APIs description metadata domain.</span></span> <span data-ttu-id="5786f-209">Sie sollten Beschreibung Swagger-Metadaten mit einem beliebigen Microservice, datengesteuerte Microservices oder erweiterte Domain driven Microservices (wie im folgenden Abschnitt erläutert) einschließen.</span><span class="sxs-lookup"><span data-stu-id="5786f-209">You should include Swagger description metadata with any kind of microservice, either data-driven microservices or more advanced domain-driven microservices (as explained in following section).</span></span>

<span data-ttu-id="5786f-210">Das Herzstück des Swagger ist der Swagger-Spezifikation, die API-Beschreibungsmetadaten in JSON oder YAML-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="5786f-210">The heart of Swagger is the Swagger specification, which is API description metadata in a JSON or YAML file.</span></span> <span data-ttu-id="5786f-211">Die Spezifikation erstellt die RESTful-Vertrag für Ihre API, über alle Ressourcen und Vorgänge sowohl einem von Menschen und machine readable Format für einfache Entwicklungs-, Discovery und Integration.</span><span class="sxs-lookup"><span data-stu-id="5786f-211">The specification creates the RESTful contract for your API, detailing all its resources and operations in both a human- and machine-readable format for easy development, discovery, and integration.</span></span>

<span data-ttu-id="5786f-212">Die Spezifikation bildet die Grundlage für die OpenAPI Spezifikation (bei-Zugriff) und entwickelt wird, in eine offene, transparent und gemeinschaftliche Community zu standardisieren, die RESTful-Schnittstellen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5786f-212">The specification is the basis of the OpenAPI Specification (OAS) and is developed in an open, transparent, and collaborative community to standardize the way RESTful interfaces are defined.</span></span>

<span data-ttu-id="5786f-213">Die Spezifikation definiert die Struktur für die wie ein Dienst ermittelt werden kann und wie seine Funktionen verstanden.</span><span class="sxs-lookup"><span data-stu-id="5786f-213">The specification defines the structure for how a service can be discovered and how its capabilities understood.</span></span> <span data-ttu-id="5786f-214">Weitere Informationen einschließlich einer Web-Editor und Beispiele der Swagger-Spezifikationen von Unternehmen wie sich von Spotify, Uber, Flaute und Microsoft, finden Sie unter der Swagger-Website (<http://swagger.io>).</span><span class="sxs-lookup"><span data-stu-id="5786f-214">For more information, including a web editor and examples of Swagger specifications from companies like Spotify, Uber, Slack, and Microsoft, see the Swagger site (<http://swagger.io>).</span></span>

### <a name="why-use-swagger"></a><span data-ttu-id="5786f-215">Gründe für die Verwendung von Swagger</span><span class="sxs-lookup"><span data-stu-id="5786f-215">Why use Swagger?</span></span>

<span data-ttu-id="5786f-216">Gründe zum Generieren von Swagger-Metadaten für Ihre-APIs sind die folgenden.</span><span class="sxs-lookup"><span data-stu-id="5786f-216">The main reasons to generate Swagger metadata for your APIs are the following.</span></span>

<span data-ttu-id="5786f-217">**Möglichkeit für andere Produkte zu konsumieren und zu integrieren Sie Ihre APIs**.</span><span class="sxs-lookup"><span data-stu-id="5786f-217">**Ability for other products to automatically consume and integrate your APIs**.</span></span> <span data-ttu-id="5786f-218">Dutzende von Produkten und [professionellen Tools](http://swagger.io/commercial-tools/) und viele [Bibliotheken und Frameworks](http://swagger.io/open-source-integrations/) Swagger zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5786f-218">Dozens of products and [commercial tools](http://swagger.io/commercial-tools/) and many [libraries and frameworks](http://swagger.io/open-source-integrations/) support Swagger.</span></span> <span data-ttu-id="5786f-219">Microsoft hat auf hoher Ebene Produkte und Tools, die automatisch Swagger-basierten APIs, wie z. B. die folgenden nutzen können:</span><span class="sxs-lookup"><span data-stu-id="5786f-219">Microsoft has high-level products and tools that can automatically consume Swagger-based APIs, such as the following:</span></span>

-   <span data-ttu-id="5786f-220">[AutoRest](https://github.com/Azure/AutoRest).</span><span class="sxs-lookup"><span data-stu-id="5786f-220">[AutoRest](https://github.com/Azure/AutoRest).</span></span> <span data-ttu-id="5786f-221">Sie können .NET-Clientklassen für den Aufruf von Swagger automatisch generieren.</span><span class="sxs-lookup"><span data-stu-id="5786f-221">You can automatically generate .NET client classes for calling Swagger.</span></span> <span data-ttu-id="5786f-222">Dies</span><span class="sxs-lookup"><span data-stu-id="5786f-222">This</span></span>

-   <span data-ttu-id="5786f-223">Tool kann von der CLI verwendet werden, und es Visual Studio auch für die einfache Verwendung über die GUI integriert.</span><span class="sxs-lookup"><span data-stu-id="5786f-223">tool can be used from the CLI and it also integrates with Visual Studio for easy use through the GUI.</span></span>

-   <span data-ttu-id="5786f-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="5786f-224">[Microsoft Flow](https://flow.microsoft.com/en-us/).</span></span> <span data-ttu-id="5786f-225">Sie können automatisch [verwenden und integrieren Sie Ihre API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) in einen allgemeinen Microsoft Flow-Workflow, ohne Programmierkenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5786f-225">You can automatically [use and integrate your API](https://flow.microsoft.com/en-us/blog/integrating-custom-api/) into a high-level Microsoft Flow workflow, with no programming skills required.</span></span>

-   <span data-ttu-id="5786f-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span><span class="sxs-lookup"><span data-stu-id="5786f-226">[Microsoft PowerApps](https://powerapps.microsoft.com/en-us/).</span></span> <span data-ttu-id="5786f-227">Können Sie automatisch Ihre API aus nutzen [PowerApps mobilapps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) mit erstellten [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), mit ohne Programmierkenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5786f-227">You can automatically consume your API from [PowerApps mobile apps](https://powerapps.microsoft.com/en-us/blog/register-and-use-custom-apis-in-powerapps/) built with [PowerApps Studio](https://powerapps.microsoft.com/en-us/guided-learning/learning-powerapps-parts/), with no programming skills required.</span></span>

-   <span data-ttu-id="5786f-228">[Azure App Service-Logik-Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span><span class="sxs-lookup"><span data-stu-id="5786f-228">[Azure App Service Logic Apps](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps).</span></span> <span data-ttu-id="5786f-229">Sie können automatisch [verwenden und Ihre API in eine Azure App Service-Logik-App integrieren](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), mit ohne Programmierkenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5786f-229">You can automatically [use and integrate your API into an Azure App Service Logic App](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api), with no programming skills required.</span></span>

<span data-ttu-id="5786f-230">**Möglichkeit zum automatischen Generieren von API-Dokumentation**.</span><span class="sxs-lookup"><span data-stu-id="5786f-230">**Ability to automatically generate API documentation**.</span></span> <span data-ttu-id="5786f-231">Bei der Erstellung von umfangreichen RESTful-APIs, z. B. komplexe Microservice basierende Anwendungen, müssen Sie viele Endpunkte mit anderen Datenmodellen verwendet werden, in der Anforderung und Antwort-Nutzlasten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5786f-231">When you create large-scale RESTful APIs, such as complex microservice-based applications, you need to handle many endpoints with different data models used in the request and response payloads.</span></span> <span data-ttu-id="5786f-232">Müssen die richtige Dokumentation und müssen einen Volltonfarbe API-Explorer aus, wie Sie mit Swagger, erhalten ist der Schlüssel für den Erfolg Ihrer API und die Annahme von Entwicklern.</span><span class="sxs-lookup"><span data-stu-id="5786f-232">Having proper documentation and having a solid API explorer, as you get with Swagger, is key for the success of your API and adoption by developers.</span></span>

<span data-ttu-id="5786f-233">Die Swagger-Metadaten ist, was Microsoft Flow-, PowerApps und Azure-Logik-Apps verwenden, um zu verstehen, wie Sie APIs verwenden und eine Verbindung mit ihnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="5786f-233">Swagger’s metadata is what Microsoft Flow, PowerApps, and Azure Logic Apps use to understand how to use APIs and connect to them.</span></span>

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a><span data-ttu-id="5786f-234">Gewusst wie: Automatisieren der Metadatengenerierung Swagger-API, mit dem Swashbuckle NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="5786f-234">How to automate API Swagger metadata generation with the Swashbuckle NuGet package</span></span>

<span data-ttu-id="5786f-235">Generieren von Swagger-Metadaten manuell (in JSON oder YAML-Datei) kann aufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="5786f-235">Generating Swagger metadata manually (in a JSON or YAML file) can be tedious work.</span></span> <span data-ttu-id="5786f-236">Allerdings können Sie API-Ermittlung von ASP.NET Web API-Dienste automatisieren, indem Sie mit der [Swashbuckle NuGet-Paket](http://aka.ms/swashbuckledotnetcore) Swagger-API-Metadaten dynamisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5786f-236">However, you can automate API discovery of ASP.NET Web API services by using the [Swashbuckle NuGet package](http://aka.ms/swashbuckledotnetcore) to dynamically generate Swagger API metadata.</span></span>

<span data-ttu-id="5786f-237">Swashbuckle generiert automatisch Swagger-Metadaten für ASP.NET Web API-Projekte.</span><span class="sxs-lookup"><span data-stu-id="5786f-237">Swashbuckle automatically generates Swagger metadata for your ASP.NET Web API projects.</span></span> <span data-ttu-id="5786f-238">ASP.NET Core Web-API-Projekte und der herkömmlichen ASP.NET Web-API und weitere Flavor, z. B. Azure-API-App, Azure-Mobile-App, Azure Service Fabric-Microservices basierend auf ASP.NET unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5786f-238">It supports ASP.NET Core Web API projects and the traditional ASP.NET Web API and any other flavor, such as Azure API App, Azure Mobile App, Azure Service Fabric microservices based on ASP.NET.</span></span> <span data-ttu-id="5786f-239">Sie unterstützt auch einfache Web-API für Container, wie in der Referenz-Anwendung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5786f-239">It also supports plain Web API deployed on containers, as in for the reference application.</span></span>

<span data-ttu-id="5786f-240">Swashbuckle kombiniert API Explorer und Swagger oder [Swagger-Ui](https://github.com/swagger-api/swagger-ui) bereitstellen, eine umfassende Ermittlung und die Dokumentation für Ihre API-Consumern auftreten.</span><span class="sxs-lookup"><span data-stu-id="5786f-240">Swashbuckle combines API Explorer and Swagger or [swagger-ui](https://github.com/swagger-api/swagger-ui) to provide a rich discovery and documentation experience for your API consumers.</span></span> <span data-ttu-id="5786f-241">Zusätzlich zu seiner generatormodul der Swagger-Metadaten enthält Swashbuckle auch eine eingebettete Version von Swagger-Ui, das sie automatisch dient Sie nach der Installation von Swashbuckle.</span><span class="sxs-lookup"><span data-stu-id="5786f-241">In addition to its Swagger metadata generator engine, Swashbuckle also contains an embedded version of swagger-ui, which it will automatically serve up once Swashbuckle is installed.</span></span>

<span data-ttu-id="5786f-242">Dies bedeutet, dass Sie Ihre API mit einer nice Ermittlung UI können Entwickler Ihre API verwenden ergänzen können.</span><span class="sxs-lookup"><span data-stu-id="5786f-242">This means you can complement your API with a nice discovery UI to help developers to use your API.</span></span> <span data-ttu-id="5786f-243">Da es sich automatisch generiert werden, können Sie den Schwerpunkt auf Ihre API erstellen, muss eine sehr kleine Menge an Code und Wartung.</span><span class="sxs-lookup"><span data-stu-id="5786f-243">It requires a very small amount of code and maintenance because it is automatically generated, allowing you to focus on building your API.</span></span> <span data-ttu-id="5786f-244">Das Ergebnis für den API Explorer sieht aus wie in Abbildung 8 – 8.</span><span class="sxs-lookup"><span data-stu-id="5786f-244">The result for the API Explorer looks like Figure 8-8.</span></span>

![](./media/image9.png)

<span data-ttu-id="5786f-245">**Abbildung 8 – 8**.</span><span class="sxs-lookup"><span data-stu-id="5786f-245">**Figure 8-8**.</span></span> <span data-ttu-id="5786f-246">Swashbuckle-API-Explorer auf der Grundlage von Swagger-Metadaten – eShopOnContainers Katalog Microservice</span><span class="sxs-lookup"><span data-stu-id="5786f-246">Swashbuckle API Explorer based on Swagger metadata—eShopOnContainers catalog microservice</span></span>

<span data-ttu-id="5786f-247">Die API-Explorer ist nicht der wichtigste hier.</span><span class="sxs-lookup"><span data-stu-id="5786f-247">The API explorer is not the most important thing here.</span></span> <span data-ttu-id="5786f-248">Nachdem Sie eine Web-API, die sich in der Swagger-Metadaten beschreiben können haben, kann Ihre API nahtlos aus Swagger-basierte Tools, einschließlich Client-Proxyklasse Code-Generatoren, die auf einer Vielzahl von Plattformen abzielen, können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5786f-248">Once you have a Web API that can describe itself in Swagger metadata, your API can be used seamlessly from Swagger-based tools, including client proxy-class code generators that can target many platforms.</span></span> <span data-ttu-id="5786f-249">Wie erwähnt, z. B. [AutoRest](https://github.com/Azure/AutoRest) .NET-Clientklassen automatisch generiert.</span><span class="sxs-lookup"><span data-stu-id="5786f-249">For example, as mentioned, [AutoRest](https://github.com/Azure/AutoRest) automatically generates .NET client classes.</span></span> <span data-ttu-id="5786f-250">Jedoch zusätzliche Tools wie [Swagger-Codegen](https://github.com/swagger-api/swagger-codegen) stehen auch zur Verfügung, die Generierung von Client-API-Bibliotheken, Server-Stubs und Dokumentation automatisch zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5786f-250">But additional tools like [swagger-codegen](https://github.com/swagger-api/swagger-codegen) are also available, which allow code generation of API client libraries, server stubs, and documentation automatically.</span></span>

<span data-ttu-id="5786f-251">Derzeit Swashbuckle besteht aus zwei NuGet-Pakete: Swashbuckle.SwaggerGen und Swashbuckle.SwaggerUi.</span><span class="sxs-lookup"><span data-stu-id="5786f-251">Currently, Swashbuckle consists of two NuGet packages: Swashbuckle.SwaggerGen and Swashbuckle.SwaggerUi.</span></span> <span data-ttu-id="5786f-252">Die erste stellt Funktionen bereit, generieren eine oder mehrere Swagger-Dokumente direkt von der API-Implementierung, und richten sie als JSON-Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="5786f-252">The former provides functionality to generate one or more Swagger documents directly from your API implementation and expose them as JSON endpoints.</span></span> <span data-ttu-id="5786f-253">Letzteres stellt eine eingebettete Version von der Swagger-Ui-Tool, das von Ihrer Anwendung bedient werden kann und die von den generierten Swagger-Dokumenten zur Beschreibung Ihrer API ausgeschaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5786f-253">The latter provides an embedded version of the swagger-ui tool that can be served by your application and powered by the generated Swagger documents to describe your API.</span></span> <span data-ttu-id="5786f-254">Die neuesten Versionen der Swashbuckle werden jedoch diese durch die Swashbuckle.AspNetCore Metapackage umbrochen.</span><span class="sxs-lookup"><span data-stu-id="5786f-254">However, the latest versions of Swashbuckle wrap these with the Swashbuckle.AspNetCore metapackage.</span></span>

<span data-ttu-id="5786f-255">Beachten Sie, dass Sie .NET Core-Web-API-Projekte verwenden müssen [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) Version 1.0.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5786f-255">Note that for .NET Core Web API projects, you need to use [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore/1.0.0) version 1.0.0 or later.</span></span>

<span data-ttu-id="5786f-256">Nachdem Sie diese NuGet-Pakete im Projekt-Web-API installiert haben, müssen Sie Swagger in der Start-Klasse, wie im folgenden Code zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="5786f-256">After you have installed these NuGet packages in your Web API project, you need to configure Swagger in the Startup class, as in the following code:</span></span>

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...
        services.AddSwaggerGen();
        services.ConfigureSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SingleApiVersion(new Swashbuckle.Swagger.Model.Info()
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API",
                TermsOfService = "eShopOnContainers terms of service"
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
            .UseSwaggerUi();
    }
}
```

<span data-ttu-id="5786f-257">Sobald dies geschehen ist, können Sie die Anwendung starten und Durchsuchen die folgenden Swagger JSON und UI-Endpunkte, mit URLs wie diesen:</span><span class="sxs-lookup"><span data-stu-id="5786f-257">Once this is done, you can start your application and browse the following Swagger JSON and UI endpoints using URLs like these:</span></span>

```json
  http://<your-root-url>/swagger/v1/swagger.json
  
  http://<your-root-url>/swagger/ui
```

<span data-ttu-id="5786f-258">Sie zuvor gesehen haben, die generierte Benutzeroberfläche von Swashbuckle für eine URL wie http:// erstellt&lt;die Stamm-Url &gt; /Swagger/Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="5786f-258">You previously saw the generated UI created by Swashbuckle for a URL like http://&lt;your-root-url&gt;/swagger/ui.</span></span> <span data-ttu-id="5786f-259">In Abbildung 8 – 9 können Sie auch sehen wie Sie alle API-Methode testen können.</span><span class="sxs-lookup"><span data-stu-id="5786f-259">In Figure 8-9 you can also see how you can test any API method.</span></span>

![](./media/image10.png)

<span data-ttu-id="5786f-260">**Abbildung 8 – 9**.</span><span class="sxs-lookup"><span data-stu-id="5786f-260">**Figure 8-9**.</span></span> <span data-ttu-id="5786f-261">Swashbuckle UI testen die Katalogelemente/API-Methode</span><span class="sxs-lookup"><span data-stu-id="5786f-261">Swashbuckle UI testing the Catalog/Items API method</span></span>

<span data-ttu-id="5786f-262">Abbildung 8 bis 10 zeigt die JSON Swagger-Metadaten aus den eShopOnContainers Microservice generiert (Dies ist, was die Tools verwenden, darunter) Wenn Sie anfordern &lt;die Stamm-Url&gt;/swagger/v1/swagger.json mit [Postman](https://www.getpostman.com/).</span><span class="sxs-lookup"><span data-stu-id="5786f-262">Figure 8-10 shows the Swagger JSON metadata generated from the eShopOnContainers microservice (which is what the tools use underneath) when you request &lt;your-root-url&gt;/swagger/v1/swagger.json using [Postman](https://www.getpostman.com/).</span></span>

![](./media/image11.png)

<span data-ttu-id="5786f-263">**Abbildung 8 bis 10**.</span><span class="sxs-lookup"><span data-stu-id="5786f-263">**Figure 8-10**.</span></span> <span data-ttu-id="5786f-264">Swagger-JSON-Metadaten</span><span class="sxs-lookup"><span data-stu-id="5786f-264">Swagger JSON metadata</span></span>

<span data-ttu-id="5786f-265">Es ist einfach.</span><span class="sxs-lookup"><span data-stu-id="5786f-265">It is that simple.</span></span> <span data-ttu-id="5786f-266">Und da er automatisch generiert werden, wächst die Swagger-Metadaten wenn Sie Ihre API weitere Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5786f-266">And because it is automatically generated, the Swagger metadata will grow when you add more functionality to your API.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5786f-267">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5786f-267">Additional resources</span></span>

-   <span data-ttu-id="5786f-268">**API-Hilfe ASP.NET-Webseiten mit Swagger**
    [*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span><span class="sxs-lookup"><span data-stu-id="5786f-268">**ASP.NET Web API Help Pages using Swagger**
[*https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger*](https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5786f-269">[Vorherigen] (Microservice-Anwendung-design.md) [weiter] (multi-container-Anwendungen-Docker-compose.md)</span><span class="sxs-lookup"><span data-stu-id="5786f-269">[Previous] (microservice-application-design.md) [Next] (multi-container-applications-docker-compose.md)</span></span>
