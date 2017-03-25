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
ms.sourcegitcommit: e374b924bf78d62227cb9607641130dfd9128186
ms.openlocfilehash: 6383a0ce253f6f7000ed8a81b29b9e1d58914acc
ms.lasthandoff: 03/06/2017

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

## <a name="prerequisites-with-visual-studio-2017"></a>Voraussetzungen für Visual Studio 2017

Sie können einen beliebigen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Windows in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio 2017](#visual-studio-2017) verwenden.

Wenn Sie Visual Studio 2017 zum Entwickeln von .NET Core-Anwendungen verwenden möchten, müssen Sie die neueste Version von Visual Studio mit dem **plattformübergreifenden .NET Core**-Toolset (im Abschnitt **Andere Toolsets**) installiert haben.

Es gibt verschiedene Editionen von Visual Studio 2017. Sie können [Visual Studio Community 2017](https://www.visualstudio.com/vs/visual-studio-2017/#downloadvs) für den Einstieg kostenlos herunterladen.  Weitere Informationen zum Installationsvorgang für Visual Studio finden Sie unter [Installieren von Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio).

Informationen zu den Änderungen in Visual Studio 2017 finden Sie in den [Anmerkungen zur Version](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes).

[sdk]: https://go.microsoft.com/fwlink/?LinkID=827546
