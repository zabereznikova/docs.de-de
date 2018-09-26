---
title: Visual Studio-Tools für Docker unter Windows
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170794"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="77d8d-103">Verwenden von Visual Studio-Tools für Docker (Visual Studio unter Windows)</span><span class="sxs-lookup"><span data-stu-id="77d8d-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="77d8d-104">Visual Studio-Tools für Docker-Entwicklungsworkflow ist vergleichbar mit der Verwendung von Visual Studio Code und Docker-CLI (er die gleichen Docker-Befehlszeilenschnittstelle basiert auf).</span><span class="sxs-lookup"><span data-stu-id="77d8d-104">The Visual Studio Tools for Docker developer workflow is similar to using Visual Studio Code and Docker CLI (it is based on the same Docker CLI).</span></span> <span data-ttu-id="77d8d-105">Visual Studio-Tools für Docker es auch erleichtert für den Einstieg, den Prozess vereinfacht und höhere Produktivität für den Build bietet, führen, und Verfassen von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="77d8d-105">Visual Studio Tools for Docker makes it even easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="77d8d-106">Ausführen und Debuggen Sie Ihre Container per simple Aktionen wie das **F5** und **STRG**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="77d8d-106">Execute and debug your containers via simple actions like **F5** and **Ctrl**+**F5**.</span></span>

> [!NOTE]
> <span data-ttu-id="77d8d-107">In diesem Artikel gilt für Visual Studio unter Windows und nicht in Visual Studio für Mac.</span><span class="sxs-lookup"><span data-stu-id="77d8d-107">This article applies to Visual Studio on Windows, and not Visual Studio for Mac.</span></span>

## <a name="configure-your-local-environment"></a><span data-ttu-id="77d8d-108">Konfigurieren der lokalen Umgebung</span><span class="sxs-lookup"><span data-stu-id="77d8d-108">Configure your local environment</span></span>

<span data-ttu-id="77d8d-109">Mit den neuesten Versionen von Docker für Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), die einfache Einrichtung erleichtert Ihnen die Docker-Anwendungen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="77d8d-109">With the latest versions of Docker for Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), the straightforward setup makes it easy to develop Docker applications.</span></span>

<span data-ttu-id="77d8d-110">Docker-Unterstützung ist in Visual Studio 2017 enthalten.</span><span class="sxs-lookup"><span data-stu-id="77d8d-110">Docker support is included in Visual Studio 2017.</span></span> <span data-ttu-id="77d8d-111">Visual Studio 2017 hier herunterladen: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="77d8d-111">Download Visual Studio 2017 here: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

## <a name="use-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="77d8d-112">Verwenden von Docker-Tools in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="77d8d-112">Use Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="77d8d-113">Es gibt zwei Ebenen der Docker-Unterstützung, die Sie einem Projekt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="77d8d-113">There are two levels of Docker support you can add to a project.</span></span> <span data-ttu-id="77d8d-114">Sie können einfach hinzufügen, in .NET Core-Web-app-Projekten, eine *dockerfile-Datei* Datei in das Projekt durch Aktivieren der Docker-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="77d8d-114">In .NET Core web app projects, you can just add a *Dockerfile* file to the project by enabling Docker support.</span></span> <span data-ttu-id="77d8d-115">Die nächste Ebene ist die Unterstützung für containerorchestrator, der hinzufügt eine *dockerfile-Datei* auf das Projekt (sofern nicht bereits vorhanden) und ein *"Docker-Compose.yml"* Datei auf Projektmappenebene.</span><span class="sxs-lookup"><span data-stu-id="77d8d-115">The next level is container orchestrator support, which adds a *Dockerfile* to the project (if it doesn't already exist) and a *docker-compose.yml* file at the solution level.</span></span>

<span data-ttu-id="77d8d-116">Die **hinzufügen** > **Docker-Unterstützung** und **hinzufügen** > **Unterstützung für Containerorchestrator** Befehle sind befindet sich auf der rechten Maustaste (oder Kontextmenü) des Projektknotens für eine Web-app-Projekt im **Projektmappen-Explorer**, wie in Abbildung 4-26 veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="77d8d-116">The **Add** > **Docker Support** and **Add** > **Container Orchestrator Support** commands are located on the right-click menu (or context menu) of the project node for a web app project in **Solution Explorer**, as shown in Figure 4-26:</span></span>

![Menüoption für Docker-Unterstützung in Visual Studio hinzufügen](media/add-docker-support-menu.png)

<span data-ttu-id="77d8d-118">Abbildung 4-26: Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2017-Projekt</span><span class="sxs-lookup"><span data-stu-id="77d8d-118">Figure 4-26: Adding Docker support to a Visual Studio 2017 project</span></span>

### <a name="add-docker-support"></a><span data-ttu-id="77d8d-119">Docker-Unterstützung hinzufügen</span><span class="sxs-lookup"><span data-stu-id="77d8d-119">Add Docker support</span></span>

<span data-ttu-id="77d8d-120">Sie können Docker-Unterstützung zu einem vorhandenen .NET Core Web-app-Projekt hinzufügen, indem Sie die Auswahl **hinzufügen** > **Docker-Unterstützung** in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77d8d-120">You can add Docker support to an existing .NET Core web app project by selecting **Add** > **Docker Support** in **Solution Explorer**.</span></span> <span data-ttu-id="77d8d-121">Sie können auch Docker-Unterstützung während der projekterstellung aktivieren, indem Sie auswählen **Aktivieren der Unterstützung für Docker** in die **neue ASP.NET Core-Webanwendung** geöffnet, nachdem Sie auf **OK** in die **neues Projekt** Dialogfeld wie in Abbildung 4-27 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="77d8d-121">You can also enable Docker support during project creation by selecting **Enable Docker Support** in the **New ASP.NET Core Web Application** dialog box that opens after you click **OK** in the **New Project** dialog box, as shown in Figure 4-27.</span></span>

![Aktivieren von Docker-Unterstützung für neue ASP.NET Core-Web-app in Visual Studio](./media/enable-docker-support-visual-studio.png)

<span data-ttu-id="77d8d-123">Abbildung 4-27: Aktivieren von Docker-Unterstützung während der projekterstellung in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="77d8d-123">Figure 4-27: Enable Docker support during project creation in Visual Studio 2017</span></span>

<span data-ttu-id="77d8d-124">Wenn Sie hinzufügen oder Docker-Unterstützung aktivieren, fügt Visual Studio eine *dockerfile-Datei* Datei zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="77d8d-124">When you add or enable Docker support, Visual Studio adds a *Dockerfile* file to the project.</span></span>

> [!NOTE]
> <span data-ttu-id="77d8d-125">Wenn Sie Docker Compose-Unterstützung während der projekterstellung für ein .NET Framework Web-app-Projekt (kein .NET Core Web-app-Projekt) aktivieren, wie in Abbildung 4-28 dargestellt, wird auch Unterstützung für containerorchestrator hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="77d8d-125">When you enable Docker Compose support during project creation for a .NET Framework web app project (not a .NET Core web app project) as shown in Figure 4-28, container orchestrator support is also added.</span></span>
>
> ![Aktivieren von Docker compose-Unterstützung für ein .NET Framework-Web-app-Projekt](media/enable-docker-compose-support.png)

> <span data-ttu-id="77d8d-127">Abbildung 4-28: Aktivieren der Unterstützung für Docker Compose auf eine .NET Framework-Web-app-Projekt in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="77d8d-127">Figure 4-28: Enabling Docker Compose support on a .NET Framework web app project in Visual Studio 2017</span></span>

### <a name="add-container-orchestrator-support"></a><span data-ttu-id="77d8d-128">Unterstützung für containerorchestrator hinzufügen</span><span class="sxs-lookup"><span data-stu-id="77d8d-128">Add container orchestrator support</span></span>

<span data-ttu-id="77d8d-129">Wenn Sie eine Lösung mit mehreren Containern erstellen möchten, fügen Sie Unterstützung für containerorchestrator zu Ihren Projekten hinzu.</span><span class="sxs-lookup"><span data-stu-id="77d8d-129">When you want to compose a multicontainer solution, add container orchestrator support to your projects.</span></span> <span data-ttu-id="77d8d-130">Wenn Sie Unterstützung für containerorchestrator hinzufügen, fügt Visual Studio eine *dockerfile-Datei* zum Projekt (sofern nicht bereits vorhanden) und eine globale *"Docker-Compose.yml"* Datei auf Projektmappenebene.</span><span class="sxs-lookup"><span data-stu-id="77d8d-130">When you add container orchestrator support, Visual Studio adds a *Dockerfile* to the project (if it doesn't already exist) and a global *docker-compose.yml* file at the solution level.</span></span> <span data-ttu-id="77d8d-131">Dadurch können Sie die ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit, wenn sie in der gleichen definiert *"Docker-Compose.yml"* Datei.</span><span class="sxs-lookup"><span data-stu-id="77d8d-131">This lets you run and debug a group of containers (a whole solution) at the same time if they're defined in the same *docker-compose.yml* file.</span></span> <span data-ttu-id="77d8d-132">Wenn *"Docker-Compose.yml"* bereits vorhanden ist, Visual Studio fügt nur die erforderlichen Zeilen Konfigurationscode hinzu.</span><span class="sxs-lookup"><span data-stu-id="77d8d-132">If *docker-compose.yml* already exists, Visual Studio just adds the required lines of configuration code to it.</span></span>

<span data-ttu-id="77d8d-133">Nachdem Sie die Orchestrierung von containerunterstützung zu Ihrem Projekt hinzufügen, werden Sie sehen eine dockerfile-Datei dem Projekt hinzugefügt und ein **Docker-compose-** hinzugefügt, um die Projektmappe im Ordner **Projektmappen-Explorer**, wie in Abbildung 4-29 dargestellt:</span><span class="sxs-lookup"><span data-stu-id="77d8d-133">After you add container orchestration support to your project, you see a Dockerfile added to the project and a **docker-compose** folder added to the solution in **Solution Explorer**, as shown in Figure 4-29:</span></span>

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

<span data-ttu-id="77d8d-135">Abbildung 4-29: Docker-Dateien im Projektmappen-Explorer in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="77d8d-135">Figure 4-29: Docker files in Solution Explorer in Visual Studio 2017</span></span>

<span data-ttu-id="77d8d-136">**Weitere Informationen:** finden Sie weitere Informationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="77d8d-136">**More information:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="77d8d-137">Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="77d8d-137">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="77d8d-138">Bereitstellen eines ASP.NET Core-Docker-Containers in einer containerregistrierung an: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="77d8d-138">Deploy an ASP.NET Core Docker container to a container registry: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="77d8d-139">[Zurück](docker-apps-inner-loop-workflow.md)
[Weiter](set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="77d8d-139">[Previous](docker-apps-inner-loop-workflow.md)
[Next](set-up-windows-containers-with-powershell.md)</span></span>