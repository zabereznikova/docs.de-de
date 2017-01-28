---
title: "Voraussetzungen für .NET Core unter Windows | Microsoft-Dokumentation"
description: "Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können."
keywords: ".NET Core, Windows, Voraussetzungen, Abhängigkeiten, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 01/05/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: c81b3b4785bff3bf8963e0ba1b917a5f797099ff
ms.openlocfilehash: b5c088da7d1155414a08995ae0d72154af891190

---

# <a name="prerequisites-for-net-core-on-windows"></a>Voraussetzungen für .NET Core unter Windows

In diesen Artikeln erfahren Sie, welche Abhängigkeiten Sie benötigen, um .NET Core-Anwendungen auf Windows-Computern bereitzustellen und auszuführen sowie mit Visual Studio zu entwickeln.

## <a name="supported-windows-versions"></a>Unterstützte Windows-Versionen

.NET Core wird von folgenden Windows-Versionen unterstützt:

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)

Eine umfassende Liste mit [unterstützten Betriebssystemen](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md#rtm-platform-support) finden Sie in den [Versionshinweisen zu .NET Core 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0.md).

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

.NET Core benötigt Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016. Diese Abhängigkeit wird für Sie automatisch installiert, wenn Sie das .NET Core-Installationsprogramm verwenden. Sie müssen [Visual C++ Redistributable für Visual Studio 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48145) jedoch manuell installieren, wenn Sie .NET Core über das [Installationsskript](https://docs.microsoft.com/en-us/dotnet/articles/core/tools/dotnet-install-script) installieren oder eine eigenständige .NET Core-Anwendung bereitstellen.

> [!NOTE]
> <em>Nur Für Windows 7- und Windows Server 2008-Computer:</em><br>
> Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/en-us/kb/2533623) enthält.

## <a name="prerequisites-with-visual-studio"></a>Voraussetzungen für Visual Studio

Sie können einen beliebigen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Windows mit Visual Studio entwickeln möchten, gibt es zwei Versionen, die Sie verwenden können:

* [Visual Studio 2015](#visual-studio-2015)
* [Visual Studio 2017 RC](#visual-studio-2017-rc)

Mit Visual Studio 2015 erstellte Projekte sind standardmäßig project.json-basiert, während mit Visual Studio 2017 RC erstellte Projekte immer MSBuild-basiert sind. Weitere Informationen über die Formatänderungen finden Sie unter [High-level overview of changes](./preview3/tools/layering.md) (Globale Übersicht der Änderungen).

### <a name="visual-studio-2015"></a>Visual Studio 2015

Wenn Sie Visual Studio 2015 zum Entwickeln von .NET Core-Apps verwenden möchten, benötigen Sie:

* Visual Studio 2015 Update 3.3 oder höher.

   Es gibt verschiedene [Editionen](https://www.visualstudio.com/vs/compare) von Visual Studio 2015. [Visual Studio Community 2015](https://www.visualstudio.com/downloads/) können Sie für den Einstieg kostenlos herunterladen. 

   Stellen Sie folgendermaßen sicher, dass Sie mit [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx) arbeiten:

   * Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
   * Im Dialogfeld **Info zu Microsoft Visual Studio** muss 14.0.25424.00 oder höher als Versionsnummer und „Update 3“ angezeigt werden.
   * Wenn Update 3 nicht angezeigt wird, müssen Sie zunächst [Visual Studio 2015 Update 3](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs) herunterladen und installieren.
   * Wenn Update 3 jedoch eine Versionsnummer kleiner als 14.0.25424.00 angezeigt wird, müssen Sie [Visual Studio 2015 Update 3.3](https://msdn.microsoft.com/library/mt752379.aspx) herunterladen und installieren.

   Informationen zu den Änderungen in Update 3 finden Sie in den [Versionshinweisen](https://www.visualstudio.com/news/releasenotes/vs2015-update3-vs).

* NuGet Manager-Erweiterung für Visual Studio

   NuGet ist der Paket-Manager für die Microsoft-Entwicklungsplattform mit .NET Core. Sie benötigen [NuGet 3.5.0-beta](https://dist.nuget.org/visualstudio-2015-vsix/v3.5.0-beta/NuGet.Tools.vsix) oder höher, um .NET Core-Apps zu erstellen.

* .NET Core Tools Preview 2

   Laden Sie das [.NET Core 1.0.1 – VS 2015 Tooling Preview 2][sdk] herunter, und installieren Sie es. 

   Vom .NET Core Tooling-Paket werden .NET Core, Projektvorlagen und andere Tools für Visual Studio 2015 installiert.

   > [!NOTE]
   > Derzeit ist es nicht möglich, ein Offline-Installationsprogramm für das [.NET Core 1.0.1 – VS 2015 Tooling Preview 2][sdk] herunterzuladen. Daher müssen Sie das [reguläre Bootstrapper][sdk] herunterladen und mit einer Befehlszeilenoption (wie `/layout c:\path`) ausführen, um das Offlinelayout anzuzeigen. Danach können Sie ein Offline-Installationsprogramm verwenden: Führen Sie dazu einfach die ausführbare Datei in einem lokalen Pfad aus. Da es sich um ein vollständiges Layout handelt, werden alle Pakete für alle unterstützten Sprachen heruntergeladen. Daher beträgt die Größe etwa 1 GB.

### <a name="visual-studio-2017-rc"></a>Visual Studio 2017 RC

Wenn Sie Visual Studio 2017 RC zum Entwickeln von .NET Core-Apps verwenden möchten, müssen Sie die neueste Version von Visual Studio RC installiert und Arbeitslast „.NET Core und Docker (Vorschau)“ ausgewählt haben. 

Es gibt verschiedene Editionen von Visual Studio 2017 RC. [Visual Studio Community 2017 RC](https://www.visualstudio.com/vs/visual-studio-2017-rc/#downloadvs) können Sie für den Einstieg kostenlos herunterladen.  Weitere Informationen zum Installationsvorgang für Visual Studio finden Sie unter [Installieren von Visual Studio 2017 RC](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio).

Um sicherzustellen, dass Sie die neueste Version von Visual Studio 2017 RC ausführen, führen Sie folgende Schritte aus:

* Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
* Im Dialogfeld **Info zu Microsoft Visual Studio** muss 15.0.26020.0 oder höher als Versionsnummer angezeigt werden.

Informationen zu den Änderungen in Visual Studio 2017 RC finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546



<!--HONumber=Jan17_HO3-->


