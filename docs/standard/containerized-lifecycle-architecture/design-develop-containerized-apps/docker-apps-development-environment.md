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
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="46529-103">Entwicklungsumgebung für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="46529-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="46529-104">Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor</span><span class="sxs-lookup"><span data-stu-id="46529-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="46529-105">Unabhängig davon Wunsch eine vollständige und leistungsfähige IDE oder eine einfache und agile-Editor, hat Microsoft Sie beim Entwickeln von Docker-Anwendungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="46529-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="46529-106">Visual Studio-Code und Docker-Befehlszeilenschnittstelle (plattformübergreifenden Tools für Windows, Mac und Linux)</span><span class="sxs-lookup"><span data-stu-id="46529-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="46529-107">Wenn Sie einen einfachen, plattformübergreifende-Editor unterstützt Entwicklungssprache bevorzugen, können Sie Visual Studio-Code und Docker-Befehlszeilenschnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="46529-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="46529-108">Diese Produkte bieten eine einfache, aber robuste erzielen Sie, die für die Optimierung von des Developer-Workflows entscheidender Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="46529-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="46529-109">Installieren Sie "Docker für Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-Befehlszeilenschnittstelle Sie um apps für Windows oder Linux (Common Language Runtime Environment) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="46529-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="46529-110">Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für dockerfile-Dateien und Verknüpfung Aufgaben zum Docker-Befehle aus dem Editor ausführen.</span><span class="sxs-lookup"><span data-stu-id="46529-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="46529-111">Um Visual Studio Code herunterzuladen, wechseln Sie zu <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="46529-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="46529-112">Um Docker für Macintosh- und Windows herunterzuladen, wechseln Sie zu <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="46529-112">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="46529-113">Visual Studio mit Docker-Tools</span><span class="sxs-lookup"><span data-stu-id="46529-113">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="46529-114">Wenn Sie Visual Studio 2015 verwenden, können Sie das Add-on-Tools "Docker-Tools für Visual Studio." installieren</span><span class="sxs-lookup"><span data-stu-id="46529-114">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="46529-115">Für Visual Studio 2017 stammen Docker-Tools bereits integrierten.</span><span class="sxs-lookup"><span data-stu-id="46529-115">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="46529-116">In beiden Fällen können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="46529-116">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="46529-117">F5 Ihrer Anwendung (einzelne Container oder mehrere Container) direkt in ein Docker hosten beim Debuggen oder drücken Sie STRG + F5, bearbeiten und aktualisieren Sie die app ohne den Container neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="46529-117">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="46529-118">Dies ist die einfachste und leistungsfähiger Wahl für Windows-Entwickler, die Docker-Container für Linux- oder Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="46529-118">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="46529-119">Um Docker-Tools für Visual Studio herunterzuladen, wechseln Sie zu <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="46529-119">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="46529-120">Sprache und Framework-Optionen</span><span class="sxs-lookup"><span data-stu-id="46529-120">Language and framework choices</span></span>

<span data-ttu-id="46529-121">Sie können die Docker-Anwendungen und Microsoft-Tools für die meisten modernen Sprachen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="46529-121">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="46529-122">Im folgenden finden eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:</span><span class="sxs-lookup"><span data-stu-id="46529-122">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="46529-123">.NET Core und ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="46529-123">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="46529-124">Node.js</span><span class="sxs-lookup"><span data-stu-id="46529-124">Node.js</span></span>

-   <span data-ttu-id="46529-125">Golang</span><span class="sxs-lookup"><span data-stu-id="46529-125">Golang</span></span>

-   <span data-ttu-id="46529-126">Java</span><span class="sxs-lookup"><span data-stu-id="46529-126">Java</span></span>

-   <span data-ttu-id="46529-127">Ruby</span><span class="sxs-lookup"><span data-stu-id="46529-127">Ruby</span></span>

-   <span data-ttu-id="46529-128">Python</span><span class="sxs-lookup"><span data-stu-id="46529-128">Python</span></span>

<span data-ttu-id="46529-129">Grundsätzlich können Sie eine moderne Sprache, die von Docker unter Linux oder Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46529-129">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="46529-130">[Vorherigen] (orchestrieren-High-Skalierbarkeit-availability.md) [weiter] (Docker-apps-Inner-Schleife-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="46529-130">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
