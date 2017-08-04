---
title: "Verweisbefehl „dotnet-list“ – .NET Core-CLI"
description: "Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Projekt-zu-Projekt-Verweisen."
keywords: dotnet-list, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 701345e4db51d26b9eefe8f02b6c0526934de5c9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-list-reference"></a>Verweis „dotnet-list“

## <a name="name"></a>Name

`dotnet-list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Listen Sie die Projektverweise für das angegebene Projekt:

`dotnet list app/app.csproj reference`

Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:

`dotnet list reference`

