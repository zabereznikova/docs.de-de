---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die auf Ihrem Computer installierten .NET Core-Tools auf.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768273"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool list`: Listet alle [.NET Core-Tools](global-tools.md) des angegebenen Typs auf, der derzeit auf dem Computer installiert sind.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool list` bietet die Möglichkeit, alle globalen, Toolpfad- oder lokalen .NET Core-Tools aufzulisten, die auf Ihrem Computer installiert sind. Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das Tool auf.  Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:

* Verwenden Sie zum Auflisten globaler Tools am Standardspeicherort die Option `--global`.
* Verwenden Sie zum Auflisten globaler Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.
* Verwenden Sie zum Auflisten lokaler Tools die Option `--local`, oder lassen Sie die Optionen `--global`, `--tool-path` und `--local` aus.

**Lokale Tools sind ab .NET Core SDK 3.0 verfügbar.**

## <a name="options"></a>Optionen

- **`-g|--global`**

  Listet benutzerweite globale Tools auf. Kann nicht mit der Option `--tool-path` kombiniert werden. Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--local`**

  Diese Option listet lokale Tools für das aktuelle Verzeichnis auf. Sie kann nicht mit der Option `--global` oder `--tool-path` kombiniert werden. Wenn Sie sowohl `--global` als auch `--tool-path` auslassen, werden lokale Tools aufgelistet, auch wenn `--local` nicht angegeben wird.

- **`--tool-path <PATH>`**

  Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert werden. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Bei Weglassen von `--global` und `--tool-path` werden lokale Tools aufgelistet.

## <a name="examples"></a>Beispiele

- **`dotnet tool list -g`**

  Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil).

- **`dotnet tool list --tool-path c:\global-tools`**

  Listet die globalen Tools in einem bestimmten Windows-Verzeichnis auf.

- **`dotnet tool list --tool-path ~/bin`**

  Listet die globalen Tools in einem bestimmten Linux/macOS-Verzeichnis auf.

- **`dotnet tool list`** oder **`dotnet tool list --local`**

  Listet alle lokalen Tools auf, die im aktuellen Verzeichnis verfügbar sind.

## <a name="see-also"></a>Siehe auch

- [.NET Core-Tools](global-tools.md)
- [Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI](global-tools-how-to-use.md)
- [Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI](local-tools-how-to-use.md)
