---
title: Arbeiten Sie mit Daten in ASP.NET Core-Apps
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Arbeiten mit Daten in asp
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: bcb8f7bbfa83db9c86cd1278a89750b9f02061d9
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a><span data-ttu-id="85632-103">Arbeiten mit Daten in ASP.NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="85632-103">Working with Data in ASP.NET Core Apps</span></span>

> <span data-ttu-id="85632-104">"Daten ist etwas wertvolle und dauert länger als die Systeme selbst".</span><span class="sxs-lookup"><span data-stu-id="85632-104">"Data is a precious thing and will last longer than the systems themselves."</span></span>

<span data-ttu-id="85632-105">Tim Berners-Lee</span><span class="sxs-lookup"><span data-stu-id="85632-105">Tim Berners-Lee</span></span>

## <a name="summary"></a><span data-ttu-id="85632-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="85632-106">Summary</span></span>

<span data-ttu-id="85632-107">Datenzugriff ist ein wichtiger Bestandteil nahezu jede softwareanwendung.</span><span class="sxs-lookup"><span data-stu-id="85632-107">Data access is an important part of almost any software application.</span></span> <span data-ttu-id="85632-108">ASP.NET Core unterstützt eine Vielzahl von Datenzugriffsoptionen, einschließlich Entity Framework Core (und Entity Framework 6 sowie) und können mit jeder beliebigen .NET Data Access-Framework arbeiten.</span><span class="sxs-lookup"><span data-stu-id="85632-108">ASP.NET Core supports a variety of data access options, including Entity Framework Core (and Entity Framework 6 as well), and can work with any .NET data access framework.</span></span> <span data-ttu-id="85632-109">Die Auswahl, von der Framework mit Datenzugriff, hängt von den Anforderungen der Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="85632-109">The choice of which data access framework to use depends on the application's needs.</span></span> <span data-ttu-id="85632-110">Diese Auswahl aus den ApplicationCore und UI-Projekten werden so abstrahiert und das Kapseln von Implementierungsdetails in Infrastruktur, erleichtert um lose, testfähig Software zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="85632-110">Abstracting these choices from the ApplicationCore and UI projects, and encapsulating implementation details in Infrastructure, helps to produce loosely coupled, testable software.</span></span>

## <a name="entity-framework-core-for-relational-databases"></a><span data-ttu-id="85632-111">Entity Framework Core (für relationale Datenbanken)</span><span class="sxs-lookup"><span data-stu-id="85632-111">Entity Framework Core (for relational databases)</span></span>

<span data-ttu-id="85632-112">Wenn Sie eine neue ASP.NET Core-Anwendung, die zum Arbeiten mit relationalen Daten benötigt schreiben, wird Entity Framework Core (EF Core) die empfohlene Vorgehensweise für Ihre Anwendung auf ihre Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="85632-112">If you're writing a new ASP.NET Core application that needs to work with relational data, then Entity Framework Core (EF Core) is the recommended way for your application to access its data.</span></span> <span data-ttu-id="85632-113">EF Core handelt es sich um eine objektrelationale Mapper (O/RM), die .NET Entwicklern Objekte in und aus einer Datenquelle beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="85632-113">EF Core is an object-relational mapper (O/RM) that enables .NET developers to persist objects to and from a data source.</span></span> <span data-ttu-id="85632-114">Er wird für die meisten der Datenzugriffscode, die Entwicklern in der Regel würden schreiben überflüssig.</span><span class="sxs-lookup"><span data-stu-id="85632-114">It eliminates the need for most of the data access code developers would typically need to write.</span></span> <span data-ttu-id="85632-115">Wie ASP.NET Core wurde von Grund auf neu bis hin zu Support modulare plattformübergreifende Anwendungen EF Core umgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="85632-115">Like ASP.NET Core, EF Core has been rewritten from the ground up to support modular cross-platform applications.</span></span> <span data-ttu-id="85632-116">Fügen Sie es als ein NuGet-Paket an die Anwendung, in den Starttasks zu konfigurieren, und über Abhängigkeitsinjektion anfordern, wo Sie ihn benötigen.</span><span class="sxs-lookup"><span data-stu-id="85632-116">You add it to your application as a NuGet package, configure it in Startup, and request it through dependency injection wherever you need it.</span></span>

<span data-ttu-id="85632-117">Um EF-Core mit einer SQL Server-Datenbank verwenden möchten, führen Sie den folgenden Dotnet-CLI-Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="85632-117">To use EF Core with a SQL Server database, run the following dotnet CLI command:</span></span>

<span data-ttu-id="85632-118">Dotnet Paket Microsoft.EntityFrameworkCore.SqlServer hinzufügen</span><span class="sxs-lookup"><span data-stu-id="85632-118">dotnet add package Microsoft.EntityFrameworkCore.SqlServer</span></span>

<span data-ttu-id="85632-119">So fügen Sie Unterstützung für eine Datenquelle InMemory für Testzwecke hinzu:</span><span class="sxs-lookup"><span data-stu-id="85632-119">To add support for an InMemory data source, for testing:</span></span>

<span data-ttu-id="85632-120">Dotnet Paket Microsoft.EntityFrameworkCore.InMemory hinzufügen</span><span class="sxs-lookup"><span data-stu-id="85632-120">dotnet add package Microsoft.EntityFrameworkCore.InMemory</span></span>

### <a name="the-dbcontext"></a><span data-ttu-id="85632-121">Die DbContext</span><span class="sxs-lookup"><span data-stu-id="85632-121">The DbContext</span></span>

<span data-ttu-id="85632-122">Um mit EF Core arbeiten, benötigen Sie eine Unterklasse von ' DbContext ' aus.</span><span class="sxs-lookup"><span data-stu-id="85632-122">To work with EF Core, you need a subclass of DbContext.</span></span> <span data-ttu-id="85632-123">Diese Klasse enthält Eigenschaften, die Auflistungen von Entitäten, denen mit Ihrer Anwendung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="85632-123">This class holds properties representing collections of the entities your application will work with.</span></span> <span data-ttu-id="85632-124">Das eShopOnWeb-Beispiel enthält eine CatalogContext mit Sammlungen für Elemente, Marken und -Typen:</span><span class="sxs-lookup"><span data-stu-id="85632-124">The eShopOnWeb sample includes a CatalogContext with collections for items, brands, and types:</span></span>

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

<span data-ttu-id="85632-125">Die DbContext muss einen Konstruktor, der DbContextOptions akzeptiert haben und dieses Argument auf der Basis DbContext-Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="85632-125">Your DbContext must have a constructor that accepts DbContextOptions and pass this argument to the base DbContext constructor.</span></span> <span data-ttu-id="85632-126">Beachten Sie, dass, wenn Sie nur ein ' DbContext ' in der Anwendung haben, können Sie eine Instanz von DbContextOptions übergeben, aber haben müssen Sie mehrere generische DbContextOptions verwenden<T> Typ, in der DbContext-Typ als generische Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="85632-126">Note that if you have only one DbContext in your application, you can pass an instance of DbContextOptions, but if you have more than one you must use the generic DbContextOptions<T> type, passing in your DbContext type as the generic parameter.</span></span>

### <a name="configuring-ef-core"></a><span data-ttu-id="85632-127">Konfigurieren von EF Core</span><span class="sxs-lookup"><span data-stu-id="85632-127">Configuring EF Core</span></span>

<span data-ttu-id="85632-128">In der Anwendung ASP.NET Core konfigurieren Sie in der Regel EF Core in der ConfigureServices-Methode.</span><span class="sxs-lookup"><span data-stu-id="85632-128">In your ASP.NET Core application, you'll typically configure EF Core in your ConfigureServices method.</span></span> <span data-ttu-id="85632-129">EF-Kern verwendet eine DbContextOptionsBuilder, die mehrere nützliche Erweiterungsmethoden zum Optimieren der Konfigurations unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85632-129">EF Core uses a DbContextOptionsBuilder, which supports several helpful extension methods to streamline its configuration.</span></span> <span data-ttu-id="85632-130">Um CatalogContext Verwendung eine SQL Server-Datenbank mit einer Verbindungszeichenfolge, die in der Konfiguration definierte zu konfigurieren, würden Sie ConfigureServices den folgenden Code hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="85632-130">To configure CatalogContext to use a SQL Server database with a connection string defined in Configuration, you would add the following code to ConfigureServices:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

<span data-ttu-id="85632-131">So verwenden Sie die Datenbank im Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="85632-131">To use the in-memory database:</span></span>

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

<span data-ttu-id="85632-132">Sobald Sie EF Core, erstellt einen ' DbContext ' untergeordneter Typ installiert und konfiguriert ihn im ConfigureServices, können Sie mithilfe von EF Core.</span><span class="sxs-lookup"><span data-stu-id="85632-132">Once you have installed EF Core, created a DbContext child type, and configured it in ConfigureServices, you are ready to use EF Core.</span></span> <span data-ttu-id="85632-133">Sie können anfordern eine Instanz von der DbContext-Typ in einem Dienst, der benötigt, und Arbeiten mit Ihrem persistenten Entitäten, die mithilfe von LINQ, als wären sie einfach in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="85632-133">You can request an instance of your DbContext type in any service that needs it, and start working with your persisted entities using LINQ as if they were simply in a collection.</span></span> <span data-ttu-id="85632-134">EF Core funktioniert die Übersetzung der LINQ-Ausdrücke in SQL-Abfragen zum Speichern und Abrufen Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="85632-134">EF Core does the work of translating your LINQ expressions into SQL queries to store and retrieve your data.</span></span>

<span data-ttu-id="85632-135">Sie können die EF Core ausgeführt wird, indem Sie eine Protokollierung konfigurieren und sicherstellen, die standardvertrauensebene ist mindestens Abfragen finden Sie unter Informationen, wie in Abbildung 8 – 1 gezeigt.</span><span class="sxs-lookup"><span data-stu-id="85632-135">You can see the queries EF Core is executing by configuring a logger and ensuring its level is set to at least Information, as shown in Figure 8-1.</span></span>

![](./media/image8-1.png)

<span data-ttu-id="85632-136">Abbildung 8: 1-Protokollierung EF Core Abfragen an die Konsole</span><span class="sxs-lookup"><span data-stu-id="85632-136">Figure 8-1 Logging EF Core queries to the console</span></span>

### <a name="fetching-and-storing-data"></a><span data-ttu-id="85632-137">Das Abrufen und Speichern von Daten</span><span class="sxs-lookup"><span data-stu-id="85632-137">Fetching and Storing Data</span></span>

<span data-ttu-id="85632-138">Abrufen von Daten aus EF Core Zugriff auf die entsprechende Eigenschaft und Verwenden von LINQ zum Filtern des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="85632-138">To retrieve data from EF Core, you access the appropriate property and use LINQ to filter the result.</span></span> <span data-ttu-id="85632-139">LINQ können auch die Projektion, führen Sie das Ergebnis von einem Typ in eine andere transformieren.</span><span class="sxs-lookup"><span data-stu-id="85632-139">You can also use LINQ to perform projection, transforming the result from one type to another.</span></span> <span data-ttu-id="85632-140">Im folgende Beispiel würde CatalogBrands, nach Namen sortiert, gefiltert nach deren Enabled-Eigenschaft und auf einen SelectListItem-Typ projiziert abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="85632-140">The following example would retrieve CatalogBrands, ordered by name, filtered by their Enabled property, and projected onto a SelectListItem type:</span></span>

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

<span data-ttu-id="85632-141">Es ist wichtig, im obigen Beispiel den Aufruf von ToListAsync, damit er sofort ausführen die Abfrage hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="85632-141">It's important in the above example to add the call to ToListAsync in order to execute the query immediately.</span></span> <span data-ttu-id="85632-142">Ordnen Sie andernfalls die Anweisung wird eine IQueryable<SelectListItem> zu BrandItems, die nicht ausgeführt werden, bis diese aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="85632-142">Otherwise, the statement will assign an IQueryable<SelectListItem> to brandItems, which will not be executed until it is enumerated.</span></span> <span data-ttu-id="85632-143">Es gibt vor- und Nachteile, IQueryable-Ergebnisse aus Methoden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="85632-143">There are pros and cons to returning IQueryable results from methods.</span></span> <span data-ttu-id="85632-144">Sie können die Abfrage, die EF Core erstellt wird, um weitere geändert werden, jedoch können auch nur während der Laufzeit auftretende Fehler führen, wenn Vorgänge zur Abfrage hinzugefügt werden, die EF Core übersetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="85632-144">It allows the query EF Core will construct to be further modified, but can also result in errors that only occur at runtime, if operations are added to the query that EF Core cannot translate.</span></span> <span data-ttu-id="85632-145">Es ist im Allgemeinen sicherer zur Übergabe von alle Filter in der Methode, die den Datenzugriff ausführen und Rückgabe Sichern einer Auflistung im Arbeitsspeicher (z. B. Liste<T>) als Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="85632-145">It's generally safer to pass any filters into the method performing the data access, and return back an in-memory collection (for example, List<T>) as the result.</span></span>

<span data-ttu-id="85632-146">EF Core verfolgt Änderungen auf Entitäten, die aus der Persistenz abgerufen.</span><span class="sxs-lookup"><span data-stu-id="85632-146">EF Core tracks changes on entities it fetches from persistence.</span></span> <span data-ttu-id="85632-147">Zum Speichern von Änderungen auf eine nachverfolgte Entität, rufen Sie einfach die SaveChanges-Methode für DbContext, stellen Sie sicher, dass er der gleichen DbContext-Instanz ist, die verwendet wurde, um die Entität abzurufen.</span><span class="sxs-lookup"><span data-stu-id="85632-147">To save changes to a tracked entity, you just call the SaveChanges method on the DbContext, making sure it's the same DbContext instance that was used to fetch the entity.</span></span> <span data-ttu-id="85632-148">Hinzufügen und Entfernen von Entitäten befindet sich direkt auf die entsprechende DbSet-Eigenschaft erneut mit einem Aufruf von SaveChanges zur Ausführung der Datenbankbefehle.</span><span class="sxs-lookup"><span data-stu-id="85632-148">Adding and removing entities is directly on the appropriate DbSet property, again with a call to SaveChanges to execute the database commands.</span></span> <span data-ttu-id="85632-149">Das folgende Beispiel veranschaulicht das Hinzufügen, aktualisieren und Löschen von Entitäten aus der Persistenz.</span><span class="sxs-lookup"><span data-stu-id="85632-149">The following example demonstrates adding, updating, and removing entities from persistence.</span></span>

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

<span data-ttu-id="85632-150">EF Core unterstützt beide synchrone und asynchrone Methoden zum Abrufen und speichern.</span><span class="sxs-lookup"><span data-stu-id="85632-150">EF Core supports both synchronous and async methods for fetching and saving.</span></span> <span data-ttu-id="85632-151">In Webanwendungen wurde empfohlen, das Async/await-Muster mit dem Async-Methoden verwenden, damit Threads für Web-Server beim Warten auf den auf den Abschluss Zugriffsvorgänge für Daten nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-151">In web applications, it's recommended to use the async/await pattern with the async methods, so that web server threads are not blocked while waiting for data access operations to complete.</span></span>

### <a name="fetching-related-data"></a><span data-ttu-id="85632-152">Abrufen von verknüpften Daten</span><span class="sxs-lookup"><span data-stu-id="85632-152">Fetching Related Data</span></span>

<span data-ttu-id="85632-153">Wenn EF Core Entitäten abgerufen werden, füllt es alle Eigenschaften, die direkt mit dieser Entität in der Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="85632-153">When EF Core retrieves entities, it populates all of the properties that are stored directly with that entity in the database.</span></span> <span data-ttu-id="85632-154">Navigationseigenschaften, z. B. Listen von verknüpften Entitäten werden nicht aufgefüllt und möglicherweise ihren Wert auf null.</span><span class="sxs-lookup"><span data-stu-id="85632-154">Navigation properties, such as lists of related entities, are not populated and may have their value set to null.</span></span> <span data-ttu-id="85632-155">Dadurch wird sichergestellt, dass EF Core nicht mehr Daten als erforderlich ist, Abrufen von ist dies besonders wichtig für Webanwendungen, die schnell verarbeiten von Anforderungen und Antworten auf effiziente Weise zurückgeben muss.</span><span class="sxs-lookup"><span data-stu-id="85632-155">This ensures EF Core is not fetching more data than is needed, which is especially important for web applications, which must quickly process requests and return responses in an efficient manner.</span></span> <span data-ttu-id="85632-156">Um Beziehungen mit einer Entität enthalten *unverzüglichem Laden*, wie dargestellt, geben Sie die Eigenschaft, die mithilfe der Include-Erweiterungsmethode für die Abfrage:</span><span class="sxs-lookup"><span data-stu-id="85632-156">To include relationships with an entity using *eager loading*, you specify the property using the Include extension method on the query, as shown:</span></span>

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

<span data-ttu-id="85632-157">Sie können mehrere Beziehungen einschließen, und Sie können auch untergeordnete Beziehungen einschließen ThenInclude verwenden.</span><span class="sxs-lookup"><span data-stu-id="85632-157">You can include multiple relationships, and you can also include sub-relationships using ThenInclude.</span></span> <span data-ttu-id="85632-158">EF Core führt eine einzelne Abfrage, um die resultierende Menge der Entitäten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="85632-158">EF Core will execute a single query to retrieve the resulting set of entities.</span></span>

<span data-ttu-id="85632-159">Eine weitere Option zum Laden von verknüpften Daten ist die Verwendung *explizites Laden*.</span><span class="sxs-lookup"><span data-stu-id="85632-159">Another option for loading related data is to use *explicit loading*.</span></span> <span data-ttu-id="85632-160">Explizites Laden können Sie zusätzliche Daten in einer Entität zu laden, die bereits abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="85632-160">Explicit loading allows you to load additional data into an entity that has already been retrieved.</span></span> <span data-ttu-id="85632-161">Da dies eine separate Anforderung an die Datenbank umfasst, wird nicht empfohlen, Webanwendungen, die die Anzahl der Datenbank zu minimieren, sollten Roundtrips pro Anforderung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="85632-161">Since this involves a separate request to the database, it's not recommended for web applications, which should minimize the number of database round trips made per request.</span></span>

<span data-ttu-id="85632-162">*Verzögertes Laden* ist ein Feature, das automatisch verknüpfte Daten lädt, wie er von der Anwendung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="85632-162">*Lazy loading* is a feature that automatically loads related data as it is referenced by the application.</span></span> <span data-ttu-id="85632-163">Es ist von EF Core derzeit nicht unterstützt, als mit expliziten Laden er jedoch sollte in der Regel deaktiviert werden für Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="85632-163">It's not currently supported by EF Core, but as with explicit loading it should typically be disabled for web applications.</span></span>

### <a name="resilient-connections"></a><span data-ttu-id="85632-164">Robuste Verbindungen</span><span class="sxs-lookup"><span data-stu-id="85632-164">Resilient Connections</span></span>

<span data-ttu-id="85632-165">Externe Ressourcen wie SQL-Datenbanken möglicherweise gelegentlich nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="85632-165">External resources like SQL databases may occasionally be unavailable.</span></span> <span data-ttu-id="85632-166">Anwendungen können in Fällen von vorübergehenden Ausfall Wiederholungslogik verwenden, um zu vermeiden, durch das Auslösen einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="85632-166">In cases of temporary unavailability, applications can use retry logic to avoid raising an exception.</span></span> <span data-ttu-id="85632-167">Diese Technik wird häufig als bezeichnet *verbindungsstabilität*.</span><span class="sxs-lookup"><span data-stu-id="85632-167">This technique is commonly referred to as *connection resiliency*.</span></span> <span data-ttu-id="85632-168">Sie implementieren können Ihre [eigenen-Wiederholung wird mit exponenzieller](https://docs.microsoft.com/azure/architecture/patterns/retry) Technik, indem er versucht, folgt mit einer exponentiell zunehmenden Wartezeit, bis eine maximale Anzahl von Wiederholungsversuchen überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="85632-168">You can implement your [own retry with exponential backoff](https://docs.microsoft.com/azure/architecture/patterns/retry) technique by attempting to rety with an exponentially increasing wait time, until a maximum retry count has been reached.</span></span> <span data-ttu-id="85632-169">Diese Technik Verwaltungsteam die Tatsache, dass Cloudressourcen zeitweise für kurze Zeit, was zu fehlschlagen einiger Anforderungen ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="85632-169">This technique embraces the fact that cloud resources might intermittently be unavailable for short periods of time, resulting in failure of some requests.</span></span>

<span data-ttu-id="85632-170">Für Azure SQL-Datenbank bietet Entity Framework Core bereits interne Datenbank Connection Resiliency und Wiederholungslogik.</span><span class="sxs-lookup"><span data-stu-id="85632-170">For Azure SQL DB, Entity Framework Core already provides internal database connection resiliency and retry logic.</span></span> <span data-ttu-id="85632-171">Jedoch müssen Sie die Entity Framework-Ausführungsstrategie für jede Verbindung DbContext aktivieren, wenn Sie robuste EF Core Verbindungen haben möchten.</span><span class="sxs-lookup"><span data-stu-id="85632-171">But you need to enable the Entity Framework execution strategy for each DbContext connection if you want to have resilient EF Core connections.</span></span>

<span data-ttu-id="85632-172">Der folgende Code auf der Verbindungsebene EF Core ermöglicht z. B. robuste SQL-Verbindungen, die wiederholt werden, wenn die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="85632-172">For instance, the following code at the EF Core connection level enables resilient SQL connections that are retried if the connection fails.</span></span>

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
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
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a><span data-ttu-id="85632-173">Ausführungsstrategien und explizite Transaktionen mit BeginTransaction und mehrere DbContexts</span><span class="sxs-lookup"><span data-stu-id="85632-173">Execution strategies and explicit transactions using BeginTransaction and multiple DbContexts</span></span> 
  
  <span data-ttu-id="85632-174">Wenn Wiederholungen in EF Core Verbindungen aktiviert sind, wird jeden Vorgang, die Sie mit EF Core ausführen eigener wiederholbar Vorgang.</span><span class="sxs-lookup"><span data-stu-id="85632-174">When retries are enabled in EF Core connections, each operation you perform using EF Core becomes its own retriable operation.</span></span> <span data-ttu-id="85632-175">Jede Abfrage und jeder Aufruf von SaveChanges werden als eine Einheit wiederholt, wenn ein vorübergehender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="85632-175">Each query and each call to SaveChanges will be retried as a unit if a transient failure occurs.</span></span>
  
  <span data-ttu-id="85632-176">Jedoch, wenn Ihr Code eine Transaktion mit BeginTransaction initiiert wird, definieren Sie eine eigene Gruppe von Vorgängen, die als Einheit behandelt werden müssen – alles innerhalb der Transaktion wurde ein Rollback ausgeführt zurück, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="85632-176">However, if your code initiates a transaction using BeginTransaction, you are defining your own group of operations that need to be treated as a unit—everything inside the transaction has be rolled back if a failure occurs.</span></span> <span data-ttu-id="85632-177">Eine Ausnahme wie im folgenden sehen, wenn Sie versuchen, diese Transaktion ausgeführt werden, wenn eine EF Ausführungsstrategie (wiederholungsrichtlinie) verwenden und Sie mehrere SaveChanges aus mehreren DbContexts darin enthalten.</span><span class="sxs-lookup"><span data-stu-id="85632-177">You will see an exception like the following if you attempt to execute that transaction when using an EF execution strategy (retry policy) and you include several SaveChanges from multiple DbContexts in it.</span></span>

<span data-ttu-id="85632-178">System.InvalidOperationException: Die konfigurierte Ausführungsstrategie 'SqlServerRetryingExecutionStrategy' unterstützt keine vom Benutzer initiierten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="85632-178">System.InvalidOperationException: The configured execution strategy 'SqlServerRetryingExecutionStrategy' does not support user initiated transactions.</span></span> <span data-ttu-id="85632-179">Verwenden Sie die Ausführungsstrategie "DbContext.Database.CreateExecutionStrategy()" zurückgegebene, um alle Vorgänge in der Transaktion als Einheit mit möglichem auszuführen.</span><span class="sxs-lookup"><span data-stu-id="85632-179">Use the execution strategy returned by 'DbContext.Database.CreateExecutionStrategy()' to execute all the operations in the transaction as a retriable unit.</span></span>

<span data-ttu-id="85632-180">Die Lösung besteht darin, manuell aufrufen Ausführungsstrategie EF mit einen Delegaten, die alle Elemente darstellt, die ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="85632-180">The solution is to manually invoke the EF execution strategy with a delegate representing everything that needs to be executed.</span></span> <span data-ttu-id="85632-181">Um ein vorübergehender Fehler auftritt, wird die Ausführungsstrategie den Delegaten erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="85632-181">If a transient failure occurs, the execution strategy will invoke the delegate again.</span></span> <span data-ttu-id="85632-182">Der folgende Code zeigt, wie Sie diesen Ansatz zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="85632-182">The following code shows how to implement this approach:</span></span>

```csharp
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
```

<span data-ttu-id="85632-183">Ist die erste DbContext der \_CatalogContext und das zweite ist ' DbContext ' innerhalb der \_IntegrationEventLogService-Objekt.</span><span class="sxs-lookup"><span data-stu-id="85632-183">The first DbContext is the \_catalogContext and the second DbContext is within the \_integrationEventLogService object.</span></span> <span data-ttu-id="85632-184">Schließlich ausgeführt die Commit-Aktion wäre mehrere DbContexts und eine Ausführungsstrategie EF verwenden.</span><span class="sxs-lookup"><span data-stu-id="85632-184">Finally, the Commit action would be performed multiple DbContexts and using an EF Execution Strategy.</span></span>

> ### <a name="references--entity-framework-core"></a><span data-ttu-id="85632-185">Verweise – Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="85632-185">References – Entity Framework Core</span></span>
> - <span data-ttu-id="85632-186">**EF zentrale Dokumente**</span><span class="sxs-lookup"><span data-stu-id="85632-186">**EF Core Docs**</span></span>  
> <span data-ttu-id="85632-187"><https://docs.Microsoft.com/EF/></span><span class="sxs-lookup"><span data-stu-id="85632-187"><https://docs.microsoft.com/ef/></span></span>
> - <span data-ttu-id="85632-188">**EF Core: Verwandte Daten**</span><span class="sxs-lookup"><span data-stu-id="85632-188">**EF Core: Related Data**</span></span>  
> <span data-ttu-id="85632-189"><https://docs.Microsoft.com/EF/Core/Querying/Related-Data></span><span class="sxs-lookup"><span data-stu-id="85632-189"><https://docs.microsoft.com/ef/core/querying/related-data></span></span>
> - <span data-ttu-id="85632-190">**Vermeiden Sie Lazy Loading Entitäten im ASPNET-Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="85632-190">**Avoid Lazy Loading Entities in ASPNET Applications**</span></span>  
> <span data-ttu-id="85632-191"><http://ardalis.com/AVOID-Lazy-Loading-Entities-in-ASP-NET-Applications></span><span class="sxs-lookup"><span data-stu-id="85632-191"><http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications></span></span>

## <a name="ef-core-or-micro-orm"></a><span data-ttu-id="85632-192">EF Core "oder" Micro-ORM, "?</span><span class="sxs-lookup"><span data-stu-id="85632-192">EF Core or micro-ORM?</span></span>

<span data-ttu-id="85632-193">Während EF Core eine gute Wahl ist für die Verwaltung von Persistenz und zum größten Teil vom Anwendungsentwickler Datenbankdetails kapselt, ist es nicht die einzige Auswahlmöglichkeit.</span><span class="sxs-lookup"><span data-stu-id="85632-193">While EF Core is a great choice for managing persistence, and for the most part encapsulates database details from application developers, it is not the only choice.</span></span> <span data-ttu-id="85632-194">Eine beliebte open Source-Alternative ist die [dapper, durch](https://github.com/StackExchange/Dapper), eine so genannte Micro-ORM.</span><span class="sxs-lookup"><span data-stu-id="85632-194">Another popular open source alternative is [Dapper](https://github.com/StackExchange/Dapper), a so-called micro-ORM.</span></span> <span data-ttu-id="85632-195">Ein Micro-ORM ist ein Lightweight-weniger mit umfassenden Tools für die Zuordnung von Objekten in Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="85632-195">A micro-ORM is a lightweight, less full-featured tool for mapping objects to data structures.</span></span> <span data-ttu-id="85632-196">Im Fall von dapper, durch verwendet seinen Entwurf auf die Leistung, Ziele konzentrieren, anstatt vollständig kapseln die zugrunde liegende Abfragen zum Abrufen und Aktualisieren von Daten.</span><span class="sxs-lookup"><span data-stu-id="85632-196">In the case of Dapper, its design goals focus on performance, rather than fully encapsulating the underlying queries it uses to retrieve and update data.</span></span> <span data-ttu-id="85632-197">Da es SQL seitens des Entwicklers abstrahieren nicht, dapper, durch "näher an die Metall" und können Entwickler die genaue schreiben Zugriffsvorgang für Abfragen, die sie für einen angegebenen Daten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="85632-197">Because it doesn't abstract SQL from the developer, Dapper is "closer to the metal" and lets developers write the exact queries they want to use for a given data access operation.</span></span>

<span data-ttu-id="85632-198">EF Core verfügt über zwei wichtige Features, die es bietet, die von dapper, durch trennen, aber auch der Verwaltungsaufwand hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="85632-198">EF Core has two significant features it provides which separate it from Dapper but also add to its performance overhead.</span></span> <span data-ttu-id="85632-199">Das erste ist die Übersetzung von LINQ-Ausdrücke in SQL.</span><span class="sxs-lookup"><span data-stu-id="85632-199">The first is translation from LINQ expressions into SQL.</span></span> <span data-ttu-id="85632-200">Diese Übersetzungen werden zwischengespeichert, aber auch also, dass sich Aufwand in die sie beim ersten ausführen.</span><span class="sxs-lookup"><span data-stu-id="85632-200">These translations are cached, but even so there is overhead in performing them the first time.</span></span> <span data-ttu-id="85632-201">Das zweite ist die änderungsnachverfolgung für Entitäten (sodass effiziente Update-Anweisungen generiert werden können).</span><span class="sxs-lookup"><span data-stu-id="85632-201">The second is change tracking on entities (so that efficient update statements can be generated).</span></span> <span data-ttu-id="85632-202">Dieses Verhalten kann für bestimmte Abfragen deaktiviert werden, mithilfe der AsNotTracking-Erweiterungs.</span><span class="sxs-lookup"><span data-stu-id="85632-202">This behavior can be turned off for specific queries by using the AsNotTracking extension.</span></span> <span data-ttu-id="85632-203">EF Core generiert auch SQL-Abfragen, die in der Regel sehr effizient und leistungsoptimierung in jedem Fall durchaus akzeptabel sind, aber wenn Sie, und Kontrolle über die genaue Abfrage Ordnung müssen ausgeführt werden, können Sie benutzerdefinierte SQL übergeben (oder Ausführen einer gespeicherten Prozedur) mithilfe von EF. Core, zu.</span><span class="sxs-lookup"><span data-stu-id="85632-203">EF Core also generates SQL queries that usually are very efficient and in any case perfectly acceptable from a performance standpoint, but if you need fine control over the precise query to be executed, you can pass in custom SQL (or execute a stored procedure) using EF Core, too.</span></span> <span data-ttu-id="85632-204">In diesem Fall übertrifft Dapper noch EF Kern ausgeführt, aber nur geringfügig.</span><span class="sxs-lookup"><span data-stu-id="85632-204">In this case, Dapper still outperforms EF Core, but only slightly.</span></span> <span data-ttu-id="85632-205">Julie Lerman zeigt einige Leistungsdaten in ihrem möglicherweise 2016 MSDN-Artikel [dapper, durch Entity Framework und Hybrid-Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span><span class="sxs-lookup"><span data-stu-id="85632-205">Julie Lerman presents some performance data in her May 2016 MSDN article [Dapper, Entity Framework, and Hybrid Apps](https://msdn.microsoft.com/magazine/mt703432.aspx).</span></span> <span data-ttu-id="85632-206">Zusätzliche Leistung Benchmark-Daten für eine Vielzahl von Methoden für den Datenzugriff finden Sie in der [Dapper Website](https://github.com/StackExchange/Dapper).</span><span class="sxs-lookup"><span data-stu-id="85632-206">Additional performance benchmark data for a variety of data access methods can be found on [the Dapper site](https://github.com/StackExchange/Dapper).</span></span>

<span data-ttu-id="85632-207">Um anzuzeigen, wie dapper, durch die Syntax von EF Kern variiert, betrachten Sie diese zwei Versionen der gleichen Methode zum Abrufen einer Liste von Elementen aus:</span><span class="sxs-lookup"><span data-stu-id="85632-207">To see how the syntax for Dapper varies from EF Core, consider these two versions of the same method for retrieving a list of items:</span></span>

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

<span data-ttu-id="85632-208">Wenn Sie komplexere Objektdiagramme mit dapper, durch erstellen möchten, müssen Sie die zugehörigen Abfragen, die selbst (im Gegensatz zu einer Include hinzufügen, wie in EF Core) schreiben.</span><span class="sxs-lookup"><span data-stu-id="85632-208">If you need to build more complex object graphs with Dapper, you need to write the associated queries yourself (as opposed to adding an Include as you would in EF Core).</span></span> <span data-ttu-id="85632-209">Dies wird unterstützt, über eine Reihe von Syntax, z. B. eine Funktion namens mehrfach zuordnen, in dem Sie einzelne Zeilen auf mehrere zugeordnete Objekte zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="85632-209">This is supported through a variety of syntaxes, including a feature called Multi Mapping that lets you map individual rows to multiple mapped objects.</span></span> <span data-ttu-id="85632-210">Z. B. zurück eine Klasse Post mit Owner-Eigenschaft des Typs Benutzer, die folgende SQL-Anweisung alle erforderlichen Daten:</span><span class="sxs-lookup"><span data-stu-id="85632-210">For example, given a class Post with a property Owner of type User, the following SQL would return all of the necessary data:</span></span>

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

<span data-ttu-id="85632-211">Jede zurückgegebene Zeile enthält sowohl Benutzer-als auch Post-Daten.</span><span class="sxs-lookup"><span data-stu-id="85632-211">Each returned row includes both User and Post data.</span></span> <span data-ttu-id="85632-212">Da die Benutzerdaten der Post-Daten über die Eigenschaft "Besitzer" angefügt werden soll, wird die folgende Funktion verwendet:</span><span class="sxs-lookup"><span data-stu-id="85632-212">Since the User data should be attached to the Post data via its Owner property, the following function is used:</span></span>

```csharp
(post, user) => { post.Owner = user; return post; }
```

<span data-ttu-id="85632-213">Die vollständige Codeliste eine Auflistung von Beiträgen ihre Eigenschaft "Besitzer" mit den zugehörigen Benutzerdaten aufgefüllt zurückgegeben würde folgendermaßen lauten:</span><span class="sxs-lookup"><span data-stu-id="85632-213">The full code listing to return a collection of posts with their Owner property populated with the associated user data would be:</span></span>

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

<span data-ttu-id="85632-214">Er weniger Kapselung bietet, dapper, durch Quellformat, sodass Entwickler wissen, wie ihre Daten gespeichert sind, werden Informationen zum effizienten Abfragen der und Schreiben weiteren Code, um sie abzurufen.</span><span class="sxs-lookup"><span data-stu-id="85632-214">Because it offers less encapsulation, Dapper requires developers know more about how their data is stored, how to query it efficiently, and write more code to fetch it.</span></span> <span data-ttu-id="85632-215">Wenn das Modell ändert statt einfach erstellen eine neue Migration (Feature von einem anderen EF Core), und/oder Aktualisieren von Zuordnungsinformationen an einem Ort in ein ' DbContext ', muss jeder Abfrage, die betroffen ist, aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-215">When the model changes, instead of simply creating a new migration (another EF Core feature), and/or updating mapping information in one place in a DbContext, every query that is impacted must be updated.</span></span> <span data-ttu-id="85632-216">Diese Abfragen haben nicht kompilieren Zeit Garantien, damit sie zur Laufzeit als Reaktion auf Änderungen am Modell oder die Datenbank, was Fehler schnell erkennen erschwert unterbrechen können.</span><span class="sxs-lookup"><span data-stu-id="85632-216">These queries have not compile time guarantees, so they may break at runtime in response to changes to the model or database, making errors more difficult to detect quickly.</span></span> <span data-ttu-id="85632-217">Für diese Nachteile bietet dapper, durch extrem hohe Leistung.</span><span class="sxs-lookup"><span data-stu-id="85632-217">In exchange for these tradeoffs, Dapper offers extremely fast performance.</span></span>

<span data-ttu-id="85632-218">Für die meisten Anwendungen und die meisten Elemente der fast alle Anwendungen bietet EF Core akzeptable Leistung.</span><span class="sxs-lookup"><span data-stu-id="85632-218">For most applications, and most parts of almost all applications, EF Core offers acceptable performance.</span></span> <span data-ttu-id="85632-219">Daher werden seine Developer Produktivitätsvorteile wahrscheinlich überwiegen im Vergleich zu der Verwaltungsaufwand.</span><span class="sxs-lookup"><span data-stu-id="85632-219">Thus, its developer productivity benefits are likely to outweigh its performance overhead.</span></span> <span data-ttu-id="85632-220">Für Abfragen, die vom Cachedienst profitieren können, die eigentliche Abfrage kann nur ausgeführt werden ein kleiner Prozentsatz der Zeit, wodurch relativ kleine Abfragen Leistung Unterschiede Moot.</span><span class="sxs-lookup"><span data-stu-id="85632-220">For queries that can benefit from caching, the actual query may only be executed a tiny percentage of the time, making relatively small query performance differences moot.</span></span>

## <a name="sql-or-nosql"></a><span data-ttu-id="85632-221">SQL oder NoSQL</span><span class="sxs-lookup"><span data-stu-id="85632-221">SQL or NoSQL</span></span>

<span data-ttu-id="85632-222">In der Regel, relationalen SQL Server-Datenbanken haben dominiert Marketplace für persistente Speicherung von Daten, aber sie sind nicht die einzige verfügbare Lösung.</span><span class="sxs-lookup"><span data-stu-id="85632-222">Traditionally, relational databases like SQL Server have dominated the marketplace for persistent data storage, but they are not the only solution available.</span></span> <span data-ttu-id="85632-223">NoSQL-Datenbanken wie [MongoDB](https://www.mongodb.com/what-is-mongodb) bieten einen anderen Ansatz zum Speichern von Objekten.</span><span class="sxs-lookup"><span data-stu-id="85632-223">NoSQL databases like [MongoDB](https://www.mongodb.com/what-is-mongodb) offer a different approach to storing objects.</span></span> <span data-ttu-id="85632-224">Anstatt das mapping von Objekten zu Tabellen und Zeilen, ist eine weitere Option des gesamten Objektdiagramms serialisieren und Speichern des Ergebnisses.</span><span class="sxs-lookup"><span data-stu-id="85632-224">Rather than mapping objects to tables and rows, another option is to serialize the entire object graph, and store the result.</span></span> <span data-ttu-id="85632-225">Die Vorteile dieses Ansatzes sind zumindest am Anfang der Einfachheit und Leistung.</span><span class="sxs-lookup"><span data-stu-id="85632-225">The benefits of this approach, at least initially, are simplicity and performance.</span></span> <span data-ttu-id="85632-226">Es ist sicherlich einfacher zum Speichern eines einzelnen serialisierten Objekts mit einem Schlüssel als das Objekt in viele Tabellen mit Beziehungen zu zerlegen und Update- und Zeilen, die seit das Objekt zuletzt geändert wurden möglicherweise aus der Datenbank abgerufen.</span><span class="sxs-lookup"><span data-stu-id="85632-226">It's certainly simpler to store a single serialized object with a key than to decompose the object into many tables with relationships and update and rows that may have changed since the object was last retrieved from the database.</span></span> <span data-ttu-id="85632-227">Ebenso ist das Abrufen und Deserialisieren eines Objekts aus einem Schlüssel-basierten Speicher in der Regel wesentlich schneller und einfacher, als komplexe Joins oder mehrere Datenbankabfragen erforderlich, um das gleiche Objekt aus einer relationalen Datenbank vollständig zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="85632-227">Likewise, fetching and deserializing a single object from a key-based store is typically much faster and easier than complex joins or multiple database queries required to fully compose the same object from a relational database.</span></span> <span data-ttu-id="85632-228">Das Fehlen von Sperren, Transaktionen oder ein festes Schema macht keine NoSQL-Datenbanken auch sehr vielen Computern, die Unterstützung sehr großer Datasets Skalierung unterziehen.</span><span class="sxs-lookup"><span data-stu-id="85632-228">The lack of locks or transactions or a fixed schema also makes NoSQL databases very amenable to scaling across many machines, supporting very large datasets.</span></span>

<span data-ttu-id="85632-229">Andererseits, haben (wie sie in der Regel aufgerufen werden) keine NoSQL-Datenbanken jeweils vor-und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="85632-229">On the other hand, NoSQL databases (as they are typically called) have their drawbacks.</span></span> <span data-ttu-id="85632-230">Relationale Datenbanken verwendet die Normalisierung erzwingt die Konsistenz und vermeiden doppelte Daten.</span><span class="sxs-lookup"><span data-stu-id="85632-230">Relational databases use normalization to enforce consistency and avoid duplication of data.</span></span> <span data-ttu-id="85632-231">Dies verringert die Gesamtgröße der Datenbank und stellt sicher, dass die Updates auf freigegebene Daten in der gesamten Datenbank sofort verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="85632-231">This reduces the total size of the database and ensures that updates to shared data are available immediately throughout the database.</span></span> <span data-ttu-id="85632-232">In einer relationalen Datenbank möglicherweise eine Tabelle nach ID, eine Country-Tabelle verweisen, wenn ein Land Namen geändert wurden, die Adressdatensätze aus dem Update ohne selbst zu aktualisierenden profitieren würden.</span><span class="sxs-lookup"><span data-stu-id="85632-232">In a relational database, an Address table might reference a Country table by ID, such that if a country's name were changed, the address records would benefit from the update without themselves having to be updated.</span></span> <span data-ttu-id="85632-233">Allerdings kann in einer NoSQL-Datenbank, Adresse und die zugehörigen Land im Rahmen des viele gespeicherten Objekte serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-233">However, in a NoSQL database, Address and its associated Country might be serialized as part of many stored objects.</span></span> <span data-ttu-id="85632-234">Alle betroffenen Objekte aktualisiert werden, anstatt eine einzelne Zeile, ein Update auf eine landnamen müsste.</span><span class="sxs-lookup"><span data-stu-id="85632-234">An update to a country name would require all such objects to be updated, rather than a single row.</span></span> <span data-ttu-id="85632-235">Relationale Datenbanken können auch die relationale Integrität sicherstellen, durch das Durchsetzen von Regeln, z. B. Fremdschlüssel.</span><span class="sxs-lookup"><span data-stu-id="85632-235">Relational databases can also ensure relational integrity by enforcing rules like foreign keys.</span></span> <span data-ttu-id="85632-236">NoSQL-Datenbanken bieten diese Einschränkungen für ihre Daten in der Regel nicht.</span><span class="sxs-lookup"><span data-stu-id="85632-236">NoSQL databases typically do not offer such constraints on their data.</span></span>

<span data-ttu-id="85632-237">Die Komplexität NoSQL-Datenbanken behandelt werden müssen, eine andere ist versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="85632-237">Another complexity NoSQL databases must deal with is versioning.</span></span> <span data-ttu-id="85632-238">Wenn die Eigenschaften eines Objekts ändern, kann er werden nicht aus früheren Versionen nicht deserialisiert werden, die gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="85632-238">When an object's properties change, it may not be able to be deserialized from past versions that were stored.</span></span> <span data-ttu-id="85632-239">Daher müssen alle vorhandenen Objekte, die eine serialisierte (Vorgängerversion) des Objekts verfügen aktualisiert werden, um das neue Schema entsprechen.</span><span class="sxs-lookup"><span data-stu-id="85632-239">Thus, all existing objects that have a serialized (previous) version of the object must be updated to conform to its new schema.</span></span> <span data-ttu-id="85632-240">Dies unterscheidet sich nicht grundsätzlich aus einer relationalen Datenbank, wobei manchmal schemaänderungen Update Skripts erfordern oder die Zuordnung von Updates.</span><span class="sxs-lookup"><span data-stu-id="85632-240">This is not conceptually different from a relational database, where schema changes sometimes require update scripts or mapping updates.</span></span> <span data-ttu-id="85632-241">Die Anzahl von Einträgen, die geändert werden müssen, ist jedoch häufig wesentlich größer im NoSQL-Ansatz, da mehrere Kopien der Daten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="85632-241">However, the number of entries that must be modified is often much greater in the NoSQL approach, because there is more duplication of data.</span></span>

<span data-ttu-id="85632-242">Es ist möglich, NoSQL-Datenbanken zum Speichern von mehreren Versionen von Objekten, relationale Datenbanken ein festes Schema in der Regel nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85632-242">It's possible in NoSQL databases to store multiple versions of objects, something fixed schema relational databases typically do not support.</span></span> <span data-ttu-id="85632-243">Allerdings wird in diesem Fall der Anwendungscode müssen das Vorhandensein von früheren Versionen von Objekten, die zusätzliche Komplexität hinzufügen, berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="85632-243">However, in this case your application code will need to account for the existence of previous versions of objects, adding additional complexity.</span></span>

<span data-ttu-id="85632-244">NoSQL-Datenbanken in der Regel nicht erzwingen [ACID](http://en.wikipedia.org/wiki/ACID), das bedeutet, dass sie Leistungs-und Skalierbarkeitsvorteile über relationale Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="85632-244">NoSQL databases typically do not enforce [ACID](http://en.wikipedia.org/wiki/ACID), which means they have both performance and scalability benefits over relational databases.</span></span> <span data-ttu-id="85632-245">Sie sind gut geeignet für extrem großen Datasets und Objekte, die nicht in den Speicher im normalisierte Tabellenstrukturen gut geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="85632-245">They're well-suited to extremely large datasets and objects that are not well-suited to storage in normalized table structures.</span></span> <span data-ttu-id="85632-246">Es gibt keinen Grund, warum eine einzelne Anwendung kann nicht nutzen beide relationalen und NoSQL-Datenbanken, die mit den einzelnen, in denen ist es am besten geeignet.</span><span class="sxs-lookup"><span data-stu-id="85632-246">There is no reason why a single application cannot take advantage of both relational and NoSQL databases, using each where it is best suited.</span></span>

## <a name="azure-documentdb"></a><span data-ttu-id="85632-247">Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="85632-247">Azure DocumentDB</span></span>

<span data-ttu-id="85632-248">Azure DocumentDB ist ein vollständig verwalteter NoSQL-Datenbankdienst, der Cloud-basierten schemafreier Datenspeicher bietet.</span><span class="sxs-lookup"><span data-stu-id="85632-248">Azure DocumentDB is a fully managed NoSQL database service that offers cloud-based schema-free data storage.</span></span> <span data-ttu-id="85632-249">DocumentDB ist für die schnelle und zuverlässige Leistung, hohe Verfügbarkeit, flexible Skalierung und globale Verteilung integriert.</span><span class="sxs-lookup"><span data-stu-id="85632-249">DocumentDB is built for fast and predictable performance, high availability, elastic scaling, and global distribution.</span></span> <span data-ttu-id="85632-250">Obwohl ein NoSQL-Datenbank, können Entwickler umfangreiche und vertraute SQL-Abfragefunktionen JSON-Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="85632-250">Despite being a NoSQL database, developers can use rich and familiar SQL query capabilities on JSON data.</span></span> <span data-ttu-id="85632-251">Alle Ressourcen in DocumentDB werden als JSON-Dokumente gespeichert.</span><span class="sxs-lookup"><span data-stu-id="85632-251">All resources in DocumentDB are stored as JSON documents.</span></span> <span data-ttu-id="85632-252">Ressourcen werden als verwaltet *Elemente*, welche werden alle Dokumente, die Metadaten, und *feeds*, wobei es sich um Auflistungen von Elementen.</span><span class="sxs-lookup"><span data-stu-id="85632-252">Resources are managed as *items*, which are documents containing metadata, and *feeds*, which are collections of items.</span></span> <span data-ttu-id="85632-253">Abbildung 8 – 2 zeigt die Beziehung zwischen verschiedenen DocumentDB-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="85632-253">Figure 8-2 shows the relationship between different DocumentDB resources.</span></span>


![Die hierarchische Beziehung zwischen Ressourcen in DocumentDB, eine JSON NoSQL-Datenbank](./media/image8-2.png)

<span data-ttu-id="85632-255">**Abbildung 8-2.**</span><span class="sxs-lookup"><span data-stu-id="85632-255">**Figure 8-2.**</span></span> <span data-ttu-id="85632-256">DocumentDB-Ressourcen-Organisation.</span><span class="sxs-lookup"><span data-stu-id="85632-256">DocumentDB resource organization.</span></span>

<span data-ttu-id="85632-257">Die DocumentDB-Abfragesprache ist eine einfache, aber leistungsstarker Schnittstelle zum Abfragen von JSON-Dokumente.</span><span class="sxs-lookup"><span data-stu-id="85632-257">The DocumentDB query language is a simple yet powerful interface for querying JSON documents.</span></span> <span data-ttu-id="85632-258">Die Sprache unterstützt eine Teilmenge der ANSI SQL-Grammatik und fügt die enge Integration der JavaScript-Objekt, Arrays, Objektkonstruktion und Funktionsaufruf hinzu.</span><span class="sxs-lookup"><span data-stu-id="85632-258">The language supports a subset of ANSI SQL grammar and adds deep integration of JavaScript object, arrays, object construction, and function invocation.</span></span>

<span data-ttu-id="85632-259">**Verweise – DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="85632-259">**References – DocumentDB**</span></span>

-   <span data-ttu-id="85632-260">DocumentDB Introduction\\</span><span class="sxs-lookup"><span data-stu-id="85632-260">DocumentDB Introduction\\</span></span>
    <span data-ttu-id="85632-261"><https://docs.Microsoft.com/Azure/documentdb/documentdb-Introduction></span><span class="sxs-lookup"><span data-stu-id="85632-261"><https://docs.microsoft.com/azure/documentdb/documentdb-introduction></span></span>

## <a name="other-persistence-options"></a><span data-ttu-id="85632-262">Andere Optionen Persistenz</span><span class="sxs-lookup"><span data-stu-id="85632-262">Other Persistence Options</span></span>

<span data-ttu-id="85632-263">ASP.NET Core-Anwendungen können zusätzlich zum relationalen und NoSQL-Speicheroptionen Azure-Speicher verwenden, um eine Vielzahl von Datenformaten und Dateien in einer Cloud-basierte, skalierbare Weise zu speichern.</span><span class="sxs-lookup"><span data-stu-id="85632-263">In addition to relational and NoSQL storage options, ASP.NET Core applications can use Azure Storage to store a variety of data formats and files in a cloud-based, scalable fashion.</span></span> <span data-ttu-id="85632-264">Azure-Speicher ist hochgradig skalierbare, damit Sie starten können, speichern kleine Mengen von Daten und skaliert und an Hunderte oder Terabyte gespeichert werden, wenn die Anwendung dies erfordert.</span><span class="sxs-lookup"><span data-stu-id="85632-264">Azure Storage is massively scalable, so you can start out storing small amounts of data and scale up to storing hundreds or terabytes if your application requires it.</span></span> <span data-ttu-id="85632-265">Azure-Speicher unterstützt vier Arten von Daten:</span><span class="sxs-lookup"><span data-stu-id="85632-265">Azure Storage supports four kinds of data:</span></span>

-   <span data-ttu-id="85632-266">BLOB-Speicher für unstrukturiertem Text oder binär Speicher, auch als Objektspeicher bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="85632-266">Blob Storage for unstructured text or binary storage, also referred to as object storage.</span></span>

-   <span data-ttu-id="85632-267">Tabellenspeicher für strukturierte Datasets, die über Zeilenschlüsseln zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="85632-267">Table Storage for structured datasets, accessible via row keys.</span></span>

-   <span data-ttu-id="85632-268">Warteschlangenspeicher für zuverlässige warteschlangenbasierte messaging.</span><span class="sxs-lookup"><span data-stu-id="85632-268">Queue Storage for reliable queue-based messaging.</span></span>

-   <span data-ttu-id="85632-269">Dateispeicher für den Zugriff auf freigegebene Dateien zwischen Azure Virtual Machines und lokale Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="85632-269">File Storage for shared file access between Azure virtual machines and on-premises applications.</span></span>

<span data-ttu-id="85632-270">**Verweise – Azure-Speicher**</span><span class="sxs-lookup"><span data-stu-id="85632-270">**References – Azure Storage**</span></span>

-   <span data-ttu-id="85632-271">Azure-Speicher Introduction\\</span><span class="sxs-lookup"><span data-stu-id="85632-271">Azure Storage Introduction\\</span></span>
    <span data-ttu-id="85632-272"><https://docs.Microsoft.com/Azure/Storage/Storage-Introduction></span><span class="sxs-lookup"><span data-stu-id="85632-272"><https://docs.microsoft.com/azure/storage/storage-introduction></span></span>

## <a name="caching"></a><span data-ttu-id="85632-273">Zwischenspeicherung</span><span class="sxs-lookup"><span data-stu-id="85632-273">Caching</span></span>

<span data-ttu-id="85632-274">In Webanwendungen sollte jeder webanforderung in der kürzestmöglichen Zeit abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="85632-274">In web applications, each web request should be completed in the shortest time possible.</span></span> <span data-ttu-id="85632-275">Eine Möglichkeit, dies zu erreichen, ist die Anzahl der externen Aufrufe zu begrenzen, die der Server vornehmen muss, um die Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="85632-275">One way to achieve this is to limit the number of external calls the server must make to complete the request.</span></span> <span data-ttu-id="85632-276">Zwischenspeichern umfasst eine Kopie der Daten auf dem Server gespeichert (oder einem anderen Datenspeicher also mehr als die Quelle der Daten leicht abgefragt).</span><span class="sxs-lookup"><span data-stu-id="85632-276">Caching involves storing a copy of data on the server (or another data store that is more easily queried than the source of the data).</span></span> <span data-ttu-id="85632-277">Webanwendungen und vor allem nicht SPA herkömmlichen Web-Anwendungen müssen die vollständige Benutzeroberfläche mit jeder Anforderung erstellen.</span><span class="sxs-lookup"><span data-stu-id="85632-277">Web applications, and especially non-SPA traditional web applications, need to build the entire user interface with every request.</span></span> <span data-ttu-id="85632-278">Dabei werden häufig viele der gleichen Datenbankabfragen wiederholt aus einer benutzeranforderung zur nächsten.</span><span class="sxs-lookup"><span data-stu-id="85632-278">This frequently involves making many of the same database queries repeatedly from one user request to the next.</span></span> <span data-ttu-id="85632-279">In den meisten Fällen ändert diese Daten in seltenen Fällen gibt es also ratsam ständig es aus der Datenbank anfordern.</span><span class="sxs-lookup"><span data-stu-id="85632-279">In most cases, this data changes rarely, so there is little reason to constantly request it from the database.</span></span> <span data-ttu-id="85632-280">ASP.NET Core unterstützt Zwischenspeichern von Antworten zum Zwischenspeichern von ganzen Seiten und Zwischenspeichern von Daten, die präziseren Verhalten beim Zwischenspeichern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="85632-280">ASP.NET Core supports response caching, for caching entire pages, and data caching, which supports more granular caching behavior.</span></span>

<span data-ttu-id="85632-281">Beim caching implementieren, ist es wichtig zu beachten Sie die Trennung von Anliegen.</span><span class="sxs-lookup"><span data-stu-id="85632-281">When implementing caching, it's important to keep in mind separation of concerns.</span></span> <span data-ttu-id="85632-282">Vermeiden Sie Cachelogik implementieren, in der darauf von Datenzugriffslogik oder in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="85632-282">Avoid implementing caching logic in your data access logic, or in your user interface.</span></span> <span data-ttu-id="85632-283">Stattdessen kapseln Sie Zwischenspeichern in einem eigenen Klassen, und verwenden Sie der Konfiguration zum Verwalten des Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="85632-283">Instead, encapsulate caching in its own classes, and use configuration to manage its behavior.</span></span> <span data-ttu-id="85632-284">Dies folgt die Öffnen/geschlossen und die einzelnen Verantwortung Prinzipien und erleichtert die Verwendung von caching in Ihrer Anwendung, während diese wächst verwalten.</span><span class="sxs-lookup"><span data-stu-id="85632-284">This follows the Open/Closed and Single Responsibility principles, and will make it easier for you to manage how you use caching in your application as it grows.</span></span>

### <a name="aspnet-core-response-caching"></a><span data-ttu-id="85632-285">ASP.NET Core Zwischenspeichern von Antworten</span><span class="sxs-lookup"><span data-stu-id="85632-285">ASP.NET Core Response Caching</span></span>

<span data-ttu-id="85632-286">ASP.NET Core unterstützt zwei Ebenen Zwischenspeichern von Antworten.</span><span class="sxs-lookup"><span data-stu-id="85632-286">ASP.NET Core supports two levels of response caching.</span></span> <span data-ttu-id="85632-287">Die erste Ebene nicht alles auf dem Server zwischenspeichert, fügt jedoch HTTP-Header, mit die Clients und Proxyservern zum Zwischenspeichern von Antworten angewiesen.</span><span class="sxs-lookup"><span data-stu-id="85632-287">The first level does not cache anything on the server, but adds HTTP headers that instruct clients and proxy servers to cache responses.</span></span> <span data-ttu-id="85632-288">Dies wird durch Hinzufügen von Attributs ResponseCache auf einzelnen Domänencontrollern oder Aktionen implementiert:</span><span class="sxs-lookup"><span data-stu-id="85632-288">This is implemented by adding the ResponseCache attribute to individual controllers or actions:</span></span>

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

<span data-ttu-id="85632-289">Die Antwort zwischenspeichern Middleware werden Antworten, die basierend auf einem Satz von Bedingungen, die Sie anpassen können, automatisch zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-289">The Response Caching Middleware will automatically cache responses based on a set of conditions, which you can customize.</span></span> <span data-ttu-id="85632-290">Standardmäßig werden nur 200 (OK), über GET oder HEAD Methoden angeforderte Antworten zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="85632-290">By default, only 200 (OK) responses requested via GET or HEAD methods are cached.</span></span> <span data-ttu-id="85632-291">Darüber hinaus benötigen Anfragen eine Antwort mit dem Cache-Control: öffentlichen Header und schließen Sie kann nicht für die Autorisierung oder Set-Cookie-Header.</span><span class="sxs-lookup"><span data-stu-id="85632-291">In addition, requests must have a response with a Cache-Control: public header, and cannot include headers for Authorization or Set-Cookie.</span></span> <span data-ttu-id="85632-292">Finden Sie unter einem [Aufstellung der zwischenspeichernden Bedingungen dar, die von der Antwort zwischenspeichern Middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span><span class="sxs-lookup"><span data-stu-id="85632-292">See a [complete list of the caching conditions used by the response caching middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).</span></span>

### <a name="data-caching"></a><span data-ttu-id="85632-293">Zwischenspeichern von Daten</span><span class="sxs-lookup"><span data-stu-id="85632-293">Data Caching</span></span>

<span data-ttu-id="85632-294">Statt (oder zusätzlich) vollständige Web zwischenspeichern, können Sie die Ergebnisse der einzelnen Datenabfragen Zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="85632-294">Rather than (or in addition to) caching full web responses, you can cache the results of individual data queries.</span></span> <span data-ttu-id="85632-295">Hierzu können Sie im Arbeitsspeicher Zwischenspeichern auf dem Webserver verwenden, oder [einen verteilten Cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span><span class="sxs-lookup"><span data-stu-id="85632-295">For this, you can use in memory caching on the web server, or use [a distributed cache](https://docs.microsoft.com/aspnet/core/performance/caching/distributed).</span></span> <span data-ttu-id="85632-296">In diesem Abschnitt wird im Arbeitsspeicher Zwischenspeichern Implementierung veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="85632-296">This section will demonstrate how to implement in memory caching.</span></span>

<span data-ttu-id="85632-297">Sie fügen Sie Unterstützung für den Speicher hinzu (oder verteilt) in ConfigureServices Zwischenspeichern:</span><span class="sxs-lookup"><span data-stu-id="85632-297">You add support for memory (or distributed) caching in ConfigureServices:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

<span data-ttu-id="85632-298">Achten Sie darauf, dass das Microsoft.Extensions.Caching.Memory NuGet-Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="85632-298">Be sure to add the Microsoft.Extensions.Caching.Memory NuGet package as well.</span></span>

<span data-ttu-id="85632-299">Nachdem Sie den Dienst hinzugefügt haben, fordern Sie IMemoryCache über Abhängigkeitsinjektion, wo Sie auf den Cache zugreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="85632-299">Once you've added the service, you request IMemoryCache via dependency injection wherever you need to access the cache.</span></span> <span data-ttu-id="85632-300">In diesem Beispiel ist der CachedCatalogService das Entwurfsmuster Proxy (oder Decorator-Element), durch die Bereitstellung einer alternativen Implementierung des ICatalogService, die steuert den Zugriff auf (oder Verhalten fügt) mithilfe der zugrunde liegenden CatalogService-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="85632-300">In this example, the CachedCatalogService is using the Proxy (or Decorator) design pattern, by providing an alternative implementation of ICatalogService that controls access to (or adds behavior to) the underlying CatalogService implementation.</span></span>

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

<span data-ttu-id="85632-301">Um die Anwendung die zwischengespeicherte Version des Diensts verwenden, aber dennoch kann der Dienst zum Abrufen einer Instanz des CatalogService in seinem Konstruktor benötigten zu konfigurieren, würden Sie Folgendes in ConfigureServices hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="85632-301">To configure the application to use the cached version of the service, but still allow the service to get the instance of CatalogService it needs in its constructor, you would add the following in ConfigureServices:</span></span>

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

<span data-ttu-id="85632-302">Mit diesem vorhanden werden die Datenbankaufrufe zum Abrufen der Katalogdaten nur einmal pro Minute und nicht bei jeder Anforderung vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="85632-302">With this in place, the database calls to fetch the catalog data will only be made once per minute, rather than on every request.</span></span> <span data-ttu-id="85632-303">Abhängig von der Datenverkehr an den Standort kann dies einen sehr entscheidenden Einfluss auf die Anzahl der Abfragen, die mit der Datenbank und die durchschnittliche Seitenladezeit auf der Startseite, von denen die Abfragen, die von diesem Dienst verfügbar gemacht werden alle drei derzeit abhängig gemacht haben.</span><span class="sxs-lookup"><span data-stu-id="85632-303">Depending on the traffic to the site, this can have a very significant impact on the number of queries made to the database, and the average page load time for the home page that currently depends on all three of the queries exposed by this service.</span></span>

<span data-ttu-id="85632-304">Ist ein Problem, das entsteht, wenn das Zwischenspeichern implementiert ist *abgelaufene Daten* – d. h. die Quelle jedoch eine veraltete Version geänderten Daten verbleiben im Cache.</span><span class="sxs-lookup"><span data-stu-id="85632-304">An issue that arises when caching is implemented is *stale data* – that is, data that has changed at the source but an out of date version remains in the cache.</span></span> <span data-ttu-id="85632-305">Eine einfache Möglichkeit, dieses Problem zu beheben ist die Verwendung von kleinen Cache Dauerangaben, Pflege, weil für eine ausgelastete Anwendung beschränkt zusätzlicher Vorteil auf, erweitern die Länge, die Daten zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-305">A simple way to mitigate this issue is to use small cache durations, since for a busy application there is limited additional benefit to extending the length data is cached.</span></span> <span data-ttu-id="85632-306">Betrachten Sie beispielsweise eine Seite, die eine einzelnen Datenbankabfrage macht und 10 Mal pro Sekunde angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="85632-306">For example, consider a page that makes a single database query, and is requested 10 times per second.</span></span> <span data-ttu-id="85632-307">Wenn diese Seite eine Minute lang zwischengespeichert wird, führt dies zu der Anzahl von Datenbankabfragen vorgenommen pro Minute auf 1, eine Reduzierung der 99,8 % von 600 gelöscht.</span><span class="sxs-lookup"><span data-stu-id="85632-307">If this page is cached for one minute, it will result in the number of database queries made per minute to drop from 600 to 1, a reduction of 99.8%.</span></span> <span data-ttu-id="85632-308">Wenn stattdessen die Cachedauer einstündigen vorgenommen wurden, die allgemeine Reduzierung wäre 99.997 %, aber jetzt die Wahrscheinlichkeit und potenzielle Alter der veraltete Daten werden sowohl erhöht erheblich.</span><span class="sxs-lookup"><span data-stu-id="85632-308">If instead the cache duration were made one hour, the overall reduction would be 99.997%, but now the likelihood and potential age of stale data are both increased dramatically.</span></span>

<span data-ttu-id="85632-309">Ein anderer Ansatz besteht darin, Cacheeinträge proaktiv zu entfernen, wenn die darin enthaltenen Daten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="85632-309">Another approach is to proactively remove cache entries when the data they contain is updated.</span></span> <span data-ttu-id="85632-310">Einzelne Einträge kann entfernt werden, wenn der Schlüssel bekannt ist:</span><span class="sxs-lookup"><span data-stu-id="85632-310">Any individual entry can be removed if its key is known:</span></span>

```csharp
_cache.Remove(cacheKey);
```

<span data-ttu-id="85632-311">Wenn Ihre Anwendung verfügbar macht, Funktionen zum Aktualisieren der Einträge, die zwischengespeichert werden, können Sie die entsprechenden Einträge in Ihrem Code entfernen, die die Updates ausführt.</span><span class="sxs-lookup"><span data-stu-id="85632-311">If your application exposes functionality for updating entries that it caches, you can remove the corresponding cache entries in your code that performs the updates.</span></span> <span data-ttu-id="85632-312">In einigen Fällen möglicherweise viele verschiedene Einträge, die einen bestimmten Satz von Daten abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="85632-312">Sometimes there may be many different entries that depend on a particular set of data.</span></span> <span data-ttu-id="85632-313">In diesem Fall kann es zum Erstellen von Abhängigkeiten zwischen Cacheeinträge mithilfe einer CancellationChangeToken hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="85632-313">In that case, it can be useful to create dependencies between cache entries, by using a CancellationChangeToken.</span></span> <span data-ttu-id="85632-314">Mit einem CancellationChangeToken können Sie das Token abgebrochen gleichzeitig mehrere Einträge im Cache ablaufen.</span><span class="sxs-lookup"><span data-stu-id="85632-314">With a CancellationChangeToken, you can expire multiple cache entries at once by cancelling the token.</span></span>

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
<span data-ttu-id="85632-315">[Vorherigen] (Develop-asp-net-core-mvc-apps.md) [weiter] (Test-asp-net-core-mvc-apps.md)</span><span class="sxs-lookup"><span data-stu-id="85632-315">[Previous] (develop-asp-net-core-mvc-apps.md) [Next] (test-asp-net-core-mvc-apps.md)</span></span>
