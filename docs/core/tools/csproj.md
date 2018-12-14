---
title: Erweiterungen des CSPROJ-Formats für .NET Core
description: Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.openlocfilehash: f2ab476ee20ae90a84de7a6ccc76ce72738c1343
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143700"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="a8593-103">Erweiterungen des CSPROJ-Formats für .NET Core</span><span class="sxs-lookup"><span data-stu-id="a8593-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="a8593-104">In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a8593-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="a8593-105">Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="a8593-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="a8593-106">Implizite Paketverweise</span><span class="sxs-lookup"><span data-stu-id="a8593-106">Implicit package references</span></span>
<span data-ttu-id="a8593-107">Es wird implizit auf Metapakete verwiesen, basierend auf der Grundlage des/der Zielfameworks, das/die in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde/n.</span><span class="sxs-lookup"><span data-stu-id="a8593-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="a8593-108">`<TargetFrameworks>` wird ignoriert, wenn `<TargetFramework>` angegeben wird, egal wie die Reihenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="a8593-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="a8593-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="a8593-109">Recommendations</span></span>
<span data-ttu-id="a8593-110">Da implizit auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="a8593-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="a8593-111">Wenn .NET Core oder .NET Standard angezielt wird, darf nie ein expliziter Verweis auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete über das `<PackageReference>`-Element in Ihrer Projektdatei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a8593-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="a8593-112">Wenn Sie .NET Core anzielen und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="a8593-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="a8593-113">Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="a8593-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="a8593-114">Wenn Sie .NET Standard anzielen und eine bestimmte Version der `NetStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="a8593-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="a8593-115">Fügen Sie dem `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapaket in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht.</span><span class="sxs-lookup"><span data-stu-id="a8593-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="a8593-116">Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NetStandard.Library` benötigt wird, installiert NuGet diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="a8593-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="a8593-117">Standardkompilierung in .NET Core-Projekten</span><span class="sxs-lookup"><span data-stu-id="a8593-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="a8593-118">Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="a8593-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="a8593-119">Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="a8593-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="a8593-120">Der Hauptgrund dafür ist die Übersichtlichkeit in Ihrer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="a8593-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="a8593-121">Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8593-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="a8593-122">Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind.</span><span class="sxs-lookup"><span data-stu-id="a8593-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="a8593-123">Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im SDK enthalten und ausgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="a8593-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="a8593-124">Element</span><span class="sxs-lookup"><span data-stu-id="a8593-124">Element</span></span>           | <span data-ttu-id="a8593-125">Glob einschließen</span><span class="sxs-lookup"><span data-stu-id="a8593-125">Include glob</span></span>                              | <span data-ttu-id="a8593-126">Glob ausschließen</span><span class="sxs-lookup"><span data-stu-id="a8593-126">Exclude glob</span></span>                                                  | <span data-ttu-id="a8593-127">Glob entfernen</span><span class="sxs-lookup"><span data-stu-id="a8593-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="a8593-128">Compile</span><span class="sxs-lookup"><span data-stu-id="a8593-128">Compile</span></span>           | <span data-ttu-id="a8593-129">\*\*/\*.cs (oder andere Spracherweiterungen)</span><span class="sxs-lookup"><span data-stu-id="a8593-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="a8593-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a8593-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="a8593-131">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a8593-131">N/A</span></span>                        |
| <span data-ttu-id="a8593-132">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="a8593-132">EmbeddedResource</span></span>  | <span data-ttu-id="a8593-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a8593-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="a8593-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a8593-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a8593-135">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a8593-135">N/A</span></span>                        |
| <span data-ttu-id="a8593-136">Keiner</span><span class="sxs-lookup"><span data-stu-id="a8593-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="a8593-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a8593-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a8593-138">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a8593-138">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="a8593-139">Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="a8593-139">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="a8593-140">Doppelte Compile-Elemente waren enthalten.</span><span class="sxs-lookup"><span data-stu-id="a8593-140">Duplicate Compile items were included.</span></span> <span data-ttu-id="a8593-141">.NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="a8593-141">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="a8593-142">Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a8593-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="a8593-143">Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="a8593-143">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="a8593-144">Wenn diese Eigenschaft auf `false` festgelegt wird, wird die implizite Aufnahme überschrieben, und das Verhalten wird wieder auf die früheren SDKs gesetzt, als Sie die Standardglobs in Ihrem Projekt angeben mussten.</span><span class="sxs-lookup"><span data-stu-id="a8593-144">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="a8593-145">Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht.</span><span class="sxs-lookup"><span data-stu-id="a8593-145">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="a8593-146">Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).</span><span class="sxs-lookup"><span data-stu-id="a8593-146">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="a8593-147">`<EnableDefaultCompileItems>` deaktiviert nur `Compile`-Globmuster, wirkt sich jedoch nicht auf andere Globmuster wie das implizite `None`-Globmuster aus, das ebenfalls für \*.cs-Elemente gilt.</span><span class="sxs-lookup"><span data-stu-id="a8593-147">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="a8593-148">Deshalb zeigt **Projektmappen-Explorer** die \*.cs-Elemente weiterhin als Teil des Projekts an, die als `None`-Elemente eingebunden wurden.</span><span class="sxs-lookup"><span data-stu-id="a8593-148">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="a8593-149">Sie können `<EnableDefaultNoneItems>` ähnlich verwenden, um das implizite `None`-Globmuster zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8593-149">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="a8593-150">Sie können die `<EnableDefaultItems>`-Eigenschaft wie im folgenden Beispiel auf `false` festlegen, um **alle impliziten Globmuster** zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="a8593-150">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="a8593-151">Anzeige des gesamten Projekts wie in MSBuild</span><span class="sxs-lookup"><span data-stu-id="a8593-151">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="a8593-152">Obwohl diese csproj-Änderungen für eine erhebliche Vereinfachung der Projektdateien sorgen, möchten Sie vielleicht das vollständig erweiterte Projekt anzeigen, so wie es von MSBuild erkannt wird, nachdem das SDK und die zugehörigen Ziele eingeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="a8593-152">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="a8593-153">Führen Sie eine Vorverarbeitung des Projekts mit der [`/pp`-Option](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](dotnet-msbuild.md) durch. Dieser zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a8593-153">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="a8593-154">Wenn das Projekt mehrere Zielframeworks umfasst, sollten nur Ergebnisse für ein Framework ausgegeben werden, indem dieses als MSBuild-Eigenschaft angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="a8593-154">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="a8593-155">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="a8593-155">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="a8593-156">SDK-Attribut</span><span class="sxs-lookup"><span data-stu-id="a8593-156">Sdk attribute</span></span> 
<span data-ttu-id="a8593-157">Das `<Project>`-Element der *.csproj*-Datei hat ein neues Attribut namens `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="a8593-157">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="a8593-158">`Sdk` gibt an, welches SDK vom Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-158">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="a8593-159">Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](/visualstudio/msbuild/msbuild-tasks) und -[Zielen](/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a8593-159">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="a8593-160">Wir liefern drei Haupt-SDKs mit .NET Core-Tools:</span><span class="sxs-lookup"><span data-stu-id="a8593-160">We ship three main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="a8593-161">Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID</span><span class="sxs-lookup"><span data-stu-id="a8593-161">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="a8593-162">Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID</span><span class="sxs-lookup"><span data-stu-id="a8593-162">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="a8593-163">Das .NET Core Razor-Klassenbibliothek SDK mit der ID von `Microsoft.NET.Sdk.Razor`</span><span class="sxs-lookup"><span data-stu-id="a8593-163">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>

<span data-ttu-id="a8593-164">Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="a8593-164">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="a8593-165">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a8593-165">PackageReference</span></span>
<span data-ttu-id="a8593-166">Element, das eine NuGet-Abhängigkeit im Projekt angibt.</span><span class="sxs-lookup"><span data-stu-id="a8593-166">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="a8593-167">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="a8593-167">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="a8593-168">Version</span><span class="sxs-lookup"><span data-stu-id="a8593-168">Version</span></span>
<span data-ttu-id="a8593-169">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="a8593-169">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="a8593-170">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="a8593-170">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="a8593-171">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="a8593-171">The default behavior is an exact version match.</span></span> <span data-ttu-id="a8593-172">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="a8593-172">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="a8593-173">IncludeAssets, ExcludeAssets und PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="a8593-173">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="a8593-174">Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a8593-174">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="a8593-175">Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a8593-175">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="a8593-176">Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a8593-176">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8593-177">`PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="a8593-177">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="a8593-178">Diese Attribute können eines oder mehrere der folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="a8593-178">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="a8593-179">`Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="a8593-179">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="a8593-180">`Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden</span><span class="sxs-lookup"><span data-stu-id="a8593-180">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="a8593-181">`ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8593-181">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="a8593-182">`Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden</span><span class="sxs-lookup"><span data-stu-id="a8593-182">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="a8593-183">`Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden</span><span class="sxs-lookup"><span data-stu-id="a8593-183">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="a8593-184">`Analyzers`: Gibt an, dass Analysen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="a8593-184">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="a8593-185">Alternativ kann das Attribut Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="a8593-185">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="a8593-186">`None`: Keines der Objekte wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-186">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="a8593-187">`All`: Alle Objekte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-187">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="a8593-188">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="a8593-188">DotNetCliToolReference</span></span>
<span data-ttu-id="a8593-189">Das `<DotNetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="a8593-189">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="a8593-190">Es ist ein Ersatz für den `tools`-Knoten in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="a8593-190">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="a8593-191">Version</span><span class="sxs-lookup"><span data-stu-id="a8593-191">Version</span></span>
<span data-ttu-id="a8593-192">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="a8593-192">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="a8593-193">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="a8593-193">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="a8593-194">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="a8593-194">The default behavior is an exact version match.</span></span> <span data-ttu-id="a8593-195">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="a8593-195">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="a8593-196">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a8593-196">RuntimeIdentifiers</span></span>
<span data-ttu-id="a8593-197">Das Element `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a8593-197">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a8593-198">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a8593-198">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="a8593-199">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a8593-199">RuntimeIdentifier</span></span>
<span data-ttu-id="a8593-200">Das `<RuntimeIdentifier>`-Element ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a8593-200">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a8593-201">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a8593-201">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="a8593-202">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a8593-202">PackageTargetFallback</span></span> 
<span data-ttu-id="a8593-203">Das `<PackageTargetFallback>`-Element ermöglicht die Angabe eines Satzes von kompatiblen Zielen, die verwendet werden sollen, wenn Pakete wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a8593-203">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="a8593-204">Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="a8593-204">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="a8593-205">Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="a8593-205">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="a8593-206">Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="a8593-206">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="a8593-207">Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp2.1`-Ziel angegeben:</span><span class="sxs-lookup"><span data-stu-id="a8593-207">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="a8593-208">NuGet-Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a8593-208">NuGet metadata properties</span></span>
<span data-ttu-id="a8593-209">Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="a8593-209">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="a8593-210">Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen.</span><span class="sxs-lookup"><span data-stu-id="a8593-210">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="a8593-211">In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDKs ist.</span><span class="sxs-lookup"><span data-stu-id="a8593-211">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="a8593-212">IsPackable</span><span class="sxs-lookup"><span data-stu-id="a8593-212">IsPackable</span></span>
<span data-ttu-id="a8593-213">Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8593-213">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="a8593-214">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="a8593-214">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="a8593-215">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="a8593-215">PackageVersion</span></span>
<span data-ttu-id="a8593-216">Gibt die Version an, die das resultierende Paket haben wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-216">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="a8593-217">Akzeptiert alle Arten von NuGet-Versionszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a8593-217">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="a8593-218">Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt.</span><span class="sxs-lookup"><span data-stu-id="a8593-218">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="a8593-219">PackageId</span><span class="sxs-lookup"><span data-stu-id="a8593-219">PackageId</span></span>
<span data-ttu-id="a8593-220">Gibt den Namen für das resultierende Paket an.</span><span class="sxs-lookup"><span data-stu-id="a8593-220">Specifies the name for the resulting package.</span></span> <span data-ttu-id="a8593-221">Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="a8593-221">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="a8593-222">Titel</span><span class="sxs-lookup"><span data-stu-id="a8593-222">Title</span></span>
<span data-ttu-id="a8593-223">Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a8593-223">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="a8593-224">Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-224">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="a8593-225">Authors</span><span class="sxs-lookup"><span data-stu-id="a8593-225">Authors</span></span>
<span data-ttu-id="a8593-226">Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="a8593-226">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="a8593-227">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="a8593-227">PackageDescription</span></span>

<span data-ttu-id="a8593-228">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="a8593-228">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="a8593-229">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8593-229">Description</span></span>
<span data-ttu-id="a8593-230">Eine lange Beschreibung für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="a8593-230">A long description for the assembly.</span></span> <span data-ttu-id="a8593-231">Wenn `PackageDescription` nicht angegeben ist, wird diese Eigenschaft auch als Beschreibung des Pakets verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-231">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="a8593-232">Copyright</span><span class="sxs-lookup"><span data-stu-id="a8593-232">Copyright</span></span>
<span data-ttu-id="a8593-233">Copyright-Informationen für das Paket.</span><span class="sxs-lookup"><span data-stu-id="a8593-233">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="a8593-234">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="a8593-234">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="a8593-235">Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="a8593-235">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="a8593-236">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a8593-236">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="a8593-237">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="a8593-237">PackageLicenseUrl</span></span>
<span data-ttu-id="a8593-238">Eine URL für die Lizenz, die auf das Paket angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8593-238">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="a8593-239">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="a8593-239">PackageProjectUrl</span></span>
<span data-ttu-id="a8593-240">Eine URL für die Paket-Homepage, häufig auf der Benutzeroberfläche sowie auf nuget.org angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8593-240">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="a8593-241">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="a8593-241">PackageIconUrl</span></span>
<span data-ttu-id="a8593-242">Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-242">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="a8593-243">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="a8593-243">PackageReleaseNotes</span></span>
<span data-ttu-id="a8593-244">Anmerkungen zu diesem Paket.</span><span class="sxs-lookup"><span data-stu-id="a8593-244">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="a8593-245">PackageTags</span><span class="sxs-lookup"><span data-stu-id="a8593-245">PackageTags</span></span>
<span data-ttu-id="a8593-246">Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.</span><span class="sxs-lookup"><span data-stu-id="a8593-246">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="a8593-247">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="a8593-247">PackageOutputPath</span></span>
<span data-ttu-id="a8593-248">Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-248">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="a8593-249">Der Standardwert ist `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="a8593-249">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="a8593-250">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="a8593-250">IncludeSymbols</span></span>
<span data-ttu-id="a8593-251">Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-251">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="a8593-252">Dieses Paket wird eine *.symbols.nupkg*-Erweiterung haben und die PDB-Dateien zusammen mit der DLL und anderen Ausgabedateien kopieren.</span><span class="sxs-lookup"><span data-stu-id="a8593-252">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="a8593-253">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="a8593-253">IncludeSource</span></span>
<span data-ttu-id="a8593-254">Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte.</span><span class="sxs-lookup"><span data-stu-id="a8593-254">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="a8593-255">Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="a8593-255">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="a8593-256">Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8593-256">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="a8593-257">IsTool</span><span class="sxs-lookup"><span data-stu-id="a8593-257">IsTool</span></span>
<span data-ttu-id="a8593-258">Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a8593-258">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="a8593-259">Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-259">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="a8593-260">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="a8593-260">RepositoryUrl</span></span>
<span data-ttu-id="a8593-261">Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-261">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="a8593-262">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="a8593-262">RepositoryType</span></span>
<span data-ttu-id="a8593-263">Gibt den Verzeichnistyp an.</span><span class="sxs-lookup"><span data-stu-id="a8593-263">Specifies the type of the repository.</span></span> <span data-ttu-id="a8593-264">Der Standardwert ist „Git“.</span><span class="sxs-lookup"><span data-stu-id="a8593-264">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="a8593-265">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="a8593-265">NoPackageAnalysis</span></span>
<span data-ttu-id="a8593-266">Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="a8593-266">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="a8593-267">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="a8593-267">MinClientVersion</span></span>
<span data-ttu-id="a8593-268">Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a8593-268">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="a8593-269">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="a8593-269">IncludeBuildOutput</span></span>
<span data-ttu-id="a8593-270">Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a8593-270">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="a8593-271">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="a8593-271">IncludeContentInPack</span></span>
<span data-ttu-id="a8593-272">Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a8593-272">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="a8593-273">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="a8593-273">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="a8593-274">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="a8593-274">BuildOutputTargetFolder</span></span>
<span data-ttu-id="a8593-275">Gibt den Ordner an, in dem die Ausgabeassemblys abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a8593-275">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="a8593-276">Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="a8593-276">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="a8593-277">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="a8593-277">ContentTargetFolders</span></span>
<span data-ttu-id="a8593-278">Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a8593-278">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="a8593-279">Der Standardwert ist „content;contentFiles“.</span><span class="sxs-lookup"><span data-stu-id="a8593-279">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="a8593-280">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="a8593-280">NuspecFile</span></span>
<span data-ttu-id="a8593-281">Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a8593-281">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8593-282">Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-282">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="a8593-283">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="a8593-283">NuspecBasePath</span></span>
<span data-ttu-id="a8593-284">Der Basispfad für die *.nuspec*-Datei.</span><span class="sxs-lookup"><span data-stu-id="a8593-284">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="a8593-285">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="a8593-285">NuspecProperties</span></span>
<span data-ttu-id="a8593-286">Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.</span><span class="sxs-lookup"><span data-stu-id="a8593-286">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="a8593-287">AssemblyInfo-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a8593-287">AssemblyInfo properties</span></span>
<span data-ttu-id="a8593-288">[Assembly-Attribute](../../framework/app-domains/set-assembly-attributes.md), die normalerweise in einer *AssemblyInfo*-Datei vorlagen, werden jetzt automatisch aus Eigenschaften generiert.</span><span class="sxs-lookup"><span data-stu-id="a8593-288">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="a8593-289">Eigenschaften pro Attribut</span><span class="sxs-lookup"><span data-stu-id="a8593-289">Properties per attribute</span></span>

<span data-ttu-id="a8593-290">Jedes Attribut weist eine Eigenschaft auf, die seinen Inhalt steuert, und eine weitere zum Deaktivieren seiner Erstellung, wie in der folgenden Tabelle ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="a8593-290">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="a8593-291">Attribut</span><span class="sxs-lookup"><span data-stu-id="a8593-291">Attribute</span></span>                                                      | <span data-ttu-id="a8593-292">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a8593-292">Property</span></span>               | <span data-ttu-id="a8593-293">Eigenschaft zum Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="a8593-293">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="a8593-294">Notizen:</span><span class="sxs-lookup"><span data-stu-id="a8593-294">Notes:</span></span>

* <span data-ttu-id="a8593-295">Das Standardverhalten von `AssemblyVersion` und `FileVersion` besteht in der Übernahme des Werts von `$(Version)` ohne Suffix.</span><span class="sxs-lookup"><span data-stu-id="a8593-295">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="a8593-296">Wenn `$(Version)` beispielsweise `1.2.3-beta.4` ist, wäre der Wert `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="a8593-296">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="a8593-297">`InformationalVersion` hat standardmäßig den Wert von `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="a8593-297">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="a8593-298">An `InformationalVersion` ist `$(SourceRevisionId)` angefügt, wenn die Eigenschaft vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a8593-298">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="a8593-299">Sie kann mithilfe von `IncludeSourceRevisionInInformationalVersion` deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a8593-299">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="a8593-300">Die Eigenschaften `Copyright` und `Description` werden auch für NuGet-Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="a8593-300">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="a8593-301">`Configuration` wird vom gesamten Buildprozess gemeinsam verwendet und über den `--configuration`-Parameter von `dotnet`-Befehlen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a8593-301">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="a8593-302">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="a8593-302">GenerateAssemblyInfo</span></span> 
<span data-ttu-id="a8593-303">Ein boolescher Wert zum Aktivieren oder Deaktivieren der AssemblyInfo-Erstellung insgesamt.</span><span class="sxs-lookup"><span data-stu-id="a8593-303">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="a8593-304">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="a8593-304">The default value is `true`.</span></span> 

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="a8593-305">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="a8593-305">GeneratedAssemblyInfoFile</span></span> 
<span data-ttu-id="a8593-306">Der Pfad der generierten Assembly-Infodatei.</span><span class="sxs-lookup"><span data-stu-id="a8593-306">The path of the generated assembly info file.</span></span> <span data-ttu-id="a8593-307">Standardmäßig eine Datei im `$(IntermediateOutputPath)` (obj)-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a8593-307">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
