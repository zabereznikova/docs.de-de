---
title: Installieren von .NET unter Windows
description: In diesem Artikel erhalten Sie Informationen zu den Windows-Versionen, unter denen Sie .NET installieren können.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b5c0949bbd591906536094a33d8583a265d8a4c8
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110233"
---
# <a name="install-net-on-windows"></a>Installieren von .NET unter Windows

> [!div class="op_single_selector"]
>
> - [Installieren unter Windows](windows.md)
> - [Installieren unter macOS](macos.md)
> - [Installieren unter Linux](linux.md)

In diesem Artikel wird erläutert, wie Sie .NET unter Windows installieren. .NET besteht aus der Runtime und dem SDK. Die Runtime wird zum Ausführen von .NET-Apps verwendet und ist möglicherweise bereits in der App enthalten. Das SDK wird zum Erstellen von .NET-Apps und -Bibliotheken verwendet. Die .NET-Runtime wird immer mit dem SDK installiert.

Version 5.0 ist die aktuelle Version von .NET.

> [!div class="button"]
> [Herunterladen von .NET](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Unterstützte Versionen

Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die Windows-Versionen, die diese unterstützen. Diese Versionen werden so lange unterstützt, bis entweder die Version von [.NET das Ende des Supports](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) oder die Version von [Windows das Ende ihrer Lebensdauer](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) erreicht.

Die Enddaten für den Support der einzelnen Windows 10-Versionen sind nach Editionen unterteilt. In der folgenden Tabelle werden nur die Editionen **Home**, **Pro**, **Pro Education** und **Pro for Workstations** berücksichtigt. Weitere Details finden Sie im [Informationsblatt zum Lebenszyklus von Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

> [!TIP]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem            | .NET Core 2.1 | .NET Core 3.1 | .NET 5 |
|-----------------------------|---------------|---------------|--------|
| Windows 10, Version 20H2    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 2004    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1909    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1903    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1809    | ✔️           | ✔️            | ✔️    |
|  Windows 10, Version 1803    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1709    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1607    | ✔️           | ✔️            | ✔️    |
| Windows 8.1                 | ✔️           | ✔️            | ✔️    |
| Windows 7 SP1 [ESU][esu]    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1607    | ✔️           | ✔️            | ✔️    |
| Windows 10, Version 1607    | ✔️           | ✔️            | ✔️    |
| Windows Server 2012 R2      | ✔️           | ✔️            | ✔️    |
| Windows Server Core 2012 R2 | ✔️           | ✔️            | ✔️    |
| Nano Server, Version 1809+  | ✔️           | ✔️            | ✔️    |
| Nano Server, Version 1803   | ✔️           | ✔️            | ❌    |

## <a name="unsupported-releases"></a>Nicht unterstützte Versionen

Die folgenden Versionen von .NET werden nicht mehr unterstützt (❌). Die Downloads dafür bleiben weiterhin veröffentlicht:

- 3.0
- 2.2
- 2.0

## <a name="runtime-information"></a>Informationen zur Runtime

Die Runtime wird zur Ausführung der mit .NET erstellten Apps verwendet. Wenn ein App-Autor eine App veröffentlicht, kann er die Runtime zusammen mit seiner App bereitstellen. Wenn er die Runtime nicht hinzufügt, ist es dem Benutzer überlassen, die Runtime zu installieren.

Es gibt drei verschiedene Runtimes, die Sie unter Windows installieren können:

*ASP.NET Core-Runtime*\
Diese führt ASP.NET Core-Apps aus. Diese Runtime schließt die .NET-Runtime ein.

*Desktopruntime*\
Diese führt .NET-Desktop-Apps für Windows aus, die unter WPF oder Windows Forms erstellt wurden. Diese Runtime schließt die .NET-Runtime ein.

*.NET-Runtime*\
Hierbei handelt es sich um die einfachste Runtime, die keine weiteren Runtimes beinhaltet. Es wird dringend empfohlen, dass Sie sowohl die *ASP.NET Core-Runtime* als auch die *Desktop-Runtime* installieren, um die bestmögliche Kompatibilität mit .NET-Apps zu erzielen.

> [!div class="button"]
> [.NET-Runtime herunterladen](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Informationen zum SDK

Das SDK wird zum Erstellen und Veröffentlichen von .NET-Apps und -Bibliotheken verwendet. Die Installation des SDK umfasst alle drei [Runtimes](#runtime-information): ASP.NET Core, Desktop und .NET.

## <a name="dependencies"></a>Abhängigkeiten

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[.NET 5.0](#tab/net50)

Die folgenden Windows-Versionen werden von .NET 5.0 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                  | Version       | Architekturen   |
|---------------------|---------------|-----------------|
| Windows 10-Client   | Version 1607 oder höher | x64, x86, ARM64 |
| Windows-Client      | 7 SP1 oder höher, 8.1   | x64, x86        |
| Windows Server      | 2012 R2 oder höher      | x64, x86        |
| Windows Server Core | 2012 R2 oder höher      | x64, x86        |
| Nano Server         | Version 1809 und höher | x64             |

Weitere Informationen zu den von .NET 5.0 unterstützten Betriebssystemen, Distributionen und Lebenszyklusrichtlinien finden Sie unter [Von .NET 5.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md).

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Die folgenden Windows-Versionen werden von .NET Core 3.1 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2012 R2 oder höher                       | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64, ARM32      |

Weitere Informationen zu den von .NET Core 3.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3.0 wird aktuell ❌ nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Die folgenden Windows-Versionen werden von .NET Core 3.0 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2012 R2 oder höher                       | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64, ARM32      |

Weitere Informationen zu den von .NET Core 3.0 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 3.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2.2 wird aktuell ❌ nicht unterstützt. Weitere Informationen finden Sie in der [Supportrichtlinie für .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Die folgenden Windows-Versionen werden von .NET Core 2.2 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 oder höher                   | x64, x86        |
| Nano Server                   | Version 1803 oder höher                   | x64, ARM32      |

Weitere Informationen zu den von .NET Core 2.2 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Die folgenden Windows-Versionen werden von .NET Core 2.1 unterstützt:

> [!NOTE]
> Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.

| Betriebssystem                            | Version                        | Architekturen   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows-Client                | 7 SP1 oder höher, 8.1                    | x64, x86        |
| Windows 10-Client             | Version 1607 oder höher                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 oder höher                   | x64, x86        |
| Nano Server                   | Version 1803 oder höher                  | x64,            |

Weitere Informationen zu den von .NET Core 2.1 unterstützten Betriebssystemen, Verteilungen und Lebenszyklusrichtlinien finden Sie unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> Windows 7/Vista/8.1/Server 2008 R2/Server 2012 R2

Weitere Abhängigkeiten sind erforderlich, wenn Sie das .NET SDK oder die Runtime unter den folgenden Windows-Versionen installieren:

- Windows 7 SP1 [ESU][esu]
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

Installieren Sie Folgendes:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685)
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

Die oben aufgeführten Anforderungen sind auch erforderlich, wenn einer der folgenden Fehler auftritt:

> Das Programm kann nicht gestartet werden, da *api-ms-win-crt-runtime-l1-1-0.dll* auf dem Computer fehlt. Installieren Sie das Programm erneut, um das Problem zu beheben.
>
> \- oder -
>
> Das Programm kann nicht gestartet werden, da *api-ms-win-cor-timezone-l1-1-0.dll* auf dem Computer fehlt. Installieren Sie das Programm erneut, um das Problem zu beheben.
>
> \- oder -
>
> The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed. (Die Bibliothek „hostfxr.dll“ wurde gefunden, aber der Ladevorgang aus C:\<Pfad_zu_App>\hostfxr.dll ist fehlgeschlagen.)

## <a name="install-with-powershell-automation"></a>Installieren mit PowerShell-Automatisierung

Die [dotnet-install-Skripts](../tools/dotnet-install-script.md) werden für die CI-Automatisierung und Installationen der Runtime durch Benutzer ohne Administratorrechte verwendet. Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.

Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1. Sie können eine bestimmte Version durch Angeben der `Channel`-Option auswählen. Schließen Sie die `Runtime`-Option mit ein, um eine Runtime zu installieren. Andernfalls installiert das Skript das SDK nicht.

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

Installieren Sie das SDK, und lassen Sie dabei den Parameter `-Runtime` weg. Der Parameter `-Channel` wird in diesem Beispiel auf `Current` festgelegt, wodurch die neuste unterstützte Version installiert wird.

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a>Installieren mit Visual Studio

Für den Fall, dass Sie Visual Studio zum Entwickeln von .NET-Apps verwenden, finden Sie in der folgenden Tabelle basierend auf der .NET SDK-Zielversion die mindestens erforderliche Version von Visual Studio.

| .NET SDK-Version      | Visual Studio-Version                      |
| --------------------- | ------------------------------------------ |
| 5.0                   | Visual Studio 2019 Version 16.8 oder höher |
| 3.1                   | Visual Studio 2019 Version 16.4 oder höher |
| 3.0                   | Visual Studio 2019 Version 16.3 oder höher |
| 2.2                   | Visual Studio 2017 Version 15.9 oder höher |
| 2.1                   | Visual Studio 2017 Version 15.7 oder höher |

Wenn Sie Visual Studio bereits installiert haben, können Sie Ihre Version mit den folgenden Schritten überprüfen.

01. Öffnen Sie Visual Studio.
01. Klicken Sie auf **Hilfe** > **Info**.
01. Informieren Sie sich über die Versionsnummer im Dialogfeld **Info**.

Visual Studio kann das neueste .NET SDK und die Runtime installieren.

> [!div class="button"]
> [Visual Studio herunterladen](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Workload auswählen

Wählen Sie in Abhängigkeit vom Typ der von Ihnen erstellten Anwendung beim Installieren oder Ändern von Visual Studio mindestens eine der folgenden Workloads aus:

- Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**
- Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**
- **Azure-Entwicklungsworkload** im Abschnitt **Web und Cloud**
- **.NET-Desktopentwicklungsworkload** im Abschnitt **Desktop und mobil**

[![Windows Visual Studio 2019 mit .NET Core-Workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Installieren zusammen mit Visual Studio Code

Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird. Visual Studio Code ist für Windows, macOS und Linux verfügbar.

Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.

01. [Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)
01. [Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)
01. [Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

## <a name="windows-installer"></a>Windows Installer

Die [Downloadseite](https://dotnet.microsoft.com/download/dotnet-core) für .NET bietet ausführbare Windows Installer-Dateien.

Wenn Sie die MSI-Dateien für die Installation von .NET verwenden, können Sie den Installationspfad durch Einstellung der Parameter `DOTNETHOME_X64` und `DOTNETHOME_X86` anpassen:

```console
dotnet-sdk-3.1.301-win-x64.exe DOTNETHOME_X64="F:\dotnet\x64" DOTNETHOME_X86="F:\dotnet\x86"
```

## <a name="download-and-manually-install"></a>Herunterladen und manuelles Installieren

Alternativ zu den Windows-Installationsprogrammen für .NET können Sie das SDK oder die Runtime herunterladen und manuell installieren. Die manuelle Installation wird normalerweise im Rahmen von CI-Tests (Continuous Integration) durchgeführt. Für Entwickler oder Benutzer eignet sich in der Regel die Verwendung eines [Installationsprogramms](https://dotnet.microsoft.com/download/dotnet-core) besser.

Sowohl das .NET SDK als auch die .NET-Runtime können nach dem Herunterladen manuell installiert werden. Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren. Laden Sie zunächst eine binäre Version entweder für das SDK oder die Runtime von einer der folgenden Websites herunter:

- [.NET 5.0-Downloads](https://dotnet.microsoft.com/download/dotnet/5.0)
- [Downloads von .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Downloads von .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Alle .NET Core-Downloads](https://dotnet.microsoft.com/download/dotnet-core)

Erstellen Sie ein Verzeichnis, in das .NET extrahiert werden soll, z. B. `%USERPROFILE%\dotnet`. Extrahieren Sie anschließend die heruntergeladene ZIP-Datei in dieses Verzeichnis.

Standardmäßig nutzen die Befehle und Anwendungen der .NET-CLI auf diese Weise installierte .NET-Instanzen nicht. Sie müssen sich explizit dafür entscheiden, .NET zu nutzen. Ändern Sie hierzu die Umgebungsvariablen, mit denen eine Anwendung gestartet wird:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

Bei diesem Ansatz können Sie mehrere Versionen in separaten Speicherorten installieren und dann explizit auswählen, welcher Installationsspeicherort von einer Anwendung verwendet werden soll, indem die Anwendung mit Umgebungsvariablen ausgeführt wird, die auf diesen Speicherort zeigen.

Wenn `DOTNET_MULTILEVEL_LOOKUP` auf `0` festgelegt ist, ignoriert .NET alle global installierten .NET-Versionen. Entfernen Sie diese Umgebungseinstellung, damit .NET den globalen Standartinstallationsspeicherort bei der Auswahl des besten Frameworks zum Ausführen der Anwendung berücksichtigt. Das Standardverzeichnis ist in der Regel `C:\Program Files\dotnet`. Dort wird .NET von den Installationsprogrammen installiert.

## <a name="docker"></a>Docker

Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren. Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.

.NET kann in einem Docker-Container ausgeführt werden. Offizielle Docker-Images für .NET werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet) verfügbar. Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.

Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind. So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.

Weitere Informationen zur Verwendung von .NET in einem Docker-Container finden Sie unter [Einführung zu .NET und Docker](../docker/introduction.md) und [Docker-Beispiele für .NET](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md?pivots=os-windows)
- [Tutorial: Hallo Welt-Tutorial](../tutorials/with-visual-studio.md)
- [Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)
- [Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)

[esu]: /troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq
