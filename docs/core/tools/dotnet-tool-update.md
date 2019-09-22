---
title: Befehl „dotnet tool update“
description: Der Befehl „dotnet tool update“ aktualisiert die angegebenen globalen .NET Core-Tools auf Ihrem Computer.
ms.date: 05/29/2018
ms.openlocfilehash: b10ce39c8b9d4df23243bcf672454a455e34eec1
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117535"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>NAME

`dotnet tool update`: Aktualisiert das angegebene [globale .NET Core-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Zusammenfassung

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a>BESCHREIBUNG

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

- [.NET Core Global Tools (Globale .NET Core-Tools)](global-tools.md)
