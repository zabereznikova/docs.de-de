---
title: "Entwicklungsprozess für auf Docker-basierende Anwendungen"
description: ".NET Microservices-Architektur für .NET-Containeranwendungen | Entwicklungsprozess für auf Docker-basierende Anwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: f4c241f463ff1270037c7d66ba39409ca5d9e728
ms.contentlocale: de-de
ms.lasthandoff: 09/05/2017

---
# <a name="development-process-for-docker-based-applications"></a>Entwicklungsprozess für auf Docker-basierende Anwendungen

*Entwickeln Sie .NET-Containeranwendungen nach Ihren Wünschen, egal ob mit Fokus auf IDE mit Visual Studio und Visual Studio-Tools für Docker oder mit Fokus auf CLI/Editor mit Docker-CLI und Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

### <a name="development-tool-choices-ide-or-editor"></a>Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor

Egal, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen einfachen und agilen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von Docker-Anwendungen verwenden können.

**Visual Studio mit Tools für Docker** Wenn Sie Visual Studio 2015 verwenden, können Sie das Add-In [Visual Studio-Tools für Docker](https://marketplace.visualstudio.com/items?itemName=MicrosoftCloudExplorer.VisualStudioToolsforDocker-Preview) installieren. Wenn Sie Visual Studio 2017 verwenden, sind Tools für Docker bereits integriert. In jedem Fall können Sie mithilfe der Tools für Docker Ihre Anwendungen direkt in der Docker-Zielumgebung entwickeln, ausführen und überprüfen. Sie können F5 drücken, um Ihre Anwendungen (einzelner oder mehrere Container) direkt in einem Docker-Host auszuführen und zu debuggen. Alternativ drücken Sie STRG+F5, um Ihre Anwendungen zu bearbeiten und zu aktualisieren, ohne den Container erneut erstellen zu müssen. Dies ist die einfachste und stärkste Wahl für Windows-Entwickler, die auf Docker-Container für Linux oder Windows abzielen.

**Visual Studio Code und Docker-CLI** Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Microsoft Visual Studio Code (VS Code) sowie die Docker-CLI verwenden. Dies ist ein plattformübergreifender Entwicklungsansatz für Mac, Linux und Windows.

Diese Produkte bieten eine einfache aber robuste Erfahrung, die den Entwicklungsworkflow optimiert. Durch Installation der Tools der [Docker Community Edition (CE)](https://www.docker.com/community-edition) können Sie eine einzelne Docker-CLI zum Erstellen von Apps für Windows und Linux verwenden. Zusätzlich unterstützt Visual Studio Code Erweiterungen für Docker, z.B. IntelliSense für Docker-Dateien und Verknüpfungsaufgaben, um Docker-Befehle aus dem Editor auszuführen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Visual Studio-Tools für Docker**
    [*https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4*](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4)

-   **Visual Studio Code**. Offizielle Website.
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Docker Community Edition (CE) für Mac und Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>.NET-Sprachen und -Frameworks für Docker-Container

Wie in vorherigen Abschnitten diese Handbuchs erwähnt, können Sie .NET Framework, .NET Core oder das Open-Source-Mono-Projekt verwenden, wenn Sie .NET-Containeranwendungen für Docker entwickeln. Sie können C\#, F\# oder Visual Studio entwickeln, wenn Sie Linux- oder Windows-Container als Ziel haben, je nachdem, welches .NET-Framework verwendet wird. Weitere Details zu .NET-Sprachen finden Sie im Blogbeitrag [The .NET Language Strategy (Strategie für die .NET-Sprache)](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).


>[!div class="step-by-step"]
[Zurück] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Weiter] (docker-app-development-workflow.md)

