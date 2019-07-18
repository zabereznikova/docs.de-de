---
title: Befehl „dotnet nuget push“
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4d5efa94c6a4494158aea447be98256d2a307cd6
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539129"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.

## <a name="synopsis"></a>Übersicht

```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a>BESCHREIBUNG

Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es. Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet). Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).

## <a name="arguments"></a>Argumente

* **`ROOT`**

  Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.

## <a name="options"></a>Optionen

* **`-d|--disable-buffering`**

  Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.

* **`--force-english-output`**

  Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.

* **`-h|--help`**

Druckt eine kurze Hilfe für den Befehl.

* **`--interactive`**

  Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion. Die Option ist seit dem .NET Core 2.2 SDK verfügbar.

* **`-k|--api-key <API_KEY>`**

  Der API-Schlüssel für den Server.

* **`-n|--no-symbols`**

  Überträgt keine Symbole (selbst wenn vorhanden).

* **`--no-service-endpoint`**

  Fügt „api/v2/package“ nicht der Quell-URL an. Die Option ist seit dem .NET Core 2.1 SDK verfügbar.

* **`-s|--source <SOURCE>`**

  Gibt die Server-URL an. Diese Option ist erforderlich, es sei denn, der `DefaultPushSource`-Konfigurationswert wurde in der NuGet-Konfigurationsdatei festgelegt.

* **`-sk|--symbol-api-key <API_KEY>`**

  Der API-Schlüssel für den Symbolserver.

* **`-ss|--symbol-source <SOURCE>`**

  Gibt die Symbolserver-URL an.

* **`-t|--timeout <TIMEOUT>`**

  Gibt das Timeout für die Übertragung auf einen Server in Sekunden an. Der Standardwert ist 300 Sekunden (5 Minuten). Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.

## <a name="examples"></a>Beispiele

* Überträgt *foo.nupkg* an die Standardpushquelle und gibt einen API-Schlüssel an:

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* Überträgt *foo.nupkg* an die standardmäßige Pushquelle:

  ```console
  dotnet nuget push foo.nupkg
  ```

* Überträgt *foo.symbols.nupkg* an die standardmäßige Symbolquelle:

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* Überträgt *foo.nupkg* an die Standardpushquelle und gibt ein Timeout von 360 Sekunden an:

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* Überträgt alle *NUPKG*-Dateien im aktuellen Verzeichnis an die standardmäßige Pushquelle:

  ```console
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > Wenn dieser Befehl nicht funktioniert, kann dies an einem Fehler aus früheren Versionen des SDK liegen (.NET Core 2.1 SDK und frühere Versionen).
  > Führen Sie ein Upgrade für das SDK durch, oder führen Sie stattdessen den folgenden Befehl aus, um diesen Fehler zu beheben: `dotnet nuget push **/*.nupkg`.
