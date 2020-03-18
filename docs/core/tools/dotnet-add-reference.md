---
title: dotnet add reference-Befehl
description: Der dotnet add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen.
ms.date: 02/14/2020
ms.openlocfilehash: 84ea25e94efc8d84aebfeccf62c30a64551c5019
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503787"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet add reference`: Fügt Projekt-zu-Projekt (P2P)-Verweise hinzu.

## <a name="synopsis"></a>Übersicht

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>Beschreibung

Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt. Nachdem Sie den Befehl ausgeführt haben, werden die `<ProjectReference>`-Elemente zur Projektdatei hinzugefügt.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argumente

- **`PROJECT`**

  Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

- **`PROJECT_REFERENCES`**

  Hinzuzufügende Projekt-zu-Projekt (P2P)-Verweise. Geben Sie ein oder mehrere Projekte an. [Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Systemen unterstützt.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`-f|--framework <FRAMEWORK>`**

  Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar seit .NET Core 3.0 SDK.

## <a name="examples"></a>Beispiele

- Projektverweis hinzufügen:

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- Fügen Sie dem Projekt im aktuellen Verzeichnis mehrere Projektverweise hinzu:

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Mehrere Projektverweise mithilfe eines Globmusters unter Linux/Unix hinzufügen:

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
