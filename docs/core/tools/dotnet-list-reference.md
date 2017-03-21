---
title: Verweisbefehl dotnet-list | Microsoft-Dokumentation
description: "Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-list, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: e95aa43bfed78d72ef1ea5f3883ae64e06ffaa99
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-list-reference"></a>Verweis „dotnet-list“

## <a name="name"></a>Name

`dotnet-list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

```
dotnet list [project] reference
dotnet list reference [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.

## <a name="arguments"></a>Argumente

`project`

Die Projektdatei, für die die Verweise aufgelistet werden. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Listen Sie die Projektverweise für das angegebene Projekt:

`dotnet list app/app.csproj reference`

Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:

`dotnet list reference`

