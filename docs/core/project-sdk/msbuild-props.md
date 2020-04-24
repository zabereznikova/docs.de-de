---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften, die vom .NET Core SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386657"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="4a890-103">MSBuild-Eigenschaften für .NET Core SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="4a890-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="4a890-104">Auf dieser Seite werden die MSBuild-Eigenschaften für das Konfigurieren von .NET Core-Projekten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a890-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="4a890-105">Diese Seite befindet sich noch in Bearbeitung und führt nicht sämtlich nützlichen MSBuild-Eigenschaften für das .NET Core SDK auf.</span><span class="sxs-lookup"><span data-stu-id="4a890-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="4a890-106">Eine Liste der gängigen MSBuild-Eigenschaften finden Sie unter [Gemeinsame MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="4a890-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="4a890-107">Frameworkeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a890-107">Framework properties</span></span>

- [<span data-ttu-id="4a890-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="4a890-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="4a890-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="4a890-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="4a890-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="4a890-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="4a890-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="4a890-111">TargetFramework</span></span>

<span data-ttu-id="4a890-112">Die Eigenschaft `TargetFramework` gibt die Zielframeworkversion für die App an, die implizit auf ein [Metapaket](../packages.md#metapackages) verweist.</span><span class="sxs-lookup"><span data-stu-id="4a890-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="4a890-113">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="4a890-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4a890-114">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4a890-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="4a890-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="4a890-115">TargetFrameworks</span></span>

<span data-ttu-id="4a890-116">Verwenden Sie die Eigenschaft `TargetFrameworks`, wenn Sie Ihre App für mehrere Zielplattformen entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="4a890-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="4a890-117">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="4a890-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="4a890-118">Diese Eigenschaft wird ignoriert, wenn `TargetFramework` (Singular) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4a890-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4a890-119">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="4a890-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="4a890-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="4a890-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="4a890-121">Diese Eigenschaft gilt nur für Projekte, die `netstandard1.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a890-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="4a890-122">Sie gilt nicht für Projekte, die `netstandard2.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a890-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="4a890-123">Verwenden Sie die Eigenschaft `NetStandardImplicitPackageVersion`, wenn Sie eine Frameworkversion angeben möchten, die niedriger ist als die [Metapaketversion](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="4a890-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="4a890-124">Die Projektdatei im folgenden Beispiel gilt für `netstandard1.3`, verwendet aber Version 1.6.0 von `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="4a890-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="4a890-125">Eigenschaften veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="4a890-125">Publish properties</span></span>

- [<span data-ttu-id="4a890-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="4a890-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="4a890-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4a890-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="4a890-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="4a890-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="4a890-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="4a890-129">RuntimeIdentifier</span></span>

<span data-ttu-id="4a890-130">Mit der Eigenschaft `RuntimeIdentifier` können Sie eine einzelne [Runtime-ID (RID)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="4a890-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4a890-131">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4a890-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="4a890-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4a890-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="4a890-133">Mit der Eigenschaft `RuntimeIdentifiers` können Sie eine durch Semikolons getrennte Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="4a890-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4a890-134">Verwenden Sie diese Eigenschaft, wenn die Veröffentlichung für mehrere Runtimes erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="4a890-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="4a890-135">`RuntimeIdentifiers` wird zur Wiederherstellungszeit verwendet, um sicherzustellen, dass sich die richtigen Assets im Graph befinden.</span><span class="sxs-lookup"><span data-stu-id="4a890-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="4a890-136">`RuntimeIdentifier` (Singular) kann schnellere Builds bereitstellen, wenn nur eine einzige Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4a890-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="4a890-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="4a890-137">UseAppHost</span></span>

<span data-ttu-id="4a890-138">Die Eigenschaft `UseAppHost` wurde in Version 2.1.400 des .NET Core SDK eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4a890-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="4a890-139">Sie steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4a890-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="4a890-140">Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4a890-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="4a890-141">In .NET Core 3.0 und höheren Versionen wird standardmäßig eine frameworkabhängige ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a890-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="4a890-142">Legen Sie die Eigenschaft `UseAppHost` auf `false` fest, um die Erzeugung der ausführbaren Datei zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4a890-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4a890-143">Weitere Informationen zur Bereitstellung finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a890-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="4a890-144">Kompilierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a890-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="4a890-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="4a890-145">LangVersion</span></span>

<span data-ttu-id="4a890-146">Mit der Eigenschaft `LangVersion` können Sie eine bestimmte Version der Programmiersprache angeben.</span><span class="sxs-lookup"><span data-stu-id="4a890-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="4a890-147">Wenn Sie beispielsweise auf C#-Vorschaufeatures zugreifen möchten, legen Sie `LangVersion` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="4a890-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="4a890-148">Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="4a890-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="4a890-149">NuGet-Pakete</span><span class="sxs-lookup"><span data-stu-id="4a890-149">NuGet packages</span></span>

- [<span data-ttu-id="4a890-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="4a890-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="4a890-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="4a890-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="4a890-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="4a890-152">PackageReference</span></span>

<span data-ttu-id="4a890-153">Mit dem Element `PackageReference` können Sie eine NuGet-Abhängigkeit angeben.</span><span class="sxs-lookup"><span data-stu-id="4a890-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="4a890-154">Beispiel: Sie möchten auf ein einzelnes Paket verweisen statt auf ein [Metapaket](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="4a890-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="4a890-155">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="4a890-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="4a890-156">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="4a890-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="4a890-157">Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="4a890-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="4a890-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="4a890-158">AssetTargetFallback</span></span>

<span data-ttu-id="4a890-159">Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projekte angeben, auf die Ihr Projekt verweist, sowie Frameworkversionen für NuGet-Pakete angeben, die Ihr Projekt nutzt.</span><span class="sxs-lookup"><span data-stu-id="4a890-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="4a890-160">Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="4a890-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="4a890-161">Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4a890-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="4a890-162">Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-framework-versions) festlegen.</span><span class="sxs-lookup"><span data-stu-id="4a890-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="4a890-163">Ziele für „pack“ und „restore“</span><span class="sxs-lookup"><span data-stu-id="4a890-163">Pack and restore targets</span></span>

<span data-ttu-id="4a890-164">In MSBuild 15.1 wurden Ziele für `pack` und `restore` eingeführt, um im Rahmen eines Buildvorgangs NuGet-Pakete zu erstellen und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4a890-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="4a890-165">Informationen zu den MSBuild-Eigenschaften für diese Ziele, einschließlich `PackageTargetFallback`, finden Sie unter [NuGet-Ziele „pack“ und „restore“ als MSBuild-Ziele](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="4a890-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a890-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a890-166">See also</span></span>

- [<span data-ttu-id="4a890-167">MSBuild-Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="4a890-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="4a890-168">Gemeinsame MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4a890-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="4a890-169">MSBuild-Eigenschaften für NuGet-Ziel „pack“</span><span class="sxs-lookup"><span data-stu-id="4a890-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="4a890-170">MSBuild-Eigenschaften für NuGet-Ziel „restore“</span><span class="sxs-lookup"><span data-stu-id="4a890-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="4a890-171">Anpassen eines Builds</span><span class="sxs-lookup"><span data-stu-id="4a890-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
