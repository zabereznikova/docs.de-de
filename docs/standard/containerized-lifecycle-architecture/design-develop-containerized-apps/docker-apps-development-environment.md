---
title: Entwicklungsumgebung für Docker-Apps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ddd1006c8c6728d4d315442f409f8fa33e54f9a3
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

## <a name="development-tools-choices-ide-or-editor"></a>Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor

Unabhängig davon Wunsch eine vollständige und leistungsfähige IDE oder eine einfache und agile-Editor, hat Microsoft Sie beim Entwickeln von Docker-Anwendungen behandelt.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio-Code und Docker-Befehlszeilenschnittstelle (plattformübergreifenden Tools für Windows, Mac und Linux)

Wenn Sie einen einfachen, plattformübergreifende-Editor unterstützt Entwicklungssprache bevorzugen, können Sie Visual Studio-Code und Docker-Befehlszeilenschnittstelle verwenden. Diese Produkte bieten eine einfache, aber robuste erzielen Sie, die für die Optimierung von des Developer-Workflows entscheidender Bedeutung ist. Installieren Sie "Docker für Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-Befehlszeilenschnittstelle Sie um apps für Windows oder Linux (Common Language Runtime Environment) zu erstellen. Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für dockerfile-Dateien und Verknüpfung Aufgaben zum Docker-Befehle aus dem Editor ausführen.

> [!NOTE]
> Um Visual Studio Code herunterzuladen, wechseln Sie zu <https://code.visualstudio.com/download>.

Um Docker für Macintosh- und Windows herunterzuladen, wechseln Sie zu <http://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio mit Docker-Tools

Wenn Sie Visual Studio 2015 verwenden, können Sie das Add-on-Tools "Docker-Tools für Visual Studio." installieren Für Visual Studio 2017 stammen Docker-Tools bereits integrierten. In beiden Fällen können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung. F5 Ihrer Anwendung (einzelne Container oder mehrere Container) direkt in ein Docker hosten beim Debuggen oder drücken Sie STRG + F5, bearbeiten und aktualisieren Sie die app ohne den Container neu erstellt wird. Dies ist die einfachste und leistungsfähiger Wahl für Windows-Entwickler, die Docker-Container für Linux- oder Windows erstellen.

> [!NOTE]
> Um Docker-Tools für Visual Studio herunterzuladen, wechseln Sie zu <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Sprache und Framework-Optionen

Sie können die Docker-Anwendungen und Microsoft-Tools für die meisten modernen Sprachen entwickeln. Im folgenden finden eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:

-   .NET Core und ASP.NET Core

-   Node.js

-   Golang

-   Java

-   Ruby

-   Python

Grundsätzlich können Sie eine moderne Sprache, die von Docker unter Linux oder Windows unterstützt.


>[!div class="step-by-step"]
[Vorherigen] (orchestrieren-High-Skalierbarkeit-availability.md) [weiter] (Docker-apps-Inner-Schleife-workflow.md)
