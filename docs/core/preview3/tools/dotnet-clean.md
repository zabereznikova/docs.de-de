---
title: Befehl dotnet-clean | Microsoft-Dokumentation
description: "Mit dem Befehl „dotnet-clean“ wird das aktuelle Verzeichnis bereinigt."
keywords: dotnet-clean, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 01/31/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 12144def2095246bb6611522b3dbc2d7e441135a

---

#<a name="dotnet-clean"></a>dotnet-clean

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Name 
`dotnet-clean`: Löscht die Ausgabe eines Projekts. 

## <a name="synopsis"></a>Übersicht

`dotnet clean [--help] [--output]  [--framework]  
    [--configuration]  [--verbosity]
    [<project>]`

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

`-v|--verbosity [Quiet|Minimal|Normal|Diag]`

Legt die Ausführlichkeit fest, die für den Aufruf des Befehls `dotnet clean` verwendet werden soll. Die Ausführlichkeitsgrade sind standardmäßige [MSBuild-Ausführlichkeitsgrade](https://msdn.microsoft.com/en-us/library/ms164311.aspx). 


## <a name="examples"></a>Beispiele

Bereinigen Sie einen Standardbuild des Projekts:

`dotnet clean`

Bereinigen Sie ein Projektbuild mit der Konfiguration „Release“:

`dotnet clean --configuration Release`



<!--HONumber=Feb17_HO2-->


