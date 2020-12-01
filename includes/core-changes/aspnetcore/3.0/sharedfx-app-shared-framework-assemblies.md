---
ms.openlocfilehash: d598d8d3203e804e5e935c3564b0053f9fc2e9a6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032653"
---
### <a name="shared-framework-assemblies-removed-from-microsoftaspnetcoreapp"></a><span data-ttu-id="a7587-101">Freigegebenes Framework: Assemblys aus Microsoft.AspNetCore.App entfernt</span><span class="sxs-lookup"><span data-stu-id="a7587-101">Shared framework: Assemblies removed from Microsoft.AspNetCore.App</span></span>

<span data-ttu-id="a7587-102">Ab ASP.NET Core 3.0 enthält das freigegebene ASP.NET Core-Framework (`Microsoft.AspNetCore.App`) nur Erstanbieterassemblys, die vollständig von Microsoft entwickelt, unterstützt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a7587-102">Starting in ASP.NET Core 3.0, the ASP.NET Core shared framework (`Microsoft.AspNetCore.App`) only contains first-party assemblies that are fully developed, supported, and serviceable by Microsoft.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a7587-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a7587-103">Change description</span></span>

<span data-ttu-id="a7587-104">Diese Änderung definiert die Grenzen der ASP.NET Core-„Plattform“ neu.</span><span class="sxs-lookup"><span data-stu-id="a7587-104">Think of the change as the redefining of boundaries for the ASP.NET Core "platform."</span></span> <span data-ttu-id="a7587-105">Das freigegebene Framework kann [von allen Benutzern über GitHub aus der Quelle erstellt](https://github.com/dotnet/source-build) werden. Es bietet Ihren Apps dabei auch weiterhin die bestehenden Vorteile der freigegebenen .NET Core-Frameworks von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7587-105">The shared framework will be [source-buildable by anybody via GitHub](https://github.com/dotnet/source-build) and will continue to offer the existing benefits of .NET Core shared frameworks to your apps.</span></span> <span data-ttu-id="a7587-106">Zu den Vorteilen zählen die kleinere Bereitstellungsgröße, das zentralisierte Patchen und die schnellere Startzeit.</span><span class="sxs-lookup"><span data-stu-id="a7587-106">Some benefits include smaller deployment size, centralized patching, and faster startup time.</span></span>

<span data-ttu-id="a7587-107">Im Rahmen der Änderung werden einige wichtige Breaking Changes in `Microsoft.AspNetCore.App` eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a7587-107">As part of the change, some notable breaking changes are introduced in `Microsoft.AspNetCore.App`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a7587-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a7587-108">Version introduced</span></span>

<span data-ttu-id="a7587-109">3.0</span><span class="sxs-lookup"><span data-stu-id="a7587-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a7587-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="a7587-110">Old behavior</span></span>

<span data-ttu-id="a7587-111">Projekte verwiesen über ein `<PackageReference>`-Element in der Projektdatei auf `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="a7587-111">Projects referenced `Microsoft.AspNetCore.App` via a `<PackageReference>` element in the project file.</span></span>

<span data-ttu-id="a7587-112">Außerdem enthielt `Microsoft.AspNetCore.App` die folgenden Unterkomponenten:</span><span class="sxs-lookup"><span data-stu-id="a7587-112">Additionally, `Microsoft.AspNetCore.App` contained the following subcomponents:</span></span>

- <span data-ttu-id="a7587-113">Json.NET (`Newtonsoft.Json`)</span><span class="sxs-lookup"><span data-stu-id="a7587-113">Json.NET (`Newtonsoft.Json`)</span></span>
- <span data-ttu-id="a7587-114">Entity Framework Core (Assemblys mit Präfix `Microsoft.EntityFrameworkCore.`)</span><span class="sxs-lookup"><span data-stu-id="a7587-114">Entity Framework Core (assemblies prefixed with `Microsoft.EntityFrameworkCore.`)</span></span>
- <span data-ttu-id="a7587-115">Roslyn (`Microsoft.CodeAnalysis`)</span><span class="sxs-lookup"><span data-stu-id="a7587-115">Roslyn (`Microsoft.CodeAnalysis`)</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a7587-116">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="a7587-116">New behavior</span></span>

<span data-ttu-id="a7587-117">Für einen Verweis auf `Microsoft.AspNetCore.App` ist kein `<PackageReference>`-Element in der Projektdatei mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a7587-117">A reference to `Microsoft.AspNetCore.App` no longer requires a `<PackageReference>` element in the project file.</span></span> <span data-ttu-id="a7587-118">Das .NET Core SDK unterstützt ein neues Element mit dem Namen `<FrameworkReference>`, das `<PackageReference>` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="a7587-118">The .NET Core SDK supports a new element called `<FrameworkReference>`, which replaces the use of `<PackageReference>`.</span></span>

<span data-ttu-id="a7587-119">Weitere Informationen finden Sie unter [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span><span class="sxs-lookup"><span data-stu-id="a7587-119">For more information, see [dotnet/aspnetcore#3612](https://github.com/dotnet/aspnetcore/issues/3612).</span></span>

<span data-ttu-id="a7587-120">Entity Framework Core wird als NuGet-Pakete bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7587-120">Entity Framework Core ships as NuGet packages.</span></span> <span data-ttu-id="a7587-121">Diese Änderung stellt eine Anpassung an das Auslieferungsmodell aller anderen Datenzugriffsbibliotheken in .NET dar.</span><span class="sxs-lookup"><span data-stu-id="a7587-121">This change aligns the shipping model with all other data access libraries on .NET.</span></span> <span data-ttu-id="a7587-122">Es bietet Entity Framework Core die einfachste Möglichkeit, weiterhin Innovationen mit Unterstützung der verschiedenen .NET-Plattformen zu schaffen.</span><span class="sxs-lookup"><span data-stu-id="a7587-122">It provides Entity Framework Core the simplest path to continue innovating while supporting the various .NET platforms.</span></span> <span data-ttu-id="a7587-123">Das Verschieben von Entity Framework Core aus dem freigegebenen Framework hat keine Auswirkung auf seinen Status als eine von Microsoft entwickelte, unterstützte und gewartete Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="a7587-123">The move of Entity Framework Core out of the shared framework has no impact on its status as a Microsoft-developed, supported, and serviceable library.</span></span> <span data-ttu-id="a7587-124">Die [.NET Core-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) gilt auch weiterhin.</span><span class="sxs-lookup"><span data-stu-id="a7587-124">The [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) continues to cover it.</span></span>

<span data-ttu-id="a7587-125">Json.NET und Entity Framework Core funktionieren auch In Zukunft mit ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7587-125">Json.NET and Entity Framework Core continue to work with ASP.NET Core.</span></span> <span data-ttu-id="a7587-126">Sie sind jedoch nicht mehr im freigegebenen Framework enthalten.</span><span class="sxs-lookup"><span data-stu-id="a7587-126">They won't, however, be included in the shared framework.</span></span>

<span data-ttu-id="a7587-127">Weitere Informationen finden Sie unter [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90) (Die Zukunft von JSON in .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="a7587-127">For more information, see [The future of JSON in .NET Core 3.0](https://github.com/dotnet/announcements/issues/90).</span></span> <span data-ttu-id="a7587-128">Sehen Sie sich auch [die komplette Liste der Binärdateien](https://github.com/dotnet/aspnetcore/issues/3755) an, die aus dem freigegebenen Framework entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="a7587-128">Also see [the complete list of binaries](https://github.com/dotnet/aspnetcore/issues/3755) removed from the shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a7587-129">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a7587-129">Reason for change</span></span>

<span data-ttu-id="a7587-130">Diese Änderung vereinfacht die Verwendung von `Microsoft.AspNetCore.App` und verringert Duplizierungen zwischen NuGet-Paketen und freigegebenen Frameworks.</span><span class="sxs-lookup"><span data-stu-id="a7587-130">This change simplifies the consumption of `Microsoft.AspNetCore.App` and reduces the duplication between NuGet packages and shared frameworks.</span></span>

<span data-ttu-id="a7587-131">Weitere Informationen zu den Gründen für diese Änderung finden Sie in [diesem Blogbeitrag](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="a7587-131">For more information on the motivation for this change, see [this blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a7587-132">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a7587-132">Recommended action</span></span>

<span data-ttu-id="a7587-133">Projekte müssen Assemblys in `Microsoft.AspNetCore.App` nicht als NuGet-Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7587-133">It won't be necessary for projects to consume assemblies in `Microsoft.AspNetCore.App` as NuGet packages.</span></span> <span data-ttu-id="a7587-134">Um die Ausrichtung und Verwendung des freigegebenen ASP.NET Core-Frameworks zu vereinfachen, werden viele NuGet-Pakete, die seit ASP.NET Core 1.0 eingeführt wurden, nicht mehr erstellt.</span><span class="sxs-lookup"><span data-stu-id="a7587-134">To simplify the targeting and usage of the ASP.NET Core shared framework, many NuGet packages shipped since ASP.NET Core 1.0 are no longer produced.</span></span> <span data-ttu-id="a7587-135">Die von diesen Paketen bereitgestellten APIs sind für Apps weiterhin mithilfe eines `<FrameworkReference>` auf `Microsoft.AspNetCore.App` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a7587-135">The APIs those packages provide are still available to apps by using a `<FrameworkReference>` to `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="a7587-136">Beispiele für gängige APIs sind Kestrel, MVC und Razor.</span><span class="sxs-lookup"><span data-stu-id="a7587-136">Common API examples include Kestrel, MVC, and Razor.</span></span>

<span data-ttu-id="a7587-137">Diese Änderung gilt nicht für alle Binärdateien, auf die über `Microsoft.AspNetCore.App` in ASP.NET Core 2.x verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a7587-137">This change doesn't apply to all binaries referenced via `Microsoft.AspNetCore.App` in ASP.NET Core 2.x.</span></span> <span data-ttu-id="a7587-138">Wichtige Ausnahmen sind:</span><span class="sxs-lookup"><span data-stu-id="a7587-138">Notable exceptions include:</span></span>

- <span data-ttu-id="a7587-139">`Microsoft.Extensions`-Bibliotheken, die weiterhin auf .NET Standard abzielen, werden als NuGet-Pakete zur Verfügung gestellt (siehe <https://github.com/dotnet/extensions>).</span><span class="sxs-lookup"><span data-stu-id="a7587-139">`Microsoft.Extensions` libraries that continue to target .NET Standard will be available as NuGet packages (see <https://github.com/dotnet/extensions>).</span></span>
- <span data-ttu-id="a7587-140">APIs, die vom ASP.NET Core-Team erstellt werden und die nicht Teil `Microsoft.AspNetCore.App` sind.</span><span class="sxs-lookup"><span data-stu-id="a7587-140">APIs produced by the ASP.NET Core team that aren't part of `Microsoft.AspNetCore.App`.</span></span> <span data-ttu-id="a7587-141">Die folgenden Komponenten sind beispielsweise als NuGet-Pakete verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a7587-141">For example, the following components are available as NuGet packages:</span></span>
  - <span data-ttu-id="a7587-142">Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="a7587-142">Entity Framework Core</span></span>
  - <span data-ttu-id="a7587-143">APIs, die eine Integration von Drittanbietern bereitstellen</span><span class="sxs-lookup"><span data-stu-id="a7587-143">APIs that provide third-party integration</span></span>
  - <span data-ttu-id="a7587-144">Experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="a7587-144">Experimental features</span></span>
  - <span data-ttu-id="a7587-145">APIs mit Abhängigkeiten, die die [Anforderungen für die Aufnahme in das freigegebene Framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md) nicht erfüllen konnten</span><span class="sxs-lookup"><span data-stu-id="a7587-145">APIs with dependencies that couldn't [fulfill the requirements to be in the shared framework](https://github.com/dotnet/aspnetcore/blob/4e44e5bcbedd961cc0d4f6b846699c7c494f5597/docs/SharedFramework.md)</span></span>
- <span data-ttu-id="a7587-146">Erweiterungen für MVC zur Unterstützung von Json.NET.</span><span class="sxs-lookup"><span data-stu-id="a7587-146">Extensions to MVC that maintain support for Json.NET.</span></span> <span data-ttu-id="a7587-147">Eine API wird als NuGet-Paket bereitgestellt, um die Verwendung von Json.NET und MVC zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7587-147">An API will be provided as a NuGet package to support using Json.NET and MVC.</span></span>
- <span data-ttu-id="a7587-148">Der SignalR-.NET-Client unterstützt weiterhin .NET Standard und wird als NuGet-Paket bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7587-148">The SignalR .NET client will continue to support .NET Standard and ship as a NuGet package.</span></span> <span data-ttu-id="a7587-149">Er ist für die Verwendung in vielen .NET-Runtimes vorgesehen, z. B. Xamarin und UWP.</span><span class="sxs-lookup"><span data-stu-id="a7587-149">It's intended for use on many .NET runtimes, such as Xamarin and UWP.</span></span>

<span data-ttu-id="a7587-150">Weitere Informationen finden Sie unter [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756) (Beenden der Erstellung von Paketen für Assemblys in freigegebenen Frameworks in 3.0).</span><span class="sxs-lookup"><span data-stu-id="a7587-150">For more information, see [Stop producing packages for shared framework assemblies in 3.0](https://github.com/dotnet/aspnetcore/issues/3756).</span></span> <span data-ttu-id="a7587-151">Weitere Informationen finden Sie unter [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span><span class="sxs-lookup"><span data-stu-id="a7587-151">For discussion, see [dotnet/aspnetcore#3757](https://github.com/dotnet/aspnetcore/issues/3757).</span></span>

#### <a name="category"></a><span data-ttu-id="a7587-152">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a7587-152">Category</span></span>

<span data-ttu-id="a7587-153">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a7587-153">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a7587-154">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a7587-154">Affected APIs</span></span>

- <xref:Microsoft.CodeAnalysis?displayProperty=nameWithType>
- <xref:Microsoft.EntityFrameworkCore?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.CodeAnalysis`
- `N:Microsoft.EntityFrameworkCore`

-->
