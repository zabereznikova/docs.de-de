---
title: Projektstruktur für Blazor apps
description: Erfahren Sie, wie die Projektstrukturen von ASP.net-Web Forms und- Blazor Projekten verglichen werden.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 09/11/2019
ms.openlocfilehash: 473b708a9b58fa88844bc6f79a898943d5a7db71
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173041"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="471e5-103">Projektstruktur für Blazor apps</span><span class="sxs-lookup"><span data-stu-id="471e5-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="471e5-104">Trotz ihrer erheblichen Unterschiede in der Projektstruktur werden ASP.net Web Forms und Blazor viele ähnliche Konzepte gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="471e5-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="471e5-105">Hier betrachten wir die Struktur eines Blazor Projekts und vergleichen es mit einem ASP.net-Web Forms Projekt.</span><span class="sxs-lookup"><span data-stu-id="471e5-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="471e5-106">Um Ihre erste APP zu erstellen Blazor , befolgen Sie die Anweisungen in den [ Blazor Schritten erste Schritte](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="471e5-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="471e5-107">Sie können die Anweisungen befolgen, um entweder eine Blazor Server-APP oder eine Blazor WebAssembly in ASP.net Core gehostete-APP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="471e5-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="471e5-108">Mit Ausnahme der hostingmodellspezifischen Logik ist der größte Teil des Codes in beiden Projekten identisch.</span><span class="sxs-lookup"><span data-stu-id="471e5-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="471e5-109">Projektdatei</span><span class="sxs-lookup"><span data-stu-id="471e5-109">Project file</span></span>

Blazor<span data-ttu-id="471e5-110">Server-apps sind .net Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="471e5-110"> Server apps are .NET Core projects.</span></span> <span data-ttu-id="471e5-111">Die Projektdatei für die Blazor Server-APP ist ungefähr so einfach wie möglich:</span><span class="sxs-lookup"><span data-stu-id="471e5-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="471e5-112">Die Projektdatei für eine Blazor WebAssembly App ist etwas komplizierter (genaue Versionsnummern können variieren):</span><span class="sxs-lookup"><span data-stu-id="471e5-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

Blazor<span data-ttu-id="471e5-113">WebAssemblyprojiziert Ziel .NET Standard anstelle von .net Core, da Sie im Browser auf einer WebAssembly -basierten .NET-Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-113"> WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="471e5-114">Sie können .net nicht in einem Webbrowser installieren, wie auf einem Server oder einem Entwickler Computer.</span><span class="sxs-lookup"><span data-stu-id="471e5-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="471e5-115">Folglich verweist das Projekt auf das Blazor Framework mit einzelnen Paket verweisen.</span><span class="sxs-lookup"><span data-stu-id="471e5-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="471e5-116">Im Vergleich dazu enthält ein Standardmäßiges ASP.net-Web Forms Projekt fast 300 XML-Zeilen in der *csproj* -Datei, von denen die meisten Code-und Inhalts Dateien im Projekt explizit aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="471e5-117">Viele der Vereinfachungen in den .net Core-und .NET Standard basierten Projekten stammen aus den Standardzielen und-Eigenschaften, die durch den Verweis `Microsoft.NET.Sdk.Web` auf das SDK importiert werden. Dies wird häufig auch als einfaches WebSDK bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="471e5-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="471e5-118">Das Web-SDK umfasst Platzhalter und andere Bequemlichkeiten, die die Einbindung von Code und Inhalts Dateien im Projekt vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="471e5-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="471e5-119">Sie müssen die Dateien nicht explizit auflisten.</span><span class="sxs-lookup"><span data-stu-id="471e5-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="471e5-120">Wenn .net Core als Zielversion verwendet wird, fügt das Web-SDK auch frameworkverweise sowohl auf die .net Core-als auch auf die ASP.net Core frei</span><span class="sxs-lookup"><span data-stu-id="471e5-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="471e5-121">Die Frameworks sind über den Knoten **Abhängigkeiten**-  >  **Frameworks** im Fenster **Projektmappen-Explorer** sichtbar.</span><span class="sxs-lookup"><span data-stu-id="471e5-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="471e5-122">Die freigegebenen Frameworks sind Assemblys, die bei der Installation von .net Core auf dem Computer installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="471e5-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="471e5-123">Obwohl Sie unterstützt werden, sind einzelne Assemblyverweise in .net Core-Projekten weniger häufig.</span><span class="sxs-lookup"><span data-stu-id="471e5-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="471e5-124">Die meisten Projekt Abhängigkeiten werden als nuget-Paket Verweise behandelt.</span><span class="sxs-lookup"><span data-stu-id="471e5-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="471e5-125">In .net Core-Projekten müssen Sie nur auf Paketabhängigkeiten der obersten Ebene verweisen.</span><span class="sxs-lookup"><span data-stu-id="471e5-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="471e5-126">Transitive Abhängigkeiten werden automatisch eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="471e5-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="471e5-127">Anstatt die *packages.config* Datei zu verwenden, die häufig in ASP.net-Web Forms Projekten für Verweise auf Pakete zu finden ist, werden Paket Verweise der Projektdatei mithilfe des-Elements hinzugefügt `<PackageReference>` .</span><span class="sxs-lookup"><span data-stu-id="471e5-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="471e5-128">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="471e5-128">Entry point</span></span>

<span data-ttu-id="471e5-129">Der Blazor Einstiegspunkt der Server-APP wird in der Datei *Program.cs* definiert, wie Sie in einer Konsolen-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="471e5-130">Wenn die app ausgeführt wird, erstellt Sie eine Webhost Instanz und führt Sie mithilfe der Standardeinstellungen für Web-Apps aus.</span><span class="sxs-lookup"><span data-stu-id="471e5-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="471e5-131">Der Webhost verwaltet den Blazor Lebenszyklus der Server-APP und richtet Dienste auf Hostebene ein.</span><span class="sxs-lookup"><span data-stu-id="471e5-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="471e5-132">Beispiele für derartige Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server.</span><span class="sxs-lookup"><span data-stu-id="471e5-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="471e5-133">Dieser Code ist größtenteils eine Bausteine und bleibt häufig unverändert.</span><span class="sxs-lookup"><span data-stu-id="471e5-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

Blazor<span data-ttu-id="471e5-134">WebAssemblyapps definieren außerdem einen Einstiegspunkt in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="471e5-134"> WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="471e5-135">Der Code sieht etwas anders aus.</span><span class="sxs-lookup"><span data-stu-id="471e5-135">The code looks slightly different.</span></span> <span data-ttu-id="471e5-136">Der Code ähnelt dem Einrichten des App-Hosts, um die gleichen Dienste auf Hostebene für die APP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="471e5-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="471e5-137">Der WebAssembly App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

Blazor<span data-ttu-id="471e5-138">Apps verfügen `Startup` anstelle einer *Global. asax* -Datei über eine-Klasse, um die Start Logik für die APP zu definieren.</span><span class="sxs-lookup"><span data-stu-id="471e5-138"> apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="471e5-139">Die `Startup` -Klasse wird verwendet, um die APP und alle App-spezifischen Dienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="471e5-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="471e5-140">In der Blazor Server-APP wird die- `Startup` Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die von Blazor zwischen den Client Browsern und dem Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="471e5-141">In der Blazor WebAssembly App definiert die `Startup` -Klasse die Stamm Komponenten für die APP und wo Sie gerendert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="471e5-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="471e5-142">Wir werfen einen tieferen Einblick in die- `Startup` Klasse im Abschnitt [App-Start](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="471e5-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="471e5-143">Statische Dateien</span><span class="sxs-lookup"><span data-stu-id="471e5-143">Static files</span></span>

<span data-ttu-id="471e5-144">Im Gegensatz zu ASP.net-Web Forms Projekten können nicht alle Dateien in einem Blazor Projekt als statische Dateien angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="471e5-145">Nur die Dateien im Ordner " *wwwroot* " sind webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="471e5-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="471e5-146">Dieser Ordner wird als "Web Root" der APP bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="471e5-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="471e5-147">Alles außerhalb des webstamms der APP *ist nicht* webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="471e5-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="471e5-148">Dieses Setup bietet ein zusätzliches Maß an Sicherheit, das eine versehentliche Offenlegung von Projektdateien über das Internet verhindert.</span><span class="sxs-lookup"><span data-stu-id="471e5-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="471e5-149">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="471e5-149">Configuration</span></span>

<span data-ttu-id="471e5-150">Die Konfiguration in ASP.net Web Forms-apps wird in der Regel mit einer oder mehreren *web.config* Dateien gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="471e5-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> Blazor<span data-ttu-id="471e5-151">Apps verfügen in der Regel nicht über *web.config* Dateien.</span><span class="sxs-lookup"><span data-stu-id="471e5-151"> apps don't typically have *web.config* files.</span></span> <span data-ttu-id="471e5-152">Wenn dies der Fall ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn Sie auf IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="471e5-153">Stattdessen Blazor verwenden Server-Apps die ASP.net Core Konfigurations Abstraktionen ( Blazor WebAssembly apps unterstützen derzeit nicht dieselben Konfigurations Abstraktionen, aber dies kann ein in der Zukunft hinzugefügtes Feature sein).</span><span class="sxs-lookup"><span data-stu-id="471e5-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="471e5-154">Beispielsweise werden in der Standard Blazor Server-App einige Einstellungen in *appsettings.js*gespeichert.</span><span class="sxs-lookup"><span data-stu-id="471e5-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="471e5-155">Weitere Informationen zur Konfiguration finden Sie unter ASP.net Core-Projekte im Abschnitt " [Konfiguration](./config.md) ".</span><span class="sxs-lookup"><span data-stu-id="471e5-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="471e5-156">Razor-Komponenten</span><span class="sxs-lookup"><span data-stu-id="471e5-156">Razor components</span></span>

<span data-ttu-id="471e5-157">Die meisten Dateien in Blazor Projekten sind *Razor* -Dateien.</span><span class="sxs-lookup"><span data-stu-id="471e5-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="471e5-158">Razor ist eine Vorlagen Sprache, die auf HTML und c# basiert und zum dynamischen Generieren der Webbenutzer Oberfläche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="471e5-159">Die *Razor* -Dateien definieren Komponenten, aus denen die Benutzeroberfläche der APP besteht.</span><span class="sxs-lookup"><span data-stu-id="471e5-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="471e5-160">Zum größten Teil sind die Komponenten sowohl für den Blazor Server als auch für die Blazor WebAssembly apps identisch.</span><span class="sxs-lookup"><span data-stu-id="471e5-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="471e5-161">Komponenten in entsprechen Blazor den Benutzer Steuerelementen in ASP.net-Web Forms.</span><span class="sxs-lookup"><span data-stu-id="471e5-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="471e5-162">Jede Razor-Komponenten Datei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="471e5-163">Die generierte-Klasse erfasst den Zustand der Komponente, die Renderinglogik, Lebenszyklus Methoden, Ereignishandler und andere Logik.</span><span class="sxs-lookup"><span data-stu-id="471e5-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="471e5-164">Wir werden uns mit der Erstellung von Komponenten im Abschnitt [Erstellen wiederverwendbarer UI- Blazor Komponenten mit](./components.md) beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="471e5-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="471e5-165">Die *_Imports. Razor* -Dateien sind keine Razor-Komponenten Dateien.</span><span class="sxs-lookup"><span data-stu-id="471e5-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="471e5-166">Stattdessen definieren Sie einen Satz von Razor-Direktiven, die in andere *Razor* -Dateien im selben Ordner und in den zugehörigen Unterordnern importiert werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="471e5-167">Beispielsweise ist eine *_Imports. Razor* -Datei ein herkömmliches Verfahren zum Hinzufügen `using` von Direktiven für häufig verwendete Namespaces:</span><span class="sxs-lookup"><span data-stu-id="471e5-167">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="471e5-168">Seiten</span><span class="sxs-lookup"><span data-stu-id="471e5-168">Pages</span></span>

<span data-ttu-id="471e5-169">Wo befinden sich die Seiten in den Blazor apps?</span><span class="sxs-lookup"><span data-stu-id="471e5-169">Where are the pages in the Blazor apps?</span></span> Blazor<span data-ttu-id="471e5-170">definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. b. die *aspx* -Dateien in ASP.net-Web Forms-apps.</span><span class="sxs-lookup"><span data-stu-id="471e5-170"> doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="471e5-171">Stattdessen werden Seiten durch Zuweisen von Routen zu Komponenten definiert.</span><span class="sxs-lookup"><span data-stu-id="471e5-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="471e5-172">Eine Route wird in der Regel mithilfe der `@page` Razor-Direktive zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="471e5-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="471e5-173">Die `Counter` in der Datei *pages/Counter. Razor* erstellte Komponente definiert z. b. die folgende Route:</span><span class="sxs-lookup"><span data-stu-id="471e5-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="471e5-174">Das Routing in Blazor erfolgt auf Clientseite, nicht auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="471e5-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="471e5-175">Wenn der Benutzer im Browser navigiert, Blazor fängt die Navigation ab und rendert die Komponente dann mit der passenden Route.</span><span class="sxs-lookup"><span data-stu-id="471e5-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="471e5-176">Die Komponenten Routen werden zurzeit nicht durch den Datei Speicherort der Komponente abgeleitet, z. b. mit *aspx* -Seiten.</span><span class="sxs-lookup"><span data-stu-id="471e5-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="471e5-177">Diese Funktion kann in Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-177">This feature may be added in the future.</span></span> <span data-ttu-id="471e5-178">Jede Route muss explizit für die Komponente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="471e5-179">Das Speichern von Routing fähigen Komponenten in einem *Seiten* Ordner hat keine besondere Bedeutung und ist rein eine Konvention.</span><span class="sxs-lookup"><span data-stu-id="471e5-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="471e5-180">Weitere Details finden Sie im Blazor Abschnitt " [Seiten, Routing und Layouts](./pages-routing-layouts.md) " unter Routing in.</span><span class="sxs-lookup"><span data-stu-id="471e5-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="471e5-181">Layout</span><span class="sxs-lookup"><span data-stu-id="471e5-181">Layout</span></span>

<span data-ttu-id="471e5-182">In ASP.net Web Forms-apps wird das allgemeine Seitenlayout mithilfe von Masterseiten (*Site. Master*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="471e5-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="471e5-183">In- Blazor apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout. Razor*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="471e5-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="471e5-184">Layoutkomponenten werden im Abschnitt "Seite" [, "Routing" und "Layouts](./pages-routing-layouts.md) " ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="471e5-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="471e5-185">BootstrapBlazor</span><span class="sxs-lookup"><span data-stu-id="471e5-185">Bootstrap Blazor</span></span>

<span data-ttu-id="471e5-186">Zum Bootstrapping Blazor muss die app folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="471e5-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="471e5-187">Geben Sie an, wo auf der Seite die Stamm Komponente (*app. Razor*) gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="471e5-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="471e5-188">Fügen Sie das entsprechende Blazor Framework-Skript hinzu.</span><span class="sxs-lookup"><span data-stu-id="471e5-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="471e5-189">In der Blazor Server-APP wird die Hostseite der Stamm Komponente in der Datei *_Host. cshtml* definiert.</span><span class="sxs-lookup"><span data-stu-id="471e5-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="471e5-190">Diese Datei definiert eine Razor-Seite und keine Komponente.</span><span class="sxs-lookup"><span data-stu-id="471e5-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="471e5-191">Razor Pages verwenden Sie Razor-Syntax, um eine Server adressierbare Seite zu definieren, ähnlich wie eine *aspx* -Seite.</span><span class="sxs-lookup"><span data-stu-id="471e5-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="471e5-192">Die- `Html.RenderComponentAsync<TComponent>(RenderMode)` Methode wird verwendet, um zu definieren, wo eine Komponente auf Stamm Ebene gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="471e5-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="471e5-193">Die- `RenderMode` Option gibt die Art an, in der die Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="471e5-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="471e5-194">In der folgenden Tabelle werden die unterstützten `RenderMode` Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="471e5-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="471e5-195">Option</span><span class="sxs-lookup"><span data-stu-id="471e5-195">Option</span></span>                        |<span data-ttu-id="471e5-196">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="471e5-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="471e5-197">Wird interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="471e5-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="471e5-198">Zuerst vorab und dann interaktiv gerendert</span><span class="sxs-lookup"><span data-stu-id="471e5-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="471e5-199">Als statischer Inhalt gerendert</span><span class="sxs-lookup"><span data-stu-id="471e5-199">Rendered as static content</span></span>|

<span data-ttu-id="471e5-200">Der Skript Verweis auf *_framework/blazor.server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich mit allen Benutzerinteraktionen und Aktualisierungen der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="471e5-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="471e5-201">In der Blazor WebAssembly App ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="471e5-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="471e5-202">Das- `<app>` Element wird verwendet, um anzugeben, wo die Stamm Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="471e5-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="471e5-203">Die zu rendernde bestimmte Komponente wird in der- `Startup.Configure` Methode der APP mit einer entsprechenden CSS-Auswahl konfiguriert, die angibt, wo die Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="471e5-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="471e5-204">Erstellen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="471e5-204">Build output</span></span>

<span data-ttu-id="471e5-205">Wenn ein Blazor Projekt erstellt wird, werden alle Razor-Komponenten-und Code Dateien in eine einzelne Assembly kompiliert.</span><span class="sxs-lookup"><span data-stu-id="471e5-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="471e5-206">Im Gegensatz zu ASP.net-Web Forms Projekten Blazor unterstützt keine Lauf Zeit Kompilierung der UI-Logik.</span><span class="sxs-lookup"><span data-stu-id="471e5-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="471e5-207">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="471e5-207">Run the app</span></span>

<span data-ttu-id="471e5-208">Um die Blazor Server-App auszuführen, drücken Sie `F5` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="471e5-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> Blazor<span data-ttu-id="471e5-209">Apps unterstützen keine Lauf Zeit Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="471e5-209"> apps don't support runtime compilation.</span></span> <span data-ttu-id="471e5-210">Um die Ergebnisse von Code-und Komponenten Markup Änderungen anzuzeigen, müssen Sie die APP mit dem angefügten Debugger neu erstellen und neu starten.</span><span class="sxs-lookup"><span data-stu-id="471e5-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="471e5-211">Wenn Sie ausführen, ohne dass der Debugger angefügt `Ctrl+F5` ist (), beobachtet Visual Studio die Dateiänderungen und startet die APP neu, sobald Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="471e5-212">Sie müssen den Browser manuell aktualisieren, wenn Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="471e5-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="471e5-213">Blazor WebAssembly Wählen Sie einen der folgenden Ansätze aus, um die APP auszuführen:</span><span class="sxs-lookup"><span data-stu-id="471e5-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="471e5-214">Führen Sie das Client Projekt direkt mit dem Development Server aus.</span><span class="sxs-lookup"><span data-stu-id="471e5-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="471e5-215">Führen Sie das Server Projekt aus, wenn die APP mit ASP.net Core gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="471e5-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

Blazor<span data-ttu-id="471e5-216">WebAssemblyapps unterstützen das Debuggen mit Visual Studio nicht.</span><span class="sxs-lookup"><span data-stu-id="471e5-216"> WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="471e5-217">Verwenden Sie anstelle von, um die APP auszuführen `Ctrl+F5` `F5` .</span><span class="sxs-lookup"><span data-stu-id="471e5-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="471e5-218">Stattdessen können Sie Blazor WebAssembly apps direkt im Browser Debuggen.</span><span class="sxs-lookup"><span data-stu-id="471e5-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="471e5-219">Weitere Informationen finden Sie unter [Debug ASP.net Core Blazor ](/aspnet/core/blazor/debug) .</span><span class="sxs-lookup"><span data-stu-id="471e5-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="471e5-220">[Zurück](hosting-models.md)
>[Weiter](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="471e5-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
