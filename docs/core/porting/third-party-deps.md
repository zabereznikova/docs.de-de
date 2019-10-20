---
title: Analysieren von Abhängigkeiten zum Portieren von Code zu .NET Core
description: Erfahren Sie, wie Sie externe Abhängigkeiten analysieren können, um Ihr Projekt von .NET Framework auf .NET Core portieren zu können.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 36d1c1d2090a0fb9e6f48fe519d15897579df2d5
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521470"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a><span data-ttu-id="418b5-103">Analysieren Ihrer Abhängigkeiten zum Portieren von Code zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="418b5-103">Analyze your dependencies to port code to .NET Core</span></span>

<span data-ttu-id="418b5-104">Um den Code zu .NET Core oder .NET Standard portieren zu können, müssen Sie Ihre Abhängigkeiten verstehen.</span><span class="sxs-lookup"><span data-stu-id="418b5-104">To port your code to .NET Core or .NET Standard, you must understand your dependencies.</span></span> <span data-ttu-id="418b5-105">Externe Abhängigkeiten sind die [NuGet-Pakete](#analyze-referenced-nuget-packages-in-your-projects) oder [DLLs](#analyze-dependencies-that-arent-nuget-packages), auf die Sie in Ihrem Projekt verweisen, aber die Sie nicht erstellen.</span><span class="sxs-lookup"><span data-stu-id="418b5-105">External dependencies are the [NuGet packages](#analyze-referenced-nuget-packages-in-your-projects) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you reference in your project, but that you don't build.</span></span> <span data-ttu-id="418b5-106">Bewerten Sie jede Abhängigkeit, und entwickeln Sie einen Alternativplan für die, die nicht mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="418b5-106">Evaluate each dependency and develop a contingency plan for the ones that aren't compatible with .NET Core.</span></span> <span data-ttu-id="418b5-107">Hier wird gezeigt, wie Sie bestimmen, ob die Abhängigkeit mit .NET Core kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="418b5-107">Here's how to determine if a dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-projects"></a><span data-ttu-id="418b5-108">Analysieren von NuGet-Paketen, auf die in Ihrem Projekt verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="418b5-108">Analyze referenced NuGet packages in your projects</span></span>

<span data-ttu-id="418b5-109">Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, müssen Sie überprüfen, ob diese mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="418b5-109">If you reference NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="418b5-110">Es gibt zwei Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="418b5-110">There are two ways to accomplish that:</span></span>

- [<span data-ttu-id="418b5-111">Verwenden der NuGet-Paket-Explorer-App</span><span class="sxs-lookup"><span data-stu-id="418b5-111">Using the NuGet Package Explorer app</span></span>](#analyze-nuget-packages-using-nuget-package-explorer)
- [<span data-ttu-id="418b5-112">Verwenden der Website nuget.org</span><span class="sxs-lookup"><span data-stu-id="418b5-112">Using the nuget.org site</span></span>](#analyze-nuget-packages-using-nugetorg)

<span data-ttu-id="418b5-113">Wenn sich bei der Analyse herausstellt, dass die Pakete nicht mit .NET Core sondern nur mit .NET Framework kompatibel sind, können Sie prüfen, ob der [.NET Framework-Kompatibilitätsmodus](#net-framework-compatibility-mode) Ihnen beim Portieren helfen kann.</span><span class="sxs-lookup"><span data-stu-id="418b5-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="418b5-114">Analysieren von NuGet-Paketen mit dem NuGet-Paket-Explorer</span><span class="sxs-lookup"><span data-stu-id="418b5-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="418b5-115">Ein NuGet-Paket besteht wiederum aus mehreren Ordnern, die plattformspezifische Assemblys enthalten.</span><span class="sxs-lookup"><span data-stu-id="418b5-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="418b5-116">Also müssen Sie prüfen, ob es im Paket einen Ordner gibt, der eine kompatible Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="418b5-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="418b5-117">Am einfachsten überprüfen Sie die NuGet-Paket-Ordner mit dem Tool [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="418b5-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="418b5-118">Führen Sie nach der Installation folgende Schritte durch, um die Ordnernamen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="418b5-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="418b5-119">Öffnen Sie den NuGet-Paket-Explorer.</span><span class="sxs-lookup"><span data-stu-id="418b5-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="418b5-120">Klicken Sie auf **Open package from online feed** (Paket über Onlinefeed öffnen).</span><span class="sxs-lookup"><span data-stu-id="418b5-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="418b5-121">Suchen Sie nach dem Namen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="418b5-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="418b5-122">Wählen Sie den Paketnamen aus den Suchergebnissen aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="418b5-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="418b5-123">Erweitern Sie den Ordner *Lib* (Bibliotheken) auf der rechten Seite, und suchen Sie in den Ordnernamen.</span><span class="sxs-lookup"><span data-stu-id="418b5-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="418b5-124">Suchen Sie nach einem Ordner mit einem der folgenden Namen:</span><span class="sxs-lookup"><span data-stu-id="418b5-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
netcoreapp2.1
netcoreapp2.2
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="418b5-125">Bei diesen Werten handelt es sich um [Target Framework Moniker (TFMs)](../../standard/frameworks.md), die den Versionen des [.NET-Standard](../../standard/net-standard.md) und .NET Core-Profils und der herkömmlichen PCL-Profilen (Portable Class Library) zugeordnet sind, die mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="418b5-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="418b5-126">Beachten Sie bei TFMs, die von einem Paket unterstützt werden, dass `netcoreapp*` trotz Kompatibilität, nur für .NET Core-Projekte konzipiert ist und nicht für .NET Standard-Projekte.</span><span class="sxs-lookup"><span data-stu-id="418b5-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="418b5-127">Eine Bibliothek, die nur auf `netcoreapp*` und nicht auf `netstandard*` ausgerichtet ist, kann nur von anderen .NET Core-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="418b5-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="418b5-128">Analysieren von NuGet-Paketen mit nuget.org</span><span class="sxs-lookup"><span data-stu-id="418b5-128">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="418b5-129">Alternativ können Sie unter [nuget.org](https://www.nuget.org/) im Abschnitt **Dependencies** (Abhängigkeiten) der Seite für jedes Paket auch sehen, welche TFMs von einem Paket unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="418b5-129">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="418b5-130">Es ist leichter, die Website zum Überprüfen der Kompatibilität zu verwenden. Allerdings stehen dort nicht für alle **Abhängigkeiten** Informationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="418b5-130">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="418b5-131">Der .NET Framework-Kompatibilitätsmodus</span><span class="sxs-lookup"><span data-stu-id="418b5-131">.NET Framework compatibility mode</span></span>

<span data-ttu-id="418b5-132">Nachdem Sie die NuGet-Pakete analysiert haben, zeigt sich möglicherweise, dass sie nur auf .NET Framework ausgerichtet sind, wie dies bei den meisten NuGet-Paketen der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="418b5-132">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="418b5-133">Mit .NET Standard 2.0 wurde der .NET Framework-Kompatibilitätsmodus eingeführt.</span><span class="sxs-lookup"><span data-stu-id="418b5-133">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="418b5-134">Mit diesem Kompatibilitätsmodus können .NET Standard- und .NET Core-Projekte auf .NET Framework-Bibliotheken verweisen.</span><span class="sxs-lookup"><span data-stu-id="418b5-134">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="418b5-135">Das Verweisen auf .NET Framework-Bibliotheken funktioniert nicht bei allen Projekten. So funktioniert es z.B. nicht, wenn die Bibliothek Windows Presentation Foundation-APIs (WPF) verwendet. Dadurch werden jedoch viele Portierungsszenarios ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="418b5-135">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="418b5-136">Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, die auf .NET Framework ausgerichtet sind, wie z.B. [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), wird eine Paketfallbackwarnung ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) wie die folgende ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="418b5-136">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="418b5-137">Diese Warnung wird angezeigt, wenn Sie das Paket hinzufügen und jedes Mal, wenn Sie etwas erstellen, um sicherzustellen, dass Sie das Paket mit Ihrem Projekt testen.</span><span class="sxs-lookup"><span data-stu-id="418b5-137">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="418b5-138">Wenn Ihr Projekt wie gewünscht funktioniert, können Sie die Warnung unterdrücken, indem Sie die Paketeigenschaften in Visual Studio bearbeiten oder die Projektdatei in Ihrem bevorzugten Code-Editor manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="418b5-138">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="418b5-139">Um die Warnung durch Bearbeiten der Projektdatei zu unterdrücken, suchen Sie den `PackageReference`-Eintrag für das Paket, für das Sie die Warnung unterdrücken möchten, und fügen Sie das `NoWarn`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="418b5-139">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="418b5-140">Das `NoWarn`-Attribut akzeptiert eine durch Trennzeichen getrennte Liste aller Warnungs-IDs.</span><span class="sxs-lookup"><span data-stu-id="418b5-140">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="418b5-141">Im folgenden Beispiel wird gezeigt, wie Sie die `NU1701`-Warnung für das `Huitian.PowerCollections`-Paket unterdrücken, indem Sie Ihre Projektdatei manuell bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="418b5-141">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="418b5-142">Weitere Informationen zum Unterdrücken von Compilerwarnungen in Visual Studio finden Sie unter [Unterdrücken von Compilerwarnungen](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages) im Abschnitt zum Unterdrücken von Warnungen für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="418b5-142">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).</span></span>

## <a name="port-your-packages-to-packagereference"></a><span data-ttu-id="418b5-143">Portieren Sie Ihre Pakete zu `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="418b5-143">Port your packages to `PackageReference`</span></span>

<span data-ttu-id="418b5-144">.NET Core verwendet [PackageReference](/nuget/consume-packages/package-references-in-project-files) zum Angeben von Paketabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="418b5-144">.NET Core uses [PackageReference](/nuget/consume-packages/package-references-in-project-files) to specify package dependencies.</span></span> <span data-ttu-id="418b5-145">Wenn Sie [packages.config](/nuget/reference/packages-config) zum Angeben Ihrer Pakete verwenden, müssen Sie zu `PackageReference` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="418b5-145">If you are using [packages.config](/nuget/reference/packages-config) to specify your packages, you will need to convert over to `PackageReference`.</span></span>

<span data-ttu-id="418b5-146">Weitere Informationen finden Sie unter [Migrieren von „packages.config“ zu „packagereference“](/nuget/reference/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="418b5-146">You can learn more at [Migrate from packages.config to PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).</span></span>

## <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="418b5-147">Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="418b5-147">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="418b5-148">Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="418b5-148">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="418b5-149">Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an die Entwickler wenden.</span><span class="sxs-lookup"><span data-stu-id="418b5-149">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="418b5-150">Sie können den Autor direkt über [nuget.org](https://www.nuget.org/) kontaktieren. Suchen Sie nach dem Paket, und klicken Sie links auf der Paketseite auf **Contact Owners** (Besitzer kontaktieren).</span><span class="sxs-lookup"><span data-stu-id="418b5-150">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="418b5-151">Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="418b5-151">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="418b5-152">Sie können den vom Paket ausgeführten Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="418b5-152">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="418b5-153">Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="418b5-153">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="418b5-154">Denken Sie daran, dass Open-Source-Projektverwalter und NuGet-Paketherausgeber häufig Freiwillige sind.</span><span class="sxs-lookup"><span data-stu-id="418b5-154">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="418b5-155">Sie beteiligen sich, weil Ihnen eine bestimmte Domäne wichtig ist. Sie arbeiten daran unentgeltlich und haben häufig einen anderen Job, für den sie unter der Woche arbeiten.</span><span class="sxs-lookup"><span data-stu-id="418b5-155">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="418b5-156">Denken Sie daran, wenn Sie sie kontaktieren, um sie nach Hilfe mit .NET Core zu fragen.</span><span class="sxs-lookup"><span data-stu-id="418b5-156">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="418b5-157">Wenn es Ihnen mit den genannten Vorschlägen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren auf .NET Core noch etwas gedulden.</span><span class="sxs-lookup"><span data-stu-id="418b5-157">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="418b5-158">Das .NET-Team würde gerne wissen, welche Bibliotheken von .NET Core unterstützt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="418b5-158">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="418b5-159">Sie können uns gerne mit einer E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="418b5-159">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="418b5-160">Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt</span><span class="sxs-lookup"><span data-stu-id="418b5-160">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="418b5-161">Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt.</span><span class="sxs-lookup"><span data-stu-id="418b5-161">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="418b5-162">Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="418b5-162">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="418b5-163">Das Tool kann Assemblys analysieren, die auf .NET Framework ausgerichtet sind, und APIs identifizieren, die nicht auf andere .NET-Plattformen wie .NET Core portiert werden können.</span><span class="sxs-lookup"><span data-stu-id="418b5-163">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="418b5-164">Sie können das Tool als Konsolenanwendung oder als [Visual Studio-Erweiterung](../../standard/analyzers/portability-analyzer.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="418b5-164">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="418b5-165">Nächste</span><span class="sxs-lookup"><span data-stu-id="418b5-165">Next</span></span>](libraries.md)
