---
title: "Verweisbefehl „dotnet-remove“ – .NET Core-CLI | Microsoft-Dokumentation"
description: "Der Verweisbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 22db4037195afa2c49ef038832e09a99c6a0d54e
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-remove-reference"></a>Verweis „dotnet-remove“

## <a name="name"></a>Name

`dotnet-remove reference`: Entfernt Projekt-zu-Projekt-Verweise.

## <a name="synopsis"></a>Übersicht

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet remove reference`-Befehl bietet eine praktische Option zum Entfernen von Projektverweisen von einem Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Zielprojektdatei. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

`PROJECT_REFERENCES`

Zu entfernende Projekt-zu-Projekt (P2P)-Verweise. Sie können ein oder mehrere Projekte angeben. [Globmuster](https://en.wikipedia.org/wiki/Glob_(programming)) werden auf Unix/Linux-basierten Terminals unterstützt.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-f|--framework <FRAMEWORK>`

Entfernt den Verweis nur, wenn auf ein bestimmtes [Framework](../../standard/frameworks.md) abgezielt wird.

## <a name="examples"></a>Beispiele

Entfernen Sie einen Projektverweis aus dem angegebenen Projekt:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Entfernen Sie mehrere Projektverweise aus dem Projekt im aktuellen Verzeichnis:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Entfernen Sie mehrere Projektverweise mithilfe eines Globmusters auf Unix/Linux:

`dotnet remove app/app.csproj reference **/*.csproj`

