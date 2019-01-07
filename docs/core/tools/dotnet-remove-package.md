---
title: Befehl „dotnet remove package“
description: Der Befehl „dotnet remove package“ bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen auf ein Projekt.
ms.date: 05/29/2018
ms.openlocfilehash: 4cc8ac927b761547dc5e53be9abeba827bf1e1d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168727"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet remove package`: Entfernt Paketverweis aus einer Projektdatei.

## <a name="synopsis"></a>Übersicht

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet remove package`-Befehl bietet eine praktische Option zum Entfernen von NuGet-Paketverweisen aus einem Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt die Projektdatei an. Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

`PACKAGE_NAME`

Zu entfernender Paketverweis.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Entfernt `Newtonsoft.Json`-NuGet-Paket aus einem Projekt im aktuellen Verzeichnis:

`dotnet remove package Newtonsoft.Json`