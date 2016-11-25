---
title: Erforderliche .NET Core-Komponenten (Tools in Preview 3)
description: Erforderliche .NET Core-Komponenten (Tools in Preview 3)
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
ms.sourcegitcommit: 07b62bd7163193eff8dc8f61fda7a45a924bba2b
ms.openlocfilehash: ee4ccba7c06f0a7f67e3fe59c885febf895235fd

---

# <a name="prerequisites-for-windows-development-preview-3-tooling"></a>Für die Windows-Entwicklung erforderliche Komponenten (Tools in Preview 3)

Für die .NET Core-Entwicklung unter Windows mit Visual Studio benötigen Sie Folgendes:

* Eine unterstützte Version eines Windows-Clients oder eines Windows-Betriebssystems
* Visual Studio 2017 RC oder höher
* .NET Core-Tools Preview 3

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

Mithilfe der .NET Core-Befehlszeilentools können Sie .NET Core-Apps in einem beliebigen Editor erstellen. Wenn Sie jedoch Visual Studio oder die Preview 3-Version der .NET Core-Tools nutzen möchten, benötigen Sie Visual Studio 2017 RC oder höher. [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/) können Sie kostenlos herunterladen. 

Stellen Sie sicher, dass Sie mit Visual Studio 2017 RC arbeiten:

* Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
* Im Dialogfeld **Info zu Microsoft Visual Studio** muss 15.0.25831.1 oder höher als Versionsnummer angezeigt werden.

Informationen zu den Änderungen in Visual Studio 2017 RC finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

Stellen Sie sicher, dass Sie „NET Core und Docker (Preview)“ während des Setups installiert haben. Falls nicht, können Sie das Setup erneut ausführen und dies nachholen.



<!--HONumber=Nov16_HO3-->


