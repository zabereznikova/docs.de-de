---
title: dotnet-Installationsskripts | Microsoft-Dokumentation
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
keywords: Dotnet-Installation, Dotnet-Installationsskripts, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
translationtype: Human Translation
ms.sourcegitcommit: 99254f84873003496ee00214d55ff908f9fd47d3
ms.openlocfilehash: 6301fb61be27d7dac6ead57159c0d9461b3eacb5
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-install-scripts-reference"></a>Dotnet-Installationsskripts Verweis

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die Befehlszeilenschnittstellen-Tools (CLI) von .NET Core und die freigegebene Laufzeit installiert werden.

## <a name="synopsis"></a>Übersicht
Windows:

```
dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture]
    [-SharedRuntime] [-DebugSymbols] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress]
```

Mac OS/Linux:

```
dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture]
    [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]
```

## <a name="description"></a>Beschreibung
Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können die Skripts aus der [CLI-GitHub-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain) herunterladen. 

Ihr Hauptverwendungszweck ist die Unterstützung bei Automatisierungsszenarios und Installationen ohne Administratorrechte. Es gibt zwei Skripts, eines für PowerShell unter Windows und ein Bash-Skript für Linux/OS X. Beide weisen dasselbe Verhalten auf. Das Bash-Skript „versteht“ auch PowerShell-Switches, sodass diese generell verwendet werden können. 

Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `--install-dir` angegebenen Speicherort. Standardmäßig wird das Installationsskript das SDK herunterladen und installieren. Wenn Sie nur die freigegebene Laufzeit abrufen möchten, können Sie das Argument `--shared-runtime` angeben. 

Standardmäßig wird das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzufügen. Dies kann überschrieben werden, wenn das Argument `--no-path` verwendet wird. 

Bevor Sie das Skript ausführen, installieren Sie alle erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`. Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden. Wenn nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die in der Hierarchie über dem Ordner gefunden wird, in dem das Skript aufgerufen wurde, das die Eigenschaft `version` enthält. Wenn diese nicht vorhanden ist, wird die neueste verwendet.

Sie können dieses Skript auch zum Abrufen des SDKs oder der freigegebenen Laufzeit-Debugbinärdateien mit Debugsymbolen mithilfe des Arguments `--debug` verwenden. Wenn Sie dies nicht bei der ersten Installation machen und bemerken, dass Sie Symbole später debuggen müssen, können Sie das Skript mit diesem Argument und der Version der Bits, die Sie installiert haben, erneut ausführen. 

## <a name="options"></a>Optionen
Optionen unterscheiden sich zwischen den Skriptimplementierungen. 

### <a name="powershell-windows"></a>PowerShell (Windows)
`-Channel [CHANNEL]`

Von welchem Kanal (z.B. `future`, `preview`, `production`) installiert wird. Der Standardwert ist `production`.

`-Version [VERSION]`

Welche CLI-Version zu installieren ist. Sie müssen die Version als dreiteilige Version (z B. 1.0.0-13232) angeben. Falls nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die die Eigenschaft `version` enthält. Wenn diese nicht vorhanden ist, wird die neueste verwendet.

`-InstallDir [DIR]`

Der Pfad für die Installation. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist *%LocalAppData%\.dotnet*.

`-Architecture [ARCH]`

Architektur von zu installierenden .NET Core-Binärdateien. Mögliche Werte sind &lt;Auto&gt;, x64 und x86. Der Standardwert ist &lt;Auto&gt;, der die derzeit ausgeführte Betriebssystemarchitektur darstellt.

`-SharedRuntime`

Falls festgelegt, werden nur die freigegebenen Laufzeitbestandteile installiert und nicht das gesamte SDK.

`-DebugSymbols`

Falls festgelegt, umfasst das Installationsprogramm Debuggingsymbole in der Installation.

> [!NOTE]
> Diese Option funktioniert noch nicht.

`-DryRun`

Falls festgelegt,wird das Skript nicht ausgeführt. Es wird stattdessen anzeigen, welche Befehlszeile verwendet werden soll, um die kürzlich angeforderte Version der .NET-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit einer bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.
Außerdem werden Speicherorte für Binärdateien angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

`-NoPath`

Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden. Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.

`-AzureFeed`

Die URL für den Azure-Feed, der von diesem Installer verwendet wird. Änderungen werden nicht empfohlen. Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Falls festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.

### <a name="bash-macoslinux"></a>Bash (Mac OS/Linux)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture]
    [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]
`

`--channel [CHANNEL]`

Der Kanal (z.B. „zukünftig“, „dev“, „Produktion“), aus dem installiert wird. Der Standardwert ist „Produktion“.

`--version [VERSION]`

Welche CLI-Version zu installieren ist. Sie müssen die Version als dreiteilige Version (z B. 1.0.0-13232) angeben. Falls nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die die Eigenschaft `version` enthält. Wenn diese nicht vorhanden ist, wird die neueste verwendet.

`--install-dir [DIR]`

Pfad zum Installationsort. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist `$HOME/.dotnet`.

`--architecture [ARCH]`

Architektur der zu installierenden .NET-Binärdateien. Mögliche Werte sind &lt;Auto&gt;, x64 und amd64. Der Standardwert ist &lt;Auto&gt;, der die derzeit ausgeführte Betriebssystemarchitektur darstellt.

`--shared-runtime`

Falls festgelegt, werden nur die freigegebenen Laufzeitbestandteile installiert und nicht das gesamte SDK.

`--debug-symbols`

Falls festgelegt, umfasst das Installationsprogramm Debuggingsymbole in der Installation.

> [!NOTE]
> Diese Option funktioniert noch nicht.

`--dry-run`

Falls festgelegt,wird das Skript nicht ausgeführt. Es wird stattdessen anzeigen, welche Befehlszeile verwendet werden soll, um die kürzlich angeforderte Version der .NET-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit einer bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann.
Außerdem werden Speicherorte für Binärdateien angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

`--no-path`

Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden. Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.

`--verbose`

Diagnoseinformationen anzeigen.

`--azure-feed`

Die URL für den Azure-Feed, der von diesem Installer verwendet wird. Änderungen werden nicht empfohlen. Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.

`--help`

Druckt Hilfe für das Skript aus.

## <a name="examples"></a>Beispiele

Installieren Sie die neueste Version von Dev am Standardspeicherort:

Windows:

`./dotnet-install.ps1 -Channel Future`

Mac OS/Linux:

`./dotnet-install.sh --channel Future`

Installieren Sie die aktuelle Preview am angegebenen Speicherort:

Windows:

`./dotnet-install.ps1 -Channel preview -InstallDir C:\cli`

Mac OS/Linux:

`./dotnet-install.sh --channel preview --install-dir ~/cli`
