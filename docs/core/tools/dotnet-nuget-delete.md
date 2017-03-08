---
title: Befehl dotnet-nuget-delete | Microsoft-Dokumentation
description: "Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf."
keywords: dotnet-nuget-delete, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 2ce157e3f32f3e899245e38bb4520b17be3e0b32
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

## <a name="name"></a>Name

`dotnet-nuget-delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf. 

## <a name="synopsis"></a>Übersicht

```
dotnet nuget delete [<package_name> <package_version>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet nuget delete`-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf. Für „NuGet.org“ wird die Auflistung des Pakets aufgehoben.

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

Löscht Version 1.0 des Pakets „MyPackage“:

`dotnet nuget delete MyPackage 1.0` 

Löscht Version 1.0 des Pakets „MyPackage“, der Benutzer wird nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

