---
title: Dotnet-Installationsskripts
description: Erfahren Sie mehr über die dotnet-Installationsskripts zur Installation des .NET Core SDK und der Shared Runtime.
ms.date: 01/23/2020
ms.openlocfilehash: bf28f872be3ac2b4115b1d5e5c06e32afec0b49e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77092862"
---
# <a name="dotnet-install-scripts-reference"></a>Dotnet-Installationsskripts Verweis

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem das .NET Core SDK und die Shared Runtime installiert werden.

## <a name="synopsis"></a>Übersicht

Windows:

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

Linux/macOS:

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a>Beschreibung

Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core SDK durchzuführen, die die .NET Core-CLI und die freigegebene Runtime enthält.

Es wird empfohlen, die stabile Version der Skripts zu verwenden:

- Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1>

Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich. Es gibt zwei Skripts: eines für PowerShell unter Windows und ein Bash-Skript für Linux/macOS. Beide Skripts weisen das gleiche Verhalten auf. Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können.

Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort. In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es. Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `-Runtime|--runtime`-Argument an.

In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu. Überschreiben Sie dieses Standardverhalten, indem sie das `-NoPath|--no-path`-Argument angeben.

Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](../install/dependencies.md).

Installieren Sie eine bestimmte Version mithilfe des Arguments `-Version|--version`. Die Version muss als dreiteilige Version (z. B. `2.1.0`) angegeben werden. Wenn nicht angegeben, wird die `latest`-Version verwendet.

## <a name="options"></a>Optionen

- **`-Channel|--channel <CHANNEL>`**

  Gibt den Quellkanal für die Installation an. Mögliche Werte sind:

  - `Current` – Aktuelles Release.
  - `LTS`: Long Term Support-Kanal (aktuell unterstütztes Release).
  - Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.1` oder `3.0`).
  - Branchname: zum Beispiel `release/3.1.1xx` oder `master` (für nächtliche Releases) Verwenden Sie diese Option, um eine Version aus einem Vorschaukanal zu installieren. Verwenden Sie den Namen des Kanals wie dieser unter [Installer und Binärdateien](https://github.com/dotnet/core-sdk#installers-and-binaries) aufgeführt wird.

  Der Standardwert ist `LTS`. Weitere Informationen zu .NET-Supportkanälen finden Sie auf der Seite [.NET-Supportrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- **`-Version|--version <VERSION>`**

  Stellt eine bestimmte Buildversion dar. Mögliche Werte sind:

  - `latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet).
  - `coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branchname-`-Channel`-Optionen verwendet).
  - Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option. Beispiel: `2.0.0-preview2-006120`.

  Wenn nichts angegeben ist, wird für `-Version` standardmäßig `latest` verwendet.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Gibt einen Pfad zu einer [global.json](global-json.md)-Datei an, die zur Bestimmung der SDK-Version verwendet wird. Die Datei *global.json* muss einen Wert für `sdk:version` haben.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Gibt den Installationspfad an. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist *%LocalAppData%\Microsoft\dotnet*. Binärdateien werden direkt im Verzeichnis platziert.

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Architektur der zu installierenden .NET Core-Binärdateien. Mögliche Werte sind `<auto>`, `amd64`, `x64`, `x86`, `arm64` und `arm`. Der Standardwert ist `<auto>`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Dieser Parameter ist veraltet und wird in einer zukünftigen Version des Skripts möglicherweise entfernt. Die empfohlene Alternative ist die `-Runtime|--runtime`-Option.

  Es werden nur die freigegebenen Runtimebestandteile installiert und nicht das gesamte SDK. Diese Option entspricht der Angabe von `-Runtime|--runtime dotnet`.

- **`-Runtime|--runtime <RUNTIME>`**

  Es wird nur die freigegebene Runtime installiert und nicht das gesamte SDK. Mögliche Werte sind:

  - `dotnet` – die freigegebene Runtime von `Microsoft.NETCore.App`.
  - `aspnetcore` – die freigegebene Runtime von `Microsoft.AspNetCore.App`.
  - `windowsdesktop` – die freigegebene Runtime von `Microsoft.WindowsDesktop.App`.

- **`-DryRun|--dry-run`**

  Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann. Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

- **`-NoPath|--no-path`**

  Wenn festgelegt, wird der Installationsordner nicht in den Pfad für die aktuelle Sitzung exportiert. Standardmäßig ändert das Skript den Pfad, wodurch die .NET Core-CLI sofort nach der Installation zur Verfügung gestellt wird.

- **`-Verbose|--verbose`**

  Es werden Diagnoseinformationen angezeigt.

- **`-AzureFeed|--azure-feed`**

  Gibt die URL für den Azure-Feed für den Installer an. Es wird nicht empfohlen, diesen Wert nicht zu ändern. Der Standardwert ist `https://dotnetcli.azureedge.net/dotnet`.

- **`-UncachedFeed|--uncached-feed`**

  Ermöglicht das Ändern der URL für den nicht zwischengespeicherten Feed, der von diesem Installer verwendet wird. Es wird nicht empfohlen, diesen Wert nicht zu ändern.

- **`-NoCdn|--no-cdn`**

  Deaktiviert das Herunterladen aus dem [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) und verwendet den nicht zwischengespeicherten Feed direkt.

- **`-FeedCredential|--feed-credential`**

  Wird als Abfragezeichenfolge zum Anfügen an den Azure-Feed verwendet. Ermöglicht das Ändern der URL, um nicht öffentliche Blob Storage-Konten verwenden zu können.

- **`--runtime-id`**

  Gibt den [Runtimebezeichner](../rid-catalog.md) an, für den die Tools installiert werden. Verwenden Sie `linux-x64` für portable Linux-Distributionen. (Nur für Linux und macOS gültig)

- **`-ProxyAddress`**

  Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen. (Nur gültig für Windows)

- **`ProxyUseDefaultCredentials`**

  Wenn festgelegt, verwendet der Installer bei Verwendung der Proxyadresse die Anmeldeinformationen des aktuellen Benutzers. (Nur gültig für Windows)

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Die Installation nicht versionierte Dateien, wie *dotnet.exe*, wird übersprungen, falls diese bereits vorhanden sind.

- **`-Help|--help`**

  Druckt Hilfe für das Skript aus.

## <a name="examples"></a>Beispiele

- Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  Mac OS/Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- Installieren Sie die aktuelle Version von Kanal 3.1 am angegebenen Speicherort:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  Mac OS/Linux:

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- Installieren Sie die Version 3.0.0 der Shared Runtime:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  Mac OS/Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- Rufen Sie das Skript ab und installieren Sie die Version 2.1.2 hinter einem Unternehmensproxy (nur Windows):

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  Mac OS/Linux:

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>Weitere Informationen

- [.NET Core-Releases](https://github.com/dotnet/core/releases)
- [Downloadarchiv von .NET Core Runtime und des SDK](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
