---
title: 'Installieren des .NET Core SDK unter Windows, Linux und macOS: .NET Core'
description: Hier erfahren Sie, wie Sie .NET Core unter Windows, Linux und macOS installieren. Informieren Sie sich über die erforderlichen Abhängigkeiten, die für die Entwicklung von .NET Core-Apps benötigt werden.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999062"
---
# <a name="install-the-net-core-sdk"></a>Installieren des .NET Core SDK

In diesem Artikel wird erläutert, wie Sie das .NET Core SDK installieren. Das .NET Core SDK wird zum Erstellen von .NET Core-Apps und -Bibliotheken verwendet. Die .NET Core-Runtime wird immer mit dem SDK installiert.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Installieren mit einem Installer

Windows verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:

- [x64-CPUs (64 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86-CPUs (32 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Installieren mit einem Installer

macOS verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:

- [x64-CPUs (64 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Installieren mit dem Paket-Manager

Sie können das .NET Core SDK mit vielen der allgemeinen Linux-Paket-Manager installieren. Weitere Informationen finden Sie unter [Linux-Paket-Manager: Installieren von .NET Core](linux-package-managers.md).

## <a name="download-and-manually-install"></a>Herunterladen und manuelles Installieren

[Laden Sie zunächst eine .NET Core-Binärversion herunter](#all-net-core-downloads), um das SDK zu extrahieren und die Befehle am Terminal verfügbar zu machen. Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle aus.

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Mit den obigen Befehlen werden nur die .NET SDK-Befehle für die Terminalsitzung verfügbar gemacht, in der die Befehle ausgeführt werden.
>
> Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen. Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen. Beispiel:
>
> - **Bash-Shell**: *~/.bash_profile*, *~/.bashrc*
> - **Korn-Shell**: *~/.kshrc* oder *.profile*
> - **Z-Shell**: *~/.kshrc* oder *.profile*
> 
> Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu. Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.
>
> Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>Installieren mit Visual Studio

Für den Fall, dass Sie Visual Studio zum Entwickeln von .NET Core-Apps verwenden, finden Sie in der folgenden Tabelle basierend auf der .NET Core SDK-Zielversion die mindestens erforderliche Version von Visual Studio.

| .NET Core SDK-Version | Visual Studio-Version                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 Version 16.4 oder höher |
| 3.0                   | Visual Studio 2019 Version 16.3 oder höher |
| 2.2                   | Visual Studio 2017 Version 15.9 oder höher |
| 2.1                   | Visual Studio 2017 Version 15.7 oder höher |

Wenn Sie Visual Studio bereits installiert haben, können Sie Ihre Version mit den folgenden Schritten überprüfen.

01. Öffnen Sie Visual Studio.
01. Klicken Sie auf **Hilfe** > **Info**.
01. Informieren Sie sich über die Versionsnummer im Dialogfeld **Info**.

Visual Studio kann das neueste .NET Core SDK und die Runtime installieren.

- [Laden Sie Visual Studio herunter](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Workload auswählen

Wählen Sie in Abhängigkeit vom Typ der von Ihnen erstellten Anwendung beim Installieren oder Ändern von Visual Studio eine der folgenden Workloads aus:

- Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**
- Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**
- **Azure-Entwicklungsworkload** im Abschnitt **Web und Cloud**
- **.NET-Desktopentwicklungsworkload** im Abschnitt **Desktop und mobil**

[![Windows Visual Studio 2019 mit .NET Core-Workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Installieren mit Visual Studio für Mac

Visual Studio für Mac installiert das .NET Core SDK, wenn die **.NET Core-Workload** ausgewählt wird. Informationen zu den ersten Schritten mit der .NET Core-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation). Für die neueste Version .NET Core 3.1 müssen Sie die Vorschauversion von Visual Studio für Mac 8.4 verwenden.

[![macOS-Feature für Visual Studio 2019 für Mac mit .NET Core-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>Installieren zusammen mit Visual Studio Code

Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird. Visual Studio Code ist für Windows, macOS und Linux verfügbar.

Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.

01. [Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)
01. [Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)
01. [Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Installieren mit PowerShell-Automatisierung

Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste Version von [LTS (long term support)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), die derzeit .NET Core 2.1 entspricht. Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Installieren mit Bash-Automatisierung

Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen des SDK von Benutzern ohne Administratorrechte verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste Version von [LTS (long term support)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), die derzeit .NET Core 2.1 entspricht. Führen Sie das Skript mit der folgenden Option aus, um die aktuelle Version von .NET Core zu installieren:

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>Alle .NET Core-Downloads

Sie können .NET Core direkt mit einem der folgenden Links herunterladen und installieren:

- [Downloads von .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Downloads von .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [Downloads von .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [Downloads von .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren. Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.

.NET Core kann in einem Docker-Container ausgeführt werden. Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar. Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.

Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind. So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.

Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Nächste Schritte

::: zone pivot="os-windows"

- [Tutorial: C#-Tutorial „Hallo Welt“](../tutorials/with-visual-studio.md)
- [Tutorial: Visual Basic-Tutorial „Hallo Welt“](../tutorials/vb-with-visual-studio.md)
- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)

::: zone-end

::: zone pivot="os-macos"

- [Tutorial: Erste Schritte unter macOS](../tutorials/using-on-mac-vs.md)
- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)

::: zone-end

::: zone pivot="os-linux"

- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)

::: zone-end
