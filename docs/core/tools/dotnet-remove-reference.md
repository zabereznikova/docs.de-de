---
title: Verweisbefehl „dotnet remove“ – .NET Core-CLI
description: Der Verweisbefehl „dotnet remove“ bietet eine praktische Option zum Entfernen von Projekt-zu-Projekt-Verweisen.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 0b7fb2788ccc04b54bf02f0387141d501612c16d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove reference`: Entfernt Projekt-zu-Projekt-Verweise.

## <a name="synopsis"></a>Übersicht

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>description

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
