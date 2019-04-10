---
title: Entwicklungsumgebung für Docker-Apps
description: Lernen Sie die wichtigsten Entwicklung Tooloptionen kennen, die den Docker-Entwicklungslebenszyklus zu unterstützen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318818"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="b8719-103">Entwicklungsumgebung für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="b8719-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="b8719-104">Auswahlmöglichkeiten für Entwicklungstools: IDE oder Editor</span><span class="sxs-lookup"><span data-stu-id="b8719-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="b8719-105">Unabhängig davon, wenn Sie eine vollständige und leistungsstarke IDE oder einen einfachen und flexiblen Editor bevorzugen hat Microsoft Sie bei der Entwicklung von Docker-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b8719-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="b8719-106">Visual Studio Code und Docker-CLI (Cross-Platform-Tools für Mac, Linux und Windows)</span><span class="sxs-lookup"><span data-stu-id="b8719-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="b8719-107">Wenn Sie einen einfachen, plattformübergreifenden Editor, die jede beliebige Entwicklungssprache unterstützt bevorzugen, können Sie Visual Studio Code und Docker-CLI.</span><span class="sxs-lookup"><span data-stu-id="b8719-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="b8719-108">Diese Produkte bieten eine einfachen aber widerstandsfähigen Prozess, der für den Entwicklungsworkflow optimiert von entscheidender Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="b8719-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="b8719-109">Durch die Installation von "Docker for Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-CLI verwenden, um apps für Windows und Linux (Common Language Runtime Environment) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b8719-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="b8719-110">Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für die dockerfile-Dateien und Verknüpfungsaufgaben Docker-Befehle aus dem Editor ausführen.</span><span class="sxs-lookup"><span data-stu-id="b8719-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b8719-111">Informationen zum Herunterladen von Visual Studio Code finden Sie unter <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="b8719-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="b8719-112">Um Docker für Mac und Windows herunterzuladen, wechseln Sie zu <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="b8719-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="b8719-113">Visual Studio mit der Docker-Tools (Windows-Entwicklungscomputer)</span><span class="sxs-lookup"><span data-stu-id="b8719-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="b8719-114">Es wird empfohlen, Visual Studio 2017 (oder höher) mit der integrierten Docker-Tools aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b8719-114">We recommend you use Visual Studio 2017 (or later) with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="b8719-115">Mit Visual Studio können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b8719-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="b8719-116">Drücken Sie F5 zum Debuggen Ihrer Anwendung (einzelne oder mehrere Container) direkt in einem Docker-Host, oder drücken Sie STRG + F5 zum Bearbeiten und aktualisieren Sie die app ohne den Container erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="b8719-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="b8719-117">Es ist die einfachste und stärkste Wahl für Windows-Entwickler zum Erstellen von Docker-Containern für Linux oder Windows.</span><span class="sxs-lookup"><span data-stu-id="b8719-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="b8719-118">Visual Studio für Mac (Macintosh-Entwicklungscomputer)</span><span class="sxs-lookup"><span data-stu-id="b8719-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="b8719-119">Sie können [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) beim Entwickeln von Docker-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b8719-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="b8719-120">Visual Studio für Mac bietet eine umfassendere IDE im Vergleich zu Visual Studio Code für Mac.</span><span class="sxs-lookup"><span data-stu-id="b8719-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="b8719-121">Sprache und Framework-Optionen</span><span class="sxs-lookup"><span data-stu-id="b8719-121">Language and framework choices</span></span>

<span data-ttu-id="b8719-122">Sie können Docker-Anwendungen, die meisten modernen Sprachen mit Microsoft-Tools entwickeln.</span><span class="sxs-lookup"><span data-stu-id="b8719-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="b8719-123">Im folgenden ist eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:</span><span class="sxs-lookup"><span data-stu-id="b8719-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="b8719-124">.NET Core und ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b8719-124">.NET Core and ASP.NET Core</span></span>
- <span data-ttu-id="b8719-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="b8719-125">Node.js</span></span>
- <span data-ttu-id="b8719-126">Gehe zu</span><span class="sxs-lookup"><span data-stu-id="b8719-126">Go</span></span>
- <span data-ttu-id="b8719-127">Java</span><span class="sxs-lookup"><span data-stu-id="b8719-127">Java</span></span>
- <span data-ttu-id="b8719-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="b8719-128">Ruby</span></span>
- <span data-ttu-id="b8719-129">Python</span><span class="sxs-lookup"><span data-stu-id="b8719-129">Python</span></span>

<span data-ttu-id="b8719-130">Im Grunde genommen können Sie alle modernen Sprache, die von Docker unter Linux oder Windows unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b8719-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b8719-131">[Zurück](deploy-azure-kubernetes-service.md)
>[Weiter](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b8719-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
