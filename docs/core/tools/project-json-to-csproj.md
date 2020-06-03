---
title: Vergleich von project.json und csproj
description: Informationen zur Zuordnung zwischen project.json und csproj-Elementen.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: a997b48f645ed58d15610a68aee7c67411f9763f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205833"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="72d07-103">Die Zuordnung zwischen project.json und csproj-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="72d07-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="72d07-104">Von [Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="72d07-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="72d07-105">Bei der Entwicklung von .NET Core-Tools wurde eine wichtige Änderung durchgeführt. *project.json*-Dateien werden nicht länger unterstützt und die .NET Core-Projekte stattdessen in das Format MSBuild/Csproj verschoben.</span><span class="sxs-lookup"><span data-stu-id="72d07-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="72d07-106">Dieser Artikel zeigt, wie die Einstellungen in *project.json* im MSBuild/Csproj-Format dargestellt sind, damit Sie das neue Format verwenden können und die Änderungen durch die Migrationstools kennen, wenn Sie Ihr Projekt auf die neueste Version der Tools aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="72d07-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span>

## <a name="the-csproj-format"></a><span data-ttu-id="72d07-107">Das Csproj-Format</span><span class="sxs-lookup"><span data-stu-id="72d07-107">The csproj format</span></span>

<span data-ttu-id="72d07-108">Das neue Format \*.csproj, ist ein XML-basiertes Format.</span><span class="sxs-lookup"><span data-stu-id="72d07-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="72d07-109">Im folgenden Beispiel wird der Stammknoten eines .NET Core-Projekts mit `Microsoft.NET.Sdk` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="72d07-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="72d07-110">Für Webprojekte ist das verwendete SDK `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="72d07-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="72d07-111">Allgemeine Eigenschaften der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="72d07-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="72d07-112">Name</span><span class="sxs-lookup"><span data-stu-id="72d07-112">name</span></span>

```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="72d07-113">Wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72d07-113">No longer supported.</span></span> <span data-ttu-id="72d07-114">In csproj wird dies durch den Dateinamen des Projekts festgelegt, der in der Regel mit dem Namen des Verzeichnisses übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="72d07-114">In csproj, this is determined by the project filename, which usually matches the directory name.</span></span> <span data-ttu-id="72d07-115">Beispielsweise `MyProjectName.csproj`.</span><span class="sxs-lookup"><span data-stu-id="72d07-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="72d07-116">Standardmäßig gibt der Dateiname des Projekts auch den Wert der `<AssemblyName>`- und `<PackageId>`- Eigenschaften an.</span><span class="sxs-lookup"><span data-stu-id="72d07-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span>

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="72d07-117">`<AssemblyName>` wird einen anderen Wert als `<PackageId>` haben, wenn die Eigenschaft `buildOptions\outputName` in project.json definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="72d07-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span>
<span data-ttu-id="72d07-118">Weitere Informationen finden Sie unter [Andere gängige Buildoptionen](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="72d07-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="72d07-119">Version</span><span class="sxs-lookup"><span data-stu-id="72d07-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```

<span data-ttu-id="72d07-120">Verwenden Sie die `VersionPrefix`- und `VersionSuffix`-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="72d07-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="72d07-121">Sie können auch die `Version`-Eigenschaft verwenden, aber dies kann beim Packen Versionseinstellungen überschreiben:</span><span class="sxs-lookup"><span data-stu-id="72d07-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="72d07-122">Andere allgemeinen Optionen auf der Stammebene</span><span class="sxs-lookup"><span data-stu-id="72d07-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="72d07-123">frameworks</span><span class="sxs-lookup"><span data-stu-id="72d07-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="72d07-124">Ein Zielframework</span><span class="sxs-lookup"><span data-stu-id="72d07-124">One target framework</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="72d07-125">Mehrere Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="72d07-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="72d07-126">Verwenden Sie die `TargetFrameworks`-Eigenschaft, um Ihre Liste der Zielframeworks zu definieren.</span><span class="sxs-lookup"><span data-stu-id="72d07-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="72d07-127">Verwenden Sie Semikolons, um mehrere Frameworkwerte zu trennen.</span><span class="sxs-lookup"><span data-stu-id="72d07-127">Use semi-colon to separate multiple framework values.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="72d07-128">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="72d07-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72d07-129">Wenn die Abhängigkeit ein **Projekt** und kein Paket ist, ist das Format anders.</span><span class="sxs-lookup"><span data-stu-id="72d07-129">If the dependency is a **project** and not a package, the format is different.</span></span>
> <span data-ttu-id="72d07-130">Weitere Informationen finden Sie im Abschnitt [Abhängigkeitstyp](#dependency-type).</span><span class="sxs-lookup"><span data-stu-id="72d07-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="72d07-131">NETStandard.Library-Metapaket</span><span class="sxs-lookup"><span data-stu-id="72d07-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="72d07-132">Microsoft.NETCore.App-Metapaket</span><span class="sxs-lookup"><span data-stu-id="72d07-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="72d07-133">Der `<RuntimeFrameworkVersion>`-Wert im migrierten Projekt richtet sich nach der installierten SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="72d07-133">The `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of SDK that's installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="72d07-134">Abhängigkeiten der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="72d07-134">Top-level dependencies</span></span>

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="72d07-135">Abhängigkeiten nach Framework</span><span class="sxs-lookup"><span data-stu-id="72d07-135">Per-framework dependencies</span></span>

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="72d07-136">Importe</span><span class="sxs-lookup"><span data-stu-id="72d07-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="72d07-137">Abhängigkeitstyp</span><span class="sxs-lookup"><span data-stu-id="72d07-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="72d07-138">Typ: Projekt</span><span class="sxs-lookup"><span data-stu-id="72d07-138">type: project</span></span>

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="72d07-139">Dies wird die Art unterbrechen, in der `dotnet pack --version-suffix $suffix` die Abhängigkeitsversion eines Projektverweises bestimmt.</span><span class="sxs-lookup"><span data-stu-id="72d07-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>

#### <a name="type-build"></a><span data-ttu-id="72d07-140">Typ: Build</span><span class="sxs-lookup"><span data-stu-id="72d07-140">type: build</span></span>

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="72d07-141">Typ: Plattform</span><span class="sxs-lookup"><span data-stu-id="72d07-141">type: platform</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="72d07-142">Es gibt keine Entsprechung in csproj.</span><span class="sxs-lookup"><span data-stu-id="72d07-142">There is no equivalent in csproj.</span></span>

## <a name="runtimes"></a><span data-ttu-id="72d07-143">runtimes</span><span class="sxs-lookup"><span data-stu-id="72d07-143">runtimes</span></span>

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="72d07-144">Eigenständige Anwendungen (eigenständige Bereitstellung)</span><span class="sxs-lookup"><span data-stu-id="72d07-144">Standalone apps (self-contained deployment)</span></span>

<span data-ttu-id="72d07-145">In Project.json bedeutet das Definieren eines `runtimes`-Abschnitts, dass die Anwendung während der Erstellung und Veröffentlichung eigenständig war.</span><span class="sxs-lookup"><span data-stu-id="72d07-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="72d07-146">Alle Projekte in MSBuild sind während des Buildvorgangs *tragbar*, werden jedoch eigenständig veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="72d07-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="72d07-147">Weitere Informationen finden Sie unter [Eigenständige Bereitstellungen (SCD)](../deploying/index.md#publish-self-contained).</span><span class="sxs-lookup"><span data-stu-id="72d07-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#publish-self-contained).</span></span>

## <a name="tools"></a><span data-ttu-id="72d07-148">Tools</span><span class="sxs-lookup"><span data-stu-id="72d07-148">tools</span></span>

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="72d07-149">`imports` auf Tools werden nicht in csproj unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72d07-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="72d07-150">Tools, die Importe benötigen, funktionieren nicht mit dem neuen `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="72d07-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="72d07-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="72d07-151">buildOptions</span></span>

<span data-ttu-id="72d07-152">Siehe auch [Dateien](#files).</span><span class="sxs-lookup"><span data-stu-id="72d07-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="72d07-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="72d07-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="72d07-154">Wenn `emitEntryPoint``false` betrug, wird der Wert von `OutputType` zu `Library` konvertiert, der der folgende Standardwert ist:</span><span class="sxs-lookup"><span data-stu-id="72d07-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="72d07-155">keyFile</span><span class="sxs-lookup"><span data-stu-id="72d07-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="72d07-156">Das `keyFile`-Element wird auf drei Eigenschaften in MSBuild erweitert:</span><span class="sxs-lookup"><span data-stu-id="72d07-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="72d07-157">Andere allgemeine Buildoptionen</span><span class="sxs-lookup"><span data-stu-id="72d07-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="72d07-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="72d07-158">packOptions</span></span>

<span data-ttu-id="72d07-159">Siehe auch [Dateien](#files).</span><span class="sxs-lookup"><span data-stu-id="72d07-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="72d07-160">Allgemeine Paketoptionen</span><span class="sxs-lookup"><span data-stu-id="72d07-160">Common pack options</span></span>

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="72d07-161">Es gibt keine Entsprechung für das `owners`-Element in MSBuild.</span><span class="sxs-lookup"><span data-stu-id="72d07-161">There is no equivalent for the `owners` element in MSBuild.</span></span> <span data-ttu-id="72d07-162">Für `summary` können Sie die MSBuild-Eigenschaft `<Description>` verwenden.</span><span class="sxs-lookup"><span data-stu-id="72d07-162">For `summary`, you can use the MSBuild `<Description>` property.</span></span> <span data-ttu-id="72d07-163">Der Wert von `summary` wird nicht automatisch zu dieser Eigenschaft migriert, da die Eigenschaft dem [`description`](#other-common-root-level-options)-Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="72d07-163">The value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="72d07-164">Skripts</span><span class="sxs-lookup"><span data-stu-id="72d07-164">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="72d07-165">Ihre Entsprechungen in MSBuild sind [Ziele](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="72d07-165">Their equivalents in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a><span data-ttu-id="72d07-166">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="72d07-166">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="72d07-167">Alle Einstellungen in dieser Gruppe, außer für die Eigenschaft `System.GC.Server`, befinden sich in einer Datei namens *runtimeconfig.template.json* im Projektordner mit den Optionen, die während der Migration auf das Stammobjekt transformiert werden:</span><span class="sxs-lookup"><span data-stu-id="72d07-167">All settings in this group, except for the `System.GC.Server` property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="72d07-168">Die Eigenschaft `System.GC.Server` wird in die CSPROJ-Datei migriert:</span><span class="sxs-lookup"><span data-stu-id="72d07-168">The `System.GC.Server` property is migrated into the csproj file:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="72d07-169">Allerdings können Sie alle diese Werte in der csproj sowie den MSBuild-Eigenschaften festlegen:</span><span class="sxs-lookup"><span data-stu-id="72d07-169">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="72d07-170">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="72d07-170">shared</span></span>

```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="72d07-171">Wird nicht in csproj unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72d07-171">Not supported in csproj.</span></span> <span data-ttu-id="72d07-172">Erstellen Sie stattdessen Include-Inhaltsdateien in Ihrer *.nuspec*-Datei.</span><span class="sxs-lookup"><span data-stu-id="72d07-172">Instead, create include content files in your *.nuspec* file.</span></span>
<span data-ttu-id="72d07-173">Weitere Informationen finden Sie unter [Inhaltsdateien einschließen](/nuget/schema/nuspec#including-content-files).</span><span class="sxs-lookup"><span data-stu-id="72d07-173">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="72d07-174">Dateien</span><span class="sxs-lookup"><span data-stu-id="72d07-174">files</span></span>

<span data-ttu-id="72d07-175">In *project.json* könnten Build und das Paket erweitert werden, um aus unterschiedlichen Ordnern zu kompilieren und einzubetten.</span><span class="sxs-lookup"><span data-stu-id="72d07-175">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="72d07-176">In MSBuild wird dies unter Verwendung von [Elementen](/visualstudio/msbuild/common-msbuild-project-items) erledigt.</span><span class="sxs-lookup"><span data-stu-id="72d07-176">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="72d07-177">Im folgenden Beispiel sehen Sie eine allgemeine Konversion:</span><span class="sxs-lookup"><span data-stu-id="72d07-177">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="72d07-178">Viele der [Standardglobmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden automatisch durch das .NET Core SDK hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="72d07-178">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span> <span data-ttu-id="72d07-179">Weitere Informationen finden Sie unter [Standardmäßige Includedateien für die Kompilierung](../project-sdk/overview.md#default-compilation-includes).</span><span class="sxs-lookup"><span data-stu-id="72d07-179">For more information, see [Default compilation includes](../project-sdk/overview.md#default-compilation-includes).</span></span>

<span data-ttu-id="72d07-180">Alle `ItemGroup`-Elemente von MSBuild unterstützen `Include`, `Exclude` und `Remove`.</span><span class="sxs-lookup"><span data-stu-id="72d07-180">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="72d07-181">Paketlayout in der .nupkg kann mit `PackagePath="path"` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="72d07-181">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="72d07-182">Mit Ausnahme von `Content` erfordern die meisten Artikelgruppen das explizite Hinzufügen von `Pack="true"` in das Paket.</span><span class="sxs-lookup"><span data-stu-id="72d07-182">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="72d07-183">`Content` wird in den Ordner *Inhalt* in einem Paket versetzt werden, da die `<IncludeContentInPack>`-Eigenschaft von MSBuild standardmäßig auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="72d07-183">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span>
<span data-ttu-id="72d07-184">Weitere Informationen finden Sie unter [Inhalt in ein Paket einschließen](/nuget/schema/msbuild-targets#including-content-in-a-package).</span><span class="sxs-lookup"><span data-stu-id="72d07-184">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="72d07-185">`PackagePath="%(Identity)"` ist eine mühelose Möglichkeit, mit der ein Paketpfad auf den projektspezifischen Dateipfad festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="72d07-185">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="72d07-186">testRunner</span><span class="sxs-lookup"><span data-stu-id="72d07-186">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="72d07-187">xUnit</span><span class="sxs-lookup"><span data-stu-id="72d07-187">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="72d07-188">MSTest</span><span class="sxs-lookup"><span data-stu-id="72d07-188">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="72d07-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72d07-189">See also</span></span>

- [<span data-ttu-id="72d07-190">Allgemeine Übersicht über Änderungen in CLI</span><span class="sxs-lookup"><span data-stu-id="72d07-190">High-level overview of changes in CLI</span></span>](cli-msbuild-architecture.md)
