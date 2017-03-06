---
title: dotnet-Installationsskripts | Microsoft-Dokumentation
description: Informationen zu Dotnet-Installationsskripts zur Installation von .NET Core CLI-Tools und freigegebener Laufzeit.
keywords: Dotnet-Installation, Dotnet-Installationsskripts, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 0063ac1220a1f01eef6e7300b0907518863ee01e

---

#<a name="dotnet-install-scripts-reference-net-core-tools-rc4"></a>dotnet-install-Skriptsreferenz (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Das Thema [dotnet-Installationsskriptverweis](../../tools/dotnet-install-script.md) gilt für .NET Core Preview 2-Tools.

## <a name="name"></a>Name
dotnet-install.ps1 | dotnet-install.sh - Skript, mit dem die Befehlszeilenschnittstellen-Tools (CLI) und die freigegebene Laufzeit installiert werden

## <a name="synopsis"></a>Übersicht
Windows:

`dotnet-install.ps1 [-Channel] [-Version]
    [-InstallDir] [-Debug] [-NoPath] 
    [-SharedRuntime]`

Mac OS/Linux:

`dotnet-install.sh [--channel] [--version]
    [--install-dir] [--debug] [--no-path] 
    [--shared-runtime]`

## <a name="description"></a>Beschreibung
Die `dotnet-install` Skripts werden verwendet, um ohne Administratorrechte eine Installation der CLI-Toolkette und der freigegebenen Laufzeit auszuführen. Sie können die Skripts aus der [CLI-GitHub-Repository](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/scripts/obtain) herunterladen. 

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

Welche Version von CLI installiert wird. Sie müssen die Version als dreiteilige Version (z.B. 1.0.0-13232) angeben. Wenn nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die die Eigenschaft `version` enthält. Wenn diese nicht vorhanden ist, wird die neueste verwendet.     

`-InstallDir [DIR]`

Der Pfad für die Installation. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist *%LocalAppData%\.dotnet*.

`-Debug`

`true` gibt an, dass größere Pakete mit Debugsymbolen verwendet werden sollen, andernfalls `false`. Der Standardwert ist `false`.

`-NoPath`

`true` gibt an, dass Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden, andernfalls `false`. Der Standardwert ist `false`, d.h. der PFAD wird geändert. Dadurch werden die CLI-Tools sofort nach der Installation verfügbar. 

`-SharedRuntime`

`true` für die Installation nur der freigegebenen Laufzeitbestandteile; `false` für die Installation des gesamten SDK. Der Standardwert ist `false`.

### <a name="bash-macoslinux"></a>Bash (Mac OS/Linux)
`--channel [CHANNEL]`

Der Kanal (z.B. „zukünftig“, „Preview“, „Produktion“), aus dem installiert wird. Der Standardwert ist „Produktion“.

`--version [VERSION]`

Welche Version von CLI installiert wird. Sie müssen die Version als dreiteilige Version (z.B. 1.0.0-13232) angeben. Wenn nicht angegeben, wird standardmäßig die erste [global.json](global-json.md)-Datei verwendet, die die Eigenschaft `version` enthält. Wenn diese nicht vorhanden ist, wird die neueste verwendet.     

`--install-dir [DIR]`

Pfad zum Installationsort. Das Verzeichnis wird erstellt, wenn es nicht vorhanden ist. Der Standardwert ist `$HOME/.dotnet`.

`--debug`

`true` gibt an, dass größere Pakete mit Debugsymbolen verwendet werden sollen, andernfalls `false`. Der Standardwert ist `false`.

`--no-path`

`true` gibt an, dass Präfix/Installdir für die aktuelle Sitzung nicht in den Pfad exportiert werden, andernfalls `false`. Der Standardwert ist `false`, d.h. der PFAD wird geändert. Dadurch werden die CLI-Tools sofort nach der Installation verfügbar.  

`--shared-runtime`

`true` für die Installation nur der freigegebenen Laufzeitbestandteile; `false` für die Installation des gesamten SDK. Der Standardwert ist `false`.

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



<!--HONumber=Feb17_HO2-->


