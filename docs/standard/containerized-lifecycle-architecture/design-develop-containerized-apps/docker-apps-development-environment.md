---
title: Entwicklungsumgebung für Docker-Apps
description: Lernen Sie die wichtigsten Entwicklung Tooloptionen kennen, die den Docker-Entwicklungslebenszyklus zu unterstützen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 1d22b45a8eee9198d337df9f0b8b4b78371fa31a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219996"
---
# <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

## <a name="development-tools-choices-ide-or-editor"></a>Auswahlmöglichkeiten für Entwicklungstools: IDE oder Editor

Unabhängig davon, wenn Sie eine vollständige und leistungsstarke IDE oder einen einfachen und flexiblen Editor bevorzugen hat Microsoft Sie bei der Entwicklung von Docker-Anwendungen.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code und Docker-CLI (Cross-Platform-Tools für Mac, Linux und Windows)

Wenn Sie einen einfachen, plattformübergreifenden Editor, die jede beliebige Entwicklungssprache unterstützt bevorzugen, können Sie Visual Studio Code und Docker-CLI. Diese Produkte bieten eine einfachen aber widerstandsfähigen Prozess, der für den Entwicklungsworkflow optimiert von entscheidender Bedeutung ist. Durch die Installation von "Docker for Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-CLI verwenden, um apps für Windows und Linux (Common Language Runtime Environment) zu erstellen. Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für die dockerfile-Dateien und Verknüpfungsaufgaben Docker-Befehle aus dem Editor ausführen.

> [!NOTE]
> Informationen zum Herunterladen von Visual Studio Code finden Sie unter <https://code.visualstudio.com/download>.

Um Docker für Mac und Windows herunterzuladen, wechseln Sie zu <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio mit der Docker-Tools

Wenn Sie Visual Studio 2015 verwenden, können Sie "Docker-Tools für Visual Studio". die Add-on-Tools installieren Für Visual Studio 2017 werden Docker-Tools bereits integrierten. In beiden Fällen können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung. F5 Ihrer Anwendung (einzelne oder mehrere Container) direkt in Docker hosten, die beim Debuggen oder drücken Sie STRG + F5 zum Bearbeiten und aktualisieren Sie die app ohne den Container erneut erstellen. Dies ist die einfachste und leistungsfähigere Wahl für Windows-Entwickler, die Docker-Container für Linux oder Windows erstellen.

> [!NOTE]
> Um Docker-Tools für Visual Studio herunterzuladen, wechseln Sie zu <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Sprache und Framework-Optionen

Sie können Docker-Anwendungen und Microsoft-Tools mit den meisten modernen Sprachen entwickeln. Im folgenden ist eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:

-   .NET Core und ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

Im Grunde genommen können Sie alle modernen Sprache, die von Docker unter Linux oder Windows unterstützt werden.

>[!div class="step-by-step"]
>[Zurück](deploy-azure-kubernetes-service.md)
>[Weiter](docker-apps-inner-loop-workflow.md)