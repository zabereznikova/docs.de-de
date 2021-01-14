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
# <a name="project-structure-for-no-locblazor-apps"></a><span data-ttu-id="03dbd-103">Projektstruktur für Blazor apps</span><span class="sxs-lookup"><span data-stu-id="03dbd-103">Project structure for Blazor apps</span></span>

<span data-ttu-id="03dbd-104">Trotz ihrer erheblichen Unterschiede in der Projektstruktur werden ASP.net Web Forms und Blazor viele ähnliche Konzepte gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="03dbd-105">Hier betrachten wir die Struktur eines Blazor Projekts und vergleichen es mit einem ASP.net-Web Forms Projekt.</span><span class="sxs-lookup"><span data-stu-id="03dbd-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="03dbd-106">Um Ihre erste APP zu erstellen Blazor , befolgen Sie die Anweisungen in den [ Blazor Schritten erste Schritte](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="03dbd-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="03dbd-107">Sie können die Anweisungen befolgen, um entweder eine Blazor Server-APP oder eine Blazor WebAssembly in ASP.net Core gehostete-APP zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="03dbd-108">Mit Ausnahme der hostingmodellspezifischen Logik ist der größte Teil des Codes in beiden Projekten identisch.</span><span class="sxs-lookup"><span data-stu-id="03dbd-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="03dbd-109">Projektdatei</span><span class="sxs-lookup"><span data-stu-id="03dbd-109">Project file</span></span>

<span data-ttu-id="03dbd-110">Blazor Server-apps sind .net-Projekte.</span><span class="sxs-lookup"><span data-stu-id="03dbd-110">Blazor Server apps are .NET projects.</span></span> <span data-ttu-id="03dbd-111">Die Projektdatei für die Blazor Server-APP ist ungefähr so einfach wie möglich:</span><span class="sxs-lookup"><span data-stu-id="03dbd-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="03dbd-112">Die Projektdatei für eine Blazor WebAssembly App ist etwas komplizierter (genaue Versionsnummern können variieren):</span><span class="sxs-lookup"><span data-stu-id="03dbd-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="03dbd-113">BlazorWebAssemblyProjektziele `Microsoft.NET.Sdk.BlazorWebAssembly` anstelle von `Microsoft.NET.Sdk.Web` SDK, da Sie im Browser auf einer WebAssembly -basierten .NET-Laufzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-113">Blazor WebAssembly project targets `Microsoft.NET.Sdk.BlazorWebAssembly` instead of `Microsoft.NET.Sdk.Web` sdk because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="03dbd-114">Sie können .net nicht in einem Webbrowser installieren, wie auf einem Server oder einem Entwickler Computer.</span><span class="sxs-lookup"><span data-stu-id="03dbd-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="03dbd-115">Folglich verweist das Projekt auf das Blazor Framework mit einzelnen Paket verweisen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="03dbd-116">Im Vergleich dazu enthält ein Standardmäßiges ASP.net-Web Forms Projekt fast 300 XML-Zeilen in der *csproj* -Datei, von denen die meisten Code-und Inhalts Dateien im Projekt explizit aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="03dbd-117">Mit der-Version `.NET 5` von `Blazor Server` und `Blazor WebAssembly` kann eine einheitliche Laufzeit auf einfache Weise gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-117">With the release of `.NET 5` both `Blazor Server` and `Blazor WebAssembly` app can easily share one unified runtime.</span></span>

<span data-ttu-id="03dbd-118">Obwohl Sie unterstützt werden, sind einzelne Assemblyverweise in .NET-Projekten weniger häufig.</span><span class="sxs-lookup"><span data-stu-id="03dbd-118">Although they're supported, individual assembly references are less common in .NET projects.</span></span> <span data-ttu-id="03dbd-119">Die meisten Projekt Abhängigkeiten werden als nuget-Paket Verweise behandelt.</span><span class="sxs-lookup"><span data-stu-id="03dbd-119">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="03dbd-120">Sie müssen nur auf Paketabhängigkeiten auf oberster Ebene in .NET-Projekten verweisen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-120">You only need to reference top-level package dependencies in .NET projects.</span></span> <span data-ttu-id="03dbd-121">Transitive Abhängigkeiten werden automatisch eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-121">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="03dbd-122">Anstatt die *packages.config* Datei zu verwenden, die häufig in ASP.net-Web Forms Projekten für Verweise auf Pakete zu finden ist, werden Paket Verweise der Projektdatei mithilfe des-Elements hinzugefügt `<PackageReference>` .</span><span class="sxs-lookup"><span data-stu-id="03dbd-122">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="03dbd-123">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="03dbd-123">Entry point</span></span>

<span data-ttu-id="03dbd-124">Der Blazor Einstiegspunkt der Server-APP wird in der Datei *Program.cs* definiert, wie Sie in einer Konsolen-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-124">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="03dbd-125">Wenn die app ausgeführt wird, erstellt Sie eine Webhost Instanz und führt Sie mithilfe der Standardeinstellungen für Web-Apps aus.</span><span class="sxs-lookup"><span data-stu-id="03dbd-125">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="03dbd-126">Der Webhost verwaltet den Blazor Lebenszyklus der Server-APP und richtet Dienste auf Hostebene ein.</span><span class="sxs-lookup"><span data-stu-id="03dbd-126">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="03dbd-127">Beispiele für derartige Dienste sind Konfiguration, Protokollierung, Abhängigkeitsinjektion und der HTTP-Server.</span><span class="sxs-lookup"><span data-stu-id="03dbd-127">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="03dbd-128">Dieser Code ist größtenteils eine Bausteine und bleibt häufig unverändert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-128">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="03dbd-129">BlazorWebAssemblyapps definieren außerdem einen Einstiegspunkt in *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="03dbd-129">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="03dbd-130">Der Code sieht etwas anders aus.</span><span class="sxs-lookup"><span data-stu-id="03dbd-130">The code looks slightly different.</span></span> <span data-ttu-id="03dbd-131">Der Code ähnelt dem Einrichten des App-Hosts, um die gleichen Dienste auf Hostebene für die APP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-131">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="03dbd-132">Der WebAssembly App-Host richtet jedoch keinen HTTP-Server ein, da er direkt im Browser ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-132">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="03dbd-133">Blazor Apps verfügen `Startup` anstelle einer *Global. asax* -Datei über eine-Klasse, um die Start Logik für die APP zu definieren.</span><span class="sxs-lookup"><span data-stu-id="03dbd-133">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="03dbd-134">Die `Startup` -Klasse wird verwendet, um die APP und alle App-spezifischen Dienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03dbd-134">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="03dbd-135">In der Blazor Server-APP wird die- `Startup` Klasse verwendet, um den Endpunkt für die Echtzeitverbindung einzurichten, die von Blazor zwischen den Client Browsern und dem Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-135">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="03dbd-136">In der Blazor WebAssembly App definiert die `Startup` -Klasse die Stamm Komponenten für die APP und wo Sie gerendert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-136">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="03dbd-137">Wir werfen einen tieferen Einblick in die- `Startup` Klasse im Abschnitt [App-Start](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="03dbd-137">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="03dbd-138">Statische Dateien</span><span class="sxs-lookup"><span data-stu-id="03dbd-138">Static files</span></span>

<span data-ttu-id="03dbd-139">Im Gegensatz zu ASP.net-Web Forms Projekten können nicht alle Dateien in einem Blazor Projekt als statische Dateien angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-139">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="03dbd-140">Nur die Dateien im Ordner " *wwwroot* " sind webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="03dbd-140">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="03dbd-141">Dieser Ordner wird als "Web Root" der APP bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="03dbd-141">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="03dbd-142">Alles außerhalb des webstamms der APP *ist nicht* webadressierbar.</span><span class="sxs-lookup"><span data-stu-id="03dbd-142">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="03dbd-143">Dieses Setup bietet ein zusätzliches Maß an Sicherheit, das eine versehentliche Offenlegung von Projektdateien über das Internet verhindert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-143">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="03dbd-144">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="03dbd-144">Configuration</span></span>

<span data-ttu-id="03dbd-145">Die Konfiguration in ASP.net Web Forms-apps wird in der Regel mit einer oder mehreren *web.config* Dateien gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="03dbd-145">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="03dbd-146">Blazor Apps verfügen in der Regel nicht über *web.config* Dateien.</span><span class="sxs-lookup"><span data-stu-id="03dbd-146">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="03dbd-147">Wenn dies der Fall ist, wird die Datei nur zum Konfigurieren von IIS-spezifischen Einstellungen verwendet, wenn Sie auf IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-147">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="03dbd-148">Stattdessen Blazor verwenden Server-Apps die ASP.net Core Konfigurations Abstraktionen ( Blazor WebAssembly apps unterstützen derzeit nicht dieselben Konfigurations Abstraktionen, aber dies kann ein in der Zukunft hinzugefügtes Feature sein).</span><span class="sxs-lookup"><span data-stu-id="03dbd-148">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="03dbd-149">Beispielsweise werden in der Standard Blazor Server-App einige Einstellungen in *appsettings.js* gespeichert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-149">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="03dbd-150">Weitere Informationen zur Konfiguration finden Sie unter ASP.net Core-Projekte im Abschnitt " [Konfiguration](./config.md) ".</span><span class="sxs-lookup"><span data-stu-id="03dbd-150">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="03dbd-151">Razor-Komponenten</span><span class="sxs-lookup"><span data-stu-id="03dbd-151">Razor components</span></span>

<span data-ttu-id="03dbd-152">Die meisten Dateien in Blazor Projekten sind *Razor* -Dateien.</span><span class="sxs-lookup"><span data-stu-id="03dbd-152">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="03dbd-153">Razor ist eine Vorlagen Sprache, die auf HTML und c# basiert und zum dynamischen Generieren der Webbenutzer Oberfläche verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-153">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="03dbd-154">Die *Razor* -Dateien definieren Komponenten, aus denen die Benutzeroberfläche der APP besteht.</span><span class="sxs-lookup"><span data-stu-id="03dbd-154">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="03dbd-155">Zum größten Teil sind die Komponenten sowohl für den Blazor Server als auch für die Blazor WebAssembly apps identisch.</span><span class="sxs-lookup"><span data-stu-id="03dbd-155">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="03dbd-156">Komponenten in entsprechen Blazor den Benutzer Steuerelementen in ASP.net-Web Forms.</span><span class="sxs-lookup"><span data-stu-id="03dbd-156">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="03dbd-157">Jede Razor-Komponenten Datei wird in eine .NET-Klasse kompiliert, wenn das Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-157">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="03dbd-158">Die generierte-Klasse erfasst den Zustand der Komponente, die Renderinglogik, Lebenszyklus Methoden, Ereignishandler und andere Logik.</span><span class="sxs-lookup"><span data-stu-id="03dbd-158">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="03dbd-159">Wir werden uns mit der Erstellung von Komponenten im Abschnitt [Erstellen wiederverwendbarer UI- Blazor Komponenten mit](./components.md) beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-159">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="03dbd-160">Die *_Imports. Razor* -Dateien sind keine Razor-Komponenten Dateien.</span><span class="sxs-lookup"><span data-stu-id="03dbd-160">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="03dbd-161">Stattdessen definieren Sie einen Satz von Razor-Direktiven, die in andere *Razor* -Dateien im selben Ordner und in den zugehörigen Unterordnern importiert werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-161">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="03dbd-162">Beispielsweise ist eine *_Imports. Razor* -Datei ein herkömmliches Verfahren zum Hinzufügen `using` von Direktiven für häufig verwendete Namespaces:</span><span class="sxs-lookup"><span data-stu-id="03dbd-162">For example, a *_Imports.razor* file is a conventional way to add `using` directives for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="03dbd-163">Seiten</span><span class="sxs-lookup"><span data-stu-id="03dbd-163">Pages</span></span>

<span data-ttu-id="03dbd-164">Wo befinden sich die Seiten in den Blazor apps?</span><span class="sxs-lookup"><span data-stu-id="03dbd-164">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="03dbd-165">Blazor definiert keine separate Dateierweiterung für adressierbare Seiten, wie z. b. die *aspx* -Dateien in ASP.net-Web Forms-apps.</span><span class="sxs-lookup"><span data-stu-id="03dbd-165">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="03dbd-166">Stattdessen werden Seiten durch Zuweisen von Routen zu Komponenten definiert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-166">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="03dbd-167">Eine Route wird in der Regel mithilfe der `@page` Razor-Direktive zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="03dbd-167">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="03dbd-168">Die `Counter` in der Datei *pages/Counter. Razor* erstellte Komponente definiert z. b. die folgende Route:</span><span class="sxs-lookup"><span data-stu-id="03dbd-168">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="03dbd-169">Das Routing in Blazor erfolgt auf Clientseite, nicht auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="03dbd-169">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="03dbd-170">Wenn der Benutzer im Browser navigiert, Blazor fängt die Navigation ab und rendert die Komponente dann mit der passenden Route.</span><span class="sxs-lookup"><span data-stu-id="03dbd-170">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="03dbd-171">Die Komponenten Routen werden zurzeit nicht durch den Datei Speicherort der Komponente abgeleitet, z. b. mit *aspx* -Seiten.</span><span class="sxs-lookup"><span data-stu-id="03dbd-171">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="03dbd-172">Diese Funktion kann in Zukunft hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-172">This feature may be added in the future.</span></span> <span data-ttu-id="03dbd-173">Jede Route muss explizit für die Komponente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-173">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="03dbd-174">Das Speichern von Routing fähigen Komponenten in einem *Seiten* Ordner hat keine besondere Bedeutung und ist rein eine Konvention.</span><span class="sxs-lookup"><span data-stu-id="03dbd-174">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="03dbd-175">Weitere Details finden Sie im Blazor Abschnitt " [Seiten, Routing und Layouts](./pages-routing-layouts.md) " unter Routing in.</span><span class="sxs-lookup"><span data-stu-id="03dbd-175">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="03dbd-176">Layout</span><span class="sxs-lookup"><span data-stu-id="03dbd-176">Layout</span></span>

<span data-ttu-id="03dbd-177">In ASP.net Web Forms-apps wird ein gängiges Seitenlayout mithilfe von Masterseiten (*Site. Master*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="03dbd-177">In ASP.NET Web Forms apps, a common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="03dbd-178">In- Blazor apps wird das Seitenlayout mithilfe von Layoutkomponenten (*Shared/MainLayout. Razor*) behandelt.</span><span class="sxs-lookup"><span data-stu-id="03dbd-178">In Blazor apps, the page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="03dbd-179">Layoutkomponenten werden im Abschnitt "Seite" [, "Routing" und "Layouts](./pages-routing-layouts.md) " ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-179">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-no-locblazor"></a><span data-ttu-id="03dbd-180">Bootstrap Blazor</span><span class="sxs-lookup"><span data-stu-id="03dbd-180">Bootstrap Blazor</span></span>

<span data-ttu-id="03dbd-181">Zum Bootstrapping Blazor muss die app folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="03dbd-181">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="03dbd-182">Geben Sie an, wo auf der Seite die Stamm Komponente (*app. Razor*) gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03dbd-182">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="03dbd-183">Fügen Sie das entsprechende Blazor Framework-Skript hinzu.</span><span class="sxs-lookup"><span data-stu-id="03dbd-183">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="03dbd-184">In der Blazor Server-APP wird die Hostseite der Stamm Komponente in der Datei *_Host. cshtml* definiert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-184">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="03dbd-185">Diese Datei definiert eine Razor-Seite und keine Komponente.</span><span class="sxs-lookup"><span data-stu-id="03dbd-185">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="03dbd-186">Razor Pages verwenden Sie Razor-Syntax, um eine Server adressierbare Seite zu definieren, ähnlich wie eine *aspx* -Seite.</span><span class="sxs-lookup"><span data-stu-id="03dbd-186">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="03dbd-187">Die- `Html.RenderComponentAsync<TComponent>(RenderMode)` Methode wird verwendet, um zu definieren, wo eine Komponente auf Stamm Ebene gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03dbd-187">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="03dbd-188">Die- `RenderMode` Option gibt die Art an, in der die Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03dbd-188">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="03dbd-189">In der folgenden Tabelle werden die unterstützten `RenderMode` Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03dbd-189">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="03dbd-190">Option</span><span class="sxs-lookup"><span data-stu-id="03dbd-190">Option</span></span>                        |<span data-ttu-id="03dbd-191">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03dbd-191">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="03dbd-192">Wird interaktiv gerendert, sobald eine Verbindung mit dem Browser hergestellt wurde</span><span class="sxs-lookup"><span data-stu-id="03dbd-192">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="03dbd-193">Zuerst vorab und dann interaktiv gerendert</span><span class="sxs-lookup"><span data-stu-id="03dbd-193">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="03dbd-194">Als statischer Inhalt gerendert</span><span class="sxs-lookup"><span data-stu-id="03dbd-194">Rendered as static content</span></span>|

<span data-ttu-id="03dbd-195">Der Skript Verweis auf *_framework/blazor.server.js* stellt die Echtzeitverbindung mit dem Server her und befasst sich mit allen Benutzerinteraktionen und Aktualisierungen der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="03dbd-195">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="03dbd-196">In der Blazor WebAssembly App ist die Hostseite eine einfache statische HTML-Datei unter *wwwroot/index.html*.</span><span class="sxs-lookup"><span data-stu-id="03dbd-196">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="03dbd-197">Das- `<div>` Element mit der ID "" `app` wird verwendet, um anzugeben, wo die Stamm Komponente gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="03dbd-197">The `<div>` element with id named `app` is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="03dbd-198">Die Stamm Komponente zum Rendering wird in der-Methode der APP angegeben `Program.Main` und bietet die Flexibilität, Dienste über die Abhängigkeitsinjektion zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="03dbd-198">The root component to render is specified in the app's `Program.Main` method with the flexibility to register services through dependency injection.</span></span> <span data-ttu-id="03dbd-199">Weitere Informationen finden Sie unter [ASP.net Core- Blazor Abhängigkeitsinjektion](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).</span><span class="sxs-lookup"><span data-stu-id="03dbd-199">For more information, see [ASP.NET Core Blazor dependency injection](/aspnet/core/blazor/fundamentals/dependency-injection?pivots=webassembly).</span></span>

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

## <a name="build-output"></a><span data-ttu-id="03dbd-200">Erstellen der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="03dbd-200">Build output</span></span>

<span data-ttu-id="03dbd-201">Wenn ein Blazor Projekt erstellt wird, werden alle Razor-Komponenten-und Code Dateien in eine einzelne Assembly kompiliert.</span><span class="sxs-lookup"><span data-stu-id="03dbd-201">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="03dbd-202">Im Gegensatz zu ASP.net-Web Forms Projekten Blazor unterstützt keine Lauf Zeit Kompilierung der UI-Logik.</span><span class="sxs-lookup"><span data-stu-id="03dbd-202">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="03dbd-203">Ausführen der App</span><span class="sxs-lookup"><span data-stu-id="03dbd-203">Run the app</span></span>

<span data-ttu-id="03dbd-204">Um die Blazor Server-App auszuführen, drücken Sie `F5` in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="03dbd-204">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="03dbd-205">Blazor Apps unterstützen keine Lauf Zeit Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="03dbd-205">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="03dbd-206">Um die Ergebnisse von Code-und Komponenten Markup Änderungen anzuzeigen, müssen Sie die APP mit dem angefügten Debugger neu erstellen und neu starten.</span><span class="sxs-lookup"><span data-stu-id="03dbd-206">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="03dbd-207">Wenn Sie ausführen, ohne dass der Debugger angefügt `Ctrl+F5` ist (), beobachtet Visual Studio die Dateiänderungen und startet die APP neu, sobald Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-207">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="03dbd-208">Sie müssen den Browser manuell aktualisieren, wenn Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="03dbd-208">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="03dbd-209">Blazor WebAssembly Wählen Sie einen der folgenden Ansätze aus, um die APP auszuführen:</span><span class="sxs-lookup"><span data-stu-id="03dbd-209">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="03dbd-210">Führen Sie das Client Projekt direkt mit dem Development Server aus.</span><span class="sxs-lookup"><span data-stu-id="03dbd-210">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="03dbd-211">Führen Sie das Server Projekt aus, wenn die APP mit ASP.net Core gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="03dbd-211">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="03dbd-212">BlazorWebAssemblyApps können sowohl in Browser als auch in Visual Studio debuggt werden. Weitere Informationen finden Sie in der [Debug-ASP.net Core Blazor WebAssembly ](/aspnet/core/blazor/debug) .</span><span class="sxs-lookup"><span data-stu-id="03dbd-212">Blazor WebAssembly apps can be debugged in both browser and Visual Studio.See [Debug ASP.NET Core Blazor WebAssembly](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="03dbd-213">[Zurück](hosting-models.md)
>[Weiter](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="03dbd-213">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
