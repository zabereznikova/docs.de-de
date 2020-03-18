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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="05e10-103">Projektstruktur für Blazor-Apps</span><span class="sxs-lookup"><span data-stu-id="05e10-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="05e10-104">Trotz ihrer erheblichen Unterschiede in der Projektstruktur teilen ASP.NET Web Forms und Blazor viele ähnliche Konzepte.</span><span class="sxs-lookup"><span data-stu-id="05e10-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="05e10-105">Hier betrachten wir die Struktur eines Blazor-Projekts und vergleichen es mit einem ASP.NET Web Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="05e10-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="05e10-106">Um Ihre erste Blazor-App zu erstellen, befolgen Sie die Anweisungen in den [Blazor-Schritte](/aspnet/core/blazor/get-started)für die ersten Schritte .</span><span class="sxs-lookup"><span data-stu-id="05e10-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="05e10-107">Sie können den Anweisungen folgen, um entweder eine Blazor Server-App oder eine Blazor WebAssembly-App zu erstellen, die in ASP.NET Core gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="05e10-108">Mit Ausnahme der modellspezifischen Hostinglogik ist der größte Teil des Codes in beiden Projekten identisch.</span><span class="sxs-lookup"><span data-stu-id="05e10-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="05e10-109">Projektdatei</span><span class="sxs-lookup"><span data-stu-id="05e10-109">Project file</span></span>

<span data-ttu-id="05e10-110">Blazor Server-Apps sind .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="05e10-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="05e10-111">Die Projektdatei für die Blazor Server App ist ungefähr so einfach wie möglich:</span><span class="sxs-lookup"><span data-stu-id="05e10-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="05e10-112">Die Projektdatei für eine Blazor WebAssembly App sieht etwas stärker involviert aus (genaue Versionsnummern können variieren):</span><span class="sxs-lookup"><span data-stu-id="05e10-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="05e10-113">Blazor WebAssembly-Projekte zielen auf .NET Standard anstelle von .NET Core ab, da sie im Browser auf einer WebAssembly-basierten .NET-Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="05e10-114">Sie können .NET nicht wie auf einem Server oder Entwicklercomputer in einem Webbrowser installieren.</span><span class="sxs-lookup"><span data-stu-id="05e10-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="05e10-115">Folglich verweist das Projekt auf das Blazor-Framework unter Verwendung einzelner Paketreferenzen.</span><span class="sxs-lookup"><span data-stu-id="05e10-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="05e10-116">Im Vergleich dazu enthält ein Standardprojekt ASP.NET Web Forms fast 300 XML-Zeilen in seiner *.csproj-Datei,* von denen die meisten explizit die verschiedenen Code- und Inhaltsdateien im Projekt auflisten.</span><span class="sxs-lookup"><span data-stu-id="05e10-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="05e10-117">Viele der Vereinfachungen in .NET Core- und .NET Standard-basierten Projekten stammen aus den `Microsoft.NET.Sdk.Web` Standardzielen und Eigenschaften, die durch Verweisen auf das SDK importiert werden, das häufig als einfach als Web SDK bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="05e10-118">Das Web SDK enthält Platzhalter und andere Annehmlichkeiten, die die Aufnahme von Code und Inhaltsdateien in das Projekt vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="05e10-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="05e10-119">Sie müssen die Dateien nicht explizit auflisten.</span><span class="sxs-lookup"><span data-stu-id="05e10-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="05e10-120">Bei der Ausrichtung auf .NET Core fügt das Web SDK auch Frameworkverweise sowohl zu den freigegebenen .NET Core- als auch zu ASP.NET Core-Frameworks hinzu.</span><span class="sxs-lookup"><span data-stu-id="05e10-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="05e10-121">Die Frameworks sind über den Knoten **Dependencies** > **Frameworks** im **Projektmappen-Explorer-Fenster** sichtbar.</span><span class="sxs-lookup"><span data-stu-id="05e10-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="05e10-122">Die freigegebenen Frameworks sind Auflistungen von Assemblys, die beim Installieren von .NET Core auf dem Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="05e10-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="05e10-123">Obwohl sie unterstützt werden, sind einzelne Assemblyverweise in .NET Core-Projekten seltener.</span><span class="sxs-lookup"><span data-stu-id="05e10-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="05e10-124">Die meisten Projektabhängigkeiten werden als NuGet-Paketverweise behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="05e10-125">Sie müssen nur auf Paketabhängigkeiten der obersten Ebene in .NET Core-Projekten verweisen.</span><span class="sxs-lookup"><span data-stu-id="05e10-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="05e10-126">Transitive Abhängigkeiten werden automatisch eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="05e10-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="05e10-127">Anstatt die *Datei packages.config* zu verwenden, die häufig in ASP.NET Web Forms-Projekten `<PackageReference>` gefunden wird, um auf Pakete zu verweisen, werden der Projektdatei mithilfe des Elements Paketverweise hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="05e10-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="05e10-128">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="05e10-128">Entry point</span></span>

<span data-ttu-id="05e10-129">Der Einstiegspunkt der Blazor Server-App ist in der *Program.cs-Datei* definiert, wie Sie in einer Konsolen-App sehen würden.</span><span class="sxs-lookup"><span data-stu-id="05e10-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="05e10-130">Wenn die App ausgeführt wird, erstellt und führt sie eine Webhostinstanz aus, die für Web-Apps spezifische Standardeinstellungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="05e10-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="05e10-131">Der Webhost verwaltet den Lebenszyklus der Blazor Server-App und richtet Dienste auf Hostebene ein.</span><span class="sxs-lookup"><span data-stu-id="05e10-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="05e10-132">Beispiele für solche Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server.</span><span class="sxs-lookup"><span data-stu-id="05e10-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="05e10-133">Dieser Code ist meist Boilerplate und wird oft unverändert gelassen.</span><span class="sxs-lookup"><span data-stu-id="05e10-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="05e10-134">Blazor WebAssembly-Apps definieren auch einen Einstiegspunkt in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="05e10-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="05e10-135">Der Code sieht etwas anders aus.</span><span class="sxs-lookup"><span data-stu-id="05e10-135">The code looks slightly different.</span></span> <span data-ttu-id="05e10-136">Der Code ist insofern ähnlich, als der App-Host so eingerichtet wird, dass er der App dieselben Dienste auf Hostebene zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="05e10-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="05e10-137">Der WebAssembly-App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="05e10-138">Blazor-Apps `Startup` haben eine Klasse anstelle einer *Global.asax-Datei,* um die Startlogik für die App zu definieren.</span><span class="sxs-lookup"><span data-stu-id="05e10-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="05e10-139">Die `Startup` Klasse wird verwendet, um die App und alle app-spezifischen Dienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="05e10-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="05e10-140">In der Blazor Server-App wird die `Startup` Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die blazor zwischen den Clientbrowsern und dem Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="05e10-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="05e10-141">In der Blazor WebAssembly-App definiert die `Startup` Klasse die Stammkomponenten für die App und deren Renderung.</span><span class="sxs-lookup"><span data-stu-id="05e10-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="05e10-142">Wir werfen einen tieferen `Startup` Blick auf die Klasse im [App-Startabschnitt.](./app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="05e10-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="05e10-143">Statische Dateien</span><span class="sxs-lookup"><span data-stu-id="05e10-143">Static files</span></span>

<span data-ttu-id="05e10-144">Im Gegensatz zu ASP.NET Web Forms-Projekten können nicht alle Dateien in einem Blazor-Projekt als statische Dateien angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="05e10-145">Nur die Dateien im *Ordner wwwroot* sind webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="05e10-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="05e10-146">Dieser Ordner wird auf den "Web-Stamm" der App verwiesen.</span><span class="sxs-lookup"><span data-stu-id="05e10-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="05e10-147">Alles außerhalb des Web-Roots der App *ist nicht* webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="05e10-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="05e10-148">Dieses Setup bietet eine zusätzliche Sicherheitsstufe, die verhindert, dass Projektdateien versehentlich über das Web verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="05e10-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="05e10-149">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="05e10-149">Configuration</span></span>

<span data-ttu-id="05e10-150">Die Konfiguration in ASP.NET Web Forms-Apps wird in der Regel mit einer oder mehreren *web.config-Dateien* behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="05e10-151">Blazor-Apps haben in der Regel keine *web.config-Dateien.*</span><span class="sxs-lookup"><span data-stu-id="05e10-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="05e10-152">Wenn dies der Zeitpunkt ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn sie auf IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="05e10-153">Stattdessen verwenden Blazor Server-Apps die ASP.NET Core-Konfigurationsabstraktionen (Blazor WebAssembly-Apps unterstützen derzeit nicht die gleichen Konfigurationsabstraktionen, aber dies kann ein Feature sein, das in der Zukunft hinzugefügt wird).</span><span class="sxs-lookup"><span data-stu-id="05e10-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="05e10-154">Die standardmäßige Blazor Server-App speichert beispielsweise einige Einstellungen in *appsettings.json*.</span><span class="sxs-lookup"><span data-stu-id="05e10-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="05e10-155">Weitere Informationen zur Konfiguration in ASP.NET Core-Projekten finden Sie im Abschnitt [Konfiguration.](./config.md)</span><span class="sxs-lookup"><span data-stu-id="05e10-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="05e10-156">Razor-Komponenten</span><span class="sxs-lookup"><span data-stu-id="05e10-156">Razor components</span></span>

<span data-ttu-id="05e10-157">Die meisten Dateien in Blazor-Projekten sind *.razor-Dateien.*</span><span class="sxs-lookup"><span data-stu-id="05e10-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="05e10-158">Razor ist eine Vorlagensprache, die auf HTML und C- basiert und zum dynamischen Generieren der Web-UI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="05e10-159">Die *.razor-Dateien* definieren Komponenten, aus denen die Benutzeroberfläche der App besteht.</span><span class="sxs-lookup"><span data-stu-id="05e10-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="05e10-160">Die Komponenten sind größtenteils sowohl für die Blazor Server- als auch für die Blazor WebAssembly-Apps identisch.</span><span class="sxs-lookup"><span data-stu-id="05e10-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="05e10-161">Komponenten in Blazor sind analog zu Benutzersteuerelementen in ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="05e10-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="05e10-162">Jede Razor-Komponentendatei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="05e10-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="05e10-163">Die generierte Klasse erfasst den Status der Komponente, die Renderinglogik, Lebenszyklusmethoden, Ereignishandler und andere Logik.</span><span class="sxs-lookup"><span data-stu-id="05e10-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="05e10-164">Wir werden uns mit dem Erstellen von Komponenten in den Komponenten [für wiederverwendbare Benutzeroberflächen erstellen mit Blazor](./components.md) befassen.</span><span class="sxs-lookup"><span data-stu-id="05e10-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="05e10-165">Die *_Imports.razor-Dateien* sind keine Razor-Komponentendateien.</span><span class="sxs-lookup"><span data-stu-id="05e10-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="05e10-166">Stattdessen definieren sie eine Reihe von Razor-Direktiven, die in andere *.razor-Dateien* innerhalb desselben Ordners und in seinen Unterordnern importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="05e10-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="05e10-167">Eine *_Imports.razor-Datei* ist z. B. eine herkömmliche Möglichkeit, Anweisungen für häufig verwendete Namespaces hinzuzufügen: `using`</span><span class="sxs-lookup"><span data-stu-id="05e10-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="05e10-168">Seiten</span><span class="sxs-lookup"><span data-stu-id="05e10-168">Pages</span></span>

<span data-ttu-id="05e10-169">Wo sind die Seiten in den Blazor-Apps?</span><span class="sxs-lookup"><span data-stu-id="05e10-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="05e10-170">Blazor definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. B. die *ASPX-Dateien* in ASP.NET Web Forms-Apps.</span><span class="sxs-lookup"><span data-stu-id="05e10-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="05e10-171">Stattdessen werden Seiten definiert, indem Routen Komponenten zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="05e10-172">Eine Route wird in `@page` der Regel mithilfe der Razor-Direktive zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="05e10-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="05e10-173">Die `Counter` in der Datei *Pages/Counter.razor* erstellte Komponente definiert beispielsweise die folgende Route:</span><span class="sxs-lookup"><span data-stu-id="05e10-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="05e10-174">Routing in Blazor wird clientseitig und nicht auf dem Server behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="05e10-175">Während der Benutzer im Browser navigiert, fängt Blazor die Navigation ab und rendert die Komponente dann mit der passenden Route.</span><span class="sxs-lookup"><span data-stu-id="05e10-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="05e10-176">Die Komponentenrouten werden derzeit nicht durch den Dateispeicherort der Komponente abgeleitet, wie sie bei *ASPX-Seiten* der Datei sind.</span><span class="sxs-lookup"><span data-stu-id="05e10-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="05e10-177">Diese Funktion kann in Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-177">This feature may be added in the future.</span></span> <span data-ttu-id="05e10-178">Jede Route muss explizit für die Komponente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="05e10-179">Das Speichern von Routingkomponenten in einem *Pages-Ordner* hat keine besondere Bedeutung und ist eine reine Konvention.</span><span class="sxs-lookup"><span data-stu-id="05e10-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="05e10-180">Im Abschnitt [Seiten, Routing und Layouts](./pages-routing-layouts.md) wird das Routing in Blazor genauer erläutert.</span><span class="sxs-lookup"><span data-stu-id="05e10-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="05e10-181">Layout</span><span class="sxs-lookup"><span data-stu-id="05e10-181">Layout</span></span>

<span data-ttu-id="05e10-182">In ASP.NET Web Forms-Apps wird das allgemeine Seitenlayout mithilfe von Masterseiten (*Site.Master*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="05e10-183">In Blazor-Apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout.razor*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="05e10-184">Layoutkomponenten werden im Abschnitt [Seite, Routing und Layouts](./pages-routing-layouts.md) ausführlicher behandelt.</span><span class="sxs-lookup"><span data-stu-id="05e10-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="05e10-185">Bootstrap Blazor</span><span class="sxs-lookup"><span data-stu-id="05e10-185">Bootstrap Blazor</span></span>

<span data-ttu-id="05e10-186">Um Blazor zu booten, muss die App:</span><span class="sxs-lookup"><span data-stu-id="05e10-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="05e10-187">Geben Sie an, wo auf der Seite die Stammkomponente (*App.Razor*) gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e10-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="05e10-188">Fügen Sie das entsprechende Blazor-Frameworkskript hinzu.</span><span class="sxs-lookup"><span data-stu-id="05e10-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="05e10-189">In der Blazor Server-App wird die Hostseite der Stammkomponente in der Datei *_Host.cshtml* definiert.</span><span class="sxs-lookup"><span data-stu-id="05e10-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="05e10-190">Diese Datei definiert eine Razor-Seite, keine Komponente.</span><span class="sxs-lookup"><span data-stu-id="05e10-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="05e10-191">Razor Pages verwenden die Razor-Syntax, um eine serveradressierbare Seite zu definieren, die einer *ASPX-Seite* sehr ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="05e10-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="05e10-192">Die `Html.RenderComponentAsync<TComponent>(RenderMode)` Methode wird verwendet, um zu definieren, wo eine Komponente auf Stammebene gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e10-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="05e10-193">Die `RenderMode` Option gibt die Art und Weise an, in der die Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e10-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="05e10-194">In der folgenden Tabelle `RenderMode` werden die unterstützten Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05e10-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="05e10-195">Option</span><span class="sxs-lookup"><span data-stu-id="05e10-195">Option</span></span>                        |<span data-ttu-id="05e10-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05e10-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="05e10-197">Interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="05e10-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="05e10-198">Erst vorgerendert und dann interaktiv gerendert</span><span class="sxs-lookup"><span data-stu-id="05e10-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="05e10-199">Als statischer Inhalt gerendert</span><span class="sxs-lookup"><span data-stu-id="05e10-199">Rendered as static content</span></span>|

<span data-ttu-id="05e10-200">Der Skriptverweis auf *_framework/blazor.server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich dann mit allen Benutzerinteraktionen und UI-Updates.</span><span class="sxs-lookup"><span data-stu-id="05e10-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="05e10-201">In der Blazor WebAssembly-App ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="05e10-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="05e10-202">Das `<app>` Element wird verwendet, um anzugeben, wo die Stammkomponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e10-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="05e10-203">Die zu rendernde Komponente wird in `Startup.Configure` der App-Methode mit einem entsprechenden CSS-Selektor konfiguriert, der angibt, wo die Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="05e10-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="05e10-204">Erstellen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="05e10-204">Build output</span></span>

<span data-ttu-id="05e10-205">Wenn ein Blazor-Projekt erstellt wird, werden alle Razor-Komponenten- und Codedateien in einer einzigen Assembly kompiliert.</span><span class="sxs-lookup"><span data-stu-id="05e10-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="05e10-206">Im Gegensatz zu ASP.NET Web Forms-Projekten unterstützt Blazor die Laufzeitkompilierung der UI-Logik nicht.</span><span class="sxs-lookup"><span data-stu-id="05e10-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="05e10-207">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="05e10-207">Run the app</span></span>

<span data-ttu-id="05e10-208">Um die Blazor Server-App auszuführen, drücken Sie `F5` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05e10-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="05e10-209">Blazor-Apps unterstützen keine Laufzeitkompilierung.</span><span class="sxs-lookup"><span data-stu-id="05e10-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="05e10-210">Um die Ergebnisse von Code- und Komponentenmarkupänderungen anzuzeigen, erstellen Sie die App neu und starten Sie sie neu, wobei der Debugger angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="05e10-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="05e10-211">Wenn Sie ohne den angefügten Debugger (`Ctrl+F5`) ausgeführt werden, überwacht Visual Studio Dateiänderungen und startet die App neu, wenn Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="05e10-212">Sie aktualisieren den Browser manuell, wenn Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="05e10-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="05e10-213">Um die Blazor WebAssembly-App auszuführen, wählen Sie einen der folgenden Ansätze aus:</span><span class="sxs-lookup"><span data-stu-id="05e10-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="05e10-214">Führen Sie das Clientprojekt direkt über den Entwicklungsserver aus.</span><span class="sxs-lookup"><span data-stu-id="05e10-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="05e10-215">Führen Sie das Serverprojekt aus, wenn Sie die App mit ASP.NET Core hosten.</span><span class="sxs-lookup"><span data-stu-id="05e10-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="05e10-216">Blazor WebAssembly-Apps unterstützen das Debuggen mit Visual Studio nicht.</span><span class="sxs-lookup"><span data-stu-id="05e10-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="05e10-217">Um die App `Ctrl+F5` auszuführen, `F5`verwenden Sie anstelle von .</span><span class="sxs-lookup"><span data-stu-id="05e10-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="05e10-218">Sie können stattdessen Blazor WebAssembly-Apps direkt im Browser debuggen.</span><span class="sxs-lookup"><span data-stu-id="05e10-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="05e10-219">Weitere Informationen finden Sie unter [Debug ASP.NET Core Blazor.](/aspnet/core/blazor/debug)</span><span class="sxs-lookup"><span data-stu-id="05e10-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="05e10-220">[VorherigeS](hosting-models.md)
>[Weiter](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="05e10-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
