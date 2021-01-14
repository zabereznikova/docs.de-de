---
title: Projektstruktur für Blazor apps
description: Erfahren Sie, wie die Projektstrukturen von ASP.net-Web Forms und- Blazor Projekten verglichen werden.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: ba7113c88db728f30812821deaf7c06a80663d1f
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189088"
---
# <a name="project-structure-for-no-locblazor-apps"></a>Projektstruktur für Blazor apps

Trotz ihrer erheblichen Unterschiede in der Projektstruktur werden ASP.net Web Forms und Blazor viele ähnliche Konzepte gemeinsam nutzen. Hier betrachten wir die Struktur eines Blazor Projekts und vergleichen es mit einem ASP.net-Web Forms Projekt.

Um Ihre erste APP zu erstellen Blazor , befolgen Sie die Anweisungen in den [ Blazor Schritten erste Schritte](/aspnet/core/blazor/get-started). Sie können die Anweisungen befolgen, um entweder eine Blazor Server-APP oder eine Blazor WebAssembly in ASP.net Core gehostete-APP zu erstellen. Mit Ausnahme der hostingmodellspezifischen Logik ist der größte Teil des Codes in beiden Projekten identisch.

## <a name="project-file"></a>Projektdatei

Blazor Server-apps sind .net-Projekte. Die Projektdatei für die Blazor Server-APP ist ungefähr so einfach wie möglich:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Die Projektdatei für eine Blazor WebAssembly App ist etwas komplizierter (genaue Versionsnummern können variieren):

```xml
<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly" Version="5.0.0" />
    <PackageReference Include="Microsoft.AspNetCore.Components.WebAssembly.DevServer" Version="5.0.0" PrivateAssets="all" />
    <PackageReference Include="System.Net.Http.Json" Version="5.0.0" />
  </ItemGroup>

</Project>
```

BlazorWebAssemblyProjektziele `Microsoft.NET.Sdk.BlazorWebAssembly` anstelle von `Microsoft.NET.Sdk.Web` SDK, da Sie im Browser auf einer WebAssembly -basierten .NET-Laufzeit ausgeführt werden. Sie können .net nicht in einem Webbrowser installieren, wie auf einem Server oder einem Entwickler Computer. Folglich verweist das Projekt auf das Blazor Framework mit einzelnen Paket verweisen.

Im Vergleich dazu enthält ein Standardmäßiges ASP.net-Web Forms Projekt fast 300 XML-Zeilen in der *csproj* -Datei, von denen die meisten Code-und Inhalts Dateien im Projekt explizit aufgelistet werden. Mit der-Version `.NET 5` von `Blazor Server` und `Blazor WebAssembly` kann eine einheitliche Laufzeit auf einfache Weise gemeinsam genutzt werden.

Obwohl Sie unterstützt werden, sind einzelne Assemblyverweise in .NET-Projekten weniger häufig. Die meisten Projekt Abhängigkeiten werden als nuget-Paket Verweise behandelt. Sie müssen nur auf Paketabhängigkeiten auf oberster Ebene in .NET-Projekten verweisen. Transitive Abhängigkeiten werden automatisch eingeschlossen. Anstatt die *packages.config* Datei zu verwenden, die häufig in ASP.net-Web Forms Projekten für Verweise auf Pakete zu finden ist, werden Paket Verweise der Projektdatei mithilfe des-Elements hinzugefügt `<PackageReference>` .

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Einstiegspunkt

Der Blazor Einstiegspunkt der Server-APP wird in der Datei *Program.cs* definiert, wie Sie in einer Konsolen-App angezeigt werden. Wenn die app ausgeführt wird, erstellt Sie eine Webhost Instanz und führt Sie mithilfe der Standardeinstellungen für Web-Apps aus. Der Webhost verwaltet den Blazor Lebenszyklus der Server-APP und richtet Dienste auf Hostebene ein. Beispiele für derartige Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server. Dieser Code ist größtenteils eine Bausteine und bleibt häufig unverändert.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

BlazorWebAssemblyapps definieren außerdem einen Einstiegspunkt in *Program.cs*. Der Code sieht etwas anders aus. Der Code ähnelt dem Einrichten des App-Hosts, um die gleichen Dienste auf Hostebene für die APP bereitzustellen. Der WebAssembly App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.

Blazor Apps verfügen `Startup` anstelle einer *Global. asax* -Datei über eine-Klasse, um die Start Logik für die APP zu definieren. Die `Startup` -Klasse wird verwendet, um die APP und alle App-spezifischen Dienste zu konfigurieren. In der Blazor Server-APP wird die- `Startup` Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die von Blazor zwischen den Client Browsern und dem Server verwendet wird. In der Blazor WebAssembly App definiert die `Startup` -Klasse die Stamm Komponenten für die APP und wo Sie gerendert werden sollen. Wir werfen einen tieferen Einblick in die- `Startup` Klasse im Abschnitt [App-Start](./app-startup.md) .

## <a name="static-files"></a>Statische Dateien

Im Gegensatz zu ASP.net-Web Forms Projekten können nicht alle Dateien in einem Blazor Projekt als statische Dateien angefordert werden. Nur die Dateien im Ordner " *wwwroot* " sind webadressierbar. Dieser Ordner wird als "Web Root" der APP bezeichnet. Alles außerhalb des webstamms der APP *ist nicht* webadressierbar. Dieses Setup bietet ein zusätzliches Maß an Sicherheit, das eine versehentliche Offenlegung von Projektdateien über das Internet verhindert.

## <a name="configuration"></a>Konfiguration

Die Konfiguration in ASP.net Web Forms-apps wird in der Regel mit einer oder mehreren *web.config* Dateien gehandhabt. Blazor Apps verfügen in der Regel nicht über *web.config* Dateien. Wenn dies der Fall ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn Sie auf IIS gehostet wird. Stattdessen Blazor verwenden Server-Apps die ASP.net Core Konfigurations Abstraktionen ( Blazor WebAssembly apps unterstützen derzeit nicht dieselben Konfigurations Abstraktionen, aber dies kann ein in der Zukunft hinzugefügtes Feature sein). Beispielsweise werden in der Standard Blazor Server-App einige Einstellungen in *appsettings.js* gespeichert.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

Weitere Informationen zur Konfiguration finden Sie unter ASP.net Core-Projekte im Abschnitt " [Konfiguration](./config.md) ".

## <a name="razor-components"></a>Razor-Komponenten

Die meisten Dateien in Blazor Projekten sind *Razor* -Dateien. Razor ist eine Vorlagen Sprache, die auf HTML und c# basiert und zum dynamischen Generieren der Webbenutzer Oberfläche verwendet wird. Die *Razor* -Dateien definieren Komponenten, aus denen die Benutzeroberfläche der APP besteht. Zum größten Teil sind die Komponenten sowohl für den Blazor Server als auch für die Blazor WebAssembly apps identisch. Komponenten in entsprechen Blazor den Benutzer Steuerelementen in ASP.net-Web Forms.

Jede Razor-Komponenten Datei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird. Die generierte-Klasse erfasst den Zustand der Komponente, die Renderinglogik, Lebenszyklus Methoden, Ereignishandler und andere Logik. Wir werden uns mit der Erstellung von Komponenten im Abschnitt [Erstellen wiederverwendbarer UI- Blazor Komponenten mit](./components.md) beschäftigen.

Die *_Imports. Razor* -Dateien sind keine Razor-Komponenten Dateien. Stattdessen definieren Sie einen Satz von Razor-Direktiven, die in andere *Razor* -Dateien im selben Ordner und in den zugehörigen Unterordnern importiert werden. Beispielsweise ist eine *_Imports. Razor* -Datei ein herkömmliches Verfahren zum Hinzufügen `using` von Direktiven für häufig verwendete Namespaces:

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>Seiten

Wo befinden sich die Seiten in den Blazor apps? Blazor definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. b. die *aspx* -Dateien in ASP.net-Web Forms-apps. Stattdessen werden Seiten durch Zuweisen von Routen zu Komponenten definiert. Eine Route wird in der Regel mithilfe der `@page` Razor-Direktive zugewiesen. Die `Counter` in der Datei *pages/Counter. Razor* erstellte Komponente definiert z. b. die folgende Route:

```razor
@page "/counter"
```

Das Routing in Blazor erfolgt auf Clientseite, nicht auf dem Server. Wenn der Benutzer im Browser navigiert, Blazor fängt die Navigation ab und rendert die Komponente dann mit der passenden Route.

Die Komponenten Routen werden zurzeit nicht durch den Datei Speicherort der Komponente abgeleitet, z. b. mit *aspx* -Seiten. Diese Funktion kann in Zukunft hinzugefügt werden. Jede Route muss explizit für die Komponente angegeben werden. Das Speichern von Routing fähigen Komponenten in einem *Seiten* Ordner hat keine besondere Bedeutung und ist rein eine Konvention.

Weitere Details finden Sie im Blazor Abschnitt " [Seiten, Routing und Layouts](./pages-routing-layouts.md) " unter Routing in.

## <a name="layout"></a>Layout

In ASP.net Web Forms-apps wird ein gängiges Seitenlayout mithilfe von Masterseiten (*Site. Master*) behandelt. In- Blazor apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout. Razor*) behandelt. Layoutkomponenten werden im Abschnitt "Seite" [, "Routing" und "Layouts](./pages-routing-layouts.md) " ausführlicher erläutert.

## <a name="bootstrap-no-locblazor"></a>Bootstrap Blazor

Zum Bootstrapping Blazor muss die app folgende Aktionen ausführen:

- Geben Sie an, wo auf der Seite die Stamm Komponente (*app. Razor*) gerendert werden soll.
- Fügen Sie das entsprechende Blazor Framework-Skript hinzu.

In der Blazor Server-APP wird die Hostseite der Stamm Komponente in der Datei *_Host. cshtml* definiert. Diese Datei definiert eine Razor-Seite und keine Komponente. Razor Pages verwenden Sie Razor-Syntax, um eine Server adressierbare Seite zu definieren, ähnlich wie eine *aspx* -Seite. Die- `Html.RenderComponentAsync<TComponent>(RenderMode)` Methode wird verwendet, um zu definieren, wo eine Komponente auf Stamm Ebene gerendert werden soll. Die- `RenderMode` Option gibt die Art an, in der die Komponente gerendert werden soll. In der folgenden Tabelle werden die unterstützten `RenderMode` Optionen beschrieben.

|Option                        |Beschreibung       |
|------------------------------|------------------|
|`RenderMode.Server`           |Wird interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde|
|`RenderMode.ServerPrerendered`|Zuerst vorab und dann interaktiv gerendert|
|`RenderMode.Static`           |Als statischer Inhalt gerendert|

Der Skript Verweis auf *_framework/blazor.server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich mit allen Benutzerinteraktionen und Aktualisierungen der Benutzeroberfläche.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

In der Blazor WebAssembly App ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/index.html*. Das- `<div>` Element mit der ID "" `app` wird verwendet, um anzugeben, wo die Stamm Komponente gerendert werden soll.

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/app.css" rel="stylesheet" />
    <link href="blazor-web.styles.css" rel="stylesheet" />
</head>

<body>
    <div id="app">Loading...</div>

    <div id="blazor-error-ui">
        An unhandled error has occurred.
        <a href="" class="reload">Reload</a>
        <a class="dismiss">🗙</a>
    </div>
    <script src="_framework/blazor.webassembly.js"></script>
</body>

</html>

```

Die Stamm Komponente zum Rendering wird in der-Methode der APP angegeben `Program.Main` und bietet die Flexibilität, Dienste über die Abhängigkeitsinjektion zu registrieren. Weitere Informationen finden Sie unter [ASP.net Core- Blazor Abhängigkeitsinjektion](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).

```csharp
public class Program
{
    public static async Task Main(string[] args)
    {
        var builder = WebAssemblyHostBuilder.CreateDefault(args);
        builder.RootComponents.Add<App>("#app");

        ....
        ....
    }
}
```

## <a name="build-output"></a>Erstellen der Ausgabe

Wenn ein Blazor Projekt erstellt wird, werden alle Razor-Komponenten-und Code Dateien in eine einzelne Assembly kompiliert. Im Gegensatz zu ASP.net-Web Forms Projekten Blazor unterstützt keine Lauf Zeit Kompilierung der UI-Logik.

## <a name="run-the-app"></a>Ausführen der App

Um die Blazor Server-App auszuführen, drücken Sie `F5` in Visual Studio. Blazor Apps unterstützen keine Lauf Zeit Kompilierung. Um die Ergebnisse von Code-und Komponenten Markup Änderungen anzuzeigen, müssen Sie die APP mit dem angefügten Debugger neu erstellen und neu starten. Wenn Sie ausführen, ohne dass der Debugger angefügt `Ctrl+F5` ist (), beobachtet Visual Studio die Dateiänderungen und startet die APP neu, sobald Änderungen vorgenommen werden. Sie müssen den Browser manuell aktualisieren, wenn Änderungen vorgenommen werden.

Blazor WebAssembly Wählen Sie einen der folgenden Ansätze aus, um die APP auszuführen:

- Führen Sie das Client Projekt direkt mit dem Development Server aus.
- Führen Sie das Server Projekt aus, wenn die APP mit ASP.net Core gehostet wird.

BlazorWebAssemblyApps können sowohl in Browser als auch in Visual Studio debuggt werden. Weitere Informationen finden Sie in der [Debug-ASP.net Core Blazor WebAssembly ](/aspnet/core/blazor/debug) .

>[!div class="step-by-step"]
>[Zurück](hosting-models.md)
>[Weiter](app-startup.md)
