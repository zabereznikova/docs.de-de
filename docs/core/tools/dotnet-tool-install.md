---
title: Befehl „dotnet tool install“
description: Der Befehl „dotnet tool install“ installiert das angegebene .NET-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1dd870a8f91e557a2f59919682616aa8817fc070
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634323"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool install`: Der Befehl installiert das angegebene [.NET-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool install <PACKAGE_NAME> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install <PACKAGE_NAME>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--framework <FRAMEWORK>] [-v|--verbosity <LEVEL>]
    [--version <VERSION_NUMBER>]

dotnet tool install -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool install` ermöglicht Ihnen das Installieren von .NET-Tools auf Ihrem Computer. Um den Befehl zu verwenden, geben Sie eine der folgenden Installationsoptionen an:

* Verwenden Sie zum Installieren eines globalen Tools am Standardspeicherort die Option `--global`.
* Verwenden Sie zum Installieren eines globalen Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.
* Wenn Sie ein lokales Tool installieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` oder `--global` angeben:

| Betriebssystem          | Pfad                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Lokale Tools werden der Datei *dotnet-tools.json* im Verzeichnis *.config* unter dem aktuellen Verzeichnis hinzugefügt. Wenn noch keine Manifestdatei vorhanden ist, erstellen Sie sie, indem Sie den folgenden Befehl ausführen:

```dotnetcli
dotnet new tool-manifest
```

Weitere Informationen finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool).

## <a name="arguments"></a>Argumente

- **`PACKAGE_NAME`**

  Der Name oder die ID des NuGet-Pakets, das das zu installierende .NET-Tool enthält

## <a name="options"></a>Optionen

- **`add-source <SOURCE>`**

  Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

- **`configfile <FILE>`**

  Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

- **`framework <FRAMEWORK>`**

  Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest. Das .NET SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.

- **`-g|--global`**

  Gibt an, dass die Installation benutzerweit ist. Kann nicht mit der Option `--tool-path` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`tool-path <PATH>`**

  Gibt den Speicherort des globalen Tools an, das installiert wird. „PATH“ kann absolut oder relativ sein. Wenn kein Pfad vorhanden ist, versucht der Befehl, ihn zu erstellen. Durch Weglassen von `--global` und `--tool-path` wird die Installation eines lokalen Tools angegeben.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

- **`--version <VERSION_NUMBER>`**

  Die Version des zu installierenden Tools. Standardmäßig wird die neueste stabile Paketversion installiert. Verwenden Sie diese Optionen zum Installieren von Vorschau- oder früheren Versionen des Tools.

## <a name="examples"></a>Beispiele

- **`dotnet tool install -g dotnetsay`**

  Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool am Standardspeicherort.

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Windows-Verzeichnis.

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool in einem bestimmten Linux/macOS-Verzeichnis.

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  Installiert Version 2.0.0 von [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als globales Tool.

- **`dotnet tool install dotnetsay`**

  Installiert [dotnetsay](https://www.nuget.org/packages/dotnetsay/) als lokales Tool im aktuellen Verzeichnis.

## <a name="see-also"></a>Siehe auch

- [.NET-Tools](global-tools.md)
- [Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI](global-tools-how-to-use.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
