---
title: "dotnet nuget delete-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 65fe52f07ed823b4f7518c5b1f2da1f7a61b0371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet nuget delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf.

## <a name="synopsis"></a>Übersicht

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf. Für [nuget.org](https://www.nuget.org/) wird die Auflistung des Pakets aufgehoben.

## <a name="arguments"></a>Argumente

`PACKAGE_NAME`

Zu löschendes Paket.

`PACKAGE_VERSION`

Version des zu löschenden Pakets.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-s|--source <SOURCE>`

Gibt die Server-URL an. Unterstützte URLs für „nuget.org“ sind u.a. `http://www.nuget.org`, `http://www.nuget.org/api/v3` und `http://www.nuget.org/api/v2/package`. Ersetzen Sie für private Feeds den Hostnamen (z.B. `%hostname%/api/v3`).

`--non-interactive`

Fordert nicht zu Eingaben oder Bestätigungen des Benutzers auf.

`-k|--api-key <API_KEY>`

Der API-Schlüssel für den Server.

`--force-english-output`

Erzwingt, dass die Befehlszeilenausgabe auf Englisch ist.

## <a name="examples"></a>Beispiele

Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

Löscht Version 1.0 des Pakets `Microsoft.AspNetCore.Mvc`, wobei der Benutzer nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert wird:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`