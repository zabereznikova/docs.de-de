---
title: Portieren auf .NET Core – Analysieren der Abhängigkeiten von Drittanbietern
description: Erfahren Sie, wie Sie Drittanbieterabhängigkeiten analysieren können, um Ihr Projekt von .NET Framework auf .NET Core portieren zu können.
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: be8d5a60977c7863136a1661a60e3bf23c0eb93e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="analyze-your-third-party-dependencies"></a><span data-ttu-id="8c190-103">Analysieren Ihrer Drittanbieterabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="8c190-103">Analyze your third-party dependencies</span></span>

<span data-ttu-id="8c190-104">Wenn Sie Ihren Code auf .NET Core oder .NET Standard portieren möchten, ist der erste Schritt zum Portieren das Verstehen Ihrer Drittanbieterabhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="8c190-104">If you're looking to port your code to .NET Core or .NET Standard, the first step in the porting process is to understand your third-party dependencies.</span></span> <span data-ttu-id="8c190-105">Drittanbieterabhängigkeiten sind entweder [NuGet-Pakete](#analyze-referenced-nuget-packages-on-your-project) oder [DLLs](#analyze-dependencies-that-arent-nuget-packages), auf die Sie in Ihrem Projekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="8c190-105">Third-party dependencies are either [NuGet packages](#analyze-referenced-nuget-packages-on-your-project) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you're referencing in your project.</span></span> <span data-ttu-id="8c190-106">Bewerten Sie jede Abhängigkeit, und entwickeln Sie einen Alternativplan für Abhängigkeiten, die nicht mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8c190-106">Evaluate each dependency and develop a contingency plan for the dependencies that aren't compatible with .NET Core.</span></span> <span data-ttu-id="8c190-107">In diesem Artikel wird gezeigt, wie Sie bestimmen, ob die Abhängigkeit mit .NET Core kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8c190-107">This article shows you how to determine if the dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-project"></a><span data-ttu-id="8c190-108">Analysieren von NuGet-Paketen, auf die in Ihrem Projekt verwiesen wird</span><span class="sxs-lookup"><span data-stu-id="8c190-108">Analyze referenced NuGet packages in your project</span></span>

<span data-ttu-id="8c190-109">Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, müssen Sie überprüfen, ob diese mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8c190-109">If you're referencing NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="8c190-110">Es gibt zwei Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="8c190-110">There are two ways to accomplish that:</span></span>

* <span data-ttu-id="8c190-111">[Die NuGet-Paket-Explorer-App](#analyze-nuget-packages-using-nuget-package-explorer) (am zuverlässigsten).</span><span class="sxs-lookup"><span data-stu-id="8c190-111">[Using the NuGet Package Explorer app](#analyze-nuget-packages-using-nuget-package-explorer) (the most reliable method).</span></span>
* <span data-ttu-id="8c190-112">[die Website nuget.org](#analyze-nuget-packages-using-nugetorg).</span><span class="sxs-lookup"><span data-stu-id="8c190-112">[Using the nuget.org site](#analyze-nuget-packages-using-nugetorg).</span></span>

<span data-ttu-id="8c190-113">Wenn sich bei der Analyse herausstellt, dass die Pakete nicht mit .NET Core sondern nur mit .NET Framework kompatibel sind, können Sie prüfen, ob der [.NET Framework-Kompatibilitätsmodus](#net-framework-compatibility-mode) Ihnen beim Portieren helfen kann.</span><span class="sxs-lookup"><span data-stu-id="8c190-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="8c190-114">Analysieren von NuGet-Paketen mit dem NuGet-Paket-Explorer</span><span class="sxs-lookup"><span data-stu-id="8c190-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="8c190-115">Ein NuGet-Paket besteht wiederum aus mehreren Ordnern, die plattformspezifische Assemblys enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c190-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="8c190-116">Also müssen Sie prüfen, ob es im Paket einen Ordner gibt, der eine kompatible Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="8c190-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="8c190-117">Am einfachsten überprüfen Sie die NuGet-Paket-Ordner mit dem Tool [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).</span><span class="sxs-lookup"><span data-stu-id="8c190-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="8c190-118">Führen Sie nach der Installation folgende Schritte durch, um die Ordnernamen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8c190-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="8c190-119">Öffnen Sie den NuGet-Paket-Explorer.</span><span class="sxs-lookup"><span data-stu-id="8c190-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="8c190-120">Klicken Sie auf **Open package from online feed** (Paket über Onlinefeed öffnen).</span><span class="sxs-lookup"><span data-stu-id="8c190-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="8c190-121">Suchen Sie nach dem Namen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="8c190-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="8c190-122">Wählen Sie den Paketnamen aus den Suchergebnissen aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8c190-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="8c190-123">Erweitern Sie den Ordner *Lib* (Bibliotheken) auf der rechten Seite, und suchen Sie in den Ordnernamen.</span><span class="sxs-lookup"><span data-stu-id="8c190-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="8c190-124">Suchen Sie nach einem Ordner mit einem der folgenden Namen:</span><span class="sxs-lookup"><span data-stu-id="8c190-124">Look for a folder with any of the following names:</span></span>

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
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="8c190-125">Bei diesen Werten handelt es sich um [Target Framework Moniker (TFMs)](../../standard/frameworks.md), die den Versionen des [.NET-Standard](../../standard/net-standard.md) und .NET Core-Profils und der herkömmlichen PCL-Profilen (Portable Class Library) zugeordnet sind, die mit .NET Core kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8c190-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c190-126">Beachten Sie bei TFMs, die von einem Paket unterstützt werden, dass `netcoreapp*` trotz Kompatibilität, nur für .NET Core-Projekte konzipiert ist und nicht für .NET Standard-Projekte.</span><span class="sxs-lookup"><span data-stu-id="8c190-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="8c190-127">Eine Bibliothek, die nur auf `netcoreapp*` und nicht auf `netstandard*` ausgerichtet ist, kann nur von anderen .NET Core-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c190-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

<span data-ttu-id="8c190-128">Es gibt auch einige ältere TFMs, die in Vorabversionen von .NET Core verwendet wurden, die möglicherweise ebenfalls kompatibel sind:</span><span class="sxs-lookup"><span data-stu-id="8c190-128">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="8c190-129">Die Wahrscheinlichkeit ist hoch, dass diese TFMs mit Ihrem Code funktionieren, eine Garantie für die Kompatibilität besteht jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="8c190-129">While these TFMs likely work with your code, there is no guarantee of compatibility.</span></span> <span data-ttu-id="8c190-130">Pakete mit diesen TFMs wurden mit der Vorabversion von .NET Core-Paketen erstellt.</span><span class="sxs-lookup"><span data-stu-id="8c190-130">Packages with these TFMs were built with pre-release .NET Core packages.</span></span> <span data-ttu-id="8c190-131">Achten Sie darauf, wann (und ob) Pakete, die diese TFMs verwenden, auf .NET Standard aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c190-131">Take note of when (or if) packages using these TFMs are updated to be .NET Standard-based.</span></span>

> [!NOTE]
> <span data-ttu-id="8c190-132">Wenn Sie ein Paket, das auf eine herkömmliche PCL oder Vorabversion von .NET Core ausrichtet ist, verwenden möchten, müssen Sie das `PackageTargetFallback`-MSBuild-Element in Ihrer Projektdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c190-132">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `PackageTargetFallback` MSBuild element in your project file.</span></span>
> <span data-ttu-id="8c190-133">Weitere Informationen zu diesem MSBuild-Element finden Sie unter [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span><span class="sxs-lookup"><span data-stu-id="8c190-133">For more information about this MSBuild element, see [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="8c190-134">Analysieren von NuGet-Paketen mit nuget.org</span><span class="sxs-lookup"><span data-stu-id="8c190-134">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="8c190-135">Alternativ können Sie unter [nuget.org](https://www.nuget.org/) im Abschnitt **Dependencies** (Abhängigkeiten) der Seite für jedes Paket auch sehen, welche TFMs von einem Paket unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8c190-135">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="8c190-136">Es ist leichter, die Website zum Überprüfen der Kompatibilität zu verwenden. Allerdings stehen dort nicht für alle **Abhängigkeiten** Informationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8c190-136">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="8c190-137">Der .NET Framework-Kompatibilitätsmodus</span><span class="sxs-lookup"><span data-stu-id="8c190-137">.NET Framework compatibility mode</span></span>

<span data-ttu-id="8c190-138">Nachdem Sie die NuGet-Pakete analysiert haben, zeigt sich möglicherweise, dass sie nur auf .NET Framework ausgerichtet sind, wie dies bei den meisten NuGet-Paketen der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="8c190-138">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="8c190-139">Mit .NET Standard 2.0 wurde der .NET Framework-Kompatibilitätsmodus eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8c190-139">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="8c190-140">Mit diesem Kompatibilitätsmodus können .NET Standard- und .NET Core-Projekte auf .NET Framework-Bibliotheken verweisen.</span><span class="sxs-lookup"><span data-stu-id="8c190-140">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="8c190-141">Das Verweisen auf .NET Framework-Bibliotheken funktioniert nicht bei allen Projekten. So funktioniert es z.B. nicht, wenn die Bibliothek Windows Presentation Foundation-APIs (WPF) verwendet. Dadurch werden jedoch viele Portierungsszenarios ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8c190-141">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="8c190-142">Wenn Sie in Ihrem Projekt auf NuGet-Pakete verweisen, die auf .NET Framework ausgerichtet sind, wie z.B. [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), wird eine Paketfallbackwarnung ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) wie die folgende ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="8c190-142">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="8c190-143">Diese Warnung wird angezeigt, wenn Sie das Paket hinzufügen und jedes Mal, wenn Sie etwas erstellen, um sicherzustellen, dass Sie das Paket mit Ihrem Projekt testen.</span><span class="sxs-lookup"><span data-stu-id="8c190-143">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="8c190-144">Wenn Ihr Projekt wie gewünscht funktioniert, können Sie die Warnung unterdrücken, indem Sie die Paketeigenschaften in Visual Studio bearbeiten oder die Projektdatei in Ihrem bevorzugten Code-Editor manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c190-144">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="8c190-145">Um die Warnung durch Bearbeiten der Projektdatei zu unterdrücken, suchen Sie den `PackageReference`-Eintrag für das Paket, für das Sie die Warnung unterdrücken möchten, und fügen Sie das `NoWarn`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c190-145">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="8c190-146">Das `NoWarn`-Attribut akzeptiert eine durch Trennzeichen getrennte Liste aller Warnungs-IDs.</span><span class="sxs-lookup"><span data-stu-id="8c190-146">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="8c190-147">Im folgenden Beispiel wird gezeigt, wie Sie die `NU1701`-Warnung für das `Huitian.PowerCollections`-Paket unterdrücken, indem Sie Ihre Projektdatei manuell bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="8c190-147">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="8c190-148">Weitere Informationen zum Unterdrücken von Compilerwarnungen in Visual Studio finden Sie unter [Unterdrücken von Compilerwarnungen](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages) im Abschnitt zum Unterdrücken von Warnungen für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="8c190-148">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="8c190-149">Vorgehensweise, wenn die NuGet-Paket-Abhängigkeit unter .NET Core nicht ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="8c190-149">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="8c190-150">Es gibt einige Dinge, die Sie tun können, wenn ein NuGet-Paket, auf das Sie angewiesen sind, unter .NET Core nicht ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="8c190-150">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="8c190-151">Wenn es sich um ein Open Source-Projekt handelt, das beispielsweise von GitHub gehostet wird, können Sie sich direkt an die Entwickler wenden.</span><span class="sxs-lookup"><span data-stu-id="8c190-151">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="8c190-152">Sie können den Autor direkt über [nuget.org](https://www.nuget.org/) kontaktieren. Suchen Sie nach dem Paket, und klicken Sie links auf der Paketseite auf **Contact Owners** (Besitzer kontaktieren).</span><span class="sxs-lookup"><span data-stu-id="8c190-152">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="8c190-153">Sie können nach einem anderen Paket suchen, das unter .NET Core ausgeführt wird und denselben Zweck erfüllt wie das Paket, das Sie bisher verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8c190-153">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="8c190-154">Sie können den vom Paket ausgeführten Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="8c190-154">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="8c190-155">Sie können die Abhängigkeit für das Paket eliminieren, indem Sie die Funktionalität Ihrer Anwendung ändern, zumindest bis eine kompatible Version des Pakets verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8c190-155">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="8c190-156">Denken Sie daran, dass Open-Source-Projektverwalter und NuGet-Paketherausgeber häufig Freiwillige sind.</span><span class="sxs-lookup"><span data-stu-id="8c190-156">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="8c190-157">Sie beteiligen sich, weil Ihnen eine bestimmte Domäne wichtig ist. Sie arbeiten daran unentgeltlich und haben häufig einen anderen Job, für den sie unter der Woche arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8c190-157">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="8c190-158">Denken Sie daran, wenn Sie sie kontaktieren, um sie nach Hilfe mit .NET Core zu fragen.</span><span class="sxs-lookup"><span data-stu-id="8c190-158">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="8c190-159">Wenn es Ihnen mit den genannten Vorschlägen nicht gelingt, Ihr Problem zu beheben, müssen Sie sich mit dem Portieren auf .NET Core noch etwas gedulden.</span><span class="sxs-lookup"><span data-stu-id="8c190-159">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="8c190-160">Das .NET-Team würde gerne wissen, welche Bibliotheken von .NET Core unterstützt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="8c190-160">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="8c190-161">Sie können uns gerne mit einer E-Mail an dotnet@microsoft.com mitteilen, welche Bibliotheken Sie gerne verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="8c190-161">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="8c190-162">Analysieren von Abhängigkeiten, bei denen es sich nicht um NuGet-Pakete handelt</span><span class="sxs-lookup"><span data-stu-id="8c190-162">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="8c190-163">Möglicherweise verfügen Sie über eine Abhängigkeit, bei der es sich nicht um ein NuGet-Paket, sondern beispielsweise um eine DLL im Dateisystem handelt.</span><span class="sxs-lookup"><span data-stu-id="8c190-163">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="8c190-164">Wenn Sie feststellen möchten, ob diese Abhängigkeit portiert werden kann, haben Sie nur die Möglichkeit, das Tool [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c190-164">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="8c190-165">Das Tool kann Assemblys analysieren, die auf .NET Framework ausgerichtet sind, und APIs identifizieren, die nicht auf andere .NET-Plattformen wie .NET Core portiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8c190-165">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="8c190-166">Sie können das Tool als Konsolenanwendung oder als [Visual Studio-Erweiterung](../../standard/analyzers/portability-analyzer.md) ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c190-166">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c190-167">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8c190-167">Next steps</span></span>

<span data-ttu-id="8c190-168">Wenn Sie eine Bibliothek portieren, lesen Sie [Portieren von Bibliotheken](libraries.md).</span><span class="sxs-lookup"><span data-stu-id="8c190-168">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
