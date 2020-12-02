---
title: Migrieren von ASP.net Web Forms zu Blazor
description: Erfahren Sie, wie Sie eine vorhandene ASP.net-Web Forms-APP zu migrieren Blazor .
author: twsouthwick
ms.author: tasou
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: 893b6f851681ec540629fe160749b2622b6d5440
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509831"
---
# <a name="migrate-from-aspnet-web-forms-to-no-locblazor"></a><span data-ttu-id="f2fec-103">Migrieren von ASP.net Web Forms zu Blazor</span><span class="sxs-lookup"><span data-stu-id="f2fec-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

<span data-ttu-id="f2fec-104">Das Migrieren einer Codebasis von ASP.net Web Forms zu Blazor ist eine zeitaufwändige Aufgabe, für die eine Planung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f2fec-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="f2fec-105">In diesem Kapitel wird der Prozess beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f2fec-105">This chapter outlines the process.</span></span> <span data-ttu-id="f2fec-106">Eine Möglichkeit, den Übergang zu vereinfachen, besteht darin sicherzustellen, dass die APP einer *N-Tier-* Architektur entspricht, bei der das App-Modell (in diesem Fall Web Forms) von der Geschäftslogik getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="f2fec-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="f2fec-107">Diese logische Trennung von Ebenen macht es klar, was zu .net Core und verschoben werden muss Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="f2fec-108">In diesem Beispiel wird die auf [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) verfügbare eShop-App verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2fec-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="f2fec-109">der eShop ist ein Katalog Dienst, der CRUD-Funktionen per Formular Eintrag und Validierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="f2fec-110">Warum sollte eine funktionierende APP zu migriert werden Blazor ?</span><span class="sxs-lookup"><span data-stu-id="f2fec-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="f2fec-111">Oft ist es nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f2fec-111">Many times, there's no need.</span></span> <span data-ttu-id="f2fec-112">ASP.net Web Forms wird noch viele Jahre lang unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="f2fec-113">Viele der Funktionen, die Blazor bereitstellt, werden jedoch nur für eine migrierte App unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="f2fec-114">Zu diesen Features gehören:</span><span class="sxs-lookup"><span data-stu-id="f2fec-114">Such features include:</span></span>

- <span data-ttu-id="f2fec-115">Leistungsverbesserungen im Framework, z. b. `Span<T>`</span><span class="sxs-lookup"><span data-stu-id="f2fec-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="f2fec-116">Möglichkeit zum Ausführen als WebAssembly</span><span class="sxs-lookup"><span data-stu-id="f2fec-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="f2fec-117">Plattformübergreifende Unterstützung für Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="f2fec-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="f2fec-118">Lokale App-Bereitstellung oder Bereitstellung von freigegebenen Frameworks ohne Auswirkung auf andere apps</span><span class="sxs-lookup"><span data-stu-id="f2fec-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="f2fec-119">Wenn diese oder andere neue Features aussagekräftig genug sind, kann es beim Migrieren der APP zu einem Wert kommen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="f2fec-120">Die Migration kann verschiedene Formen annehmen. Dabei kann es sich um die gesamte APP oder nur bestimmte Endpunkte handeln, für die die Änderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="f2fec-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="f2fec-121">Die Entscheidung für die Migration basiert letztendlich auf den geschäftlichen Problemen, die vom Entwickler gelöst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="f2fec-122">Server seitiges und Client seitiges Hosting</span><span class="sxs-lookup"><span data-stu-id="f2fec-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="f2fec-123">Wie im Kapitel [Hostingmodelle](hosting-models.md) beschrieben, kann eine- Blazor App auf zwei verschiedene Arten gehostet werden: Server-und Client seitig.</span><span class="sxs-lookup"><span data-stu-id="f2fec-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="f2fec-124">Das serverseitige Modell verwendet ASP.net Core signalr-Verbindungen, um die DOM-Aktualisierungen bei der Ausführung von tatsächlichem Code auf dem Server zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f2fec-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="f2fec-125">Das Client seitige Modell wird wie WebAssembly in einem Browser ausgeführt und erfordert keine Serververbindungen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="f2fec-126">Es gibt eine Reihe von unterschieden, die sich darauf auswirken können, was für eine bestimmte App am besten geeignet ist:</span><span class="sxs-lookup"><span data-stu-id="f2fec-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="f2fec-127">Das Ausführen WebAssembly von unterstützt nicht alle Features (z. b. Threading) zum aktuellen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-127">Running as WebAssembly doesn't support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="f2fec-128">Die Kommunikation zwischen dem Client und dem Server kann zu Latenzproblemen im serverseitigen Modus führen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="f2fec-129">Der Zugriff auf Datenbanken und interne oder geschützte Dienste erfordert einen separaten Dienst mit Client seitigem Hosting.</span><span class="sxs-lookup"><span data-stu-id="f2fec-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="f2fec-130">Zum Zeitpunkt des Schreibens ähnelt das serverseitige Modell Web Forms.</span><span class="sxs-lookup"><span data-stu-id="f2fec-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="f2fec-131">In diesem Kapitel liegt der Schwerpunkt auf dem serverseitigen Hostingmodell, da es in der Produktion bereit ist.</span><span class="sxs-lookup"><span data-stu-id="f2fec-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="f2fec-132">Erstellen eines neuen Projekts</span><span class="sxs-lookup"><span data-stu-id="f2fec-132">Create a new project</span></span>

<span data-ttu-id="f2fec-133">Dieser erste Migrationsschritt besteht darin, ein neues Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="f2fec-134">Dieser Projekttyp basiert auf den SDK-Stil Projekten von .net und vereinfacht einen Großteil der Bausteine, die in früheren Projekt Formaten verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-134">This project type is based on the SDK style projects of .NET and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="f2fec-135">Weitere Details finden Sie im Kapitel zur [Projektstruktur](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f2fec-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="f2fec-136">Nachdem das Projekt erstellt wurde, installieren Sie die Bibliotheken, die im vorherigen Projekt verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="f2fec-137">In älteren Web Forms Projekten haben Sie möglicherweise die Datei *packages.config* verwendet, um die benötigten nuget-Pakete aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="f2fec-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="f2fec-138">Im neuen Projekt im SDK-Stil wurde *packages.config* durch `<PackageReference>` Elemente in der Projektdatei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="f2fec-139">Ein Vorteil dieses Ansatzes besteht darin, dass alle Abhängigkeiten transitiv installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="f2fec-140">Sie Listen nur die Abhängigkeiten auf oberster Ebene auf, für die Sie sich interessieren.</span><span class="sxs-lookup"><span data-stu-id="f2fec-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="f2fec-141">Viele der von Ihnen verwendeten Abhängigkeiten sind für .net verfügbar, einschließlich Entity Framework 6 und log4net.</span><span class="sxs-lookup"><span data-stu-id="f2fec-141">Many of the dependencies you're using are available for .NET, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="f2fec-142">Wenn keine .net-oder .NET Standard Version verfügbar ist, kann die .NET Framework Version häufig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-142">If there's no .NET or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="f2fec-143">Ihre Erfahrungen können hiervon abweichen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-143">Your mileage may vary.</span></span> <span data-ttu-id="f2fec-144">Jede verwendete API, die in .net nicht verfügbar ist, verursacht einen Laufzeitfehler.</span><span class="sxs-lookup"><span data-stu-id="f2fec-144">Any API used that isn't available in .NET causes a runtime error.</span></span> <span data-ttu-id="f2fec-145">Visual Studio benachrichtigt Sie über solche Pakete.</span><span class="sxs-lookup"><span data-stu-id="f2fec-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="f2fec-146">Ein gelbes Symbol wird im Knoten **Verweise** des Projekts in **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="f2fec-147">Im Blazor -basierten eShop-Projekt können Sie die installierten Pakete sehen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="f2fec-148">Zuvor hat die *packages.config* -Datei alle im Projekt verwendeten Pakete aufgelistet, was zu einer Datei mit einer Länge von fast 50 Zeilen führte.</span><span class="sxs-lookup"><span data-stu-id="f2fec-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="f2fec-149">Ein Ausschnitt von *packages.config* ist:</span><span class="sxs-lookup"><span data-stu-id="f2fec-149">A snippet of *packages.config* is:</span></span>

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

<span data-ttu-id="f2fec-150">Das- `<packages>` Element enthält alle notwendigen Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="f2fec-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="f2fec-151">Es ist schwierig festzustellen, welche dieser Pakete eingeschlossen werden, da Sie Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="f2fec-152">Einige `<package>` Elemente werden einfach aufgelistet, um die Anforderungen der benötigten Abhängigkeiten zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="f2fec-153">Im Blazor Projekt werden die Abhängigkeiten aufgelistet, die innerhalb eines `<ItemGroup>` Elements in der Projektdatei erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="f2fec-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.4.4" />
    <PackageReference Include="log4net" Version="2.0.12" />
    <PackageReference Include="Microsoft.Extensions.Logging.Log4Net.AspNetCore" Version="2.2.12" />
</ItemGroup>
```

<span data-ttu-id="f2fec-154">Ein nuget-Paket, das die Lebensdauer von Web Forms Entwicklern vereinfacht, ist das [Windows-Kompatibilitätspaket](../../core/porting/windows-compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f2fec-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="f2fec-155">Obwohl .net plattformübergreifend ist, stehen einige Funktionen nur unter Windows zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-155">Although .NET is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="f2fec-156">Windows-spezifische Funktionen werden durch die Installation des Kompatibilitätspakets zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="f2fec-157">Beispiele für solche Features sind die Registrierungs-, WMI-und Verzeichnisdienste.</span><span class="sxs-lookup"><span data-stu-id="f2fec-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="f2fec-158">Das Paket fügt ungefähr 20.000 APIs hinzu und aktiviert viele Dienste, mit denen Sie möglicherweise bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="f2fec-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="f2fec-159">Das Projekt "eShop" erfordert nicht das Kompatibilitätspaket. Wenn in Ihren Projekten jedoch Windows-spezifische Features verwendet werden, vereinfacht das Paket den Migrations Aufwand.</span><span class="sxs-lookup"><span data-stu-id="f2fec-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="f2fec-160">Startprozess aktivieren</span><span class="sxs-lookup"><span data-stu-id="f2fec-160">Enable startup process</span></span>

<span data-ttu-id="f2fec-161">Der Startvorgang für Blazor hat sich von Web Forms geändert und folgt einem ähnlichen Setup für andere ASP.net Core Dienste.</span><span class="sxs-lookup"><span data-stu-id="f2fec-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="f2fec-162">Wenn serverseitig gehostet werden, Blazor werden Komponenten als Teil einer normalen ASP.net Core-app ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="f2fec-163">Wenn im Browser mit gehostet WebAssembly wird, Blazor verwenden Komponenten ein ähnliches Hostingmodell.</span><span class="sxs-lookup"><span data-stu-id="f2fec-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="f2fec-164">Der Unterschied besteht darin, dass die Komponenten als separater Dienst von einem beliebigen Back-End-Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="f2fec-165">In jedem Fall ist der Start ähnlich.</span><span class="sxs-lookup"><span data-stu-id="f2fec-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="f2fec-166">Die Datei *Global.asax.cs* ist die Standard Startseite für Web Forms Projekte.</span><span class="sxs-lookup"><span data-stu-id="f2fec-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="f2fec-167">Im Projekt "eShop" konfiguriert diese Datei den "Inversion of Control" (IOC)-Container und behandelt die verschiedenen Lebenszyklus Ereignisse der APP oder Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="f2fec-168">Einige dieser Ereignisse werden mit Middleware behandelt (z. b `Application_BeginRequest` .).</span><span class="sxs-lookup"><span data-stu-id="f2fec-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="f2fec-169">Bei anderen Ereignissen müssen bestimmte Dienste über die Abhängigkeitsinjektion (di) überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="f2fec-170">Beispielsweise enthält die Datei *Global.asax.cs* für den eShop den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f2fec-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

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
    /// https://autofaccn.readthedocs.io/en/latest/integration/webforms.html
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

<span data-ttu-id="f2fec-171">Die vorherige Datei wird zur- `Startup` Klasse auf Serverseite Blazor :</span><span class="sxs-lookup"><span data-stu-id="f2fec-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

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

<span data-ttu-id="f2fec-172">Eine bedeutende Änderung, die Sie von Web Forms bemerken, ist die Bedeutung von di.</span><span class="sxs-lookup"><span data-stu-id="f2fec-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="f2fec-173">DI ist ein Leitfaden für das ASP.net Core Design.</span><span class="sxs-lookup"><span data-stu-id="f2fec-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="f2fec-174">Es unterstützt die Anpassung fast aller Aspekte des ASP.net Core Frameworks.</span><span class="sxs-lookup"><span data-stu-id="f2fec-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="f2fec-175">Es gibt sogar einen integrierten Dienstanbieter, der in vielen Szenarios verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2fec-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="f2fec-176">Wenn eine größere Anpassung erforderlich ist, kann Sie von vielen Community-Projekten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-176">If more customization is required, it can be supported by many community projects.</span></span> <span data-ttu-id="f2fec-177">Beispielsweise können Sie die Investition ihrer Drittanbieter-di-Bibliothek weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="f2fec-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="f2fec-178">In der ursprünglichen eShop-App gibt es eine Konfiguration für die Sitzungsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="f2fec-179">Da serverseitig Blazor ASP.net Core signalr für die Kommunikation verwendet, wird der Sitzungszustand nicht unterstützt, da die Verbindungen unabhängig von einem HTTP-Kontext auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f2fec-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, the session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="f2fec-180">Eine APP, die den Sitzungszustand verwendet, erfordert eine Neuentwicklung, bevor Sie als-app ausgeführt wird Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-180">An app that uses the session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="f2fec-181">Weitere Informationen zum Starten der App finden Sie unter [App Startup](app-startup.md).</span><span class="sxs-lookup"><span data-stu-id="f2fec-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="f2fec-182">Migrieren von HTTP-Modulen und-Handlern zu Middleware</span><span class="sxs-lookup"><span data-stu-id="f2fec-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="f2fec-183">HTTP-Module und-Handler sind gängige Muster in Web Forms, um die HTTP-Anforderungs Pipeline zu steuern.</span><span class="sxs-lookup"><span data-stu-id="f2fec-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="f2fec-184">Klassen, die `IHttpModule` oder implementieren `IHttpHandler` und eingehende Anforderungen verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="f2fec-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="f2fec-185">Web Forms Konfigurieren von Modulen und Handlern in der *web.config* Datei.</span><span class="sxs-lookup"><span data-stu-id="f2fec-185">Web Forms configure modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="f2fec-186">Web Forms basiert ebenfalls stark auf der Ereignis Behandlung für den App-Lebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="f2fec-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="f2fec-187">ASP.net Core verwendet stattdessen Middleware.</span><span class="sxs-lookup"><span data-stu-id="f2fec-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="f2fec-188">Die Middleware ist in der- `Configure` Methode der- `Startup` Klasse registriert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="f2fec-189">Die Ausführungsreihenfolge der Middleware wird durch die Registrierung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="f2fec-190">Im Abschnitt [enable Startup Process](#enable-startup-process) wurde ein Lifecycle-Ereignis durch Web Forms als-Methode ausgelöst `Application_BeginRequest` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="f2fec-191">Dieses Ereignis ist in ASP.net Core nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2fec-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="f2fec-192">Eine Möglichkeit, dieses Verhalten zu erreichen, besteht in der Implementierung von Middleware, wie im Beispiel für die *Startup.cs* -Datei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="f2fec-193">Diese Middleware übernimmt dieselbe Logik und überträgt dann die Steuerung an den nächsten Handler in der middlewarepipeline.</span><span class="sxs-lookup"><span data-stu-id="f2fec-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="f2fec-194">Weitere Informationen zum Migrieren von Modulen und Handlern finden [Sie unter Migrieren von HTTP-Handlern und Modulen zu ASP.net Core Middleware](/aspnet/core/migration/http-modules).</span><span class="sxs-lookup"><span data-stu-id="f2fec-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="f2fec-195">Migrieren statischer Dateien</span><span class="sxs-lookup"><span data-stu-id="f2fec-195">Migrate static files</span></span>

<span data-ttu-id="f2fec-196">Zum Bereitstellen statischer Dateien (z. b. html, CSS, Bilder und JavaScript) müssen die Dateien von der Middleware verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="f2fec-197">Durch den Aufruf der- `UseStaticFiles` Methode wird die Funktion statischer Dateien aus dem webstammpfad ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f2fec-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="f2fec-198">Das Standardweb Stammverzeichnis ist " *wwwroot*", kann jedoch angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="f2fec-199">Wie in der `Configure` -Methode der-Klasse von eShop enthalten `Startup` :</span><span class="sxs-lookup"><span data-stu-id="f2fec-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="f2fec-200">Das Projekt "eShop" ermöglicht grundlegenden statischen Dateizugriff.</span><span class="sxs-lookup"><span data-stu-id="f2fec-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="f2fec-201">Für den Zugriff auf statische Dateien sind viele Anpassungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2fec-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="f2fec-202">Informationen zum Aktivieren von Standard Dateien oder eines Datei Browsers finden Sie unter [statische Dateien in ASP.net Core](/aspnet/core/fundamentals/static-files).</span><span class="sxs-lookup"><span data-stu-id="f2fec-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="f2fec-203">Migrieren von Lauf Zeit bündeln und Minimieren der Einrichtung</span><span class="sxs-lookup"><span data-stu-id="f2fec-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="f2fec-204">Bündelung und Minimierung sind Techniken zur Leistungsoptimierung, mit denen die Anzahl und Größe von Serveranforderungen zum Abrufen bestimmter Dateitypen reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="f2fec-205">JavaScript und CSS unterliegen häufig einer Form der Bündelung oder Minimierung, bevor Sie an den Client gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="f2fec-206">In ASP.net-Web Forms werden diese Optimierungen zur Laufzeit behandelt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="f2fec-207">Die Optimierungs Konventionen sind *App_Start/bundleconfig.cs* -Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="f2fec-208">In ASP.net Core wird ein deklarativer Ansatz gewählt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="f2fec-209">In einer Datei werden die zu minigenden Dateien zusammen mit bestimmten minieringeinstellungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f2fec-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="f2fec-210">Weitere Informationen zur Bündelung und Minimierung finden Sie unter [Bundle and minimieren static Assets in ASP.net Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="f2fec-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="f2fec-211">Migrieren von ASPX-Seiten</span><span class="sxs-lookup"><span data-stu-id="f2fec-211">Migrate ASPX pages</span></span>

<span data-ttu-id="f2fec-212">Eine Seite in einer Web Forms-APP ist eine Datei mit der Erweiterung " *. aspx* ".</span><span class="sxs-lookup"><span data-stu-id="f2fec-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="f2fec-213">Eine Web Forms Seite kann häufig einer Komponente in zugeordnet werden Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="f2fec-214">Eine Blazor Komponente wird in einer Datei mit der *Razor* -Erweiterung erstellt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="f2fec-215">Für das Projekt "eShop" werden fünf Seiten in eine Razor Page konvertiert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="f2fec-216">Die Detailansicht umfasst z. b. drei Dateien im Web Forms Projekt: *Details. aspx*, *Details.aspx.cs* und *Details.aspx.Designer.cs*.</span><span class="sxs-lookup"><span data-stu-id="f2fec-216">For example, the details view comprises three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="f2fec-217">Beim umstellen in Blazor werden Code-Behind und Markup in *Details. Razor* kombiniert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="f2fec-218">Die Razor-Kompilierung (entspricht der *Designer.cs* -Dateien) wird im *obj* -Verzeichnis gespeichert und ist nicht standardmäßig in **Projektmappen-Explorer** sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f2fec-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and isn't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="f2fec-219">Die Web Forms Seite besteht aus folgendem Markup:</span><span class="sxs-lookup"><span data-stu-id="f2fec-219">The Web Forms page consists of the following markup:</span></span>

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

<span data-ttu-id="f2fec-220">Der Code Behind des vorangehenden Markups enthält den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f2fec-220">The preceding markup's code-behind includes the following code:</span></span>

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

<span data-ttu-id="f2fec-221">Bei der Konvertierung in Blazor wird die Web Forms Seite in den folgenden Code übersetzt:</span><span class="sxs-lookup"><span data-stu-id="f2fec-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

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

<span data-ttu-id="f2fec-222">Beachten Sie, dass sich der Code und das Markup in derselben Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="f2fec-223">Alle erforderlichen Dienste werden mit dem-Attribut zugänglich gemacht `@inject` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="f2fec-224">Gemäß der- `@page` Direktive kann auf diese Seite über die `Catalog/Details/{id}` Route zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="f2fec-225">Der Wert des Platzhalters der Route wurde `{id}` auf einen Integer-Wert beschränkt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="f2fec-226">Wie im Abschnitt [Routing](pages-routing-layouts.md) beschrieben, gibt eine Razor-Komponente im Gegensatz zu Web Forms explizit Ihre Route und alle darin enthaltenen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="f2fec-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="f2fec-227">Viele Web Forms Steuerelemente weisen in möglicherweise keine exakten Entsprechungen auf Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="f2fec-228">Häufig gibt es einen äquivalenten HTML-Code Ausschnitt, der denselben Zweck erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="f2fec-229">Beispielsweise kann das `<asp:Label />` Steuerelement durch ein HTML-Element ersetzt werden `<label>` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-no-locblazor"></a><span data-ttu-id="f2fec-230">Modell Validierung in Blazor</span><span class="sxs-lookup"><span data-stu-id="f2fec-230">Model validation in Blazor</span></span>

<span data-ttu-id="f2fec-231">Wenn Ihr Web Forms Code die Validierung umfasst, können Sie viele der Funktionen übertragen, bei denen es sich um geringfügige Änderungen handelt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="f2fec-232">Ein Vorteil der Ausführung von in Blazor besteht darin, dass dieselbe Validierungs Logik ohne benutzerdefiniertes JavaScript ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2fec-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="f2fec-233">Daten Anmerkungen ermöglichen eine einfache Modell Validierung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="f2fec-234">Beispielsweise verfügt die Seite *Create. aspx* über ein Dateneingabe Formular mit Validierung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="f2fec-235">Ein Beispiel Ausschnitt sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f2fec-235">An example snippet would look like this:</span></span>

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

<span data-ttu-id="f2fec-236">In Blazor wird das entsprechende Markup in einer *Create. Razor* -Datei bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="f2fec-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

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

<span data-ttu-id="f2fec-237">Der `EditForm` Kontext umfasst Validierungs Unterstützung und kann um eine Eingabe umschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-237">The `EditForm` context includes validation support and can be wrapped around an input.</span></span> <span data-ttu-id="f2fec-238">Daten Anmerkungen sind eine gängige Methode zum Hinzufügen der Validierung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="f2fec-239">Diese Validierungs Unterstützung kann über die Komponente hinzugefügt werden `DataAnnotationsValidator` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="f2fec-240">Weitere Informationen zu diesem Mechanismus finden Sie unter [ASP.net Core Blazor Forms und Validierung](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="f2fec-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="f2fec-241">Migrating Configuration (Migrieren der Konfiguration)</span><span class="sxs-lookup"><span data-stu-id="f2fec-241">Migrate configuration</span></span>

<span data-ttu-id="f2fec-242">In einem Web Forms Projekt werden Konfigurationsdaten am häufigsten in der *web.config* -Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-242">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="f2fec-243">Der Zugriff auf die Konfigurationsdaten erfolgt mit `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-243">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="f2fec-244">Dienste waren häufig erforderlich, um Objekte zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="f2fec-244">Services were often required to parse objects.</span></span> <span data-ttu-id="f2fec-245">Mit .NET Framework 4.7.2 wurde die Zusammensetz barkeit der Konfiguration über hinzugefügt `ConfigurationBuilders` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-245">With .NET Framework 4.7.2, composability was added to the configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="f2fec-246">Diese Generatoren ermöglichten Entwicklern, verschiedene Quellen für die Konfiguration hinzuzufügen, die dann zur Laufzeit zum Abrufen der erforderlichen Werte erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f2fec-246">These builders allowed developers to add various sources for the configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="f2fec-247">ASP.net Core wurde ein flexibles Konfigurationssystem eingeführt, mit dem Sie die von Ihrer APP und Bereitstellung verwendete Konfigurations Quelle oder die Quell Quellen definieren können.</span><span class="sxs-lookup"><span data-stu-id="f2fec-247">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="f2fec-248">Die `ConfigurationBuilder` Infrastruktur, die Sie möglicherweise in Ihrer Web Forms-App verwenden, wurde nach den im ASP.net Core Konfigurationssystem verwendeten Konzepten modelliert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-248">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="f2fec-249">Der folgende Code Ausschnitt veranschaulicht, wie das Web Forms eShop-Projekt *web.config* verwendet, um Konfigurationswerte zu speichern:</span><span class="sxs-lookup"><span data-stu-id="f2fec-249">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

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

<span data-ttu-id="f2fec-250">Es ist üblich, dass geheime Schlüssel, wie z. b. Daten bankverbindungs Zeichenfolgen, in der *web.config* gespeichert werden. Die Geheimnisse werden unweigerlich an unsicheren Speicherorten wie der Quell Code Verwaltung persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-250">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="f2fec-251">Bei Blazor ASP.net Core wird die vorherige XML-basierte Konfiguration durch den folgenden JSON-Code ersetzt:</span><span class="sxs-lookup"><span data-stu-id="f2fec-251">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="f2fec-252">JSON ist das Standard Konfigurationsformat. ASP.net Core unterstützt jedoch viele andere Formate, einschließlich XML.</span><span class="sxs-lookup"><span data-stu-id="f2fec-252">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="f2fec-253">Es gibt auch mehrere von der Community unterstützte Formate.</span><span class="sxs-lookup"><span data-stu-id="f2fec-253">There are also several community-supported formats.</span></span>

<span data-ttu-id="f2fec-254">Der Konstruktor in der Blazor -Klasse des Projekts `Startup` akzeptiert eine `IConfiguration` Instanz über eine di-Technik, die als Konstruktorinjektion bezeichnet wird:</span><span class="sxs-lookup"><span data-stu-id="f2fec-254">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

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

<span data-ttu-id="f2fec-255">Standardmäßig werden Umgebungsvariablen, JSON-Dateien (*appsettings.jsauf* und *appSettings. { Environment}. JSON*) und Befehlszeilenoptionen werden als gültige Konfigurations Quellen im Konfigurationsobjekt registriert.</span><span class="sxs-lookup"><span data-stu-id="f2fec-255">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="f2fec-256">Auf die Konfigurations Quellen kann über zugegriffen werden `Configuration[key]` .</span><span class="sxs-lookup"><span data-stu-id="f2fec-256">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="f2fec-257">Eine fortgeschrittenere Methode besteht darin, die Konfigurationsdaten mithilfe des Options Musters an Objekte zu binden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-257">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="f2fec-258">Weitere Informationen zur Konfiguration und zum Options Muster finden Sie unter [Konfiguration in ASP.net Core](/aspnet/core/fundamentals/configuration/) und [options Muster in ASP.net Core](/aspnet/core/fundamentals/configuration/options)bzw.</span><span class="sxs-lookup"><span data-stu-id="f2fec-258">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="f2fec-259">Migrieren des Datenzugriffs</span><span class="sxs-lookup"><span data-stu-id="f2fec-259">Migrate data access</span></span>

<span data-ttu-id="f2fec-260">Der Datenzugriff ist ein wichtiger Aspekt jeder app.</span><span class="sxs-lookup"><span data-stu-id="f2fec-260">Data access is an important aspect of any app.</span></span> <span data-ttu-id="f2fec-261">Das Projekt "eShop" speichert Katalog Informationen in einer Datenbank und ruft die Daten mit Entity Framework (EF) 6 ab.</span><span class="sxs-lookup"><span data-stu-id="f2fec-261">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="f2fec-262">Da EF 6 in .net 5,0 unterstützt wird, kann es vom Projekt weiterhin verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-262">Since EF 6 is supported in .NET 5.0, the project can continue to use it.</span></span>

<span data-ttu-id="f2fec-263">Für den eShop waren die folgenden EF-bezogenen Änderungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="f2fec-263">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="f2fec-264">In .NET Framework akzeptiert das `DbContext` Objekt eine Zeichenfolge im Format *Name = ConnectionString* und verwendet die Verbindungs Zeichenfolge von `ConfigurationManager.AppSettings[ConnectionString]` , um eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-264">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="f2fec-265">In .net Core wird dies nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-265">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="f2fec-266">Die Verbindungs Zeichenfolge muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-266">The connection string must be supplied.</span></span>
- <span data-ttu-id="f2fec-267">Der Zugriff auf die Datenbank war synchron.</span><span class="sxs-lookup"><span data-stu-id="f2fec-267">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="f2fec-268">Obwohl dies funktioniert, kann die Skalierbarkeit beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-268">Though this works, scalability may suffer.</span></span> <span data-ttu-id="f2fec-269">Diese Logik sollte in ein asynchrones Muster verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-269">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="f2fec-270">Obwohl es nicht die gleiche systemeigene Unterstützung für DataSet-Bindungen gibt, Blazor bietet die c#-Unterstützung in einer Razor-Seite Flexibilität und Leistung.</span><span class="sxs-lookup"><span data-stu-id="f2fec-270">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="f2fec-271">Beispielsweise können Sie Berechnungen ausführen und das Ergebnis anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-271">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="f2fec-272">Weitere Informationen zu Datenmustern in finden Sie im Blazor Kapitel [Datenzugriff](data.md) .</span><span class="sxs-lookup"><span data-stu-id="f2fec-272">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="f2fec-273">Änderungen an der Architektur</span><span class="sxs-lookup"><span data-stu-id="f2fec-273">Architectural changes</span></span>

<span data-ttu-id="f2fec-274">Schließlich gibt es einige wichtige Unterschiede bei der Architektur, die bei der Migration zu berücksichtigt werden müssen Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-274">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="f2fec-275">Viele dieser Änderungen gelten für alle Elemente, die auf .net Core oder ASP.net Core basieren.</span><span class="sxs-lookup"><span data-stu-id="f2fec-275">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="f2fec-276">Da Blazor auf .net Core basiert, müssen bei der Unterstützung von .net Core unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f2fec-276">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="f2fec-277">Zu den wichtigsten Änderungen gehören das Entfernen der folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="f2fec-277">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="f2fec-278">Mehrere AppDomains</span><span class="sxs-lookup"><span data-stu-id="f2fec-278">Multiple AppDomains</span></span>
- <span data-ttu-id="f2fec-279">Remoting</span><span class="sxs-lookup"><span data-stu-id="f2fec-279">Remoting</span></span>
- <span data-ttu-id="f2fec-280">Codezugriffssicherheit (Code Access Security, CAS)</span><span class="sxs-lookup"><span data-stu-id="f2fec-280">Code Access Security (CAS)</span></span>
- <span data-ttu-id="f2fec-281">Sicherheitstransparenz</span><span class="sxs-lookup"><span data-stu-id="f2fec-281">Security Transparency</span></span>

<span data-ttu-id="f2fec-282">Weitere Informationen zu Techniken zur Identifizierung der erforderlichen Änderungen für die Unterstützung von unter .net Core finden [Sie unter Portieren von Code aus .NET Framework zu .net Core](../../core/porting/index.md).</span><span class="sxs-lookup"><span data-stu-id="f2fec-282">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](../../core/porting/index.md).</span></span>

<span data-ttu-id="f2fec-283">ASP.net Core ist eine neue Version von ASP.net und weist einige Änderungen auf, die möglicherweise nicht anfänglich offensichtlich erscheinen.</span><span class="sxs-lookup"><span data-stu-id="f2fec-283">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="f2fec-284">Die Haupt Änderungen lauten:</span><span class="sxs-lookup"><span data-stu-id="f2fec-284">The main changes are:</span></span>

- <span data-ttu-id="f2fec-285">Kein Synchronisierungs Kontext. Dies bedeutet, dass es keine `HttpContext.Current` , `Thread.CurrentPrincipal` oder andere statische Accessoren gibt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-285">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="f2fec-286">Keine Schatten Kopien</span><span class="sxs-lookup"><span data-stu-id="f2fec-286">No shadow copying</span></span>
- <span data-ttu-id="f2fec-287">Keine Anforderungs Warteschlange</span><span class="sxs-lookup"><span data-stu-id="f2fec-287">No request queue</span></span>

<span data-ttu-id="f2fec-288">Viele Vorgänge in ASP.net Core sind asynchron, wodurch das Laden von e/a-gebundenen Aufgaben vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="f2fec-288">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="f2fec-289">Es ist wichtig, niemals mit oder zu `Task.Wait()` blockieren `Task.GetResult()` , wodurch Thread Pool Ressourcen schnell aufgebraucht werden können.</span><span class="sxs-lookup"><span data-stu-id="f2fec-289">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="f2fec-290">Schlussfolgerung der Migration</span><span class="sxs-lookup"><span data-stu-id="f2fec-290">Migration conclusion</span></span>

<span data-ttu-id="f2fec-291">An diesem Punkt haben Sie viele Beispiele dafür gesehen, wie ein Web Forms Projekt in verschoben wird Blazor .</span><span class="sxs-lookup"><span data-stu-id="f2fec-291">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="f2fec-292">Ein vollständiges Beispiel finden Sie im [eshopon Blazor ](https://github.com/dotnet-architecture/eShopOnBlazor) -Projekt.</span><span class="sxs-lookup"><span data-stu-id="f2fec-292">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="f2fec-293">Zurück</span><span class="sxs-lookup"><span data-stu-id="f2fec-293">Previous</span></span>](security-authentication-authorization.md)
