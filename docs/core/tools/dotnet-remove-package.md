---
title: Paketbefehl dotnet-remove | Microsoft-Dokumentation
description: "Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt."
keywords: dotnet-remove, CLI, CLI-Befehl, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 87c80ad193df9cc3e0feabc41bb58f1d8dda23cd
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-remove-package"></a>Paket „dotnet-remove“

## <a name="name"></a>Name

`dotnet-remove package`: Entfernt Paketverweis aus einer Projektdatei.

## <a name="synopsis"></a>Übersicht

```
dotnet remove [project] package <package_name>
dotnet remove package [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.

## <a name="arguments"></a>Argumente

`project`

Auszuführende Projektdatei. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.

`package_name`

Zu entfernender Paketverweis.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:

`dotnet remove package Newtonsoft.Json`
