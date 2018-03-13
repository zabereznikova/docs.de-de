---
title: "Voraussetzungen für .NET Core unter Windows"
description: "Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können."
author: JRAlexander
ms.author: johalex
ms.date: 03/02/2018
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 48102f3fb7fa6e93238eefff0e7f1ecbed4d8409
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a>Voraussetzungen für .NET Core unter Windows

Dieser Artikel erläutert die notwendigen Abhängigkeiten zum Entwickeln von .NET Core-Anwendungen unter Windows. Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:

* [Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>Von .NET Core unterstützte Windows-Versionen

.NET Core wird von folgenden Versionen unterstützt:

* Windows 7 SP1
* Windows 8.1
* Windows 10 Anniversary Update (Version 1607) oder höhere Versionen
* Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 R2 (vollständiger Server oder Serverkern)
* Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)

Eine umfassende Liste mit von .NET Core 2.x unterstützten Betriebssystemen finden Sie unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

Eine umfassende Liste mit von .NET Core 1.x unterstützten Betriebssystemen finden Sie unter [.NET Core 1.x Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md).

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

.NET Core 1.1 und frühere Versionen benötigen Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016. Diese Abhängigkeit wird automatisch durch das .NET Core-Installationsprogramm installiert.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:

* Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).
* Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.
* Beim Erstellen des Produkt aus der Quelle.
* Beim Installieren von .NET Core über eine *ZIP*-Datei. Dazu können Build-/CI-/CD-Server gehören.

> [!NOTE]
> *Nur für Windows 7- und Windows Server 2008-Computer:* Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/help/2533623) enthält.

## <a name="prerequisites-with-visual-studio-2017"></a>Voraussetzungen für Visual Studio 2017

Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. [Visual Studio 2017](#visual-studio-2017) stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.

Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

So entwickeln Sie .NET Core 2.x-Apps in Visual Studio 2017:

 1. [Download and install Visual Studio 2017 version 15.3.0 or higher (Laden Sie Visual Studio Version 15.3.0 oder höher herunter und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)**, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-3-workloads.jpg)

Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio 2017 standardmäßig .NET Core 1.x. Installieren Sie die .NET Core 2.x SDK, um .NET Core 2.x in Visual Studio 2017 zu unterstützen.

 2. Installieren Sie das [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).
 3. Weisen Sie bestehende oder neue .NET Core 1.x-Projekte neu .NET Core 2.x zu, indem Sie die folgenden Anweisungen verwenden:
    * Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
    * Setzen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.0**.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Sobald die .NET Core 2.x SDK installiert ist, verwendet Visual Studio 2017 diese standardmäßig und unterstützt die folgenden Aktionen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x-Projekte.
* Neuzuweisen von .NET Core 1.x-Projekten auf .NET Core 2.x sowie Erstellen und Ausführen derselben.
* Erstellen neuer .NET Core 2.x-Projekte.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

[download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher (Laden Sie Visual Studio 2017 RTM (Version 15.0.26228.4 oder höher))](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)** herunter, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:
  > * Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.
  > * Die Projekte basieren auf dem Format „project.json“, das veraltet ist.
>
> Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).
---

> [!TIP]
> So überprüfen Sie Ihre Version von Visual Studio 2017:
>
> * Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
> * Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.
>   * Für .NET Core 2.1 Vorschau 1-Apps muss dies Visual Studio 2017 Version 15.6 Vorschau 6 oder höher sein.
>   * Für .NET Core 2.0-Apps muss dies Visual Studio 2017 Version 15.3 oder höher sein.
>   * Für .NET Core 1.x-Apps muss dies Visual Studio 2017 Version 15.0 oder höher sein.
