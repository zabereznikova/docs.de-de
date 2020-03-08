---
title: Projektstruktur für blazor-apps
description: Erfahren Sie, wie die Projektstrukturen von ASP.net Web Forms-und blazor-Projekten verglichen werden.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675004"
---
# <a name="project-structure-for-blazor-apps"></a>Projektstruktur für blazor-apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Trotz ihrer erheblichen Unterschiede in der Projektstruktur haben ASP.net Web Forms und blazor viele ähnliche Konzepte gemeinsam. Hier betrachten wir die Struktur eines blazor-Projekts und vergleichen es mit einem ASP.net-Web Forms Projekt.

Um Ihre erste blazor-APP zu erstellen, befolgen Sie die Anweisungen unter erste [Schritte mit blazor](/aspnet/core/blazor/get-started). Sie können die Anweisungen befolgen, um entweder eine blazor-Server-APP oder eine in ASP.net Core gehostete blazor Webassembly-APP zu erstellen. Mit Ausnahme der hostingmodellspezifischen Logik ist der größte Teil des Codes in beiden Projekten identisch.

## <a name="project-file"></a>Projektdatei

Blazor-Server-apps sind .net Core-Projekte. Die Projektdatei für die blazor-Server-APP ist ungefähr so einfach wie möglich:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Die Projektdatei für eine blazor Webassembly-App sieht etwas mehr an (genaue Versionsnummern können variieren):

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

Blazor-webassemblyprojekte verwenden .NET Standard anstelle von .net Core, da Sie im Browser auf einer webassemblybasierten .NET-Laufzeit ausgeführt werden. Sie können .net nicht in einem Webbrowser installieren, wie auf einem Server oder einem Entwickler Computer. Folglich verweist das Projekt auf das blazor-Framework mit einzelnen Paket verweisen.

Im Vergleich dazu enthält ein Standardmäßiges ASP.net-Web Forms Projekt fast 300 XML-Zeilen in der *csproj* -Datei, von denen die meisten Code-und Inhalts Dateien im Projekt explizit aufgelistet werden. Viele der Vereinfachungen in den .net Core-und .NET Standard basierten Projekten stammen aus den Standardzielen und-Eigenschaften, die durch den Verweis auf das `Microsoft.NET.Sdk.Web` SDK importiert werden. Dies wird häufig auch als einfaches WebSDK bezeichnet. Das Web-SDK umfasst Platzhalter und andere Bequemlichkeiten, die die Einbindung von Code und Inhalts Dateien im Projekt vereinfachen. Sie müssen die Dateien nicht explizit auflisten. Wenn .net Core als Zielversion verwendet wird, fügt das Web-SDK auch frameworkverweise sowohl auf die .net Core-als auch auf die ASP.net Core frei Die Frameworks sind über den Knoten **Abhängigkeiten** > **Frameworks** im **Projektmappen-Explorer** Fenster sichtbar. Die freigegebenen Frameworks sind Assemblys, die bei der Installation von .net Core auf dem Computer installiert wurden.

Obwohl Sie unterstützt werden, sind einzelne Assemblyverweise in .net Core-Projekten weniger häufig. Die meisten Projekt Abhängigkeiten werden als nuget-Paket Verweise behandelt. In .net Core-Projekten müssen Sie nur auf Paketabhängigkeiten der obersten Ebene verweisen. Transitive Abhängigkeiten werden automatisch eingeschlossen. Anstatt die Datei " *Packages. config* " zu verwenden, die in ASP.net-Web Forms Projekten für Verweise auf Pakete gefunden wird, werden Paket Verweise der Projektdatei mithilfe des `<PackageReference>`-Elements hinzugefügt.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Einstiegspunkt

Der Einstiegspunkt der blazor-Server-APP wird in der Datei *Program.cs* definiert, wie Sie in einer Konsolen-App angezeigt werden. Wenn die app ausgeführt wird, erstellt Sie eine Webhost Instanz und führt Sie mithilfe der Standardeinstellungen für Web-Apps aus. Der Webhost verwaltet den Lebenszyklus der blazor-Server-APP und richtet Dienste auf Hostebene ein. Beispiele für derartige Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server. Dieser Code ist größtenteils eine Bausteine und bleibt häufig unverändert.

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

Blazor Webassembly-apps definieren außerdem einen Einstiegspunkt in *Program.cs*. Der Code sieht etwas anders aus. Der Code ähnelt dem Einrichten des App-Hosts, um die gleichen Dienste auf Hostebene für die APP bereitzustellen. Der Webassembly-App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.

Blazor-apps verfügen über eine `Startup`-Klasse anstelle einer *Global. asax* -Datei, um die Start Logik für die APP zu definieren. Die `Startup`-Klasse wird verwendet, um die APP und alle App-spezifischen Dienste zu konfigurieren. In der blazor-Server-APP wird die `Startup`-Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die von blazor zwischen den Client Browsern und dem Server verwendet wird. In der blazor Webassembly-App definiert die `Startup`-Klasse die Stamm Komponenten für die APP und wo Sie gerendert werden sollen. Wir werfen einen tieferen Einblick in die `Startup`-Klasse im Abschnitt [App-Start](./app-startup.md) .

## <a name="static-files"></a>Statische Dateien

Im Gegensatz zu ASP.net-Web Forms Projekten können nicht alle Dateien in einem blazor-Projekt als statische Dateien angefordert werden. Nur die Dateien im Ordner " *wwwroot* " sind webadressierbar. Dieser Ordner wird als "Web Root" der APP bezeichnet. Alles außerhalb des webstamms der APP *ist nicht* webadressierbar. Dieses Setup bietet ein zusätzliches Maß an Sicherheit, das eine versehentliche Offenlegung von Projektdateien über das Internet verhindert.

## <a name="configuration"></a>Konfiguration

Die Konfiguration in ASP.net Web Forms-apps wird in der Regel mit einer oder mehreren *Web. config* -Dateien verarbeitet. Blazor-apps verfügen in der Regel nicht über *Web. config* -Dateien. Wenn dies der Fall ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn Sie auf IIS gehostet wird. Stattdessen verwenden blazor-Server-Apps die ASP.net Core Konfigurations Abstraktionen (blazor-webassemblyanwendungen unterstützen derzeit nicht dieselben Konfigurations Abstraktionen, aber dies kann ein in der Zukunft hinzugefügtes Feature sein). Beispielsweise speichert die Standard-App für den blazor-Server einige Einstellungen in *appSettings. JSON*.

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

Die meisten Dateien in blazor-Projekten sind *Razor* -Dateien. Razor ist eine Vorlagen Sprache, die auf HTML basiert C# und zum dynamischen Generieren der Webbenutzer Oberfläche verwendet wird. Die *Razor* -Dateien definieren Komponenten, aus denen die Benutzeroberfläche der APP besteht. Größtenteils sind die Komponenten sowohl für den blazor-Server als auch für die blazor Webassembly-apps identisch. Komponenten in blazor sind analog zu Benutzer Steuerelementen in ASP.net-Web Forms.

Jede Razor-Komponenten Datei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird. Die generierte-Klasse erfasst den Zustand der Komponente, die Renderinglogik, Lebenszyklus Methoden, Ereignishandler und andere Logik. Wir werden uns mit der Erstellung von Komponenten im Abschnitt [Erstellen wiederverwendbarer UI-Komponenten mit blazor](./components.md) befassen.

Die *_Imports. Razor* -Dateien sind keine Razor-Komponenten Dateien. Stattdessen definieren Sie einen Satz von Razor-Direktiven, die in andere *Razor* -Dateien im selben Ordner und in den zugehörigen Unterordnern importiert werden. Beispielsweise ist eine *_Imports. Razor* -Datei ein herkömmliches Verfahren zum Hinzufügen von `using`-Anweisungen für häufig verwendete Namespaces:

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

Wo befinden sich die Seiten in den blazor-apps? Blazor definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. b. die *aspx* -Dateien in ASP.net-Web Forms-apps. Stattdessen werden Seiten durch Zuweisen von Routen zu Komponenten definiert. Eine Route wird in der Regel mithilfe der `@page` Razor-Direktive zugewiesen. Beispielsweise definiert die `Counter` Komponente, die in der Datei *pages/Counter. Razor* erstellt wurde, die folgende Route:

```razor
@page "/counter"
```

Das Routing in blazor erfolgt auf Clientseite, nicht auf dem Server. Wenn der Benutzer im Browser navigiert, fängt blazor die Navigation ab und rendert die Komponente dann mit der passenden Route.

Die Komponenten Routen werden zurzeit nicht durch den Datei Speicherort der Komponente abgeleitet, z. b. mit *aspx* -Seiten. Diese Funktion kann in Zukunft hinzugefügt werden. Jede Route muss explizit für die Komponente angegeben werden. Das Speichern von Routing fähigen Komponenten in einem *Seiten* Ordner hat keine besondere Bedeutung und ist rein eine Konvention.

Weitere Informationen finden Sie im Abschnitt " [Seiten, Routing und Layouts](./pages-routing-layouts.md) " im Abschnitt "Routing in blazor" ausführlicher.

## <a name="layout"></a>Layout

In ASP.net Web Forms-apps wird das allgemeine Seitenlayout mithilfe von Masterseiten (*Site. Master*) behandelt. In blazor-apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout. Razor*) behandelt. Layoutkomponenten werden im Abschnitt "Seite" [, "Routing" und "Layouts](./pages-routing-layouts.md) " ausführlicher erläutert.

## <a name="bootstrap-blazor"></a>Bootstrap-blazor

Zum Bootstrap von blazor muss die app folgende Aktionen ausführen:

- Geben Sie an, wo auf der Seite die Stamm Komponente (*app. Razor*) gerendert werden soll.
- Fügen Sie das entsprechende blazor-Framework-Skript hinzu.

In der blazor-Server-APP wird die Hostseite der Stamm Komponente in der Datei *_Host. cshtml* definiert. Diese Datei definiert eine Razor-Seite und keine Komponente. Razor Pages verwenden Sie Razor-Syntax, um eine Server adressierbare Seite zu definieren, ähnlich wie eine *aspx* -Seite. Die `Html.RenderComponentAsync<TComponent>(RenderMode)`-Methode wird verwendet, um zu definieren, wo eine Komponente auf Stamm Ebene gerendert werden soll. Die Option `RenderMode` gibt an, wie die Komponente gerendert werden soll. In der folgenden Tabelle werden die unterstützten `RenderMode` Optionen beschrieben.

|Option                        |BESCHREIBUNG       |
|------------------------------|------------------|
|`RenderMode.Server`           |Wird interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde|
|`RenderMode.ServerPrerendered`|Zuerst vorab und dann interaktiv gerendert|
|`RenderMode.Static`           |Als statischer Inhalt gerendert|

Der Skript Verweis auf *_framework/blazor.Server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich mit allen Benutzerinteraktionen und Aktualisierungen der Benutzeroberfläche.

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

In der blazor Webassembly-APP ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/Index.html*. Das `<app>`-Element wird verwendet, um anzugeben, wo die Stamm Komponente gerendert werden soll.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

Die zu rendernde bestimmte Komponente wird in der `Startup.Configure`-Methode der APP mit einer entsprechenden CSS-Auswahl konfiguriert, die angibt, wo die Komponente gerendert werden soll.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>Erstellen der Ausgabe

Wenn ein blazor-Projekt erstellt wird, werden alle Razor-Komponenten-und Code Dateien in eine einzelne Assembly kompiliert. Im Gegensatz zu ASP.net-Web Forms Projekten unterstützt blazor keine Lauf Zeit Kompilierung der UI-Logik.

## <a name="run-the-app"></a>Ausführen der App

Um die blazor-Server-App auszuführen, drücken Sie in Visual Studio `F5`. Blazor-apps unterstützen keine Lauf Zeit Kompilierung. Um die Ergebnisse von Code-und Komponenten Markup Änderungen anzuzeigen, müssen Sie die APP mit dem angefügten Debugger neu erstellen und neu starten. Wenn Sie ausführen, ohne dass der Debugger angefügt ist (`Ctrl+F5`), beobachtet Visual Studio die Dateiänderungen und startet die APP neu, sobald Änderungen vorgenommen werden. Sie müssen den Browser manuell aktualisieren, wenn Änderungen vorgenommen werden.

Wählen Sie zum Ausführen der blazor Webassembly-APP einen der folgenden Vorgehensweisen aus:

- Führen Sie das Client Projekt direkt mit dem Development Server aus.
- Führen Sie das Server Projekt aus, wenn die APP mit ASP.net Core gehostet wird.

Blazor Webassembly-apps unterstützen das Debuggen mit Visual Studio nicht. Verwenden Sie `Ctrl+F5` anstelle von `F5`, um die APP auszuführen. Stattdessen können Sie blazor-webassemblyanwendungen direkt im Browser Debuggen. Weitere Informationen finden Sie unter [Debug ASP.net Core blazor](/aspnet/core/blazor/debug) .

>[!div class="step-by-step"]
>[Zurück](hosting-models.md)
>[Weiter](app-startup.md)
