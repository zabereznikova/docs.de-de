---
title: Dotnet-Test-Befehl | .NET Core SDK
description: "Der Befehl „dotnet-Test“ wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet."
keywords: Dotnet-Test, CLI, CLI-Befehl, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 66c9f949980612f6e21b6d441c004cc09f4eb7d3

---

#<a name="dotnet-test"></a>Dotnet-Test

## <a name="name"></a>Name

`dotnet-test` – .NET-Testtreiber

## <a name="synopsis"></a>Übersicht

`dotnet test [project] [--help] 
    [--settings] [--listTests] [--testCaseFilter] 
    [--testAdapterPath] [--logger] 
    [--configuration] [--output] [--framework] [--diag]
    [--noBuild]`  

## <a name="description"></a>Beschreibung

Der Befehl `dotnet test` wird zum Ausführen von Komponententests in einem bestimmten Projekt verwendet. Komponententests sind Klassenbibliotheksprojekte, die Abhängigkeiten vom Komponententest-Framework (z.B. NUnit oder xUnit) und dotnet-Test-Runner für dieses Komponententestframework aufweisen. Sie werden als NuGet-Pakete verpackt und als gewöhnliche Abhängigkeiten für das Projekt wiederhergestellt.

Testprojekte müssen auch den Test Runner angeben. Dieser wird mit einem normalen `<PackageReference>`-Element angegeben, wie in der folgenden Beispielprojektdatei gezeigt:

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Test.Sdk">
      <Version>15.0.0-preview-20161024-02</Version>
    </PackageReference>
    <PackageReference Include="xunit">
      <Version>2.2.0-beta3-build3402</Version>
    </PackageReference>
    <PackageReference Include="xunit.runner.visualstudio">
      <Version>2.2.0-beta4-build1188</Version>
    </PackageReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="options"></a>Optionen

`[project]`
    
Gibt den Pfad des Testprojekts an. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis angegeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s | --settings <SETTINGS_FILE>`

Einstellungen, die beim Ausführen von Tests verwendet werden. 

`-lt | --listTests`

Listen Sie alle ermittelten Tests im aktuellen Projekt auf. 

`-tcf | --testCaseFilter <EXPRESSION>`

Filtern Sie Tests im aktuellen Projekt mithilfe des angegebenen Ausdrucks. 

`-tap | --testAdapterPath <TEST_ADAPTER_PATH>`

Verwenden Sie die benutzerdefinierten Testadapter aus dem angegebenen Pfad in diesem Testlauf. 

`--logger <LOGGER>`

Geben Sie eine Protokollierung für die Testergebnisse an. 

`-c|--configuration <Debug|Release>`

Konfiguration für die Erstellung. Der Standardwert ist `Release`. 

`-o|--output [OUTPUT_DIRECTORY]`

Verzeichnis, in dem die auszuführenden Binärdateien zu finden sind.

`-f|--framework [FRAMEWORK]`

Sucht nach Testbinärdateien für ein bestimmtes Framework.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Suchen Sie nach den Testbinärdateien für die angegebene Laufzeit.

`--noBuild` 

Erstellt das Testprojekt nicht vor der Ausführung. 

`-d | --diag <DIAGNOSTICS_FILE>`

Aktivieren Sie den Diagnosemodus für die Testplattform, und schreiben Sie Diagnosemeldungen in die angegebene Datei. 

## <a name="examples"></a>Beispiele

Führen Sie die Tests im Projekt im aktuellen Verzeichnis durch:

`dotnet test` 

Führen Sie die Tests im Projekt test1 durch:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>Siehe auch

[Frameworks](../../../standard/frameworks.md)

[Runtime-ID-Katalog (RID)](../../rid-catalog.md)



<!--HONumber=Nov16_HO3-->


