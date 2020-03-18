---
title: Befehl „dotnet remove reference“
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
ms.date: 02/14/2020
ms.openlocfilehash: fcadf677faaf9281fb019c3c4bb16efc906b1aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503617"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Zielprojektdatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

`PROJECT_REFERENCES`

Zu entfernende Projekt-zu-Projekt-Verweise (P2P). Sie können ein oder mehrere Projekte angeben. [Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`-f|--framework <FRAMEWORK>`**

  Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.

## <a name="examples"></a>Beispiele

- Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
