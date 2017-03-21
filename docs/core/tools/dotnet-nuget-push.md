---
title: Befehl dotnet-nuget-push | Microsoft-Dokumentation
description: "Der dotnet-nuget-push-Befehl überträgt ein Paket auf den Server und veröffentlicht es."
keywords: dotnet-nuget-push, CLI, CLI-Befehl, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 54ffd79cc9306ffcc5793990c3dc2e7534ed3f4b
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-nuget-push"></a>dotnet-nuget-push

## <a name="name"></a>Name

`dotnet-nuget-push` – Überträgt ein Paket auf den Server und veröffentlicht es. 

## <a name="synopsis"></a>Übersicht

```
dotnet nuget push [<package>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-v|--verbosity]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>Beschreibung

Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es. Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet). Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.  

`-s|--source <SOURCE>`

Gibt die Server-URL an. Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.

`--symbols-source <SOURCE>`

Gibt die Symbolserver-URL an.

`-t|--timeout <TIMEOUT>`

Gibt das Timeout für die Übertragung auf einen Server in Sekunden an. Der Standardwert ist 300 Sekunden (5 Minuten). Wenn Sie 0 angeben, wird dieser Standardwert auch verwendet.

`-k|--api-key <API_KEY>`

Der API-Schlüssel für den Server.

`--symbol-api-key <API_KEY>`

Der API-Schlüssel für den Symbolserver.

`-d|--disable-buffering`

Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu verringern.

`-n|--no-symbols`

Überträgt keine Symbole (selbst wenn vorhanden).

`--force-english-output`

Erzwingt, dass alle protokollierten Ausgaben auf Englisch sein müssen. Neben der Flexibilität, eine englische Ausgabe auf einem nicht englischen Computer zu erzeugen, ist die Konsistenz zwischen Plattformen, die durch diese Option ermöglicht wird, ein nützliches Feature für automatisierte Tools, die aus den Protokollen Text extrahieren.

`--verbosity <LEVEL>`

Zeigt diesen Umfang an Details in der Ausgabe an. „Level“ kann `normal`, `quiet` oder `detailed` sein.

## <a name="examples"></a>Beispiele

Überträgt „foo.nupkg“ an die standardmäßige Pushquelle und stellt den API-Schlüssel bereit:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

Überträgt „foo.nupkg“ an die benutzerdefinierte Pushquelle `http://customsource` und stellt den API-Schlüssel bereit:

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

Überträgt „foo.nupkg“ an die standardmäßige Pushquelle:

`dotnet nuget push foo.nupkg` 

Überträgt „foo.symbols.nupkg“ an die standardmäßige Symbolquelle:

`dotnet nuget push foo.symbols.nupkg`

Überträgt „foo.nupkg“ an die standardmäßige Pushquelle und gibt ein Timeout von 360 Sekunden an:

`dotnet nuget push foo.nupkg --timeout 360`

Überträgt alle NUPKG-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:

`dotnet nuget push *.nupkg`

Überträgt alle NUPKG-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle und gibt die benutzerdefinierte Konfigurationsdatei *./config/My.Config* an:

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

Überträgt alle NUPKG-Dateien im aktuellen Verzeichnis mit maximaler Ausführlichkeit an die standardmäßige Pushquelle:

`dotnet nuget push *.nupkg --verbosity detailed`

