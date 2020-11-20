---
title: Befehl „dotnet tool update“
description: Der Befehl „dotnet tool update“ aktualisiert das angegebene .NET-Tool auf Ihrem Computer.
ms.date: 07/08/2020
ms.openlocfilehash: 18b153e53a6dbcb32e50ae4a7d06a1c2f53d1eb5
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634076"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool update`: Aktualisiert das angegebene [.NET-Tool](global-tools.md) auf Ihrem Computer

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool update` ermöglicht Ihnen das Aktualisieren der .NET-Tools auf Ihrem Computer auf die neueste stabile Version des Pakets. Der Befehl deinstalliert und installiert ein Tool neu, sodass es aktualisiert wird. Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:

* Verwenden Sie zum Aktualisieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.
* Verwenden Sie zum Aktualisieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.
* Um ein lokales Tool zu aktualisieren, verwenden Sie die Option `--local`.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

## <a name="arguments"></a>Argumente

- **`PACKAGE_ID`**

  Der Name oder die ID des NuGet-Pakets, das das zu aktualisierende globale .NET-Tool enthält. Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.

## <a name="options"></a>Optionen

- **`--add-source <SOURCE>`**

  Fügt eine zusätzliche NuGet-Paketquelle für die Installation hinzu.

- **`--configfile <FILE>`**

  Die zu verwendende NuGet-Konfigurationsdatei (*nuget.config*).

- **`--disable-parallel`**

  Verhindert die parallele Wiederherstellung mehrerer Projekte.

- **`--framework <FRAMEWORK>`**

  Legt das [Zielframework](../../standard/frameworks.md) des zu aktualisierenden Tools fest.

- **`--ignore-failed-sources`**

  Paketquellenfehler werden als Warnungen behandelt.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).

- **`--local`**

  Aktualisieren Sie das Tool und das lokale Toolmanifest. Kann nicht mit der Option `--global` oder der Option `--tool-path` kombiniert werden.

- **`--no-cache`**

  Pakete und HTTP-Anforderungen werden nicht zwischengespeichert.

- **`--tool-manifest <PATH>`**

  Pfad zur Manifestdatei.

- **`--tool-path <PATH>`**

  Gibt den Speicherort an, in dem das globale Tool installiert ist. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.

- **`--version <VERSION>`**

  Der Versionsbereich des Toolpakets, auf das aktualisiert werden soll. Dies kann nicht zum Herabstufen von Versionen verwendet werden. Sie müssen zuerst neuere Versionen `uninstall`.

- **`-g|--global`**

  Gibt an, dass das Update für ein benutzerweites Tool ist. Kann nicht mit der Option `--tool-path` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu aktualisierende Tool ein lokales Tool ist.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

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

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) auf die neueste Patchversion mit einer Hauptversion von `2` und einer Nebenversion von `0`.

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  Aktualisiert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) auf die niedrigste Version innerhalb des angegebenen Bereichs `(> 2.0.0 && < 2.1.4)`, Version `2.1.0` würde installiert. Weitere Informationen zu Bereichen der semantischen Versionsverwaltung finden Sie unter [Versionsbereiche von NuGet-Paketen](/nuget/concepts/package-versioning#version-ranges).

## <a name="see-also"></a>Siehe auch

- [.NET-Tools](global-tools.md)
- [Semantische Versionsverwaltung](https://semver.org)
- [Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI](global-tools-how-to-use.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
