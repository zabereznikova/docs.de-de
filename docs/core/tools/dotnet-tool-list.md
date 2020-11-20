---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die auf Ihrem Computer installierten .NET-Tools auf.
ms.date: 02/14/2020
ms.openlocfilehash: d884f2c41834dd9704de3a8ca15417ba368fde4b
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634284"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool list`: Der Befehl listet alle [.NET-Tools](global-tools.md) des angegebenen Typs auf, die derzeit auf Ihrem Computer installiert sind.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool list` bietet die Ihnen Möglichkeit, alle globalen, tool-path- oder lokalen .NET-Tools aufzulisten, die auf Ihrem Computer installiert sind. Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das Tool auf.  Um den Befehl zu verwenden, geben Sie eine der folgenden Optionen an:

* Verwenden Sie zum Auflisten globaler Tools am Standardspeicherort die Option `--global`.
* Verwenden Sie zum Auflisten globaler Tools an einem benutzerdefinierten Speicherort die Option `--tool-path`.
* Verwenden Sie die Option `--local`, oder lassen Sie die Optionen `--global`, `--tool-path` und `--local` aus, um lokale Tools aufzulisten.

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

- [.NET-Tools](global-tools.md)
- [Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI](global-tools-how-to-use.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
