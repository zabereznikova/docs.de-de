---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: 477d303b50495070ba3a3540188deb274dd9f510
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44277246"
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
* Windows Server 2016 oder höhere Versionen (vollständiger Server, Serverkern oder Nano-Server)

## <a name="net-core-supported-operating-systems"></a>Von .NET Core unterstützte Betriebssysteme

Die folgenden Artikel enthalten eine vollständige Liste der von .NET Core unterstützten Betriebssysteme je nach Version:

* [.NET Core 2.1 – Supported OS Versions (Von .NET Core 2.1 unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 2.0 – Supported OS Versions (Von .NET Core 2.0 unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [.NET Core 1.x – Supported OS Versions (Von .NET Core 1.x unterstützte Betriebssysteme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

.NET Core 1.1 und frühere Versionen benötigen Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016. Diese Abhängigkeit wird automatisch durch das .NET Core-Installationsprogramm installiert.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) muss in folgenden Fällen installiert werden:

* Beim Installieren von .NET Core mit dem [Installationsprogrammskript](./tools/dotnet-install-script.md).
* Beim Bereitstellen einer eigenständigen .NET Core-Anwendung.
* Beim Erstellen des Produkt aus der Quelle.
* Beim Installieren von .NET Core über eine *ZIP*-Datei. Dazu können Build-/CI-/CD-Server gehören.

> [!NOTE]
> **Für Windows 8.1 und frühere Versionen oder Windows Server 2012 R2 und frühere Versionen:**
>
> Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows) enthält, das über Windows Update installiert werden kann. Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung wie die folgende angezeigt: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.
>
> **Für Windows 7 oder Windows Server 2008 R2:**
>
> Stellen Sie sicher, dass Sie neben KB2999226 auch [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installiert haben. Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung ähnlich der folgenden angezeigt: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-with-visual-studio-2017"></a>Voraussetzungen für Visual Studio 2017

Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. [Visual Studio 2017](#visual-studio-2017) stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.

Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

So entwickeln Sie .NET Core 2.1-Apps in Visual Studio 2017:

 1. [Download and install Visual Studio 2017 version 15.7.0 or higher (Laden Sie Visual Studio Version 15.7.0 oder höher herunter, und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung** , die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-8-workloads.jpg)

Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert wurde, verwendet Visual Studio 2017 15.7 standardmäßig das .NET Core 2.0. SDK und Visual Studio 2017 15.8 das .NET Core 2.1 SDK.

 2. Wenn Sie Visual Studio 2017 15.7 verwenden, müssen Sie das [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) verwenden oder ein Upgrade auf Visual Studio 2017 15.8 durchführen.

 3. Weisen Sie .NET Core 2.1 bestehende oder neue .NET Core 2.1-Projekte neu zu, indem Sie die folgenden Anweisungen verwenden:
    * Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
    * Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.1** fest.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Nach der Konfiguration von Visual Studio mit dem .NET Core 2.1 SDK können Sie folgende Aktionen ausführen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.
* Neuzuweisen von .NET Core 1.x-Projekten und .NET Core 2.0-Projekten zu .NET Core 2.1 sowie Erstellen und Ausführen derselben.
* Erstellen neuer .NET Core 2.1-Projekte.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

So entwickeln Sie .NET Core 2.0-Apps in Visual Studio 2017:

 1. [Download and install Visual Studio 2017 version 15.3.0 or higher (Laden Sie Visual Studio Version 15.3.0 oder höher herunter und installieren Sie diese)](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **.NET Core cross-platform development (Plattformübergreifende .NET Core-Entwicklung)**, das im Abschnitt **Andere Toolsets** ausgewählt sein sollte.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-15-3-workloads.jpg)

Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio 2017 standardmäßig .NET Core 1.x. Installieren Sie das .NET Core 2.0 SDK, um .NET Core 2.0 in Visual Studio 2017 zu unterstützen.

 2. Installieren Sie das [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).
 3. Weisen Sie .NET Core 2.0 bestehende oder neue .NET Core 1.x-Projekte neu zu, indem Sie die folgenden Anweisungen verwenden:
    * Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
    * Setzen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.0**.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.0“](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Nach der Installation des .NET Core 2.0. SDK verwendet Visual Studio 2017 dieses standardmäßig. Es unterstützt die folgenden Aktionen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x-Projekte.
* Neuzuweisen von .NET Core 1.x-Projekten zu .NET Core 2.0 sowie Erstellen und Ausführen derselben.
* Erstellen neuer .NET Core 2.0-Projekte.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

[Laden Sie Visual Studio 2017 RTM herunter, und installieren es](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:
  > * Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.
  > * Die Projekte basieren auf dem Format „project.json“, das veraltet ist.
>
> Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).
---

<a name="vs-mapping"></a>

> [!TIP]
> So überprüfen Sie Ihre Version von Visual Studio 2017:
>
> * Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
> * Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.
>   * Für Vorschauversion 1 der .NET Core 2.2-Apps muss dies Visual Studio 2017 Version 15.9 (aktuell als Vorschau) oder höher sein.
>   * Für .NET Core 2.1-Apps muss dies Visual Studio 2017 Version 15.7 oder höher sein.
>   * Für .NET Core 2.0-Apps muss dies Visual Studio 2017 Version 15.3 oder höher sein.
>   * Für .NET Core 1.x-Apps muss dies Visual Studio 2017 Version 15.0 oder höher sein.
