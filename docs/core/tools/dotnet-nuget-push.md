---
title: Befehl „dotnet nuget push“
description: Der dotnet nuget push-Befehl überträgt ein Paket auf den Server und veröffentlicht es.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 99e735f7bb18b7af1c12c3ef77fc150a19083542
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970654"
---
# <a name="dotnet-nuget-push"></a>dotnet nuget push

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet nuget push` – Überträgt ein Paket auf den Server und veröffentlicht es.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet nuget push`-Befehl überträgt ein Paket auf den Server und veröffentlicht es. Der Pushbefehl verwendet Details zum Server und den Anmeldeinformationen aus der NuGet-Konfigurationsdatei oder der Kette von Konfigurationsdateien des Systems. Weitere Informationen zu Konfigurationsdateien finden Sie unter [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Konfigurieren des Verhaltens von NuGet). Die NuGet-Standardkonfiguration wird abgerufen, indem *%AppData%\NuGet\NuGet.config* (Windows) oder *$HOME/.local/share* (Linux/macOS) geladen wird. Anschließend wird eine beliebige Datei *nuget.config* oder *.nuget\nuget.config* geladen (beginnend mit dem Stamm des Laufwerks und endend im aktuellen Verzeichnis).

Der Befehl pusht ein vorhandenes Paket. Es wird kein Paket erstellt. Verwenden Sie [`dotnet pack`](dotnet-pack.md), um ein Paket zu erstellen.

## <a name="arguments"></a>Argumente

- **`ROOT`**

  Gibt den Dateipfad des Pakets an, das per Push übertragen werden soll.

## <a name="options"></a>Optionen

- **`-d|--disable-buffering`**

  Deaktiviert die Pufferung bei Übertragungen an HTTP(S)-Server, um die Speicherauslastung zu reduzieren.

- **`--force-english-output`**

  Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht, den Befehl zu blockieren, und fordert für Vorgänge wie z.B. die Authentifizierung eine manuelle Aktion. Die Option ist seit dem .NET Core 2.2 SDK verfügbar.

- **`-k|--api-key <API_KEY>`**

  Der API-Schlüssel für den Server.

- **`-n|--no-symbols true`**

  Überträgt keine Symbole (selbst wenn vorhanden).

- **`--no-service-endpoint`**

  Fügt „api/v2/package“ nicht der Quell-URL an. Die Option ist seit dem .NET Core 2.1 SDK verfügbar.

- **`-s|--source <SOURCE>`**

  Gibt die Server-URL an. NuGet identifiziert eine UNC oder lokale Ordnerquelle und kopiert die Datei dorthin, anstatt sie mithilfe von HTTP zu pushen.
  > [!IMPORTANT]
  > Ab NuGet 3.4.2 handelt es sich hierbei um einen obligatorischen Parameter, außer in der NuGet-Konfigurationsdatei wird ein `DefaultPushSource`-Wert angegeben. Weitere Informationen finden Sie unter [Konfigurieren des NuGet-Verhaltens](/nuget/consume-packages/configuring-nuget-behavior).

- **`--skip-duplicate`**

  Wenn Sie mehrere Pakete per Push an einen HTTP(S)-Server senden, werden alle Antworten des Typs „409 (Konflikt)“ als Warnung behandelt, sodass der Pushvorgang fortgesetzt werden kann. Verfügbar seit .NET Core 3.1 SDK.

- **`-sk|--symbol-api-key <API_KEY>`**

  Der API-Schlüssel für den Symbolserver.

- **`-ss|--symbol-source <SOURCE>`**

  Gibt die Symbolserver-URL an.

- **`-t|--timeout <TIMEOUT>`**

  Gibt das Timeout für die Übertragung auf einen Server in Sekunden an. Der Standardwert ist 300 Sekunden (5 Minuten). Wenn 0 (null Sekunden) angegeben wird, gilt der Standardwert.

## <a name="examples"></a>Beispiele

- Pusht *foo.nupkg* mithilfe eines API-Schlüssels an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- Überträgt *foo.nupkg* an den offiziellen NuGet-Server und gibt einen API-Schlüssel an:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * Überträgt *foo.nupkg* an die benutzerdefinierte Pushquelle `https://customsource` und gibt einen API-Schlüssel an:

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- Pusht *foo.nupkg* an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- Pusht *foo.symbols.nupkg* an die Standardsymbolquelle:

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- Pusht *foo.nupkg* an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle, mit einem Timeout von 360 Sekunden:

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- Pusht alle *NUPKG*-Dateien im aktuellen Verzeichnis an die in der NuGet-Konfigurationsdatei angegebene Standardpushquelle:

  ```dotnetcli
  dotnet nuget push "*.nupkg"
  ```

  > [!NOTE]
  > Wenn dieser Befehl nicht funktioniert, kann dies an einem Fehler aus früheren Versionen des SDK liegen (.NET Core 2.1 SDK und frühere Versionen).
  > Führen Sie ein Upgrade für das SDK durch, oder führen Sie stattdessen den folgenden Befehl aus, um diesen Fehler zu beheben: `dotnet nuget push "**/*.nupkg"`.
  
  > [!NOTE]
  > Die einschließenden Anführungszeichen sind für Shells wie Bash erforderlich, die Dateiglobbing ausführen. Weitere Informationen finden Sie unter [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).

- Pushen Sie alle *.nupkg*-Dateien an die in der NuGet-Konfigurationsdateien angegebene Standardpushquelle, auch wenn von einem HTTP(S)-Server eine Antwort des Typs „409 (Konflikt)“ zurückgegeben wird:

  ```dotnetcli
  dotnet nuget push "*.nupkg" --skip-duplicate
  ```

- Pushen Sie alle *NUPKG*-Dateien im aktuellen Verzeichnis an ein lokales Feedverzeichnis:

  ```dotnetcli
  dotnet nuget push "*.nupkg" -s c:\mydir
  ```

  Dieser Befehl speichert Pakete nicht in einer hierarchischen Ordnerstruktur, um die Leistung zu optimieren. Weitere Informationen finden Sie im Artikel zu [lokalen Feeds](/nuget/hosting-packages/local-feeds).  
