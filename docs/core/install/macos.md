---
title: Installieren von .NET Core unter macOS
description: Informationen zu den macOS-Versionen, unter denen Sie .NET Core installieren können
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 951e9b6a64d55274729e233b4a2d7728c75d05d4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302931"
---
# <a name="install-net-core-on-macos"></a>Installieren von .NET Core unter macOS

> [!div class="op_single_selector"]
>
> - [Installieren unter Windows](windows.md)
> - [Installieren unter macOS](macos.md)
> - [Installieren unter Linux](linux.md)

In diesem Artikel wird erläutert, wie Sie .NET Core unter macOS installieren. .NET Core besteht aus der Runtime und dem SDK. Die Runtime wird zum Ausführen von .NET Core-Apps verwendet und ist möglicherweise bereits in der App enthalten. Dies ist allerdings keine Voraussetzung. Das SDK wird zum Erstellen von .NET Core-Apps und -Bibliotheken verwendet. Die .NET Core-Runtime wird immer mit dem SDK installiert.

Version 3.1 ist die aktuelle Version von .NET Core.

> [!div class="button"]
> [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Unterstützte Versionen

Die folgende Tabelle enthält die derzeit unterstützten .NET Core-Releases und die macOS-Versionen, die diese unterstützen. Diese Versionen werden so lange unterstützt, bis die Version von [.NET Core das Ende des Supports erreicht](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- ✔️ gibt an, dass die Version von .NET Core weiterhin unterstützt wird.
- ❌ gibt an, dass die Version von .NET Core nicht unterstützt wird.

| Betriebssystem          | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview |
|---------------------------|---------------|---------------|----------------|
| macOS 10.15 Catalina    | ✔️ 2.1 ([Versionshinweise][release-notes-21]) | ✔️ 3.1 ([Versionshinweise][release-notes-31]) | ✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50]) |
| macOS 10.14 Mojave      | ✔️ 2.1 ([Versionshinweise][release-notes-21]) | ✔️ 3.1 ([Versionshinweise][release-notes-31]) | ✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50]) |
| macOS 10.13 High Sierra | ✔️ 2.1 ([Versionshinweise][release-notes-21]) | ✔️ 3.1 ([Versionshinweise][release-notes-31]) | ✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50]) |
| macOS 10.12 „Sierra“      | ✔️ 2.1 ([Versionshinweise][release-notes-21]) | ❌ 3.1 ([Versionshinweise][release-notes-31]) | ❌ Vorschauversion 5.0. ([Versionshinweise][release-notes-50]) |

## <a name="unsupported-releases"></a>Nicht unterstützte Versionen

Die folgenden Versionen von .NET Core werden ❌ nicht mehr unterstützt. Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0 ([Versionshinweise][release-notes-30])
- 2.2 ([Versionshinweise][release-notes-22])
- 2.0 ([Versionshinweise][release-notes-20])

## <a name="runtime-information"></a>Informationen zur Runtime

Die Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet. Wenn ein App-Autor eine App veröffentlicht, kann er die Runtime zusammen mit seiner App bereitstellen. Wenn er die Runtime nicht hinzufügt, ist es dem Benutzer überlassen, die Runtime zu installieren.

Es gibt drei verschiedene Runtimes, die Sie unter macOS installieren können:

*ASP.NET Core-Runtime*\
Diese führt ASP.NET Core-Apps aus. Sie umfasst die .NET Core-Runtime.

*.NET Core-Runtime*\
Hierbei handelt es sich um die einfachste Runtime, die keine weiteren Runtimes beinhaltet. Es wird dringend empfohlen, dass Sie die *ASP.NET Core-Runtime* installieren, um die bestmögliche Kompatibilität mit .NET Core-Apps zu erzielen.

> [!div class="button"]
> [.NET Core-Runtime herunterladen](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Informationen zum SDK

Das SDK wird zum Erstellen und Veröffentlichen von .NET Core-Apps und -Bibliotheken verwendet. Die Installation des SDK umfasst beide [Runtimes](#runtime-information): ASP.NET Core und .NET Core.

> [!div class="button"]
> [.NET Core SDK herunterladen](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>Abhängigkeiten

.NET Core wird von den folgenden macOS-Versionen unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| .NET Core-Version | macOS                 | Architekturen |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13 oder höher)  | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13 oder höher)  | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 oder höher)       | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 oder höher)       | x64 | [Weitere Informationen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird. Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.

Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert. Vorherige Versionen wurden nicht notarisiert. Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.

Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS. Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a>Installieren mit einem Installer

macOS verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:

- [x64-CPUs (64 Bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Herunterladen und manuelles Installieren

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie das SDK und die Runtime herunterladen und manuell installieren. Die manuelle Installation wird normalerweise im Rahmen von CI-Tests (Continuous Integration) durchgeführt. Für Entwickler oder Benutzer eignet sich in der Regel die Verwendung eines [Installationsprogramms](https://dotnet.microsoft.com/download/dotnet-core) besser.

Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:

- ✔️ [.NET 5.0 Preview herunterladen](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Alle .NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core)

Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von . NET Core verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET Core in PATH befindet.

Laden Sie zunächst eine binäre .NET Core-Version herunter, um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen. Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde. Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.

**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.
>
> Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen. Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen. Zum Beispiel:
>
> - **Bash-Shell**: *~/.bash_profile*, *~/.bashrc*
> - **Korn-Shell**: *~/.kshrc* oder *.profile*
> - **Z-Shell**: *~/.kshrc* oder *.profile*
>
> Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu. Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.
>
> Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.

Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.

## <a name="install-with-visual-studio-for-mac"></a>Installieren mit Visual Studio für Mac

Visual Studio für Mac installiert das .NET Core SDK, wenn die **.NET Core-Workload** ausgewählt wird. Informationen zu den ersten Schritten mit der .NET Core-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation). Für die neueste Version .NET Core 3.1 müssen Sie die Vorschauversion von Visual Studio für Mac 8.4 verwenden.

[![macOS-Feature für Visual Studio 2019 für Mac mit .NET Core-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Installieren zusammen mit Visual Studio Code

Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird. Visual Studio Code ist für Windows, macOS und Linux verfügbar.

Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.

01. [Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)
01. [Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)
01. [Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

## <a name="install-with-bash-automation"></a>Installieren mit Bash-Automatisierung

Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1. Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen. Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren. Andernfalls installiert das Skript das [SDK](sdk.md) nicht.

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert. Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.

## <a name="docker"></a>Docker

Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren. Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.

.NET Core kann in einem Docker-Container ausgeführt werden. Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar. Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.

Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind. So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.

Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md?pivots=os-macos)
- [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md)
- [Tutorial: Erste Schritte unter macOS](../tutorials/with-visual-studio-mac.md)
- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
