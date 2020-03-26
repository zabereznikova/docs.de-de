---
title: Migration von ASP.NET Web Forms nach Blazor
description: Erfahren Sie, wie Sie die Migration einer vorhandenen ASP.NET Web Forms-App nach Blazor angehen.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134091"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="74787-103">Migration von ASP.NET Web Forms nach Blazor</span><span class="sxs-lookup"><span data-stu-id="74787-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="74787-104">Das Migrieren einer Codebasis aus ASP.NET Web Forms nach Blazor ist eine zeitaufwändige Aufgabe, die eine Planung erfordert.</span><span class="sxs-lookup"><span data-stu-id="74787-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="74787-105">In diesem Kapitel wird der Prozess beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74787-105">This chapter outlines the process.</span></span> <span data-ttu-id="74787-106">Eine Möglichkeit, den Übergang zu erleichtern, besteht darin, sicherzustellen, dass die App einer *N-Tier-Architektur* entspricht, wobei das App-Modell (in diesem Fall Web Forms) von der Geschäftslogik getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="74787-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="74787-107">Diese logische Trennung von Ebenen macht deutlich, was zu .NET Core und Blazor verschoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="74787-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="74787-108">In diesem Beispiel wird die auf [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) verfügbare eShop-App verwendet.</span><span class="sxs-lookup"><span data-stu-id="74787-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="74787-109">eShop ist ein Katalogservice, der CRUD-Funktionen über Formulareingabe und -validierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="74787-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="74787-110">Warum sollte eine funktionierende App nach Blazor migriert werden?</span><span class="sxs-lookup"><span data-stu-id="74787-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="74787-111">Oft gibt es keine Notwendigkeit.</span><span class="sxs-lookup"><span data-stu-id="74787-111">Many times, there's no need.</span></span> <span data-ttu-id="74787-112">ASP.NET Web Forms wird noch viele Jahre lang unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74787-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="74787-113">Viele der funktionen, die Blazor bereitstellt, werden jedoch nur in einer migrierten App unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74787-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="74787-114">Zu diesen Funktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="74787-114">Such features include:</span></span>

- <span data-ttu-id="74787-115">Leistungsverbesserungen im Rahmen, wie z. B.`Span<T>`</span><span class="sxs-lookup"><span data-stu-id="74787-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="74787-116">Fähigkeit, als WebAssembly ausgeführt zu werden</span><span class="sxs-lookup"><span data-stu-id="74787-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="74787-117">Plattformübergreifende Unterstützung für Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="74787-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="74787-118">App-lokale Bereitstellung oder bereitstellung eines freigegebenen Frameworks ohne Auswirkungen auf andere Apps</span><span class="sxs-lookup"><span data-stu-id="74787-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="74787-119">Wenn diese oder andere neue Funktionen überzeugend genug sind, kann es einen Wert für die Migration der App geben.</span><span class="sxs-lookup"><span data-stu-id="74787-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="74787-120">Die Migration kann verschiedene Formen annehmen. Es kann die gesamte App oder nur bestimmte Endpunkte sein, die die Änderungen erfordern.</span><span class="sxs-lookup"><span data-stu-id="74787-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="74787-121">Die Entscheidung für die Migration basiert letztlich auf den Geschäftsproblemen, die vom Entwickler gelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="74787-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="74787-122">Serverseitiges im Vergleich zum clientseitigen Hosting</span><span class="sxs-lookup"><span data-stu-id="74787-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="74787-123">Wie im [Kapitel Hostingmodelle](hosting-models.md) beschrieben, kann eine Blazor-App auf zwei verschiedene Arten gehostet werden: server- und clientseitig.</span><span class="sxs-lookup"><span data-stu-id="74787-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="74787-124">Das serverseitige Modell verwendet ASP.NET Core SignalR-Verbindungen, um die DOM-Updates zu verwalten, während der tatsächliche Code auf dem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74787-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="74787-125">Das clientseitige Modell wird als WebAssembly in einem Browser ausgeführt und erfordert keine Serververbindungen.</span><span class="sxs-lookup"><span data-stu-id="74787-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="74787-126">Es gibt eine Reihe von Unterschieden, die sich auf eine bestimmte App auswirken können:</span><span class="sxs-lookup"><span data-stu-id="74787-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="74787-127">Das Ausführen als WebAssembly befindet sich noch in der Entwicklung und unterstützt möglicherweise nicht alle Features (z. B. Threading) zum aktuellen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="74787-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="74787-128">Die Chaty-Kommunikation zwischen Client und Server kann zu Latenzproblemen im serverseitigen Modus führen</span><span class="sxs-lookup"><span data-stu-id="74787-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="74787-129">Der Zugriff auf Datenbanken und interne oder geschützte Dienste erfordert einen separaten Dienst mit clientseitigem Hosting</span><span class="sxs-lookup"><span data-stu-id="74787-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="74787-130">Zum Zeitpunkt des Schreibens ähnelt das serverseitige Modell eher Web Forms.</span><span class="sxs-lookup"><span data-stu-id="74787-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="74787-131">Der größte Teil dieses Kapitels konzentriert sich auf das serverseitige Hostingmodell, da es produktionsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="74787-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="74787-132">Erstellen eines neuen Projekts</span><span class="sxs-lookup"><span data-stu-id="74787-132">Create a new project</span></span>

<span data-ttu-id="74787-133">Dieser erste Migrationsschritt besteht darin, ein neues Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74787-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="74787-134">Dieser Projekttyp basiert auf den SDK-Projekten von .NET Core und vereinfacht einen Großteil der Bausteinplatte, die in früheren Projektformaten verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="74787-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="74787-135">Weitere Einzelheiten finden Sie im Kapitel [über Projektstruktur](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="74787-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="74787-136">Nachdem das Projekt erstellt wurde, installieren Sie die Bibliotheken, die im vorherigen Projekt verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="74787-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="74787-137">In älteren Web Forms-Projekten haben Sie möglicherweise die Datei *packages.config* verwendet, um die erforderlichen NuGet-Pakete aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="74787-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="74787-138">Im neuen SDK-Projekt wurde *packages.config* durch `<PackageReference>` Elemente in der Projektdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="74787-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="74787-139">Ein Vorteil dieses Ansatzes besteht darin, dass alle Abhängigkeiten transitiv installiert werden.</span><span class="sxs-lookup"><span data-stu-id="74787-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="74787-140">Sie listen nur die Abhängigkeiten der obersten Ebene auf, die Ihnen wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="74787-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="74787-141">Viele der von Ihnen verwendenden Abhängigkeiten sind für .NET Core verfügbar, einschließlich Entity Framework 6 und log4net.</span><span class="sxs-lookup"><span data-stu-id="74787-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="74787-142">Wenn keine .NET Core- oder .NET Standard-Version verfügbar ist, kann die .NET Framework-Version häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="74787-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="74787-143">Ihre Erfahrungen können hiervon abweichen.</span><span class="sxs-lookup"><span data-stu-id="74787-143">Your mileage may vary.</span></span> <span data-ttu-id="74787-144">Jede API, die in .NET Core nicht verfügbar ist, verursacht einen Laufzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="74787-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="74787-145">Visual Studio benachrichtigt Sie über solche Pakete.</span><span class="sxs-lookup"><span data-stu-id="74787-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="74787-146">Auf dem **Referenzknoten** des Projekts im **Projektmappen-Explorer**wird ein gelbes Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="74787-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="74787-147">Im Blazor-basierten eShop-Projekt können Sie die pakete sehen, die installiert sind.</span><span class="sxs-lookup"><span data-stu-id="74787-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="74787-148">Zuvor listete die Datei *packages.config* jedes im Projekt verwendete Paket auf, was zu einer Fast 50 Zeilen langen Datei führte.</span><span class="sxs-lookup"><span data-stu-id="74787-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="74787-149">Ein Ausschnitt von *packages.config* ist:</span><span class="sxs-lookup"><span data-stu-id="74787-149">A snippet of *packages.config* is:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

<span data-ttu-id="74787-150">Das `<packages>` Element enthält alle erforderlichen Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="74787-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="74787-151">Es ist schwierig zu identifizieren, welche dieser Pakete enthalten sind, da Sie sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="74787-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="74787-152">Einige `<package>` Elemente werden einfach aufgelistet, um die Anforderungen von Abhängigkeiten zu erfüllen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="74787-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="74787-153">Das Blazor-Projekt listet die Abhängigkeiten `<ItemGroup>` auf, die Sie innerhalb eines Elements in der Projektdatei benötigen:</span><span class="sxs-lookup"><span data-stu-id="74787-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="74787-154">Ein NuGet-Paket, das die Lebensdauer von Web Forms-Entwicklern vereinfacht, ist das [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="74787-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="74787-155">Obwohl .NET Core plattformübergreifend ist, sind einige Funktionen nur unter Windows verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74787-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="74787-156">Windows-spezifische Funktionen werden durch die Installation des Kompatibilitätspakets zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="74787-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="74787-157">Beispiele für solche Funktionen sind die Registrierungs-, WMI- und Verzeichnisdienste.</span><span class="sxs-lookup"><span data-stu-id="74787-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="74787-158">Das Paket fügt rund 20.000 APIs hinzu und aktiviert viele Dienste, mit denen Sie möglicherweise bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="74787-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="74787-159">Für das eShop-Projekt ist das Kompatibilitätspaket nicht erforderlich. Wenn Ihre Projekte jedoch Windows-spezifische Features verwenden, erleichtert das Paket die Migrationsbemühungen.</span><span class="sxs-lookup"><span data-stu-id="74787-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="74787-160">Startvorgang aktivieren</span><span class="sxs-lookup"><span data-stu-id="74787-160">Enable startup process</span></span>

<span data-ttu-id="74787-161">Der Startvorgang für Blazor wurde von Web Forms geändert und folgt einem ähnlichen Setup für andere ASP.NET Core-Diensten.</span><span class="sxs-lookup"><span data-stu-id="74787-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="74787-162">Wenn die Serverseite gehostet wird, werden Blazor-Komponenten als Teil einer normalen ASP.NET Core-App ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74787-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="74787-163">Wenn Blazor-Komponenten im Browser mit WebAssembly gehostet werden, verwenden sie ein ähnliches Hostingmodell.</span><span class="sxs-lookup"><span data-stu-id="74787-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="74787-164">Der Unterschied besteht darin, dass die Komponenten als separater Dienst von einem der Back-End-Prozesse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="74787-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="74787-165">So oder so ist der Start ähnlich.</span><span class="sxs-lookup"><span data-stu-id="74787-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="74787-166">Die *Global.asax.cs* Datei ist die Standardstartseite für Web Forms-Projekte.</span><span class="sxs-lookup"><span data-stu-id="74787-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="74787-167">Im eShop-Projekt konfiguriert diese Datei den Container Inversion of Control (IoC) und verarbeitet die verschiedenen Lebenszyklusereignisse der App oder Anforderung.</span><span class="sxs-lookup"><span data-stu-id="74787-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="74787-168">Einige dieser Ereignisse werden mit Middleware `Application_BeginRequest`behandelt (z. B. ).</span><span class="sxs-lookup"><span data-stu-id="74787-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="74787-169">Andere Ereignisse erfordern das Überschreiben bestimmter Dienste über Abhängigkeitsinjektion (DI).</span><span class="sxs-lookup"><span data-stu-id="74787-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="74787-170">Die *Global.asax.cs* Datei für eShop enthält beispielsweise den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="74787-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// http://docs.autofac.org/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

<span data-ttu-id="74787-171">Die vorhergehende `Startup` Datei wird zur Klasse im serverseitigen Blazor:</span><span class="sxs-lookup"><span data-stu-id="74787-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

<span data-ttu-id="74787-172">Eine wesentliche Änderung, die Sie von Web Forms bemerken können, ist die Bedeutung von DI.</span><span class="sxs-lookup"><span data-stu-id="74787-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="74787-173">DI ist ein Leitgedanke im ASP.NET Core-Design.</span><span class="sxs-lookup"><span data-stu-id="74787-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="74787-174">Es unterstützt die Anpassung fast aller Aspekte des ASP.NET Core-Frameworks.</span><span class="sxs-lookup"><span data-stu-id="74787-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="74787-175">Es gibt sogar einen integrierten Dienstanbieter, der für viele Szenarien verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="74787-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="74787-176">Wenn mehr Anpassungen erforderlich sind, kann sie von den vielen Community-Projekten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="74787-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="74787-177">Sie können z. B. Ihre DI-Bibliotheksinvestitionen von Drittanbietern vortragen.</span><span class="sxs-lookup"><span data-stu-id="74787-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="74787-178">In der ursprünglichen eShop-App gibt es eine konfiguration für die Sitzungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="74787-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="74787-179">Da der serverseitige Blazor ASP.NET Core SignalR für die Kommunikation verwendet, wird der Sitzungsstatus nicht unterstützt, da die Verbindungen unabhängig von einem HTTP-Kontext auftreten können.</span><span class="sxs-lookup"><span data-stu-id="74787-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="74787-180">Eine App, die den Sitzungsstatus verwendet, erfordert eine Neuarchitektur, bevor sie als Blazor-App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74787-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="74787-181">Weitere Informationen zum App-Start finden Sie unter [App-Start](app-startup.md).</span><span class="sxs-lookup"><span data-stu-id="74787-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="74787-182">Migrieren von HTTP-Modulen und -Handlern zur Middleware</span><span class="sxs-lookup"><span data-stu-id="74787-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="74787-183">HTTP-Module und -Handler sind häufige Muster in Web Forms, um die HTTP-Anforderungspipeline zu steuern.</span><span class="sxs-lookup"><span data-stu-id="74787-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="74787-184">Klassen, `IHttpModule` die `IHttpHandler` eingehende Anforderungen implementieren oder registrieren und verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="74787-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="74787-185">Web Forms konfiguriert Module und Handler in der Datei *web.config.*</span><span class="sxs-lookup"><span data-stu-id="74787-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="74787-186">Web Forms basiert auch stark auf der Behandlung von App-Lebenszyklus-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="74787-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="74787-187">ASP.NET Core verwendet stattdessen Middleware.</span><span class="sxs-lookup"><span data-stu-id="74787-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="74787-188">Middleware ist in `Configure` der `Startup` Methode der Klasse registriert.</span><span class="sxs-lookup"><span data-stu-id="74787-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="74787-189">Die Middleware-Ausführungsreihenfolge wird durch den Registrierungsauftrag bestimmt.</span><span class="sxs-lookup"><span data-stu-id="74787-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="74787-190">Im Abschnitt [Startprozess aktivieren](#enable-startup-process) wurde von Web Forms `Application_BeginRequest` als Methode ein Lebenszyklusereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="74787-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="74787-191">Dieses Ereignis ist in ASP.NET Core nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74787-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="74787-192">Eine Möglichkeit, dieses Verhalten zu erreichen, besteht darin, Middleware zu implementieren, wie sie im *Beispiel Startup.cs* Datei gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="74787-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="74787-193">Diese Middleware führt die gleiche Logik aus und überträgt dann die Steuerung an den nächsten Handler in der Middlewarepipeline.</span><span class="sxs-lookup"><span data-stu-id="74787-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="74787-194">Weitere Informationen zum Migrieren von Modulen und Handlern finden Sie unter [Migrieren von HTTP-Handlern und -Modulen zu ASP.NET Core-Middleware](/aspnet/core/migration/http-modules).</span><span class="sxs-lookup"><span data-stu-id="74787-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="74787-195">Migration statischer Dateien</span><span class="sxs-lookup"><span data-stu-id="74787-195">Migrate static files</span></span>

<span data-ttu-id="74787-196">Um statische Dateien (z. B. HTML, CSS, Images und JavaScript) zu bedienen, müssen die Dateien von Middleware verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="74787-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="74787-197">Durch `UseStaticFiles` Aufrufen der Methode wird die Bereitstellung statischer Dateien aus dem Webstammpfad ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="74787-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="74787-198">Das Standard-Webstammverzeichnis ist *wwwroot*, kann jedoch angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="74787-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="74787-199">Wie in `Configure` der Methode der `Startup` eShop-Klasse enthalten:</span><span class="sxs-lookup"><span data-stu-id="74787-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="74787-200">Das eShop-Projekt ermöglicht den statischen Einfachen Dateizugriff.</span><span class="sxs-lookup"><span data-stu-id="74787-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="74787-201">Für den statischen Dateizugriff stehen viele Anpassungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="74787-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="74787-202">Informationen zum Aktivieren von Standarddateien oder einem Dateibrowser finden Sie [unter Statische Dateien in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span><span class="sxs-lookup"><span data-stu-id="74787-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="74787-203">Migrieren von Laufzeitbündelungs- und Minifikationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="74787-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="74787-204">Bündelung und Minimierung sind Techniken zur Leistungsoptimierung, um die Anzahl und Größe von Serveranforderungen zum Abrufen bestimmter Dateitypen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="74787-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="74787-205">JavaScript und CSS werden häufig in irgendeiner Form gebündelt oder minifikiert, bevor sie an den Client gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="74787-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="74787-206">In ASP.NET Web Forms werden diese Optimierungen zur Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="74787-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="74787-207">Die Optimierungskonventionen sind eine *App_Start/BundleConfig.cs-Datei* definiert.</span><span class="sxs-lookup"><span data-stu-id="74787-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="74787-208">In ASP.NET Core wird ein deklarativerer Ansatz gewählt.</span><span class="sxs-lookup"><span data-stu-id="74787-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="74787-209">Eine Datei listet die zu minimierenden Dateien zusammen mit bestimmten Minifizierungseinstellungen auf.</span><span class="sxs-lookup"><span data-stu-id="74787-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="74787-210">Weitere Informationen zur Bündelung und Minierung finden Sie unter [Bündeln und Minimieren statischer Assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="74787-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="74787-211">MIGrieren von ASPX-Seiten</span><span class="sxs-lookup"><span data-stu-id="74787-211">Migrate ASPX pages</span></span>

<span data-ttu-id="74787-212">Eine Seite in einer Web Forms-App ist eine Datei mit der *Aspx-Erweiterung.*</span><span class="sxs-lookup"><span data-stu-id="74787-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="74787-213">Eine Web Forms-Seite kann häufig einer Komponente in Blazor zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="74787-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="74787-214">Eine Blazor-Komponente wird in einer Datei mit der *Erweiterung .razor* erstellt.</span><span class="sxs-lookup"><span data-stu-id="74787-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="74787-215">Für das eShop-Projekt werden fünf Seiten in eine Razor-Seite konvertiert.</span><span class="sxs-lookup"><span data-stu-id="74787-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="74787-216">Die Detailansicht besteht beispielsweise aus drei Dateien im Web Forms-Projekt: *Details.aspx*, *Details.aspx.cs*und *Details.aspx.designer.cs*.</span><span class="sxs-lookup"><span data-stu-id="74787-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="74787-217">Bei der Konvertierung in Blazor werden Code-Behind und Markup in *Details.razor*kombiniert.</span><span class="sxs-lookup"><span data-stu-id="74787-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="74787-218">Die Razor-Kompilierung (entspricht dem in *.designer.cs-Dateien)* wird im *obj-Verzeichnis* gespeichert und ist im **Projektmappen-Explorer**standardmäßig nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="74787-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="74787-219">Die Web Forms-Seite besteht aus folgendem Markup:</span><span class="sxs-lookup"><span data-stu-id="74787-219">The Web Forms page consists of the following markup:</span></span>

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

<span data-ttu-id="74787-220">Das Codebehind des vorherigen Markups enthält den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="74787-220">The preceding markup's code-behind includes the following code:</span></span>

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

<span data-ttu-id="74787-221">Bei der Konvertierung in Blazor wird die Web Forms-Seite in den folgenden Code übersetzt:</span><span class="sxs-lookup"><span data-stu-id="74787-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

<span data-ttu-id="74787-222">Beachten Sie, dass sich der Code und das Markup in derselben Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="74787-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="74787-223">Alle erforderlichen Dienste werden `@inject` mit dem Attribut zugänglich gemacht.</span><span class="sxs-lookup"><span data-stu-id="74787-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="74787-224">Gemäß `@page` der Direktive kann diese `Catalog/Details/{id}` Seite an der Route aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="74787-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="74787-225">Der Wert des Platzhalters `{id}` der Route wurde auf eine ganze Zahl beschränkt.</span><span class="sxs-lookup"><span data-stu-id="74787-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="74787-226">Wie im [Routingabschnitt](pages-routing-layouts.md) beschrieben, gibt eine Razor-Komponente im Gegensatz zu Web Forms ihre Route und alle enthaltenen Parameter explizit an.</span><span class="sxs-lookup"><span data-stu-id="74787-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="74787-227">Viele Web Forms-Steuerelemente haben möglicherweise keine genauen Gegenstücke in Blazor.</span><span class="sxs-lookup"><span data-stu-id="74787-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="74787-228">Es gibt oft einen entsprechenden HTML-Ausschnitt, der dem gleichen Zweck dient.</span><span class="sxs-lookup"><span data-stu-id="74787-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="74787-229">Das `<asp:Label />` Steuerelement kann z. B. `<label>` durch ein HTML-Element ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="74787-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="74787-230">Modellvalidierung in Blazor</span><span class="sxs-lookup"><span data-stu-id="74787-230">Model validation in Blazor</span></span>

<span data-ttu-id="74787-231">Wenn Ihr Web Forms-Code eine Validierung enthält, können Sie vieles von dem, was Sie haben, mit wenig bis gar keinen Änderungen übertragen.</span><span class="sxs-lookup"><span data-stu-id="74787-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="74787-232">Ein Vorteil der Ausführung in Blazor besteht darin, dass dieselbe Validierungslogik ausgeführt werden kann, ohne dass benutzerdefiniertes JavaScript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="74787-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="74787-233">Datenanmerkungen ermöglichen eine einfache Modellvalidierung.</span><span class="sxs-lookup"><span data-stu-id="74787-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="74787-234">Beispielsweise verfügt die Seite *Create.aspx* über ein Dateneingabeformular mit Validierung.</span><span class="sxs-lookup"><span data-stu-id="74787-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="74787-235">Ein Beispielausschnitt würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="74787-235">An example snippet would look like this:</span></span>

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

<span data-ttu-id="74787-236">In Blazor wird das entsprechende Markup in einer *Create.razor-Datei* bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="74787-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

<span data-ttu-id="74787-237">Der `EditForm` Kontext umfasst Validierungsunterstützung und kann um Eingabe umbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="74787-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="74787-238">Datenanmerkungen sind eine gängige Möglichkeit zum Hinzufügen von Validierungen.</span><span class="sxs-lookup"><span data-stu-id="74787-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="74787-239">Eine solche Validierungsunterstützung `DataAnnotationsValidator` kann über die Komponente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="74787-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="74787-240">Weitere Informationen zu diesem Mechanismus finden Sie [unter ASP.NET Core Blazor Forms and Validation](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="74787-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="74787-241">Migrieren integrierter Web Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="74787-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="74787-242">*Dieser Inhalt wird bald kommen.*</span><span class="sxs-lookup"><span data-stu-id="74787-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="74787-243">Migrating Configuration (Migrieren der Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="74787-243">Migrate configuration</span></span>

<span data-ttu-id="74787-244">In einem Web Forms-Projekt werden Konfigurationsdaten am häufigsten in der *Datei web.config* gespeichert.</span><span class="sxs-lookup"><span data-stu-id="74787-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="74787-245">Auf die Konfigurationsdaten `ConfigurationManager`wird mit zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="74787-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="74787-246">Häufig waren Dienste zum Analysieren von Objekten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="74787-246">Services were often required to parse objects.</span></span> <span data-ttu-id="74787-247">Mit .NET Framework 4.7.2 wurde der Konfiguration `ConfigurationBuilders`über die Komposität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="74787-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="74787-248">Diese Builder ermöglichten Entwicklern das Hinzufügen verschiedener Quellen für die Konfiguration, die dann zur Laufzeit zusammengesetzt wurden, um die erforderlichen Werte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="74787-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="74787-249">ASP.NET Core hat ein flexibles Konfigurationssystem eingeführt, mit dem Sie die Konfigurationsquelle oder die von Ihrer App und Bereitstellung verwendeten Quellen definieren können.</span><span class="sxs-lookup"><span data-stu-id="74787-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="74787-250">Die `ConfigurationBuilder` Infrastruktur, die Sie möglicherweise in Ihrer Web Forms-App verwenden, wurde nach den Konzepten modelliert, die im ASP.NET Core-Konfigurationssystem verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="74787-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="74787-251">Der folgende Ausschnitt veranschaulicht, wie das Web Forms eShop-Projekt *web.config* zum Speichern von Konfigurationswerten verwendet:</span><span class="sxs-lookup"><span data-stu-id="74787-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

<span data-ttu-id="74787-252">Es ist üblich, dass Geheimnisse, z. B. Datenbankverbindungszeichenfolgen, in der *web.config*gespeichert werden. Die Geheimnisse werden unweigerlich an unsicheren Orten, z. B. der Quellcodeverwaltung, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="74787-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="74787-253">Mit Blazor auf ASP.NET Core wird die vorhergehende XML-basierte Konfiguration durch die folgende JSON ersetzt:</span><span class="sxs-lookup"><span data-stu-id="74787-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="74787-254">JSON ist das Standardkonfigurationsformat. ASP.NET Core unterstützt jedoch viele andere Formate, einschließlich XML.</span><span class="sxs-lookup"><span data-stu-id="74787-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="74787-255">Es gibt auch mehrere von der Community unterstützte Formate.</span><span class="sxs-lookup"><span data-stu-id="74787-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="74787-256">Der Konstruktor in der Klasse `Startup` des `IConfiguration` Blazor-Projekts akzeptiert eine Instanz über eine DI-Technik, die als Konstruktorinjektion bekannt ist:</span><span class="sxs-lookup"><span data-stu-id="74787-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

<span data-ttu-id="74787-257">Standardmäßig sind Umgebungsvariablen, JSON-Dateien (*appsettings.json* und *appsettings. Die Optionen "Environment.json*" und die Befehlszeilenoptionen werden als gültige Konfigurationsquellen im Konfigurationsobjekt registriert.</span><span class="sxs-lookup"><span data-stu-id="74787-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="74787-258">Auf die Konfigurationsquellen `Configuration[key]`kann über zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="74787-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="74787-259">Eine erweiterte Technik besteht darin, die Konfigurationsdaten mithilfe des Optionsmusters an Objekte zu binden.</span><span class="sxs-lookup"><span data-stu-id="74787-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="74787-260">Weitere Informationen zur Konfiguration und zum Optionsmuster finden Sie unter [Konfiguration in ASP.NET Core-](/aspnet/core/fundamentals/configuration/) und [Optionsmuster in ASP.NET Core](/aspnet/core/fundamentals/configuration/options).</span><span class="sxs-lookup"><span data-stu-id="74787-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="74787-261">Migrieren des Datenzugriffs</span><span class="sxs-lookup"><span data-stu-id="74787-261">Migrate data access</span></span>

<span data-ttu-id="74787-262">Der Datenzugriff ist ein wichtiger Aspekt jeder App.</span><span class="sxs-lookup"><span data-stu-id="74787-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="74787-263">Das eShop-Projekt speichert Kataloginformationen in einer Datenbank und ruft die Daten mit Entity Framework (EF) 6 ab.</span><span class="sxs-lookup"><span data-stu-id="74787-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="74787-264">Da EF 6 in .NET Core 3.0 unterstützt wird, kann das Projekt es weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="74787-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="74787-265">Folgende EF-bezogene Änderungen waren für eShop notwendig:</span><span class="sxs-lookup"><span data-stu-id="74787-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="74787-266">In .NET Framework `DbContext` akzeptiert das Objekt eine Zeichenfolge des Formulars *name=ConnectionString* und verwendet die Verbindungszeichenfolge von `ConfigurationManager.AppSettings[ConnectionString]` zum Verbinden.</span><span class="sxs-lookup"><span data-stu-id="74787-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="74787-267">In .NET Core wird dies nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="74787-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="74787-268">Die Verbindungszeichenfolge muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="74787-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="74787-269">Auf die Datenbank wurde synchron zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="74787-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="74787-270">Obwohl dies funktioniert, kann die Skalierbarkeit leiden.</span><span class="sxs-lookup"><span data-stu-id="74787-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="74787-271">Diese Logik sollte in ein asynchrones Muster verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="74787-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="74787-272">Obwohl es nicht die gleiche systemeigene Unterstützung für die Datasetbindung gibt, bietet Blazor Flexibilität und Leistung mit seiner C-Unterstützung auf einer Razor-Seite.</span><span class="sxs-lookup"><span data-stu-id="74787-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="74787-273">Sie können z. B. Berechnungen durchführen und das Ergebnis anzeigen.</span><span class="sxs-lookup"><span data-stu-id="74787-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="74787-274">Weitere Informationen zu Datenmustern in Blazor finden Sie im Kapitel [Datenzugriff.](data.md)</span><span class="sxs-lookup"><span data-stu-id="74787-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="74787-275">Architektonische Veränderungen</span><span class="sxs-lookup"><span data-stu-id="74787-275">Architectural changes</span></span>

<span data-ttu-id="74787-276">Schließlich gibt es einige wichtige architektonische Unterschiede zu berücksichtigen, wenn sie nach Blazor wandern.</span><span class="sxs-lookup"><span data-stu-id="74787-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="74787-277">Viele dieser Änderungen gelten für alle Änderungen, die auf .NET Core oder ASP.NET Core basieren.</span><span class="sxs-lookup"><span data-stu-id="74787-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="74787-278">Da Blazor auf .NET Core basiert, gibt es Überlegungen, die Unterstützung für .NET Core sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="74787-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="74787-279">Zu den wichtigsten Änderungen gehört das Entfernen der folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="74787-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="74787-280">Mehrere AppDomains</span><span class="sxs-lookup"><span data-stu-id="74787-280">Multiple AppDomains</span></span>
- <span data-ttu-id="74787-281">Remoting</span><span class="sxs-lookup"><span data-stu-id="74787-281">Remoting</span></span>
- <span data-ttu-id="74787-282">Codezugriffssicherheit (Code Access Security, CAS)</span><span class="sxs-lookup"><span data-stu-id="74787-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="74787-283">Sicherheitstransparenz</span><span class="sxs-lookup"><span data-stu-id="74787-283">Security Transparency</span></span>

<span data-ttu-id="74787-284">Weitere Informationen zu Techniken zum Identifizieren notwendiger Änderungen zur Unterstützung der Ausführung von .NET Core finden Sie unter [Portieren des Codes von .NET Framework auf .NET Core](/dotnet/core/porting).</span><span class="sxs-lookup"><span data-stu-id="74787-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="74787-285">ASP.NET Core ist eine neu gestaltete Version von ASP.NET und hat einige Änderungen, die zunächst nicht offensichtlich erscheinen.</span><span class="sxs-lookup"><span data-stu-id="74787-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="74787-286">Die wichtigsten Änderungen sind:</span><span class="sxs-lookup"><span data-stu-id="74787-286">The main changes are:</span></span>

- <span data-ttu-id="74787-287">Kein Synchronisierungskontext, d. `HttpContext.Current`h., es gibt keine , `Thread.CurrentPrincipal`oder andere statische Accessoren</span><span class="sxs-lookup"><span data-stu-id="74787-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="74787-288">Kein Schattenkopieren</span><span class="sxs-lookup"><span data-stu-id="74787-288">No shadow copying</span></span>
- <span data-ttu-id="74787-289">Keine Anforderungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="74787-289">No request queue</span></span>

<span data-ttu-id="74787-290">Viele Vorgänge in ASP.NET Core sind asynchron, was eine einfachere Auslagerung von E/A-gebundenen Aufgaben ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="74787-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="74787-291">Es ist wichtig, niemals `Task.Wait()` zu `Task.GetResult()`blockieren, indem Sie oder verwenden, was Threadpoolressourcen schnell ausschöpfen kann.</span><span class="sxs-lookup"><span data-stu-id="74787-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="74787-292">Migrationsabschluss</span><span class="sxs-lookup"><span data-stu-id="74787-292">Migration conclusion</span></span>

<span data-ttu-id="74787-293">An diesem Punkt haben Sie viele Beispiele dafür gesehen, was es braucht, um ein Web Forms-Projekt nach Blazor zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="74787-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="74787-294">Ein vollständiges Beispiel finden Sie im [eShopOnBlazor-Projekt.](https://github.com/dotnet-architecture/eShopOnBlazor)</span><span class="sxs-lookup"><span data-stu-id="74787-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="74787-295">Zurück</span><span class="sxs-lookup"><span data-stu-id="74787-295">Previous</span></span>](security-authentication-authorization.md)
