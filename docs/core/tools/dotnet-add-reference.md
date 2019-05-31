---
title: Befehl „dotnet-add reference“
description: Der dotnet add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen.
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631940"
---
# <a name="dotnet-add-reference"></a>dotnet-add-Verweis

**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet add reference`: Fügt Projekt-zu-Projekt (P2P)-Verweise hinzu.

## <a name="synopsis"></a>Übersicht

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt. Nach dem Ausführen des Befehls werden die [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items)-Elemente zur Projektdatei hinzugefügt.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argumente

* **`PROJECT`**

  Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

* **`PROJECT_REFERENCES`**

  Hinzuzufügende Projekt-zu-Projekt (P2P)-Verweise. Geben Sie ein oder mehrere Projekte an. [Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Systemen unterstützt.

## <a name="options"></a>Optionen

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

* **`-f|--framework <FRAMEWORK>`**

  Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.

## <a name="examples"></a>Beispiele

* Projektverweis hinzufügen:

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* Fügen Sie dem Projekt im aktuellen Verzeichnis mehrere Projektverweise hinzu:

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* Mehrere Projektverweise mithilfe eines Globmusters unter Linux/Unix hinzufügen:

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
