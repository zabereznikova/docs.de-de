---
title: MSBuild-Eigenschaften für Microsoft.NET.Sdk
description: Referenz für MSBuild-Eigenschaften und -Elemente, die vom .NET SDK verstanden werden.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: e7deb8c32fd01452524122e41f758ab037020ee4
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970706"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="dc1b5-103">MSBuild-Referenz für .NET SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="dc1b5-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="dc1b5-104">Diese Seite ist eine Referenz für die MSBuild-Eigenschaften und -Elemente, mit denen Sie .NET-Projekte konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="dc1b5-105">Diese Seite befindet sich noch in Bearbeitung und führt nicht sämtlich nützlichen MSBuild-Eigenschaften für das .NET SDK auf.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="dc1b5-106">Eine Liste der gängigen MSBuild-Eigenschaften finden Sie unter [Gemeinsame MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="dc1b5-107">Frameworkeigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-107">Framework properties</span></span>

- [<span data-ttu-id="dc1b5-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="dc1b5-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="dc1b5-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="dc1b5-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="dc1b5-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="dc1b5-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="dc1b5-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="dc1b5-111">TargetFramework</span></span>

<span data-ttu-id="dc1b5-112">Die Eigenschaft `TargetFramework` gibt die Zielframeworkversion für die App an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="dc1b5-113">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-114">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="dc1b5-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="dc1b5-115">TargetFrameworks</span></span>

<span data-ttu-id="dc1b5-116">Verwenden Sie die Eigenschaft `TargetFrameworks`, wenn Sie Ihre App für mehrere Zielplattformen entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="dc1b5-117">Eine Liste gültiger Zielframeworkmoniker finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="dc1b5-118">Diese Eigenschaft wird ignoriert, wenn `TargetFramework` (Singular) angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-119">Weitere Informationen finden Sie unter [Zielframeworks in Projekten im SDK-Format](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="dc1b5-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="dc1b5-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="dc1b5-121">Diese Eigenschaft gilt nur für Projekte, die `netstandard1.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="dc1b5-122">Sie gilt nicht für Projekte, die `netstandard2.x` verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="dc1b5-123">Verwenden Sie die Eigenschaft `NetStandardImplicitPackageVersion`, wenn Sie eine Frameworkversion angeben möchten, die niedriger ist als die Metapaketversion.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="dc1b5-124">Die Projektdatei im folgenden Beispiel gilt für `netstandard1.3`, verwendet aber Version 1.6.0 von `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="dc1b5-125">Paketeigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-125">Package properties</span></span>

<span data-ttu-id="dc1b5-126">Sie können Eigenschaften wie `PackageId`, `PackageVersion`, `PackageIcon`, `Title` und `Description` angeben, um das Paket zu beschreiben, das aus Ihrem Projekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="dc1b5-127">Informationen zu diesen und anderen Eigenschaften finden Sie unter [Paketziel](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="dc1b5-128">Veröffentlichen von Eigenschaften und Elementen</span><span class="sxs-lookup"><span data-stu-id="dc1b5-128">Publish properties and items</span></span>

- [<span data-ttu-id="dc1b5-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="dc1b5-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="dc1b5-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="dc1b5-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="dc1b5-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="dc1b5-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="dc1b5-132">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="dc1b5-132">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="dc1b5-133">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="dc1b5-133">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="dc1b5-134">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="dc1b5-134">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="dc1b5-135">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="dc1b5-135">UseAppHost</span></span>](#useapphost)

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="dc1b5-136">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="dc1b5-136">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="dc1b5-137">Die `AppendTargetFrameworkToOutputPath`-Eigenschaft steuert, ob der [Zielframeworkmoniker (TFM, Target Framework Moniker)](../../standard/frameworks.md) an den Ausgabepfad angehängt wird, der durch [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-137">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="dc1b5-138">Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-138">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="dc1b5-139">Wenn Sie `AppendTargetFrameworkToOutputPath` auf `false` festlegen, wird verhindert, dass der Zielframeworkmoniker an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-139">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="dc1b5-140">Jedoch überschreiben sich ohne den Zielframeworkmoniker im Ausgabepfad mehrere Buildartefakte gegenseitig.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-140">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="dc1b5-141">Beispielsweise wird für eine .NET 5.0-App der Ausgabepfad von `bin\Debug\net5.0` in `bin\Debug` mit der folgenden Einstellung geändert:</span><span class="sxs-lookup"><span data-stu-id="dc1b5-141">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="dc1b5-142">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="dc1b5-142">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="dc1b5-143">Die `AppendRuntimeIdentifierToOutputPath`-Eigenschaft steuert, ob der [Runtimebezeichner (RID, Runtime Identifier)](../rid-catalog.md) an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-143">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="dc1b5-144">Das .NET SDK fügt automatisch das Zielframework und, falls vorhanden, den Runtimebezeichner an den Ausgabepfad an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-144">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="dc1b5-145">Wenn Sie `AppendRuntimeIdentifierToOutputPath` auf `false` festlegen, wird verhindert, dass der Runtimebezeichner an den Ausgabepfad angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-145">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="dc1b5-146">Beispielsweise wird für eine .NET 5.0-App und einen Runtimebezeichner von `win10-x64` der Ausgabepfad von `bin\Debug\net5.0\win10-x64` in `bin\Debug\net5.0` mit der folgenden Einstellung geändert:</span><span class="sxs-lookup"><span data-stu-id="dc1b5-146">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="dc1b5-147">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="dc1b5-147">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="dc1b5-148">Die Eigenschaft `CopyLocalLockFileAssemblies` ist nützlich für Plug-In-Projekte, die von anderen Bibliotheken abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-148">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="dc1b5-149">Wenn Sie diese Eigenschaft auf `true` festlegen, werden alle Abhängigkeiten von NuGet-Paketen in das Ausgabeverzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-149">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="dc1b5-150">Das bedeutet, dass Sie die Ausgabe von `dotnet build` verwenden können, um das Plug-In auf einem beliebigen Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-150">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="dc1b5-151">Alternativ können Sie auch `dotnet publish` verwenden, um die Klassenbibliothek zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-151">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="dc1b5-152">Weitere Informationen finden Sie unter [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-152">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="dc1b5-153">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="dc1b5-153">RuntimeIdentifier</span></span>

<span data-ttu-id="dc1b5-154">Mit der Eigenschaft `RuntimeIdentifier` können Sie eine einzelne [Runtime-ID (RID)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-154">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="dc1b5-155">RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-155">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="dc1b5-156">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="dc1b5-156">RuntimeIdentifiers</span></span>

<span data-ttu-id="dc1b5-157">Mit der Eigenschaft `RuntimeIdentifiers` können Sie eine durch Semikolons getrennte Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-157">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="dc1b5-158">Verwenden Sie diese Eigenschaft, wenn die Veröffentlichung für mehrere Runtimes erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-158">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="dc1b5-159">`RuntimeIdentifiers` wird zur Wiederherstellungszeit verwendet, um sicherzustellen, dass sich die richtigen Assets im Graph befinden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-159">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="dc1b5-160">`RuntimeIdentifier` (Singular) kann schnellere Builds bereitstellen, wenn nur eine einzige Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-160">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="dc1b5-161">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="dc1b5-161">TrimmerRootAssembly</span></span>

<span data-ttu-id="dc1b5-162">Mit dem `TrimmerRootAssembly`-Element können Sie eine Assembly aus der [*Kürzung*](../deploying/trim-self-contained.md) ausschließen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-162">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="dc1b5-163">Die Kürzung ist der Prozess, bei dem nicht verwendete Teile der Runtime aus einer gepackten Anwendung entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-163">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="dc1b5-164">In einigen Fällen können die erforderlichen Verweise durch eine Kürzung fälschlicherweise entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-164">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="dc1b5-165">Der folgende XML-Code schließt die `System.Security`-Assembly aus der Kürzung aus.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-165">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="dc1b5-166">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="dc1b5-166">UseAppHost</span></span>

<span data-ttu-id="dc1b5-167">Die `UseAppHost`-Eigenschaft steuert, ob eine native ausführbare Datei für eine Bereitstellung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-167">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="dc1b5-168">Eine native ausführbare Datei ist für eigenständige Bereitstellungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-168">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="dc1b5-169">In .NET Core 3.0 und höheren Versionen wird standardmäßig eine frameworkabhängige ausführbare Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-169">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="dc1b5-170">Legen Sie die Eigenschaft `UseAppHost` auf `false` fest, um die Erzeugung der ausführbaren Datei zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-170">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-171">Weitere Informationen zur Bereitstellung finden Sie unter [.NET-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-171">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="dc1b5-172">Kompilierungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-172">Compile properties</span></span>

- [<span data-ttu-id="dc1b5-173">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="dc1b5-173">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="dc1b5-174">LangVersion</span><span class="sxs-lookup"><span data-stu-id="dc1b5-174">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="dc1b5-175">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="dc1b5-175">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="dc1b5-176">Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft definiert, ob Ressourcenmanifest-Dateinamen aus Typinformationen in Quelldateien generiert werden, die mit Ressourcendateien angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-176">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="dc1b5-177">Wenn sich beispielsweise *Form1.resx* im selben Ordner wie *Form1.cs* befindet und `EmbeddedResourceUseDependentUponConvention` auf `true` festgelegt ist, nimmt die generierte *.resources*-Datei den Namen des ersten Typs an, der in *Form1.cs* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-177">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="dc1b5-178">Wenn z. B. `MyNamespace.Form1` der erste in *Form1.cs* definierte Typ ist, lautet der generierte Dateiname *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-178">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="dc1b5-179">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element angegeben werden, basiert der generierte Manifestdateiname für diese Ressourcendatei stattdessen auf diesen Metadaten.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-179">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="dc1b5-180">Standardmäßig ist diese Eigenschaft in einem neuen .NET-Projekt auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-180">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="dc1b5-181">Wenn bei Festlegung auf `false` keine `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für das `EmbeddedResource`-Element in der Projektdatei angegeben werden, basiert der Ressourcenmanifest-Dateiname auf dem Stammnamespace für das Projekt und dem relativen Dateipfad zur *.resx*-Datei.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-181">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="dc1b5-182">Weitere Informationen finden Sie unter [Benennung von Ressourcenmanifestdateien](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-182">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="dc1b5-183">LangVersion</span><span class="sxs-lookup"><span data-stu-id="dc1b5-183">LangVersion</span></span>

<span data-ttu-id="dc1b5-184">Mit der Eigenschaft `LangVersion` können Sie eine bestimmte Version der Programmiersprache angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-184">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="dc1b5-185">Wenn Sie beispielsweise auf C#-Vorschaufeatures zugreifen möchten, legen Sie `LangVersion` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-185">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-186">Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-186">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="dc1b5-187">Standardeigenschaften für den Elementeinschluss</span><span class="sxs-lookup"><span data-stu-id="dc1b5-187">Default item inclusion properties</span></span>

- [<span data-ttu-id="dc1b5-188">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="dc1b5-188">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="dc1b5-189">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="dc1b5-189">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="dc1b5-190">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-190">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="dc1b5-191">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-191">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="dc1b5-192">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-192">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="dc1b5-193">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-193">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="dc1b5-194">Weitere Informationen finden Sie unter dem Abschnitt zu [standardmäßigen Include- und Excludedateien](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-194">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="dc1b5-195">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="dc1b5-195">DefaultItemExcludes</span></span>

<span data-ttu-id="dc1b5-196">Verwenden Sie die `DefaultItemExcludes`-Eigenschaft, um Globmuster für Dateien und Ordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-196">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="dc1b5-197">Standardmäßig werden die Ordner *./bin* und *./obj* aus den Globmustern ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-197">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="dc1b5-198">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="dc1b5-198">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="dc1b5-199">Verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft, um Globmuster für Dateien und Ordner im Projektordner zu definieren, die aus der Include- und Excludedatei sowie Remove-Globs ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-199">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="dc1b5-200">Standardmäßig werden Ordner, die mit einem Punkt (`.`) beginnen, z. B. *.git* und *.vs*, aus den Globmustern ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-200">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="dc1b5-201">Diese Eigenschaft ähnelt der `DefaultItemExcludes`-Eigenschaft, mit der Ausnahme, dass sie nur Dateien und Ordner im Projektordner berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-201">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="dc1b5-202">Wenn ein Globmuster versehentlich mit Elementen außerhalb des Projektordners mit einem relativen Pfad übereinstimmen würde, verwenden Sie die `DefaultExcludesInProjectFolder`-Eigenschaft anstelle der `DefaultItemExcludes`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-202">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="dc1b5-203">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-203">EnableDefaultItems</span></span>

<span data-ttu-id="dc1b5-204">Die `EnableDefaultItems`-Eigenschaft steuert, ob Kompilierungselemente, eingebettete Ressourcenelemente und `None`-Elemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-204">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="dc1b5-205">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-205">The default value is `true`.</span></span> <span data-ttu-id="dc1b5-206">Um jedes implizite Einbeziehen von Dateien zu deaktivieren, legen Sie die `EnableDefaultItems`-Eigenschaft auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-206">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="dc1b5-207">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-207">EnableDefaultCompileItems</span></span>

<span data-ttu-id="dc1b5-208">Die `EnableDefaultCompileItems`-Eigenschaft steuert, ob Kompilierungselemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-208">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="dc1b5-209">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-209">The default value is `true`.</span></span> <span data-ttu-id="dc1b5-210">Legen Sie die `EnableDefaultCompileItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von \*.cs-Dateien und anderen Spracherweiterungsdateien zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-210">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="dc1b5-211">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-211">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="dc1b5-212">Die `EnableDefaultEmbeddedResourceItems`-Eigenschaft steuert, ob eingebettete Ressourcenelemente implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-212">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="dc1b5-213">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-213">The default value is `true`.</span></span> <span data-ttu-id="dc1b5-214">Legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf `false` fest, um die implizite Einbindung eingebetteter Ressourcendateien zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-214">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="dc1b5-215">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="dc1b5-215">EnableDefaultNoneItems</span></span>

<span data-ttu-id="dc1b5-216">Die `EnableDefaultNoneItems`-Eigenschaft steuert, ob `None`-Elemente (Dateien, die keine Rolle im Buildprozess aufweisen) implizit in das Projekt eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-216">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="dc1b5-217">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-217">The default value is `true`.</span></span> <span data-ttu-id="dc1b5-218">Legen Sie die `EnableDefaultNoneItems`-Eigenschaft auf `false` fest, um die implizite Einbindung von `None`-Elementen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-218">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="dc1b5-219">Codeanalyseeigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-219">Code analysis properties</span></span>

- [<span data-ttu-id="dc1b5-220">AnalysisLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-220">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="dc1b5-221">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="dc1b5-221">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="dc1b5-222">CodeAnalysisTreatWarningsAsErrors-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-222">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="dc1b5-223">EnableNETAnalyzers-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-223">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="dc1b5-224">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="dc1b5-224">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="dc1b5-225">AnalysisLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-225">AnalysisLevel</span></span>

<span data-ttu-id="dc1b5-226">Mit der `AnalysisLevel`-Eigenschaft können Sie eine Codeanalyseebene angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-226">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="dc1b5-227">Wenn Sie beispielsweise auf Analysetools für Vorschaucode zugreifen möchten, legen Sie `AnalysisLevel` auf `preview` fest.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-227">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="dc1b5-228">Standardwert: `latest`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-228">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-229">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-229">The following table shows the available options.</span></span>

| <span data-ttu-id="dc1b5-230">Wert</span><span class="sxs-lookup"><span data-stu-id="dc1b5-230">Value</span></span> | <span data-ttu-id="dc1b5-231">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="dc1b5-231">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="dc1b5-232">Die neuesten Codeanalysen, die veröffentlicht wurden, werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-232">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="dc1b5-233">Dies ist die Standardoption.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-233">This is the default.</span></span> |
| `preview` | <span data-ttu-id="dc1b5-234">Die neuesten Codeanalysetools werden verwendet, auch wenn sie sich in der Vorschau befinden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-234">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="dc1b5-235">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-235">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="dc1b5-236">Die Regeln, die für das .NET 5.0-Release aktiviert wurden, werden verwendet, auch wenn neuere Regeln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-236">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="dc1b5-237">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="dc1b5-237">AnalysisMode</span></span>

<span data-ttu-id="dc1b5-238">Ab .NET 5.0, sind alle [Codequalitätsregeln für Zertifizierungsstellen](../../fundamentals/code-analysis/quality-rules/index.md) im .NET SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-238">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="dc1b5-239">Standardmäßig werden nur [einige Regeln als Buildwarnungen aktiviert](../../fundamentals/code-analysis/overview.md#enabled-rules).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-239">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="dc1b5-240">Mit der `AnalysisMode`-Eigenschaft können Sie die Regeln anpassen, die standardmäßig aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-240">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="dc1b5-241">Sie können entweder zu einem aggressiveren Analysemodus (Deaktivierung) oder zu einem konservativeren Analysemodus (Aktivierung) wechseln.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-241">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="dc1b5-242">Wenn Sie beispielsweise alle Regeln standardmäßig als Buildwarnungen aktivieren möchten, legen Sie den Wert auf `AllEnabledByDefault` fest.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-242">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-243">Die verfügbaren Optionen sind in der nachfolgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-243">The following table shows the available options.</span></span>

| <span data-ttu-id="dc1b5-244">Wert</span><span class="sxs-lookup"><span data-stu-id="dc1b5-244">Value</span></span> | <span data-ttu-id="dc1b5-245">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="dc1b5-245">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="dc1b5-246">Dies ist der Standardmodus, in dem bestimmte Regeln als Buildwarnungen bzw. Visual Studio-IDE-Vorschläge aktiviert sind und der Rest deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-246">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="dc1b5-247">Dies ist der aggressive Modus (Deaktivierung), in dem alle Regeln als Buildwarnungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-247">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="dc1b5-248">Sie können einzelne Regeln [deaktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-248">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="dc1b5-249">Dies ist der konservative Modus (Aktivierung), in dem alle Regeln standardmäßig deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-249">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="dc1b5-250">Sie können einzelne Regeln [aktivieren](../../fundamentals/code-analysis/configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-250">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="dc1b5-251">CodeAnalysisTreatWarningsAsErrors-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-251">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="dc1b5-252">Mit der `CodeAnalysisTreatWarningsAsErrors`-Eigenschaft können Sie konfigurieren, ob Warnungen im Rahmen der Codequalitätsanalyse (CAxxxx) als Warnungen behandelt werden und den Build unterbrechen sollen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-252">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="dc1b5-253">Wenn Sie beim Erstellen von Projekten das `-warnaserror`-Flag verwenden, werden [Warnungen im Rahmen der .NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ebenfalls als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-253">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="dc1b5-254">Wenn Warnungen bei der Codequalitätsanalyse nicht als Fehler behandelt werden sollen, können Sie die MSBuild-Eigenschaft `CodeAnalysisTreatWarningsAsErrors` in Ihrer Projektdatei auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-254">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="dc1b5-255">EnableNETAnalyzers-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc1b5-255">EnableNETAnalyzers</span></span>

<span data-ttu-id="dc1b5-256">Die [.NET-Codequalitätsanalyse](../../fundamentals/code-analysis/overview.md#code-quality-analysis) ist für Projekte, die auf .NET 5.0 oder höher ausgerichtet sind, standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-256">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="dc1b5-257">Sie können die .NET-Codeanalyse für Projekte aktivieren, die auf frühere Versionen von .NET abzielen, indem Sie die Eigenschaft `EnableNETAnalyzers` auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-257">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="dc1b5-258">Legen Sie diese Eigenschaft auf `false` fest, um die Codeanalyse in einem beliebigen Projekt zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-258">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="dc1b5-259">Eine andere Möglichkeit, die .NET-Codeanalyse für Projekte zu aktivieren, die auf .NET-Versionen vor .NET 5.0 abzielen, besteht darin, die [AnalysisLevel](#analysislevel)-Eigenschaft auf `latest` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-259">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="dc1b5-260">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="dc1b5-260">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="dc1b5-261">Hierbei handelt es sich aktuell um ein experimentelles Feature, das möglicherweise in den Versionen zwischen .NET 5 und .NET 6 geändert wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-261">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="dc1b5-262">Die [.NET-Codeformatsanalyse](../../fundamentals/code-analysis/overview.md#code-style-analysis) ist beim Build für alle .NET-Projekte standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-262">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="dc1b5-263">Sie können die Codeformatsanalyse für .NET-Projekte aktivieren, indem Sie die `EnforceCodeStyleInBuild`-Eigenschaft auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-263">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-264">Alle Codeformatregeln, die als Warnungen oder Fehler [konfiguriert](../../fundamentals/code-analysis/overview.md#code-style-analysis) sind, werden beim Build ausgeführt und melden Verstöße.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-264">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="dc1b5-265">Runtimekonfigurationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-265">Run-time configuration properties</span></span>

<span data-ttu-id="dc1b5-266">Sie können manche Verhaltensweisen der Runtime konfigurieren, indem Sie die MSBuild-Eigenschaften in der Projektdatei der App angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-266">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="dc1b5-267">Informationen zu anderen Konfigurationsmöglichkeiten für das Runtimeverhalten finden Sie unter [Konfigurationseinstellungen für die Runtime](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-267">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="dc1b5-268">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-268">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="dc1b5-269">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="dc1b5-269">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="dc1b5-270">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-270">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="dc1b5-271">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-271">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="dc1b5-272">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="dc1b5-272">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="dc1b5-273">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="dc1b5-273">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="dc1b5-274">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="dc1b5-274">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="dc1b5-275">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="dc1b5-275">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="dc1b5-276">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="dc1b5-276">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="dc1b5-277">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-277">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="dc1b5-278">Mit der `ConcurrentGarbageCollection`-Eigenschaft wird konfiguriert, ob [die Garbage Collection im Hintergrund (parallele GC)](../../standard/garbage-collection/background-gc.md) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-278">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="dc1b5-279">Legen Sie den Wert auf `false` fest, um die Garbage Collection im Hintergrund zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-279">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="dc1b5-280">Weitere Informationen finden Sie unter [Garbage Collection im Hintergrund](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-280">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="dc1b5-281">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="dc1b5-281">InvariantGlobalization</span></span>

<span data-ttu-id="dc1b5-282">Mit der `InvariantGlobalization`-Eigenschaft wird konfiguriert, ob die App im *globalisierungsinvarianten Modus* ausgeführt wird, was bedeutet, dass sie keinen Zugriff auf kulturspezifische Daten hat.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-282">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="dc1b5-283">Legen Sie den Wert auf `true` fest, um die Ausführung im globalisierungsinvarianten Modus zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-283">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="dc1b5-284">Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-284">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="dc1b5-285">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-285">RetainVMGarbageCollection</span></span>

<span data-ttu-id="dc1b5-286">Mit der `RetainVMGarbageCollection`-Eigenschaft wird der Garbage Collector so konfiguriert, dass gelöschte Speichersegmente in eine Standbyliste eingefügt werden, damit Sie diese zukünftig verwenden oder freigeben können.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-286">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="dc1b5-287">Wenn der Wert auf `true` festgelegt wird, wird der Garbage Collector angewiesen, die Segmente in eine Standbyliste einzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-287">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="dc1b5-288">Weitere Informationen finden Sie unter [Beibehalten der VM](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-288">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="dc1b5-289">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="dc1b5-289">ServerGarbageCollection</span></span>

<span data-ttu-id="dc1b5-290">Mit der `ServerGarbageCollection`-Eigenschaft wird konfiguriert, ob die Anwendung die [Garbage Collection für Arbeitsstationen oder für Server](../../standard/garbage-collection/workstation-server-gc.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-290">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="dc1b5-291">Legen Sie den Wert auf `true` fest, um die Garbage Collection für Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-291">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="dc1b5-292">Weitere Informationen finden Sie unter [Workstation und Server im Vergleich](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-292">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="dc1b5-293">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="dc1b5-293">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="dc1b5-294">Mit der `ThreadPoolMaxThreads`-Eigenschaft wird die maximale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-294">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="dc1b5-295">Weitere Informationen finden Sie unter [Maximale Threadanzahl](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-295">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="dc1b5-296">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="dc1b5-296">ThreadPoolMinThreads</span></span>

<span data-ttu-id="dc1b5-297">Mit der `ThreadPoolMinThreads`-Eigenschaft wird die minimale Threadanzahl für den Arbeitsthreadpool konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-297">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="dc1b5-298">Weitere Informationen finden Sie unter [Minimale Threadanzahl](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-298">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="dc1b5-299">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="dc1b5-299">TieredCompilation</span></span>

<span data-ttu-id="dc1b5-300">Mit der `TieredCompilation`-Eigenschaft wird konfiguriert, ob der JIT-Compiler (Just-in-Time) die [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-300">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="dc1b5-301">Legen Sie den Wert auf `false` fest, um die mehrstufige Kompilierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-301">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="dc1b5-302">Weitere Informationen finden Sie unter [Mehrstufige Kompilierung](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-302">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="dc1b5-303">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="dc1b5-303">TieredCompilationQuickJit</span></span>

<span data-ttu-id="dc1b5-304">Mit der `TieredCompilationQuickJit`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-304">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="dc1b5-305">Legen Sie den Wert auf `false` fest, um Quick JIT zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-305">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="dc1b5-306">Weitere Informationen finden Sie unter [Quick JIT](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-306">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="dc1b5-307">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="dc1b5-307">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="dc1b5-308">Mit der `TieredCompilationQuickJitForLoops`-Eigenschaft wird konfiguriert, ob der JIT-Compiler Quick JIT für Methoden mit Schleifen verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-308">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="dc1b5-309">Legen Sie den Wert auf `true` fest, um Quick JIT für Methoden mit Schleifen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-309">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="dc1b5-310">Weitere Informationen finden Sie unter [Quick JIT für Schleifen](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-310">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="dc1b5-311">Referenz für Eigenschaften und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc1b5-311">Reference properties and items</span></span>

- [<span data-ttu-id="dc1b5-312">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="dc1b5-312">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="dc1b5-313">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="dc1b5-313">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="dc1b5-314">PackageReference</span><span class="sxs-lookup"><span data-stu-id="dc1b5-314">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="dc1b5-315">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="dc1b5-315">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="dc1b5-316">Verweis</span><span class="sxs-lookup"><span data-stu-id="dc1b5-316">Reference</span></span>](#reference)
- [<span data-ttu-id="dc1b5-317">Wiederherstellungsbezogene Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-317">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="dc1b5-318">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="dc1b5-318">AssetTargetFallback</span></span>

<span data-ttu-id="dc1b5-319">Mit der Eigenschaft `AssetTargetFallback` können Sie zusätzliche kompatible Frameworkversionen für Projektverweise und NuGet-Pakete angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-319">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="dc1b5-320">Wenn Sie z. B. mit `PackageReference` eine Paketabhängigkeit angeben, aber das entsprechende Paket keine Assets enthält, die mit dem `TargetFramework` Ihres Projekts kompatibel sind, kommt die Eigenschaft `AssetTargetFallback` ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-320">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="dc1b5-321">Die Kompatibilität des referenzierten Pakets wird erneut anhand jedes Zielframeworks überprüft, das in `AssetTargetFallback` angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-321">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="dc1b5-322">Sie können die Eigenschaft `AssetTargetFallback` auf eine oder mehrere [Zielframeworkversionen](../../standard/frameworks.md#supported-target-frameworks) festlegen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-322">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="dc1b5-323">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="dc1b5-323">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="dc1b5-324">Die Eigenschaft `DisableImplicitFrameworkReferences` steuert `FrameworkReference`-Elemente implizit, wenn .NET Core 3.0 oder höher als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-324">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="dc1b5-325">Wenn .NET Core 2.1 oder .NET Standard 2.0 oder niedriger als Ziel verwendet wird, steuert die Eigenschaft implizit [PackageReference](#packagereference)-Elemente für Pakete in einem Metapaket.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-325">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="dc1b5-326">Ein Metapaket ist ein frameworkbasiertes Paket, das nur aus Abhängigkeiten von anderen Paketen besteht. Diese Eigenschaft steuert ebenfalls implizite Verweise wie `System` und `System.Core`, wenn das .NET Framework als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-326">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="dc1b5-327">Legen Sie diese Eigenschaft auf `true` fest, um implizite `FrameworkReference`- oder [PackageReference](#packagereference)-Elemente zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-327">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="dc1b5-328">Wenn Sie diese Eigenschaft auf `true` festlegen, können Sie auf Framework- oder Paketebene je nach Bedarf explizite Verweise hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-328">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="dc1b5-329">PackageReference</span><span class="sxs-lookup"><span data-stu-id="dc1b5-329">PackageReference</span></span>

<span data-ttu-id="dc1b5-330">Das `PackageReference`-Element definiert einen Verweis auf ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-330">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="dc1b5-331">Das `Include`-Attribut gibt die Paket-ID an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-331">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="dc1b5-332">Das `Version`-Attribut gibt die Version oder den Versionsbereich an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-332">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="dc1b5-333">Informationen, wie Sie eine Mindestversion, Maximalversion, einen Versionsbereich oder eine exakte Versionsübereinstimmung angeben, finden Sie unter [Versionsbereiche](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-333">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="dc1b5-334">Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-334">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="dc1b5-335">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-335">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="dc1b5-336">Weitere Informationen finden Sie unter [Paketverweis in Projektdateien](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-336">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="dc1b5-337">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="dc1b5-337">ProjectReference</span></span>

<span data-ttu-id="dc1b5-338">Das `ProjectReference`-Element definiert einen Verweis auf ein anderes Projekt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-338">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="dc1b5-339">Das referenzierte Projekt wird als NuGet-Paketabhängigkeit hinzugefügt, d. h., es wird genauso wie eine `PackageReference` behandelt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-339">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="dc1b5-340">Das Attribut `Include` gibt den Pfad zu dem Projekt an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-340">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="dc1b5-341">Sie können auch die folgenden Metadaten zu einem Projektverweis hinzufügen: `IncludeAssets`, `ExcludeAssets` und `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-341">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="dc1b5-342">Der Codeausschnitt für die Projektdatei im folgenden Beispiel verweist auf ein Projekt namens `Project2`.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-342">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="dc1b5-343">Referenz</span><span class="sxs-lookup"><span data-stu-id="dc1b5-343">Reference</span></span>

<span data-ttu-id="dc1b5-344">Das `Reference`-Element definiert einen Verweis auf eine Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-344">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="dc1b5-345">Das `Include`-Attribut gibt den Namen der Datei an, und die `HintPath`-Metadaten geben den Pfad zu der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-345">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="dc1b5-346">Wiederherstellungsbezogene Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-346">Restore-related properties</span></span>

<span data-ttu-id="dc1b5-347">Durch das Wiederherstellen eines referenzierten Pakets werden alle seine direkten Abhängigkeiten sowie alle Abhängigkeiten dieser Abhängigkeiten installiert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-347">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="dc1b5-348">Sie können die Paketwiederherstellung anpassen, indem Sie Eigenschaften wie `RestorePackagesPath` und `RestoreIgnoreFailedSources` angeben.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-348">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="dc1b5-349">Weitere Informationen zu diesen und anderen Eigenschaften finden Sie unter [Wiederherstellungsziel](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-349">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="dc1b5-350">Ausführungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-350">Run properties</span></span>

<span data-ttu-id="dc1b5-351">Die folgenden Eigenschaften werden verwendet, um Apps mit dem Befehl [`dotnet run`](../tools/dotnet-run.md) zu starten:</span><span class="sxs-lookup"><span data-stu-id="dc1b5-351">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="dc1b5-352">RunArguments</span><span class="sxs-lookup"><span data-stu-id="dc1b5-352">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="dc1b5-353">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="dc1b5-353">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="dc1b5-354">RunArguments</span><span class="sxs-lookup"><span data-stu-id="dc1b5-354">RunArguments</span></span>

<span data-ttu-id="dc1b5-355">Die Eigenschaft `RunArguments` definiert die Argumente, die beim Ausführen an die App übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-355">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="dc1b5-356">Sie können zusätzliche Argumente angeben, die an die App übergeben werden sollen, indem Sie die Option [`--` für `dotnet run`](../tools/dotnet-run.md#options)verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-356">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="dc1b5-357">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="dc1b5-357">RunWorkingDirectory</span></span>

<span data-ttu-id="dc1b5-358">Die Eigenschaft `RunWorkingDirectory` definiert das Arbeitsverzeichnis für den Anwendungsprozess, in dem diese gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-358">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="dc1b5-359">Dies kann ein absoluter Pfad oder ein Pfad sein, der relativ zum Projektverzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-359">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="dc1b5-360">Wenn Sie kein Verzeichnis angeben, wird `OutDir` als Arbeitsverzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-360">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="dc1b5-361">Hostingeigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-361">Hosting properties</span></span>

- [<span data-ttu-id="dc1b5-362">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="dc1b5-362">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="dc1b5-363">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="dc1b5-363">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="dc1b5-364">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="dc1b5-364">EnableComHosting</span></span>

<span data-ttu-id="dc1b5-365">Die `EnableComHosting`-Eigenschaft gibt an, dass eine Assembly einen COM-Server bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-365">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="dc1b5-366">Wenn die `EnableComHosting`-Eigenschaft auf `true` festgelegt wird, bedeutet dies auch, dass [EnableDynamicLoading](#enabledynamicloading) `true` ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-366">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="dc1b5-367">Weitere Informationen finden Sie unter [Verfügbarmachen von .NET Core-Komponenten in COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-367">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="dc1b5-368">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="dc1b5-368">EnableDynamicLoading</span></span>

<span data-ttu-id="dc1b5-369">Die `EnableDynamicLoading`-Eigenschaft gibt an, dass eine Assembly eine dynamisch geladene Komponente ist.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-369">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="dc1b5-370">Die Komponente kann eine [COM-Bibliothek](/windows/win32/com/the-component-object-model) oder eine Nicht-COM-Bibliothek sein, die [von einem nativen Host verwendet werden kann](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="dc1b5-370">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="dc1b5-371">Wenn diese Eigenschaft auf `true` festgelegt wird, hat diese die folgenden Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="dc1b5-371">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="dc1b5-372">Eine *.runtimeconfig.json*-Datei wird generiert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-372">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="dc1b5-373">[Rollforward ausführen](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) wird auf `LatestMinor` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-373">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="dc1b5-374">NuGet-Verweise werden lokal kopiert.</span><span class="sxs-lookup"><span data-stu-id="dc1b5-374">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="dc1b5-375">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc1b5-375">See also</span></span>

- [<span data-ttu-id="dc1b5-376">MSBuild-Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="dc1b5-376">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="dc1b5-377">Gemeinsame MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc1b5-377">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="dc1b5-378">MSBuild-Eigenschaften für NuGet-Ziel „pack“</span><span class="sxs-lookup"><span data-stu-id="dc1b5-378">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="dc1b5-379">MSBuild-Eigenschaften für NuGet-Ziel „restore“</span><span class="sxs-lookup"><span data-stu-id="dc1b5-379">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="dc1b5-380">Anpassen eines Builds</span><span class="sxs-lookup"><span data-stu-id="dc1b5-380">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
