---
title: Vergleich von project.json und csproj
description: Informationen zur Zuordnung zwischen project.json und csproj-Elementen.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: feaa7e9cde7e1aa4dfe94d699b14a018fc728f27
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794623"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a>Die Zuordnung zwischen project.json und csproj-Eigenschaften

Von [Nate McMaster](https://github.com/natemcmaster)

Bei der Entwicklung von .NET Core-Tools wurde eine wichtige Änderung durchgeführt. *project.json*-Dateien werden nicht länger unterstützt und die .NET Core-Projekte stattdessen in das Format MSBuild/Csproj verschoben.

Dieser Artikel zeigt, wie die Einstellungen in *project.json* im MSBuild/Csproj-Format dargestellt sind, damit Sie das neue Format verwenden können und die Änderungen durch die Migrationstools kennen, wenn Sie Ihr Projekt auf die neueste Version der Tools aktualisieren.

## <a name="the-csproj-format"></a>Das Csproj-Format

Das neue Format \*.csproj, ist ein XML-basiertes Format. Im folgenden Beispiel wird der Stammknoten eines .NET Core-Projekts mit `Microsoft.NET.Sdk` gezeigt. Für Webprojekte ist das verwendete SDK `Microsoft.NET.Sdk.Web`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a>Allgemeine Eigenschaften der obersten Ebene

### <a name="name"></a>Name

```json
{
  "name": "MyProjectName"
}
```

Wird nicht mehr unterstützt. In csproj wird dies durch den Dateinamen des Projekts festgelegt, der in der Regel mit dem Namen des Verzeichnisses übereinstimmt. Beispiel: `MyProjectName.csproj`.

Standardmäßig gibt der Dateiname des Projekts auch den Wert der `<AssemblyName>`- und `<PackageId>`- Eigenschaften an.

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

`<AssemblyName>` wird einen anderen Wert als `<PackageId>` haben, wenn die Eigenschaft `buildOptions\outputName` in project.json definiert wurde.
Weitere Informationen finden Sie unter [Andere gängige Buildoptionen](#other-common-build-options).

### <a name="version"></a>Version

```json
{
  "version": "1.0.0-alpha-*"
}
```

Verwenden Sie die `VersionPrefix`- und `VersionSuffix`-Eigenschaften:

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

Sie können auch die `Version`-Eigenschaft verwenden, aber dies kann beim Packen Versionseinstellungen überschreiben:

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a>Andere allgemeinen Optionen auf der Stammebene

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

## <a name="frameworks"></a>frameworks

### <a name="one-target-framework"></a>Ein Zielframework

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

### <a name="multiple-target-frameworks"></a>Mehrere Zielframeworks

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

Verwenden Sie die `TargetFrameworks`-Eigenschaft, um Ihre Liste der Zielframeworks zu definieren. Verwenden Sie Semikolons, um mehrere Frameworkwerte zu trennen.

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a>Abhängigkeiten

> [!IMPORTANT]
> Wenn die Abhängigkeit ein **Projekt** und kein Paket ist, ist das Format anders.
> Weitere Informationen finden Sie im Abschnitt [Abhängigkeitstyp](#dependency-type).

### <a name="netstandardlibrary-metapackage"></a>NETStandard.Library-Metapaket

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

### <a name="microsoftnetcoreapp-metapackage"></a>Microsoft.NETCore.App-Metapaket

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

Beachten Sie, dass sich der `<RuntimeFrameworkVersion>`-Wert im migrierten Projekt nach der Version des SDK richtet, das Sie installiert haben.

### <a name="top-level-dependencies"></a>Abhängigkeiten der obersten Ebene

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

### <a name="per-framework-dependencies"></a>Abhängigkeiten nach Framework

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

### <a name="imports"></a>Importe

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

### <a name="dependency-type"></a>Abhängigkeitstyp

#### <a name="type-project"></a>Typ: Projekt

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
> Dies wird die Art unterbrechen, in der `dotnet pack --version-suffix $suffix` die Abhängigkeitsversion eines Projektverweises bestimmt.

#### <a name="type-build"></a>Typ: Build

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

#### <a name="type-platform"></a>Typ: Plattform

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

Es gibt keine Entsprechung in csproj.

## <a name="runtimes"></a>runtimes

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

### <a name="standalone-apps-self-contained-deployment"></a>Eigenständige Anwendungen (eigenständige Bereitstellung)

In Project.json bedeutet das Definieren eines `runtimes`-Abschnitts, dass die Anwendung während der Erstellung und Veröffentlichung eigenständig war.
Alle Projekte in MSBuild sind während des Buildvorgangs *tragbar*, werden jedoch eigenständig veröffentlicht.

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

Weitere Informationen finden Sie unter [Eigenständige Bereitstellungen (SCD)](../deploying/index.md#publish-self-contained).

## <a name="tools"></a>Tools

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
> `imports` auf Tools werden nicht in csproj unterstützt. Tools, die Importe benötigen, funktionieren nicht mit dem neuen `Microsoft.NET.Sdk`.

## <a name="buildoptions"></a>buildOptions

Siehe auch [Dateien](#files).

### <a name="emitentrypoint"></a>emitEntryPoint

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

Wenn `emitEntryPoint``false` betrug, wird der Wert von `OutputType` zu `Library` konvertiert, der der folgende Standardwert ist:

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

### <a name="keyfile"></a>keyFile

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

Das `keyFile`-Element wird auf drei Eigenschaften in MSBuild erweitert:

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a>Andere allgemeine Buildoptionen

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

## <a name="packoptions"></a>packOptions

Siehe auch [Dateien](#files).

### <a name="common-pack-options"></a>Allgemeine Paketoptionen

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

Es gibt keine Entsprechung für das `owners`-Element in MSBuild.
Für `summary` können Sie die `<Description>`-Eigenschaft von MSBuild verwenden, obwohl der Wert der `summary` nicht automatisch zur Eigenschaft migriert wird, da die Eigenschaft dem [`description`](#other-common-root-level-options)-Element zugeordnet ist.

## <a name="scripts"></a>Skripts

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

Ihre Entsprechungen in MSBuild sind [Ziele](/visualstudio/msbuild/msbuild-targets):

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a>runtimeOptions

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

Alle Einstellungen in dieser Gruppe, außer für die Eigenschaft „System.GC.Server“ befinden sich in einer Datei namens *runtimeconfig.template.json* im Projektordner mit den Optionen, die während der Migration auf das Stammobjekt transformiert werden:

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

Die Eigenschaft „System.GC.Server“ ist in die csproj-Datei migriert:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

Allerdings können Sie alle diese Werte in der csproj sowie den MSBuild-Eigenschaften festlegen:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a>Freigegeben

```json
{
  "shared": "shared/**/*.cs"
}
```

Wird nicht in csproj unterstützt. Stattdessen müssen Sie Dateien zum Einschließen von Inhalten in Ihrer *.nuspec*-Datei erstellen.
Weitere Informationen finden Sie unter [Inhaltsdateien einschließen](/nuget/schema/nuspec#including-content-files).

## <a name="files"></a>Dateien

In *project.json* könnten Build und das Paket erweitert werden, um aus unterschiedlichen Ordnern zu kompilieren und einzubetten.
In MSBuild wird dies unter Verwendung von [Elementen](/visualstudio/msbuild/common-msbuild-project-items) erledigt. Im folgenden Beispiel sehen Sie eine allgemeine Konversion:

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
> Viele der [Standardglobmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden automatisch durch das .NET Core SDK hinzugefügt.
> Weitere Informationen finden Sie unter [Werte für Standardkompilierungselemente](https://aka.ms/sdkimplicititems).

Alle `ItemGroup`-Elemente von MSBuild unterstützen `Include`, `Exclude` und `Remove`.

Paketlayout in der .nupkg kann mit `PackagePath="path"` geändert werden.

Mit Ausnahme von `Content` erfordern die meisten Artikelgruppen das explizite Hinzufügen von `Pack="true"` in das Paket. `Content` wird in den Ordner *Inhalt* in einem Paket versetzt werden, da die `<IncludeContentInPack>`-Eigenschaft von MSBuild standardmäßig auf `true` festgelegt ist.
Weitere Informationen finden Sie unter [Inhalt in ein Paket einschließen](/nuget/schema/msbuild-targets#including-content-in-a-package).

`PackagePath="%(Identity)"` ist eine mühelose Möglichkeit, mit der ein Paketpfad auf den projektspezifischen Dateipfad festgelegt werden kann.

## <a name="testrunner"></a>testRunner

### <a name="xunit"></a>xUnit

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

### <a name="mstest"></a>MSTest

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

## <a name="see-also"></a>Weitere Informationen

- [Allgemeine Übersicht über Änderungen in CLI](cli-msbuild-architecture.md)
