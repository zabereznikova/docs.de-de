---
title: "Entwicklungsprozess für auf Docker-basierende Anwendungen"
description: ".NET Microservices-Architektur für .NET-Containeranwendungen | Entwicklungsprozess für auf Docker-basierende Anwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc91c7d5e2e27602afd6d583bf09adae3caea59e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="910a3-104">Entwicklungsprozess für auf Docker-basierende Anwendungen</span><span class="sxs-lookup"><span data-stu-id="910a3-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="910a3-105">*Entwickeln Sie .NET-Containeranwendungen nach Ihren Wünschen, egal ob mit Fokus auf IDE mit Visual Studio und Visual Studio-Tools für Docker oder mit Fokus auf CLI/Editor mit Docker-CLI und Visual Studio Code.*</span><span class="sxs-lookup"><span data-stu-id="910a3-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="910a3-106">Entwicklungsumgebung für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="910a3-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="910a3-107">Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor</span><span class="sxs-lookup"><span data-stu-id="910a3-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="910a3-108">Egal, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen einfachen und agilen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von Docker-Anwendungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="910a3-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="910a3-109">**Visual Studio (für Windows)**.</span><span class="sxs-lookup"><span data-stu-id="910a3-109">**Visual Studio (for Windows)**.</span></span> <span data-ttu-id="910a3-110">Um Docker-basierte Anwendungen zu entwickeln, verwenden Sie Visual Studio 2017 oder höhere Versionen, die Tools für Docker enthalten, die bereits integriert sind.</span><span class="sxs-lookup"><span data-stu-id="910a3-110">To develop Docker-based applications, use Visual Studio 2017 or later versions that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="910a3-111">Mit den Tools für Docker können Sie Ihre Anwendungen direkt in der Docker-Zielumgebung entwickeln, ausführen und überprüfen.</span><span class="sxs-lookup"><span data-stu-id="910a3-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="910a3-112">Sie können F5 drücken, um Ihre Anwendungen (einzelner oder mehrere Container) direkt in einem Docker-Host auszuführen und zu debuggen. Alternativ drücken Sie STRG+F5, um Ihre Anwendungen zu bearbeiten und zu aktualisieren, ohne den Container erneut erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="910a3-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="910a3-113">Dies ist die leistungsstärkste Entwicklungsoption für Docker-basierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="910a3-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="910a3-114">**Visual Studio für Mac**.</span><span class="sxs-lookup"><span data-stu-id="910a3-114">**Visual Studio for Mac**.</span></span> <span data-ttu-id="910a3-115">Es handelt sich um eine IDE, eine Weiterentwicklung von Xamarin Studio, die unter macOS ausgeführt wird und die Docker-basierte Anwendungsentwicklung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="910a3-115">It is an IDE, evolution of Xamarin Studio, that runs on macOS and supports Docker-based application development.</span></span> <span data-ttu-id="910a3-116">Dies sollte die bevorzugte Wahl für Entwickler sein, die auf Mac-Computern arbeiten und eine leistungsfähige IDE verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="910a3-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="910a3-117">**Visual Studio Code und Docker-CLI**</span><span class="sxs-lookup"><span data-stu-id="910a3-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="910a3-118">Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Microsoft Visual Studio Code (VS Code) sowie die Docker-CLI verwenden.</span><span class="sxs-lookup"><span data-stu-id="910a3-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="910a3-119">Dies ist ein plattformübergreifender Entwicklungsansatz für Mac, Linux und Windows.</span><span class="sxs-lookup"><span data-stu-id="910a3-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span>

<span data-ttu-id="910a3-120">Durch Installation der Tools der [Docker Community Edition (CE)](https://www.docker.com/community-edition) können Sie eine einzelne Docker-CLI zum Erstellen von Apps für Windows und Linux verwenden.</span><span class="sxs-lookup"><span data-stu-id="910a3-120">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span> <span data-ttu-id="910a3-121">Zusätzlich unterstützt Visual Studio Code Erweiterungen für Docker, z.B. IntelliSense für Docker-Dateien und Verknüpfungsaufgaben, um Docker-Befehle aus dem Editor auszuführen.</span><span class="sxs-lookup"><span data-stu-id="910a3-121">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="910a3-122">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="910a3-122">Additional resources</span></span>

-   <span data-ttu-id="910a3-123">**Visual Studio-Tools für Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span><span class="sxs-lookup"><span data-stu-id="910a3-123">**Visual Studio Tools for Docker**
[*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>

-   <span data-ttu-id="910a3-124">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="910a3-124">**Visual Studio Code**.</span></span> <span data-ttu-id="910a3-125">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="910a3-125">Official site.</span></span>
    [<span data-ttu-id="910a3-126">*https://code.visualstudio.com/download*</span><span class="sxs-lookup"><span data-stu-id="910a3-126">*https://code.visualstudio.com/download*</span></span>](https://code.visualstudio.com/download)

-   <span data-ttu-id="910a3-127">**Docker Community Edition (CE) für Mac und Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span><span class="sxs-lookup"><span data-stu-id="910a3-127">**Docker Community Edition (CE) for Mac and Windows**
[*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span></span>

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="910a3-128">.NET-Sprachen und -Frameworks für Docker-Container</span><span class="sxs-lookup"><span data-stu-id="910a3-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="910a3-129">Wie in vorherigen Abschnitten diese Handbuchs erwähnt, können Sie .NET Framework, .NET Core oder das Open-Source-Mono-Projekt verwenden, wenn Sie .NET-Containeranwendungen für Docker entwickeln.</span><span class="sxs-lookup"><span data-stu-id="910a3-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="910a3-130">Sie können C\#, F\# oder Visual Studio entwickeln, wenn Sie Linux- oder Windows-Container als Ziel haben, je nachdem, welches .NET-Framework verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="910a3-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="910a3-131">Weitere Details zu .NET-Sprachen finden Sie im Blogbeitrag [The .NET Language Strategy (Strategie für die .NET-Sprache)](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span><span class="sxs-lookup"><span data-stu-id="910a3-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="910a3-132">[Zurück] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Weiter] (docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="910a3-132">[Previous] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Next] (docker-app-development-workflow.md)</span></span>
