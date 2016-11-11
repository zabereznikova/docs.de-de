---
title: "Erforderliche Komponenten für .NET Core"
description: "Erforderliche Komponenten für .NET Core"
keywords: .NET, .NET Core
author: billwagner
manager: wpickett
ms.date: 09/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: 130b94a745b0e3222e205d8af26194239130ec9c
ms.openlocfilehash: 04018ec65272745ef98a2a96eb30009bcf44cb2e

---

# <a name="prerequisites-for-windows-development"></a>Erforderliche Komponenten für die Windows-Entwicklung

Für die .NET Core-Entwicklung unter Windows mit Visual Studio benötigen Sie Folgendes:

* Eine unterstützte Version eines Windows-Clients oder eines Windows-Betriebssystems
* Visual Studio 2015 Update 3.3 oder höher
* NuGet Manager-Erweiterung für Visual Studio
* .NET Core Tools Preview 2

## <a name="supported-windows-versions"></a>Unterstützte Windows-Versionen

.NET Core wird von den folgenden Versionen von Windows unterstützt:

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)

Eine umfassende Liste mit [unterstützten Betriebssystemen](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) finden Sie in den [Versionshinweisen zu .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

Wenn .NET Core unter Windows ausgeführt wird, muss VC++ Redistributable verwendet werden. Diese Komponente wird vom .NET Core-Installationsprogramm installiert. Visual C++ Redistributable muss manuell installiert werden, wenn .NET Core mittels Installationsprogrammskript (`dotnet-install.ps1`) installiert wird. 

Die Visual C++ Redistributable-Versionen sind je nach Windows-Version unterschiedlich.

* Windows 10
    * [Visual C++ Redistributable für Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145)
* Windows 7+ (nicht Windows 10)
    * Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/en-us/kb/2533623) enthält.
    * [Universal CRT Update](https://www.microsoft.com/en-us/download/details.aspx?id=48234) (weitere Informationen zu Universal CRT finden Sie in [diesem Blogbeitrag](https://blogs.msdn.microsoft.com/vcblog/2015/03/03/introducing-the-universal-crt/))

## <a name="visual-studio"></a>Visual Studio

Zum Entwickeln von .NET Core-Anwendungen benötigen Sie Visual Studio 2015. [Visual Studio Community 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs) können Sie kostenlos herunterladen. 

Stellen Sie sicher, dass Sie mit [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx) arbeiten:

* Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
* Im Dialogfeld **Info zu Microsoft Visual Studio** muss 14.0.25424.00 oder höher als Versionsnummer und „Update 3“ angezeigt werden.
* Wenn Update 3 nicht angezeigt wird, müssen Sie zunächst [Visual Studio 2015 Update 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs) herunterladen und installieren.
* Wenn Update 3 jedoch eine Versionsnummer kleiner als 14.0.25424.00 angezeigt wird, müssen Sie [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx) herunterladen und installieren.

Informationen zu den Änderungen in Update 3 finden Sie in den [Versionshinweisen](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

## <a name="nuget-manager-extension-for-visual-studio"></a>NuGet Manager-Erweiterung für Visual Studio

NuGet ist der Paket-Manager für die Microsoft-Entwicklungsplattform mit .NET Core. Sie benötigen [NuGet 3.5.0](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) oder höher, um .NET Core-Anwendungen zu erstellen.

## <a name="net-core-tools-for-visual-studio-2015"></a>.NET Core-Tools für Visual Studio 2015

Laden Sie das [.NET Core 1.0.1 – VS 2015 Tooling Preview 2][SDK] herunter, und installieren Sie es. 

Vom .NET Core Tooling-Paket werden .NET Core, Projektvorlagen und andere Tools für Visual Studio 2015 installiert.

> [!NOTE]
Derzeit ist es nicht möglich, ein Offline-Installationsprogramm für das [.NET Core 1.0.1 – VS 2015 Tooling Preview 2][SDK] herunterzuladen. Daher müssen Sie das [reguläre Bootstrapper][SDK] herunterladen, und mit einer Befehlszeilenoption (wie `/layout c:\path`) ausführen, um das Offlinelayout anzuzeigen. Danach können Sie ein Offline-Installationsprogramm verwenden: Führen Sie dazu einfach die ausführbare Datei in einem lokalen Pfad aus. Da es sich um ein vollständiges Layout handelt, werden alle Pakete für alle unterstützten Sprachen heruntergeladen. Daher beträgt die Größe etwa 1 GB.

[SDK]: https://go.microsoft.com/fwlink/?LinkID=827546



<!--HONumber=Nov16_HO1-->


