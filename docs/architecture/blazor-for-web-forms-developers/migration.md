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
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>Migration von ASP.NET Web Forms nach Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Das Migrieren einer Codebasis aus ASP.NET Web Forms nach Blazor ist eine zeitaufwändige Aufgabe, die eine Planung erfordert. In diesem Kapitel wird der Prozess beschrieben. Eine Möglichkeit, den Übergang zu erleichtern, besteht darin, sicherzustellen, dass die App einer *N-Tier-Architektur* entspricht, wobei das App-Modell (in diesem Fall Web Forms) von der Geschäftslogik getrennt ist. Diese logische Trennung von Ebenen macht deutlich, was zu .NET Core und Blazor verschoben werden muss.

In diesem Beispiel wird die auf [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) verfügbare eShop-App verwendet. eShop ist ein Katalogservice, der CRUD-Funktionen über Formulareingabe und -validierung bereitstellt.

Warum sollte eine funktionierende App nach Blazor migriert werden? Oft gibt es keine Notwendigkeit. ASP.NET Web Forms wird noch viele Jahre lang unterstützt. Viele der funktionen, die Blazor bereitstellt, werden jedoch nur in einer migrierten App unterstützt. Zu diesen Funktionen gehören:

- Leistungsverbesserungen im Rahmen, wie z. B.`Span<T>`
- Fähigkeit, als WebAssembly ausgeführt zu werden
- Plattformübergreifende Unterstützung für Linux und macOS
- App-lokale Bereitstellung oder bereitstellung eines freigegebenen Frameworks ohne Auswirkungen auf andere Apps

Wenn diese oder andere neue Funktionen überzeugend genug sind, kann es einen Wert für die Migration der App geben. Die Migration kann verschiedene Formen annehmen. Es kann die gesamte App oder nur bestimmte Endpunkte sein, die die Änderungen erfordern. Die Entscheidung für die Migration basiert letztlich auf den Geschäftsproblemen, die vom Entwickler gelöst werden müssen.

## <a name="server-side-versus-client-side-hosting"></a>Serverseitiges im Vergleich zum clientseitigen Hosting

Wie im [Kapitel Hostingmodelle](hosting-models.md) beschrieben, kann eine Blazor-App auf zwei verschiedene Arten gehostet werden: server- und clientseitig. Das serverseitige Modell verwendet ASP.NET Core SignalR-Verbindungen, um die DOM-Updates zu verwalten, während der tatsächliche Code auf dem Server ausgeführt wird. Das clientseitige Modell wird als WebAssembly in einem Browser ausgeführt und erfordert keine Serververbindungen. Es gibt eine Reihe von Unterschieden, die sich auf eine bestimmte App auswirken können:

- Das Ausführen als WebAssembly befindet sich noch in der Entwicklung und unterstützt möglicherweise nicht alle Features (z. B. Threading) zum aktuellen Zeitpunkt.
- Die Chaty-Kommunikation zwischen Client und Server kann zu Latenzproblemen im serverseitigen Modus führen
- Der Zugriff auf Datenbanken und interne oder geschützte Dienste erfordert einen separaten Dienst mit clientseitigem Hosting

Zum Zeitpunkt des Schreibens ähnelt das serverseitige Modell eher Web Forms. Der größte Teil dieses Kapitels konzentriert sich auf das serverseitige Hostingmodell, da es produktionsbereit ist.

## <a name="create-a-new-project"></a>Erstellen eines neuen Projekts

Dieser erste Migrationsschritt besteht darin, ein neues Projekt zu erstellen. Dieser Projekttyp basiert auf den SDK-Projekten von .NET Core und vereinfacht einen Großteil der Bausteinplatte, die in früheren Projektformaten verwendet wurde. Weitere Einzelheiten finden Sie im Kapitel [über Projektstruktur](project-structure.md).

Nachdem das Projekt erstellt wurde, installieren Sie die Bibliotheken, die im vorherigen Projekt verwendet wurden. In älteren Web Forms-Projekten haben Sie möglicherweise die Datei *packages.config* verwendet, um die erforderlichen NuGet-Pakete aufzulisten. Im neuen SDK-Projekt wurde *packages.config* durch `<PackageReference>` Elemente in der Projektdatei ersetzt. Ein Vorteil dieses Ansatzes besteht darin, dass alle Abhängigkeiten transitiv installiert werden. Sie listen nur die Abhängigkeiten der obersten Ebene auf, die Ihnen wichtig sind.

Viele der von Ihnen verwendenden Abhängigkeiten sind für .NET Core verfügbar, einschließlich Entity Framework 6 und log4net. Wenn keine .NET Core- oder .NET Standard-Version verfügbar ist, kann die .NET Framework-Version häufig verwendet werden. Ihre Erfahrungen können hiervon abweichen. Jede API, die in .NET Core nicht verfügbar ist, verursacht einen Laufzeitfehler. Visual Studio benachrichtigt Sie über solche Pakete. Auf dem **Referenzknoten** des Projekts im **Projektmappen-Explorer**wird ein gelbes Symbol angezeigt.

Im Blazor-basierten eShop-Projekt können Sie die pakete sehen, die installiert sind. Zuvor listete die Datei *packages.config* jedes im Projekt verwendete Paket auf, was zu einer Fast 50 Zeilen langen Datei führte. Ein Ausschnitt von *packages.config* ist:

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

Das `<packages>` Element enthält alle erforderlichen Abhängigkeiten. Es ist schwierig zu identifizieren, welche dieser Pakete enthalten sind, da Sie sie benötigen. Einige `<package>` Elemente werden einfach aufgelistet, um die Anforderungen von Abhängigkeiten zu erfüllen, die Sie benötigen.

Das Blazor-Projekt listet die Abhängigkeiten `<ItemGroup>` auf, die Sie innerhalb eines Elements in der Projektdatei benötigen:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Ein NuGet-Paket, das die Lebensdauer von Web Forms-Entwicklern vereinfacht, ist das [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md). Obwohl .NET Core plattformübergreifend ist, sind einige Funktionen nur unter Windows verfügbar. Windows-spezifische Funktionen werden durch die Installation des Kompatibilitätspakets zur Verfügung gestellt. Beispiele für solche Funktionen sind die Registrierungs-, WMI- und Verzeichnisdienste. Das Paket fügt rund 20.000 APIs hinzu und aktiviert viele Dienste, mit denen Sie möglicherweise bereits vertraut sind. Für das eShop-Projekt ist das Kompatibilitätspaket nicht erforderlich. Wenn Ihre Projekte jedoch Windows-spezifische Features verwenden, erleichtert das Paket die Migrationsbemühungen.

## <a name="enable-startup-process"></a>Startvorgang aktivieren

Der Startvorgang für Blazor wurde von Web Forms geändert und folgt einem ähnlichen Setup für andere ASP.NET Core-Diensten. Wenn die Serverseite gehostet wird, werden Blazor-Komponenten als Teil einer normalen ASP.NET Core-App ausgeführt. Wenn Blazor-Komponenten im Browser mit WebAssembly gehostet werden, verwenden sie ein ähnliches Hostingmodell. Der Unterschied besteht darin, dass die Komponenten als separater Dienst von einem der Back-End-Prozesse ausgeführt werden. So oder so ist der Start ähnlich.

Die *Global.asax.cs* Datei ist die Standardstartseite für Web Forms-Projekte. Im eShop-Projekt konfiguriert diese Datei den Container Inversion of Control (IoC) und verarbeitet die verschiedenen Lebenszyklusereignisse der App oder Anforderung. Einige dieser Ereignisse werden mit Middleware `Application_BeginRequest`behandelt (z. B. ). Andere Ereignisse erfordern das Überschreiben bestimmter Dienste über Abhängigkeitsinjektion (DI).

Die *Global.asax.cs* Datei für eShop enthält beispielsweise den folgenden Code:

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

Die vorhergehende `Startup` Datei wird zur Klasse im serverseitigen Blazor:

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

Eine wesentliche Änderung, die Sie von Web Forms bemerken können, ist die Bedeutung von DI. DI ist ein Leitgedanke im ASP.NET Core-Design. Es unterstützt die Anpassung fast aller Aspekte des ASP.NET Core-Frameworks. Es gibt sogar einen integrierten Dienstanbieter, der für viele Szenarien verwendet werden kann. Wenn mehr Anpassungen erforderlich sind, kann sie von den vielen Community-Projekten unterstützt werden. Sie können z. B. Ihre DI-Bibliotheksinvestitionen von Drittanbietern vortragen.

In der ursprünglichen eShop-App gibt es eine konfiguration für die Sitzungsverwaltung. Da der serverseitige Blazor ASP.NET Core SignalR für die Kommunikation verwendet, wird der Sitzungsstatus nicht unterstützt, da die Verbindungen unabhängig von einem HTTP-Kontext auftreten können. Eine App, die den Sitzungsstatus verwendet, erfordert eine Neuarchitektur, bevor sie als Blazor-App ausgeführt wird.

Weitere Informationen zum App-Start finden Sie unter [App-Start](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Migrieren von HTTP-Modulen und -Handlern zur Middleware

HTTP-Module und -Handler sind häufige Muster in Web Forms, um die HTTP-Anforderungspipeline zu steuern. Klassen, `IHttpModule` die `IHttpHandler` eingehende Anforderungen implementieren oder registrieren und verarbeiten können. Web Forms konfiguriert Module und Handler in der Datei *web.config.* Web Forms basiert auch stark auf der Behandlung von App-Lebenszyklus-Ereignis. ASP.NET Core verwendet stattdessen Middleware. Middleware ist in `Configure` der `Startup` Methode der Klasse registriert. Die Middleware-Ausführungsreihenfolge wird durch den Registrierungsauftrag bestimmt.

Im Abschnitt [Startprozess aktivieren](#enable-startup-process) wurde von Web Forms `Application_BeginRequest` als Methode ein Lebenszyklusereignis ausgelöst. Dieses Ereignis ist in ASP.NET Core nicht verfügbar. Eine Möglichkeit, dieses Verhalten zu erreichen, besteht darin, Middleware zu implementieren, wie sie im *Beispiel Startup.cs* Datei gezeigt wird. Diese Middleware führt die gleiche Logik aus und überträgt dann die Steuerung an den nächsten Handler in der Middlewarepipeline.

Weitere Informationen zum Migrieren von Modulen und Handlern finden Sie unter [Migrieren von HTTP-Handlern und -Modulen zu ASP.NET Core-Middleware](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Migration statischer Dateien

Um statische Dateien (z. B. HTML, CSS, Images und JavaScript) zu bedienen, müssen die Dateien von Middleware verfügbar gemacht werden. Durch `UseStaticFiles` Aufrufen der Methode wird die Bereitstellung statischer Dateien aus dem Webstammpfad ermöglicht. Das Standard-Webstammverzeichnis ist *wwwroot*, kann jedoch angepasst werden. Wie in `Configure` der Methode der `Startup` eShop-Klasse enthalten:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Das eShop-Projekt ermöglicht den statischen Einfachen Dateizugriff. Für den statischen Dateizugriff stehen viele Anpassungen zur Verfügung. Informationen zum Aktivieren von Standarddateien oder einem Dateibrowser finden Sie [unter Statische Dateien in ASP.NET Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Migrieren von Laufzeitbündelungs- und Minifikationseinstellungen

Bündelung und Minimierung sind Techniken zur Leistungsoptimierung, um die Anzahl und Größe von Serveranforderungen zum Abrufen bestimmter Dateitypen zu reduzieren. JavaScript und CSS werden häufig in irgendeiner Form gebündelt oder minifikiert, bevor sie an den Client gesendet werden. In ASP.NET Web Forms werden diese Optimierungen zur Laufzeit behandelt. Die Optimierungskonventionen sind eine *App_Start/BundleConfig.cs-Datei* definiert. In ASP.NET Core wird ein deklarativerer Ansatz gewählt. Eine Datei listet die zu minimierenden Dateien zusammen mit bestimmten Minifizierungseinstellungen auf.

Weitere Informationen zur Bündelung und Minierung finden Sie unter [Bündeln und Minimieren statischer Assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>MIGrieren von ASPX-Seiten

Eine Seite in einer Web Forms-App ist eine Datei mit der *Aspx-Erweiterung.* Eine Web Forms-Seite kann häufig einer Komponente in Blazor zugeordnet werden. Eine Blazor-Komponente wird in einer Datei mit der *Erweiterung .razor* erstellt. Für das eShop-Projekt werden fünf Seiten in eine Razor-Seite konvertiert.

Die Detailansicht besteht beispielsweise aus drei Dateien im Web Forms-Projekt: *Details.aspx*, *Details.aspx.cs*und *Details.aspx.designer.cs*. Bei der Konvertierung in Blazor werden Code-Behind und Markup in *Details.razor*kombiniert. Die Razor-Kompilierung (entspricht dem in *.designer.cs-Dateien)* wird im *obj-Verzeichnis* gespeichert und ist im **Projektmappen-Explorer**standardmäßig nicht sichtbar. Die Web Forms-Seite besteht aus folgendem Markup:

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

Das Codebehind des vorherigen Markups enthält den folgenden Code:

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

Bei der Konvertierung in Blazor wird die Web Forms-Seite in den folgenden Code übersetzt:

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

Beachten Sie, dass sich der Code und das Markup in derselben Datei befinden. Alle erforderlichen Dienste werden `@inject` mit dem Attribut zugänglich gemacht. Gemäß `@page` der Direktive kann diese `Catalog/Details/{id}` Seite an der Route aufgerufen werden. Der Wert des Platzhalters `{id}` der Route wurde auf eine ganze Zahl beschränkt. Wie im [Routingabschnitt](pages-routing-layouts.md) beschrieben, gibt eine Razor-Komponente im Gegensatz zu Web Forms ihre Route und alle enthaltenen Parameter explizit an. Viele Web Forms-Steuerelemente haben möglicherweise keine genauen Gegenstücke in Blazor. Es gibt oft einen entsprechenden HTML-Ausschnitt, der dem gleichen Zweck dient. Das `<asp:Label />` Steuerelement kann z. B. `<label>` durch ein HTML-Element ersetzt werden.

### <a name="model-validation-in-blazor"></a>Modellvalidierung in Blazor

Wenn Ihr Web Forms-Code eine Validierung enthält, können Sie vieles von dem, was Sie haben, mit wenig bis gar keinen Änderungen übertragen. Ein Vorteil der Ausführung in Blazor besteht darin, dass dieselbe Validierungslogik ausgeführt werden kann, ohne dass benutzerdefiniertes JavaScript erforderlich ist. Datenanmerkungen ermöglichen eine einfache Modellvalidierung.

Beispielsweise verfügt die Seite *Create.aspx* über ein Dateneingabeformular mit Validierung. Ein Beispielausschnitt würde wie folgt aussehen:

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

In Blazor wird das entsprechende Markup in einer *Create.razor-Datei* bereitgestellt:

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

Der `EditForm` Kontext umfasst Validierungsunterstützung und kann um Eingabe umbrochen werden. Datenanmerkungen sind eine gängige Möglichkeit zum Hinzufügen von Validierungen. Eine solche Validierungsunterstützung `DataAnnotationsValidator` kann über die Komponente hinzugefügt werden. Weitere Informationen zu diesem Mechanismus finden Sie [unter ASP.NET Core Blazor Forms and Validation](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Migrieren integrierter Web Forms-Steuerelemente

*Dieser Inhalt wird bald kommen.*

## <a name="migrate-configuration"></a>Migrating Configuration (Migrieren der Konfiguration)

In einem Web Forms-Projekt werden Konfigurationsdaten am häufigsten in der *Datei web.config* gespeichert. Auf die Konfigurationsdaten `ConfigurationManager`wird mit zugegriffen. Häufig waren Dienste zum Analysieren von Objekten erforderlich. Mit .NET Framework 4.7.2 wurde der Konfiguration `ConfigurationBuilders`über die Komposität hinzugefügt. Diese Builder ermöglichten Entwicklern das Hinzufügen verschiedener Quellen für die Konfiguration, die dann zur Laufzeit zusammengesetzt wurden, um die erforderlichen Werte abzurufen.

ASP.NET Core hat ein flexibles Konfigurationssystem eingeführt, mit dem Sie die Konfigurationsquelle oder die von Ihrer App und Bereitstellung verwendeten Quellen definieren können. Die `ConfigurationBuilder` Infrastruktur, die Sie möglicherweise in Ihrer Web Forms-App verwenden, wurde nach den Konzepten modelliert, die im ASP.NET Core-Konfigurationssystem verwendet werden.

Der folgende Ausschnitt veranschaulicht, wie das Web Forms eShop-Projekt *web.config* zum Speichern von Konfigurationswerten verwendet:

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

Es ist üblich, dass Geheimnisse, z. B. Datenbankverbindungszeichenfolgen, in der *web.config*gespeichert werden. Die Geheimnisse werden unweigerlich an unsicheren Orten, z. B. der Quellcodeverwaltung, beibehalten. Mit Blazor auf ASP.NET Core wird die vorhergehende XML-basierte Konfiguration durch die folgende JSON ersetzt:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON ist das Standardkonfigurationsformat. ASP.NET Core unterstützt jedoch viele andere Formate, einschließlich XML. Es gibt auch mehrere von der Community unterstützte Formate.

Der Konstruktor in der Klasse `Startup` des `IConfiguration` Blazor-Projekts akzeptiert eine Instanz über eine DI-Technik, die als Konstruktorinjektion bekannt ist:

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

Standardmäßig sind Umgebungsvariablen, JSON-Dateien (*appsettings.json* und *appsettings. Die Optionen "Environment.json*" und die Befehlszeilenoptionen werden als gültige Konfigurationsquellen im Konfigurationsobjekt registriert. Auf die Konfigurationsquellen `Configuration[key]`kann über zugegriffen werden. Eine erweiterte Technik besteht darin, die Konfigurationsdaten mithilfe des Optionsmusters an Objekte zu binden. Weitere Informationen zur Konfiguration und zum Optionsmuster finden Sie unter [Konfiguration in ASP.NET Core-](/aspnet/core/fundamentals/configuration/) und [Optionsmuster in ASP.NET Core](/aspnet/core/fundamentals/configuration/options).

## <a name="migrate-data-access"></a>Migrieren des Datenzugriffs

Der Datenzugriff ist ein wichtiger Aspekt jeder App. Das eShop-Projekt speichert Kataloginformationen in einer Datenbank und ruft die Daten mit Entity Framework (EF) 6 ab. Da EF 6 in .NET Core 3.0 unterstützt wird, kann das Projekt es weiterhin verwenden.

Folgende EF-bezogene Änderungen waren für eShop notwendig:

- In .NET Framework `DbContext` akzeptiert das Objekt eine Zeichenfolge des Formulars *name=ConnectionString* und verwendet die Verbindungszeichenfolge von `ConfigurationManager.AppSettings[ConnectionString]` zum Verbinden. In .NET Core wird dies nicht unterstützt. Die Verbindungszeichenfolge muss angegeben werden.
- Auf die Datenbank wurde synchron zugegriffen. Obwohl dies funktioniert, kann die Skalierbarkeit leiden. Diese Logik sollte in ein asynchrones Muster verschoben werden.

Obwohl es nicht die gleiche systemeigene Unterstützung für die Datasetbindung gibt, bietet Blazor Flexibilität und Leistung mit seiner C-Unterstützung auf einer Razor-Seite. Sie können z. B. Berechnungen durchführen und das Ergebnis anzeigen. Weitere Informationen zu Datenmustern in Blazor finden Sie im Kapitel [Datenzugriff.](data.md)

## <a name="architectural-changes"></a>Architektonische Veränderungen

Schließlich gibt es einige wichtige architektonische Unterschiede zu berücksichtigen, wenn sie nach Blazor wandern. Viele dieser Änderungen gelten für alle Änderungen, die auf .NET Core oder ASP.NET Core basieren.

Da Blazor auf .NET Core basiert, gibt es Überlegungen, die Unterstützung für .NET Core sicherzustellen. Zu den wichtigsten Änderungen gehört das Entfernen der folgenden Funktionen:

- Mehrere AppDomains
- Remoting
- Codezugriffssicherheit (Code Access Security, CAS)
- Sicherheitstransparenz

Weitere Informationen zu Techniken zum Identifizieren notwendiger Änderungen zur Unterstützung der Ausführung von .NET Core finden Sie unter [Portieren des Codes von .NET Framework auf .NET Core](/dotnet/core/porting).

ASP.NET Core ist eine neu gestaltete Version von ASP.NET und hat einige Änderungen, die zunächst nicht offensichtlich erscheinen. Die wichtigsten Änderungen sind:

- Kein Synchronisierungskontext, d. `HttpContext.Current`h., es gibt keine , `Thread.CurrentPrincipal`oder andere statische Accessoren
- Kein Schattenkopieren
- Keine Anforderungswarteschlange

Viele Vorgänge in ASP.NET Core sind asynchron, was eine einfachere Auslagerung von E/A-gebundenen Aufgaben ermöglicht. Es ist wichtig, niemals `Task.Wait()` zu `Task.GetResult()`blockieren, indem Sie oder verwenden, was Threadpoolressourcen schnell ausschöpfen kann.

## <a name="migration-conclusion"></a>Migrationsabschluss

An diesem Punkt haben Sie viele Beispiele dafür gesehen, was es braucht, um ein Web Forms-Projekt nach Blazor zu verschieben. Ein vollständiges Beispiel finden Sie im [eShopOnBlazor-Projekt.](https://github.com/dotnet-architecture/eShopOnBlazor)

>[!div class="step-by-step"]
>[Zurück](security-authentication-authorization.md)
