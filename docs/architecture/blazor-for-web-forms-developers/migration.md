---
title: Migrieren von ASP.net Web Forms zu Blazor
description: Erfahren Sie, wie Sie eine vorhandene ASP.net-Web Forms-APP zu migrieren Blazor .
author: twsouthwick
ms.author: tasou
no-loc:
- Blazor
- WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 853358fbf534ee7501412259c61efe054b4757a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161203"
---
# <a name="migrate-from-aspnet-web-forms-to-no-locblazor"></a>Migrieren von ASP.net Web Forms zu Blazor

Das Migrieren einer Codebasis von ASP.net Web Forms zu Blazor ist eine zeitaufwändige Aufgabe, für die eine Planung erforderlich ist. In diesem Kapitel wird der Prozess beschrieben. Eine Möglichkeit, den Übergang zu vereinfachen, besteht darin sicherzustellen, dass die APP einer *N-Tier-* Architektur entspricht, bei der das App-Modell (in diesem Fall Web Forms) von der Geschäftslogik getrennt ist. Diese logische Trennung von Ebenen macht es klar, was zu .net Core und verschoben werden muss Blazor .

In diesem Beispiel wird die auf [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) verfügbare eShop-App verwendet. der eShop ist ein Katalog Dienst, der CRUD-Funktionen per Formular Eintrag und Validierung bereitstellt.

Warum sollte eine funktionierende APP zu migriert werden Blazor ? Oft ist es nicht erforderlich. ASP.net Web Forms wird noch viele Jahre lang unterstützt. Viele der Funktionen, die Blazor bereitstellt, werden jedoch nur für eine migrierte App unterstützt. Zu diesen Features gehören:

- Leistungsverbesserungen im Framework, z. b. `Span<T>`
- Möglichkeit zum Ausführen als WebAssembly
- Plattformübergreifende Unterstützung für Linux und macOS
- Lokale App-Bereitstellung oder Bereitstellung von freigegebenen Frameworks ohne Auswirkung auf andere apps

Wenn diese oder andere neue Features aussagekräftig genug sind, kann es beim Migrieren der APP zu einem Wert kommen. Die Migration kann verschiedene Formen annehmen. Dabei kann es sich um die gesamte APP oder nur bestimmte Endpunkte handeln, für die die Änderungen erforderlich sind. Die Entscheidung für die Migration basiert letztendlich auf den geschäftlichen Problemen, die vom Entwickler gelöst werden müssen.

## <a name="server-side-versus-client-side-hosting"></a>Server seitiges und Client seitiges Hosting

Wie im Kapitel [Hostingmodelle](hosting-models.md) beschrieben, kann eine- Blazor App auf zwei verschiedene Arten gehostet werden: Server-und Client seitig. Das serverseitige Modell verwendet ASP.net Core signalr-Verbindungen, um die DOM-Aktualisierungen bei der Ausführung von tatsächlichem Code auf dem Server zu verwalten. Das Client seitige Modell wird wie WebAssembly in einem Browser ausgeführt und erfordert keine Serververbindungen. Es gibt eine Reihe von unterschieden, die sich darauf auswirken können, was für eine bestimmte App am besten geeignet ist:

- Das Ausführen WebAssembly von als ist noch in der Entwicklung und unterstützt möglicherweise nicht alle Features (z. b. Threading) zum aktuellen Zeitpunkt.
- Die Kommunikation zwischen dem Client und dem Server kann zu Latenzproblemen im serverseitigen Modus führen.
- Der Zugriff auf Datenbanken und interne oder geschützte Dienste erfordert einen separaten Dienst mit Client seitigem Hosting.

Zum Zeitpunkt des Schreibens ähnelt das serverseitige Modell Web Forms. In diesem Kapitel liegt der Schwerpunkt auf dem serverseitigen Hostingmodell, da es in der Produktion bereit ist.

## <a name="create-a-new-project"></a>Erstellt ein neues Projekt

Dieser erste Migrationsschritt besteht darin, ein neues Projekt zu erstellen. Dieser Projekttyp basiert auf den SDK-Stil Projekten von .net Core und vereinfacht einen Großteil der Bausteine, die in früheren Projekt Formaten verwendet wurden. Weitere Details finden Sie im Kapitel zur [Projektstruktur](project-structure.md).

Nachdem das Projekt erstellt wurde, installieren Sie die Bibliotheken, die im vorherigen Projekt verwendet wurden. In älteren Web Forms Projekten haben Sie möglicherweise die Datei *packages.config* verwendet, um die benötigten nuget-Pakete aufzulisten. Im neuen Projekt im SDK-Stil wurde *packages.config* durch `<PackageReference>` Elemente in der Projektdatei ersetzt. Ein Vorteil dieses Ansatzes besteht darin, dass alle Abhängigkeiten transitiv installiert werden. Sie Listen nur die Abhängigkeiten auf oberster Ebene auf, für die Sie sich interessieren.

Viele der von Ihnen verwendeten Abhängigkeiten sind für .net Core verfügbar, einschließlich Entity Framework 6 und log4net. Wenn keine .net Core-oder .NET Standard Version verfügbar ist, kann die .NET Framework Version häufig verwendet werden. Ihre Erfahrungen können hiervon abweichen. Jede verwendete API, die in .net Core nicht verfügbar ist, verursacht einen Laufzeitfehler. Visual Studio benachrichtigt Sie über solche Pakete. Ein gelbes Symbol wird im Knoten **Verweise** des Projekts in **Projektmappen-Explorer**angezeigt.

Im Blazor -basierten eShop-Projekt können Sie die installierten Pakete sehen. Zuvor hat die *packages.config* -Datei alle im Projekt verwendeten Pakete aufgelistet, was zu einer Datei mit einer Länge von fast 50 Zeilen führte. Ein Ausschnitt von *packages.config* ist:

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

Das- `<packages>` Element enthält alle notwendigen Abhängigkeiten. Es ist schwierig festzustellen, welche dieser Pakete eingeschlossen werden, da Sie Sie benötigen. Einige `<package>` Elemente werden einfach aufgelistet, um die Anforderungen der benötigten Abhängigkeiten zu erfüllen.

Im Blazor Projekt werden die Abhängigkeiten aufgelistet, die innerhalb eines `<ItemGroup>` Elements in der Projektdatei erforderlich sind:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Ein nuget-Paket, das die Lebensdauer von Web Forms Entwicklern vereinfacht, ist das [Windows-Kompatibilitätspaket](../../core/porting/windows-compat-pack.md). Obwohl .net Core plattformübergreifend ist, stehen einige Funktionen nur unter Windows zur Verfügung. Windows-spezifische Funktionen werden durch die Installation des Kompatibilitätspakets zur Verfügung gestellt. Beispiele für solche Features sind die Registrierungs-, WMI-und Verzeichnisdienste. Das Paket fügt ungefähr 20.000 APIs hinzu und aktiviert viele Dienste, mit denen Sie möglicherweise bereits vertraut sind. Das Projekt "eShop" erfordert nicht das Kompatibilitätspaket. Wenn in Ihren Projekten jedoch Windows-spezifische Features verwendet werden, vereinfacht das Paket den Migrations Aufwand.

## <a name="enable-startup-process"></a>Startprozess aktivieren

Der Startvorgang für Blazor hat sich von Web Forms geändert und folgt einem ähnlichen Setup für andere ASP.net Core Dienste. Wenn serverseitig gehostet werden, Blazor werden Komponenten als Teil einer normalen ASP.net Core-app ausgeführt. Wenn im Browser mit gehostet WebAssembly wird, Blazor verwenden Komponenten ein ähnliches Hostingmodell. Der Unterschied besteht darin, dass die Komponenten als separater Dienst von einem beliebigen Back-End-Prozess ausgeführt werden. In jedem Fall ist der Start ähnlich.

Die Datei *Global.asax.cs* ist die Standard Startseite für Web Forms Projekte. Im Projekt "eShop" konfiguriert diese Datei den "Inversion of Control" (IOC)-Container und behandelt die verschiedenen Lebenszyklus Ereignisse der APP oder Anforderung. Einige dieser Ereignisse werden mit Middleware behandelt (z. b `Application_BeginRequest` .). Bei anderen Ereignissen müssen bestimmte Dienste über die Abhängigkeitsinjektion (di) überschrieben werden.

Beispielsweise enthält die Datei *Global.asax.cs* für den eShop den folgenden Code:

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

Die vorherige Datei wird zur- `Startup` Klasse auf Serverseite Blazor :

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

Eine bedeutende Änderung, die Sie von Web Forms bemerken, ist die Bedeutung von di. DI ist ein Leitfaden für das ASP.net Core Design. Es unterstützt die Anpassung fast aller Aspekte des ASP.net Core Frameworks. Es gibt sogar einen integrierten Dienstanbieter, der in vielen Szenarios verwendet werden kann. Wenn eine größere Anpassung erforderlich ist, kann Sie von den vielen Community-Projekten unterstützt werden. Beispielsweise können Sie die Investition ihrer Drittanbieter-di-Bibliothek weiterleiten.

In der ursprünglichen eShop-App gibt es eine Konfiguration für die Sitzungsverwaltung. Da der serverseitige Blazor ASP.net Core signalr für die Kommunikation verwendet, wird der Sitzungszustand nicht unterstützt, weil die Verbindungen unabhängig von einem HTTP-Kontext auftreten können. Eine APP, die den Sitzungszustand verwendet, erfordert eine Neuentwicklung, bevor Sie als-app ausgeführt wird Blazor .

Weitere Informationen zum Starten der App finden Sie unter [App Startup](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Migrieren von HTTP-Modulen und-Handlern zu Middleware

HTTP-Module und-Handler sind gängige Muster in Web Forms, um die HTTP-Anforderungs Pipeline zu steuern. Klassen, die `IHttpModule` oder implementieren `IHttpHandler` und eingehende Anforderungen verarbeiten können. Web Forms konfiguriert Module und Handler in der *web.config* Datei. Web Forms basiert ebenfalls stark auf der Ereignis Behandlung für den App-Lebenszyklus. ASP.net Core verwendet stattdessen Middleware. Die Middleware ist in der- `Configure` Methode der- `Startup` Klasse registriert. Die Ausführungsreihenfolge der Middleware wird durch die Registrierung bestimmt.

Im Abschnitt [enable Startup Process](#enable-startup-process) wurde ein Lifecycle-Ereignis durch Web Forms als-Methode ausgelöst `Application_BeginRequest` . Dieses Ereignis ist in ASP.net Core nicht verfügbar. Eine Möglichkeit, dieses Verhalten zu erreichen, besteht in der Implementierung von Middleware, wie im Beispiel für die *Startup.cs* -Datei gezeigt. Diese Middleware übernimmt dieselbe Logik und überträgt dann die Steuerung an den nächsten Handler in der middlewarepipeline.

Weitere Informationen zum Migrieren von Modulen und Handlern finden [Sie unter Migrieren von HTTP-Handlern und Modulen zu ASP.net Core Middleware](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Migrieren statischer Dateien

Zum Bereitstellen statischer Dateien (z. b. html, CSS, Bilder und JavaScript) müssen die Dateien von der Middleware verfügbar gemacht werden. Durch den Aufruf der- `UseStaticFiles` Methode wird die Funktion statischer Dateien aus dem webstammpfad ermöglicht. Das Standardweb Stammverzeichnis ist " *wwwroot*", kann jedoch angepasst werden. Wie in der `Configure` -Methode der-Klasse von eShop enthalten `Startup` :

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Das Projekt "eShop" ermöglicht grundlegenden statischen Dateizugriff. Für den Zugriff auf statische Dateien sind viele Anpassungen verfügbar. Informationen zum Aktivieren von Standard Dateien oder eines Datei Browsers finden Sie unter [statische Dateien in ASP.net Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Migrieren von Lauf Zeit bündeln und Minimieren der Einrichtung

Bündelung und Minimierung sind Techniken zur Leistungsoptimierung, mit denen die Anzahl und Größe von Serveranforderungen zum Abrufen bestimmter Dateitypen reduziert werden. JavaScript und CSS unterliegen häufig einer Form der Bündelung oder Minimierung, bevor Sie an den Client gesendet werden. In ASP.net-Web Forms werden diese Optimierungen zur Laufzeit behandelt. Die Optimierungs Konventionen sind *App_Start/bundleconfig.cs* -Datei definiert. In ASP.net Core wird ein deklarativer Ansatz gewählt. In einer Datei werden die zu minigenden Dateien zusammen mit bestimmten minieringeinstellungen aufgelistet.

Weitere Informationen zur Bündelung und Minimierung finden Sie unter [Bundle and minimieren static Assets in ASP.net Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Migrieren von ASPX-Seiten

Eine Seite in einer Web Forms-APP ist eine Datei mit der Erweiterung " *. aspx* ". Eine Web Forms Seite kann häufig einer Komponente in zugeordnet werden Blazor . Eine Blazor Komponente wird in einer Datei mit der *Razor* -Erweiterung erstellt. Für das Projekt "eShop" werden fünf Seiten in eine Razor Page konvertiert.

Die Detailansicht umfasst z. b. drei Dateien im Web Forms Projekt: *Details. aspx*, *Details.aspx.cs*und *Details.aspx.Designer.cs*. Beim umstellen in Blazor werden Code-Behind und Markup in *Details. Razor*kombiniert. Die Razor-Kompilierung (entspricht der *Designer.cs* -Dateien) wird im *obj* -Verzeichnis gespeichert und ist nicht standardmäßig in **Projektmappen-Explorer**sichtbar. Die Web Forms Seite besteht aus folgendem Markup:

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

Der Code Behind des vorangehenden Markups enthält den folgenden Code:

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

Bei der Konvertierung in Blazor wird die Web Forms Seite in den folgenden Code übersetzt:

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

Beachten Sie, dass sich der Code und das Markup in derselben Datei befinden. Alle erforderlichen Dienste werden mit dem-Attribut zugänglich gemacht `@inject` . Gemäß der- `@page` Direktive kann auf diese Seite über die `Catalog/Details/{id}` Route zugegriffen werden. Der Wert des Platzhalters der Route wurde `{id}` auf einen Integer-Wert beschränkt. Wie im Abschnitt [Routing](pages-routing-layouts.md) beschrieben, gibt eine Razor-Komponente im Gegensatz zu Web Forms explizit Ihre Route und alle darin enthaltenen Parameter an. Viele Web Forms Steuerelemente weisen in möglicherweise keine exakten Entsprechungen auf Blazor . Häufig gibt es einen äquivalenten HTML-Code Ausschnitt, der denselben Zweck erfüllt. Beispielsweise kann das `<asp:Label />` Steuerelement durch ein HTML-Element ersetzt werden `<label>` .

### <a name="model-validation-in-no-locblazor"></a>Modell Validierung in Blazor

Wenn Ihr Web Forms Code die Validierung umfasst, können Sie viele der Funktionen übertragen, bei denen es sich um geringfügige Änderungen handelt. Ein Vorteil der Ausführung von in Blazor besteht darin, dass dieselbe Validierungs Logik ohne benutzerdefiniertes JavaScript ausgeführt werden kann. Daten Anmerkungen ermöglichen eine einfache Modell Validierung.

Beispielsweise verfügt die Seite *Create. aspx* über ein Dateneingabe Formular mit Validierung. Ein Beispiel Ausschnitt sieht wie folgt aus:

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

In Blazor wird das entsprechende Markup in einer *Create. Razor* -Datei bereitgestellt:

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

Der `EditForm` Kontext umfasst Validierungs Unterstützung und kann um Eingaben umschlossen werden. Daten Anmerkungen sind eine gängige Methode zum Hinzufügen der Validierung. Diese Validierungs Unterstützung kann über die Komponente hinzugefügt werden `DataAnnotationsValidator` . Weitere Informationen zu diesem Mechanismus finden Sie unter [ASP.net Core Blazor Forms und Validierung](/aspnet/core/blazor/forms-validation).

## <a name="migrate-configuration"></a>Migrating Configuration (Migrieren der Konfiguration)

In einem Web Forms Projekt werden Konfigurationsdaten am häufigsten in der *web.config* -Datei gespeichert. Der Zugriff auf die Konfigurationsdaten erfolgt mit `ConfigurationManager` . Dienste waren häufig erforderlich, um Objekte zu analysieren. Mit .NET Framework 4.7.2 wurde die Zusammensetz barkeit der Konfiguration über hinzugefügt `ConfigurationBuilders` . Diese Generatoren ermöglichten Entwicklern, verschiedene Quellen für die Konfiguration hinzuzufügen, die dann zur Laufzeit zum Abrufen der erforderlichen Werte erstellt wurden.

ASP.net Core wurde ein flexibles Konfigurationssystem eingeführt, mit dem Sie die von Ihrer APP und Bereitstellung verwendete Konfigurations Quelle oder die Quell Quellen definieren können. Die `ConfigurationBuilder` Infrastruktur, die Sie möglicherweise in Ihrer Web Forms-App verwenden, wurde nach den im ASP.net Core Konfigurationssystem verwendeten Konzepten modelliert.

Der folgende Code Ausschnitt veranschaulicht, wie das Web Forms eShop-Projekt *web.config* verwendet, um Konfigurationswerte zu speichern:

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

Es ist üblich, dass geheime Schlüssel, wie z. b. Daten bankverbindungs Zeichenfolgen, in der *web.config*gespeichert werden. Die Geheimnisse werden unweigerlich an unsicheren Speicherorten wie der Quell Code Verwaltung persistent gespeichert. Bei Blazor ASP.net Core wird die vorherige XML-basierte Konfiguration durch den folgenden JSON-Code ersetzt:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON ist das Standard Konfigurationsformat. ASP.net Core unterstützt jedoch viele andere Formate, einschließlich XML. Es gibt auch mehrere von der Community unterstützte Formate.

Der Konstruktor in der Blazor -Klasse des Projekts `Startup` akzeptiert eine `IConfiguration` Instanz über eine di-Technik, die als Konstruktorinjektion bezeichnet wird:

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

Standardmäßig werden Umgebungsvariablen, JSON-Dateien (*appsettings.jsauf* und *appSettings. { Environment}. JSON*) und Befehlszeilenoptionen werden als gültige Konfigurations Quellen im Konfigurationsobjekt registriert. Auf die Konfigurations Quellen kann über zugegriffen werden `Configuration[key]` . Eine fortgeschrittenere Methode besteht darin, die Konfigurationsdaten mithilfe des Options Musters an Objekte zu binden. Weitere Informationen zur Konfiguration und zum Options Muster finden Sie unter [Konfiguration in ASP.net Core](/aspnet/core/fundamentals/configuration/) und [options Muster in ASP.net Core](/aspnet/core/fundamentals/configuration/options)bzw.

## <a name="migrate-data-access"></a>Migrieren des Datenzugriffs

Der Datenzugriff ist ein wichtiger Aspekt jeder app. Das Projekt "eShop" speichert Katalog Informationen in einer Datenbank und ruft die Daten mit Entity Framework (EF) 6 ab. Da EF 6 in .net Core 3,0 unterstützt wird, kann es vom Projekt weiterhin verwendet werden.

Für den eShop waren die folgenden EF-bezogenen Änderungen erforderlich:

- In .NET Framework akzeptiert das `DbContext` Objekt eine Zeichenfolge im Format *Name = ConnectionString* und verwendet die Verbindungs Zeichenfolge von `ConfigurationManager.AppSettings[ConnectionString]` , um eine Verbindung herzustellen. In .net Core wird dies nicht unterstützt. Die Verbindungs Zeichenfolge muss angegeben werden.
- Der Zugriff auf die Datenbank war synchron. Obwohl dies funktioniert, kann die Skalierbarkeit beeinträchtigt werden. Diese Logik sollte in ein asynchrones Muster verschoben werden.

Obwohl es nicht die gleiche systemeigene Unterstützung für DataSet-Bindungen gibt, Blazor bietet die c#-Unterstützung in einer Razor-Seite Flexibilität und Leistung. Beispielsweise können Sie Berechnungen ausführen und das Ergebnis anzeigen. Weitere Informationen zu Datenmustern in finden Sie im Blazor Kapitel [Datenzugriff](data.md) .

## <a name="architectural-changes"></a>Änderungen an der Architektur

Schließlich gibt es einige wichtige Unterschiede bei der Architektur, die bei der Migration zu berücksichtigt werden müssen Blazor . Viele dieser Änderungen gelten für alle Elemente, die auf .net Core oder ASP.net Core basieren.

Da Blazor auf .net Core basiert, müssen bei der Unterstützung von .net Core unterstützt werden. Zu den wichtigsten Änderungen gehören das Entfernen der folgenden Features:

- Mehrere AppDomains
- Remoting
- Codezugriffssicherheit (Code Access Security, CAS)
- Sicherheitstransparenz

Weitere Informationen zu Techniken zur Identifizierung der erforderlichen Änderungen für die Unterstützung von unter .net Core finden [Sie unter Portieren von Code aus .NET Framework zu .net Core](../../core/porting/index.md).

ASP.net Core ist eine neue Version von ASP.net und weist einige Änderungen auf, die möglicherweise nicht anfänglich offensichtlich erscheinen. Die Haupt Änderungen lauten:

- Kein Synchronisierungs Kontext. Dies bedeutet, dass es keine `HttpContext.Current` , `Thread.CurrentPrincipal` oder andere statische Accessoren gibt.
- Keine Schatten Kopien
- Keine Anforderungs Warteschlange

Viele Vorgänge in ASP.net Core sind asynchron, wodurch das Laden von e/a-gebundenen Aufgaben vereinfacht wird. Es ist wichtig, niemals mit oder zu `Task.Wait()` blockieren `Task.GetResult()` , wodurch Thread Pool Ressourcen schnell aufgebraucht werden können.

## <a name="migration-conclusion"></a>Schlussfolgerung der Migration

An diesem Punkt haben Sie viele Beispiele dafür gesehen, wie ein Web Forms Projekt in verschoben wird Blazor . Ein vollständiges Beispiel finden Sie im [eshopon Blazor ](https://github.com/dotnet-architecture/eShopOnBlazor) -Projekt.

>[!div class="step-by-step"]
>[Vorherige](security-authentication-authorization.md)
