---
title: Befehl dotnet-nuget-delete | Microsoft-Dokumentation
description: "Der dotnet-nuget-delete-Befehl löscht ein Paket vom Server oder hebt dessen Auflistung auf."
keywords: dotnet-nuget-delete, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 787b1427b1064943570cbc361042ab2f20d11088
ms.lasthandoff: 01/21/2017

---

#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Name 
`dotnet-nuget-delete` – Löscht ein Paket vom Server oder hebt dessen Auflistung auf. 

## <a name="synopsis"></a>Übersicht

`dotnet nuget delete [<package_name> <package_version>] 
    [--help] [--source] [--non-interactive] 
    [--api-key] [--force-english-output] [--verbosity] [--config-file]`

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

`--verbosity <LEVEL>`

Zeigt diesen Umfang an Details in der Ausgabe an. „Level“ kann `normal`, `quiet` oder `detailed` sein.

`--config-file <FILE>`

Eine NuGet-Konfigurationsdatei, die speziell für diesen Befehl verwendet wird. Sie ersetzt andere Konfigurationsdateien, die vom standardmäßigen Vorgang zur Ermittlung und Verkettung von Konfigurationsdateien gefunden wurden. Der Pfad kann absolut oder relativ sein.
Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet).

## <a name="examples"></a>Beispiele

Löscht Version 1.0 des Pakets „MyPackage“:

`dotnet nuget delete MyPackage 1.0` 

Löscht Version 1.0 des Pakets „MyPackage“, der Benutzer wird nicht zur Eingabe von Anmeldeinformationen oder zu anderen Eingaben aufgefordert:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

Löscht Version 1.0 des Pakets „MyPackage“, dabei wird die benutzerdefinierte Konfigurationsdatei *./config/My.Config* angegeben:

`dotnet nuget delete MyPackage 1.0 --config-file ./config/My.Config`

Löscht Version 1.0 des Pakets „MyPackage“ mit einem maximalen Grad an Ausführlichkeit:

`dotnet nuget delete MyPackage 1.0 --verbosity detailed`

