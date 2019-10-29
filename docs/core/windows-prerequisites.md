---
title: Voraussetzungen für .NET Core unter Windows
description: Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771951"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Voraussetzungen für .NET Core unter Windows

Dieser Artikel beschreibt die zur Ausführung von .NET Core-Anwendungen auf Windows unterstützten Betriebssystemversionen. Die unterstützten Betriebssystemversionen und die daraus folgenden Abhängigkeiten gelten für die drei Möglichkeiten, um .NET Core-Apps unter Windows zu entwickeln:

* [Befehlszeile](./tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [Visual Studio Code](https://code.visualstudio.com/)

Nutzen Sie für die Entwicklung unter Windows mit Visual Studio die ausführlicheren Informationen über die für die .NET Core-Entwicklung unterstützten Mindestversionen im Abschnitt [Voraussetzungen für die Entwicklung von .NET Core-Anwendungen mit Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio).

## <a name="net-core-supported-operating-systems"></a>Von .NET Core unterstützte Betriebssysteme

Die folgenden Artikel enthalten eine vollständige Liste der von .NET Core unterstützten Betriebssysteme je nach Version:

* [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Downloads](https://dotnet.microsoft.com/download) für die neueste Version bzw. [.NET Download Archives](https://dotnet.microsoft.com/download/archives#dotnet-core) für ältere Versionen.

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

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

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a>Voraussetzungen für die Entwicklung von .NET Core-Anwendungen mit Visual Studio

Für die Entwicklung von .NET Core-Anwendungen können Sie zwar einen beliebigen Editor verwenden. Das .NET Core SDK sowie Visual Studio 2017 und höhere Versionen stellen jedoch eine integrierte Entwicklungsumgebung für .NET Core-Anwendungen unter Windows bereit.

<a name="vs-mapping"></a>

Für jede .NET Core-Version ist eine Mindestversion von Visual Studio erforderlich. So überprüfen Sie Ihre Version von Visual Studio:

* Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
* Verifizieren Sie die Versionsnummer im Dialogfeld **Info zu Microsoft Visual Studio**.

In der folgenden Tabelle sind die Mindestversionen für die einzelnen SDKs aufgeführt:

| .NET Core SDK-Version | Visual Studio-Version                      |
| --------------------- | ------------------------------------------ |
| 3.0                   | Visual Studio 2019 Version 16.3 oder höher |
| 2.2                   | Visual Studio 2017 Version 15.9 oder höher |
| 2.1                   | Visual Studio 2017 Version 15.7 oder höher |
| 1.x                   | Visual Studio 2017 Version 15.0 oder höher |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

So entwickeln Sie .NET Core-Apps in Visual Studio 2019 mithilfe des .NET Core 3.0 SDK:

* [Laden Sie Visual Studio 2019 Version 16.3 oder höher herunter, und installieren Sie diese Version.](/visualstudio/install/install-visual-studio) Wählen Sie je nach der Art der Anwendung, die Sie entwickeln, eine der folgenden Workloads, die das .NET Core SDK enthält:

  * Die Workload **Plattformübergreifende .NET Core-Entwicklung** im Abschnitt **Weitere Toolsets**
  * Die Workload **ASP.NET und Webentwicklung** im Abschnitt **Web und Cloud**
  * Die Workload **NET-Desktopentwicklung** im Abschnitt **Windows**

In der folgenden Abbildung ist die in der Benutzeroberfläche von Visual Studio ausgewählte Workload **Plattformübergreifende .NET Core-Entwicklung** dargestellt:

![Screenshot der Visual Studio 2019-Installation mit ausgewählter Workload „Plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2019-workloads.jpg)

Visual Studio 2019 Version 16.3 verwendet standardmäßig das.NET Core 3.0 SDK, nachdem einer dieser Workloads installiert wurde.

Wenn Ihre vorhandenen Projekte die neueste .NET Core-Runtime verwenden soll, weisen Sie die vorhandenen .NET Core-Projekte mithilfe der folgenden Anweisungen .NET Core 3.0 neu zu:

* Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
* Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 3.0** fest.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2019 mit dem als Zielframework ausgewählten Menüelement „.NET Core 3.0“](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

Nach der Konfiguration von Visual Studio mit dem .NET Core 3.0 SDK können Sie folgende Aktionen ausführen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.
* Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 3.0 sowie Erstellen und Ausführen derselben.
* Erstellen Sie neue .NET Core 3.0-Projekte.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

So entwickeln Sie .NET Core-Apps in Visual Studio 2017 mithilfe des .NET Core 2.2 SDK:

* [Laden Sie Visual Studio 2019 Version 16.3 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Weitere Toolsets** ausgewählt sein sollte.
* [Laden Sie Visual Studio 2017 Version 15.9.0 oder höher herunter, und installieren Sie diese](/visualstudio/install/install-visual-studio) zusammen mit der Workload **Plattformübergreifende .NET Core-Entwicklung**, die im Abschnitt **Andere Toolsets** ausgewählt sein sollte.

![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs-2017-workloads.jpg)

Nachdem das Toolset **Plattformübergreifende .NET Core-Entwicklung** installiert ist, verwendet Visual Studio in der Regel eine frühere Version von .NET Core SDK.
Beispielsweise verwendet Visual Studio 2017 Version 15.9 standardmäßig das .NET Core 2.1 SDK, nachdem die Workload installiert wurde.

So aktualisieren Sie Visual Studio, um .NET Core 2.2 SDK zu verwenden:

 1. Installieren Sie das [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).

 1. Wenn Ihr Projekt die neueste .NET Core-Runtime verwenden soll, weisen Sie vorhandene oder neue .NET Core-Projekte mithilfe der folgenden Anweisungen .NET Core 2.2 neu zu:

    * Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
    * Legen Sie im Auswahlmenü **Zielframework** den Wert auf **.NET Core 2.2** fest.

![Screenshot von den Projekteigenschaften der Anwendung Visual Studio 2017 mit dem als Zielframework ausgewählten Menüelement „.NET Core 2.2“](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Nach der Konfiguration von Visual Studio mit dem .NET Core 2.2 SDK können Sie folgende Aktionen ausführen:

* Öffnen, Erstellen und Ausführen bestehender .NET Core 1.x- und .NET Core 2.x-Projekte.
* Neuzuweisen von .NET Core 1.x- und 2.x-Projekten zu .NET Core 2.2 sowie Erstellen und Ausführen derselben.
* Erstellen Sie neue .NET Core 2.2-Projekte.

---
