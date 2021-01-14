---
title: Entwicklungsumgebung für Docker-Apps
description: Lernen Sie die wichtigsten Optionen für Entwicklungstools kennen, die den Docker-Entwicklungslebenszyklus unterstützen.
ms.date: 01/06/2021
ms.openlocfilehash: c6c4a1fda41131c00ba87808ed408f1d3250cabf
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970524"
---
# <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

## <a name="development-tools-choices-ide-or-editor"></a>Auswahlmöglichkeiten für Entwicklungstools: IDE oder Editor

Ganz gleich, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen schlanken und flexiblen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von Docker-Anwendungen verwenden können.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code und Docker-CLI (plattformübergreifende Tools für Mac, Linux und Windows)

Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Visual Studio Code und die Docker-CLI verwenden. Diese Produkte bieten einen einfachen aber widerstandsfähigen Prozess, der für die Optimierung des Entwicklungsworkflows kritisch ist. Durch Installieren von „Docker für Mac“ oder „Docker für Windows“ (Entwicklungsumgebung), können Docker-Entwickler eine einzelne Docker-CLI verwenden, um Apps sowohl für Windows als auch für Linux (Laufzeitumgebung) zu erstellen. Außerdem unterstützt Visual Studio Code mit IntelliSense für Docker-Dateien und Verknüpfungsaufgaben, um Docker-Befehle aus dem Editor auszuführen, Erweiterungen für Docker.

> [!NOTE]
> Sie können Visual Studio Code hier herunterladen: <https://code.visualstudio.com/download>.
>
> Docker für Mac und Windows können Sie hier herunterladen: <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio mit Docker-Tools (Windows-Entwicklungscomputer)

Es wird empfohlen, Visual Studio 2019 mit den aktivierten integrierten Docker-Tools zu verwenden. Mit Visual Studio können Sie Ihre Anwendungen direkt in der gewählten Docker-Umgebung entwickeln, ausführen und überprüfen. Drücken Sie F5, um Ihre Anwendungen (einzelner oder mehrere Container) direkt auf einem Docker-Host zu debuggen. Alternativ drücken Sie STRG+F5, um Ihre App zu bearbeiten und zu aktualisieren, ohne den Container erneut erstellen zu müssen. Dies ist die einfachste und stärkste Wahl für Windows-Entwickler, um Docker-Container für Linux oder Windows zu erstellen.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio für Mac (Macintosh-Entwicklungscomputer)

Sie können [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum Entwickeln von Docker-basierten Anwendungen verwenden. Visual Studio für Mac bietet im Vergleich mit Visual Studio Code für Mac die reichhaltiger ausgestattete IDE.

## <a name="language-and-framework-choices"></a>Optionen zu Sprache und Framework

Sie können Docker-Anwendungen mithilfe von Microsoft-Tools in den meisten modernen Sprachen entwickeln. Das Folgende ist eine erste Liste, auf die Sie aber nicht beschränkt sind:

- .NET und ASP.NET Core
- Node.js
- Gehe zu
- Java
- Ruby
- Python

Im Grunde genommen können Sie jede moderne Sprache verwenden, die von Docker unter Linux oder Windows unterstützt wird.

>[!div class="step-by-step"]
>[Zurück](deploy-azure-kubernetes-service.md)
>[Weiter](docker-apps-inner-loop-workflow.md)
