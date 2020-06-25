---
ms.openlocfilehash: d00b8ecaa61b358e062d85a2b68ca8a95cada442
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803234"
---
### <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="e66a7-101">Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt</span><span class="sxs-lookup"><span data-stu-id="e66a7-101">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="e66a7-102">Kestrel reagiert nun auf Änderungen, die zur Laufzeit am `Kestrel`-Abschnitt der `IConfiguration`-Instanz des Projekts (z. B. *appsettings.json*) vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="e66a7-102">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="e66a7-103">Weitere Informationen zum Konfigurieren von Kestrel mithilfe von *appsettings.json* finden Sie im *appsettings.json*-Beispiel unter [Endpunktkonfiguration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span><span class="sxs-lookup"><span data-stu-id="e66a7-103">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="e66a7-104">Nach Bedarf bindet Kestrel Endpunkte, hebt die Bindung auf und bindet sie erneut, um auf diese Konfigurationsänderungen zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="e66a7-104">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="e66a7-105">Weitere Informationen finden Sie unter dem Issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span><span class="sxs-lookup"><span data-stu-id="e66a7-105">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e66a7-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="e66a7-106">Version introduced</span></span>

<span data-ttu-id="e66a7-107">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="e66a7-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e66a7-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="e66a7-108">Old behavior</span></span>

<span data-ttu-id="e66a7-109">Vor ASP.NET Core 5.0 Preview 6 hat Kestrel das Ändern der Konfiguration zur Laufzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e66a7-109">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="e66a7-110">In ASP.NET Core 5.0 Preview 6 konnten Sie das jetzige Standardverhalten zur Reaktion auf Konfigurationsänderungen zur Laufzeit aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e66a7-110">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="e66a7-111">Zum Aktivieren mussten Sie die Kestrel-Konfiguration manuell binden.</span><span class="sxs-lookup"><span data-stu-id="e66a7-111">Opting in required binding Kestrel's configuration manually:</span></span>

```csharp
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args) =>
        CreateHostBuilder(args).Build().Run();

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

#### <a name="new-behavior"></a><span data-ttu-id="e66a7-112">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="e66a7-112">New behavior</span></span>

<span data-ttu-id="e66a7-113">Kestrel reagiert standardmäßig auf Konfigurationsänderungen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="e66a7-113">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="e66a7-114">Zum Unterstützen dieser Änderung wird `KestrelServerOptions.Configure(IConfiguration, bool)` von <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> standardmäßig mit `reloadOnChange: true` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e66a7-114">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e66a7-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="e66a7-115">Reason for change</span></span>

<span data-ttu-id="e66a7-116">Durch die Änderung sollte die erneute Endpunktkonfiguration zur Laufzeit unterstützt werden, ohne den Server vollständig neu starten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e66a7-116">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="e66a7-117">Anders als bei einem vollständigen Serverneustart wird die Bindung für unveränderte Endpunkte nicht einmal temporär aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="e66a7-117">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e66a7-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="e66a7-118">Recommended action</span></span>

* <span data-ttu-id="e66a7-119">Bei den meisten Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel nicht zur Laufzeit geändert wird, hat diese Änderung keine Auswirkung, und es ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e66a7-119">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="e66a7-120">Bei Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel zur Laufzeit geändert wird und Kestrel darauf reagieren sollte, ist dies nun das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="e66a7-120">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="e66a7-121">Bei Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel zur Laufzeit geändert wird und Kestrel nicht darauf reagieren sollte, können Sie dieses Verhalten wie folgt deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="e66a7-121">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="e66a7-122">**Hinweise:**</span><span class="sxs-lookup"><span data-stu-id="e66a7-122">**Notes:**</span></span>

<span data-ttu-id="e66a7-123">Durch diese Änderung wird nicht das Verhalten des Überladens von `KestrelServerOptions.Configure(IConfiguration)` geändert. Hierfür gilt weiterhin das Standardverhalten `reloadOnChange: false`.</span><span class="sxs-lookup"><span data-stu-id="e66a7-123">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="e66a7-124">Es ist zudem wichtig, sicherzustellen, dass die Konfigurationsquelle das erneute Laden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e66a7-124">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="e66a7-125">Bei JSON-Quellen wird das erneute Laden konfiguriert, indem `AddJsonFile(path, reloadOnChange: true)` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e66a7-125">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="e66a7-126">Bei *appsettings.json* und *appsettings.{Umgebung}.json* ist das erneute Laden standardmäßig bereits konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e66a7-126">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

#### <a name="category"></a><span data-ttu-id="e66a7-127">Kategorie</span><span class="sxs-lookup"><span data-stu-id="e66a7-127">Category</span></span>

<span data-ttu-id="e66a7-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e66a7-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e66a7-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e66a7-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
