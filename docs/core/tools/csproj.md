---
title: Erweiterungen des CSPROJ-Formats für .NET Core
description: Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: 4ce9227839a610308071c36185b63db8b1ee86ed
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739296"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="5842c-103">Erweiterungen des CSPROJ-Formats für .NET Core</span><span class="sxs-lookup"><span data-stu-id="5842c-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="5842c-104">In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="5842c-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="5842c-105">Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="5842c-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="5842c-106">Implizite Paketverweise</span><span class="sxs-lookup"><span data-stu-id="5842c-106">Implicit package references</span></span>

<span data-ttu-id="5842c-107">Es wird implizit auf Metapakete verwiesen, basierend auf der Grundlage des/der Zielfameworks, das/die in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde/n.</span><span class="sxs-lookup"><span data-stu-id="5842c-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="5842c-108">`<TargetFrameworks>` wird ignoriert, wenn `<TargetFramework>` angegeben wird, egal wie die Reihenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="5842c-109">Weitere Informationen finden Sie unter [Pakete, Metapakete und Frameworks](../packages.md).</span><span class="sxs-lookup"><span data-stu-id="5842c-109">For more information, see [Packages, metapackages and frameworks](../packages.md).</span></span> 

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

### <a name="recommendations"></a><span data-ttu-id="5842c-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="5842c-110">Recommendations</span></span>

<span data-ttu-id="5842c-111">Da implizit auf die `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:</span><span class="sxs-lookup"><span data-stu-id="5842c-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="5842c-112">Wenn .NET Core oder .NET Standard angezielt wird, darf nie ein expliziter Verweis auf die `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapakete über das `<PackageReference>`-Element in Ihrer Projektdatei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="5842c-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="5842c-113">Wenn Sie .NET Core anzielen und eine bestimmte Version der Runtime benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="5842c-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="5842c-114">Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="5842c-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="5842c-115">Wenn Sie .NET Standard anzielen und eine bestimmte Version der `NETStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="5842c-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="5842c-116">Fügen Sie dem `Microsoft.NETCore.App`- oder `NETStandard.Library`-Metapaket in .NET Framework-Projekten nicht explizit Verweise hinzu, und aktualisieren Sie diese auch nicht.</span><span class="sxs-lookup"><span data-stu-id="5842c-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="5842c-117">Wenn bei der Verwendung eines auf .NET Standard basierenden NuGet-Pakets eine bestimmte Version von `NETStandard.Library` benötigt wird, installiert NuGet diese automatisch.</span><span class="sxs-lookup"><span data-stu-id="5842c-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="5842c-118">Implizite Version für einige Paketverweise</span><span class="sxs-lookup"><span data-stu-id="5842c-118">Implicit version for some package references</span></span>

<span data-ttu-id="5842c-119">Die meisten Anwendungen von [`<PackageReference>`](#packagereference) erfordern das Festlegen des Attributs `Version`, um die zu verwendende NuGet-Paketversion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5842c-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="5842c-120">Bei Verwendung von .NET Core 2.1 oder 2.2 und Verweis auf [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) oder [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage) ist das Attribut jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5842c-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="5842c-121">Das .NET Core SDK kann automatisch die Version dieser Pakete auswählen, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5842c-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="5842c-122">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="5842c-122">Recommendation</span></span>

<span data-ttu-id="5842c-123">Wenn Sie auf die Pakete `Microsoft.AspNetCore.App` oder `Microsoft.AspNetCore.All` verweisen, geben Sie deren Version nicht an.</span><span class="sxs-lookup"><span data-stu-id="5842c-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="5842c-124">Wenn eine Version angegeben wird, kann das SDK eine Warnung NETSDK1071 ausgeben.</span><span class="sxs-lookup"><span data-stu-id="5842c-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="5842c-125">Um diese Warnung zu beheben, entfernen Sie die Paketversion wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5842c-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="5842c-126">Bekanntes Problem: Das.NET Core 2.1 SDK unterstützte diese Syntax nur, wenn das Projekt auch „Microsoft.NET.Sdk.Web“ verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="5842c-127">Dies wird im .NET Core SDK 2.2 gelöst.</span><span class="sxs-lookup"><span data-stu-id="5842c-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="5842c-128">Diese Verweise auf ASP.NET Core-Metapakete haben ein etwas anderes Verhalten als die meisten normalen NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="5842c-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="5842c-129">[Frameworkabhängige Bereitstellungen](../deploying/index.md#framework-dependent-deployments-fdd) von Anwendungen, die das Metapaket verwenden, profitieren automatisch vom freigegebenen ASP.NET Core-Framework.</span><span class="sxs-lookup"><span data-stu-id="5842c-129">[Framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="5842c-130">Bei Verwendung des Metapakets werden **keine** Objekte aus den referenzierten NuGet-Paketen für ASP.NET Core mit der Anwendung bereitgestellt. Das freigegebene ASP.NET Core-Framework enthält diese Objekte.</span><span class="sxs-lookup"><span data-stu-id="5842c-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="5842c-131">Die Objekte im freigegebenen Framework sind zur Verbesserung der Startzeit für die Zielplattform optimiert.</span><span class="sxs-lookup"><span data-stu-id="5842c-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="5842c-132">Weitere Informationen zu freigegebenen Frameworks finden Sie unter [Packen von .NET Core-Verteilungen](../build/distribution-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="5842c-132">For more information about shared framework, see [.NET Core distribution packaging](../build/distribution-packaging.md).</span></span>

<span data-ttu-id="5842c-133">Wenn eine Version angegeben *ist*, wird sie als *Mindestversion* des ASP.NET Core Shared Framework-abhängigen Frameworks und als *exakte* Version für eigenständige Bereitstellungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="5842c-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="5842c-134">Dies kann folgenden Konsequenzen haben:</span><span class="sxs-lookup"><span data-stu-id="5842c-134">This can have the following consequences:</span></span>

- <span data-ttu-id="5842c-135">Wenn die auf dem Server installierte Version von ASP.NET Core kleiner ist als die in der „PackageReference“ angegebene Version, kann der .NET Core-Prozess nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="5842c-136">Aktualisierungen des Metapakets sind oft auf NuGet.org verfügbar, bevor Updates in Hostingumgebungen wie Azure bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="5842c-137">Das Aktualisieren der Version auf PackageReference auf ASP.NET Core kann dazu führen, dass eine bereitgestellte Anwendung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="5842c-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="5842c-138">Wenn die Anwendung als [eigenständige Bereitstellung](../deploying/index.md#self-contained-deployments-scd) bereitgestellt wird, enthält die Anwendung möglicherweise nicht die neuesten Sicherheitsupdates für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5842c-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="5842c-139">Wenn keine Version angegeben ist, kann das SDK automatisch die neueste Version von ASP.NET Core in die eigenständige Bereitstellung aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="5842c-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="5842c-140">Standardkompilierung in .NET Core-Projekten</span><span class="sxs-lookup"><span data-stu-id="5842c-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="5842c-141">Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="5842c-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="5842c-142">Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="5842c-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="5842c-143">Der Hauptgrund dafür ist die Übersichtlichkeit in Ihrer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="5842c-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="5842c-144">Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="5842c-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="5842c-145">Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind.</span><span class="sxs-lookup"><span data-stu-id="5842c-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="5842c-146">Die folgende Tabelle zeigt, welche Elemente und welche [Globs](https://en.wikipedia.org/wiki/Glob_(programming)) im SDK enthalten und ausgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="5842c-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="5842c-147">Element</span><span class="sxs-lookup"><span data-stu-id="5842c-147">Element</span></span>           | <span data-ttu-id="5842c-148">Glob einschließen</span><span class="sxs-lookup"><span data-stu-id="5842c-148">Include glob</span></span>                              | <span data-ttu-id="5842c-149">Glob ausschließen</span><span class="sxs-lookup"><span data-stu-id="5842c-149">Exclude glob</span></span>                                                  | <span data-ttu-id="5842c-150">Glob entfernen</span><span class="sxs-lookup"><span data-stu-id="5842c-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="5842c-151">Compile</span><span class="sxs-lookup"><span data-stu-id="5842c-151">Compile</span></span>           | <span data-ttu-id="5842c-152">\*\*/\*.cs (oder andere Spracherweiterungen)</span><span class="sxs-lookup"><span data-stu-id="5842c-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="5842c-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="5842c-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="5842c-154">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="5842c-154">N/A</span></span>                      |
| <span data-ttu-id="5842c-155">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="5842c-155">EmbeddedResource</span></span>  | <span data-ttu-id="5842c-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="5842c-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="5842c-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="5842c-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="5842c-158">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="5842c-158">N/A</span></span>                      |
| <span data-ttu-id="5842c-159">Keine</span><span class="sxs-lookup"><span data-stu-id="5842c-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="5842c-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="5842c-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="5842c-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="5842c-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="5842c-162">**Glob ausschließen** schließt immer die Ordner `./bin` und `./obj` aus, die von den MSBuild-Eigenschaften `$(BaseOutputPath)` und `$(BaseIntermediateOutputPath)` dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="5842c-163">Als Ganzes werden alle Ausschlüsse von `$(DefaultItemExcludes)` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5842c-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="5842c-164">Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="5842c-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="5842c-165">Doppelte Compile-Elemente waren enthalten.</span><span class="sxs-lookup"><span data-stu-id="5842c-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="5842c-166">.NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="5842c-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="5842c-167">Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5842c-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="5842c-168">Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="5842c-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="5842c-169">Wenn diese Eigenschaft auf `false` festgelegt wird, wird der implizite Einschluss deaktiviert, und das Verhalten wird wieder auf das der vorherigen SDKs festgelegt. Bei diesem Verhalten müssen Sie die Standardglobs in Ihrem Projekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="5842c-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="5842c-170">Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht.</span><span class="sxs-lookup"><span data-stu-id="5842c-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="5842c-171">Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).</span><span class="sxs-lookup"><span data-stu-id="5842c-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="5842c-172">`<EnableDefaultCompileItems>` deaktiviert nur `Compile`-Globmuster, wirkt sich jedoch nicht auf andere Globmuster wie das implizite `None`-Globmuster aus, das ebenfalls für \*.cs-Elemente gilt.</span><span class="sxs-lookup"><span data-stu-id="5842c-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="5842c-173">Deshalb zeigt **Projektmappen-Explorer** die \*.cs-Elemente weiterhin als Teil des Projekts an, die als `None`-Elemente eingebunden wurden.</span><span class="sxs-lookup"><span data-stu-id="5842c-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="5842c-174">Sie können ebenso `<EnableDefaultNoneItems>` auf FALSE festlegen, um das implizite `None`-Globmuster zu deaktivieren, so wie hier dargestellt:</span><span class="sxs-lookup"><span data-stu-id="5842c-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="5842c-175">Sie können die `<EnableDefaultItems>`-Eigenschaft wie im folgenden Beispiel auf `false` festlegen, um **alle impliziten Globmuster** zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="5842c-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="5842c-176">Anzeige des gesamten Projekts wie in MSBuild</span><span class="sxs-lookup"><span data-stu-id="5842c-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="5842c-177">Obwohl diese csproj-Änderungen für eine erhebliche Vereinfachung der Projektdateien sorgen, möchten Sie vielleicht das vollständig erweiterte Projekt anzeigen, so wie es von MSBuild erkannt wird, nachdem das SDK und die zugehörigen Ziele eingeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="5842c-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="5842c-178">Führen Sie eine Vorverarbeitung des Projekts mit der [`/pp`-Option](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) des Befehls [`dotnet msbuild`](dotnet-msbuild.md) durch. Dieser zeigt die importierten Dateien, ihre Quellen und ihren Beitrag zum Build, ohne das Projekt tatsächlich zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5842c-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="5842c-179">Wenn das Projekt mehrere Zielframeworks umfasst, sollten nur Ergebnisse für ein Framework ausgegeben werden, indem dieses als MSBuild-Eigenschaft angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="5842c-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="5842c-180">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="5842c-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="5842c-181">SDK-Attribut</span><span class="sxs-lookup"><span data-stu-id="5842c-181">Sdk attribute</span></span>

<span data-ttu-id="5842c-182">Das `<Project>`-Stammelement der *CSPROJ*-Datei hat ein neues Attribut namens `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="5842c-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="5842c-183">`Sdk` gibt an, welches SDK vom Projekt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="5842c-184">Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](/visualstudio/msbuild/msbuild-tasks) und -[Zielen](/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können.</span><span class="sxs-lookup"><span data-stu-id="5842c-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="5842c-185">Für .NET Core sind die folgenden SDKs verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5842c-185">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="5842c-186">Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID</span><span class="sxs-lookup"><span data-stu-id="5842c-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="5842c-187">Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID</span><span class="sxs-lookup"><span data-stu-id="5842c-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="5842c-188">Das .NET Core Razor-Klassenbibliothek SDK mit der ID von `Microsoft.NET.Sdk.Razor`</span><span class="sxs-lookup"><span data-stu-id="5842c-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="5842c-189">Der .NET Core-Workerdienst mit der ID `Microsoft.NET.Sdk.Worker` (seit .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="5842c-189">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="5842c-190">.NET Core WinForms und WPF mit der ID `Microsoft.NET.Sdk.WindowsDesktop` (seit .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="5842c-190">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="5842c-191">Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="5842c-191">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="5842c-192">PackageReference</span><span class="sxs-lookup"><span data-stu-id="5842c-192">PackageReference</span></span>

<span data-ttu-id="5842c-193">Ein `<PackageReference>`-Element gibt eine [NuGet-Abhängigkeit im Projekt an](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="5842c-193">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="5842c-194">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="5842c-194">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="5842c-195">Version</span><span class="sxs-lookup"><span data-stu-id="5842c-195">Version</span></span>

<span data-ttu-id="5842c-196">Das erforderliche Attribut `Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="5842c-196">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="5842c-197">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="5842c-197">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="5842c-198">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="5842c-198">The default behavior is an exact version match.</span></span> <span data-ttu-id="5842c-199">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="5842c-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="5842c-200">IncludeAssets, ExcludeAssets und PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="5842c-200">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>

<span data-ttu-id="5842c-201">Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5842c-201">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="5842c-202">Standardmäßig sind alle Paketobjekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="5842c-202">By default, all package assets are included.</span></span>

<span data-ttu-id="5842c-203">Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5842c-203">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="5842c-204">Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5842c-204">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="5842c-205">Die Objekte `Analyzers`, `Build` und `ContentFiles` sind standardmäßig privat, wenn dieses Attribut nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-205">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="5842c-206">`PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="5842c-206">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="5842c-207">Diese Attribute können eines oder mehrere der folgenden Elemente enthalten, getrennt durch das Semikolon `;`-Zeichen, wenn mehr als eines aufgeführt ist:</span><span class="sxs-lookup"><span data-stu-id="5842c-207">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="5842c-208">`Compile` gibt an, dass die Inhalte des Ordners *lib* zum Kompilieren verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5842c-208">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="5842c-209">`Runtime` gibt an, dass die Inhalte des Ordners *runtime* verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-209">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="5842c-210">`ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-210">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="5842c-211">`Build` gibt an, dass die Eigenschaften/Ziele im Ordner *build* verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-211">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="5842c-212">`Native` gibt an, dass die Inhalte nativer Objekte für die Runtime in den *Ausgabeordner* kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-212">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="5842c-213">`Analyzers`: Gibt an, dass Analysen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="5842c-213">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="5842c-214">Alternativ kann das Attribut Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="5842c-214">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="5842c-215">`None`: Keines der Objekte wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-215">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="5842c-216">`All`: Alle Objekte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-216">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="5842c-217">DotNetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="5842c-217">DotNetCliToolReference</span></span>

<span data-ttu-id="5842c-218">Ein `<DotNetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="5842c-218">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="5842c-219">Es ist ein Ersatz für den `tools`-Knoten in *project.json*.</span><span class="sxs-lookup"><span data-stu-id="5842c-219">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="5842c-220">Version</span><span class="sxs-lookup"><span data-stu-id="5842c-220">Version</span></span>

<span data-ttu-id="5842c-221">`Version` gibt die Version des wiederherzustellenden Pakets an.</span><span class="sxs-lookup"><span data-stu-id="5842c-221">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="5842c-222">Das Attribut berücksichtigt die Regeln für das [NuGet-Versionsschema](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="5842c-222">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="5842c-223">Das Standardverhalten ist eine genau Übereinstimmung mit der Version.</span><span class="sxs-lookup"><span data-stu-id="5842c-223">The default behavior is an exact version match.</span></span> <span data-ttu-id="5842c-224">Beispiel: Die Angabe von `Version="1.2.3"` ist gleichbedeutend mit der NuGet-Notation `[1.2.3]` für die genaue 1.2.3 Version des Pakets.</span><span class="sxs-lookup"><span data-stu-id="5842c-224">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="5842c-225">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="5842c-225">RuntimeIdentifiers</span></span>

<span data-ttu-id="5842c-226">Das Eigenschaftenelement `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5842c-226">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="5842c-227">RIDs ermöglichen das Veröffentlichen eigenständiger Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="5842c-227">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="5842c-228">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="5842c-228">RuntimeIdentifier</span></span>

<span data-ttu-id="5842c-229">Das Eigenschaftenelement `<RuntimeIdentifier>` ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5842c-229">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="5842c-230">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5842c-230">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="5842c-231">Verwenden Sie stattdessen `<RuntimeIdentifiers>` (Plural), wenn Sie für mehrere Runtimes eine Veröffentlichung durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="5842c-231">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="5842c-232">Durch `<RuntimeIdentifier>` können Sie Builds schneller abschließen, wenn nur eine einzige Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-232">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="5842c-233">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="5842c-233">PackageTargetFallback</span></span>

<span data-ttu-id="5842c-234">Das Eigenschaftenelement `<PackageTargetFallback>` ermöglicht die Angabe mehrerer kompatibler Ziele, die verwendet werden, wenn Pakete wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-234">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="5842c-235">Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-235">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="5842c-236">Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="5842c-236">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="5842c-237">Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="5842c-237">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="5842c-238">Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp2.1`-Ziel angegeben:</span><span class="sxs-lookup"><span data-stu-id="5842c-238">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="5842c-239">Buildereignisse</span><span class="sxs-lookup"><span data-stu-id="5842c-239">Build events</span></span>

<span data-ttu-id="5842c-240">Die Art und Weise, wie Präbuild- und Postbuildereignisse in der Projektdatei angegeben werden, hat sich geändert.</span><span class="sxs-lookup"><span data-stu-id="5842c-240">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="5842c-241">Die Eigenschaften „PreBuildEvent“ und „PostBuildEvent“ werden im SDK-Projektformat nicht empfohlen, da Makros wie $(ProjectDir) nicht aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-241">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="5842c-242">Der folgende Code wird z. B. nicht mehr unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5842c-242">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

<span data-ttu-id="5842c-243">Verwenden Sie in Projekten im SDK-Format ein MSBuild-Ziel namens `PreBuild` oder `PostBuild`, und legen Sie die Eigenschaft `BeforeTargets` für `PreBuild` oder die Eigenschaft `AfterTargets` für `PostBuild` fest.</span><span class="sxs-lookup"><span data-stu-id="5842c-243">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="5842c-244">Verwenden Sie für das vorherige Beispiel den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="5842c-244">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="5842c-245">Sie können einen beliebigen Namen für die MSBuild-Ziele verwenden, aber die Visual Studio-IDE erkennt `PreBuild`- und `PostBuild`-Ziele. Daher empfiehlt es sich, diese Namen zu verwenden, damit Sie die Befehle in der Visual Studio-IDE bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="5842c-245">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span> 

## <a name="nuget-metadata-properties"></a><span data-ttu-id="5842c-246">NuGet-Metadateneigenschaften</span><span class="sxs-lookup"><span data-stu-id="5842c-246">NuGet metadata properties</span></span>

<span data-ttu-id="5842c-247">Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben.</span><span class="sxs-lookup"><span data-stu-id="5842c-247">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="5842c-248">Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen.</span><span class="sxs-lookup"><span data-stu-id="5842c-248">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="5842c-249">In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDK ist:</span><span class="sxs-lookup"><span data-stu-id="5842c-249">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="5842c-250">IsPackable</span><span class="sxs-lookup"><span data-stu-id="5842c-250">IsPackable</span></span>

<span data-ttu-id="5842c-251">Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5842c-251">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="5842c-252">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="5842c-252">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="5842c-253">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="5842c-253">PackageVersion</span></span>

<span data-ttu-id="5842c-254">Gibt die Version an, die das resultierende Paket haben wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-254">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="5842c-255">Akzeptiert alle Arten von NuGet-Versionszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="5842c-255">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="5842c-256">Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt.</span><span class="sxs-lookup"><span data-stu-id="5842c-256">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="5842c-257">PackageId</span><span class="sxs-lookup"><span data-stu-id="5842c-257">PackageId</span></span>

<span data-ttu-id="5842c-258">Gibt den Namen für das resultierende Paket an.</span><span class="sxs-lookup"><span data-stu-id="5842c-258">Specifies the name for the resulting package.</span></span> <span data-ttu-id="5842c-259">Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="5842c-259">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="5842c-260">Titel</span><span class="sxs-lookup"><span data-stu-id="5842c-260">Title</span></span>

<span data-ttu-id="5842c-261">Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5842c-261">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="5842c-262">Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-262">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="5842c-263">Authors</span><span class="sxs-lookup"><span data-stu-id="5842c-263">Authors</span></span>

<span data-ttu-id="5842c-264">Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="5842c-264">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="5842c-265">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="5842c-265">PackageDescription</span></span>

<span data-ttu-id="5842c-266">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="5842c-266">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="5842c-267">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5842c-267">Description</span></span>

<span data-ttu-id="5842c-268">Eine lange Beschreibung für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="5842c-268">A long description for the assembly.</span></span> <span data-ttu-id="5842c-269">Wenn `PackageDescription` nicht angegeben ist, wird diese Eigenschaft auch als Beschreibung des Pakets verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-269">If `PackageDescription` is not specified then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="5842c-270">Copyright</span><span class="sxs-lookup"><span data-stu-id="5842c-270">Copyright</span></span>

<span data-ttu-id="5842c-271">Copyright-Informationen für das Paket.</span><span class="sxs-lookup"><span data-stu-id="5842c-271">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="5842c-272">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="5842c-272">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="5842c-273">Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5842c-273">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="5842c-274">Die Standardeinstellung ist `false`.</span><span class="sxs-lookup"><span data-stu-id="5842c-274">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="5842c-275">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="5842c-275">PackageLicenseExpression</span></span>

<span data-ttu-id="5842c-276">Ein [SPDX Lizenzbezeichner](https://spdx.org/licenses/) oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5842c-276">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="5842c-277">Beispielsweise `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="5842c-277">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="5842c-278">Hier ist die vollständige Liste der [SPDX Lizenzbezeichner](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="5842c-278">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="5842c-279">NuGet.org akzeptiert nur von OSI oder FSF genehmigte Lizenzen, wenn der Ausdruck „license type“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-279">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="5842c-280">Die genaue Syntax für die Lizenzausdrücke wird unten in [ABNF](https://tools.ietf.org/html/rfc5234) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5842c-280">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="5842c-281">`PackageLicenseExpression`, `PackageLicenseFile` oder `PackageLicenseUrl` können jeweils nur einzeln angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-281">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="5842c-282">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="5842c-282">PackageLicenseFile</span></span>

<span data-ttu-id="5842c-283">Pfad zu einer Lizenzdatei innerhalb des Pakets, wenn Sie eine Lizenz verwenden, der kein SPDX-Bezeichner zugewiesen wurde, oder es sich um eine benutzerdefinierte Lizenz handelt (sonst wird `PackageLicenseExpression` bevorzugt).</span><span class="sxs-lookup"><span data-stu-id="5842c-283">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="5842c-284">Ersetzt `PackageLicenseUrl`, kann nicht mit `PackageLicenseExpression` kombiniert werden und erfordert Visual Studio 15.9.4, .NET SDK 2.1.502 oder 2.2.101 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5842c-284">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression` and requires Visual Studio 15.9.4, .NET SDK 2.1.502 or 2.2.101, or newer.</span></span>

<span data-ttu-id="5842c-285">Sie müssen sicherstellen, dass die Lizenzdatei gepackt ist, indem Sie sie explizit zum Projekt hinzufügen. Beispielnutzung:</span><span class="sxs-lookup"><span data-stu-id="5842c-285">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="5842c-286">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="5842c-286">PackageLicenseUrl</span></span>

<span data-ttu-id="5842c-287">Eine URL für die Lizenz, die auf das Paket angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5842c-287">An URL to the license that is applicable to the package.</span></span> <span data-ttu-id="5842c-288">(_seit Visual Studio 15.9.4, .NET SDK 2.1.502 und 2.2.101 veraltet_)</span><span class="sxs-lookup"><span data-stu-id="5842c-288">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="5842c-289">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="5842c-289">PackageIconUrl</span></span>

<span data-ttu-id="5842c-290">Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-290">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="5842c-291">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="5842c-291">PackageReleaseNotes</span></span>

<span data-ttu-id="5842c-292">Anmerkungen zu diesem Paket.</span><span class="sxs-lookup"><span data-stu-id="5842c-292">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="5842c-293">PackageTags</span><span class="sxs-lookup"><span data-stu-id="5842c-293">PackageTags</span></span>

<span data-ttu-id="5842c-294">Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.</span><span class="sxs-lookup"><span data-stu-id="5842c-294">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="5842c-295">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="5842c-295">PackageOutputPath</span></span>

<span data-ttu-id="5842c-296">Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-296">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="5842c-297">Der Standardwert ist `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="5842c-297">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="5842c-298">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="5842c-298">IncludeSymbols</span></span>
<span data-ttu-id="5842c-299">Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-299">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="5842c-300">Das Format des Symbolpakets wird durch die Eigenschaft `SymbolPackageFormat` gesteuert.</span><span class="sxs-lookup"><span data-stu-id="5842c-300">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="5842c-301">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="5842c-301">SymbolPackageFormat</span></span>
<span data-ttu-id="5842c-302">Gibt das Format des Symbolpakets an.</span><span class="sxs-lookup"><span data-stu-id="5842c-302">Specifies the format of the symbols package.</span></span> <span data-ttu-id="5842c-303">Im Fall von „symbols.nupkg“ wird ein älteres Symbolpaket mit der Erweiterung *.symbols.nupkg* erstellt, das PDB-, DLL- und andere Ausgabedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="5842c-303">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="5842c-304">Im Fall von „snupkg“ wird ein Symbolpaket dieses Typs erstellt, das die portablen PDB-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="5842c-304">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="5842c-305">Der Standardwert ist „symbols.nupkg“.</span><span class="sxs-lookup"><span data-stu-id="5842c-305">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="5842c-306">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="5842c-306">IncludeSource</span></span>

<span data-ttu-id="5842c-307">Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte.</span><span class="sxs-lookup"><span data-stu-id="5842c-307">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="5842c-308">Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien.</span><span class="sxs-lookup"><span data-stu-id="5842c-308">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="5842c-309">Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5842c-309">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="5842c-310">IsTool</span><span class="sxs-lookup"><span data-stu-id="5842c-310">IsTool</span></span>

<span data-ttu-id="5842c-311">Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-311">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="5842c-312">Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-312">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="5842c-313">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="5842c-313">RepositoryUrl</span></span>

<span data-ttu-id="5842c-314">Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-314">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="5842c-315">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="5842c-315">RepositoryType</span></span>

<span data-ttu-id="5842c-316">Gibt den Verzeichnistyp an.</span><span class="sxs-lookup"><span data-stu-id="5842c-316">Specifies the type of the repository.</span></span> <span data-ttu-id="5842c-317">Der Standardwert ist „Git“.</span><span class="sxs-lookup"><span data-stu-id="5842c-317">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="5842c-318">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="5842c-318">RepositoryBranch</span></span>
<span data-ttu-id="5842c-319">Gibt den Namen des Quellbranch im Repository an.</span><span class="sxs-lookup"><span data-stu-id="5842c-319">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="5842c-320">Wenn das Projekt in einem NuGet-Paket gepackt ist, wird es den Paketmetadaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5842c-320">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="5842c-321">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="5842c-321">RepositoryCommit</span></span>
<span data-ttu-id="5842c-322">Optionaler Repositorycommit oder ein Changeset, um anzugeben, für welches Quellpaket die Erstellung erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-322">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="5842c-323">`RepositoryUrl` muss ebenfalls angegeben werden, damit diese Eigenschaft einbezogen wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-323">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="5842c-324">Wenn das Projekt in einem NuGet-Paket gepackt ist, wird dieser Commit oder das Changeset den Paketmetadaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5842c-324">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="5842c-325">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="5842c-325">NoPackageAnalysis</span></span>

<span data-ttu-id="5842c-326">Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.</span><span class="sxs-lookup"><span data-stu-id="5842c-326">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="5842c-327">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="5842c-327">MinClientVersion</span></span>

<span data-ttu-id="5842c-328">Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5842c-328">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="5842c-329">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="5842c-329">IncludeBuildOutput</span></span>

<span data-ttu-id="5842c-330">Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="5842c-330">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="5842c-331">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="5842c-331">IncludeContentInPack</span></span>

<span data-ttu-id="5842c-332">Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5842c-332">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="5842c-333">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="5842c-333">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="5842c-334">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="5842c-334">BuildOutputTargetFolder</span></span>

<span data-ttu-id="5842c-335">Gibt den Ordner an, in dem die Ausgabeassemblys abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-335">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="5842c-336">Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="5842c-336">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="5842c-337">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="5842c-337">ContentTargetFolders</span></span>

<span data-ttu-id="5842c-338">Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-338">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="5842c-339">Der Standardwert ist „content;contentFiles“.</span><span class="sxs-lookup"><span data-stu-id="5842c-339">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="5842c-340">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="5842c-340">NuspecFile</span></span>

<span data-ttu-id="5842c-341">Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5842c-341">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="5842c-342">Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-342">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="5842c-343">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="5842c-343">NuspecBasePath</span></span>

<span data-ttu-id="5842c-344">Der Basispfad für die *.nuspec*-Datei.</span><span class="sxs-lookup"><span data-stu-id="5842c-344">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="5842c-345">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="5842c-345">NuspecProperties</span></span>

<span data-ttu-id="5842c-346">Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.</span><span class="sxs-lookup"><span data-stu-id="5842c-346">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="5842c-347">AssemblyInfo-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5842c-347">AssemblyInfo properties</span></span>

<span data-ttu-id="5842c-348">[Assembly-Attribute](../../standard/assembly/set-attributes.md), die normalerweise in einer *AssemblyInfo*-Datei vorlagen, werden jetzt automatisch aus Eigenschaften generiert.</span><span class="sxs-lookup"><span data-stu-id="5842c-348">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="5842c-349">Eigenschaften pro Attribut</span><span class="sxs-lookup"><span data-stu-id="5842c-349">Properties per attribute</span></span>

<span data-ttu-id="5842c-350">Jedes Attribut weist eine Eigenschaft auf, die seinen Inhalt steuert, und eine weitere zum Deaktivieren seiner Erstellung, wie in der folgenden Tabelle ersichtlich:</span><span class="sxs-lookup"><span data-stu-id="5842c-350">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="5842c-351">Attribut</span><span class="sxs-lookup"><span data-stu-id="5842c-351">Attribute</span></span>                                                      | <span data-ttu-id="5842c-352">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5842c-352">Property</span></span>               | <span data-ttu-id="5842c-353">Eigenschaft zum Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5842c-353">Property to disable</span></span>                             |
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

<span data-ttu-id="5842c-354">Notizen:</span><span class="sxs-lookup"><span data-stu-id="5842c-354">Notes:</span></span>

- <span data-ttu-id="5842c-355">Das Standardverhalten von `AssemblyVersion` und `FileVersion` besteht in der Übernahme des Werts von `$(Version)` ohne Suffix.</span><span class="sxs-lookup"><span data-stu-id="5842c-355">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="5842c-356">Wenn `$(Version)` beispielsweise `1.2.3-beta.4` ist, wäre der Wert `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="5842c-356">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="5842c-357">`InformationalVersion` hat standardmäßig den Wert von `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="5842c-357">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="5842c-358">An `InformationalVersion` ist `$(SourceRevisionId)` angefügt, wenn die Eigenschaft vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5842c-358">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="5842c-359">Sie kann mithilfe von `IncludeSourceRevisionInInformationalVersion` deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5842c-359">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="5842c-360">Die Eigenschaften `Copyright` und `Description` werden auch für NuGet-Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="5842c-360">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="5842c-361">`Configuration` wird vom gesamten Buildprozess gemeinsam verwendet und über den `--configuration`-Parameter von `dotnet`-Befehlen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5842c-361">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="5842c-362">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="5842c-362">GenerateAssemblyInfo</span></span>

<span data-ttu-id="5842c-363">Ein boolescher Wert zum Aktivieren oder Deaktivieren der AssemblyInfo-Erstellung insgesamt.</span><span class="sxs-lookup"><span data-stu-id="5842c-363">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="5842c-364">Der Standardwert ist `true`sein.</span><span class="sxs-lookup"><span data-stu-id="5842c-364">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="5842c-365">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="5842c-365">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="5842c-366">Der Pfad der generierten Assembly-Infodatei.</span><span class="sxs-lookup"><span data-stu-id="5842c-366">The path of the generated assembly info file.</span></span> <span data-ttu-id="5842c-367">Standardmäßig eine Datei im `$(IntermediateOutputPath)` (obj)-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5842c-367">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
