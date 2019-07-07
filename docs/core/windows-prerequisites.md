---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 9c4c15a08e0988955ecdf442307059868cb377d1
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539353"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Voraussetzungen für .NET Core unter Windows

Dieser Artikel beschreibt die zur Ausführung von .NET Core-Anwendungen auf Windows unterstützten Betriebssystemversionen. Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:

* [Befehlszeile](tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [Visual Studio Code](https://code.visualstudio.com/)

Wenn Sie auf Windows mit Visual Studio 2017 entwickeln, nutzen Sie die ausführlicheren Informationen über die für die .NET Core-Entwicklung unterstützten Mindestversionen im Abschnitt [Voraussetzungen für Visual Studio 2017](#prerequisites-with-visual-studio-2017).

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

* [.NET Core 3.0 (Vorschau)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Downloads](https://dotnet.microsoft.com/download) für die neueste Version bzw. [.NET Download Archives](https://dotnet.microsoft.com/download/archives#dotnet-core) für ältere Versionen.

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
> Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) enthält, das über Windows Update installiert werden kann. Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung wie die folgende angezeigt: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.
>
> **Für Windows 7 oder Windows Server 2008 R2:**
>
> Stellen Sie sicher, dass Sie neben KB2999226 auch [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installiert haben. Wenn Sie dieses Update noch nicht installiert haben, wird beim Ausführen einer .NET Core-Anwendung eine Fehlermeldung ähnlich der folgenden angezeigt: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-for-net-core-30-preview-3"></a>Voraussetzungen für .NET Core 3.0 Vorschauversion 3

.NET Core 3.0 Vorschauversion 3 hat die gleichen Voraussetzungen wie andere Versionen von .NET Core. Wenn jedoch .NET Core 3.0-Projekte mit Visual Studio erstellt werden sollen, müssen Sie [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) verwenden. Visual Studio 2019 kann parallel mit anderen Versionen von Visual Studio installiert werden, ohne dass dadurch Konflikte entstehen.

## <a name="prerequisites-with-visual-studio-2017"></a>Voraussetzungen für Visual Studio 2017
    
Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Visual Studio 2017 stellt eine integrierte Entwicklungsumgebung für .NET Core-Apps unter Windows bereit.

Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](/visualstudio/releasenotes/vs2017-relnotes).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

So entwickeln Sie .NET Core-Apps in Visual Studio 2017 mithilfe des .NET Core 2.2 SDK:

 1. [Laden Sie Visual Studio 2017 Version 15.9.0 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2017-workloads.jpg)

Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio in der Regel eine frühere Version von .NET Core SDK.
Visual Studio 2017 15.9 verwendet z. B. .NET Core 2.1 SDK standardmäßig nach der Installation der Workload.

So aktualisieren Sie Visual Studio, um .NET Core 2.2 SDK zu verwenden:

 1. Installieren Sie das [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).

 1. Wenn Ihr Projekt die neueste .NET Core-Runtime verwenden soll, weisen Sie vorhandene oder neue .NET Core-Projekte .NET Core 2.2 mithilfe der folgenden Anweisungen neu zu:

    * Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
    * Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.2** fest.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.2“](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Nach der Konfiguration von Visual Studio mit dem .NET Core 2.2 SDK können Sie folgende Aktionen ausführen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.
* Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 2.2 sowie Erstellen und Ausführen derselben.
* Erstellen Sie neue .NET Core 2.2-Projekte.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

[Laden Sie Visual Studio 2017 RTM herunter, und installieren es](/visualstudio/install/install-visual-studio) zusammen mit dem Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte, um .NET Core 1.x-Apps in Visual Studio zu entwickeln.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> Es ist möglich, Visual Studio 2015 für die .NET Core 1.x-Entwicklung zu verwenden, es wird jedoch aus den folgenden Gründen nicht empfohlen:
  > * Bei den .NET Core-Tools handelt es sich um eine nicht unterstützte Vorschauversion.
  > * Die Projekte basieren auf dem Format „project.json“, das veraltet ist.
>
> Weitere Informationen zu den Änderungen der Projektformate finden Sie unter [High-level overview of changes (Globale Übersicht der Änderungen)](./tools/cli-msbuild-architecture.md).

---

<a name="vs-mapping"></a>

> [!TIP]
> So überprüfen Sie Ihre Version von Visual Studio:
>
> * Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
> * Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.
>   * Für .NET Core 3.0 Vorschauversion 3-Apps muss dies Visual Studio 2019 Version 16.0 oder höher sein.
>   * Für .NET Core 2.2-Apps muss dies Visual Studio 2017 Version 15.9 oder höher sein.
>   * Für .NET Core 2.1-Apps muss dies Visual Studio 2017 Version 15.7 oder höher sein.
>   * Für .NET Core 1.x-Apps muss dies Visual Studio 2017 Version 15.0 oder höher sein.
