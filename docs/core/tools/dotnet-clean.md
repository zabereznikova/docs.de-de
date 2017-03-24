---
title: Befehl dotnet-clean | Microsoft-Dokumentation
description: "Mit dem Befehl „dotnet-clean“ wird das aktuelle Verzeichnis bereinigt."
keywords: dotnet-clean, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3c00f4616932318b5dc5d77cbdf6c645696a4226
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Name

`dotnet-clean`: Löscht die Ausgabe eines Projekts. 

## <a name="synopsis"></a>Übersicht

```
dotnet clean [project] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity]
dotnet clean [--help] 
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet clean` löscht die Ausgabe des vorherigen Builds. Der Befehl ist als ein MSBuild-Ziel implementiert, sodass das Projekt ausgewertet wird. Es werden nur die Ausgaben gelöscht, die während des Builds erstellt wurden. Sowohl der Ordner für Zwischenausgabe (`obj`) als auch der Ordner für die endgültige Ausgabe (`bin`) werden bereinigt. 

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-o|--output <OUTPUT_DIRECTORY>`

Verzeichnis, in dem die erstellten Binärdateien abgelegt wurden. Sie müssen außerdem `--framework` definieren, wenn Sie diese Option angeben. Wenn Sie diese Eigenschaft zur Buildzeit nicht angegeben haben, müssen Sie sie nicht zum Bereinigen angeben.

`-f|--framework <FRAMEWORK>`

Das Framework, das zur Buildzeit angegeben wurde. Wenn Sie diese Eigenschaft zur Buildzeit nicht angegeben haben, müssen Sie sie nicht zum Bereinigen angeben. Das Framework muss in der [Projektdatei](csproj.md) definiert werden.

`-c|--configuration [Debug|Release]`

Gibt eine Konfiguration an, unter der der Build ausgeführt wurde.  Wenn kein Wert angegeben ist, wird als Standardwert `Debug` verwendet. Wenn Sie diese Eigenschaft zur Buildzeit nicht angegeben haben, müssen Sie sie nicht zum Bereinigen angeben.

`-v|--verbosity <Quiet|Minimal|Normal|Diag>`

Legt die Ausführlichkeit fest, die für den Aufruf des Befehls `dotnet clean` verwendet werden soll. Die Ausführlichkeitsgrade sind standardmäßige [MSBuild-Ausführlichkeitsgrade](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Beispiele

Bereinigen Sie einen Standardbuild des Projekts:

`dotnet clean`

Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

`dotnet clean --configuration Release`

