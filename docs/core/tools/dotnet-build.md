---
title: dotnet build-Befehl – .NET Core-CLI
description: Der dotnet build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.openlocfilehash: 4fc93e013c271fdf856f5c73affffd3880d0dbea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-build"></a>dotnet-build

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet build`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a>description

Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien. Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden. Eine JSON-Datei für Abhängigkeiten (*\*.deps.json*) wird erstellt, die Abhängigkeiten der Anwendung aufführt. Eine *\*.runtimeconfig.json*-Datei wird erstellt, die die gemeinsam genutzte Laufzeit und deren Version für die Anwendung anzeigt.

Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar. Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann. Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist. Um ein ähnliches Verhalten mit .NET Core zu erhalten, müssen Sie den Befehl [dotnet publish](dotnet-publish.md) verwenden. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md).

Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt. Die Datei wird erstellt, wenn [`dotnet restore`](dotnet-restore.md) ausgeführt wird. Ohne die vorhandenen Ressourcendateien kann das Tool die Verweisassemblys nicht auflösen, was zu Fehlern führt. Mit dem .NET Core 1.x SDK müssen Sie `dotnet restore` explizit ausführen, bevor Sie `dotnet build` ausführen. Ab dem .NET Core 2.0 SDK wird `dotnet restore` implizit ausgeführt, wenn Sie `dotnet build` ausführen. Wenn Sie das implizite Wiederherstellen deaktivieren möchten, wenn Sie den Buildbefehl ausführen, können Sie die `--no-restore`-Option übergeben.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

`dotnet build` verwendet MSBuild, um das Projekt zu erstellen und unterstützt daher parallele und inkrementelle Builds. Weitere Informationen finden Sie unter [Inkrementelle Builds](/visualstudio/msbuild/incremental-builds).

Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `/p` zum Festlegen von Eigenschaften oder `/l` zum Definieren eines Protokolls. Erfahren Sie mehr über diese Optionen in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). 

Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei. Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Lassen Sie die `<OutputType>`-Eigenschaft weg, um eine Bibliothek zu erstellen. Der Hauptunterschied in der Buildausgabe ist, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält und nicht ausgeführt werden kann. 

## <a name="arguments"></a>Argumente

`PROJECT`

Die zu erstellende Projektdatei. Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit *proj* endet, und verwendet diese.

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md). Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

`--force`

 Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dies entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das zum Erstellen angegebene Stammprojekt.

`--no-incremental`

Markiert den Build als unsicher für inkrementelle Builds. Deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

`--no-restore`

Führt ekine implizite Wiederherstellung während der Projekterstellung durch.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die erstellten Binärdateien platziert werden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Legt die Ziellaufzeit fest. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei. Das Format entspricht den NuGet-Versionsrichtlinien.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md). Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das zum Erstellen angegebene Stammprojekt.

`--no-incremental`

Markiert den Build als unsicher für inkrementelle Builds. Deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die erstellten Binärdateien platziert werden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Legt die Ziellaufzeit fest. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei. Das Format entspricht den NuGet-Versionsrichtlinien.

---

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet build`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet build --configuration Release`

Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`

Erstellt ein Projekt und verwendet die angegebene NuGet-Paketquelle während des Wiederherstellungsvorgangs (.NET Core SDK 2.0 und spätere Versionen):

`dotnet build --source c:\packages\mypackages`