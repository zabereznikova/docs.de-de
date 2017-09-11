---
title: CSPROJ-Referenz
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 63c7a6f0aa3a926c7ae01ad6c434ecf296c81811
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="819fe-104">Erweiterungen des CSPROJ-Formats für .NET Core</span><span class="sxs-lookup"><span data-stu-id="819fe-104">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="819fe-105">In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="819fe-105">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="819fe-106">Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="819fe-106">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="819fe-107">Implizite Paketverweise</span><span class="sxs-lookup"><span data-stu-id="819fe-107">Implicit package references</span></span>
<span data-ttu-id="819fe-108">Es wird implizit auf Metapakete verwiesen, basierend auf der Grundlage des/der Zielfameworks, das/die in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde/n.</span><span class="sxs-lookup"><span data-stu-id="819fe-108">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="819fe-109">`<TargetFrameworks>` wird ignoriert, wenn `<TargetFramework>` angegeben wird, egal wie die Reihenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="819fe-109">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp1.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp1.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="819fe-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="819fe-110">Recommendations</span></span>
<span data-ttu-id="819fe-111">Da implizit auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="819fe-111">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="819fe-112">Es darf nie ein expliziter Verweis auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete über das `<PackageReference>`-Element in Ihrer Projektdatei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="819fe-112">Never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="819fe-113">Wenn Sie eine bestimmte Version der Laufzeit benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="819fe-113">If you need a specific version of the runtime, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="819fe-114">Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="819fe-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="819fe-115">Sollten Sie eine bestimmte Version der `NetStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="819fe-115">If you need a specific version of the `NetStandard.Library` metapackage, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span> 

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="819fe-116">Standardkompilierung in .NET Core-Projekten</span><span class="sxs-lookup"><span data-stu-id="819fe-116">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="819fe-117">Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="819fe-117">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="819fe-118">Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="819fe-118">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="819fe-119">Der Hauptgrund dafür ist die Übersichtlichkeit in Ihrer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="819fe-119">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="819fe-120">Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="819fe-120">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="819fe-121">Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind.</span><span class="sxs-lookup"><span data-stu-id="819fe-121">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="819fe-122">Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im SDK enthalten und ausgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="819fe-122">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="819fe-123">Element</span><span class="sxs-lookup"><span data-stu-id="819fe-123">Element</span></span>           | <span data-ttu-id="819fe-124">Glob einschließen</span><span class="sxs-lookup"><span data-stu-id="819fe-124">Include glob</span></span>                              | <span data-ttu-id="819fe-125">Glob ausschließen</span><span class="sxs-lookup"><span data-stu-id="819fe-125">Exclude glob</span></span>                                                  | <span data-ttu-id="819fe-126">Glob entfernen</span><span class="sxs-lookup"><span data-stu-id="819fe-126">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="819fe-127">Compile</span><span class="sxs-lookup"><span data-stu-id="819fe-127">Compile</span></span>           | <span data-ttu-id="819fe-128">\*\*/\*.cs (oder andere Spracherweiterungen)</span><span class="sxs-lookup"><span data-stu-id="819fe-128">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="819fe-129">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="819fe-129">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="819fe-130">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="819fe-130">N/A</span></span>                        |
| <span data-ttu-id="819fe-131">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="819fe-131">EmbeddedResource</span></span>  | <span data-ttu-id="819fe-132">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="819fe-132">\*\*/\*.resx</span></span>                              | <span data-ttu-id="819fe-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="819fe-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="819fe-134">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="819fe-134">N/A</span></span>                        |
| <span data-ttu-id="819fe-135">Keine</span><span class="sxs-lookup"><span data-stu-id="819fe-135">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="819fe-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="819fe-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="819fe-137">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="819fe-137">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="819fe-138">Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="819fe-138">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="819fe-139">Doppelte Compile-Elemente waren enthalten.</span><span class="sxs-lookup"><span data-stu-id="819fe-139">Duplicate Compile items were included.</span></span> <span data-ttu-id="819fe-140">.NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="819fe-140">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="819fe-141">Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="819fe-141">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="819fe-142">Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="819fe-142">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="819fe-143">Wenn diese Eigenschaft auf `false` festgelegt wird, wird die implizite Aufnahme überschrieben, und das Verhalten wird wieder auf die früheren SDKs gesetzt, als Sie die Standardglobs in Ihrem Projekt angeben mussten.</span><span class="sxs-lookup"><span data-stu-id="819fe-143">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="819fe-144">Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht.</span><span class="sxs-lookup"><span data-stu-id="819fe-144">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="819fe-145">Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).</span><span class="sxs-lookup"><span data-stu-id="819fe-145">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

### <a name="recommendation"></a><span data-ttu-id="819fe-146">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="819fe-146">Recommendation</span></span>
<span data-ttu-id="819fe-147">Für csproj empfehlen wir, dass Sie die Standardglobs aus Ihrem Projekt entfernen und nur Dateipfade mit Globs für die Artefakte hinzufügen, die Ihre App/Bibliothek für verschiedene Szenarios benötigt (z.B. Runtime und NuGet-Paket).</span><span class="sxs-lookup"><span data-stu-id="819fe-147">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="819fe-148">Anzeige des gesamten Projekts wie in MSBuild</span><span class="sxs-lookup"><span data-stu-id="819fe-148">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="819fe-149">Obwohl diese csproj-Änderungen für eine erhebliche Vereinfachung der Projektdateien sorgen, möchten Sie vielleicht das vollständig erweiterte Projekt anzeigen, so wie es von MSBuild erkannt wird, nachdem das SDK und die zugehörigen Ziele eingeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="819fe-149">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="819fe-150">Führen Sie eine Vorverarbeitung des Projekts mit der [`/pp`-Option](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](dotnet-msbuild.md) durch. Dieser zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="819fe-150">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="819fe-151">Wenn das Projekt mehrere Zielframeworks umfasst, sollten nur Ergebnisse für ein Framework ausgegeben werden, indem dieses als MSBuild-Eigenschaft angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="819fe-151">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="819fe-152">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="819fe-152">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="819fe-153">SDK-Attribut</span><span class="sxs-lookup"><span data-stu-id="819fe-153">Sdk attribute</span></span> 
<span data-ttu-id="819fe-154">Das `<Project>`-Element der *.csproj*-Datei hat ein neues Attribut namens `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="819fe-154">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="819fe-155">`Sdk` gibt an, welches SDK vom Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-155">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="819fe-156">Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](/visualstudio/msbuild/msbuild-tasks) und -[Zielen](/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können.</span><span class="sxs-lookup"><span data-stu-id="819fe-156">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="819fe-157">Wir liefern zwei Haupt-SDKs mit .NET Core-Tools:</span><span class="sxs-lookup"><span data-stu-id="819fe-157">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="819fe-158">Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID</span><span class="sxs-lookup"><span data-stu-id="819fe-158">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="819fe-159">Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID</span><span class="sxs-lookup"><span data-stu-id="819fe-159">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="819fe-160">Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="819fe-160">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="819fe-161">PackageReference</span><span class="sxs-lookup"><span data-stu-id="819fe-161">PackageReference</span></span>
<span data-ttu-id="819fe-162">Element, das eine NuGet-Abhängigkeit im Projekt angibt.</span><span class="sxs-lookup"><span data-stu-id="819fe-162">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="819fe-163">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="819fe-163">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="819fe-164">Version</span><span class="sxs-lookup"><span data-stu-id="819fe-164">Version</span></span>
<span data-ttu-id="819fe-165">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="819fe-165">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="819fe-166">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="819fe-166">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="819fe-167">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="819fe-167">The default behavior is an exact version match.</span></span> <span data-ttu-id="819fe-168">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="819fe-168">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="819fe-169">IncludeAssets, ExcludeAssets und PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="819fe-169">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="819fe-170">Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="819fe-170">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="819fe-171">Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="819fe-171">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="819fe-172">Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="819fe-172">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="819fe-173">`PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="819fe-173">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="819fe-174">Diese Attribute können eines oder mehrere der folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="819fe-174">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="819fe-175">`Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="819fe-175">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="819fe-176">`Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden</span><span class="sxs-lookup"><span data-stu-id="819fe-176">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="819fe-177">`ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="819fe-177">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="819fe-178">`Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden</span><span class="sxs-lookup"><span data-stu-id="819fe-178">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="819fe-179">`Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden</span><span class="sxs-lookup"><span data-stu-id="819fe-179">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="819fe-180">`Analyzers`: Gibt an, dass Analysen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="819fe-180">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="819fe-181">Alternativ kann das Attribut Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="819fe-181">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="819fe-182">`None`: Keines der Objekte wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="819fe-182">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="819fe-183">`All`: Alle Objekte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="819fe-183">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="819fe-184">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="819fe-184">DotNetCliToolReference</span></span>
<span data-ttu-id="819fe-185">Das `<DotNetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="819fe-185">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="819fe-186">Es ist ein Ersatz für den `tools`-Knoten in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="819fe-186">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="819fe-187">Version</span><span class="sxs-lookup"><span data-stu-id="819fe-187">Version</span></span>
<span data-ttu-id="819fe-188">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="819fe-188">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="819fe-189">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="819fe-189">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="819fe-190">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="819fe-190">The default behavior is an exact version match.</span></span> <span data-ttu-id="819fe-191">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="819fe-191">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="819fe-192">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="819fe-192">RuntimeIdentifiers</span></span>
<span data-ttu-id="819fe-193">Das Element `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="819fe-193">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="819fe-194">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="819fe-194">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="819fe-195">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="819fe-195">RuntimeIdentifier</span></span>
<span data-ttu-id="819fe-196">Das `<RuntimeIdentifier>`-Element ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="819fe-196">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="819fe-197">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="819fe-197">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="819fe-198">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="819fe-198">PackageTargetFallback</span></span> 
<span data-ttu-id="819fe-199">Das `<PackageTargetFallback>`-Element ermöglicht die Angabe eines Satzes von kompatiblen Zielen, die verwendet werden sollen, wenn Pakete wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="819fe-199">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="819fe-200">Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="819fe-200">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="819fe-201">Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="819fe-201">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="819fe-202">Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="819fe-202">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="819fe-203">Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp1.0`-Ziel angegeben:</span><span class="sxs-lookup"><span data-stu-id="819fe-203">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="819fe-204">NuGet-Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="819fe-204">NuGet metadata properties</span></span>
<span data-ttu-id="819fe-205">Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="819fe-205">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="819fe-206">Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen.</span><span class="sxs-lookup"><span data-stu-id="819fe-206">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="819fe-207">In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDKs ist.</span><span class="sxs-lookup"><span data-stu-id="819fe-207">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="819fe-208">IsPackable</span><span class="sxs-lookup"><span data-stu-id="819fe-208">IsPackable</span></span>
<span data-ttu-id="819fe-209">Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann.</span><span class="sxs-lookup"><span data-stu-id="819fe-209">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="819fe-210">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="819fe-210">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="819fe-211">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="819fe-211">PackageVersion</span></span>
<span data-ttu-id="819fe-212">Gibt die Version an, die das resultierende Paket haben wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-212">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="819fe-213">Akzeptiert alle Arten von NuGet-Versionszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="819fe-213">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="819fe-214">Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt.</span><span class="sxs-lookup"><span data-stu-id="819fe-214">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="819fe-215">PackageId</span><span class="sxs-lookup"><span data-stu-id="819fe-215">PackageId</span></span>
<span data-ttu-id="819fe-216">Gibt den Namen für das resultierende Paket an.</span><span class="sxs-lookup"><span data-stu-id="819fe-216">Specifies the name for the resulting package.</span></span> <span data-ttu-id="819fe-217">Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="819fe-217">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="819fe-218">Titel</span><span class="sxs-lookup"><span data-stu-id="819fe-218">Title</span></span>
<span data-ttu-id="819fe-219">Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="819fe-219">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="819fe-220">Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="819fe-220">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="819fe-221">Authors</span><span class="sxs-lookup"><span data-stu-id="819fe-221">Authors</span></span>
<span data-ttu-id="819fe-222">Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="819fe-222">A semicolon-separated list of packages authors, matching the profile names on nuget.org.</span></span> <span data-ttu-id="819fe-223">Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="819fe-223">These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="819fe-224">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="819fe-224">Description</span></span>
<span data-ttu-id="819fe-225">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="819fe-225">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="819fe-226">Copyright</span><span class="sxs-lookup"><span data-stu-id="819fe-226">Copyright</span></span>
<span data-ttu-id="819fe-227">Copyright-Informationen für das Paket.</span><span class="sxs-lookup"><span data-stu-id="819fe-227">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="819fe-228">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="819fe-228">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="819fe-229">Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="819fe-229">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="819fe-230">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="819fe-230">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="819fe-231">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="819fe-231">PackageLicenseUrl</span></span>
<span data-ttu-id="819fe-232">Eine URL für die Lizenz, die auf das Paket angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="819fe-232">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="819fe-233">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="819fe-233">PackageProjectUrl</span></span>
<span data-ttu-id="819fe-234">Eine URL für die Paket-Homepage, häufig auf der Benutzeroberfläche sowie auf nuget.org angezeigt.</span><span class="sxs-lookup"><span data-stu-id="819fe-234">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="819fe-235">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="819fe-235">PackageIconUrl</span></span>
<span data-ttu-id="819fe-236">Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-236">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="819fe-237">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="819fe-237">PackageReleaseNotes</span></span>
<span data-ttu-id="819fe-238">Anmerkungen zu diesem Paket.</span><span class="sxs-lookup"><span data-stu-id="819fe-238">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="819fe-239">PackageTags</span><span class="sxs-lookup"><span data-stu-id="819fe-239">PackageTags</span></span>
<span data-ttu-id="819fe-240">Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.</span><span class="sxs-lookup"><span data-stu-id="819fe-240">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="819fe-241">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="819fe-241">PackageOutputPath</span></span>
<span data-ttu-id="819fe-242">Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-242">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="819fe-243">Der Standardwert ist `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="819fe-243">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="819fe-244">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="819fe-244">IncludeSymbols</span></span>
<span data-ttu-id="819fe-245">Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-245">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="819fe-246">Dieses Paket wird eine *.symbols.nupkg*-Erweiterung haben und die PDB-Dateien zusammen mit der DLL und anderen Ausgabedateien kopieren.</span><span class="sxs-lookup"><span data-stu-id="819fe-246">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="819fe-247">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="819fe-247">IncludeSource</span></span>
<span data-ttu-id="819fe-248">Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte.</span><span class="sxs-lookup"><span data-stu-id="819fe-248">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="819fe-249">Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="819fe-249">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="819fe-250">Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="819fe-250">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="819fe-251">IsTool</span><span class="sxs-lookup"><span data-stu-id="819fe-251">IsTool</span></span>
<span data-ttu-id="819fe-252">Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="819fe-252">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="819fe-253">Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-253">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="819fe-254">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="819fe-254">RepositoryUrl</span></span>
<span data-ttu-id="819fe-255">Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-255">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="819fe-256">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="819fe-256">RepositoryType</span></span>
<span data-ttu-id="819fe-257">Gibt den Verzeichnistyp an.</span><span class="sxs-lookup"><span data-stu-id="819fe-257">Specifies the type of the repository.</span></span> <span data-ttu-id="819fe-258">Der Standardwert ist „Git“.</span><span class="sxs-lookup"><span data-stu-id="819fe-258">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="819fe-259">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="819fe-259">NoPackageAnalysis</span></span>
<span data-ttu-id="819fe-260">Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="819fe-260">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="819fe-261">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="819fe-261">MinClientVersion</span></span>
<span data-ttu-id="819fe-262">Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.</span><span class="sxs-lookup"><span data-stu-id="819fe-262">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="819fe-263">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="819fe-263">IncludeBuildOutput</span></span>
<span data-ttu-id="819fe-264">Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="819fe-264">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="819fe-265">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="819fe-265">IncludeContentInPack</span></span>
<span data-ttu-id="819fe-266">Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="819fe-266">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="819fe-267">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="819fe-267">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="819fe-268">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="819fe-268">BuildOutputTargetFolder</span></span>
<span data-ttu-id="819fe-269">Gibt den Ordner an, in dem die Ausgabeassemblys positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="819fe-269">Specifies the folder where to place the output assemblies..</span></span> <span data-ttu-id="819fe-270">Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="819fe-270">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="819fe-271">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="819fe-271">ContentTargetFolders</span></span>
<span data-ttu-id="819fe-272">Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="819fe-272">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="819fe-273">Der Standardwert ist „content;contentFiles“.</span><span class="sxs-lookup"><span data-stu-id="819fe-273">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="819fe-274">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="819fe-274">NuspecFile</span></span>
<span data-ttu-id="819fe-275">Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="819fe-275">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="819fe-276">Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="819fe-276">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="819fe-277">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="819fe-277">NuspecBasePath</span></span>
<span data-ttu-id="819fe-278">Der Basispfad für die *.nuspec*-Datei.</span><span class="sxs-lookup"><span data-stu-id="819fe-278">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="819fe-279">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="819fe-279">NuspecProperties</span></span>
<span data-ttu-id="819fe-280">Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.</span><span class="sxs-lookup"><span data-stu-id="819fe-280">Semicolon separated list of key=value pairs.</span></span>

