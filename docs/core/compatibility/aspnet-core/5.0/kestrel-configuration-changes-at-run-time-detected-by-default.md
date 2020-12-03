---
title: 'Breaking Change: Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 2e879f020dd108baa14fa8ff67dee7b948209faf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759201"
---
# <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a>Kestrel: Konfigurationsänderungen zur Laufzeit werden standardmäßig erkannt

Kestrel reagiert nun auf Änderungen, die zur Laufzeit am `Kestrel`-Abschnitt der `IConfiguration`-Instanz des Projekts (z. B. *appsettings.json*) vorgenommen wurden. Weitere Informationen zum Konfigurieren von Kestrel mithilfe von *appsettings.json* finden Sie im *appsettings.json*-Beispiel unter [Endpunktkonfiguration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).

Nach Bedarf bindet Kestrel Endpunkte, hebt die Bindung auf und bindet sie erneut, um auf diese Konfigurationsänderungen zu reagieren.

Weitere Informationen finden Sie unter dem Issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 7

## <a name="old-behavior"></a>Altes Verhalten

Vor ASP.NET Core 5.0 Preview 6 hat Kestrel das Ändern der Konfiguration zur Laufzeit nicht unterstützt.

In ASP.NET Core 5.0 Preview 6 konnten Sie das jetzige Standardverhalten zur Reaktion auf Konfigurationsänderungen zur Laufzeit aktivieren. Zum Aktivieren mussten Sie die Kestrel-Konfiguration manuell binden.

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

## <a name="new-behavior"></a>Neues Verhalten

Kestrel reagiert standardmäßig auf Konfigurationsänderungen zur Laufzeit. Zum Unterstützen dieser Änderung wird `KestrelServerOptions.Configure(IConfiguration, bool)` von <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> standardmäßig mit `reloadOnChange: true` aufgerufen.

## <a name="reason-for-change"></a>Grund für die Änderung

Durch die Änderung sollte die erneute Endpunktkonfiguration zur Laufzeit unterstützt werden, ohne den Server vollständig neu starten zu müssen. Anders als bei einem vollständigen Serverneustart wird die Bindung für unveränderte Endpunkte nicht einmal temporär aufgehoben.

## <a name="recommended-action"></a>Empfohlene Aktion

* Bei den meisten Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel nicht zur Laufzeit geändert wird, hat diese Änderung keine Auswirkung, und es ist keine Aktion erforderlich.
* Bei Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel zur Laufzeit geändert wird und Kestrel darauf reagieren sollte, ist dies nun das Standardverhalten.
* Bei Szenarios, bei denen der Standardkonfigurationsabschnitt von Kestrel zur Laufzeit geändert wird und Kestrel nicht darauf reagieren sollte, können Sie dieses Verhalten wie folgt deaktivieren:

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

**Hinweise:**

Durch diese Änderung wird nicht das Verhalten des Überladens von `KestrelServerOptions.Configure(IConfiguration)` geändert. Hierfür gilt weiterhin das Standardverhalten `reloadOnChange: false`.

Es ist zudem wichtig, sicherzustellen, dass die Konfigurationsquelle das erneute Laden unterstützt. Bei JSON-Quellen wird das erneute Laden konfiguriert, indem `AddJsonFile(path, reloadOnChange: true)` aufgerufen wird. Bei *appsettings.json* und *appsettings.{Umgebung}.json* ist das erneute Laden standardmäßig bereits konfiguriert.

## <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
