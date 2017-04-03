---
title: Verweisbefehl dotnet-add | Microsoft-Dokumentation
description: "Der dotnet-add-Verweisbefehl bietet eine praktische Option zum Hinzufügen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-add, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 7d23377244cfe60730b50bd247209de6e90bec70
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add-Verweis

## <a name="name"></a>Name

`dotnet-add reference` – Fügt Projekt-zu-Projekt-Verweise hinzu.

## <a name="synopsis"></a>Übersicht

```
dotnet add [project] reference [-f|--framework] <project_references>
dotnet add reference [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet add reference`-Befehl bietet eine praktische Option zum Hinzufügen von Projektverweisen auf ein Projekt. Nach dem Ausführen des Befehls werden die [`<ProjectReference>`](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items)-Fragmente in die Projektdatei hinzugefügt.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argumente

`project`

Auszuführende Projektdatei. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.

`project_references`

Hinzuzufügende Projekt-zu-Projekt-Verweise. Sie können ein oder mehrere Projekte angeben. Globmuster wird auf Unix/Linux-basierten Terminals unterstützt.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-f|--framework <FRAMEWORK>`

Fügt Projektverweise nur hinzu, wenn auf ein bestimmtes Framework abgezielt wird.

## <a name="examples"></a>Beispiele

Projektverweis hinzufügen:

`dotnet add app/app.csproj reference lib/lib.csproj`

Mehrere Projektverweise hinzufügen:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Mehrere Projektverweise mithilfe von Linux/Unix-Globmustern hinzufügen:

`dotnet add app/app.csproj reference **/*.csproj`
