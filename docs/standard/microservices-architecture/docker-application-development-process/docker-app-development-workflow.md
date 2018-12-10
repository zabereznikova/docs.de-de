---
title: Entwicklungsworkflow für Docker-Apps
description: .NET Microservices-Architektur für .NET-Containeranwendungen | Entwicklungsworkflow für Docker-Apps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/05/2018
ms.openlocfilehash: bc6b1796ed7b12a04affc521ac2efee515c48ae2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150549"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="ebdcd-103">Entwicklungsworkflow für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="ebdcd-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="ebdcd-104">Der Lebenszyklus der Anwendungsentwicklung beginnt am Computer eines Entwicklers, an dem dieser die Anwendung mithilfe seiner bevorzugten Sprache codiert und lokal testet.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-104">The application development life cycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="ebdcd-105">Unabhängig davon, welche Sprache, welches Framework und welche Plattform die Entwickler wählen, entwickeln und testen sie mit diesem Workflow Docker-Container stets lokal.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="ebdcd-106">Jeder Container (eine Instanz eines Docker-Images) umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-106">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="ebdcd-107">Eine Betriebssystemauswahl (z.B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

- <span data-ttu-id="ebdcd-108">Dateien, die vom Entwickler hinzugefügt wurden (Anwendungsbinärdateien usw.).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-108">Files added by the developer (application binaries, etc.).</span></span>

- <span data-ttu-id="ebdcd-109">Konfigurationsinformationen (Umgebungseinstellungen und Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="ebdcd-110">Workflow für die Entwicklung von Docker-Container-basierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="ebdcd-111">In diesem Abschnitt wird der *Entwicklungsworkflow* für Docker-Container-basierte Anwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="ebdcd-112">Der Entwicklungsworkflow berücksichtigt den größeren DevOps-Workflow nicht und konzentriert sich nur auf die Entwicklungsarbeit, die am Computer des Entwicklers vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="ebdcd-113">Die ersten Schritte zum Einrichten der Umgebung wurden nicht berücksichtigt, da diese nur einmal durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="ebdcd-114">Eine Anwendung besteht aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="ebdcd-115">Im Folgenden sind die grundlegenden Schritte dargestellt, die Sie normalerweise beim Erstellen einer Docker-Anwendung ausführen, wie in Abbildung 5-1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![Grafik: Workflowschritte für die Entwicklung von Containeranwendungen für Docker](./media/image1.png)

<span data-ttu-id="ebdcd-117">**Abbildung 5-1.**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-117">**Figure 5-1.**</span></span> <span data-ttu-id="ebdcd-118">Workflowschritte für die Entwicklung von Containeranwendungen für Docker</span><span class="sxs-lookup"><span data-stu-id="ebdcd-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="ebdcd-119">In diesem Handbuch wird der gesamte Prozess ausführlich beschrieben, und jeder wichtige Schritt wird unter besonderer Berücksichtigung einer Visual Studio-Umgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="ebdcd-120">Bei Verwendung eines Editor-/CLI-Entwicklungsansatzes (z.B. Visual Studio Code plus Docker-CLI auf MacOS oder Windows) müssen Sie die einzelnen Schritte in der Regel detaillierter kennen als bei Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="ebdcd-121">Weitere Informationen zum Arbeiten in einer CLI-Umgebung finden Sie im E-Book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Lebenszyklus von Docker-Containeranwendungen mit Microsoft-Plattformen und Tools)](https://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-121">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="ebdcd-122">Wenn Sie Visual Studio verwenden, werden viele dieser Schritte für Sie ausgeführt, wodurch sich Ihre Produktivität entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-122">When you're using Visual Studio, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="ebdcd-123">Dies gilt insbesondere, Visual Studio 2017 verwenden und Anwendungen mit mehreren Containern das Ziel sind.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="ebdcd-124">Visual Studio fügt beispielsweise mit nur einem Mausklick die Dateien *Dockerfile* und *docker-compose.yml* mit der Konfiguration für Ihre Anwendung Ihren Projekten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-124">For instance, with just one mouse click, Visual Studio adds the *Dockerfile* and *docker-compose.yml* files to your projects with the configuration for your application.</span></span> <span data-ttu-id="ebdcd-125">Wenn Sie die Anwendung in Visual Studio ausführen, wird das Docker-Image erstellt, und die Anwendung mit mehreren Containern wird direkt in Docker ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker.</span></span> <span data-ttu-id="ebdcd-126">Sie haben sogar die Möglichkeit, mehrere Container auf einmal zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-126">It even allows you to debug several containers at once.</span></span> <span data-ttu-id="ebdcd-127">Diese Features erhöhen Ihre Entwicklungsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-127">These features boost your development speed.</span></span>

<span data-ttu-id="ebdcd-128">In der folgenden Anleitung wird erklärt, was im Hintergrund mit Docker passiert.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-128">In the guidance that follows, we explain what's happening "under the covers" with Docker.</span></span>

![Grafik: Schritt 1: Codieren Ihrer Anwendung](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="ebdcd-130">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-130">Step 1.</span></span> <span data-ttu-id="ebdcd-131">Beginnen Sie mit dem Codieren, und erstellen Sie eine erste Anwendungs- oder Dienstbaseline</span><span class="sxs-lookup"><span data-stu-id="ebdcd-131">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="ebdcd-132">Das Entwickeln einer Docker-Anwendung ist mit der Art und Weise vergleichbar, wie Anwendungen ohne Docker entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-132">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="ebdcd-133">Der Unterschied besteht darin, dass Sie beim Entwickeln für Docker eine Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-133">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="ebdcd-134">Bei dem Container kann es sich um einen Linux-Container oder einen Windows-Container handeln.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-134">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="ebdcd-135">Einrichten der lokalen Umgebung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="ebdcd-136">Stellen Sie zuerst sicher, dass [Docker Community Edition (CE)](https://www.docker.com/community-edition) für Windows wie nachfolgend erläutert installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-136">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="ebdcd-137">Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)</span><span class="sxs-lookup"><span data-stu-id="ebdcd-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="ebdcd-138">Zudem benötigen Sie Visual Studio 2017 mit installierter Workload für die **plattformübergreifende .NET Core-Entwicklung**, wie in Abbildung 5-2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-138">In addition, you need Visual Studio 2017 with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="ebdcd-139">**Abbildung 5-2**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-139">**Figure 5-2**.</span></span> <span data-ttu-id="ebdcd-140">Auswählen der **.NET Core und Docker**-Workload während der Installation von Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ebdcd-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="ebdcd-141">Sie können sogar vor dem Aktivieren von Docker in der Anwendung und Bereitstellen und Testen in Docker mit dem Codieren der Anwendung im einfachen .NET (normalerweise in .NET Core, wenn Sie Container verwenden möchten) beginnen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="ebdcd-142">Allerdings wird empfohlen, dass Sie so bald wie möglich mit Docker arbeiten, d.h. in der realen Umgebung, sodass etwaige Probleme schnellstmöglich erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="ebdcd-143">Dies wird empfohlen, da Visual Studio die Arbeit mit Docker so sehr erleichtert, dass sie fast transparent erscheint – insbesondere beim Debuggen von Anwendungen mit mehreren Containern über Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent — the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-144">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-144">Additional resources</span></span>

- <span data-ttu-id="ebdcd-145">**Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-145">**Get started with Docker CE for Windows**</span></span>

   [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="ebdcd-146">**Visual Studio 2017**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-146">**Visual Studio 2017**</span></span>

   [*https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![Grafik: Schritt 2: Schreiben von Dockerfile-Dateien](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="ebdcd-148">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="ebdcd-148">Step 2.</span></span> <span data-ttu-id="ebdcd-149">Erstellen Sie eine Dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basisimage</span><span class="sxs-lookup"><span data-stu-id="ebdcd-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="ebdcd-150">Für jedes benutzerdefinierte Image, das Sie erstellen möchten, benötigen Sie eine Dockerfile-Datei. Außerdem benötigen Sie eine Dockerfile-Datei für jeden bereitzustellenden Container, unabhängig davon, ob Sie automatisch über Visual Studio oder manuell mithilfe der Docker-CLI bereitstellen (Befehle „docker run“ und „docker-compose“).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="ebdcd-151">Wenn Ihre Anwendung einen benutzerdefinierten Dienst enthält, benötigen Sie eine einzelne Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="ebdcd-152">Wenn Ihre Anwendung mehrere Dienste enthält (wie in einer Microservicearchitektur), benötigen Sie pro Dienst eine Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="ebdcd-153">Die Dockerfile-Datei befindet sich im Stammordner der Anwendung oder des Diensts.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="ebdcd-154">Sie enthält die Befehle, die Docker mitteilen, wie die Anwendung oder der Dienst in einem Container eingerichtet und ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="ebdcd-155">Sie können eine Dockerfile-Datei manuell im Code erstellen und mit Ihren .NET-Abhängigkeiten Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="ebdcd-156">Mit Visual Studio-Tools für Docker erledigen Sie diese Aufgabe mit nur wenigen Mausklicks.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-156">With Visual Studio Tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="ebdcd-157">Beim Erstellen eines neuen Projekts in Visual Studio 2017 ist die Option **Enable Docker Support** (Docker-Unterstützung aktivieren) verfügbar, wie in Abbildung 5-3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-157">When you create a new project in Visual Studio 2017, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Aktivieren der Unterstützung für Docker beim Erstellen eines neuen Projekts in Visual Studio 2017](./media/image5.png)

<span data-ttu-id="ebdcd-159">**Abbildung 5-3**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-159">**Figure 5-3**.</span></span> <span data-ttu-id="ebdcd-160">Aktivieren der Unterstützung für Docker beim Erstellen eines neuen Projekts in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ebdcd-160">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="ebdcd-161">Sie können die Docker-Unterstützung auch für ein vorhandenes .NET Core-Web-App-Projekt aktivieren, indem Sie mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** klicken und **Hinzufügen** > **Docker-Unterstützung** auswählen, wie in Abbildung 5-4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-161">You can also enable Docker support on an existing .NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Menüoption „Add Docker support“ (Docker-Unterstützung hinzufügen) in Visual Studio](./media/add-docker-support.png)

<span data-ttu-id="ebdcd-163">**Abbildung 5-4**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-163">**Figure 5-4**.</span></span> <span data-ttu-id="ebdcd-164">Aktivieren der Unterstützung für Docker in einem vorhandenen Visual Studio 2017-Projekt</span><span class="sxs-lookup"><span data-stu-id="ebdcd-164">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="ebdcd-165">Durch diesen Vorgang wird dem Projekt eine *Dockerfile-Datei* mit der erforderlichen Konfiguration hinzugefügt, die nur für .NET Core-Web-App-Projekte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-165">This action adds a *Dockerfile* to the project with the required configuration, and is only available on .NET Core web app projects.</span></span>

<span data-ttu-id="ebdcd-166">Klicken Sie zum Hinzufügen einer *docker-compose.yml*-Datei für die gesamte Projektmappe mit der rechten Maustaste im **Projektmappen-Explorer** auf das Projekt, und klicken Sie auf **Hinzufügen** > **Containerorchestrator-Unterstützung**, wie in Abbildung 5-5 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-166">To add a *docker-compose.yml* file for the whole solution, right-click on the project in **Solution Explorer** and select **Add** > **Container Orchestrator Support**, as shown in Figure 5-5.</span></span>

![Menüoption zum Hinzufügen der Containerorchestrator-Unterstützung in Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="ebdcd-168">**Abbildung 5-5**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-168">**Figure 5-5**.</span></span> <span data-ttu-id="ebdcd-169">Hinzufügen der Containerorchestrator-Unterstützung zu einem vorhandenen Projekt in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-169">Adding container orchestrator support to an existing project in Visual Studio 2017.</span></span>

<span data-ttu-id="ebdcd-170">In den folgenden Abschnitten werden die Informationen beschrieben, die in diese Dateien übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-170">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="ebdcd-171">Obwohl Visual Studio Ihnen diese Aufgabe abnehmen kann, ist es ist wichtig zu wissen, was in eine Dockerfile-Datei übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-171">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="ebdcd-172">Option A: Erstellen eines Projekts mit einem vorhandenen offiziellen .NET Docker-Image</span><span class="sxs-lookup"><span data-stu-id="ebdcd-172">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="ebdcd-173">Sie erstellen ein benutzerdefiniertes Image für den Container in der Regel auf einem Basisimage, das Sie von einem offiziellen-Repository in der [Docker-Hub](https://hub.docker.com/)-Registrierung erhalten.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-173">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="ebdcd-174">Das ist genau das, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-174">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="ebdcd-175">Die Dockerfile-Datei verwendet ein vorhandenes aspnetcore-Image.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-175">The Dockerfile uses an existing aspnetcore image.</span></span>

<span data-ttu-id="ebdcd-176">Es wurde bereits erläutert, welche Docker-Images und Repositorys Sie abhängig vom Framework und Betriebssystem, das Sie ausgewählt haben, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-176">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="ebdcd-177">Wenn Sie beispielsweise ASP.NET Core (Linux oder Windows) verwenden möchten, muss das Image microsoft/aspnetcore:2.0 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-177">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="ebdcd-178">Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages Sie für den Container verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-178">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="ebdcd-179">Fügen Sie zu diesem Zweck FROM microsoft/aspnetcore:2.0 in die Dockerfile-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-179">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="ebdcd-180">Dies wird zwar automatisch von Visual Studio ausgeführt, aber wenn Sie die Version aktualisieren, müssen Sie auch diesen Wert aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-180">This is automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="ebdcd-181">Durch Verwendung eines offiziellen .NET Image-Repositorys von Docker-Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-181">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="ebdcd-182">Das folgende Beispiel veranschaulicht eine Dockerfile-Beispieldatei für einen ASP.NET Core-Container.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-182">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0

ARG source

WORKDIR /app

EXPOSE 80

COPY ${source:-obj/Docker/publish} .

ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="ebdcd-183">In diesem Fall basiert der Container auf Version 2.0 des offiziellen ASP.NET Core-Docker-Images (Multi-Arch für Linux und Windows).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-183">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="ebdcd-184">Dies ist die Einstellung `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-184">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="ebdcd-185">(Weitere Informationen zu diesem Basisimage finden Sie unter [ASP.NET Core Docker Image (ASP.NET Core-Docker-Image)](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/r/microsoft/dotnet/).) In der Dockerfile-Datei müssen Sie auch angeben, dass Docker an dem TCP-Port lauscht, den Sie zur Runtime verwenden (in diesem Fall Port 80 gemäß Konfiguration mit der EXPOSE-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-185">(For more information about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="ebdcd-186">Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-186">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="ebdcd-187">Beispielsweise weist die ENTRYPOINT-Zeile mit \["dotnet", "MySingleContainerWebApp.dll"\] Docker an, eine .NET Core-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-187">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="ebdcd-188">Wenn Sie das SDK und die .NET Core-CLI (Dotnet CLI) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-188">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="ebdcd-189">Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen je nach Sprache und Plattform variieren können, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-189">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-190">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-190">Additional resources</span></span>

- <span data-ttu-id="ebdcd-191">**Erstellen von Docker-Images für .NET Core-Anwendungen**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-191">**Building Docker Images for .NET Core Applications**</span></span>

   [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="ebdcd-192">**Build your own image (Entwickeln eines eigenen Images)**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-192">**Build your own image**.</span></span> <span data-ttu-id="ebdcd-193">In der offiziellen Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-193">In the official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="ebdcd-194">Verwenden von Repositorys für Images für mehrere Architekturen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-194">Using multi-arch image repositories</span></span>

<span data-ttu-id="ebdcd-195">Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-195">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="ebdcd-196">Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-196">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="ebdcd-197">Das in der Docker-Hub-Registrierung verfügbare [Microsoft/Dotnet](https://hub.docker.com/r/microsoft/aspnetcore/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Repositoryname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-197">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="ebdcd-198">Wenn Sie ein explizites Tag für eine bestimmte Plattform angeben, wie in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-198">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- <span data-ttu-id="ebdcd-199">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-199">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

- <span data-ttu-id="ebdcd-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="ebdcd-201">Neu seit Mitte 2017 ist jedoch, dass die neuen Images für mehrere Architekturen (z.B. das aspnetcore-Image, das mehrere Architekturen unterstützt) bei Angabe des gleichen Imagenamens, auch mit dem gleichen Tag, je nach dem von Ihnen bereitgestellten Docker-Host-Betriebssystem die Linux- oder die Windows-Version verwenden, was im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-201">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image, which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

- <span data-ttu-id="ebdcd-202">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-202">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="ebdcd-203">Wenn Sie also ein Image von einem Windows-Host pullen, wird die Windows-Variante gepullt. Wenn der gleiche Imagename von einem Linux-Host gepullt wird, wird die Linux-Variante gepullt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-203">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="ebdcd-204">Option B: Neuerstellung des Basisimages</span><span class="sxs-lookup"><span data-stu-id="ebdcd-204">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="ebdcd-205">Sie können ein eigenes Docker-Basisimage von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-205">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="ebdcd-206">Dieses Szenario wird Docker-Einsteigern nicht empfohlen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-206">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-207">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-207">Additional resources</span></span>

- <span data-ttu-id="ebdcd-208">**Multi-arch .NET Core images (.NET Core-Images für mehrere Architekturen)**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-208">**Multi-arch .NET Core images**.</span></span>

   https://github.com/dotnet/announcements/issues/14

- <span data-ttu-id="ebdcd-209">**Create a base image (Erstellen eines Basisimages)**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-209">**Create a base image**.</span></span> <span data-ttu-id="ebdcd-210">Offizielle Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-210">Official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![Grafik: Schritt 3: Erstellen von Images](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="ebdcd-212">Schritt 3</span><span class="sxs-lookup"><span data-stu-id="ebdcd-212">Step 3.</span></span> <span data-ttu-id="ebdcd-213">Erstellen Sie Ihre benutzerdefinierten Docker-Images, und betten Sie Ihre Anwendung oder Ihren Dienst in diese ein</span><span class="sxs-lookup"><span data-stu-id="ebdcd-213">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="ebdcd-214">Sie müssen für jeden Dienst in Ihrer Anwendung ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-214">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="ebdcd-215">Wenn Ihre Anwendung aus einem einzelnen Dienst oder einer einzelnen Webanwendung besteht, benötigen Sie nur ein Image.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-215">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="ebdcd-216">Die Docker-Images werden in Visual Studio automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-216">The Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="ebdcd-217">Die folgenden Schritte sind nur für den Editor-/CLI-Workflow und zur Erläuterung der Vorgänge, die im Hintergrund ablaufen, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-217">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="ebdcd-218">Als Entwickler entwickeln und testen Sie so lange lokal, bis Sie ein abgeschlossenes Feature pushen oder zu Ihrem Quellkontrollsystem wechseln (z.B. zu GitHub).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-218">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="ebdcd-219">Dies bedeutet, dass Sie die Docker-Images erstellen und Container auf einem lokalen Docker-Host (Windows- oder Linux-VM) bereitstellen und für die lokalen Container ausführen, testen und debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-219">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="ebdcd-220">Mithilfe des Befehls „docker build“ können Sie, wie in Abbildung 5-5 gezeigt, unter Verwendung der Docker-CLI und Ihrer Dockerfile-Datei ein benutzerdefiniertes Image in Ihrer lokalen Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-220">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Erstellen eines benutzerdefinierten Docker-Images](./media/image8.png)

<span data-ttu-id="ebdcd-222">**Abbildung 5-5**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-222">**Figure 5-5**.</span></span> <span data-ttu-id="ebdcd-223">Erstellen eines benutzerdefinierten Docker-Images</span><span class="sxs-lookup"><span data-stu-id="ebdcd-223">Creating a custom Docker image</span></span>

<span data-ttu-id="ebdcd-224">Optional können Sie, anstatt „docker build“ über den Projektordner direkt auszuführen, zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken und Binärdateien generieren, indem Sie erst „dotnet publish“ ausführen und dann den Befehl „docker build“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-224">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="ebdcd-225">Dadurch wird ein Docker-Image mit dem Namen **cesardl/netcore-webapi-microservice-docker:first** erstellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-225">This will create a Docker image with the name **cesardl/netcore-webapi-microservice-docker:first**.</span></span> <span data-ttu-id="ebdcd-226">In diesem Fall ist :first ein Tag, das eine bestimmte Version darstellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-226">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="ebdcd-227">Sie können diesen Schritt für jedes benutzerdefinierte Image wiederholen, das Sie für Ihre zusammengesetzte Docker-Anwendung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-227">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="ebdcd-228">Wenn eine Anwendung aus mehreren Containern besteht (d.h. es handelt sich um eine Anwendung mit mehreren Containern), können Sie auch den Befehl „docker-compose up --build“ verwenden, um alle zugehörigen Images mit einem Befehl unter Verwendung der in den zugehörigen docker-compose.yml-Dateien verfügbar gemachten Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-228">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="ebdcd-229">Sie können die vorhandenen Images in Ihrem lokalen Repository suchen, indem Sie den „docker images“-Befehl, wie in Abbildung 5-6 dargestellt, verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-229">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Anzeigen vorhandener Images mithilfe des Befehls „docker images“](./media/image9.png)

<span data-ttu-id="ebdcd-231">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-231">**Figure 5-6.**</span></span> <span data-ttu-id="ebdcd-232">Anzeigen vorhandener Images mithilfe des Befehls „docker images“</span><span class="sxs-lookup"><span data-stu-id="ebdcd-232">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="ebdcd-233">Erstellen von Docker-Images mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-233">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="ebdcd-234">Wenn Sie Visual Studio zum Erstellen eines Projekts mit Docker-Unterstützung verwenden, erstellen Sie nicht explizit ein Image.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-234">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="ebdcd-235">Stattdessen wird das Image für Sie erstellt, wenn Sie **F5** drücken und die dockerisierte Anwendung oder den dockerisierten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-235">Instead, the image is created for you when you press **F5** to run the dockerized application or service.</span></span> <span data-ttu-id="ebdcd-236">Dieser Schritt wird in Visual Studio automatisch und für Sie nicht erkennbar ausgeführt, aber es ist wichtig, dass Sie wissen, was im Hintergrund passiert.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-236">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Grafik: Schritt 4: Definieren von Diensten](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="ebdcd-238">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-238">Step 4.</span></span> <span data-ttu-id="ebdcd-239">Definieren Sie Ihre Dienste in der Datei docker-compose.yml beim Erstellen einer Docker-Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="ebdcd-239">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="ebdcd-240">Mithilfe der Datei [docker compose.yml](https://docs.docker.com/compose/compose-file/) können Sie mehrere verwandte Dienste definieren, die als zusammengesetzte Anwendung mit Bereitstellungsbefehlen bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-240">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="ebdcd-241">Wenn Sie eine docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in Ihrem Haupt- oder Stammlösungsordner mit Inhalt erstellen, der mit dem in dem folgenden Beispiel verwendeten vergleichbar ist:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-241">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="ebdcd-242">Diese „docker-compose.yml“-Datei ist eine vereinfachte und zusammengeführte Version.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-242">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="ebdcd-243">Sie enthält die statischen Konfigurationsdaten für jeden Container (z.B. den Namen des benutzerdefinierten Images), das stets anwendbar sind, sowie Konfigurationsinformationen, die sich nach der Bereitstellungsumgebung richten können, z.B. die Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-243">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="ebdcd-244">In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der docker-compose.yml-Datei in mehrere docker-compose-Dateien aufteilen und Werte je nach Umgebung und Ausführungstyp (Debug oder Release) außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-244">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="ebdcd-245">Im Beispiel der Datei „docker-compose.yml“ werden vier Dienste definiert: der webmvc-Dienst (Webanwendung), zwei Microservices (catalog.api und ordering.api) und ein Datenquellcontainer, sql.data, basierend auf von als Container ausgeführtem SQL Server für Linux.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-245">The docker-compose.yml file example defines four services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="ebdcd-246">Da jeder Dienst als ein Container bereitgestellt wird, ist für jeden ein Docker-Image erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-246">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="ebdcd-247">Die docker-compose.yml-Datei gibt nicht nur an, welche Container verwendet werden, sondern auch, wie diese einzeln konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-247">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="ebdcd-248">Die webmvc-Containerdefinition in der .yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-248">For instance, the webmvc container definition in the .yml file:</span></span>

- <span data-ttu-id="ebdcd-249">Verwendet ein vorab erstelltes eshop/web:latest-Image.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-249">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="ebdcd-250">Sie können jedoch das als Teil der docker-compose-Ausführung zu erstellende Image mit einer zusätzlichen, auf einem build:-Abschnitt in der docker-compose-Datei basierenden Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-250">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="ebdcd-251">Initialisiert die beiden Umgebungsvariablen (CatalogUrl und OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-251">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="ebdcd-252">Leitet den verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer weiter.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-252">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="ebdcd-253">Verknüpft die Web-App mit dem Katalog- und Bestelldienst mit der depends\_-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-253">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="ebdcd-254">Dies bewirkt, dass der Dienst wartet, bis diese Dienste gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-254">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="ebdcd-255">Wir gehen in einem der folgenden Abschnitte erneut auf die Datei docker-compose.yml ein, wenn wir uns damit beschäftigen, wie Microservices und Apps mit mehreren Containern implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-255">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="ebdcd-256">Arbeiten mit docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ebdcd-256">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="ebdcd-257">Wenn Sie einem Web-App-Projekt Containerorchestrator-Unterstützung hinzufügen, wie in Abbildung 5-7 gezeigt, fügt Visual Studio der Projektmappe einen Dienstbereich (Projekt) hinzu, der eine „docker-compose.yml“-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-257">When you add container orchestrator support to a web app project, as shown in Figure 5-7, Visual Studio adds a service section (project) to the solution that contains a docker-compose.yml file.</span></span> <span data-ttu-id="ebdcd-258">So kann eine Projektmappe mit mehreren Containern auf einfache Weise erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-258">This is an easy way to start composing a multiple-container solution.</span></span>

![Menüelement zum Hinzufügen der Containerorchestrator-Unterstützung in Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="ebdcd-260">**Abbildung 5-7**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-260">**Figure 5-7**.</span></span> <span data-ttu-id="ebdcd-261">Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein ASP.NET Core-Projekt</span><span class="sxs-lookup"><span data-stu-id="ebdcd-261">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="ebdcd-262">Durch Hinzufügen der Containerorchestrator-Unterstützung wird die Dockerfile-Datei Ihrem Projekt hinzugefügt (sofern nicht bereits vorhanden).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-262">Adding container orchestrator support adds the Dockerfile to your project (if it doesn't already exist).</span></span> <span data-ttu-id="ebdcd-263">Außerdem werden Konfigurationsinformationen einer globalen „docker-compose.yml“-Datei auf Projektmappenebene hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-263">It also adds configuration information to a global docker-compose.yml file at the solution level.</span></span> <span data-ttu-id="ebdcd-264">Sie sehen dann einen neuen Projektknoten (die *docker-compose.dcproj*-Projektdatei) im **Projektmappen-Explorer**, der die „docker-compose.yml“-Datei enthält, wie in Abbildung 5-8 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-264">You'll see a new project node (the *docker-compose.dcproj* project file) in **Solution Explorer** that contains the docker-compose.yml file, as shown in Figure 5-8.</span></span>

![Knoten „docker-compose“ im Projektmappen-Explorer](./media/docker-compose-files.png)

<span data-ttu-id="ebdcd-266">**Abbildung 5-8**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-266">**Figure 5-8**.</span></span> <span data-ttu-id="ebdcd-267">Der im Projektmappen-Editor in Visual Studio 2017 hinzugefügte **docker-compose**-Strukturknoten</span><span class="sxs-lookup"><span data-stu-id="ebdcd-267">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="ebdcd-268">Sie können dann die „docker-compose.yml“-Datei öffnen und sie mit zusätzlichen Features aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-268">You can then open the docker-compose.yml file and update it with additional features.</span></span>

<span data-ttu-id="ebdcd-269">Eine Anwendung mit mehreren Containern kann unter Verwendung des Befehls `docker-compose up` mit einer einzelnen „docker-compose.yml“-Datei bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-269">You can deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span>

![Grafik: Schritt 5: Ausführen einer Anwendung](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="ebdcd-271">Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-271">Step 5.</span></span> <span data-ttu-id="ebdcd-272">Erstellen Sie Ihre Docker-Anwendung, und führen Sie sie aus</span><span class="sxs-lookup"><span data-stu-id="ebdcd-272">Build and run your Docker application</span></span>

<span data-ttu-id="ebdcd-273">Wenn die Anwendung nur über einen einzelnen Container verfügt, können Sie sie ausführen, indem Sie sie auf dem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-273">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="ebdcd-274">Enthält Ihre Anwendung dagegen mehrere Dienste, können Sie sie als zusammengesetzte Anwendung bereitstellen, indem Sie entweder einen einzelnen CLI-Befehl (docker-compose up) oder Visual Studio verwenden, wobei der Befehl dann im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-274">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="ebdcd-275">Betrachten wir die unterschiedlichen Optionen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-275">Let’s look at the different options.</span></span>

### <a name="option-a-run-a-single-container-app"></a><span data-ttu-id="ebdcd-276">Option A: Ausführen einer Anwendung mit einem Container</span><span class="sxs-lookup"><span data-stu-id="ebdcd-276">Option A: Run a single-container app</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="ebdcd-277">Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="ebdcd-277">Docker CLI</span></span>

<span data-ttu-id="ebdcd-278">Sie können einen Docker-Container mit dem Befehl „docker run“, wie in Abbildung 5-9 dargestellt, ausführen:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-278">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![Ausführen eines Docker-Containers mithilfe des Befehls „docker run“](./media/image13.png)

<span data-ttu-id="ebdcd-280">**Abbildung 5-9**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-280">**Figure 5-9**.</span></span> <span data-ttu-id="ebdcd-281">Ausführen eines Docker-Containers mithilfe des Befehls „docker run“</span><span class="sxs-lookup"><span data-stu-id="ebdcd-281">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="ebdcd-282">In diesem Fall bindet der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-282">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="ebdcd-283">Dies bedeutet, dass der Host an Port 80 lauscht und an Port 5000 des Containers weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-283">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="ebdcd-284">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-284">Visual Studio</span></span>

<span data-ttu-id="ebdcd-285">Wenn Sie die Containerorchestrator-Unterstützung nicht hinzugefügt haben, können Sie auch eine Anwendung mit einem Container in Visual Studio ausführen, indem Sie **F5** drücken.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-285">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **F5**.</span></span> <span data-ttu-id="ebdcd-286">Der Container wird lokal mit „docker run“ ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-286">The container runs locally using docker run.</span></span>

### <a name="option-b-run-a-multi-container-app"></a><span data-ttu-id="ebdcd-287">Option B: Ausführen einer Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="ebdcd-287">Option B: Run a multi-container app</span></span>

<span data-ttu-id="ebdcd-288">In den meisten Unternehmensszenarios setzt sich eine Docker-Anwendung aus mehreren Diensten zusammen. Dies bedeutet, dass Sie eine Anwendung mit mehreren Containern, wie in Abbildung 5-10 dargestellt, ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-288">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Grafik: VM mit bereitgestellten Docker-Containern](./media/image14.png)

<span data-ttu-id="ebdcd-290">**Abbildung 5-10**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-290">**Figure 5-10**.</span></span> <span data-ttu-id="ebdcd-291">VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="ebdcd-291">VM with Docker containers deployed</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="ebdcd-292">Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="ebdcd-292">Docker CLI</span></span>

<span data-ttu-id="ebdcd-293">Zum Ausführen einer Anwendung mit mehreren Containern mithilfe der Docker-CLI können Sie den Befehl „docker-compose up“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-293">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="ebdcd-294">Dieser Befehl stellt mithilfe der docker-compose.yml-Datei, die auf Projektmappenebene verfügbar ist, eine Anwendung mit mehreren Containern bereit.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-294">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="ebdcd-295">Abbildung 5-11 zeigt die Ergebnisse an, wenn der Befehl aus Ihrem Hauptprojektverzeichnis ausgeführt wird, das die docker-compose.yml-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-295">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“](./media/image15.png)

<span data-ttu-id="ebdcd-297">**Abbildung 5-11**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-297">**Figure 5-11**.</span></span> <span data-ttu-id="ebdcd-298">Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“</span><span class="sxs-lookup"><span data-stu-id="ebdcd-298">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="ebdcd-299">Nachdem der Befehl „docker-compose up“ ausgeführt wurde, werden die Anwendung und ihre zugehörigen Container in Ihrem Docker-Host bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-299">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="ebdcd-300">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-300">Visual Studio</span></span>

<span data-ttu-id="ebdcd-301">Das Ausführen einer Anwendung mit mehreren Containern mit Visual Studio 2017 ist einfach.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-301">Running a multi-container application using Visual Studio 2017 is simple.</span></span> <span data-ttu-id="ebdcd-302">Sie können nicht nur die Anwendung mit mehreren Containern ausführen, sondern alle Container direkt in Visual Studio debuggen, indem Sie reguläre Haltepunkte festlegen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-302">Not only can you run the multi-container application, but you're able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="ebdcd-303">Wie bereits erwähnt, wird jedes Mal, wenn Sie einem Projekt in einer Projektmappe Containerorchestrator-Unterstützung hinzufügen, das Projekt in der globalen „docker-compose.yml“-Datei (Projektmappenebene) konfiguriert, wodurch Sie die gesamte Projektmappe auf einmal ausführen oder debuggen können.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-303">As mentioned before, each time you add container orchestrator support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="ebdcd-304">Visual Studio startet einen Container für jedes Projekt, für das die Docker-Projektmappenunterstützung aktiviert ist, und führt alle internen Schritte aus (dotnet publish, docker build usw.).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-304">Visual Studio will start one container for each project that has Docker solution support enabled and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="ebdcd-305">Wichtig dabei ist, dass Visual Studio 2017, wie in Abbildung 5-12 dargestellt, über einen zusätzlichen **Docker**-Befehl für die Aktion der **F5**-Taste verfügt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-305">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there's an additional **Docker** command for the **F5** key action.</span></span> <span data-ttu-id="ebdcd-306">Diese Option ermöglicht Ihnen, eine Anwendung mit mehreren Containern auszuführen oder zu debuggen, indem Sie alle in den docker-compose.yml-Dateien auf Projektmappenebene definierten Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-306">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="ebdcd-307">Die Möglichkeit, Lösungen mit mehreren Containern zu debuggen, bedeutet, das Sie mehrere Haltepunkte festlegen und jeden Haltepunkt in einem anderen Projekt (Container) festlegen können. Während des Debuggings in Visual Studio halten Sie an Haltepunkten an, die in verschiedenen Projekten definiert sind und in verschiedenen Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-307">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Ausführen von Apps mit mehreren Containern in Visual Studio 2017](./media/image16.png)

<span data-ttu-id="ebdcd-309">**Abbildung 5-12**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-309">**Figure 5-12**.</span></span> <span data-ttu-id="ebdcd-310">Ausführen von Apps mit mehreren Containern in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ebdcd-310">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-311">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-311">Additional resources</span></span>

-  <span data-ttu-id="ebdcd-312">**Bereitstellen eines ASP.NET-Containers mit einem Docker-Remotehost**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-312">**Deploy an ASP.NET container to a remote Docker host**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="ebdcd-313">Ein Hinweis zum Testen und Bereitstellen mit Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="ebdcd-313">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="ebdcd-314">Die Befehle „docker-compose up“ und „docker run“ (oder Ausführen und Debuggen der Container in Visual Studio) sind zum Testen von Containern in der Entwicklungsumgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-314">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="ebdcd-315">Sie sollten diese Methode jedoch nicht verwenden, wenn Docker-Cluster und Orchestratoren wie Docker Swarm, Mesosphere DC/OS oder Kubernetes als Ziel dienen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-315">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="ebdcd-316">Wenn Sie einen Cluster wie [Docker Swarm-Modus](https://docs.docker.com/engine/swarm/) (in Docker CE für Windows und Mac ab Version 1.12 verfügbar) verwenden, müssen Sie mit zusätzlichen Befehlen wie [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) für einzelne Dienste bereitstellen und testen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-316">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="ebdcd-317">Wenn Sie eine aus mehreren Containern bestehende Anwendung bereitstellen, verwenden Sie [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) und [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/), um die zusammengesetzte Anwendung als *Stapel* bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-317">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="ebdcd-318">Weitere Informationen finden Sie im Blogbeitrag [Introducing Experimental Distributed Application Bundles (Einführung in experimentelle verteilte Anwendungsbündel Bündel)](https://blog.docker.com/2016/06/docker-app-bundle/) in der Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-318">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="ebdcd-319">auf der Docker-Website.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-319">on the Docker site.</span></span>

<span data-ttu-id="ebdcd-320">Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) verwenden Sie ebenfalls unterschiedliche Bereitstellungsbefehle und Skripts.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-320">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![Grafik: Schritt 6](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="ebdcd-322">Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-322">Step 6.</span></span> <span data-ttu-id="ebdcd-323">Testen Sie die Docker-Anwendung mithilfe des lokalen Docker-Hosts</span><span class="sxs-lookup"><span data-stu-id="ebdcd-323">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="ebdcd-324">Dieser Schritt hängt davon ab, welche Vorgänge die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-324">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="ebdcd-325">In einer einfachen .NET Core-Webanwendung, die als einzelner Container oder Dienst bereitgestellt wird, können Sie auf den Dienst zugreifen, indem Sie einen Browser auf dem Docker-Host öffnen und, wie in Abbildung 5-13 gezeigt, zu dieser Site navigieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-325">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="ebdcd-326">(Wenn die Konfiguration in der Docker-Datei den Container einem anderen Port als Port 80 auf dem Host zuordnet, berücksichtigen Sie den Host-Port in der URL.)</span><span class="sxs-lookup"><span data-stu-id="ebdcd-326">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“](./media/image18.png)

<span data-ttu-id="ebdcd-328">**Abbildung 5-13**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-328">**Figure 5-13**.</span></span> <span data-ttu-id="ebdcd-329">Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“</span><span class="sxs-lookup"><span data-stu-id="ebdcd-329">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="ebdcd-330">Wenn „localhost“ nicht auf die Docker-Host-IP verweist (was bei Verwendung von Docker CE jedoch standardmäßig der Fall sein sollte), verwenden Sie die IP-Adresse der Netzwerkkarte Ihres Computers, um zum Dienst zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-330">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="ebdcd-331">Diese URL verwendet im Browser Port 80 für das besprochene Containerbeispiel.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-331">This URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="ebdcd-332">Allerdings werden intern die Anforderungen zu Port 5000 umgeleitet, da die Bereitstellung, wie in einem vorherigen Schritt beschrieben, mit dem Befehl „docker run“ erfolgte.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-332">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="ebdcd-333">Sie können die Anwendung auch mithilfe von „curl“ über das Terminal testen, was in Abbildung 5-14 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-333">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="ebdcd-334">Bei einer Docker-Installation unter Windows lautet die standardmäßige Docker-Host-IP zusätzlich zur eigentlichen IP-Adresse Ihres Computers stets 10.0.75.1.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-334">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“](./media/image19.png)

<span data-ttu-id="ebdcd-336">**Abbildung 5-14**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-336">**Figure 5-14**.</span></span> <span data-ttu-id="ebdcd-337">Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“</span><span class="sxs-lookup"><span data-stu-id="ebdcd-337">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="ebdcd-338">Testen und Debuggen von Containern mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ebdcd-338">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="ebdcd-339">Beim Ausführen und Debuggen des Containers mit Visual Studio 2017 können Sie die .NET-Anwendung in etwa so debuggen wie ohne Ausführung von Containern.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-339">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="ebdcd-340">Testen und Debuggen ohne Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-340">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="ebdcd-341">Wenn Sie mit dem Editor-/CLI-Ansatz entwickeln, ist das Debuggen von Containern schwieriger. Es ist ratsam zu debuggen, indem Traces generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-341">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-342">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-342">Additional resources</span></span>

- <span data-ttu-id="ebdcd-343">**Debuggen von Apps in einem lokalen Docker-Container**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-343">**Debugging apps in a local Docker container**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="ebdcd-344">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker (Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker).**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-344">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="ebdcd-345">Video.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-345">Video.</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="ebdcd-346">Vereinfachter Workflow bei der Entwicklung von Containern mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-346">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="ebdcd-347">Der Workflow bei Verwendung von Visual Studio ist wesentlich einfacher als bei Verwendung des Editor/CLI-Ansatzes.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-347">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="ebdcd-348">Die meisten der von Docker vorausgesetzten Schritte in Zusammenhang mit der Dockerfile-Datei und den docker-compose.yml-Dateien werden, wie in Abbildung 5-15 gezeigt, von Visual Studio ausgeblendet oder vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-348">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Vereinfachter Workflow bei der Entwicklung mit Visual Studio](./media/image20.png)

<span data-ttu-id="ebdcd-350">**Abbildung 5-15**.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-350">**Figure 5-15**.</span></span> <span data-ttu-id="ebdcd-351">Vereinfachter Workflow bei der Entwicklung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebdcd-351">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="ebdcd-352">Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-352">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="ebdcd-353">Aus diesem Grund ähnelt der Workflow den üblichen Entwicklungsaufgaben bei Verwendung von .NET für andere Entwicklungsarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-353">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="ebdcd-354">Sie müssen wissen, was im Hintergrund passiert (Imageerstellungsprozess, verwendete Basisimages, Bereitstellung von Containern usw.), und in einigen Fällen müssen Sie auch die Dockerfile-Datei oder die docker-compose.yml-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-354">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="ebdcd-355">Aber der Großteil der Arbeit wird durch Verwendung von Visual Studio, stark vereinfacht, und Ihre Produktivität wird entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-355">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-356">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-356">Additional resources</span></span>

- <span data-ttu-id="ebdcd-357">**Steve Lasker. .NET Docker Development with Visual Studio 2017 (.NET-Docker-Entwicklung mit Visual Studio 2017)**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-357">**Steve Lasker. .NET Docker Development with Visual Studio 2017**</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

- <span data-ttu-id="ebdcd-358">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio (Verschieben einer .NET Core-App in einen Container mit den neuen Docker-Tools für Visual Studio)**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-358">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**</span></span>

   [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="ebdcd-359">Verwenden von PowerShell-Befehlen in einer Dockerfile-Datei zum Einrichten von Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="ebdcd-359">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="ebdcd-360">[Windows-Container](/virtualization/windowscontainers/about/) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images zu konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-360">[Windows Containers](/virtualization/windowscontainers/about/) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="ebdcd-361">Um Windows-Container zu verwenden, führen Sie PowerShell-Befehle in der Dockerfile-Datei aus, was im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-361">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="ebdcd-362">In diesem Fall wird ein Windows Server Core-Basisimage (FROM-Einstellung) verwendet und IIS wird mit einem PowerShell-Befehl ausgeführt (RUN-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="ebdcd-362">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="ebdcd-363">Auf ähnliche Weise können Sie auch PowerShell-Befehle verwenden, um zusätzliche Komponenten wie ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-363">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="ebdcd-364">Der folgende Befehl in einer Dockerfile-Datei richtet z.B. ASP.NET 4.5 ein:</span><span class="sxs-lookup"><span data-stu-id="ebdcd-364">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="ebdcd-365">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ebdcd-365">Additional resources</span></span>

- <span data-ttu-id="ebdcd-366">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="ebdcd-366">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="ebdcd-367">PowerShell-Beispielbefehle, die über Dockerfile-Dateien ausgeführt werden, um Windows-Features zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="ebdcd-367">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>

   [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="ebdcd-368">[Zurück](index.md)
>[Weiter](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="ebdcd-368">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
