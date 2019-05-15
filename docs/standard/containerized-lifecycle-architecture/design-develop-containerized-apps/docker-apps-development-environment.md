---
title: Entwicklungsumgebung für Docker-Apps
description: Lernen Sie die wichtigsten Entwicklung Tooloptionen kennen, die den Docker-Entwicklungslebenszyklus zu unterstützen.
ms.date: 02/15/2019
ms.openlocfilehash: 0f71ffa5e6870f45908e4def6577120a17ec744c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641422"
---
# <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

## <a name="development-tools-choices-ide-or-editor"></a>Auswahlmöglichkeiten für Entwicklungstools: IDE oder Editor

Unabhängig davon, wenn Sie eine vollständige und leistungsstarke IDE oder einen einfachen und flexiblen Editor bevorzugen hat Microsoft Sie bei der Entwicklung von Docker-Anwendungen.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code und Docker-CLI (Cross-Platform-Tools für Mac, Linux und Windows)

Wenn Sie einen einfachen, plattformübergreifenden Editor, die jede beliebige Entwicklungssprache unterstützt bevorzugen, können Sie Visual Studio Code und Docker-CLI. Diese Produkte bieten eine einfachen aber widerstandsfähigen Prozess, der für den Entwicklungsworkflow optimiert von entscheidender Bedeutung ist. Durch die Installation von "Docker for Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-CLI verwenden, um apps für Windows und Linux (Common Language Runtime Environment) zu erstellen. Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für die dockerfile-Dateien und Verknüpfungsaufgaben Docker-Befehle aus dem Editor ausführen.

> [!NOTE]
>
> Informationen zum Herunterladen von Visual Studio Code finden Sie unter <https://code.visualstudio.com/download>.
>
> Um Docker für Mac und Windows herunterzuladen, wechseln Sie zu <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio mit der Docker-Tools (Windows-Entwicklungscomputer)

Es wird empfohlen, Visual Studio 2017 (oder höher) mit der integrierten Docker-Tools aktiviert. Mit Visual Studio können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung. Drücken Sie F5 zum Debuggen Ihrer Anwendung (einzelne oder mehrere Container) direkt in einem Docker-Host, oder drücken Sie STRG + F5 zum Bearbeiten und aktualisieren Sie die app ohne den Container erneut erstellen. Es ist die einfachste und stärkste Wahl für Windows-Entwickler zum Erstellen von Docker-Containern für Linux oder Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio für Mac (Macintosh-Entwicklungscomputer)

Sie können [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) beim Entwickeln von Docker-basierte Anwendungen. Visual Studio für Mac bietet eine umfassendere IDE im Vergleich zu Visual Studio Code für Mac.

## <a name="language-and-framework-choices"></a>Sprache und Framework-Optionen

Sie können Docker-Anwendungen, die meisten modernen Sprachen mit Microsoft-Tools entwickeln. Im folgenden ist eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:

- .NET Core und ASP.NET Core
- Node.js
- Gehe zu
- Java
- Ruby
- Python

Im Grunde genommen können Sie alle modernen Sprache, die von Docker unter Linux oder Windows unterstützt werden.

>[!div class="step-by-step"]
>[Zurück](deploy-azure-kubernetes-service.md)
>[Weiter](docker-apps-inner-loop-workflow.md)
