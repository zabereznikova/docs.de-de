---
title: '.NET Core-CLI-Befehl: dotnet tool update'
description: Der Befehl „dotnet tool update“ aktualisiert die angegebenen globalen .NET Core-Tools auf Ihrem Computer.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 90b0dc91f74d890420dc7185642aa89100cadba8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389471"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>name

`dotnet tool update`: Aktualisiert das angegebene [globale .NET Core-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Übersicht

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a>Beschreibung 

Der Befehl `dotnet tool update` ermöglicht Ihnen das Aktualisieren der globalen .NET Core-Tools auf Ihrem Computer auf die neueste stabile Version des Pakets. Der Befehl deinstalliert und installiert ein Tool neu, sodass es aktualisiert wird. Zum Verwenden des Befehls müssen Sie entweder mit der Option `--global` angeben, dass Sie ein Tool einer benutzerweiten Installation aktualisieren möchten, oder mit der Option `--tool-path` einen Pfad zum installierten Tool angeben.

## <a name="arguments"></a>Argumente

`PACKAGE_NAME`

Name oder ID des NuGet-Pakets, das das zu aktualisierende globale .NET Core-Tool enthält. Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.

## <a name="options"></a>Optionen

`--add-source <SOURCE>`

Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

`--configfile <FILE>`

Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

`--framework <FRAMEWORK>`

Legt das [Zielframework](../../standard/frameworks.md) des zu aktualisierenden Tools fest.

`-g|--global`

Gibt an, dass das Update für ein benutzerweites Tool ist. Kann nicht mit der Option `--tool-path` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--tool-path <PATH>`

Gibt den Speicherort an, in dem das globale Tool installiert ist. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool update -g dotnetsay`

Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Windows-Ordner befindet:

`dotnet tool update dotnetsay --tool-path c:\global-tools`

Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Linux-/macOS-Ordner befindet:

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Siehe auch

* [.NET Core Global Tools (Globale .NET Core-Tools)](global-tools.md)