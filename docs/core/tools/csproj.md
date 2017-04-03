---
title: CSPROJ-Referenz | Microsoft-Dokumentation
description: "Erfahren Sie mehr über die Unterschiede zwischen vorhandenen CSPROJ-Dateien und CSPROJ-Dateien von .NET Core"
keywords: Referenz, CSPROJ, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/03/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e67270cf713857a5fea16ebdd0abab774f555808
ms.lasthandoff: 03/07/2017

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Erweiterungen des CSPROJ-Formats für .NET Core

In diesem Dokument werden die Änderungen erläutert, die an die Projektdateien beim Wechsel von *project.json* auf *csproj* und [MSBuild](https://github.com/Microsoft/MSBuild) hinzugefügt wurden. Weitere Informationen über die allgemeine Projektdateisyntax und eine Referenz finden Sie in der Dokumentation zur [MSBuild-Projektdatei](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="implicit-package-references"></a>Implizite Paketverweise
Es wird jetzt implizit auf Metapakete verwiesen, basierend auf der Grundlage des Zielframeworks, das in der `<TargetFramework>`- oder `<TargetFrameworks>`-Eigenschaft Ihrer Projektdatei angegeben wurde. Wenn das Zielframework `netcoreap1.x` ist, wird auf die richtige Version des `Microsoft.NETCore.App`-Metapakets verwiesen. Wenn das Zielframework jedoch `netstandard1.x` ist, wird auf die richtige Version des `NetStandard.Library`-Metapakets verwiesen.

Hinsichtlich des restlichen Verhaltens arbeiten die Tools wie erwartet, und die meisten Gesten werden gleich bleiben (z.B. `dotnet restore`). 

### <a name="recommendations"></a>Empfehlungen
Da jetzt implizit auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete verwiesen wird, sehen Sie im Folgenden unsere empfohlenen bewährten Methoden:

* Sie dürfen nie über einen expliziten Verweis auf die `Microsoft.NETCore.App`- oder `NetStandard.Library`-Metapakete über die `<PackageReference>`-Eigenschaft in Ihrer Projektdatei verfügen.
* Wenn Sie eine bestimmte Version der Laufzeit benötigen, sollten Sie die `<RuntimeFrameworkVersion>`-Eigenschaft in Ihrem Projekt (z.B. `1.0.4`) verwenden, anstatt auf Metapakete zu verweisen.
    * Dies kann vorkommen, wenn Sie [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) verwenden und Sie z.B. eine bestimmte Patchversion der 1.0.0 LTS-Laufzeit benötigen.
* Sollten Sie eine bestimmte Version der `NetStandard.Library`-Metapakete benötigen, können Sie die `<NetStandardImplicitPackageVersion>`-Eigenschaft verwenden und die Version festlegen, die Sie benötigen. 

## <a name="default-compilation-includes-in-net-core-projects"></a>Standardkompilierung in .NET Core-Projekten
Beim Wechsel zum *csproj*-Format in den neuesten SDK-Versionen, haben wir die Standardaufnahmen- und ausschlüsse für Compile-Elemente und eingebettete Ressourcen zu den SDK-Eigenschaftendateien verschoben. Dies bedeutet, dass Sie diese Elemente nicht länger in Ihrer Projektdatei angeben müssen. 

Der Hauptgrund dafür ist die Übersichtlichkeit für Ihre Projektdatei. Die Standardeinstellungen im SDK sollten die gängigen Anwendungsbeispiele abdecken. Es besteht keine Notwendigkeit, sie in jedem Projekt zu wiederholen, das Sie erstellen. Dies führt zu kleineren Projektdateien, die viel einfacher zu verstehen und bei Bedarf auch manuell zu bearbeiten sind. 

Die folgende Tabelle zeigt, welche Elemente und welche Globs im SDK enthalten und ausgeschlossen sind: 

| Element              | Glob einschließen                               | Glob ausschließen                                                     | Glob entfernen                  |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Compile              | \*\*/\*.cs (oder andere Spracherweiterungen) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc     | Nicht zutreffend                          |
| EmbeddedResource     | \*\*/\*.resx                                 | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | Nicht zutreffend                          |
| Keine                 | \*\*/\*                                      | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | - \*\*/\*.cs; \*\*/\*.resx |

Wenn Sie über Globs in Ihrem Projekt verfügen, und Sie versuchen, es mit dem neuesten SDK zu erstellen, erhalten Sie den folgenden Fehler:

> Doppelte Compile-Elemente waren enthalten. .NET SDK enthält Compile-Elemente aus Ihrem Projektverzeichnis in der Standardeinstellung. Sie können diese Elemente aus Ihrer Projektdatei entfernen oder die Eigenschaft „EnableDefaultCompileItems“ auf „FALSE“ festlegen, wenn Sie sie explizit in Ihrer Projektdatei einfügen möchten. 

Um diesen Fehler zu umgehen, können Sie entweder die expliziten `Compile`-Elemente entfernen, die mit denen übereinstimmen, die in der vorherigen Tabelle aufgeführt sind, oder Sie können die `<EnableDefaultCompileItems>`-Eigenschaft auf `false` wie folgt festlegen:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
Wenn diese Eigenschaft auf `false` festgelegt wird, wird die implizite Aufnahme überschrieben, und das Verhalten wird wieder auf die früheren SDKs gesetzt, als Sie die Standardglobs in Ihrem Projekt angeben mussten. 

Diese Änderung ändert die Hauptfunktionsweise anderer Aufnahmen nicht. Wenn Sie z.B. einige Dateien angeben möchten, die mit Ihrer Anwendung veröffentlicht werden, können Sie weiterhin die bekannten Mechanismen in *csproj* dafür nutzen (z.B. das `<Content>`-Element).

### <a name="recommendation"></a>Empfehlung
Mit csproj empfehlen wir, dass Sie die Standardglobs aus Ihrem Projekt entfernen und nur Globsdateipfade für diese Artefakte hinzufügen, die Ihre Anwendung/Bibliothek für verschiedene Szenarios benötigt (Laufzeit, NuGet-Paket usw.)


## <a name="additions"></a>Erweiterungen

### <a name="sdk-attribute"></a>SDK-Attribut 
Das `<Project>`-Element der *.csproj*-Datei hat ein neues Attribut namens `Sdk`. `Sdk` gibt an, welches SDK vom Projekt verwendet wird. Das SDK ist, wie das [Schichtendokument](cli-msbuild-architecture.md) beschreibt, ein Satz von MSBuild-[Aufgaben](https://docs.microsoft.com/visualstudio/msbuild/msbuild-tasks) und -[Zielen](https://docs.microsoft.com/visualstudio/msbuild/msbuild-targets), die .NET Core-Code erstellen können. Wir liefern zwei Haupt-SDKs mit .NET Core-Tools:

1. Das .NET Core SDK mit der `Microsoft.NET.Sdk`-ID
2. Das .NET Core Web-SDK mit der `Microsoft.NET.Sdk.Web`-ID

Das `Sdk`-Attribut muss auf eine dieser IDs auf dem `<Project>`-Element festgelegt werden, um die .NET Core-Tools nutzen und Codes erstellen zu können. 

### <a name="packagereference"></a>PackageReference
Element, das eine NuGet-Abhängigkeit im Projekt angibt. Das `Include`-Attribut gibt die Paket-ID an. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Version
`Version` gibt die Version des wiederherzustellenden Pakets an. Das Element berücksichtigt die Regeln für das NuGet-Versionsschema.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets und PrivateAssets
Das `IncludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt werden sollen. 

Das `ExcludeAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, nicht genutzt werden sollen.

Das `PrivateAssets`-Attribut gibt an, welche Objekte, die zu dem durch `<PackageReference>` angegebenen Paket gehören, genutzt, aber nicht an das nächste Projekt übertragen werden sollen. 

> [!NOTE]
> `PrivateAssets` entspricht dem Element *project.json*/*xproj* `SuppressParent`.

Diese Attribute können eines oder mehrere der folgenden Elemente enthalten:

* `Compile`: Gibt an, dass die Inhalte des Ordners „lib“ zum Kompilieren verfügbar sind
* `Runtime`: Gibt an, dass die Inhalte des Ordners „runtime“ verteilt werden
* `ContentFiles`: Gibt an, dass die Inhalte des *contentfiles*-Ordner verwendet werden.
* `Build`: Gibt an, dass die Eigenschaften/Ziele im Ordner „build“ verwendet werden
* `Native`: Gibt an, dass die Inhalte der nativen Objekte für die Runtime in den Ausgabeordner kopiert werden
* `Analyzers`: Gibt an, dass Analysen verwendet werden

Alternativ kann das Attribut Folgendes enthalten:

* `None`: Keines der Objekte wird verwendet.
* `All`: Alle Objekte werden verwendet.

### <a name="dotnetclitoolreference"></a>DotnetCliToolReference
Das `<DotnetCliToolReference>`-Element gibt das CLI-Tool an, das der Benutzer im Kontext des Projekts wiederherstellen möchte. Es ist ein Ersatz für den `tools`-Knoten in *project.json*. 

```xml
<DotnetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>Version
`Version` gibt die Version des wiederherzustellenden Pakets an. Für das Attribut werden die Regeln für das NuGet-Versionsschema berücksichtigt.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
Das Element `<RuntimeIdentifiers>` ermöglicht die Angabe einer durch Semikolons getrennten Liste von [Runtime-IDs (RIDs)](../rid-catalog.md) für das Projekt. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


### <a name="runtimeidentifier"></a>RuntimeIdentifier
Das `<RuntimeIdentifier>`-Element ermöglicht die Angabe von nur einer einzigen [Runtime-ID (RID)](../rid-catalog.md) für das Projekt. RIDs ermöglichen das Veröffentlichen einer eigenständigen Bereitstellung. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


### <a name="packagetargetfallback"></a>PackageTargetFallback 
Das `<PackageTargetFallback>`-Element ermöglicht die Angabe eines Satzes von kompatiblen Zielen, die verwendet werden sollen, wenn Pakete wiederhergestellt werden. Dies soll ermöglichen, dass Pakete, in denen das .NET [TxM (Target x Moniker)](https://docs.microsoft.com/nuget/schema/target-frameworks) verwendet wird, mit Paketen funktionieren, in denen kein .NET TxM deklariert ist. Wird in einem Projekt das .NET TxM verwendet, müssen alle Pakete, zu denen es eine Abhängigkeit gibt, ebenfalls ein .NET TxM haben. Dies trifft nur dann nicht zu, wenn Sie das `<PackageTargetFallback>`-Element zu Ihrem Projekt hinzufügen, sodass Nicht-.NET-Plattformen mit .NET kompatibel sind. 

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
Mit dem Wechsel zu MSBuild haben wir die Eingabemetadaten, die beim Packen eines NuGet-Pakets verwendet werden, aus *project.json* in *.csproj*-Dateien verschoben. Die Eingaben sind MSBuild-Eigenschaften, sodass sie in eine `<PropertyGroup>`-Gruppe wechseln müssen. In der folgenden Liste sind die Eigenschaften aufgeführt, die als Eingaben für den Packvorgang verwendet werden, wenn der Befehl `dotnet pack` oder das MSBuild-Ziel `Pack` verwendet wird, das Bestandteil des SDKs ist. 

### <a name="ispackable"></a>IsPackable
Ein Boolescher Wert, der angibt, ob das Projekt verpackt werden kann. Der Standardwert ist `true`. 

### <a name="packageversion"></a>PackageVersion
Gibt die Version an, die das resultierende Paket haben wird. Akzeptiert alle Arten von NuGet-Versionszeichenfolgen. Standardmäßig beträgt der Wert `$(Version)` der Eigenschaft `Version` im Projekt. 

### <a name="packageid"></a>PackageId
Gibt den Namen für das resultierende Paket an. Wenn nicht angegeben, verwendet der `pack`-Vorgang standardmäßig `AssemblyName` oder den Verzeichnisnamen als Paketnamen. 

### <a name="title"></a>Titel
Ein benutzerfreundlicher Titel des Pakets, der in der Regel in der Benutzeroberfläche wie auf nuget.org angezeigt wird und der Paket-Manager in Visual Studio. Wenn nicht angegeben, wird stattdessen die Paket-ID verwendet.

### <a name="authors"></a>Authors
Eine durch Semikolons getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Diese werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete von den gleichen Autoren zu geben.

### <a name="description"></a>Beschreibung
Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.

### <a name="copyright"></a>Copyright
Copyright-Informationen für das Paket.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance
Ein Boolescher Wert, der angibt, ob der Client den Verbraucher dazu auffordern muss, die Paketlizenz vor der Installation des Pakets zu akzeptieren. Die Standardeinstellung ist `false`.

### <a name="packagelicenseurl"></a>PackageLicenseUrl
Eine URL für die Lizenz, die auf das Paket angewendet werden kann.

### <a name="packageprojecturl"></a>PackageProjectUrl
Eine URL für die Paket-Homepage, häufig auf der Benutzeroberfläche sowie auf nuget.org angezeigt.

### <a name="packageiconurl"></a>PackageIconUrl
Eine URL für ein 64x64-Bild mit transparentem Hintergrund, das als Symbol für das Paket in der UI-Anzeige verwendet wird.

### <a name="packagereleasenotes"></a>PackageReleaseNotes
Anmerkungen zu diesem Paket.

### <a name="packagetags"></a>PackageTags
Eine durch Semikolons getrennte Liste von Tags, die das Paket festlegt.

### <a name="packageoutputpath"></a>PackageOutputPath
Bestimmt den Ausgabepfad, in dem das gepackte Paket abgelegt wird. Der Standardwert ist `$(OutputPath)`. 

### <a name="includesymbols"></a>IncludeSymbols
Dieser Boolesche Wert gibt an, ob das Paket ein zusätzliches Symbolpaket erstellen soll, wenn das Projekt verpackt wird. Dieses Paket wird eine *.symbols.nupkg*-Erweiterung haben und die PDB-Dateien zusammen mit der DLL und anderen Ausgabedateien kopieren.

### <a name="includesource"></a>IncludeSource
Dieser Boolesche Wert gibt an, ob der Packprozess ein Quellpaket erstellen sollte. Das Quellpaket enthält den Quellcode der Bibliothek sowie die PDB-Dateien. Quelldateien werden im `src/ProjectName`-Verzeichnis in der resultierenden Paketdatei gespeichert. 

### <a name="istool"></a>IsTool
Gibt an, ob alle Ausgabedateien in den *Tools*-Ordner anstelle des *Lib*-Ordners kopiert werden. Beachten Sie, dass dies anders als ein `DotNetCliTool` ist, der angegeben wird, indem die `PackageType` in der *.csproj*-Datei eingestellt wird.

### <a name="repositoryurl"></a>RepositoryUrl
Gibt die URL für das Repository an, in der sich der Quellcode für das Paket befindet und/oder aus der es erstellt wird. 

### <a name="repositorytype"></a>RepositoryType
Gibt den Verzeichnistyp an. Der Standardwert ist „Git“. 

### <a name="nopackageanalysis"></a>NoPackageAnalysis
Gibt an, dass der Packvorgang keine Paketanalyse nach dem Erstellen des Pakets ausführen sollte.

### <a name="minclientversion"></a>MinClientVersion
Gibt die minimale Version des NuGet-Clients an, der dieses Paket installieren kann. Dies wird von nuget.exe und dem Paket-Manager von Visual Studio erzwungen.

### <a name="includebuildoutput"></a>IncludeBuildOutput
Dieser Boolesche Werte gibt an, ob die Buildausgabeassemblys in die *.nupkg*-Datei gepackt werden sollen oder nicht.

### <a name="includecontentinpack"></a>IncludeContentInPack
Dieser Boolesche Wert gibt an, ob alle Elemente, die über einen `Content`-Typ verfügen, automatisch im resultierenden Paket enthalten sind. Die Standardeinstellung ist `true`. 

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder
Gibt den Ordner an, in dem die Ausgabeassemblys positioniert werden. Die Ausgabeassemblys (und andere Ausgabedateien) werden in ihre jeweiligen Frameworkordner kopiert.

### <a name="contenttargetfolders"></a>ContentTargetFolders
Diese Eigenschaft gibt den Standardspeicherort an, an dem alle Inhaltsdateien gespeichert werden sollten, wenn `PackagePath` für sie nicht angegeben ist. Der Standardwert ist „content;contentFiles“.

### <a name="nuspecfile"></a>NuspecFile
Relativer oder absoluter Pfad zur *.nuspec*-Datei, die für die Komprimierung verwendet wird. 

> [!NOTE]
> Wenn die *.nuspec*-Datei angegeben ist, wird sie **ausschließlich** zur Verpackung von Informationen verwendet, und die Information in den Projekten wird nicht verwendet. 

### <a name="nuspecbasepath"></a>NuspecBasePath
Der Basispfad für die *.nuspec*-Datei.

### <a name="nuspecproperties"></a>NuspecProperties
Durch Semikolons getrennte Liste der Schlüssel = Wertpaare.
