---
title: "dotnet-nuget-push-Befehl – .NET Core-CLI"
description: "Der dotnet-nuget-push-Befehl überträgt ein Paket auf den Server und veröffentlicht es."
keywords: dotnet-nuget-push, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 83da967d9d7432fcb422b88344ff597d45fc9e85
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-push"></a>dotnet-nuget push

## <a name="name"></a>Name

`dotnet-nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.

## <a name="synopsis"></a>Übersicht

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es. Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet). Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).

## <a name="arguments"></a>Argumente

`ROOT`

Geben Sie den Pfad des Pakets und den API-Schlüssel an, um das Paket an den Server zu übertragen.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-s|--source <SOURCE>`

Gibt die Server-URL an. Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.

`--symbols-source <SOURCE>`

Gibt die Symbolserver-URL an.

`-t|--timeout <TIMEOUT>`

Gibt das Timeout für die Übertragung auf einen Server in Sekunden an. Der Standardwert ist 300 Sekunden (5 Minuten). Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.

`-k|--api-key <API_KEY>`

Der API-Schlüssel für den Server.

`--symbol-api-key <API_KEY>`

Der API-Schlüssel für den Symbolserver.

`-d|--disable-buffering`

Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu verringern.

`-n|--no-symbols`

Überträgt keine Symbole (selbst wenn vorhanden).

`--force-english-output`

Erzwingt, dass alle protokollierten Ausgaben auf Englisch sein müssen.

## <a name="examples"></a>Beispiele

Überträgt *foo.nupkg* an die standardmäßige Pushquelle und stellt einen API-Schlüssel bereit:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `http://customsource` und stellt einen API-Schlüssel bereit:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

Überträgt *foo.nupkg* an die standardmäßige Pushquelle:

`dotnet nuget push foo.nupkg` 

Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:

`dotnet nuget push foo.symbols.nupkg`

Überträgt *foo.nupkg* an die standardmäßige Pushquelle und gibt ein Timeout von 360 Sekunden an:

`dotnet nuget push foo.nupkg --timeout 360`

Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:

`dotnet nuget push *.nupkg`

Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle und gibt die benutzerdefinierte Konfigurationsdatei *./config/My.Config* an:

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis mit maximaler Ausführlichkeit an die standardmäßige Pushquelle:

`dotnet nuget push *.nupkg --verbosity detailed`

