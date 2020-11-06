---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften und -Elemente, die vom .NET SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 463e2a163e6a20f5631b0ab82462614834156ae3
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063227"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="5e1db-103">MSBuild-Referenz für .NET SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="5e1db-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="5e1db-104">Diese Seite ist eine Referenz für die MSBuild-Eigenschaften und -Elemente, mit denen Sie .NET-Projekte konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="5e1db-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="5e1db-105">Diese Seite befindet sich noch in Bearbeitung und führt nicht sämtlich nützlichen MSBuild-Eigenschaften für das .NET SDK auf.</span><span class="sxs-lookup"><span data-stu-id="5e1db-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="5e1db-106">Eine Liste der gängigen MSBuild-Eigenschaften finden Sie unter [Gemeinsame MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="5e1db-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="5e1db-107">Frameworkeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-107">Framework properties</span></span>

- [<span data-ttu-id="5e1db-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="5e1db-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="5e1db-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="5e1db-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="5e1db-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="5e1db-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="5e1db-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="5e1db-111">TargetFramework</span></span>

<span data-ttu-id="5e1db-112">Die Eigenschaft `TargetFramework` gibt die Zielframeworkversion für die App an.</span><span class="sxs-lookup"><span data-stu-id="5e1db-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="5e1db-113">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="5e1db-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="5e1db-114">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="5e1db-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="5e1db-115">TargetFrameworks</span></span>

<span data-ttu-id="5e1db-116">Verwenden Sie die Eigenschaft `TargetFrameworks`, wenn Sie Ihre App für mehrere Zielplattformen entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="5e1db-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="5e1db-117">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="5e1db-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="5e1db-118">Diese Eigenschaft wird ignoriert, wenn `TargetFramework` (Singular) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="5e1db-119">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="5e1db-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="5e1db-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="5e1db-121">Diese Eigenschaft gilt nur für Projekte, die `netstandard1.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="5e1db-122">Sie gilt nicht für Projekte, die `netstandard2.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="5e1db-123">Verwenden Sie die Eigenschaft `NetStandardImplicitPackageVersion`, wenn Sie eine Frameworkversion angeben möchten, die niedriger ist als die Metapaketversion.</span><span class="sxs-lookup"><span data-stu-id="5e1db-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="5e1db-124">Die Projektdatei im folgenden Beispiel gilt für `netstandard1.3`, verwendet aber Version 1.6.0 von `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="5e1db-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="5e1db-125">Paketeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-125">Package properties</span></span>

<span data-ttu-id="5e1db-126">Sie können Eigenschaften wie `PackageId`, `PackageVersion`, `PackageIcon`, `Title` und `Description` angeben, um das Paket zu beschreiben, das aus Ihrem Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e1db-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="5e1db-127">Informationen zu diesen und anderen Eigenschaften finden Sie unter [Paketziel](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="5e1db-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="5e1db-128">Veröffentlichen von Eigenschaften und Elementen</span><span class="sxs-lookup"><span data-stu-id="5e1db-128">Publish properties and items</span></span>

- [<span data-ttu-id="5e1db-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="5e1db-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="5e1db-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="5e1db-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="5e1db-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="5e1db-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="5e1db-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="5e1db-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="5e1db-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="5e1db-133">RuntimeIdentifier</span></span>

<span data-ttu-id="5e1db-134">Mit der Eigenschaft `RuntimeIdentifier` können Sie eine einzelne [Runtime-ID (RID)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="5e1db-135">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5e1db-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="5e1db-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="5e1db-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="5e1db-137">Mit der Eigenschaft `RuntimeIdentifiers` können Sie eine durch Semikolons getrennte Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="5e1db-138">Verwenden Sie diese Eigenschaft, wenn die Veröffentlichung für mehrere Runtimes erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="5e1db-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="5e1db-139">`RuntimeIdentifiers` wird zur Wiederherstellungszeit verwendet, um sicherzustellen, dass sich die richtigen Assets im Graph befinden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="5e1db-140">`RuntimeIdentifier` (Singular) kann schnellere Builds bereitstellen, wenn nur eine einzige Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="5e1db-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="5e1db-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="5e1db-142">Mit dem `TrimmerRootAssembly`-Element können Sie eine Assembly aus der [*Kürzung*](../deploying/trim-self-contained.md) ausschließen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="5e1db-143">Die Kürzung ist der Prozess, bei dem nicht verwendete Teile der Runtime aus einer gepackten Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="5e1db-144">In einigen Fällen können die erforderlichen Verweise durch eine Kürzung fälschlicherweise entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="5e1db-145">Der folgende XML-Code schließt die `System.Security`-Assembly aus der Kürzung aus.</span><span class="sxs-lookup"><span data-stu-id="5e1db-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="5e1db-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="5e1db-146">UseAppHost</span></span>

<span data-ttu-id="5e1db-147">Die Eigenschaft `UseAppHost` wurde in Version 2.1.400 des .NET SDK eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET SDK.</span></span> <span data-ttu-id="5e1db-148">Sie steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e1db-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="5e1db-149">Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5e1db-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="5e1db-150">In .NET Core 3.0 und höheren Versionen wird standardmäßig eine frameworkabhängige ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="5e1db-151">Legen Sie die Eigenschaft `UseAppHost` auf `false` fest, um die Erzeugung der ausführbaren Datei zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="5e1db-152">Weitere Informationen zur Bereitstellung finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-152">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="5e1db-153">Kompilierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-153">Compile properties</span></span>

- [<span data-ttu-id="5e1db-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="5e1db-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="5e1db-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="5e1db-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="5e1db-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="5e1db-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="5e1db-157">Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft definiert, ob Ressourcenmanifest-Dateinamen aus Typinformationen in Quelldateien generiert werden, die mit Ressourcendateien angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="5e1db-158">Wenn sich beispielsweise *Form1.resx* im selben Ordner wie *Form1.cs* befindet und `EmbeddedResourceUseDependentUponConvention` auf `true` festgelegt ist, nimmt die generierte *.resources* -Datei den Namen des ersten Typs an, der in *Form1.cs* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-158">For example, if *Form1.resx* is in the same folder as *Form1.cs* , and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="5e1db-159">Wenn z. B. `MyNamespace.Form1` der erste in *Form1.cs* definierte Typ ist, lautet der generierte Dateiname *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="5e1db-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs* , the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="5e1db-160">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element angegeben werden, basiert der generierte Manifestdateiname für diese Ressourcendatei stattdessen auf diesen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="5e1db-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="5e1db-161">Standardmäßig ist diese Eigenschaft in einem neuen .NET-Projekt auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-161">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="5e1db-162">Wenn bei Festlegung auf `false` keine `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für das `EmbeddedResource`-Element in der Projektdatei angegeben werden, basiert der Ressourcenmanifest-Dateiname auf dem Stammnamespace für das Projekt und dem relativen Dateipfad zur *.resx* -Datei.</span><span class="sxs-lookup"><span data-stu-id="5e1db-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="5e1db-163">Weitere Informationen finden Sie unter [Benennung von Ressourcenmanifestdateien](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="5e1db-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="5e1db-164">LangVersion</span></span>

<span data-ttu-id="5e1db-165">Mit der Eigenschaft `LangVersion` können Sie eine bestimmte Version der Programmiersprache angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="5e1db-166">Wenn Sie beispielsweise auf C#-Vorschaufeatures zugreifen möchten, legen Sie `LangVersion` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="5e1db-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="5e1db-167">Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="5e1db-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="5e1db-168">Codeanalyseeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="5e1db-169">AnalysisLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5e1db-169">AnalysisLevel</span></span>

<span data-ttu-id="5e1db-170">Mit der `AnalysisLevel`-Eigenschaft können Sie eine Codeanalyseebene angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="5e1db-171">Wenn Sie beispielsweise auf Analysetools für Vorschaucode zugreifen möchten, legen Sie `AnalysisLevel` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="5e1db-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="5e1db-172">Standardwert: `latest`.</span><span class="sxs-lookup"><span data-stu-id="5e1db-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="5e1db-173">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-173">The following table shows the available options.</span></span>

| <span data-ttu-id="5e1db-174">Wert</span><span class="sxs-lookup"><span data-stu-id="5e1db-174">Value</span></span> | <span data-ttu-id="5e1db-175">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="5e1db-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="5e1db-176">Die neuesten Codeanalysen, die veröffentlicht wurden, werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e1db-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="5e1db-177">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="5e1db-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="5e1db-178">Die neuesten Codeanalysetools werden verwendet, auch wenn sie sich in der Vorschau befinden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="5e1db-179">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5e1db-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="5e1db-180">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5e1db-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="5e1db-181">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="5e1db-181">AnalysisMode</span></span>

<span data-ttu-id="5e1db-182">Ab .NET 5.0 RC2 umfasst das .NET SDK alle [Codequalitätsregeln für Zertifizierungsstellen](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-182">Starting with .NET 5.0 RC2, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="5e1db-183">Standardmäßig werden nur [einige Regeln als Buildwarnungen aktiviert](../../fundamentals/code-analysis/overview.md#enabled-rules).</span><span class="sxs-lookup"><span data-stu-id="5e1db-183">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="5e1db-184">Mit der `AnalysisMode`-Eigenschaft können Sie die Regeln anpassen, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5e1db-184">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="5e1db-185">Sie können entweder zu einem aggressiveren Analysemodus (Deaktivierung) oder zu einem konservativeren Analysemodus (Aktivierung) wechseln.</span><span class="sxs-lookup"><span data-stu-id="5e1db-185">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="5e1db-186">Wenn Sie beispielsweise alle Regeln standardmäßig als Buildwarnungen aktivieren möchten, legen Sie den Wert auf `AllEnabledByDefault` fest.</span><span class="sxs-lookup"><span data-stu-id="5e1db-186">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="5e1db-187">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-187">The following table shows the available options.</span></span>

| <span data-ttu-id="5e1db-188">Wert</span><span class="sxs-lookup"><span data-stu-id="5e1db-188">Value</span></span> | <span data-ttu-id="5e1db-189">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="5e1db-189">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="5e1db-190">Dies ist der Standardmodus, in dem bestimmte Regeln als Buildwarnungen bzw. Visual Studio-IDE-Vorschläge aktiviert sind und der Rest deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-190">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="5e1db-191">Dies ist der aggressive Modus (Deaktivierung), in dem alle Regeln als Buildwarnungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5e1db-191">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="5e1db-192">Sie können einzelne Regeln [deaktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-192">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="5e1db-193">Dies ist der konservative Modus (Aktivierung), in dem alle Regeln standardmäßig deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="5e1db-193">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="5e1db-194">Sie können einzelne Regeln [aktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-194">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="5e1db-195">CodeAnalysisTreatWarningsAsErrors-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5e1db-195">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="5e1db-196">Mit der `CodeAnalysisTreatWarningsAsErrors`-Eigenschaft können Sie konfigurieren, ob Warnungen im Rahmen der Codequalitätsanalyse (CAxxxx) als Warnungen behandelt werden und den Build unterbrechen sollen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-196">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="5e1db-197">Wenn Sie beim Erstellen von Projekten das `-warnaserror`-Flag verwenden, werden [Warnungen im Rahmen der .NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ebenfalls als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-197">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="5e1db-198">Wenn Warnungen bei der Codequalitätsanalyse nicht als Fehler behandelt werden sollen, können Sie die MSBuild-Eigenschaft `CodeAnalysisTreatWarningsAsErrors` in Ihrer Projektdatei auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-198">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="5e1db-199">EnableNETAnalyzers-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5e1db-199">EnableNETAnalyzers</span></span>

<span data-ttu-id="5e1db-200">Die [.NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ist für Projekte, die auf .NET 5.0 oder höher ausgerichtet sind, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5e1db-200">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="5e1db-201">Sie können die .NET-Codeanalyse für Projekte aktivieren, die auf frühere Versionen von .NET abzielen, indem Sie die Eigenschaft `EnableNETAnalyzers` auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-201">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="5e1db-202">Legen Sie diese Eigenschaft auf `false` fest, um die Codeanalyse in einem beliebigen Projekt zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-202">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="5e1db-203">Eine andere Möglichkeit, die .NET-Codeanalyse für Projekte zu aktivieren, die auf .NET-Versionen vor .NET 5.0 abzielen, besteht darin, die [AnalysisLevel](#analysislevel)-Eigenschaft auf `latest` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-203">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="5e1db-204">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="5e1db-204">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="5e1db-205">Hierbei handelt es sich aktuell um ein experimentelles Feature, das möglicherweise in den Versionen zwischen .NET 5 und .NET 6 geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5e1db-205">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="5e1db-206">Die [.NET-Codeformatsanalyse](../../fundamentals/code-analysis/overview.md#code-style-analysis) ist beim Build für alle .NET-Projekte standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5e1db-206">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="5e1db-207">Sie können die Codeformatsanalyse für .NET-Projekte aktivieren, indem Sie die `EnforceCodeStyleInBuild`-Eigenschaft auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-207">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="5e1db-208">Alle Codeformatregeln, die als Warnungen oder Fehler [konfiguriert](../../fundamentals/code-analysis/overview.md#code-style-analysis) sind, werden beim Build ausgeführt und melden Verstöße.</span><span class="sxs-lookup"><span data-stu-id="5e1db-208">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="5e1db-209">Runtimekonfigurationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-209">Run-time configuration properties</span></span>

<span data-ttu-id="5e1db-210">Sie können manche Verhaltensweisen der Runtime konfigurieren, indem Sie die MSBuild-Eigenschaften in der Projektdatei der App angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-210">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="5e1db-211">Informationen zu anderen Konfigurationsmöglichkeiten für das Runtimeverhalten finden Sie unter [Konfigurationseinstellungen für die Runtime](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e1db-211">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="5e1db-212">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-212">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="5e1db-213">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="5e1db-213">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="5e1db-214">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-214">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="5e1db-215">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-215">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="5e1db-216">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="5e1db-216">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="5e1db-217">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="5e1db-217">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="5e1db-218">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="5e1db-218">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="5e1db-219">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="5e1db-219">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="5e1db-220">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="5e1db-220">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="5e1db-221">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-221">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="5e1db-222">Mit der `ConcurrentGarbageCollection`-Eigenschaft wird konfiguriert, ob [die Garbage Collection im Hintergrund (parallele GC)](../../standard/garbage-collection/background-gc.md) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-222">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="5e1db-223">Legen Sie den Wert auf `false` fest, um die Garbage Collection im Hintergrund zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-223">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="5e1db-224">Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="5e1db-224">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="5e1db-225">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="5e1db-225">InvariantGlobalization</span></span>

<span data-ttu-id="5e1db-226">Mit der `InvariantGlobalization`-Eigenschaft wird konfiguriert, ob die App im *globalisierungsinvarianten Modus* ausgeführt wird, was bedeutet, dass sie keinen Zugriff auf kulturspezifische Daten hat.</span><span class="sxs-lookup"><span data-stu-id="5e1db-226">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="5e1db-227">Legen Sie den Wert auf `true` fest, um die Ausführung im globalisierungsinvarianten Modus zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-227">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="5e1db-228">Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="5e1db-228">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="5e1db-229">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-229">RetainVMGarbageCollection</span></span>

<span data-ttu-id="5e1db-230">Mit der `RetainVMGarbageCollection`-Eigenschaft wird der Garbage Collector so konfiguriert, dass gelöschte Speichersegmente in eine Standbyliste eingefügt werden, damit Sie diese zukünftig verwenden oder freigeben können.</span><span class="sxs-lookup"><span data-stu-id="5e1db-230">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="5e1db-231">Wenn der Wert auf `true` festgelegt wird, wird der Garbage Collector angewiesen, die Segmente in eine Standbyliste einzufügen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-231">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="5e1db-232">Weitere Informationen finden Sie unter [Beibehalten der VM](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="5e1db-232">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="5e1db-233">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="5e1db-233">ServerGarbageCollection</span></span>

<span data-ttu-id="5e1db-234">Mit der `ServerGarbageCollection`-Eigenschaft wird konfiguriert, ob die Anwendung die [Garbage Collection für Arbeitsstationen oder für Server](../../standard/garbage-collection/workstation-server-gc.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e1db-234">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="5e1db-235">Legen Sie den Wert auf `true` fest, um die Garbage Collection für Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e1db-235">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="5e1db-236">Weitere Informationen finden Sie unter [Workstation und Server im Vergleich](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="5e1db-236">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="5e1db-237">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="5e1db-237">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="5e1db-238">Mit der `ThreadPoolMaxThreads`-Eigenschaft wird die maximale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5e1db-238">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="5e1db-239">Weitere Informationen finden Sie unter [Maximale Threadanzahl](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="5e1db-239">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="5e1db-240">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="5e1db-240">ThreadPoolMinThreads</span></span>

<span data-ttu-id="5e1db-241">Mit der `ThreadPoolMinThreads`-Eigenschaft wird die minimale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5e1db-241">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="5e1db-242">Weitere Informationen finden Sie unter [Minimale Threadanzahl](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="5e1db-242">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="5e1db-243">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="5e1db-243">TieredCompilation</span></span>

<span data-ttu-id="5e1db-244">Mit der `TieredCompilation`-Eigenschaft wird konfiguriert, ob der JIT-Compiler (Just-in-Time) die [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e1db-244">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="5e1db-245">Legen Sie den Wert auf `false` fest, um die mehrstufige Kompilierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-245">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="5e1db-246">Weitere Informationen finden Sie unter [Mehrstufige Kompilierung](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="5e1db-246">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="5e1db-247">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="5e1db-247">TieredCompilationQuickJit</span></span>

<span data-ttu-id="5e1db-248">Mit der `TieredCompilationQuickJit`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e1db-248">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="5e1db-249">Legen Sie den Wert auf `false` fest, um Quick JIT zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-249">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="5e1db-250">Weitere Informationen finden Sie unter [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="5e1db-250">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="5e1db-251">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="5e1db-251">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="5e1db-252">Mit der `TieredCompilationQuickJitForLoops`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT für Methoden mit Schleifen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e1db-252">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="5e1db-253">Legen Sie den Wert auf `true` fest, um Quick JIT für Methoden mit Schleifen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5e1db-253">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="5e1db-254">Weitere Informationen finden Sie unter [Quick JIT für Schleifen](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="5e1db-254">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="5e1db-255">Referenz für Eigenschaften und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e1db-255">Reference properties and items</span></span>

- [<span data-ttu-id="5e1db-256">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="5e1db-256">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="5e1db-257">PackageReference</span><span class="sxs-lookup"><span data-stu-id="5e1db-257">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="5e1db-258">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="5e1db-258">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="5e1db-259">Verweis</span><span class="sxs-lookup"><span data-stu-id="5e1db-259">Reference</span></span>](#reference)
- [<span data-ttu-id="5e1db-260">Wiederherstellen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-260">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="5e1db-261">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="5e1db-261">AssetTargetFallback</span></span>

<span data-ttu-id="5e1db-262">Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projektverweise und NuGet-Pakete angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-262">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="5e1db-263">Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="5e1db-263">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="5e1db-264">Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5e1db-264">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="5e1db-265">Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-frameworks) festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e1db-265">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="5e1db-266">PackageReference</span><span class="sxs-lookup"><span data-stu-id="5e1db-266">PackageReference</span></span>

<span data-ttu-id="5e1db-267">Das `PackageReference`-Element definiert einen Verweis auf ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="5e1db-267">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="5e1db-268">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="5e1db-268">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="5e1db-269">Das `Version`-Attribut gibt die Version oder den Versionsbereich an.</span><span class="sxs-lookup"><span data-stu-id="5e1db-269">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="5e1db-270">Informationen, wie Sie eine Mindestversion, Maximalversion, einen Versionsbereich oder eine exakte Versionsübereinstimmung angeben, finden Sie unter [Versionsbereiche](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="5e1db-270">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="5e1db-271">Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="5e1db-271">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="5e1db-272">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="5e1db-272">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="5e1db-273">Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="5e1db-273">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="5e1db-274">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="5e1db-274">ProjectReference</span></span>

<span data-ttu-id="5e1db-275">Das `ProjectReference`-Element definiert einen Verweis auf ein anderes Projekt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-275">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="5e1db-276">Das referenzierte Projekt wird als NuGet-Paketabhängigkeit hinzugefügt, d. h., es wird genauso wie eine `PackageReference` behandelt.</span><span class="sxs-lookup"><span data-stu-id="5e1db-276">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="5e1db-277">Das Attribut `Include` gibt den Pfad zu dem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="5e1db-277">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="5e1db-278">Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="5e1db-278">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="5e1db-279">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf ein Projekt namens `Project2`.</span><span class="sxs-lookup"><span data-stu-id="5e1db-279">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="5e1db-280">Referenz</span><span class="sxs-lookup"><span data-stu-id="5e1db-280">Reference</span></span>

<span data-ttu-id="5e1db-281">Das `Reference`-Element definiert einen Verweis auf eine Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="5e1db-281">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="5e1db-282">Das `Include`-Attribut gibt den Namen der Datei an, und die `HintPath`-Metadaten geben den Pfad zu der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="5e1db-282">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="5e1db-283">Wiederherstellen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-283">Restore properties</span></span>

<span data-ttu-id="5e1db-284">Durch das Wiederherstellen eines referenzierten Pakets werden alle seine direkten Abhängigkeiten sowie alle Abhängigkeiten dieser Abhängigkeiten installiert.</span><span class="sxs-lookup"><span data-stu-id="5e1db-284">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="5e1db-285">Sie können die Paketwiederherstellung anpassen, indem Sie Eigenschaften wie `RestorePackagesPath` und `RestoreIgnoreFailedSources` angeben.</span><span class="sxs-lookup"><span data-stu-id="5e1db-285">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="5e1db-286">Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter [Wiederherstellungsziel](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="5e1db-286">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="5e1db-287">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e1db-287">See also</span></span>

- [<span data-ttu-id="5e1db-288">MSBuild-Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="5e1db-288">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="5e1db-289">Gemeinsame MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e1db-289">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="5e1db-290">MSBuild-Eigenschaften für NuGet-Ziel „pack“</span><span class="sxs-lookup"><span data-stu-id="5e1db-290">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="5e1db-291">MSBuild-Eigenschaften für NuGet-Ziel „restore“</span><span class="sxs-lookup"><span data-stu-id="5e1db-291">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="5e1db-292">Anpassen eines Builds</span><span class="sxs-lookup"><span data-stu-id="5e1db-292">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
