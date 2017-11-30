---
title: "Entwicklungsumgebung für Docker-Apps"
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="42d83-104">Entwicklungsumgebung für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="42d83-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="42d83-105">Optionen für Entwicklungstools: IDE oder -Editor</span><span class="sxs-lookup"><span data-stu-id="42d83-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="42d83-106">Unabhängig davon Wunsch eine vollständige und leistungsfähige IDE oder eine einfache und agile-Editor, hat Microsoft Sie beim Entwickeln von Docker-Anwendungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="42d83-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="42d83-107">Visual Studio-Code und Docker-Befehlszeilenschnittstelle (plattformübergreifenden Tools für Windows, Mac und Linux)</span><span class="sxs-lookup"><span data-stu-id="42d83-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="42d83-108">Wenn Sie einen einfachen, plattformübergreifende-Editor unterstützt Entwicklungssprache bevorzugen, können Sie Visual Studio-Code und Docker-Befehlszeilenschnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="42d83-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="42d83-109">Diese Produkte bieten eine einfache, aber robuste erzielen Sie, die für die Optimierung von des Developer-Workflows entscheidender Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="42d83-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="42d83-110">Installieren Sie "Docker für Mac" oder "Docker für Windows" (Development Environment), können Docker-Entwickler eine einzelne Docker-Befehlszeilenschnittstelle Sie um apps für Windows oder Linux (Common Language Runtime Environment) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42d83-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="42d83-111">Darüber hinaus Visual Studio Code unterstützt Erweiterungen für Docker mit IntelliSense für dockerfile-Dateien und Verknüpfung Aufgaben zum Docker-Befehle aus dem Editor ausführen.</span><span class="sxs-lookup"><span data-stu-id="42d83-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="42d83-112">Um Visual Studio Code herunterzuladen, wechseln Sie zu <https://code.visualstudio.com/download>.</span><span class="sxs-lookup"><span data-stu-id="42d83-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="42d83-113">Um Docker für Macintosh- und Windows herunterzuladen, wechseln Sie zu <http://www.docker.com/products/docker>.</span><span class="sxs-lookup"><span data-stu-id="42d83-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="42d83-114">Visual Studio mit Docker-Tools</span><span class="sxs-lookup"><span data-stu-id="42d83-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="42d83-115">Wenn Sie Visual Studio 2015 verwenden, können Sie das Add-on-Tools "Docker-Tools für Visual Studio." installieren</span><span class="sxs-lookup"><span data-stu-id="42d83-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="42d83-116">Für Visual Studio 2017 stammen Docker-Tools bereits integrierten.</span><span class="sxs-lookup"><span data-stu-id="42d83-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="42d83-117">In beiden Fällen können Sie entwickeln, ausführen und überprüfen Ihre Anwendungen direkt in der ausgewählten Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="42d83-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="42d83-118">F5 Ihrer Anwendung (einzelne Container oder mehrere Container) direkt in ein Docker hosten beim Debuggen oder drücken Sie STRG + F5, bearbeiten und aktualisieren Sie die app ohne den Container neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="42d83-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="42d83-119">Dies ist die einfachste und leistungsfähiger Wahl für Windows-Entwickler, die Docker-Container für Linux- oder Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="42d83-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="42d83-120">Um Docker-Tools für Visual Studio herunterzuladen, wechseln Sie zu <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span><span class="sxs-lookup"><span data-stu-id="42d83-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="42d83-121">Sprache und Framework-Optionen</span><span class="sxs-lookup"><span data-stu-id="42d83-121">Language and framework choices</span></span>

<span data-ttu-id="42d83-122">Sie können die Docker-Anwendungen und Microsoft-Tools für die meisten modernen Sprachen entwickeln.</span><span class="sxs-lookup"><span data-stu-id="42d83-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="42d83-123">Im folgenden finden eine anfängliche Liste, aber Sie sind nicht darauf beschränkt:</span><span class="sxs-lookup"><span data-stu-id="42d83-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="42d83-124">.NET Core und ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="42d83-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="42d83-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="42d83-125">Node.js</span></span>

-   <span data-ttu-id="42d83-126">Golang</span><span class="sxs-lookup"><span data-stu-id="42d83-126">Golang</span></span>

-   <span data-ttu-id="42d83-127">Java</span><span class="sxs-lookup"><span data-stu-id="42d83-127">Java</span></span>

-   <span data-ttu-id="42d83-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="42d83-128">Ruby</span></span>

-   <span data-ttu-id="42d83-129">Python</span><span class="sxs-lookup"><span data-stu-id="42d83-129">Python</span></span>

<span data-ttu-id="42d83-130">Grundsätzlich können Sie eine moderne Sprache, die von Docker unter Linux oder Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42d83-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="42d83-131">[Vorherigen] (orchestrieren-High-Skalierbarkeit-availability.md) [weiter] (Docker-apps-Inner-Schleife-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="42d83-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
