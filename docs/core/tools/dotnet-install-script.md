---
title: Dotnet-Installationsskripts
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
keywords: Dotnet-Installation, Dotnet-Installationsskripts, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/10/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8af168e96f8f5b57626b126135d8b5e509fbb059
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-install-scripts-reference"></a>Dotnet-Installationsskripts Verweis

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die .NET Core-Befehlszeilenschnittstellen-Tools und die freigegebene Laufzeit installiert werden.

## <a name="synopsis"></a>Übersicht

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DebugSymbols] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress]`

Mac OS/Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

## <a name="description"></a>Beschreibung

Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können die Skripts aus dem [CLI-GitHub-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain) herunterladen. 

Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich. Es gibt zwei Skripts: Das eine ist ein PowerShell-Skript, das unter Windows funktioniert. Das andere Skript ist ein Bash-Skript, das auf Linux/OS X funktioniert. Beide Skripts weisen dasselbe Verhalten auf. Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/OS X-Systemen verwenden können. 

Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort. In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es. Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `--shared-runtime`-Argument an. 

In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu. Überschreiben Sie dieses Standardverhalten, indem sie das `--no-path`-Argument angeben. 

Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`. Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden. Wenn nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die in der Hierarchie über dem Ordner gefunden wird, in dem das Skript aufgerufen wird, das die Eigenschaft `version` enthält. Wenn nicht vorhanden, wird die neueste Version verwendet.

Sie können dieses Skript auch zum Abrufen des SDK oder der freigegebenen Laufzeit-Debugbinärdateien mit Debugsymbolen mithilfe des Arguments `--debug` verwenden. Wenn Sie dies bei der ersten Installation nicht getan haben und Sie später die Debugsymbole benötigen, können Sie das Skript mit dem `--debug`-Argument und der installierten SDK-Version erneut ausführen, um die Debugsymbole zu erhalten. 

## <a name="options"></a>Optionen

Hinweis: Optionen unterscheiden sich zwischen den Skriptimplementierungen. 

### <a name="powershell-windows"></a>PowerShell (Windows)

`-Channel <CHANNEL>`

Gibt den Quellkanal für die Installation an. Mögliche Werte sind:

- `Current`: Aktuelle Version
- `LTS`: Long Term Support-Kanal (aktuell unterstützte Versionen)
- Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`)
- Branchname [z.B. `release/2.0.0`, `release/2.0.0-preview2`, oder `master` für die neueste aus dem Branch `master` („topaktuelle“ nächtliche Versionen)]

Der Standardwert ist `LTS`. Weitere Informationen zu .NET-Supportkanälen finden Sie unter dem Thema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support).

`-Version <VERSION>`

Stellt eine Buildversion auf dem Quellkanal dar (weitere Informationen finden Sie unter der Option `-Channel`). Mögliche Werte sind:

- `latest`: Neuester Build auf dem Kanal
- `coherent`: Neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination
- Dreiteilige Version im X.Y.Z-Format, das eine bestimmte Buildversion darstellt (z B. `1.0.x` mit `x`, das die Patchversion darstellt; oder ein bestimmter Build wie `2.0.0-preview2-006120`)

Falls nicht angegeben, verwendet `-Version` standardmäßig die erste [global.json-Datei](global-json.md), die den `version`-Member enthält. Wenn dies nicht vorhanden ist, verwendet `-Version` standardmäßig `latest`.

`-InstallDir <DIRECTORY>`

Gibt den Installationspfad an. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist *%LocalAppData%\.dotnet*. Beachten Sie, dass Binärdateien direkt im Verzeichnis platziert werden.

`-Architecture <ARCHITECTURE>`

Architektur der zu installierenden .NET Core-Binärdateien. Mögliche Werte sind `auto`, `x64` und `x86`. Der Standardwert ist `auto`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.

`-SharedRuntime`

Wenn festgelegt, beschränkt dieser Schalter die Installation auf die freigegebene Laufzeit. Das gesamte SDK ist nicht installiert.

`-DebugSymbols` (siehe HINWEIS)

Wenn festgelegt, umfasst das Installationsprogramm Debugsymbole in der Installation.

> [!NOTE]
> Der `-DebugSymbols`-Schalter ist derzeit nicht verfügbar, jedoch für eine zukünftige Version geplant.

`-DryRun`

Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann. Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

`-NoPath`

Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden. Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.

`-AzureFeed`

Gibt die URL für den Azure-Feed für den Installer an. Es wird nicht empfohlen, diesen Wert zu ändern. Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen.

### <a name="bash-macoslinux"></a>Bash (Mac OS/Linux)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

`-Channel <CHANNEL>`

Gibt den Quellkanal für die Installation an. Mögliche Werte sind:

- `Current`: Aktuelle Version
- `LTS`: Long Term Support-Kanal (aktuell unterstützte Versionen)
- Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`)
- Branchname [z.B. `release/2.0.0`, `release/2.0.0-preview2`, oder `master` für die neueste aus dem Branch `master` („topaktuelle“ nächtliche Versionen)]

Der Standardwert ist `LTS`. Weitere Informationen zu .NET-Supportkanälen finden Sie unter dem Thema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support).

`-Version <VERSION>`

Stellt eine Buildversion auf dem Quellkanal dar (weitere Informationen finden Sie unter der Option `-Channel`). Mögliche Werte sind:

- `latest`: Neuester Build auf dem Kanal
- `coherent`: Neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination
- Dreiteilige Version im X.Y.Z-Format, das eine bestimmte Buildversion darstellt (z B. `1.0.x` mit `x`, das die Patchversion darstellt, oder ein bestimmter Build wie `2.0.0-preview2-006120`)

Falls nicht angegeben, verwendet `-Version` standardmäßig die erste [global.json-Datei](global-json.md), die den `version`-Member enthält. Wenn dies nicht vorhanden ist, verwendet `-Version` standardmäßig `latest`.

`--install-dir <DIRECTORY>`

Gibt den Installationspfad an. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist `$HOME/.dotnet`.

`--architecture <ARCHITECTURE>`

Architektur der zu installierenden .NET Core-Binärdateien. Mögliche Werte sind `auto`, `x64` und `amd64`. Der Standardwert ist `auto`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.

`--shared-runtime`

Wenn festgelegt, beschränkt dieser Schalter die Installation auf die freigegebene Laufzeit. Das gesamte SDK ist nicht installiert.

`--debug-symbols`

Wenn festgelegt, umfasst das Installationsprogramm Debugsymbole in der Installation.

> [!NOTE]
> Dieser Schalter ist derzeit nicht verfügbar, jedoch für eine zukünftige Version geplant.

`--dry-run`

Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann. Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

`--no-path`

Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden. Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.

`--verbose`

Diagnoseinformationen anzeigen.

`--azure-feed`

Gibt die URL für den Azure-Feed für den Installer an. Es wird nicht empfohlen, diesen Wert zu ändern. Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.

`--help`

Druckt Hilfe für das Skript aus.

## <a name="examples"></a>Beispiele

Installieren Sie die neueste Entwicklungsversion am Standardspeicherort:

Windows:

`./dotnet-install.ps1 -Channel Future`

Mac OS/Linux:

`./dotnet-install.sh --channel Future`

Installieren Sie die aktuelle Preview am angegebenen Speicherort:

Windows:

`./dotnet-install.ps1 -Channel preview -InstallDir C:\cli`

Mac OS/Linux:

`./dotnet-install.sh --channel preview --install-dir ~/cli`

## <a name="see-also"></a>Siehe auch

[.NET Core-Versionen](https://github.com/dotnet/core/releases)   
[Downloadarchiv von .NET Core Runtime und des SDK](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)

