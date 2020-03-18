---
title: Projektstruktur für Blazor-Apps
description: Erfahren Sie, wie die Projektstrukturen von ASP.NET Web Forms- und Blazor-Projekten verglichen werden.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401742"
---
# <a name="project-structure-for-blazor-apps"></a>Projektstruktur für Blazor-Apps

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Trotz ihrer erheblichen Unterschiede in der Projektstruktur teilen ASP.NET Web Forms und Blazor viele ähnliche Konzepte. Hier betrachten wir die Struktur eines Blazor-Projekts und vergleichen es mit einem ASP.NET Web Forms-Projekt.

Um Ihre erste Blazor-App zu erstellen, befolgen Sie die Anweisungen in den [Blazor-Schritte](/aspnet/core/blazor/get-started)für die ersten Schritte . Sie können den Anweisungen folgen, um entweder eine Blazor Server-App oder eine Blazor WebAssembly-App zu erstellen, die in ASP.NET Core gehostet wird. Mit Ausnahme der modellspezifischen Hostinglogik ist der größte Teil des Codes in beiden Projekten identisch.

## <a name="project-file"></a>Projektdatei

Blazor Server-Apps sind .NET Core-Projekte. Die Projektdatei für die Blazor Server App ist ungefähr so einfach wie möglich:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Die Projektdatei für eine Blazor WebAssembly App sieht etwas stärker involviert aus (genaue Versionsnummern können variieren):

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

Blazor WebAssembly-Projekte zielen auf .NET Standard anstelle von .NET Core ab, da sie im Browser auf einer WebAssembly-basierten .NET-Laufzeit ausgeführt werden. Sie können .NET nicht wie auf einem Server oder Entwicklercomputer in einem Webbrowser installieren. Folglich verweist das Projekt auf das Blazor-Framework unter Verwendung einzelner Paketreferenzen.

Im Vergleich dazu enthält ein Standardprojekt ASP.NET Web Forms fast 300 XML-Zeilen in seiner *.csproj-Datei,* von denen die meisten explizit die verschiedenen Code- und Inhaltsdateien im Projekt auflisten. Viele der Vereinfachungen in .NET Core- und .NET Standard-basierten Projekten stammen aus den `Microsoft.NET.Sdk.Web` Standardzielen und Eigenschaften, die durch Verweisen auf das SDK importiert werden, das häufig als einfach als Web SDK bezeichnet wird. Das Web SDK enthält Platzhalter und andere Annehmlichkeiten, die die Aufnahme von Code und Inhaltsdateien in das Projekt vereinfachen. Sie müssen die Dateien nicht explizit auflisten. Bei der Ausrichtung auf .NET Core fügt das Web SDK auch Frameworkverweise sowohl zu den freigegebenen .NET Core- als auch zu ASP.NET Core-Frameworks hinzu. Die Frameworks sind über den Knoten **Dependencies** > **Frameworks** im **Projektmappen-Explorer-Fenster** sichtbar. Die freigegebenen Frameworks sind Auflistungen von Assemblys, die beim Installieren von .NET Core auf dem Computer installiert wurden.

Obwohl sie unterstützt werden, sind einzelne Assemblyverweise in .NET Core-Projekten seltener. Die meisten Projektabhängigkeiten werden als NuGet-Paketverweise behandelt. Sie müssen nur auf Paketabhängigkeiten der obersten Ebene in .NET Core-Projekten verweisen. Transitive Abhängigkeiten werden automatisch eingeschlossen. Anstatt die *Datei packages.config* zu verwenden, die häufig in ASP.NET Web Forms-Projekten `<PackageReference>` gefunden wird, um auf Pakete zu verweisen, werden der Projektdatei mithilfe des Elements Paketverweise hinzugefügt.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Einstiegspunkt

Der Einstiegspunkt der Blazor Server-App ist in der *Program.cs-Datei* definiert, wie Sie in einer Konsolen-App sehen würden. Wenn die App ausgeführt wird, erstellt und führt sie eine Webhostinstanz aus, die für Web-Apps spezifische Standardeinstellungen verwendet. Der Webhost verwaltet den Lebenszyklus der Blazor Server-App und richtet Dienste auf Hostebene ein. Beispiele für solche Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server. Dieser Code ist meist Boilerplate und wird oft unverändert gelassen.

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

Blazor WebAssembly-Apps definieren auch einen Einstiegspunkt in *Program.cs*. Der Code sieht etwas anders aus. Der Code ist insofern ähnlich, als der App-Host so eingerichtet wird, dass er der App dieselben Dienste auf Hostebene zur Verfügung stellt. Der WebAssembly-App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.

Blazor-Apps `Startup` haben eine Klasse anstelle einer *Global.asax-Datei,* um die Startlogik für die App zu definieren. Die `Startup` Klasse wird verwendet, um die App und alle app-spezifischen Dienste zu konfigurieren. In der Blazor Server-App wird die `Startup` Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die blazor zwischen den Clientbrowsern und dem Server verwendet. In der Blazor WebAssembly-App definiert die `Startup` Klasse die Stammkomponenten für die App und deren Renderung. Wir werfen einen tieferen `Startup` Blick auf die Klasse im [App-Startabschnitt.](./app-startup.md)

## <a name="static-files"></a>Statische Dateien

Im Gegensatz zu ASP.NET Web Forms-Projekten können nicht alle Dateien in einem Blazor-Projekt als statische Dateien angefordert werden. Nur die Dateien im *Ordner wwwroot* sind webadressierbar. Dieser Ordner wird auf den "Web-Stamm" der App verwiesen. Alles außerhalb des Web-Roots der App *ist nicht* webadressierbar. Dieses Setup bietet eine zusätzliche Sicherheitsstufe, die verhindert, dass Projektdateien versehentlich über das Web verfügbar sind.

## <a name="configuration"></a>Konfiguration

Die Konfiguration in ASP.NET Web Forms-Apps wird in der Regel mit einer oder mehreren *web.config-Dateien* behandelt. Blazor-Apps haben in der Regel keine *web.config-Dateien.* Wenn dies der Zeitpunkt ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn sie auf IIS gehostet wird. Stattdessen verwenden Blazor Server-Apps die ASP.NET Core-Konfigurationsabstraktionen (Blazor WebAssembly-Apps unterstützen derzeit nicht die gleichen Konfigurationsabstraktionen, aber dies kann ein Feature sein, das in der Zukunft hinzugefügt wird). Die standardmäßige Blazor Server-App speichert beispielsweise einige Einstellungen in *appsettings.json*.

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

Weitere Informationen zur Konfiguration in ASP.NET Core-Projekten finden Sie im Abschnitt [Konfiguration.](./config.md)

## <a name="razor-components"></a>Razor-Komponenten

Die meisten Dateien in Blazor-Projekten sind *.razor-Dateien.* Razor ist eine Vorlagensprache, die auf HTML und C- basiert und zum dynamischen Generieren der Web-UI verwendet wird. Die *.razor-Dateien* definieren Komponenten, aus denen die Benutzeroberfläche der App besteht. Die Komponenten sind größtenteils sowohl für die Blazor Server- als auch für die Blazor WebAssembly-Apps identisch. Komponenten in Blazor sind analog zu Benutzersteuerelementen in ASP.NET Web Forms.

Jede Razor-Komponentendatei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird. Die generierte Klasse erfasst den Status der Komponente, die Renderinglogik, Lebenszyklusmethoden, Ereignishandler und andere Logik. Wir werden uns mit dem Erstellen von Komponenten in den Komponenten [für wiederverwendbare Benutzeroberflächen erstellen mit Blazor](./components.md) befassen.

Die *_Imports.razor-Dateien* sind keine Razor-Komponentendateien. Stattdessen definieren sie eine Reihe von Razor-Direktiven, die in andere *.razor-Dateien* innerhalb desselben Ordners und in seinen Unterordnern importiert werden sollen. Eine *_Imports.razor-Datei* ist z. B. eine herkömmliche Möglichkeit, Anweisungen für häufig verwendete Namespaces hinzuzufügen: `using`

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

Wo sind die Seiten in den Blazor-Apps? Blazor definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. B. die *ASPX-Dateien* in ASP.NET Web Forms-Apps. Stattdessen werden Seiten definiert, indem Routen Komponenten zugewiesen werden. Eine Route wird in `@page` der Regel mithilfe der Razor-Direktive zugewiesen. Die `Counter` in der Datei *Pages/Counter.razor* erstellte Komponente definiert beispielsweise die folgende Route:

```razor
@page "/counter"
```

Routing in Blazor wird clientseitig und nicht auf dem Server behandelt. Während der Benutzer im Browser navigiert, fängt Blazor die Navigation ab und rendert die Komponente dann mit der passenden Route.

Die Komponentenrouten werden derzeit nicht durch den Dateispeicherort der Komponente abgeleitet, wie sie bei *ASPX-Seiten* der Datei sind. Diese Funktion kann in Zukunft hinzugefügt werden. Jede Route muss explizit für die Komponente angegeben werden. Das Speichern von Routingkomponenten in einem *Pages-Ordner* hat keine besondere Bedeutung und ist eine reine Konvention.

Im Abschnitt [Seiten, Routing und Layouts](./pages-routing-layouts.md) wird das Routing in Blazor genauer erläutert.

## <a name="layout"></a>Layout

In ASP.NET Web Forms-Apps wird das allgemeine Seitenlayout mithilfe von Masterseiten (*Site.Master*) behandelt. In Blazor-Apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout.razor*) behandelt. Layoutkomponenten werden im Abschnitt [Seite, Routing und Layouts](./pages-routing-layouts.md) ausführlicher behandelt.

## <a name="bootstrap-blazor"></a>Bootstrap Blazor

Um Blazor zu booten, muss die App:

- Geben Sie an, wo auf der Seite die Stammkomponente (*App.Razor*) gerendert werden soll.
- Fügen Sie das entsprechende Blazor-Frameworkskript hinzu.

In der Blazor Server-App wird die Hostseite der Stammkomponente in der Datei *_Host.cshtml* definiert. Diese Datei definiert eine Razor-Seite, keine Komponente. Razor Pages verwenden die Razor-Syntax, um eine serveradressierbare Seite zu definieren, die einer *ASPX-Seite* sehr ähnlich ist. Die `Html.RenderComponentAsync<TComponent>(RenderMode)` Methode wird verwendet, um zu definieren, wo eine Komponente auf Stammebene gerendert werden soll. Die `RenderMode` Option gibt die Art und Weise an, in der die Komponente gerendert werden soll. In der folgenden Tabelle `RenderMode` werden die unterstützten Optionen beschrieben.

|Option                        |Beschreibung       |
|------------------------------|------------------|
|`RenderMode.Server`           |Interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde|
|`RenderMode.ServerPrerendered`|Erst vorgerendert und dann interaktiv gerendert|
|`RenderMode.Static`           |Als statischer Inhalt gerendert|

Der Skriptverweis auf *_framework/blazor.server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich dann mit allen Benutzerinteraktionen und UI-Updates.

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

In der Blazor WebAssembly-App ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/index.html*. Das `<app>` Element wird verwendet, um anzugeben, wo die Stammkomponente gerendert werden soll.

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

Die zu rendernde Komponente wird in `Startup.Configure` der App-Methode mit einem entsprechenden CSS-Selektor konfiguriert, der angibt, wo die Komponente gerendert werden soll.

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

Wenn ein Blazor-Projekt erstellt wird, werden alle Razor-Komponenten- und Codedateien in einer einzigen Assembly kompiliert. Im Gegensatz zu ASP.NET Web Forms-Projekten unterstützt Blazor die Laufzeitkompilierung der UI-Logik nicht.

## <a name="run-the-app"></a>Ausführen der App

Um die Blazor Server-App auszuführen, drücken Sie `F5` in Visual Studio. Blazor-Apps unterstützen keine Laufzeitkompilierung. Um die Ergebnisse von Code- und Komponentenmarkupänderungen anzuzeigen, erstellen Sie die App neu und starten Sie sie neu, wobei der Debugger angefügt ist. Wenn Sie ohne den angefügten Debugger (`Ctrl+F5`) ausgeführt werden, überwacht Visual Studio Dateiänderungen und startet die App neu, wenn Änderungen vorgenommen werden. Sie aktualisieren den Browser manuell, wenn Änderungen vorgenommen werden.

Um die Blazor WebAssembly-App auszuführen, wählen Sie einen der folgenden Ansätze aus:

- Führen Sie das Clientprojekt direkt über den Entwicklungsserver aus.
- Führen Sie das Serverprojekt aus, wenn Sie die App mit ASP.NET Core hosten.

Blazor WebAssembly-Apps unterstützen das Debuggen mit Visual Studio nicht. Um die App `Ctrl+F5` auszuführen, `F5`verwenden Sie anstelle von . Sie können stattdessen Blazor WebAssembly-Apps direkt im Browser debuggen. Weitere Informationen finden Sie unter [Debug ASP.NET Core Blazor.](/aspnet/core/blazor/debug)

>[!div class="step-by-step"]
>[VorherigeS](hosting-models.md)
>[Weiter](app-startup.md)
