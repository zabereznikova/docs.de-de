---
title: "Erweiterungen des CSPROJ-Formats für .NET Core"
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.workload:
- dotnetcore
ms.openlocfilehash: d2a318f099eaa67912c2cecd1c67ceebaee8629e
ms.sourcegitcommit: dd6ea7f0e581ac84e0a90d9b23c463fcf1ec3ce7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2018
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="d4898-104">Erweiterungen des CSPROJ-Formats für .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4898-104">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="d4898-105">In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4898-105">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="d4898-106">Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="d4898-106">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="d4898-107">Implizite Paketverweise</span><span class="sxs-lookup"><span data-stu-id="d4898-107">Implicit package references</span></span>
<span data-ttu-id="d4898-108">Es wird implizit auf Metapakete verwiesen, basierend auf der Grundlage des/der Zielfameworks, das/die in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde/n.</span><span class="sxs-lookup"><span data-stu-id="d4898-108">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="d4898-109">`<TargetFrameworks>` wird ignoriert, wenn `<TargetFramework>` angegeben wird, egal wie die Reihenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="d4898-109">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="d4898-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="d4898-110">Recommendations</span></span>
<span data-ttu-id="d4898-111">Da implizit auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="d4898-111">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="d4898-112">Wenn .NET Core oder .NET Standard angezielt wird, darf nie ein expliziter Verweis auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete über das `<PackageReference>`-Element in Ihrer Projektdatei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d4898-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="d4898-113">Wenn Sie .NET Core anzielen und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d4898-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="d4898-114">Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="d4898-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="d4898-115">Wenn Sie .NET Standard anzielen und eine bestimmte Version der `NetStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="d4898-115">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="d4898-116">Fügen Sie dem `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapaket in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht.</span><span class="sxs-lookup"><span data-stu-id="d4898-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="d4898-117">Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NetStandard.Library` benötigt wird, installiert NuGet diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="d4898-117">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="d4898-118">Standardkompilierung in .NET Core-Projekten</span><span class="sxs-lookup"><span data-stu-id="d4898-118">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="d4898-119">Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="d4898-119">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="d4898-120">Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="d4898-120">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="d4898-121">Der Hauptgrund dafür ist die Übersichtlichkeit in Ihrer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="d4898-121">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="d4898-122">Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4898-122">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="d4898-123">Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind.</span><span class="sxs-lookup"><span data-stu-id="d4898-123">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="d4898-124">Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im SDK enthalten und ausgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="d4898-124">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="d4898-125">Element</span><span class="sxs-lookup"><span data-stu-id="d4898-125">Element</span></span>           | <span data-ttu-id="d4898-126">Glob einschließen</span><span class="sxs-lookup"><span data-stu-id="d4898-126">Include glob</span></span>                              | <span data-ttu-id="d4898-127">Glob ausschließen</span><span class="sxs-lookup"><span data-stu-id="d4898-127">Exclude glob</span></span>                                                  | <span data-ttu-id="d4898-128">Glob entfernen</span><span class="sxs-lookup"><span data-stu-id="d4898-128">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="d4898-129">Compile</span><span class="sxs-lookup"><span data-stu-id="d4898-129">Compile</span></span>           | <span data-ttu-id="d4898-130">\*\*/\*.cs (oder andere Spracherweiterungen)</span><span class="sxs-lookup"><span data-stu-id="d4898-130">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="d4898-131">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d4898-131">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="d4898-132">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4898-132">N/A</span></span>                        |
| <span data-ttu-id="d4898-133">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="d4898-133">EmbeddedResource</span></span>  | <span data-ttu-id="d4898-134">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="d4898-134">\*\*/\*.resx</span></span>                              | <span data-ttu-id="d4898-135">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d4898-135">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="d4898-136">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="d4898-136">N/A</span></span>                        |
| <span data-ttu-id="d4898-137">Keiner</span><span class="sxs-lookup"><span data-stu-id="d4898-137">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="d4898-138">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="d4898-138">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="d4898-139">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="d4898-139">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="d4898-140">Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="d4898-140">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="d4898-141">Doppelte Compile-Elemente waren enthalten.</span><span class="sxs-lookup"><span data-stu-id="d4898-141">Duplicate Compile items were included.</span></span> <span data-ttu-id="d4898-142">.NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d4898-142">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="d4898-143">Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4898-143">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="d4898-144">Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="d4898-144">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="d4898-145">Wenn diese Eigenschaft auf `false` festgelegt wird, wird die implizite Aufnahme überschrieben, und das Verhalten wird wieder auf die früheren SDKs gesetzt, als Sie die Standardglobs in Ihrem Projekt angeben mussten.</span><span class="sxs-lookup"><span data-stu-id="d4898-145">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="d4898-146">Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht.</span><span class="sxs-lookup"><span data-stu-id="d4898-146">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="d4898-147">Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).</span><span class="sxs-lookup"><span data-stu-id="d4898-147">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="d4898-148">`<EnableDefaultCompileItems>` deaktiviert nur `Compile`-Globmuster, wirkt sich jedoch nicht auf andere Globmuster wie das implizite `None`-Globmuster aus, das ebenfalls für \*.cs-Elemente gilt.</span><span class="sxs-lookup"><span data-stu-id="d4898-148">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="d4898-149">Deshalb zeigt **Projektmappen-Explorer** die \*.cs-Elemente weiterhin als Teil des Projekts an, die als `None`-Elemente eingebunden wurden.</span><span class="sxs-lookup"><span data-stu-id="d4898-149">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="d4898-150">Sie können `<EnableDefaultNoneItems>` ähnlich verwenden, um das implizite `None`-Globmuster zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d4898-150">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="d4898-151">Sie können die `<EnableDefaultItems>`-Eigenschaft wie im folgenden Beispiel auf `false` festlegen, um **alle impliziten Globmuster** zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="d4898-151">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a><span data-ttu-id="d4898-152">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="d4898-152">Recommendation</span></span>
<span data-ttu-id="d4898-153">Für csproj empfehlen wir, dass Sie die Standardglobs aus Ihrem Projekt entfernen und nur Dateipfade mit Globs für die Artefakte hinzufügen, die Ihre App/Bibliothek für verschiedene Szenarios benötigt (z.B. Runtime und NuGet-Paket).</span><span class="sxs-lookup"><span data-stu-id="d4898-153">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="d4898-154">Anzeige des gesamten Projekts wie in MSBuild</span><span class="sxs-lookup"><span data-stu-id="d4898-154">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="d4898-155">Obwohl diese csproj-Änderungen für eine erhebliche Vereinfachung der Projektdateien sorgen, möchten Sie vielleicht das vollständig erweiterte Projekt anzeigen, so wie es von MSBuild erkannt wird, nachdem das SDK und die zugehörigen Ziele eingeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="d4898-155">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="d4898-156">Führen Sie eine Vorverarbeitung des Projekts mit der [`/pp`-Option](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](dotnet-msbuild.md) durch. Dieser zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d4898-156">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="d4898-157">Wenn das Projekt mehrere Zielframeworks umfasst, sollten nur Ergebnisse für ein Framework ausgegeben werden, indem dieses als MSBuild-Eigenschaft angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="d4898-157">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="d4898-158">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d4898-158">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="d4898-159">SDK-Attribut</span><span class="sxs-lookup"><span data-stu-id="d4898-159">Sdk attribute</span></span> 
<span data-ttu-id="d4898-160">Das `<Project>`-Element der *.csproj*-Datei hat ein neues Attribut namens `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="d4898-160">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="d4898-161">`Sdk` gibt an, welches SDK vom Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-161">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="d4898-162">Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](/visualstudio/msbuild/msbuild-tasks) und -[Zielen](/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d4898-162">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="d4898-163">Wir liefern zwei Haupt-SDKs mit .NET Core-Tools:</span><span class="sxs-lookup"><span data-stu-id="d4898-163">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="d4898-164">Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID</span><span class="sxs-lookup"><span data-stu-id="d4898-164">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="d4898-165">Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID</span><span class="sxs-lookup"><span data-stu-id="d4898-165">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="d4898-166">Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="d4898-166">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="d4898-167">PackageReference</span><span class="sxs-lookup"><span data-stu-id="d4898-167">PackageReference</span></span>
<span data-ttu-id="d4898-168">Element, das eine NuGet-Abhängigkeit im Projekt angibt.</span><span class="sxs-lookup"><span data-stu-id="d4898-168">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="d4898-169">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="d4898-169">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="d4898-170">Version</span><span class="sxs-lookup"><span data-stu-id="d4898-170">Version</span></span>
<span data-ttu-id="d4898-171">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="d4898-171">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="d4898-172">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="d4898-172">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="d4898-173">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="d4898-173">The default behavior is an exact version match.</span></span> <span data-ttu-id="d4898-174">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="d4898-174">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="d4898-175">IncludeAssets, ExcludeAssets und PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="d4898-175">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="d4898-176">Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4898-176">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="d4898-177">Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4898-177">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="d4898-178">Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4898-178">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="d4898-179">`PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="d4898-179">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="d4898-180">Diese Attribute können eines oder mehrere der folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="d4898-180">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="d4898-181">`Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="d4898-181">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="d4898-182">`Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden</span><span class="sxs-lookup"><span data-stu-id="d4898-182">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="d4898-183">`ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4898-183">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="d4898-184">`Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden</span><span class="sxs-lookup"><span data-stu-id="d4898-184">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="d4898-185">`Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden</span><span class="sxs-lookup"><span data-stu-id="d4898-185">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="d4898-186">`Analyzers`: Gibt an, dass Analysen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="d4898-186">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="d4898-187">Alternativ kann das Attribut Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="d4898-187">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="d4898-188">`None`: Keines der Objekte wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4898-188">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="d4898-189">`All`: Alle Objekte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4898-189">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="d4898-190">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="d4898-190">DotNetCliToolReference</span></span>
<span data-ttu-id="d4898-191">Das `<DotNetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="d4898-191">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="d4898-192">Es ist ein Ersatz für den `tools`-Knoten in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="d4898-192">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="d4898-193">Version</span><span class="sxs-lookup"><span data-stu-id="d4898-193">Version</span></span>
<span data-ttu-id="d4898-194">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="d4898-194">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="d4898-195">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="d4898-195">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="d4898-196">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="d4898-196">The default behavior is an exact version match.</span></span> <span data-ttu-id="d4898-197">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="d4898-197">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="d4898-198">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="d4898-198">RuntimeIdentifiers</span></span>
<span data-ttu-id="d4898-199">Das Element `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d4898-199">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="d4898-200">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d4898-200">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="d4898-201">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="d4898-201">RuntimeIdentifier</span></span>
<span data-ttu-id="d4898-202">Das `<RuntimeIdentifier>`-Element ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="d4898-202">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="d4898-203">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d4898-203">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="d4898-204">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="d4898-204">PackageTargetFallback</span></span> 
<span data-ttu-id="d4898-205">Das `<PackageTargetFallback>`-Element ermöglicht die Angabe eines Satzes von kompatiblen Zielen, die verwendet werden sollen, wenn Pakete wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4898-205">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="d4898-206">Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="d4898-206">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="d4898-207">Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="d4898-207">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="d4898-208">Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="d4898-208">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="d4898-209">Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp1.0`-Ziel angegeben:</span><span class="sxs-lookup"><span data-stu-id="d4898-209">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="d4898-210">NuGet-Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4898-210">NuGet metadata properties</span></span>
<span data-ttu-id="d4898-211">Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="d4898-211">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="d4898-212">Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen.</span><span class="sxs-lookup"><span data-stu-id="d4898-212">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="d4898-213">In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDKs ist.</span><span class="sxs-lookup"><span data-stu-id="d4898-213">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="d4898-214">IsPackable</span><span class="sxs-lookup"><span data-stu-id="d4898-214">IsPackable</span></span>
<span data-ttu-id="d4898-215">Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4898-215">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="d4898-216">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="d4898-216">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="d4898-217">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="d4898-217">PackageVersion</span></span>
<span data-ttu-id="d4898-218">Gibt die Version an, die das resultierende Paket haben wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-218">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="d4898-219">Akzeptiert alle Arten von NuGet-Versionszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="d4898-219">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="d4898-220">Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt.</span><span class="sxs-lookup"><span data-stu-id="d4898-220">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="d4898-221">PackageId</span><span class="sxs-lookup"><span data-stu-id="d4898-221">PackageId</span></span>
<span data-ttu-id="d4898-222">Gibt den Namen für das resultierende Paket an.</span><span class="sxs-lookup"><span data-stu-id="d4898-222">Specifies the name for the resulting package.</span></span> <span data-ttu-id="d4898-223">Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="d4898-223">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="d4898-224">Titel</span><span class="sxs-lookup"><span data-stu-id="d4898-224">Title</span></span>
<span data-ttu-id="d4898-225">Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4898-225">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="d4898-226">Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4898-226">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="d4898-227">Authors</span><span class="sxs-lookup"><span data-stu-id="d4898-227">Authors</span></span>
<span data-ttu-id="d4898-228">Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="d4898-228">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="d4898-229">description</span><span class="sxs-lookup"><span data-stu-id="d4898-229">Description</span></span>
<span data-ttu-id="d4898-230">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="d4898-230">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="d4898-231">Copyright</span><span class="sxs-lookup"><span data-stu-id="d4898-231">Copyright</span></span>
<span data-ttu-id="d4898-232">Copyright-Informationen für das Paket.</span><span class="sxs-lookup"><span data-stu-id="d4898-232">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="d4898-233">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="d4898-233">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="d4898-234">Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="d4898-234">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="d4898-235">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d4898-235">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="d4898-236">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="d4898-236">PackageLicenseUrl</span></span>
<span data-ttu-id="d4898-237">Eine URL für die Lizenz, die auf das Paket angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d4898-237">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="d4898-238">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="d4898-238">PackageProjectUrl</span></span>
<span data-ttu-id="d4898-239">Eine URL für die Paket-Homepage, häufig auf der Benutzeroberfläche sowie auf nuget.org angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4898-239">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="d4898-240">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="d4898-240">PackageIconUrl</span></span>
<span data-ttu-id="d4898-241">Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-241">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="d4898-242">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="d4898-242">PackageReleaseNotes</span></span>
<span data-ttu-id="d4898-243">Anmerkungen zu diesem Paket.</span><span class="sxs-lookup"><span data-stu-id="d4898-243">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="d4898-244">PackageTags</span><span class="sxs-lookup"><span data-stu-id="d4898-244">PackageTags</span></span>
<span data-ttu-id="d4898-245">Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.</span><span class="sxs-lookup"><span data-stu-id="d4898-245">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="d4898-246">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="d4898-246">PackageOutputPath</span></span>
<span data-ttu-id="d4898-247">Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-247">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="d4898-248">Der Standardwert ist `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="d4898-248">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="d4898-249">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="d4898-249">IncludeSymbols</span></span>
<span data-ttu-id="d4898-250">Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-250">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="d4898-251">Dieses Paket wird eine *.symbols.nupkg*-Erweiterung haben und die PDB-Dateien zusammen mit der DLL und anderen Ausgabedateien kopieren.</span><span class="sxs-lookup"><span data-stu-id="d4898-251">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="d4898-252">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="d4898-252">IncludeSource</span></span>
<span data-ttu-id="d4898-253">Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte.</span><span class="sxs-lookup"><span data-stu-id="d4898-253">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="d4898-254">Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d4898-254">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="d4898-255">Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d4898-255">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="d4898-256">IsTool</span><span class="sxs-lookup"><span data-stu-id="d4898-256">IsTool</span></span>
<span data-ttu-id="d4898-257">Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4898-257">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="d4898-258">Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-258">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="d4898-259">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="d4898-259">RepositoryUrl</span></span>
<span data-ttu-id="d4898-260">Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-260">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="d4898-261">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="d4898-261">RepositoryType</span></span>
<span data-ttu-id="d4898-262">Gibt den Verzeichnistyp an.</span><span class="sxs-lookup"><span data-stu-id="d4898-262">Specifies the type of the repository.</span></span> <span data-ttu-id="d4898-263">Der Standardwert ist „Git“.</span><span class="sxs-lookup"><span data-stu-id="d4898-263">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="d4898-264">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="d4898-264">NoPackageAnalysis</span></span>
<span data-ttu-id="d4898-265">Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="d4898-265">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="d4898-266">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="d4898-266">MinClientVersion</span></span>
<span data-ttu-id="d4898-267">Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.</span><span class="sxs-lookup"><span data-stu-id="d4898-267">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="d4898-268">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="d4898-268">IncludeBuildOutput</span></span>
<span data-ttu-id="d4898-269">Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d4898-269">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="d4898-270">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="d4898-270">IncludeContentInPack</span></span>
<span data-ttu-id="d4898-271">Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d4898-271">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="d4898-272">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="d4898-272">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="d4898-273">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="d4898-273">BuildOutputTargetFolder</span></span>
<span data-ttu-id="d4898-274">Gibt den Ordner an, in dem die Ausgabeassemblys positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="d4898-274">Specifies the folder where to place the output assemblies..</span></span> <span data-ttu-id="d4898-275">Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="d4898-275">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="d4898-276">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="d4898-276">ContentTargetFolders</span></span>
<span data-ttu-id="d4898-277">Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d4898-277">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="d4898-278">Der Standardwert ist „content;contentFiles“.</span><span class="sxs-lookup"><span data-stu-id="d4898-278">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="d4898-279">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="d4898-279">NuspecFile</span></span>
<span data-ttu-id="d4898-280">Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4898-280">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="d4898-281">Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4898-281">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="d4898-282">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="d4898-282">NuspecBasePath</span></span>
<span data-ttu-id="d4898-283">Der Basispfad für die *.nuspec*-Datei.</span><span class="sxs-lookup"><span data-stu-id="d4898-283">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="d4898-284">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="d4898-284">NuspecProperties</span></span>
<span data-ttu-id="d4898-285">Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.</span><span class="sxs-lookup"><span data-stu-id="d4898-285">Semicolon separated list of key=value pairs.</span></span>
