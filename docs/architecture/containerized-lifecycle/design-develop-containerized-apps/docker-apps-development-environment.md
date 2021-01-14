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
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="2fda6-103">Entwicklungsumgebung für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="2fda6-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="2fda6-104">Auswahlmöglichkeiten für Entwicklungstools: IDE oder Editor</span><span class="sxs-lookup"><span data-stu-id="2fda6-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="2fda6-105">Ganz gleich, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen schlanken und flexiblen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von Docker-Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2fda6-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="2fda6-106">Visual Studio Code und Docker-CLI (plattformübergreifende Tools für Mac, Linux und Windows)</span><span class="sxs-lookup"><span data-stu-id="2fda6-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="2fda6-107">Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Visual Studio Code und die Docker-CLI verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fda6-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="2fda6-108">Diese Produkte bieten einen einfachen aber widerstandsfähigen Prozess, der für die Optimierung des Entwicklungsworkflows kritisch ist.</span><span class="sxs-lookup"><span data-stu-id="2fda6-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="2fda6-109">Durch Installieren von „Docker für Mac“ oder „Docker für Windows“ (Entwicklungsumgebung), können Docker-Entwickler eine einzelne Docker-CLI verwenden, um Apps sowohl für Windows als auch für Linux (Laufzeitumgebung) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2fda6-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="2fda6-110">Außerdem unterstützt Visual Studio Code mit IntelliSense für Docker-Dateien und Verknüpfungsaufgaben, um Docker-Befehle aus dem Editor auszuführen, Erweiterungen für Docker.</span><span class="sxs-lookup"><span data-stu-id="2fda6-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="2fda6-111">Sie können Visual Studio Code hier herunterladen: <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="2fda6-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="2fda6-112">Docker für Mac und Windows können Sie hier herunterladen: <https://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="2fda6-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="2fda6-113">Visual Studio mit Docker-Tools (Windows-Entwicklungscomputer)</span><span class="sxs-lookup"><span data-stu-id="2fda6-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="2fda6-114">Es wird empfohlen, Visual Studio 2019 mit den aktivierten integrierten Docker-Tools zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fda6-114">It's recommend that you use Visual Studio 2019 with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="2fda6-115">Mit Visual Studio können Sie Ihre Anwendungen direkt in der gewählten Docker-Umgebung entwickeln, ausführen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2fda6-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="2fda6-116">Drücken Sie F5, um Ihre Anwendungen (einzelner oder mehrere Container) direkt auf einem Docker-Host zu debuggen. Alternativ drücken Sie STRG+F5, um Ihre App zu bearbeiten und zu aktualisieren, ohne den Container erneut erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2fda6-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="2fda6-117">Dies ist die einfachste und stärkste Wahl für Windows-Entwickler, um Docker-Container für Linux oder Windows zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2fda6-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="2fda6-118">Visual Studio für Mac (Macintosh-Entwicklungscomputer)</span><span class="sxs-lookup"><span data-stu-id="2fda6-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="2fda6-119">Sie können [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum Entwickeln von Docker-basierten Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fda6-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="2fda6-120">Visual Studio für Mac bietet im Vergleich mit Visual Studio Code für Mac die reichhaltiger ausgestattete IDE.</span><span class="sxs-lookup"><span data-stu-id="2fda6-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="2fda6-121">Optionen zu Sprache und Framework</span><span class="sxs-lookup"><span data-stu-id="2fda6-121">Language and framework choices</span></span>

<span data-ttu-id="2fda6-122">Sie können Docker-Anwendungen mithilfe von Microsoft-Tools in den meisten modernen Sprachen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="2fda6-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="2fda6-123">Das Folgende ist eine erste Liste, auf die Sie aber nicht beschränkt sind:</span><span class="sxs-lookup"><span data-stu-id="2fda6-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="2fda6-124">.NET und ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2fda6-124">.NET and ASP.NET Core</span></span>
- <span data-ttu-id="2fda6-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="2fda6-125">Node.js</span></span>
- <span data-ttu-id="2fda6-126">Gehe zu</span><span class="sxs-lookup"><span data-stu-id="2fda6-126">Go</span></span>
- <span data-ttu-id="2fda6-127">Java</span><span class="sxs-lookup"><span data-stu-id="2fda6-127">Java</span></span>
- <span data-ttu-id="2fda6-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="2fda6-128">Ruby</span></span>
- <span data-ttu-id="2fda6-129">Python</span><span class="sxs-lookup"><span data-stu-id="2fda6-129">Python</span></span>

<span data-ttu-id="2fda6-130">Im Grunde genommen können Sie jede moderne Sprache verwenden, die von Docker unter Linux oder Windows unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="2fda6-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2fda6-131">[Zurück](deploy-azure-kubernetes-service.md)
>[Weiter](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2fda6-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
