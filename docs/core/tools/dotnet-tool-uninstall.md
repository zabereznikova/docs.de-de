---
title: Befehl „dotnet tool uninstall“
description: Der Befehl „dotnet tool uninstall“ deinstalliert das angegebene .NET-Tool auf Ihrem Computer.
ms.date: 02/14/2020
ms.openlocfilehash: 34dffde8f9c930327c6b42d1d89bb4f511959fb2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634089"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool uninstall`: Der Befehl deinstalliert das angegebene [.NET-Tool](global-tools.md) auf Ihrem Computer.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool uninstall` ermöglicht Ihnen das Deinstallieren von .NET-Tools auf Ihrem Computer. Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:

* Verwenden Sie zum Deinstallieren eines globalen Tools, das am Standardspeicherort installiert wurde, die Option `--global`.
* Verwenden Sie zum Deinstallieren eines globalen Tools, das an einem benutzerdefinierten Speicherort installiert wurde, die Option `--tool-path`.
* Wenn Sie ein lokales Tool deinstallieren möchten, lassen Sie die Optionen `--global` und `--tool-path` weg.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

## <a name="arguments"></a>Argumente

- **`PACKAGE_NAME`**

  Der Name oder die ID des NuGet-Pakets, das das zu deinstallierende .NET Core-Tool enthält Mithilfe des Befehls [dotnet tool list](dotnet-tool-list.md) können Sie den Paketnamen abrufen.

## <a name="options"></a>Optionen

- **`-g|--global`**

  Gibt an, dass das zu entfernende Tool von einer benutzerweiten Installation stammt. Kann nicht mit der Option `--tool-path` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--tool-path <PATH>`**

  Gibt den Speicherort des Tools an, das deinstalliert wird. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Durch Weglassen von `--global` und `--tool-path` wird angegeben, dass das zu entfernende Tool ein lokales Tool ist.

## <a name="examples"></a>Beispiele

- **`dotnet tool uninstall -g dotnetsay`**

  Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Windows-Verzeichnis.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Deinstalliert das globale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus einem bestimmten Linux/macOS-Verzeichnis.

- **`dotnet tool uninstall dotnetsay`**

  Deinstalliert das lokale Tool [dotnetsay](https://www.nuget.org/packages/dotnetsay/) aus dem aktuellen Verzeichnis.

## <a name="see-also"></a>Siehe auch

- [.NET-Tools](global-tools.md)
- [Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI](global-tools-how-to-use.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
