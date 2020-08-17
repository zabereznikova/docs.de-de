---
title: App-Start
description: Erfahren Sie, wie Sie die Start Logik für Ihre APP definieren.
author: csharpfritz
ms.author: jefritz
ms.date: 02/25/2020
ms.openlocfilehash: ea2ea458011d8351a834aa12db02e5d2bac2dc65
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267697"
---
# <a name="app-startup"></a><span data-ttu-id="9ab57-103">App-Start</span><span class="sxs-lookup"><span data-stu-id="9ab57-103">App startup</span></span>

<span data-ttu-id="9ab57-104">Anwendungen, die für ASP.NET geschrieben werden, verfügen in der Regel über eine `global.asax.cs` Datei, in der das `Application_Start` Ereignis definiert ist, das steuert, welche Dienste für HTML-Rendering und .NET-Verarbeitung zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9ab57-104">Applications that are written for ASP.NET typically have a `global.asax.cs` file that defines the `Application_Start` event that controls which services are configured and made available for both HTML rendering and .NET processing.</span></span> <span data-ttu-id="9ab57-105">In diesem Kapitel wird erläutert, wie sich die Dinge bei ASP.net Core-und blazor-Server geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9ab57-105">This chapter looks at how things are slightly different with ASP.NET Core and Blazor Server.</span></span>

## <a name="application_start-and-web-forms"></a><span data-ttu-id="9ab57-106">Application_Start und Web Forms</span><span class="sxs-lookup"><span data-stu-id="9ab57-106">Application_Start and Web Forms</span></span>

<span data-ttu-id="9ab57-107">Die standardmäßige Web Forms- `Application_Start` Methode wurde im Laufe der Zeit über Jahre erweitert, um viele Konfigurationsaufgaben zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9ab57-107">The default web forms `Application_Start` method has grown in purpose over years to handle many configuration tasks.</span></span>  <span data-ttu-id="9ab57-108">Ein neues Web Forms-Projekt mit der Standardvorlage in Visual Studio 2019 enthält jetzt die folgende Konfigurations Logik:</span><span class="sxs-lookup"><span data-stu-id="9ab57-108">A fresh web forms project with the default template in Visual Studio 2019 now contains the following configuration logic:</span></span>

- <span data-ttu-id="9ab57-109">`RouteConfig` -Anwendungs-URL-Routing</span><span class="sxs-lookup"><span data-stu-id="9ab57-109">`RouteConfig` - Application URL routing</span></span>
- <span data-ttu-id="9ab57-110">`BundleConfig` -CSS und JavaScript-Bündelung und-Minimierung</span><span class="sxs-lookup"><span data-stu-id="9ab57-110">`BundleConfig` - CSS and JavaScript bundling and minification</span></span>

<span data-ttu-id="9ab57-111">Jede dieser einzelnen Dateien befindet sich im `App_Start` Ordner und wird nur einmal am Anfang der Anwendung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-111">Each of these individual files reside in the `App_Start` folder and run only once at the start of our application.</span></span>  <span data-ttu-id="9ab57-112">`RouteConfig` Fügt in der Standard Projektvorlage den `FriendlyUrlSettings` für Web Forms hinzu, damit Anwendungs-URLs die Dateierweiterung weglassen können `.ASPX` .</span><span class="sxs-lookup"><span data-stu-id="9ab57-112">`RouteConfig` in the default project template adds the `FriendlyUrlSettings` for web forms to allow application URLs to omit the `.ASPX` file extension.</span></span>  <span data-ttu-id="9ab57-113">Die Standardvorlage enthält auch eine-Direktive, die permanente http-Umleitungs Statuscodes (http 301) für die `.ASPX` Seiten an die Friendly URL mit dem Dateinamen bereitstellt, der die Erweiterung auslässt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-113">The default template also contains a directive that provides permanent HTTP redirect status codes (HTTP 301) for the `.ASPX` pages to the friendly URL with the file name that omits the extension.</span></span>

<span data-ttu-id="9ab57-114">Mit ASP.net Core und blazor werden diese Methoden entweder vereinfacht und in der-Klasse konsolidiert, `Startup` oder Sie werden zugunsten gängiger Webtechnologien eliminiert.</span><span class="sxs-lookup"><span data-stu-id="9ab57-114">With ASP.NET Core and Blazor, these methods are either simplified and consolidated into the `Startup` class or they are eliminated in favor of common web technologies.</span></span>

## <a name="blazor-server-startup-structure"></a><span data-ttu-id="9ab57-115">Start Struktur des blazor-Servers</span><span class="sxs-lookup"><span data-stu-id="9ab57-115">Blazor Server Startup Structure</span></span>

<span data-ttu-id="9ab57-116">Blazor-Server Anwendungen befinden sich auf einem ASP.net Core 3,0 oder einer höheren Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ab57-116">Blazor Server applications reside on top of an ASP.NET Core 3.0 or later application.</span></span>  <span data-ttu-id="9ab57-117">ASP.net Core Webanwendungen werden über ein paar von Methoden in der-Klasse im Stamm `Startup.cs` Ordner der Anwendung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9ab57-117">ASP.NET Core web applications are configured through a pair of methods in the `Startup.cs` class on the root folder of the application.</span></span>  <span data-ttu-id="9ab57-118">Der Standard Inhalt der Startklasse ist unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-118">The Startup class's default content is listed below</span></span>

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

<span data-ttu-id="9ab57-119">Wie bei den restlichen ASP.net Core wird die Startup-Klasse mit den Prinzipien der Abhängigkeitsinjektion erstellt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-119">Like the rest of ASP.NET Core, the Startup class is created with dependency injection principles.</span></span>  <span data-ttu-id="9ab57-120">`IConfiguration`Wird für den Konstruktor bereitgestellt und für den späteren Zugriff während der Konfiguration in einer öffentlichen Eigenschaft gezischt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-120">The `IConfiguration` is provided to the constructor and stashed in a public property for later access during configuration.</span></span>

<span data-ttu-id="9ab57-121">Die `ConfigureServices` in ASP.net Core eingeführte-Methode ermöglicht die Konfiguration der verschiedenen ASP.net Core Framework-Dienste für den integrierten Abhängigkeits Injection-Container des Frameworks.</span><span class="sxs-lookup"><span data-stu-id="9ab57-121">The `ConfigureServices` method introduced in ASP.NET Core allows for the various ASP.NET Core framework services to be configured for the framework's built-in dependency injection container.</span></span>  <span data-ttu-id="9ab57-122">Mit den verschiedenen `services.Add*` Methoden werden Dienste hinzugefügt, die Funktionen wie Authentifizierung, Razor-Seiten, MVC-Controller Routing, signalr-und blazor-Server Interaktionen unter vielen anderen Funktionen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9ab57-122">The various `services.Add*` methods add services that enable features such as authentication, razor pages, MVC controller routing, SignalR, and Blazor Server interactions among many others.</span></span>  <span data-ttu-id="9ab57-123">Diese Methode wurde in Web Forms nicht benötigt, da die Verarbeitung und Behandlung der ASPX-, ASCX-, ashx-und ASMX-Dateien durch Verweisen auf ASP.net in der web.config Konfigurationsdatei definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9ab57-123">This method was not needed in web forms, as the parsing and handling of the ASPX, ASCX, ASHX, and ASMX files was defined by referencing ASP.NET in the web.config configuration file.</span></span>  <span data-ttu-id="9ab57-124">Weitere Informationen zur Abhängigkeitsinjektion in ASP.net Core finden Sie in der [Online Dokumentation](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="9ab57-124">More information about dependency injection in ASP.NET Core is available in the [online documentation](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span>

<span data-ttu-id="9ab57-125">Mit der- `Configure` Methode wird das Konzept der HTTP-Pipeline zum ASP.net Core eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9ab57-125">The `Configure` method introduces the concept of the HTTP pipeline to ASP.NET Core.</span></span>  <span data-ttu-id="9ab57-126">Bei dieser Methode deklarieren wir von oben nach unten die [Middleware](middleware.md) , die jede Anforderung verarbeitet, die an die Anwendung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ab57-126">In this method, we declare from top to bottom the [Middleware](middleware.md) that will handle every request sent to our application.</span></span> <span data-ttu-id="9ab57-127">Die meisten dieser Features in der Standardkonfiguration waren in den Web Forms-Konfigurationsdateien verstreut und sind nun an einem Ort, um die Referenz zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="9ab57-127">Most of these features in the default configuration were scattered across the web forms configuration files and are now in one place for ease of reference.</span></span>

<span data-ttu-id="9ab57-128">Die Konfiguration der benutzerdefinierten Fehlerseite ist nicht mehr in einer `web.config` Datei gespeichert, sondern ist nun so konfiguriert, dass Sie immer angezeigt wird, wenn die Anwendungsumgebung nicht beschriftet ist `Development` .</span><span class="sxs-lookup"><span data-stu-id="9ab57-128">No longer is the configuration of the custom error page placed in a `web.config` file, but now is configured to always be shown if the application environment is not labeled `Development`.</span></span>  <span data-ttu-id="9ab57-129">Darüber hinaus sind ASP.net Core Anwendungen nun so konfiguriert, dass Sie sichere Seiten mit TLS standardmäßig mit dem-Methoden Befehl bereitstellen `UseHttpsRedirection` .</span><span class="sxs-lookup"><span data-stu-id="9ab57-129">Additionally, ASP.NET Core applications are now configured to serve secure pages with TLS by default with the `UseHttpsRedirection` method call.</span></span>

<span data-ttu-id="9ab57-130">Als nächstes wird eine unerwartete Konfigurations Methode in aufgelistet `UseStaticFiles` .</span><span class="sxs-lookup"><span data-stu-id="9ab57-130">Next, an unexpected configuration method is listed to `UseStaticFiles`.</span></span>  <span data-ttu-id="9ab57-131">In ASP.net Core muss die Unterstützung für statische Dateien (z. b. JavaScript-, CSS-und Bilddateien) explizit aktiviert werden, und nur die Dateien im Ordner " *wwwroot* " der APP sind standardmäßig öffentlich adressierbar.</span><span class="sxs-lookup"><span data-stu-id="9ab57-131">In ASP.NET Core, support for requests for static files (like JavaScript, CSS, and image files) must be explicitly enabled, and only files in the app's *wwwroot* folder are publicly addressable by default.</span></span>

<span data-ttu-id="9ab57-132">Die nächste Zeile ist die erste Zeile, in der eine der Konfigurationsoptionen von Web Forms repliziert wird: `UseRouting` .</span><span class="sxs-lookup"><span data-stu-id="9ab57-132">The next line is the first that replicates one of the configuration options from web forms: `UseRouting`.</span></span>  <span data-ttu-id="9ab57-133">Diese Methode fügt der Pipeline den ASP.net Core Router hinzu, und er kann entweder hier oder in den einzelnen Dateien konfiguriert werden, an die er weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="9ab57-133">This method adds the ASP.NET Core router to the pipeline and it can be either configured here or in the individual files that it can consider routing to.</span></span>  <span data-ttu-id="9ab57-134">Weitere Informationen zur Routing Konfiguration finden Sie im [Abschnitt Routing](pages-routing-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="9ab57-134">More information about routing configuration can be found in the [Routing section](pages-routing-layouts.md).</span></span>

<span data-ttu-id="9ab57-135">Die letzte Anweisung in dieser Methode definiert die Endpunkte, die ASP.net Core überwachen.</span><span class="sxs-lookup"><span data-stu-id="9ab57-135">The final statement in this method defines the endpoints that ASP.NET Core is listening on.</span></span>  <span data-ttu-id="9ab57-136">Dabei handelt es sich um Websites, auf die über den Webserver zugegriffen werden kann, auf die Sie auf dem Webserver zugreifen und Inhalte erhalten, die von .NET verarbeitet und an Sie</span><span class="sxs-lookup"><span data-stu-id="9ab57-136">These are the web accessible locations that you can access on the web server and receive some content handled by .NET and returned to you.</span></span>  <span data-ttu-id="9ab57-137">Der erste Eintrag `MapBlazorHub` konfiguriert einen signalr-Hub für die Verwendung bei der Bereitstellung der Echtzeitverbindung und der permanenten Verbindung mit dem Server, auf dem der Status und das Rendering von blazor-Komponenten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9ab57-137">The first entry, `MapBlazorHub` configures a SignalR hub for use in providing the real-time and persistent connection to the server where the state and rendering of Blazor components is handled.</span></span>  <span data-ttu-id="9ab57-138">Der `MapFallbackToPage` Methodenaufruf gibt den Speicherort der Website an, auf die der Zugriff auf die Seite der Seite erfolgt, von der die blazor-Anwendung gestartet wird. Außerdem wird die Anwendung für die Verarbeitung von Deep-Linking-Anforderungen von Client</span><span class="sxs-lookup"><span data-stu-id="9ab57-138">The `MapFallbackToPage` method call indicates the web-accessible location of the page that starts the Blazor application and also configures the application to handle deep-linking requests from the client-side.</span></span>  <span data-ttu-id="9ab57-139">Diese Funktion wird bei der Arbeit angezeigt, wenn Sie einen Browser öffnen und direkt zur von blazor verarbeiteten Route in Ihrer Anwendung navigieren, z `/counter` . b. in der Standard Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="9ab57-139">You will see this feature at work if you open a browser and navigate directly to Blazor handled route in your application, such as `/counter` in the default project template.</span></span> <span data-ttu-id="9ab57-140">Die Anforderung wird von der Fall Back-Seite *_Host. cshtml* verarbeitet, von der dann der blazor-Router ausgeführt und die Gegenseite gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="9ab57-140">The request gets handled by the *_Host.cshtml* fallback page, which then runs the Blazor router and renders the counter page.</span></span>

## <a name="upgrading-the-bundleconfig-process"></a><span data-ttu-id="9ab57-141">Aktualisieren des bundleconfig-Prozesses</span><span class="sxs-lookup"><span data-stu-id="9ab57-141">Upgrading the BundleConfig Process</span></span>

<span data-ttu-id="9ab57-142">Technologien zum Bündeln von Assets wie CSS-Stylesheets und JavaScript-Dateien haben sich deutlich verbessert, mit anderen Technologien, die sich schnell entwickelnden Tools und Techniken zur Verwaltung dieser Ressourcen anbieten.</span><span class="sxs-lookup"><span data-stu-id="9ab57-142">Technologies for bundling assets like CSS stylesheets and JavaScript files have evolved significantly, with other technologies providing quickly evolving tools and techniques for managing these resources.</span></span>  <span data-ttu-id="9ab57-143">Zu diesem Zweck empfehlen wir die Verwendung eines Node-Befehlszeilen Tools, wie z. b. grunt/Gulp/WebPack, um Ihre statischen Assets zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="9ab57-143">To this end, we recommend using a Node command-line tool such as Grunt / Gulp / WebPack to package your static assets.</span></span>

<span data-ttu-id="9ab57-144">Die Befehlszeilen Tools "Grunt", "Gulp" und "WebPack" und die zugehörigen Konfigurationen können Ihrer Anwendung hinzugefügt werden. diese Dateien werden von ASP.net Core während des anwendungsbuildprozesses in Ruhe ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9ab57-144">The Grunt, Gulp, and WebPack command-line tools and their associated configurations can be added to your application and ASP.NET Core will quietly ignore those files during the application build process.</span></span>  <span data-ttu-id="9ab57-145">Sie können einen-Befehl zum Ausführen ihrer Aufgaben hinzufügen, indem Sie eine `Target` in der Projektdatei mit einer Syntax hinzufügen, die der folgenden ähnelt, die ein Gulp-Skript und das `min` Ziel innerhalb des Skripts auslöst.</span><span class="sxs-lookup"><span data-stu-id="9ab57-145">You can add a call to run their tasks by adding a `Target` inside your project file with syntax similar to the following that would trigger a gulp script and the `min` target inside that script</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

<span data-ttu-id="9ab57-146">Weitere Informationen zu beiden Strategien zum Verwalten Ihrer CSS-und JavaScript-Dateien finden Sie in den Paketen [und minimieren static Assets in ASP.net Core](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9ab57-146">More details about both strategies to manage your CSS and JavaScript files are available in the [Bundle and minify static assets in ASP.NET Core](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9ab57-147">[Zurück](project-structure.md)
>[Weiter](components.md)</span><span class="sxs-lookup"><span data-stu-id="9ab57-147">[Previous](project-structure.md)
[Next](components.md)</span></span>
