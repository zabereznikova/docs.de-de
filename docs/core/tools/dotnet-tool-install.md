---
title: Befehl „dotnet tool install“
description: Der Befehl „dotnet tool install“ installiert das angegebene .NET Core-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 723d25caa6009288dbb55d55f173b04d7b983450
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463362"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool install`: Installiert das angegebene [.NET Core-Tool](global-tools.md) auf Ihrem Computer.

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

Der Befehl `dotnet tool install` ermöglicht Ihnen das Installieren von .NET Core-Tools auf Ihrem Computer. Um den Befehl zu verwenden, geben Sie eine der folgenden Installationsoptionen an:

* Verwenden Sie zum Installieren eines globalen Tools am Standardspeicherort die Option `--global`.
* Verwenden Sie zum Installieren eines globalen Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.
* Wenn Sie ein lokales Tool installieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

Globale Tools werden standardmäßig in den folgenden Verzeichnissen installiert, wenn Sie die Option `-g` oder `--global` angeben:

| Betriebssystem          | Pfad                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Lokale Tools werden zur Datei *tool-manifest.json* im Verzeichnis *.config* unter dem aktuellen Verzeichnis hinzugefügt. Wenn noch keine Manifestdatei vorhanden ist, erstellen Sie sie, indem Sie den folgenden Befehl ausführen:

```dotnetcli
dotnet new tool-manifest
```

Weitere Informationen finden Sie unter [Installieren eines lokalen Tools](global-tools.md#install-a-local-tool).

## <a name="arguments"></a>Argumente

- **`PACKAGE_NAME`**

  Name oder ID des NuGet-Pakets, das das zu installierende .NET Core-Tool enthält.

## <a name="options"></a>Optionen

- **`add-source <SOURCE>`**

  Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

- **`configfile <FILE>`**

  Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

- **`framework <FRAMEWORK>`**

  Legt das [Zielframework](../../standard/frameworks.md) des zu installierenden Tools fest. Das .NET Core SDK versucht standardmäßig, das am besten geeignete Zielframework auszuwählen.

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

- [.NET Core-Tools](global-tools.md)
- [Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI](global-tools-how-to-use.md)
- [Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI](local-tools-how-to-use.md)
