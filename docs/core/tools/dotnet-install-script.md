---
title: Dotnet-Installationsskripts
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
keywords: Dotnet-Installation, Dotnet-Installationsskripts, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.translationtype: HT
ms.sourcegitcommit: b041fbec3ff22157d00af2447e76a7ce242007fc
ms.openlocfilehash: 2f15f37016fe824d76b501e4793e0b28bbdbe167
ms.contentlocale: de-de
ms.lasthandoff: 09/14/2017

---

# <a name="dotnet-install-scripts-reference"></a>Dotnet-Installationsskripts Verweis

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: Skript, mit dem die .NET Core-CLI-Tools und die freigegebene Laufzeit installiert werden.

## <a name="synopsis"></a>Übersicht

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

Mac OS/Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a>Beschreibung

Die `dotnet-install`-Skripts werden verwendet, um eine Nicht-Administrator-Installation des .NET Core-SDK durchzuführen, die die .NET Core-CLI-Tools und die freigegebene Laufzeit enthält.

Sie sollten die stabile Version verwenden, die auf der [.NET Core-Hauptwebsite](https://dot.net) gehostet wird. Die direkten Pfade zu den Skripts sind:

* https://dot.net/v1/dotnet-install.sh (bash, UNIX)
* https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)

Diese Skripts sind vor allem in Szenarios für die Automatisierung und Nicht-Administrator-Installationen nützlich. Es gibt zwei Skripts: Das eine ist ein PowerShell-Skript, das unter Windows funktioniert. Das andere Skript ist ein Bash-Skript für Linux/macOS. Beide Skripts weisen das gleiche Verhalten auf. Das Bash-Skript liest auch PowerShell-Schalter, sodass Sie PowerShell-Schalter mit dem Skript auf Linux/macOS-Systemen verwenden können. 

Die Installationsskripts laden die ZIP/Tarball-Datei vom CLI-Build-Ablagespeicherort herunter und installieren sie entweder am Standardspeicherort oder an einem in `-InstallDir|--install-dir` angegebenen Speicherort. In der Standardeinstellung laden die Installationsskripts das SDK herunter und installieren es. Wenn Sie nur die freigegebene Laufzeit abrufen möchten, geben Sie das `--shared-runtime`-Argument an. 

In der Standardeinstellung fügt das Skript den Installationsort dem $PATH für die aktuelle Sitzung hinzu. Überschreiben Sie dieses Standardverhalten, indem sie das `--no-path`-Argument angeben. 

Bevor Sie das Skript ausführen, installieren Sie die erforderlichen [Abhängigkeiten](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).

Installieren Sie eine bestimmte Version mithilfe des Arguments `--version`. Die Version muss als dreiteilige Version (z.B. 1.0.0-13232) angegeben werden. Wenn nicht angegeben, wird die `latest`-Version verwendet.

## <a name="options"></a>Optionen

`-Channel <CHANNEL>`

Gibt den Quellkanal für die Installation an. Mögliche Werte sind:

- `Current`: Aktuelle Version
- `LTS`: Long Term Support-Kanal (aktuell unterstützte Versionen)
- Zweiteilige Version im X.Y-Format, das eine bestimmte Version darstellt (z.B. `2.0` oder `1.0`)
- Branchname [z.B. `release/2.0.0`, `release/2.0.0-preview2`, oder `master` für die neueste aus dem Branch `master` („topaktuelle“ nächtliche Versionen)]

Der Standardwert ist `LTS`. Weitere Informationen zu .NET-Supportkanälen finden Sie unter dem Thema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support).

`-Version <VERSION>`

Stellt eine bestimmte Buildversion dar. Mögliche Werte sind:

- `latest` – der neueste Build auf dem Kanal (mit der `-Channel`-Option verwendet)
- `coherent` – neuester kohärenter Build auf dem Kanal; verwendet die neueste stabile Paketkombination (mit Branch-Name-`-Channel`-Optionen verwendet)
- Dreiteilige Version im X.Y.Z-Format, die eine bestimmte Buildversion darstellt; sie hat Vorrang vor der `-Channel`-Option. Beispiel: `2.0.0-preview2-006120`

Wenn kein Wert angegeben ist, hat `-Version` den Standardwert `latest`.

`-InstallDir <DIRECTORY>`

Gibt den Installationspfad an. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist *%LocalAppData%\.dotnet*. Beachten Sie, dass Binärdateien direkt im Verzeichnis platziert werden.

`-Architecture <ARCHITECTURE>`

Architektur der zu installierenden .NET Core-Binärdateien. Mögliche Werte sind `auto`, `x64` und `x86`. Der Standardwert ist `auto`, was die derzeit ausgeführte Betriebssystemarchitektur darstellt.

`-SharedRuntime`

Wenn festgelegt, beschränkt dieser Schalter die Installation auf die freigegebene Laufzeit. Das gesamte SDK ist nicht installiert.

`-DryRun`

Wenn festgelegt, führt das Skript die Installation nicht aus. Es zeigt stattdessen an, welche Befehlszeile verwendet werden soll, um die derzeit erforderliche Version der .NET Core-CLI konsistent zu installieren. Wenn Sie z.B. Version `latest` angeben, wird eine Verbindung mit der bestimmten Version angezeigt, damit dieser Befehl deterministisch in einem Buildskript verwendet werden kann. Außerdem wird der Speicherort der Binärdatei angezeigt, wenn Sie sie selbst installieren oder herunterladen möchten.

`-NoPath`

Falls festgelegt, wird das Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden. Standardmäßig wird das Skript den PFAD ändern. Somit werden die CLI-Tools sofort nach der Installation zur Verfügung gestellt.

`-AzureFeed`

Gibt die URL für den Azure-Feed für den Installer an. Es wird nicht empfohlen, diesen Wert zu ändern. Die Standardeinstellung ist `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Wenn festgelegt, verwendet das Installationsprogramm den Proxy bei der Durchführung von Webanfragen. (Nur gültig für Windows)

`--verbose`

Diagnoseinformationen anzeigen.

`--help`

Druckt Hilfe für das Skript aus.

## <a name="examples"></a>Beispiele

Installieren Sie die neueste langfristig unterstützte (Long-Term Supported, LTS) Version am Standardspeicherort:

Windows:

`./dotnet-install.ps1 -Channel LTS`

Mac OS/Linux:

`./dotnet-install.sh --channel LTS`

Installieren Sie die aktuelle Version von Kanal 2.0 am angegebenen Speicherort:

Windows:

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

Mac OS/Linux:

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

Installieren Sie die Version 1.1.0 der freigegebenen Laufzeit:

Windows:

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

Mac OS/Linux:

`./dotnet-install.sh --shared-runtime --version 1.1.0`

Rufen Sie das Skript ab, und installieren Sie die Beispiele für die .NET Core-CLI:

Windows:

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

Mac OS/Linux:

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a>Siehe auch

[.NET Core-Versionen](https://github.com/dotnet/core/releases)   
[Downloadarchiv von .NET Core Runtime und des SDK](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)

