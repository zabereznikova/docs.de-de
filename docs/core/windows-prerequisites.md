---
title: "Voraussetzungen für .NET Core unter Windows"
description: "Erfahren Sie, welche Abhängigkeiten Ihr Windows-Computer aufweisen muss, damit Sie .NET Core-Anwendungen entwickeln und ausführen können."
keywords: ".NET Core, Windows, Voraussetzungen, Abhängigkeiten, Visual Studio"
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a>Voraussetzungen für .NET Core unter Windows

In diesem Artikel erfahren Sie, welche Abhängigkeiten Sie benötigen, um .NET Core-Anwendungen auf Windows-Computern bereitzustellen und auszuführen sowie mit Visual Studio zu entwickeln.

## <a name="supported-windows-versions"></a>Unterstützte Windows-Versionen

.NET Core wird von folgenden Windows-Versionen unterstützt:

* Windows 7 SP1
* Windows 8.1
* Windows 10
* Windows Server 2008 R2 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 SP1 (vollständiger Server oder Serverkern)
* Windows Server 2012 R2 (vollständiger Server oder Serverkern)
* Windows Server 2016 (vollständiger Server, Serverkern oder Nano-Server)

In den [Versionshinweisen zu .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) finden Sie eine umfassende Liste mit unterstützten Betriebssystemen.

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

.NET Core benötigt Visual C++ Redistributable zur Ausführung unter Windows-Versionen vor Windows 10 und Windows Server 2016. Diese Abhängigkeit wird für Sie automatisch installiert, wenn Sie das .NET Core-Installationsprogramm verwenden. Sie müssen [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) jedoch manuell installieren, wenn Sie .NET Core über das [Installationsskript](./tools/dotnet-install-script.md) installieren oder eine eigenständige .NET Core-Anwendung bereitstellen.

> [!NOTE]
> <em>Nur Für Windows 7- und Windows Server 2008-Computer:</em><br>
> Stellen Sie sicher, dass Ihre Windows-Installation auf dem neuesten Stand ist und den über Windows Update installierten Hotfix [KB2533623](https://support.microsoft.com/help/2533623) enthält.

## <a name="prerequisites-with-visual-studio-2017"></a>Voraussetzungen für Visual Studio 2017

Sie können einen beliebigen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Windows in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio 2017](#visual-studio-2017) verwenden.

> [!IMPORTANT]
> Obwohl Visual Studio 2015 mit einer Vorschauversion von .NET Core-Tools verwendet werden kann, werden diese Projekte *project.json*-basiert sein, was nun veraltet ist. Visual Studio 2017 verwendet auf MSBuild basierende Projektdateien. Weitere Informationen über die Formatänderungen finden Sie unter [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Globale Übersicht der Änderungen).

Wenn Sie Visual Studio 2017 zum Entwickeln von .NET Core-Anwendungen verwenden möchten, müssen Sie die neueste Version von Visual Studio mit dem **plattformübergreifenden .NET Core**-Toolset (im Abschnitt **Andere Toolsets**) installiert haben.
![Screenshot der Visual Studio 2017-Installation mit ausgewählter Arbeitsauslastung „plattformübergreifende .NET Core-Entwicklung“](./media/windows-prerequisites/vs_workloads.jpg)

Es gibt verschiedene Editionen von Visual Studio 2017. Sie können [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) für den Einstieg kostenlos herunterladen.  Weitere Informationen zum Installationsvorgang für Visual Studio finden Sie unter [Installieren von Visual Studio 2017](/visualstudio/install/install-visual-studio).

Um sicherzustellen, dass Sie die neueste Version von Visual Studio 2017 ausführen, führen Sie folgende Schritte aus:

 * Wählen Sie im **Hilfemenü** die Option **Info zu Microsoft Visual Studio**.
 * Im Dialogfeld **Info zu Microsoft Visual Studio** muss als Versionsnummer 15.0.26228.4 oder höher angezeigt werden.

Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).

