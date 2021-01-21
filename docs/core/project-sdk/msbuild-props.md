---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften und -Elemente, die vom .NET SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: e35ccc3540756a4cb7905d5864caf65cded4362b
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189978"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="8beaa-103">MSBuild-Referenz für .NET SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="8beaa-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="8beaa-104">Diese Seite ist eine Referenz für die MSBuild-Eigenschaften und -Elemente, mit denen Sie .NET-Projekte konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="8beaa-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="8beaa-105">Diese Seite befindet sich noch in Bearbeitung und führt nicht sämtlich nützlichen MSBuild-Eigenschaften für das .NET SDK auf.</span><span class="sxs-lookup"><span data-stu-id="8beaa-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="8beaa-106">Eine Liste der gängigen MSBuild-Eigenschaften finden Sie unter [Gemeinsame MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="8beaa-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="8beaa-107">Frameworkeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-107">Framework properties</span></span>

- [<span data-ttu-id="8beaa-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="8beaa-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="8beaa-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="8beaa-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="8beaa-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="8beaa-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="8beaa-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="8beaa-111">TargetFramework</span></span>

<span data-ttu-id="8beaa-112">Die Eigenschaft `TargetFramework` gibt die Zielframeworkversion für die App an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="8beaa-113">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="8beaa-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="8beaa-114">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="8beaa-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="8beaa-115">TargetFrameworks</span></span>

<span data-ttu-id="8beaa-116">Verwenden Sie die Eigenschaft `TargetFrameworks`, wenn Sie Ihre App für mehrere Zielplattformen entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="8beaa-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="8beaa-117">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="8beaa-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="8beaa-118">Diese Eigenschaft wird ignoriert, wenn `TargetFramework` (Singular) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="8beaa-119">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="8beaa-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="8beaa-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="8beaa-121">Diese Eigenschaft gilt nur für Projekte, die `netstandard1.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="8beaa-122">Sie gilt nicht für Projekte, die `netstandard2.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="8beaa-123">Verwenden Sie die Eigenschaft `NetStandardImplicitPackageVersion`, wenn Sie eine Frameworkversion angeben möchten, die niedriger ist als die Metapaketversion.</span><span class="sxs-lookup"><span data-stu-id="8beaa-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="8beaa-124">Die Projektdatei im folgenden Beispiel gilt für `netstandard1.3`, verwendet aber Version 1.6.0 von `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="8beaa-125">Paketeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-125">Package properties</span></span>

<span data-ttu-id="8beaa-126">Sie können Eigenschaften wie `PackageId`, `PackageVersion`, `PackageIcon`, `Title` und `Description` angeben, um das Paket zu beschreiben, das aus Ihrem Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="8beaa-127">Informationen zu diesen und anderen Eigenschaften finden Sie unter [Paketziel](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="8beaa-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-items-and-metadata"></a><span data-ttu-id="8beaa-128">Veröffentlichen von Eigenschaften, Elementen und Metadaten</span><span class="sxs-lookup"><span data-stu-id="8beaa-128">Publish properties, items, and metadata</span></span>

- [<span data-ttu-id="8beaa-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="8beaa-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="8beaa-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="8beaa-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="8beaa-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="8beaa-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="8beaa-132">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="8beaa-132">CopyToPublishDirectory</span></span>](#copytopublishdirectory)
- [<span data-ttu-id="8beaa-133">LinkBase</span><span class="sxs-lookup"><span data-stu-id="8beaa-133">LinkBase</span></span>](#linkbase)
- [<span data-ttu-id="8beaa-134">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="8beaa-134">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="8beaa-135">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="8beaa-135">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="8beaa-136">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="8beaa-136">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="8beaa-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="8beaa-137">UseAppHost</span></span>](#useapphost)

### <a name="copytopublishdirectory"></a><span data-ttu-id="8beaa-138">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="8beaa-138">CopyToPublishDirectory</span></span>

<span data-ttu-id="8beaa-139">Die `CopyToPublishDirectory`-Metadaten in einem MSBuild-Element steuern, wann das Element in das Veröffentlichungsverzeichnis kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-139">The `CopyToPublishDirectory` metadata on an MSBuild item controls when the item is copied to the publish directory.</span></span> <span data-ttu-id="8beaa-140">Zulässige Werte sind `PreserveNewest`, wodurch das Element nur kopiert wird, wenn es geändert wurde, `Always`, wodurch das Element immer kopiert wird, und `Never`, wodurch das Element nie kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-140">Allowable values are `PreserveNewest`, which only copies the item if it has changed, `Always`, which always copies the item, and `Never`, which never copies the item.</span></span> <span data-ttu-id="8beaa-141">Aus Leistungssicht ist `PreserveNewest` zu bevorzugen, da so inkrementelle Builds ermöglicht werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-141">From a performance standpoint, `PreserveNewest` is preferable because it enables an incremental build.</span></span>

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a><span data-ttu-id="8beaa-142">LinkBase</span><span class="sxs-lookup"><span data-stu-id="8beaa-142">LinkBase</span></span>

<span data-ttu-id="8beaa-143">Wenn ein Element sich außerhalb des Projektverzeichnisses und dessen Unterverzeichnissen befindet, verwendet das Veröffentlichungsziel die [Link-Metadaten](/visualstudio/msbuild/common-msbuild-item-metadata) des Elements, um zu bestimmen, wohin es kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8beaa-143">For an item that's outside of the project directory and its subdirectories, the publish target uses the item's [Link metadata](/visualstudio/msbuild/common-msbuild-item-metadata) to determine where to copy the item to.</span></span> <span data-ttu-id="8beaa-144">`Link` legt auch fest, wie Elemente außerhalb der Projektstruktur im Projektmappen-Explorer von Visual Studio angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-144">`Link` also determines how items outside of the project tree are displayed in the Solution Explorer window of Visual Studio.</span></span>

<span data-ttu-id="8beaa-145">Wenn `Link` für ein Element nicht angegeben ist, das sich außerhalb der Projektstruktur befindet, wird standardmäßig der Wert `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-145">If `Link` is not specified for an item that's outside of the project cone, it defaults to `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)`.</span></span> <span data-ttu-id="8beaa-146">Mit `LinkBase` können Sie einen sinnvollen Basisordner für Elemente außerhalb der Projektstruktur angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-146">`LinkBase` lets you specify a sensible base folder for items outside of the project cone.</span></span> <span data-ttu-id="8beaa-147">Die Ordnerhierarchie des Basisordners wird mit `RecursiveDir` beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8beaa-147">The folder hierarchy under the base folder is preserved via `RecursiveDir`.</span></span> <span data-ttu-id="8beaa-148">Wenn `LinkBase` nicht angegeben wird, wird das Element im `Link`-Pfad weggelassen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-148">If `LinkBase` is not specified, it's omitted from the `Link` path.</span></span>

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

<span data-ttu-id="8beaa-149">Auf der folgenden Abbildung sehen Sie, wie eine Datei, die über das Globmuster des vorherigen Elements `Include` eingefügt wird, im Projektmappen-Explorer dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-149">The following image shows how a file that's included via the previous item `Include` glob displays in Solution Explorer.</span></span>

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="Projektmappen-Explorer zeigt Element mit LinkBase-Metadaten":::

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="8beaa-151">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="8beaa-151">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="8beaa-152">Die `AppendTargetFrameworkToOutputPath`-Eigenschaft steuert, ob der [Zielframeworkmoniker (TFM, Target Framework Moniker)](../../standard/frameworks.md) an den Ausgabepfad angehängt wird, der durch [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-152">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="8beaa-153">Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-153">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="8beaa-154">Wenn Sie `AppendTargetFrameworkToOutputPath` auf `false` festlegen, wird verhindert, dass der Zielframeworkmoniker an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-154">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="8beaa-155">Jedoch überschreiben sich ohne den Zielframeworkmoniker im Ausgabepfad mehrere Buildartefakte gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="8beaa-155">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="8beaa-156">Beispielsweise wird für eine .NET 5.0-App der Ausgabepfad von `bin\Debug\net5.0` in `bin\Debug` mit der folgenden Einstellung geändert:</span><span class="sxs-lookup"><span data-stu-id="8beaa-156">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="8beaa-157">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="8beaa-157">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="8beaa-158">Die `AppendRuntimeIdentifierToOutputPath`-Eigenschaft steuert, ob der [Runtimebezeichner (RID, Runtime Identifier)](../rid-catalog.md) an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-158">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="8beaa-159">Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-159">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="8beaa-160">Wenn Sie `AppendRuntimeIdentifierToOutputPath` auf `false` festlegen, wird verhindert, dass der Runtimebezeichner an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-160">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="8beaa-161">Beispielsweise wird für eine .NET 5.0-App und einen Runtimebezeichner von `win10-x64` der Ausgabepfad von `bin\Debug\net5.0\win10-x64` in `bin\Debug\net5.0` mit der folgenden Einstellung geändert:</span><span class="sxs-lookup"><span data-stu-id="8beaa-161">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="8beaa-162">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="8beaa-162">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="8beaa-163">Die Eigenschaft `CopyLocalLockFileAssemblies` ist nützlich für Plug-In-Projekte, die von anderen Bibliotheken abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-163">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="8beaa-164">Wenn Sie diese Eigenschaft auf `true` festlegen, werden alle Abhängigkeiten von NuGet-Paketen in das Ausgabeverzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-164">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="8beaa-165">Das bedeutet, dass Sie die Ausgabe von `dotnet build` verwenden können, um das Plug-In auf einem beliebigen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-165">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="8beaa-166">Alternativ können Sie auch `dotnet publish` verwenden, um die Klassenbibliothek zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-166">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="8beaa-167">Weitere Informationen finden Sie unter [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-167">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="8beaa-168">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="8beaa-168">RuntimeIdentifier</span></span>

<span data-ttu-id="8beaa-169">Mit der Eigenschaft `RuntimeIdentifier` können Sie eine einzelne [Runtime-ID (RID)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-169">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="8beaa-170">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8beaa-170">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="8beaa-171">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="8beaa-171">RuntimeIdentifiers</span></span>

<span data-ttu-id="8beaa-172">Mit der Eigenschaft `RuntimeIdentifiers` können Sie eine durch Semikolons getrennte Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-172">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="8beaa-173">Verwenden Sie diese Eigenschaft, wenn die Veröffentlichung für mehrere Runtimes erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="8beaa-173">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="8beaa-174">`RuntimeIdentifiers` wird zur Wiederherstellungszeit verwendet, um sicherzustellen, dass sich die richtigen Assets im Graph befinden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-174">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="8beaa-175">`RuntimeIdentifier` (Singular) kann schnellere Builds bereitstellen, wenn nur eine einzige Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-175">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="8beaa-176">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="8beaa-176">TrimmerRootAssembly</span></span>

<span data-ttu-id="8beaa-177">Mit dem `TrimmerRootAssembly`-Element können Sie eine Assembly aus der [*Kürzung*](../deploying/trim-self-contained.md) ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-177">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="8beaa-178">Die Kürzung ist der Prozess, bei dem nicht verwendete Teile der Runtime aus einer gepackten Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-178">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="8beaa-179">In einigen Fällen können die erforderlichen Verweise durch eine Kürzung fälschlicherweise entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-179">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="8beaa-180">Der folgende XML-Code schließt die `System.Security`-Assembly aus der Kürzung aus.</span><span class="sxs-lookup"><span data-stu-id="8beaa-180">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="8beaa-181">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="8beaa-181">UseAppHost</span></span>

<span data-ttu-id="8beaa-182">Die `UseAppHost`-Eigenschaft steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-182">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="8beaa-183">Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8beaa-183">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="8beaa-184">In .NET Core 3.0 und höheren Versionen wird standardmäßig eine frameworkabhängige ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-184">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="8beaa-185">Legen Sie die Eigenschaft `UseAppHost` auf `false` fest, um die Erzeugung der ausführbaren Datei zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-185">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="8beaa-186">Weitere Informationen zur Bereitstellung finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-186">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="8beaa-187">Kompilierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-187">Compile properties</span></span>

- [<span data-ttu-id="8beaa-188">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="8beaa-188">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="8beaa-189">LangVersion</span><span class="sxs-lookup"><span data-stu-id="8beaa-189">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="8beaa-190">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="8beaa-190">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="8beaa-191">Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft definiert, ob Ressourcenmanifest-Dateinamen aus Typinformationen in Quelldateien generiert werden, die mit Ressourcendateien angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-191">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="8beaa-192">Wenn sich beispielsweise *Form1.resx* im selben Ordner wie *Form1.cs* befindet und `EmbeddedResourceUseDependentUponConvention` auf `true` festgelegt ist, nimmt die generierte *.resources*-Datei den Namen des ersten Typs an, der in *Form1.cs* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-192">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="8beaa-193">Wenn z. B. `MyNamespace.Form1` der erste in *Form1.cs* definierte Typ ist, lautet der generierte Dateiname *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="8beaa-193">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="8beaa-194">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element angegeben werden, basiert der generierte Manifestdateiname für diese Ressourcendatei stattdessen auf diesen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="8beaa-194">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="8beaa-195">Standardmäßig ist diese Eigenschaft in einem neuen .NET-Projekt auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-195">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="8beaa-196">Wenn bei Festlegung auf `false` keine `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für das `EmbeddedResource`-Element in der Projektdatei angegeben werden, basiert der Ressourcenmanifest-Dateiname auf dem Stammnamespace für das Projekt und dem relativen Dateipfad zur *.resx*-Datei.</span><span class="sxs-lookup"><span data-stu-id="8beaa-196">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="8beaa-197">Weitere Informationen finden Sie unter [Benennung von Ressourcenmanifestdateien](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-197">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="8beaa-198">LangVersion</span><span class="sxs-lookup"><span data-stu-id="8beaa-198">LangVersion</span></span>

<span data-ttu-id="8beaa-199">Mit der Eigenschaft `LangVersion` können Sie eine bestimmte Version der Programmiersprache angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-199">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="8beaa-200">Wenn Sie beispielsweise auf C#-Vorschaufeatures zugreifen möchten, legen Sie `LangVersion` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="8beaa-200">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="8beaa-201">Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="8beaa-201">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="8beaa-202">Standardeigenschaften für den Elementeinschluss</span><span class="sxs-lookup"><span data-stu-id="8beaa-202">Default item inclusion properties</span></span>

- [<span data-ttu-id="8beaa-203">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="8beaa-203">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="8beaa-204">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="8beaa-204">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="8beaa-205">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-205">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="8beaa-206">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-206">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="8beaa-207">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-207">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="8beaa-208">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-208">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="8beaa-209">Weitere Informationen finden Sie unter dem Abschnitt zu [standardmäßigen Include- und Excludedateien](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="8beaa-209">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="8beaa-210">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="8beaa-210">DefaultItemExcludes</span></span>

<span data-ttu-id="8beaa-211">Verwenden Sie die `DefaultItemExcludes`-Eigenschaft, um Globmuster für Dateien und Ordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-211">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="8beaa-212">Standardmäßig werden die Ordner *./bin* und *./obj* aus den Globmustern ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-212">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="8beaa-213">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="8beaa-213">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="8beaa-214">Verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft, um Globmuster für Dateien und Ordner im Projektordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-214">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="8beaa-215">Standardmäßig werden Ordner, die mit einem Punkt (`.`) beginnen, z. B. *.git* und *.vs*, aus den Globmustern ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-215">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="8beaa-216">Diese Eigenschaft ähnelt der `DefaultItemExcludes`-Eigenschaft, mit der Ausnahme, dass sie nur Dateien und Ordner im Projektordner berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-216">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="8beaa-217">Wenn ein Globmuster versehentlich mit Elementen außerhalb des Projektordners mit einem relativen Pfad übereinstimmen würde, verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft anstelle der `DefaultItemExcludes`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8beaa-217">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="8beaa-218">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-218">EnableDefaultItems</span></span>

<span data-ttu-id="8beaa-219">Die `EnableDefaultItems`-Eigenschaft steuert, ob Kompilierungselemente, eingebettete Ressourcenelemente und `None`-Elemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-219">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="8beaa-220">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-220">The default value is `true`.</span></span> <span data-ttu-id="8beaa-221">Um jedes implizite Einbeziehen von Dateien zu deaktivieren, legen Sie die `EnableDefaultItems`-Eigenschaft auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="8beaa-221">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="8beaa-222">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-222">EnableDefaultCompileItems</span></span>

<span data-ttu-id="8beaa-223">Die `EnableDefaultCompileItems`-Eigenschaft steuert, ob Kompilierungselemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-223">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="8beaa-224">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-224">The default value is `true`.</span></span> <span data-ttu-id="8beaa-225">Legen Sie die `EnableDefaultCompileItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von \*.cs-Dateien und anderen Spracherweiterungsdateien zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-225">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="8beaa-226">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-226">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="8beaa-227">Die `EnableDefaultEmbeddedResourceItems`-Eigenschaft steuert, ob eingebettete Ressourcenelemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-227">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="8beaa-228">Standardwert: `true`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-228">The default value is `true`.</span></span> <span data-ttu-id="8beaa-229">Legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf `false` fest, um die implizite Einbindung eingebetteter Ressourcendateien zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-229">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="8beaa-230">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="8beaa-230">EnableDefaultNoneItems</span></span>

<span data-ttu-id="8beaa-231">Die `EnableDefaultNoneItems`-Eigenschaft steuert, ob `None`-Elemente (Dateien, die keine Rolle im Buildprozess aufweisen) implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-231">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="8beaa-232">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-232">The default value is `true`.</span></span> <span data-ttu-id="8beaa-233">Legen Sie die `EnableDefaultNoneItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von `None`-Elementen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-233">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="8beaa-234">Codeanalyseeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-234">Code analysis properties</span></span>

- [<span data-ttu-id="8beaa-235">AnalysisLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-235">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="8beaa-236">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="8beaa-236">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="8beaa-237">CodeAnalysisTreatWarningsAsErrors-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-237">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="8beaa-238">EnableNETAnalyzers-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-238">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="8beaa-239">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="8beaa-239">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="8beaa-240">AnalysisLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-240">AnalysisLevel</span></span>

<span data-ttu-id="8beaa-241">Mit der `AnalysisLevel`-Eigenschaft können Sie eine Codeanalyseebene angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-241">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="8beaa-242">Wenn Sie beispielsweise auf Analysetools für Vorschaucode zugreifen möchten, legen Sie `AnalysisLevel` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="8beaa-242">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="8beaa-243">Standardwert: `latest`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-243">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="8beaa-244">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-244">The following table shows the available options.</span></span>

| <span data-ttu-id="8beaa-245">Wert</span><span class="sxs-lookup"><span data-stu-id="8beaa-245">Value</span></span> | <span data-ttu-id="8beaa-246">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="8beaa-246">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="8beaa-247">Die neuesten Codeanalysen, die veröffentlicht wurden, werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-247">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="8beaa-248">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="8beaa-248">This is the default.</span></span> |
| `preview` | <span data-ttu-id="8beaa-249">Die neuesten Codeanalysetools werden verwendet, auch wenn sie sich in der Vorschau befinden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-249">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="8beaa-250">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-250">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="8beaa-251">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-251">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="8beaa-252">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="8beaa-252">AnalysisMode</span></span>

<span data-ttu-id="8beaa-253">Ab .NET 5.0, sind alle [Codequalitätsregeln für Zertifizierungsstellen](../../fundamentals/code-analysis/quality-rules/index.md) im .NET SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="8beaa-253">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="8beaa-254">Standardmäßig werden nur [einige Regeln als Buildwarnungen aktiviert](../../fundamentals/code-analysis/overview.md#enabled-rules).</span><span class="sxs-lookup"><span data-stu-id="8beaa-254">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="8beaa-255">Mit der `AnalysisMode`-Eigenschaft können Sie die Regeln anpassen, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-255">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="8beaa-256">Sie können entweder zu einem aggressiveren Analysemodus (Deaktivierung) oder zu einem konservativeren Analysemodus (Aktivierung) wechseln.</span><span class="sxs-lookup"><span data-stu-id="8beaa-256">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="8beaa-257">Wenn Sie beispielsweise alle Regeln standardmäßig als Buildwarnungen aktivieren möchten, legen Sie den Wert auf `AllEnabledByDefault` fest.</span><span class="sxs-lookup"><span data-stu-id="8beaa-257">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="8beaa-258">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-258">The following table shows the available options.</span></span>

| <span data-ttu-id="8beaa-259">Wert</span><span class="sxs-lookup"><span data-stu-id="8beaa-259">Value</span></span> | <span data-ttu-id="8beaa-260">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="8beaa-260">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="8beaa-261">Dies ist der Standardmodus, in dem bestimmte Regeln als Buildwarnungen bzw. Visual Studio-IDE-Vorschläge aktiviert sind und der Rest deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-261">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="8beaa-262">Dies ist der aggressive Modus (Deaktivierung), in dem alle Regeln als Buildwarnungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-262">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="8beaa-263">Sie können einzelne Regeln [deaktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-263">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="8beaa-264">Dies ist der konservative Modus (Aktivierung), in dem alle Regeln standardmäßig deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-264">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="8beaa-265">Sie können einzelne Regeln [aktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-265">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="8beaa-266">CodeAnalysisTreatWarningsAsErrors-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-266">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="8beaa-267">Mit der `CodeAnalysisTreatWarningsAsErrors`-Eigenschaft können Sie konfigurieren, ob Warnungen im Rahmen der Codequalitätsanalyse (CAxxxx) als Warnungen behandelt werden und den Build unterbrechen sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-267">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="8beaa-268">Wenn Sie beim Erstellen von Projekten das `-warnaserror`-Flag verwenden, werden [Warnungen im Rahmen der .NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ebenfalls als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-268">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="8beaa-269">Wenn Warnungen bei der Codequalitätsanalyse nicht als Fehler behandelt werden sollen, können Sie die MSBuild-Eigenschaft `CodeAnalysisTreatWarningsAsErrors` in Ihrer Projektdatei auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-269">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="8beaa-270">EnableNETAnalyzers-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8beaa-270">EnableNETAnalyzers</span></span>

<span data-ttu-id="8beaa-271">Die [.NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ist für Projekte, die auf .NET 5.0 oder höher ausgerichtet sind, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-271">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="8beaa-272">Sie können die .NET-Codeanalyse für Projekte aktivieren, die auf frühere Versionen von .NET abzielen, indem Sie die Eigenschaft `EnableNETAnalyzers` auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-272">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="8beaa-273">Legen Sie diese Eigenschaft auf `false` fest, um die Codeanalyse in einem beliebigen Projekt zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-273">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="8beaa-274">Eine andere Möglichkeit, die .NET-Codeanalyse für Projekte zu aktivieren, die auf .NET-Versionen vor .NET 5.0 abzielen, besteht darin, die [AnalysisLevel](#analysislevel)-Eigenschaft auf `latest` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-274">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="8beaa-275">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="8beaa-275">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="8beaa-276">Hierbei handelt es sich aktuell um ein experimentelles Feature, das möglicherweise in den Versionen zwischen .NET 5 und .NET 6 geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-276">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="8beaa-277">Die [.NET-Codeformatsanalyse](../../fundamentals/code-analysis/overview.md#code-style-analysis) ist beim Build für alle .NET-Projekte standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-277">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="8beaa-278">Sie können die Codeformatsanalyse für .NET-Projekte aktivieren, indem Sie die `EnforceCodeStyleInBuild`-Eigenschaft auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-278">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="8beaa-279">Alle Codeformatregeln, die als Warnungen oder Fehler [konfiguriert](../../fundamentals/code-analysis/overview.md#code-style-analysis) sind, werden beim Build ausgeführt und melden Verstöße.</span><span class="sxs-lookup"><span data-stu-id="8beaa-279">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="8beaa-280">Runtimekonfigurationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-280">Run-time configuration properties</span></span>

<span data-ttu-id="8beaa-281">Sie können manche Verhaltensweisen der Runtime konfigurieren, indem Sie die MSBuild-Eigenschaften in der Projektdatei der App angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-281">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="8beaa-282">Informationen zu anderen Konfigurationsmöglichkeiten für das Runtimeverhalten finden Sie unter [Konfigurationseinstellungen für die Runtime](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-282">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="8beaa-283">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-283">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="8beaa-284">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="8beaa-284">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="8beaa-285">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-285">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="8beaa-286">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-286">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="8beaa-287">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8beaa-287">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="8beaa-288">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="8beaa-288">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="8beaa-289">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="8beaa-289">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="8beaa-290">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="8beaa-290">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="8beaa-291">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="8beaa-291">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="8beaa-292">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-292">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="8beaa-293">Mit der `ConcurrentGarbageCollection`-Eigenschaft wird konfiguriert, ob [die Garbage Collection im Hintergrund (parallele GC)](../../standard/garbage-collection/background-gc.md) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-293">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="8beaa-294">Legen Sie den Wert auf `false` fest, um die Garbage Collection im Hintergrund zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-294">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="8beaa-295">Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="8beaa-295">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="8beaa-296">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="8beaa-296">InvariantGlobalization</span></span>

<span data-ttu-id="8beaa-297">Mit der `InvariantGlobalization`-Eigenschaft wird konfiguriert, ob die App im *globalisierungsinvarianten Modus* ausgeführt wird, was bedeutet, dass sie keinen Zugriff auf kulturspezifische Daten hat.</span><span class="sxs-lookup"><span data-stu-id="8beaa-297">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="8beaa-298">Legen Sie den Wert auf `true` fest, um die Ausführung im globalisierungsinvarianten Modus zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-298">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="8beaa-299">Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="8beaa-299">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="8beaa-300">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-300">RetainVMGarbageCollection</span></span>

<span data-ttu-id="8beaa-301">Mit der `RetainVMGarbageCollection`-Eigenschaft wird der Garbage Collector so konfiguriert, dass gelöschte Speichersegmente in eine Standbyliste eingefügt werden, damit Sie diese zukünftig verwenden oder freigeben können.</span><span class="sxs-lookup"><span data-stu-id="8beaa-301">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="8beaa-302">Wenn der Wert auf `true` festgelegt wird, wird der Garbage Collector angewiesen, die Segmente in eine Standbyliste einzufügen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-302">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="8beaa-303">Weitere Informationen finden Sie unter [Beibehalten der VM](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="8beaa-303">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="8beaa-304">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="8beaa-304">ServerGarbageCollection</span></span>

<span data-ttu-id="8beaa-305">Mit der `ServerGarbageCollection`-Eigenschaft wird konfiguriert, ob die Anwendung die [Garbage Collection für Arbeitsstationen oder für Server](../../standard/garbage-collection/workstation-server-gc.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-305">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="8beaa-306">Legen Sie den Wert auf `true` fest, um die Garbage Collection für Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-306">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="8beaa-307">Weitere Informationen finden Sie unter [Workstation und Server im Vergleich](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="8beaa-307">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="8beaa-308">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8beaa-308">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="8beaa-309">Mit der `ThreadPoolMaxThreads`-Eigenschaft wird die maximale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-309">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="8beaa-310">Weitere Informationen finden Sie unter [Maximale Threadanzahl](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="8beaa-310">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="8beaa-311">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="8beaa-311">ThreadPoolMinThreads</span></span>

<span data-ttu-id="8beaa-312">Mit der `ThreadPoolMinThreads`-Eigenschaft wird die minimale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-312">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="8beaa-313">Weitere Informationen finden Sie unter [Minimale Threadanzahl](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="8beaa-313">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="8beaa-314">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="8beaa-314">TieredCompilation</span></span>

<span data-ttu-id="8beaa-315">Mit der `TieredCompilation`-Eigenschaft wird konfiguriert, ob der JIT-Compiler (Just-in-Time) die [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-315">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="8beaa-316">Legen Sie den Wert auf `false` fest, um die mehrstufige Kompilierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-316">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="8beaa-317">Weitere Informationen finden Sie unter [Mehrstufige Kompilierung](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="8beaa-317">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="8beaa-318">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="8beaa-318">TieredCompilationQuickJit</span></span>

<span data-ttu-id="8beaa-319">Mit der `TieredCompilationQuickJit`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-319">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="8beaa-320">Legen Sie den Wert auf `false` fest, um Quick JIT zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-320">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="8beaa-321">Weitere Informationen finden Sie unter [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="8beaa-321">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="8beaa-322">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="8beaa-322">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="8beaa-323">Mit der `TieredCompilationQuickJitForLoops`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT für Methoden mit Schleifen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-323">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="8beaa-324">Legen Sie den Wert auf `true` fest, um Quick JIT für Methoden mit Schleifen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-324">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="8beaa-325">Weitere Informationen finden Sie unter [Quick JIT für Schleifen](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="8beaa-325">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="8beaa-326">Referenz für Eigenschaften und Elemente</span><span class="sxs-lookup"><span data-stu-id="8beaa-326">Reference properties and items</span></span>

- [<span data-ttu-id="8beaa-327">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="8beaa-327">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="8beaa-328">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="8beaa-328">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="8beaa-329">PackageReference</span><span class="sxs-lookup"><span data-stu-id="8beaa-329">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="8beaa-330">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="8beaa-330">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="8beaa-331">Verweis</span><span class="sxs-lookup"><span data-stu-id="8beaa-331">Reference</span></span>](#reference)
- [<span data-ttu-id="8beaa-332">Wiederherstellungsbezogene Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-332">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="8beaa-333">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="8beaa-333">AssetTargetFallback</span></span>

<span data-ttu-id="8beaa-334">Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projektverweise und NuGet-Pakete angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-334">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="8beaa-335">Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="8beaa-335">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="8beaa-336">Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-336">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span> <span data-ttu-id="8beaa-337">Diese Eigenschaft ersetzt die veraltete Eigenschaft `PackageTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-337">This property replaces the deprecated property `PackageTargetFallback`.</span></span>

<span data-ttu-id="8beaa-338">Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-frameworks) festlegen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-338">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="8beaa-339">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="8beaa-339">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="8beaa-340">Die Eigenschaft `DisableImplicitFrameworkReferences` steuert `FrameworkReference`-Elemente implizit, wenn .NET Core 3.0 oder höher als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-340">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="8beaa-341">Wenn .NET Core 2.1 oder .NET Standard 2.0 oder niedriger als Ziel verwendet wird, steuert die Eigenschaft implizit [PackageReference](#packagereference)-Elemente für Pakete in einem Metapaket.</span><span class="sxs-lookup"><span data-stu-id="8beaa-341">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="8beaa-342">Ein Metapaket ist ein frameworkbasiertes Paket, das nur aus Abhängigkeiten von anderen Paketen besteht. Diese Eigenschaft steuert ebenfalls implizite Verweise wie `System` und `System.Core`, wenn das .NET Framework als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8beaa-342">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="8beaa-343">Legen Sie diese Eigenschaft auf `true` fest, um implizite `FrameworkReference`- oder [PackageReference](#packagereference)-Elemente zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8beaa-343">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="8beaa-344">Wenn Sie diese Eigenschaft auf `true` festlegen, können Sie auf Framework- oder Paketebene je nach Bedarf explizite Verweise hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-344">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="8beaa-345">PackageReference</span><span class="sxs-lookup"><span data-stu-id="8beaa-345">PackageReference</span></span>

<span data-ttu-id="8beaa-346">Das `PackageReference`-Element definiert einen Verweis auf ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="8beaa-346">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="8beaa-347">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-347">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="8beaa-348">Das `Version`-Attribut gibt die Version oder den Versionsbereich an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-348">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="8beaa-349">Informationen, wie Sie eine Mindestversion, Maximalversion, einen Versionsbereich oder eine exakte Versionsübereinstimmung angeben, finden Sie unter [Versionsbereiche](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="8beaa-349">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="8beaa-350">Sie können auch [Objektattribute](#asset-attributes) zu einem Paketverweis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-350">You can also add [asset attributes](#asset-attributes) to a package reference.</span></span>

<span data-ttu-id="8beaa-351">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="8beaa-351">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="8beaa-352">Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="8beaa-352">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

#### <a name="asset-attributes"></a><span data-ttu-id="8beaa-353">Objektattribute</span><span class="sxs-lookup"><span data-stu-id="8beaa-353">Asset attributes</span></span>

<span data-ttu-id="8beaa-354">Die Metadaten von `IncludeAssets`, `ExcludeAssets` und `PrivateAssets` können zu einem Paketverweis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-354">The `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets` metadata can be added to a package reference.</span></span>

| <span data-ttu-id="8beaa-355">Attribut</span><span class="sxs-lookup"><span data-stu-id="8beaa-355">Attribute</span></span> | <span data-ttu-id="8beaa-356">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8beaa-356">Description</span></span> |
| - | - |
| `IncludeAssets` | <span data-ttu-id="8beaa-357">Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-357">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="8beaa-358">Standardmäßig sind alle Paketobjekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="8beaa-358">By default, all package assets are included.</span></span> |
| `ExcludeAssets`| <span data-ttu-id="8beaa-359">Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-359">Specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span> |
| `PrivateAssets` | <span data-ttu-id="8beaa-360">Dieses Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8beaa-360">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="8beaa-361">Die Objekte `Analyzers`, `Build` und `ContentFiles` sind standardmäßig privat, wenn dieses Attribut nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-361">The `Analyzers`, `Build`, and `ContentFiles` assets are private by default when this attribute is not present.</span></span> |

<span data-ttu-id="8beaa-362">Diese Attribute können die folgenden Elemente enthalten, die durch ein `;`-Zeichen getrennt werden, wenn mehr als eines enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="8beaa-362">These attributes can contain one or more of the following items, separated by a semicolon `;` if more than one is listed:</span></span>

- <span data-ttu-id="8beaa-363">`Compile` gibt an, dass die Inhalte des Ordners *lib* zum Kompilieren verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8beaa-363">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="8beaa-364">`Runtime` gibt an, dass die Inhalte des Ordners *runtime* verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-364">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="8beaa-365">`ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-365">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="8beaa-366">`Build` gibt an, dass die Eigenschaften/Ziele im Ordner *build* verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-366">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="8beaa-367">`Native` gibt an, dass die Inhalte nativer Objekte für die Runtime in den *Ausgabeordner* kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-367">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="8beaa-368">`Analyzers`: Gibt an, dass Analysen verwendet werden</span><span class="sxs-lookup"><span data-stu-id="8beaa-368">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="8beaa-369">Alternativ kann das Attribut Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="8beaa-369">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="8beaa-370">`None`: Keines der Objekte wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-370">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="8beaa-371">`All`: Alle Objekte werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-371">`All` – all assets are used.</span></span>

### <a name="projectreference"></a><span data-ttu-id="8beaa-372">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="8beaa-372">ProjectReference</span></span>

<span data-ttu-id="8beaa-373">Das `ProjectReference`-Element definiert einen Verweis auf ein anderes Projekt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-373">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="8beaa-374">Das referenzierte Projekt wird als NuGet-Paketabhängigkeit hinzugefügt, d. h., es wird genauso wie eine `PackageReference` behandelt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-374">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="8beaa-375">Das Attribut `Include` gibt den Pfad zu dem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-375">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="8beaa-376">Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-376">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="8beaa-377">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf ein Projekt namens `Project2`.</span><span class="sxs-lookup"><span data-stu-id="8beaa-377">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="8beaa-378">Referenz</span><span class="sxs-lookup"><span data-stu-id="8beaa-378">Reference</span></span>

<span data-ttu-id="8beaa-379">Das `Reference`-Element definiert einen Verweis auf eine Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="8beaa-379">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="8beaa-380">Das `Include`-Attribut gibt den Namen der Datei an, und die `HintPath`-Metadaten geben den Pfad zu der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="8beaa-380">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="8beaa-381">Wiederherstellungsbezogene Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-381">Restore-related properties</span></span>

<span data-ttu-id="8beaa-382">Durch das Wiederherstellen eines referenzierten Pakets werden alle seine direkten Abhängigkeiten sowie alle Abhängigkeiten dieser Abhängigkeiten installiert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-382">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="8beaa-383">Sie können die Paketwiederherstellung anpassen, indem Sie Eigenschaften wie `RestorePackagesPath` und `RestoreIgnoreFailedSources` angeben.</span><span class="sxs-lookup"><span data-stu-id="8beaa-383">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="8beaa-384">Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter [Wiederherstellungsziel](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="8beaa-384">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="8beaa-385">Ausführungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-385">Run properties</span></span>

<span data-ttu-id="8beaa-386">Die folgenden Eigenschaften werden verwendet, um Apps mit dem Befehl [`dotnet run`](../tools/dotnet-run.md) zu starten:</span><span class="sxs-lookup"><span data-stu-id="8beaa-386">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="8beaa-387">RunArguments</span><span class="sxs-lookup"><span data-stu-id="8beaa-387">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="8beaa-388">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="8beaa-388">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="8beaa-389">RunArguments</span><span class="sxs-lookup"><span data-stu-id="8beaa-389">RunArguments</span></span>

<span data-ttu-id="8beaa-390">Die Eigenschaft `RunArguments` definiert die Argumente, die beim Ausführen an die App übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-390">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="8beaa-391">Sie können zusätzliche Argumente angeben, die an die App übergeben werden sollen, indem Sie die Option [`--` für `dotnet run`](../tools/dotnet-run.md#options)verwenden.</span><span class="sxs-lookup"><span data-stu-id="8beaa-391">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="8beaa-392">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="8beaa-392">RunWorkingDirectory</span></span>

<span data-ttu-id="8beaa-393">Die Eigenschaft `RunWorkingDirectory` definiert das Arbeitsverzeichnis für den Anwendungsprozess, in dem diese gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8beaa-393">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="8beaa-394">Dies kann ein absoluter Pfad oder ein Pfad sein, der relativ zum Projektverzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-394">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="8beaa-395">Wenn Sie kein Verzeichnis angeben, wird `OutDir` als Arbeitsverzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="8beaa-395">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="8beaa-396">Hostingeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-396">Hosting properties</span></span>

- [<span data-ttu-id="8beaa-397">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="8beaa-397">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="8beaa-398">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="8beaa-398">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="8beaa-399">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="8beaa-399">EnableComHosting</span></span>

<span data-ttu-id="8beaa-400">Die `EnableComHosting`-Eigenschaft gibt an, dass eine Assembly einen COM-Server bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-400">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="8beaa-401">Wenn die `EnableComHosting`-Eigenschaft auf `true` festgelegt wird, bedeutet dies auch, dass [EnableDynamicLoading](#enabledynamicloading) `true` ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-401">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="8beaa-402">Weitere Informationen finden Sie unter [Verfügbarmachen von .NET Core-Komponenten in COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-402">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="8beaa-403">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="8beaa-403">EnableDynamicLoading</span></span>

<span data-ttu-id="8beaa-404">Die `EnableDynamicLoading`-Eigenschaft gibt an, dass eine Assembly eine dynamisch geladene Komponente ist.</span><span class="sxs-lookup"><span data-stu-id="8beaa-404">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="8beaa-405">Die Komponente kann eine [COM-Bibliothek](/windows/win32/com/the-component-object-model) oder eine Nicht-COM-Bibliothek sein, die [von einem nativen Host verwendet werden kann](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="8beaa-405">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="8beaa-406">Wenn diese Eigenschaft auf `true` festgelegt wird, hat diese die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="8beaa-406">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="8beaa-407">Eine *.runtimeconfig.json*-Datei wird generiert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-407">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="8beaa-408">[Rollforward ausführen](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) wird auf `LatestMinor` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8beaa-408">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="8beaa-409">NuGet-Verweise werden lokal kopiert.</span><span class="sxs-lookup"><span data-stu-id="8beaa-409">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="8beaa-410">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8beaa-410">See also</span></span>

- [<span data-ttu-id="8beaa-411">MSBuild-Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="8beaa-411">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="8beaa-412">Gemeinsame MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8beaa-412">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="8beaa-413">MSBuild-Eigenschaften für NuGet-Ziel „pack“</span><span class="sxs-lookup"><span data-stu-id="8beaa-413">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="8beaa-414">MSBuild-Eigenschaften für NuGet-Ziel „restore“</span><span class="sxs-lookup"><span data-stu-id="8beaa-414">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="8beaa-415">Anpassen eines Builds</span><span class="sxs-lookup"><span data-stu-id="8beaa-415">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
