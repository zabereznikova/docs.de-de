---
title: Verweisbefehl dotnet-remove | Microsoft-Dokumentation
description: "Der Verweisbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 1f1a364b703c6b83a9b21ee420d62411bf9cd3ec
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-reference"></a>Verweis „dotnet-remove“

## <a name="name"></a>Name

`dotnet-remove reference`: Entfernt Projekt-zu-Projekt-Verweise.

## <a name="synopsis"></a>Übersicht

```
dotnet remove [project] reference [-f|--framework] <project_references>
dotnet remove reference [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.

## <a name="arguments"></a>Argumente

`project`

Auszuführende Projektdatei. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.

`project_references`

Zu entfernende Projekt-zu-Projekt-Verweise. Sie können ein oder mehrere Projekte angeben. Globmuster wird auf Unix/Linux-basierten Terminals unterstützt.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-f|--framework <FRAMEWORK>`

Entfernt Projektverweise nur, wenn auf ein bestimmtes Framework abgezielt wird.

## <a name="examples"></a>Beispiele

Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Entfernen Sie mehrere Projektverweise mithilfe von Globmustern:

`dotnet remove app/app.csproj reference **/*.csproj`
