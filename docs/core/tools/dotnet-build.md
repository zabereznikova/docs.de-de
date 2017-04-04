---
title: "Befehl dotnet-build – .NET Core CLI | Microsoft-Dokumentation"
description: "Der dotnet-build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-build, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: e5deac8a7b8faac97ccf8b801f274a2c03268d64
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-build"></a>dotnet-build

## <a name="name"></a>Name

`dotnet-build`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet build [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien. Die Binärdateien enthalten den Projektcode in Intermediate Language-Dateien (IL) mit einer *.dll*-Erweiterung und Symboldateien, die zum Debuggen mit einer *.pdb*-Erweiterung verwendet werden. Eine JSON-Datei für Abhängigkeiten (*\*.deps.json*) wird erstellt, die Abhängigkeiten der Anwendung aufführt. Eine *\*.runtimeconfig.json*-Datei wird erstellt, die die gemeinsam genutzte Laufzeit und deren Version für die Anwendung anzeigt.

Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar. Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden kann. Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist. Um ein ähnliches Verhalten mit .NET Core zu erhalten, verwenden Sie den Befehl [dotnet publish](dotnet-publish.md). Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md). 

Das Erstellen erfordert die *project.assets.json*-Datei, die die Abhängigkeiten Ihrer Anwendung aufführt. Die Datei wird erstellt, wenn Sie [`dotnet restore`](dotnet-restore.md) vor dem Erstellen des Projekts ausführen. Ohne die vorhandenen Ressourcendateien kann das Tools die Verweisassemblys nicht auflösen, was zu Fehlern führt.

`dotnet build` verwendet MSBuild, um das Projekt zu erstellen und unterstützt daher parallele und inkrementelle Builds. Weitere Informationen finden Sie unter [Inkrementelle Builds](https://docs.microsoft.com/visualstudio/msbuild/incremental-builds). 

Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `/p` zum Festlegen von Eigenschaften oder `/l` zum Definieren eines Protokolls. Erfahren Sie mehr über diese Optionen in der [MSBuild-Befehlszeilenreferenz](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

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

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die erstellten Binärdateien platziert werden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.

`-f|--framework <FRAMEWORK>`

Kompiliert für ein bestimmtes [Framework](../../standard/frameworks.md). Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

`-c|--configuration <CONFIGURATION>`

Legt die Buildkonfiguration fest. Wenn nicht angegeben, wird standardmäßig die Buildkonfiguration auf `Debug` festgelegt. Verwendet `Release`, um eine Releasekonfiguration zu erstellen.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Legt die Ziellaufzeit fest. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix für ein Sternchen (`*`) im Versionsfeld der Projektdatei. Das Format entspricht den NuGet-Versionsrichtlinien.

`--no-incremental`

Markiert den Build als unsicher für inkrementelle Builds. Deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten (P2P) und erstellt nur das zum Erstellen angegebene Stammprojekt.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet build`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet build --configuration Release`

Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`

