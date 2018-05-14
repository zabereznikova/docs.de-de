---
title: Paketbefehl „dotnet-remove“ – .NET Core-CLI
description: Der Paketbefehl „dotnet-remove“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 6a18be1a853119be245623e8fa0a0e44ed819e8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.

## <a name="synopsis"></a>Übersicht

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>description

Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt die Projektdatei an. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektmappendatei.

`PACKAGE_NAME`

Zu entfernender Paketverweis.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:

`dotnet remove package Newtonsoft.Json`
