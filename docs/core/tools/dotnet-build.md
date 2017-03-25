---
title: Befehl dotnet-build | Microsoft-Dokumentation
description: "Der dotnet-build-Befehl erstellt ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-build, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 17c2db54f871795c370a6475c21e36736a6b46c3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-build"></a>dotnet-build

## <a name="name"></a>Name

`dotnet-build`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

```
dotnet build [project] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity]
dotnet build [--help]
```

## <a name="description"></a>Beschreibung
Der `dotnet build`-Befehl erstellt das Projekt und die zugehörigen Abhängigkeiten in einen Satz von Binärdateien. Die Binärdateien sind Symboldateien (mit einer `*.pdb`-Erweiterung), die zum Debuggen sowie als Projektcode in Intermediate Language (IL) mit einer `*.dll`-Erweiterung verwendet werden. Darüber hinaus wird eine JSON-Datei erstellt, die die Abhängigkeiten der Anwendung mit der `*.deps.json`-Erweiterung listet. Schließlich wird ebenfalls eine `runtime.config.json`-Datei erstellt. Diese Datei gibt die freigegebene Laufzeit und Version an, die für den erstellten Code ausgeführt werden. 

Verfügt das Projekt über Abhängigkeiten von Drittanbietern, z.B. Bibliotheken von NuGet, werden diese aus dem NuGet-Cache aufgelöst und sind nicht mit der Buildausgabe des Projekts verfügbar. Bedenken Sie, dass das Produkt von `dotnet build` nicht auf einen anderen Computer zur Ausführung übertragen werden sollen. Dies unterscheidet sich zum Verhalten des .NET Framework, bei dem die Erstellung eines ausführbaren Projekts (eine Anwendung) eine Ausgabe erzeugt, die auf jedem Computer ausgeführt werden kann, auf dem .NET Framework installiert ist. Um ein ähnliches Verhalten in .NET Core zu erhalten, müssen Sie den Befehl [dotnet publish](dotnet-publish.md) verwenden. Weitere Informationen finden Sie im Dokument [.NET Core-Anwendungsbereitstellung](../deploying/index.md). 

Zum Erstellen muss eine *assets.json*-Datei vorhanden sein (eine Datei, die alle Abhängigkeiten Ihrer Anwendung listet). Das bedeutet, dass Sie [`dotnet restore`](dotnet-restore.md) vor dem Erstellen des Projekts ausführen müssen. Ein Mangel an Ressourcendateien manifestiert sich als Unfähigkeit des Tools, die Verweisassemblys aufzulösen, was zu Fehlern führt. 

`dotnet build` verwendet MSBuild, um das Projekt zu erstellen und unterstützt daher parallele und inkrementelle Builds. Weitere Informationen zu diesen Themen finden Sie unter [MSBuild-Dokumentation](https://docs.microsoft.com/visualstudio/msbuild/msbuild). 

Zusätzlich zu diesen Optionen akzeptiert der `dotnet build`-Befehl MSBuild-Optionen, wie z.B. `/p` zum Festlegen von Eigenschaften oder `/l` zum Definieren eines Protokolls. Weitere Informationen über diese Optionen finden Sie in der [`dotnet msbuild`](dotnet-msbuild.md)-Befehlsdokumentation. Wenn Sie wissen möchten wann 

Ob das Projekt ausführbar ist oder nicht, richtet sich nach der `<OutputType>`-Eigenschaft in der Projektdatei. Das folgende Beispiel zeigt ein Projekt, das ausführbaren Code erzeugt: 


```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Lassen Sie diese Eigenschaft einfach weg, um eine Bibliothek zu erstellen. Der Hauptunterschied der Ausgabe ist die Tatsache, dass die IL-DLL für eine Bibliothek keine Einstiegspunkte enthält, und es nicht möglich ist, sie auszuführen. 

## <a name="arguments"></a>Argumente

`project`

Die zu erstellende Projektdatei.
Wenn Sie keine Projektdatei angeben, durchsucht MSBuild das aktuelle Arbeitsverzeichnis nach einer Dateierweiterung, die mit `proj` endet, und verwendet diese.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die erstellten Binärdateien platziert werden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben.

`-f|--framework <FRAMEWORK>`

Kompilierungen für ein bestimmtes Framework. Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

`-c|--configuration [Debug|Release]`

Definiert eine Konfiguration für die Erstellung. Wenn kein Wert angegeben ist, wird als Standardwert `Debug` verwendet.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Ziellaufzeit für die Erstellung. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`--version-suffix [VERSION_SUFFIX]`

Definiert, durch was `*` im Versionsfeld der Projektdatei ersetzt werden soll. Das Format entspricht den NuGet-Versionsrichtlinien.

`--no-incremental`

Markiert den Build als unsicher für inkrementelle Builds. Deaktiviert die inkrementelle Kompilierung und erzwingt eine komplette Neuerstellung des Abhängigkeitsdiagramms des Projekts.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten und erstellt nur das zum Erstellen angegebene Stammprojekt.

`-v|--verbosity`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet build`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet build --configuration Release`

Erstellt ein Projekt und seine Abhängigkeiten für eine bestimmte Laufzeit (in diesem Beispiel Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`
