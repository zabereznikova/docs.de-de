---
title: Befehl „dotnet remove reference“
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
ms.date: 02/14/2020
ms.openlocfilehash: 92d36bbbde64d806abc8f223c5f08e3f3d79ce9d
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463443"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework <FRAMEWORK>] <PROJECT_REFERENCES>

dotnet remove reference -h|--help
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
