---
title: Befehl „dotnet tool update“
description: Der Befehl „dotnet tool update“ aktualisiert das angegebene .NET Core-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 497b052a8b9cfa9dca8d80316075fe7565d6b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847819"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool update`: Aktualisiert das angegebene [.NET Core-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME> <--tool-path>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <PACKAGE_NAME>
    [--configfile] [--framework] [-v|--verbosity]
    [--add-source]

dotnet tool update <-h|--help>
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool update` ermöglicht Ihnen das Aktualisieren der .NET Core-Tools auf Ihrem Computer auf die neueste stabile Version des Pakets. Der Befehl deinstalliert und installiert ein Tool neu, sodass es aktualisiert wird. Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:

* Verwenden Sie zum Aktualisieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.
* Verwenden Sie zum Aktualisieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.
* Wenn Sie ein lokales Tool aktualisieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

## <a name="arguments"></a>Argumente

- **`PACKAGE_NAME`**

  Name oder ID des NuGet-Pakets, das das zu aktualisierende globale .NET Core-Tool enthält. Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.

## <a name="options"></a>Optionen

- **`--add-source <SOURCE>`**

  Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

- **`--configfile <FILE>`**

  Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

- **`--framework <FRAMEWORK>`**

  Legt das [Zielframework](../../standard/frameworks.md) des zu aktualisierenden Tools fest.

- **`-g|--global`**

  Gibt an, dass das Update für ein benutzerweites Tool ist. Kann nicht mit der Option `--tool-path` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--tool-path <PATH>`**

  Gibt den Speicherort an, in dem das globale Tool installiert ist. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

- **`dotnet tool update -g dotnetsay`**

  Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Windows-Verzeichnis befindet.

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das sich in einem bestimmten Linux-/macOS-Verzeichnis befindet.

- **`dotnet tool update dotnetsay`**

  Aktualisiert das lokale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/), das im lokalen Verzeichnis installiert ist.

## <a name="see-also"></a>Siehe auch

- [.NET Core-Tools](global-tools.md)
- [Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI](global-tools-how-to-use.md)
- [Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI](local-tools-how-to-use.md)
