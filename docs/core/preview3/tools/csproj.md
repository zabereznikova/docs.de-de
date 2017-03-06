---
title: CSPROJ-Referenz | Microsoft-Dokumentation
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 0402707f98af8b716b041ba1260162cd227918cc
ms.openlocfilehash: 98f6ced2a199bdbe2f91f46e48ffd3ac52438cf8

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Erweiterungen des CSPROJ-Formats für .NET Core

[!INCLUDE[preview-warning](../../../includes/warning.md)]

In diesem Dokument werden die Änderungen erläutert, die zu CSPROJ-Dateien beim Wechsel von `project.json` zu `csproj` und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden. Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="additions"></a>Erweiterungen

* PackageReference-Element, das eine NuGet-Abhängigkeit im Projekt angibt. Das `Include`-Attribut gibt die Paket-ID an. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

## <a name="version"></a>Version
`Version` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

## <a name="includeassets"></a>IncludeAssets
Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen. 

Das Attribut kann einen oder mehrere der folgenden Werte enthalten:

* `Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* `Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden
* `ContentFiles`: Gibt an, dass die Inhalte des Ordners „contentfiles“ verwendet werden
* `Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* `Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Attribut Folgendes enthalten:

* `None`: Keines der Objekte wird verwendet.
* `All`: Alle Objekte werden verwendet.

## <a name="excludeassets"></a>ExcludeAssets
Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.

Das Attribut kann einen oder mehrere der folgenden Werte enthalten:

* `Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* `Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden
* `ContentFiles`: Gibt an, dass die Inhalte des Ordners „contentfiles“ verwendet werden
* `Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* `Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Element Folgendes enthalten:

* `None`: Keines der Objekte wird verwendet.
* `All`: Alle Objekte werden verwendet.

## <a name="privateassets"></a>PrivateAssets
Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen. 

> [!NOTE]
> Dies ist eine neue Bezeichnung für das `SuppressParent`-Element von project.json/xproj. 

Das Attribut kann einen oder mehrere der folgenden Werte enthalten:

* `Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* `Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden
* `ContentFiles`: Gibt an, dass die Inhalte des Ordners „contentfiles“ verwendet werden
* `Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* `Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Attribut Folgendes enthalten:

* `None`: Keines der Objekte wird verwendet.
* `All`: Alle Objekte werden verwendet.

* Das DotnetCliToolReference `<DotnetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte. Es ist ein Ersatz für den `tools`-Knoten in `project.json`. 

```xml
<DotnetCliToolReference Include="<package-id>" Version="" />
```

## <a name="version"></a>Version
`Version` gibt die Version des wiederherzustellenden Pakets an. Für das Attribut werden die Regeln für das NuGet-Versionsschema berücksichtigt.

* RuntimeIdentifiers Das `<RuntimeIdentifiers>`-Element ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../../rid-catalog.md) für das Projekt. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


* RuntimeIdentifier Das `<RuntieIdentifier>`-Element ermöglicht die Angabe nur einer einzigen [Runtime-ID (RID)](../../rid-catalog.md) für das Projekt. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


* PackageTargetFallback Das `<PackageTargetFallback>`-Element ermöglicht die Angabe eines Satzes von kompatiblen Zielen, die verwendet werden sollen, wenn Pakete wiederhergestellt werden. Es soll ermöglichen, dass Pakete, in denen das .NET TxM verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist. Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sein können. 

Im folgenden Beispiel werden die Fallbacks für alle Ziele in Ihrem Projekt bereitgestellt: 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

Im folgenden Beispiel werden nur die Fallbacks für das `netcoreapp1.0`-Ziel angegeben:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>NuGet-Metadateneigenschaften
Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Paket verwendet werden, aus project.json- in csproj-Dateien verschoben. Die Eingaben sind MSBuild-Eigenschaften. In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDKs ist. 

* IsPackable
* PackageVersion
* PackageId
* Titel
* Authors
* Beschreibung
* Copyright
* PackageRequireLicenseAcceptance
* PackageLicenseUrl
* PackageProjectUrl
* PackageIconUrl
* PackageReleaseNotes
* PackageTags
* PackageOutputPath
* IncludeSymbols
* IncludeSource
* PackageTypes
* IsTool
* RepositoryUrl
* RepositoryType
* NoPackageAnalysis
* MinClientVersion
* IncludeBuildOutput
* IncludeContentInPack
* BuildOutputTargetFolder
* ContentTargetFolders
* NuspecFile
* NuspecBasePath
* NuspecProperties


<!--HONumber=Feb17_HO2-->


