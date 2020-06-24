---
title: Installieren von .NET Core-Runtime unter Windows, Linux und macOS (.NET Core)
description: Erfahren Sie. wie Sie .NET Core unter Windows, Linux und macOS installieren. Entdecken Sie die erforderlichen Abhängigkeiten, die für die Ausführung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: c079e1856cdd370a278efc6fdfb4953059b6f2ba
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596292"
---
# <a name="install-the-net-core-runtime"></a>Installieren der .NET Core-Runtime

In diesem Artikel erfahren Sie, wie Sie die .NET Core-Runtime herunterladen und installieren. Die .NET Core-Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Installieren mit einem Installer

Windows verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:

- [x64-CPUs (64 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86-CPUs (32 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Installieren mit einem Installer

macOS verfügt über eigenständige Installer, die zur Installation der .NET Core-Runtime 3.1 verwendet werden können:

- [x64-CPUs (64 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Herunterladen und manuelles Installieren

Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie die Runtime herunterladen und manuell installieren.

[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu installieren und die Verwendung von .NET Core-CLI-Befehle im Terminal zu ermöglichen. Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus. Bei diesen Befehlen wird dabei ausgegangen, dass die Runtime in die `~/Downloads/dotnet-runtime.pkg`-Datei heruntergeladen wurde.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a>Installation unter Linux

Dieser Artikel wird bald entfernt. Er wird derzeit durch [Installieren von .NET Core unter Linux](linux.md) ersetzt.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Installieren mit PowerShell-Automatisierung

Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1. Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen. Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren. Andernfalls installiert das Skript das [SDK](sdk.md) nicht.

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert. Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.

## <a name="download-and-manually-install"></a>Herunterladen und manuelles Installieren

[Laden Sie zunächst ein .NET Core-Binärrelease herunter](#all-net-core-downloads), um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen. Erstellen Sie dann ein Installationsverzeichnis wie z. B. `%USERPROFILE%\dotnet`. Extrahieren Sie schließlich die heruntergeladene ZIP-Datei in dieses Verzeichnis.

Standardmäßig nutzen die Befehle und Anwendungen der .NET Core CLI auf diese Weise installiertes .NET Core nicht. Sie müssen sich explizit dafür entscheiden, es zu nutzen. Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.

Selbst wenn diese Umgebungsvariablen festgelegt sind, berücksichtigt .NET Core bei der Auswahl des besten Frameworks für die Ausführung der Anwendung nach wie vor den standardmäßigen globalen Installationsspeicherort. Der Standardwert ist normalerweise `C:\Program Files\dotnet`, den die Installationsprogramme verwenden. Sie können die Runtime anweisen, nur den benutzerdefinierten Installationsspeicherort zu verwenden, indem Sie diese Umgebungsvariable festlegen:

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Installieren mit Bash-Automatisierung

Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1. Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen. Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren. Andernfalls installiert das Skript das [SDK](sdk.md) nicht.

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert. Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.

::: zone-end

## <a name="all-net-core-downloads"></a>Alle .NET Core-Downloads

Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:

- [Downloads von .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Downloads von .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren. Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.

.NET Core kann in einem Docker-Container ausgeführt werden. Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar. Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.

Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind. So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.

Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md)
