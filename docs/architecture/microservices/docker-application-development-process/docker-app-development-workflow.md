---
title: Entwicklungsworkflow für Docker-Apps
description: Erläuterungen zu den Workflowdetails für die Entwicklung von auf Docker basierenden Anwendungen. Beginnen Sie mit den Grundlagen. Gehen Sie dann ausführlicher auf das Optimieren von Dockerfiles ein. Arbeiten Sie zum Schluss mit dem vereinfachten Workflow, der bei der Verwendung mit Visual Studio verfügbar ist.
ms.date: 01/07/2019
ms.openlocfilehash: 0c2789377bc388b8ac7373ee7fa46e3141f1b518
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "73740359"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="5b161-104">Entwicklungsworkflow für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="5b161-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="5b161-105">Der Lebenszyklus der Anwendungsentwicklung beginnt auf Ihrem Computer. Als Entwickler programmieren Sie die Anwendung mit Ihrer bevorzugten Programmiersprache und testen sie lokal.</span><span class="sxs-lookup"><span data-stu-id="5b161-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="5b161-106">Mit diesem Workflow entwickeln und testen Sie Docker-Container stets lokal, unabhängig davon, welche Sprache, welches Framework und welche Plattform Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b161-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="5b161-107">Jeder Container (eine Instanz eines Docker-Images) umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="5b161-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="5b161-108">Eine Betriebssystemauswahl, z. B. eine Linux-Distribution, Windows Nano Server oder Windows Server Core</span><span class="sxs-lookup"><span data-stu-id="5b161-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="5b161-109">Dateien, die während der Entwicklung hinzugefügt wurden, z. B. Quellcode- und Anwendungsbinärdateien</span><span class="sxs-lookup"><span data-stu-id="5b161-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="5b161-110">Konfigurationsinformationen, z. B. Umgebungseinstellungen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="5b161-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="5b161-111">Workflow für die Entwicklung von Docker-Container-basierten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5b161-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="5b161-112">In diesem Abschnitt wird der *Entwicklungsworkflow* für Docker-Container-basierte Anwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b161-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="5b161-113">Der innere Entwicklungsworkflow berücksichtigt nicht den breiteren DevOps-Workflow, der bis zur Produktionsbereitstellung reichen kann. Stattdessen liegt der Fokus nur auf der Entwicklungsarbeit, die auf dem Computer des Entwicklers vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-113">The inner-loop workflow means it's not considering the broader DevOps workflow, which can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="5b161-114">Die ersten Schritte zum Einrichten der Umgebung wurden nicht berücksichtigt, da diese nur einmal durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="5b161-115">Eine Anwendung besteht aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="5b161-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="5b161-116">Im Folgenden sind die grundlegenden Schritte dargestellt, die Sie normalerweise beim Erstellen einer Docker-Anwendung ausführen, wie in Abbildung 5-1 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramm, das die erforderlichen 7 Schritte zum Erstellen einer Container-App zeigt.":::
<span data-ttu-id="5b161-118">Der Entwicklungsprozess für Docker-Apps: 1. Programmieren der App, 2. Schreiben der Dockerfile(s), 3. Erstellen der in der Dockerfile definierten Images, 4. Erstellen von Diensten in der docker-compose.yml-Datei (optional), 5. Ausführen des Containers oder der docker-compose-App, 6. Testen der App oder des Microservices, 7. Mithilfe von Push an das Repository übertragen und Prozedur wiederholen</span><span class="sxs-lookup"><span data-stu-id="5b161-118">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="5b161-119">**Abbildung 5-1.**</span><span class="sxs-lookup"><span data-stu-id="5b161-119">**Figure 5-1.**</span></span> <span data-ttu-id="5b161-120">Workflowschritte für die Entwicklung von Containeranwendungen für Docker</span><span class="sxs-lookup"><span data-stu-id="5b161-120">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="5b161-121">In diesem Abschnitt wird der gesamte Prozess ausführlich beschrieben, und jeder wichtige Schritt wird unter besonderer Berücksichtigung einer Visual Studio-Umgebung erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b161-121">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="5b161-122">Bei Verwendung eines Editor-/CLI-Entwicklungsansatzes (z. B. Visual Studio Code plus Docker-CLI auf macOS oder Windows) müssen Sie die einzelnen Schritte in der Regel detaillierter kennen als bei Verwendung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b161-122">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="5b161-123">Weitere Informationen zum Arbeiten in einer CLI-Umgebung finden Sie im E-Book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools (Lebenszyklus von Docker-Containeranwendungen mit Microsoft-Plattformen und Tools)](https://aka.ms/dockerlifecycleebook/).</span><span class="sxs-lookup"><span data-stu-id="5b161-123">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="5b161-124">Wenn Sie Visual Studio 2017 verwenden, werden viele dieser Schritte für Sie ausgeführt, wodurch sich Ihre Produktivität entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="5b161-124">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="5b161-125">Dies gilt insbesondere, wenn Sie Visual Studio 2017 verwenden und Anwendungen mit mehreren Containern das Ziel sind.</span><span class="sxs-lookup"><span data-stu-id="5b161-125">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="5b161-126">Visual Studio fügt beispielsweise mit nur einem Mausklick die Dateien Dockerfile und docker-compose.yml mit der Konfiguration für Ihre Anwendung Ihren Projekten hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b161-126">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="5b161-127">Wenn Sie die Anwendung in Visual Studio ausführen, wird das Docker-Image erstellt und die Anwendung mit mehreren Containern wird direkt in Docker ausgeführt. Sie haben sogar die Möglichkeit, mehrere Container auf einmal zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="5b161-127">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="5b161-128">Diese Features erhöhen Ihre Entwicklungsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="5b161-128">These features will boost your development speed.</span></span>

<span data-ttu-id="5b161-129">Allerdings bedeutet die Tatsache, dass Visual Studio die Schritte automatisch ausführt, nicht, dass Sie nicht wissen müssen, was im Hintergrund mit Docker geschieht.</span><span class="sxs-lookup"><span data-stu-id="5b161-129">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="5b161-130">Aus diesem Grund werden im folgenden Leitfaden alle Schritte ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b161-130">Therefore, the following guidance details every step.</span></span>

![Abbildung für Schritt 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="5b161-132">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="5b161-132">Step 1.</span></span> <span data-ttu-id="5b161-133">Beginnen Sie mit dem Codieren, und erstellen Sie eine erste Anwendungs- oder Dienstbaseline</span><span class="sxs-lookup"><span data-stu-id="5b161-133">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="5b161-134">Das Entwickeln einer Docker-Anwendung ist mit der Art und Weise vergleichbar, wie Anwendungen ohne Docker entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-134">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="5b161-135">Der Unterschied besteht darin, dass Sie beim Entwickeln für Docker Ihre Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern in Ihrer lokalen Umgebung ausgeführt werden (entweder in einem Setup für eine Linux-VM von Docker oder direkt unter Windows, wenn Sie Windows-Container verwenden).</span><span class="sxs-lookup"><span data-stu-id="5b161-135">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="5b161-136">Einrichten der lokalen Umgebung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-136">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="5b161-137">Stellen Sie zuerst sicher, dass [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) für Windows wie nachfolgend erläutert installiert wurde:</span><span class="sxs-lookup"><span data-stu-id="5b161-137">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="5b161-138">Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)</span><span class="sxs-lookup"><span data-stu-id="5b161-138">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="5b161-139">Zudem benötigen Sie Visual Studio 2017, Version 15.7 oder höher, mit installierter Workload für die **plattformübergreifende .NET Core-Entwicklung**, wie in Abbildung 5.2 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-139">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Screenshot der Auswahl der plattformübergreifenden .NET Core-Entwicklung.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

<span data-ttu-id="5b161-141">**Abbildung 5-2**.</span><span class="sxs-lookup"><span data-stu-id="5b161-141">**Figure 5-2**.</span></span> <span data-ttu-id="5b161-142">Auswahl der **Workload für die plattformübergreifende .NET Core-Entwicklung** während des Setups in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5b161-142">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="5b161-143">Sie können mit dem Codieren Ihrer Anwendung in einer einfachen .NET-Umgebung beginnen (normalerweise in .NET Core, wenn Sie Container verwenden möchten), noch bevor Sie Docker in Ihrer Anwendung aktivieren und in Docker Bereitstellungsprozesse und Tests durchführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-143">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="5b161-144">Allerdings wird empfohlen, dass Sie so bald wie möglich mit Docker arbeiten, d.h. in der realen Umgebung, sodass etwaige Probleme schnellstmöglich erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="5b161-144">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="5b161-145">Dies wird empfohlen, da Visual Studio die Arbeit mit Docker so erleichtert, dass sie fast transparent erscheint – insbesondere beim Debuggen von Anwendungen mit mehreren Containern über Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b161-145">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-146">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-146">Additional resources</span></span>

- <span data-ttu-id="5b161-147">**Get started with Docker CE for Windows (Erste Schritte mit Docker CE für Windows)**  </span><span class="sxs-lookup"><span data-stu-id="5b161-147">**Get started with Docker CE for Windows** </span></span>\
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="5b161-148">**Visual Studio 2017** </span><span class="sxs-lookup"><span data-stu-id="5b161-148">**Visual Studio 2017** </span></span>\
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

![Abbildung für Schritt 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="5b161-150">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="5b161-150">Step 2.</span></span> <span data-ttu-id="5b161-151">Erstellen Sie eine Dockerfile-Datei im Zusammenhang mit einem vorhandenen .NET-Basisimage</span><span class="sxs-lookup"><span data-stu-id="5b161-151">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="5b161-152">Für jedes benutzerdefinierte Image, das Sie erstellen möchten, benötigen Sie eine Dockerfile-Datei. Außerdem benötigen Sie eine Dockerfile-Datei für jeden bereitzustellenden Container unabhängig davon, ob Sie automatisch über Visual Studio oder manuell mithilfe der Docker-CLI bereitstellen (Befehle „docker run“ und „docker-compose“).</span><span class="sxs-lookup"><span data-stu-id="5b161-152">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="5b161-153">Wenn Ihre Anwendung einen benutzerdefinierten Dienst enthält, benötigen Sie eine einzelne Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="5b161-153">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="5b161-154">Wenn Ihre Anwendung mehrere Dienste enthält (wie in einer Microservicearchitektur), benötigen Sie pro Dienst eine Dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="5b161-154">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="5b161-155">Die Dockerfile-Datei befindet sich im Stammordner der Anwendung oder des Diensts.</span><span class="sxs-lookup"><span data-stu-id="5b161-155">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="5b161-156">Sie enthält die Befehle, die Docker mitteilen, wie die Anwendung oder der Dienst in einem Container eingerichtet und ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b161-156">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="5b161-157">Sie können eine Dockerfile-Datei manuell im Code erstellen und mit Ihren .NET-Abhängigkeiten Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b161-157">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="5b161-158">Mit Visual Studio und den Tools für Docker erledigen Sie diese Aufgabe mit einigen wenigen Mausklicks.</span><span class="sxs-lookup"><span data-stu-id="5b161-158">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="5b161-159">Beim Erstellen eines neuen Projekts in Visual Studio 2017 ist die Option **Enable Container (Docker) Support** (Containerunterstützung (Docker) aktivieren) verfügbar, wie in Abbildung 5.3 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-159">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![Screenshot, der das Kontrollkästchen „Docker-Unterstützung aktivieren“ zeigt.](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

<span data-ttu-id="5b161-161">**Abbildung 5-3**.</span><span class="sxs-lookup"><span data-stu-id="5b161-161">**Figure 5-3**.</span></span> <span data-ttu-id="5b161-162">Aktivieren der Docker-Unterstützung beim Erstellen eines neuen ASP.NET Core-Projekts in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5b161-162">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="5b161-163">Sie können die Docker-Unterstützung auch für ein vorhandenes ASP.NET Core-Web-App-Projekt aktivieren, indem Sie mit der rechten Maustaste auf das Projekt im **Projektmappen-Explorer** klicken und **Hinzufügen** > **Docker-Unterstützung** auswählen, wie in Abbildung 5.4 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-163">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Screenshot, der die Option „Docker-Unterstützung“ im Menü „Hinzufügen“ zeigt.](./media/docker-app-development-workflow/add-docker-support-option.png)

<span data-ttu-id="5b161-165">**Abbildung 5-4**.</span><span class="sxs-lookup"><span data-stu-id="5b161-165">**Figure 5-4**.</span></span> <span data-ttu-id="5b161-166">Aktivieren der Unterstützung für Docker in einem vorhandenen Visual Studio 2017-Projekt</span><span class="sxs-lookup"><span data-stu-id="5b161-166">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="5b161-167">Durch diesen Vorgang wird dem Projekt eine *Dockerfile* mit der erforderlichen Konfiguration hinzugefügt, die nur für ASP.NET Core-Projekte verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5b161-167">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="5b161-168">Visual Studio kann auf ganz ähnliche Weise eine docker-compose.yml-Datei für die gesamte Projektmappe hinzufügen. Dazu wird die Option **Add > Container Orchestrator Support** (Hinzufügen > Containerorchestratorunterstützung) verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b161-168">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="5b161-169">In Schritt 4 wird diese Option genauer erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b161-169">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="5b161-170">Verwenden eines vorhandenen offiziellen .NET Docker-Images</span><span class="sxs-lookup"><span data-stu-id="5b161-170">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="5b161-171">Sie erstellen ein benutzerdefiniertes Image für den Container in der Regel auf einem Basisimage, das Sie von einem offiziellen Repository in der [Docker-Hub](https://hub.docker.com/)-Registrierung erhalten.</span><span class="sxs-lookup"><span data-stu-id="5b161-171">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="5b161-172">Das ist genau das, was im Hintergrund geschieht, wenn Sie die Docker-Unterstützung in Visual Studio aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-172">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="5b161-173">Die Dockerfile verwendet ein vorhandenes `aspnetcore`-Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-173">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="5b161-174">Es wurde bereits erläutert, welche Docker-Images und Repositorys Sie abhängig vom Framework und Betriebssystem, das Sie ausgewählt haben, verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5b161-174">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="5b161-175">Wenn Sie beispielsweise ASP.NET Core (Linux oder Windows) verwenden möchten, muss das Image `mcr.microsoft.com/dotnet/core/aspnet:2.2` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-175">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="5b161-176">Aus diesem Grund müssen Sie nur angeben, welche Docker-Basisimages Sie für den Container verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-176">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="5b161-177">Fügen Sie hierzu `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` Ihrer Dockerfile hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b161-177">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` to your Dockerfile.</span></span> <span data-ttu-id="5b161-178">Dies wird automatisch von Visual Studio ausgeführt, aber wenn Sie die Version aktualisieren müssen, aktualisieren Sie diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="5b161-178">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="5b161-179">Durch Verwendung eines offiziellen .NET Image-Repositorys von Docker-Hub mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b161-179">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="5b161-180">Das folgende Beispiel veranschaulicht eine Dockerfile-Beispieldatei für einen ASP.NET Core-Container.</span><span class="sxs-lookup"><span data-stu-id="5b161-180">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="5b161-181">In diesem Fall basiert das Image auf Version 2.2 des offiziellen ASP.NET Core-Docker-Images (mehrere Architekturen für Linux und Windows).</span><span class="sxs-lookup"><span data-stu-id="5b161-181">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="5b161-182">Dies ist die Einstellung `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="5b161-182">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="5b161-183">(Weitere Informationen zu diesem Basisimage finden Sie unter [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core/).) In der Dockerfile-Datei müssen Sie auch angeben, dass Docker an dem TCP-Port lauscht, den Sie zur Runtime verwenden (in diesem Fall Port 80 gemäß Konfiguration mit der EXPOSE-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="5b161-183">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="5b161-184">Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben.</span><span class="sxs-lookup"><span data-stu-id="5b161-184">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="5b161-185">Beispielsweise weist die ENTRYPOINT-Zeile mit `["dotnet", "MySingleContainerWebApp.dll"]` Docker an, eine .NET Core-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-185">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="5b161-186">Wenn Sie das SDK und die .NET Core-CLI (Dotnet-CLI) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b161-186">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="5b161-187">Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen je nach Sprache und Plattform variieren können, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="5b161-187">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-188">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-188">Additional resources</span></span>

- <span data-ttu-id="5b161-189">**Erstellen von Docker-Images für .NET Core-Anwendungen** </span><span class="sxs-lookup"><span data-stu-id="5b161-189">**Building Docker Images for .NET Core Applications** </span></span>\
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- <span data-ttu-id="5b161-190">**Build your own image (Entwickeln eines eigenen Images)** .</span><span class="sxs-lookup"><span data-stu-id="5b161-190">**Build your own image**.</span></span> <span data-ttu-id="5b161-191">In der offiziellen Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5b161-191">In the official Docker documentation.</span></span>\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="5b161-192">**Staying up-to-date with .NET Container Images (Immer auf dem neuesten Stand mit .NET-Containerimages)**  </span><span class="sxs-lookup"><span data-stu-id="5b161-192">**Staying up-to-date with .NET Container Images** </span></span>\
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="5b161-193">**Using .NET and Docker together - DockerCon 2018 Update (Gemeinsame Verwendung von .NET und Docker: Update zu DockerCon 2018)**  </span><span class="sxs-lookup"><span data-stu-id="5b161-193">**Using .NET and Docker Together - DockerCon 2018 Update** </span></span>\
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="5b161-194">Verwenden von Repositorys für Images für mehrere Architekturen</span><span class="sxs-lookup"><span data-stu-id="5b161-194">Using multi-arch image repositories</span></span>

<span data-ttu-id="5b161-195">Ein Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-195">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="5b161-196">Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="5b161-196">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="5b161-197">Das in der Docker-Hub-Registrierung verfügbare [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Repositoryname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-197">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="5b161-198">Wenn Sie ein explizites Tag für eine bestimmte Plattform angeben, wie in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="5b161-198">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="5b161-199">Ziele: Nur .NET Core 2.2-Runtime unter Linux</span><span class="sxs-lookup"><span data-stu-id="5b161-199">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="5b161-200">Ziele: Nur .NET Core 2.2-Runtime unter Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="5b161-200">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="5b161-201">Die Images für mehrere Architekturen (z. B. das `aspnetcore`-Image) verwenden bei Angabe des gleichen Imagenamens, auch mit dem gleichen Tag, je nach dem von Ihnen bereitgestellten Docker-Host-Betriebssystem die Linux- oder die Windows-Version, was im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="5b161-201">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="5b161-202">Mehrfacharchitektur: Nur .NET Core 2.2-Runtime unter Linux und Windows Nano Server, abhängig vom Betriebssystem des Docker-Hosts</span><span class="sxs-lookup"><span data-stu-id="5b161-202">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="5b161-203">Wenn Sie also ein Image von einem Windows-Host pullen, wird die Windows-Variante gepullt. Wenn der gleiche Imagename von einem Linux-Host gepullt wird, wird die Linux-Variante gepullt.</span><span class="sxs-lookup"><span data-stu-id="5b161-203">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="5b161-204">Mehrstufige Builds in einer Dockerfile</span><span class="sxs-lookup"><span data-stu-id="5b161-204">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="5b161-205">Die Dockerfile ähnelt einem Batchskript.</span><span class="sxs-lookup"><span data-stu-id="5b161-205">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="5b161-206">Die Vorgehensweise ist in etwa so wie beim Einrichten des Computers über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="5b161-206">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="5b161-207">Sie beginnen mit einem Basisimage, das den Anfangskontext einrichtet, was dem Startdateisystem ähnelt, das sich auf dem Hostbetriebssystem befindet.</span><span class="sxs-lookup"><span data-stu-id="5b161-207">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="5b161-208">Dabei handelt es sich jedoch nicht um ein Betriebssystem, Sie können es sich eher als „das“ Betriebssystem innerhalb des Containers vorstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-208">It's not an OS, but you can think of it like "the" OS inside the container.</span></span>

<span data-ttu-id="5b161-209">Durch die Ausführung jeder Befehlszeile wird eine neue Ebene im Dateisystem erstellt, wobei jede Ebene die Änderungen der vorherigen enthält. Das gesamte Konstrukt ergibt zusammen das Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="5b161-209">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="5b161-210">Da jede Ebene auf der vorherigen „aufliegt“, und die daraus resultierende Imagegröße mit jedem Befehl zunimmt, können Images sehr groß werden, wenn darin beispielsweise das für die Erstellung und Veröffentlichung einer Anwendung benötigte SDK enthalten sein muss.</span><span class="sxs-lookup"><span data-stu-id="5b161-210">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="5b161-211">Zu diesem Zeitpunkt kommen mehrstufige Builds (ab Docker 17.05 und höher) ins Spiel.</span><span class="sxs-lookup"><span data-stu-id="5b161-211">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="5b161-212">Die Kernidee dahinter ist, dass Sie den Ausführungsprozess für die Dockerfile in Stufen aufteilen können, wobei jede Stufe ein anfängliches Image darstellt, auf das mindestens ein Befehl folgt. Die letzte Stufe bestimmt die endgültige Imagegröße.</span><span class="sxs-lookup"><span data-stu-id="5b161-212">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="5b161-213">Zusammengefasst bedeutet das also, dass für mehrstufige Builds die Erstellung in unterschiedlichen „Phasen“ ablaufen kann und das endgültige Image dann ausschließlich mit den relevanten Verzeichnissen aus den weiterführenden Stufen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-213">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="5b161-214">Die allgemeine Strategie zur Verwendung dieses Features ist die folgende:</span><span class="sxs-lookup"><span data-stu-id="5b161-214">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="5b161-215">Verwenden Sie ein SDK-Basisimage (dabei ist die Größe nicht wichtig) mit allen Elementen, die zum Erstellen und Veröffentlichen der Anwendung in einem Ordner erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5b161-215">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="5b161-216">Verwenden Sie anschließend ein kleines Image, das nur als Runtime dient, und kopieren Sie den Veröffentlichungsordner aus der vorherigen Stufe, um ein kleineres endgültiges Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-216">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="5b161-217">Sie können den mehrstufigen Prozess am besten verstehen, wenn Sie eine Dockerfile ausführlich durchlaufen, und zwar Zeile für Zeile. Beginnen wir also mit der ursprünglichen Dockerfile, die von Visual Studio erstellt wird, wenn zu einem Projekt Docker-Unterstützung hinzugefügt wird. Später erhalten Sie noch mehr Informationen zu einigen Optimierungen.</span><span class="sxs-lookup"><span data-stu-id="5b161-217">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="5b161-218">Die ursprüngliche Dockerfile kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="5b161-218">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="5b161-219">Hier sind die Details zeilenweise dargestellt:</span><span class="sxs-lookup"><span data-stu-id="5b161-219">And these are the details, line by line:</span></span>

- <span data-ttu-id="5b161-220">**Linie 1:** Beginnen Sie eine Stufe mit einem „kleinen“ Basisimage, das nur als Runtime dient. Nennen Sie es zu Referenzzwecken **base**.</span><span class="sxs-lookup"><span data-stu-id="5b161-220">**Line #1:** Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>

- <span data-ttu-id="5b161-221">**Zeile 2:** Erstellen Sie das Verzeichnis **/app** im Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-221">**Line #2:** Create the **/app** directory in the image.</span></span>

- <span data-ttu-id="5b161-222">**Zeilen 3:** Machen Sie den Port **80** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b161-222">**Line #3:** Expose port **80**.</span></span>

- <span data-ttu-id="5b161-223">**Zeilen 5:** Beginnen Sie eine neue Stufe mit einem „großen“ Image zur Erstellung/Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="5b161-223">**Line #5:** Begin a new stage with the "large" image for building/publishing.</span></span> <span data-ttu-id="5b161-224">Nennen Sie es zu Referenzzwecken **build**.</span><span class="sxs-lookup"><span data-stu-id="5b161-224">Call it **build** for reference.</span></span>

- <span data-ttu-id="5b161-225">**Zeilen 6:** Erstellen Sie das **/src**-Verzeichnis im Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-225">**Line #6:** Create directory **/src** in the image.</span></span>

- <span data-ttu-id="5b161-226">**Zeilen 7:** Kopieren Sie bis zur Zeile 16 die **CSPROJ**-Projektdateien, auf die verwiesen wird, damit Sie Pakete zu einem späteren Zeitpunkt wiederherstellen können.</span><span class="sxs-lookup"><span data-stu-id="5b161-226">**Line #7:** Up to line 16, copy referenced **.csproj** project files to be able to restore packages later.</span></span>

- <span data-ttu-id="5b161-227">**Zeile 17:** Stellen Sie die Pakete für das **Catalog.API**-Projekt und die Projekte, auf die verwiesen wird, wieder her.</span><span class="sxs-lookup"><span data-stu-id="5b161-227">**Line #17:** Restore packages for the **Catalog.API** project and the referenced projects.</span></span>

- <span data-ttu-id="5b161-228">**Zeilen 18:** Kopieren Sie **alle Verzeichnisstrukturen für die Projektmappe** (mit Ausnahme der Dateien und Verzeichnisse in der **DOCKERIGNORE**-Datei) in das Verzeichnis **/src** im Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-228">**Line #18:** Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) to the **/src** directory in the image.</span></span>

- <span data-ttu-id="5b161-229">**Zeilen 19:** Ändern Sie den aktuellen Ordner in das **Catalog.API**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b161-229">**Line #19:** Change the current folder to the **Catalog.API** project.</span></span>

- <span data-ttu-id="5b161-230">**Zeilen 20:** Erstellen Sie das Projekt (und andere Projektabhängigkeiten) sowie die Ausgabe im Verzeichnis **/app** im Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-230">**Line #20:** Build the project (and other project dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="5b161-231">**Zeile 22:** Beginnen Sie eine weitere neue Stufe aus dem Build.</span><span class="sxs-lookup"><span data-stu-id="5b161-231">**Line #22:** Begin a new stage continuing from the build.</span></span> <span data-ttu-id="5b161-232">Nennen Sie sie zu Verweiszwecken **publish**.</span><span class="sxs-lookup"><span data-stu-id="5b161-232">Call it **publish** for reference.</span></span>

- <span data-ttu-id="5b161-233">**Zeile 23:** Veröffentlichen Sie das Projekt (und die Abhängigkeiten) sowie die Ausgabe im Verzeichnis **/app** im Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-233">**Line #23:** Publish the project (and dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="5b161-234">**Zeile 25:** Beginnen Sie eine neue Stufe aus dem Image **base**, und nennen Sie sie **final**.</span><span class="sxs-lookup"><span data-stu-id="5b161-234">**Line #25:** Begin a new stage continuing from **base** and call it **final**.</span></span>

- <span data-ttu-id="5b161-235">**Zeile 26:** Ändern Sie das aktuelle Verzeichnis in **/app**.</span><span class="sxs-lookup"><span data-stu-id="5b161-235">**Line #26:** Change the current directory to **/app**.</span></span>

- <span data-ttu-id="5b161-236">**Zeile 27:** Kopieren Sie das Verzeichnis **/app** aus der Stufe **publish** in das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b161-236">**Line #27:** Copy the **/app** directory from stage **publish** to the current directory.</span></span>

- <span data-ttu-id="5b161-237">**Zeile 28:** Definieren Sie den Befehl, der ausgeführt werden soll, sobald der Container gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-237">**Line #28:** Define the command to run when the container is started.</span></span>

<span data-ttu-id="5b161-238">Lernen Sie nun einige Optimierungen kennen, die Ihnen dabei helfen, die gesamte Prozessleistung zu verbessern. Im Falle von eShopOnContainers bedeutet dies, dass es 22 Minuten oder länger dauert, um die gesamte Projektmappe in Linux-Containern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-238">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="5b161-239">Sie nutzen die Cachefunktion für die Ebenen in Docker. Das ist ganz einfach: Wenn sich das Basisimage und die Befehle nicht von den zuvor ausgeführten unterscheiden, kann einfach die sich daraus resultierende Ebene verwendet werden, ohne dass die Befehle ausgeführt werden müssen, wodurch Sie Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="5b161-239">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="5b161-240">Konzentrieren wir uns daher auf die **build**-Stufe: Die Zeilen 5–6 unterscheiden sich kaum, jedoch unterscheiden sich die Zeilen 7–17 für jeden eShopOnContainers-Dienst, weshalb sie jedes Mal ausgeführt werden müssen. Ganz anders sieht es aus, wenn Sie die Zeilen 7–16 wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="5b161-240">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```Dockerfile
COPY . .
```

<span data-ttu-id="5b161-241">Die Vorgehensweise wäre dann für jeden Dienst die gleiche: Die gesamte Projektmappe wird kopiert, und es wird eine größere Ebene erstellt. Dazu ist jedoch Folgendes zu beachten:</span><span class="sxs-lookup"><span data-stu-id="5b161-241">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1. <span data-ttu-id="5b161-242">Der Kopiervorgang würde nur zum ersten Mal ausgeführt (und bei einer Neuerstellung, wenn eine Datei geändert wird) und würde den Cache für alle anderen Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b161-242">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2. <span data-ttu-id="5b161-243">Da das größere Image in einem Zwischenstadium auftritt, wirkt es sich nicht auf die endgültige Imagegröße aus.</span><span class="sxs-lookup"><span data-stu-id="5b161-243">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="5b161-244">Die nächste wichtige Optimierung umfasst den `restore`-Befehl, der in Zeile 17 ausgeführt wird, der sich jedoch auch für jeden Dienst von eShopOnContainers unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="5b161-244">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="5b161-245">Wenn Sie also diese Zeile nur wie folgt ändern...</span><span class="sxs-lookup"><span data-stu-id="5b161-245">If you change that line to just:</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="5b161-246">...dann werden die Pakete für die gesamte Projektmappe wiederhergestellt. Dies geschieht jedoch nur ein einziges Mal und nicht 15 Mal wie bei der aktuellen Strategie.</span><span class="sxs-lookup"><span data-stu-id="5b161-246">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="5b161-247">Jedoch wird `dotnet restore` nur ausgeführt, wenn sich ein einzelnes Projekt oder eine einzelne Projektmappendatei im Ordner befindet. Der Weg dahin ist etwas komplizierter, und der Lösungsweg (ohne dass Sie sich in zu vielen Details verlieren) sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5b161-247">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1. <span data-ttu-id="5b161-248">Fügen Sie der **.dockerignore**-Datei die folgenden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="5b161-248">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="5b161-249">`*.sln`, um alle Projektmappendateien in der Hauptordnerstruktur zu ignorieren</span><span class="sxs-lookup"><span data-stu-id="5b161-249">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="5b161-250">`!eShopOnContainers-ServicesAndWebApps.sln`, um nur diese Projektmappendatei einzufügen</span><span class="sxs-lookup"><span data-stu-id="5b161-250">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2. <span data-ttu-id="5b161-251">Schließen Sie das `/ignoreprojectextensions:.dcproj`-Argument in `dotnet restore` ein, damit auch das docker-compose-Projekt ignoriert und nur das Paket für die Projektmappe „eShopOnContainers-ServicesAndWebApps“ wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-251">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="5b161-252">Für die letzte Optimierung kann es der Fall sein, dass Zeile 20 redundant wird, da Zeile 23 ebenso die Anwendung erstellt und im Grunde genommen gleich auf Zeile 20 folgt. So sparen Sie sich daher einen weiteren zeitaufwändigen Befehl.</span><span class="sxs-lookup"><span data-stu-id="5b161-252">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="5b161-253">Die Datei, die sich daraus ergibt, sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5b161-253">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="5b161-254">Neuerstellung des Basisimages</span><span class="sxs-lookup"><span data-stu-id="5b161-254">Creating your base image from scratch</span></span>

<span data-ttu-id="5b161-255">Sie können ein eigenes Docker-Basisimage von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-255">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="5b161-256">Dieses Szenario wird Docker-Einsteigern nicht empfohlen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="5b161-256">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-257">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-257">Additional resources</span></span>

- <span data-ttu-id="5b161-258">**Multi-arch .NET Core images** (.NET Core-Images für mehrere Architekturen).</span><span class="sxs-lookup"><span data-stu-id="5b161-258">**Multi-arch .NET Core images**.</span></span>\
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="5b161-259">**Create a base image (Erstellen eines Basisimages)** .</span><span class="sxs-lookup"><span data-stu-id="5b161-259">**Create a base image**.</span></span> <span data-ttu-id="5b161-260">Offizielle Docker-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="5b161-260">Official Docker documentation.</span></span>\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Abbildung für Schritt 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="5b161-262">Schritt 3</span><span class="sxs-lookup"><span data-stu-id="5b161-262">Step 3.</span></span> <span data-ttu-id="5b161-263">Erstellen Sie Ihre benutzerdefinierten Docker-Images, und betten Sie Ihre Anwendung oder Ihren Dienst in diese ein</span><span class="sxs-lookup"><span data-stu-id="5b161-263">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="5b161-264">Sie müssen für jeden Dienst in Ihrer Anwendung ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-264">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="5b161-265">Wenn Ihre Anwendung aus einem einzelnen Dienst oder einer einzelnen Webanwendung besteht, benötigen Sie nur ein Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-265">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="5b161-266">Beachten Sie, dass die Docker-Images in Visual Studio automatisch erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-266">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="5b161-267">Die folgenden Schritte sind nur für den Editor-/CLI-Workflow und zur Erläuterung der Vorgänge, die im Hintergrund ablaufen, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b161-267">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="5b161-268">Als Entwickler entwickeln und testen Sie so lange lokal, bis Sie ein abgeschlossenes Feature pushen oder zu Ihrem Quellkontrollsystem wechseln (z.B. zu GitHub).</span><span class="sxs-lookup"><span data-stu-id="5b161-268">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="5b161-269">Dies bedeutet, dass Sie die Docker-Images erstellen und Container auf einem lokalen Docker-Host (Windows- oder Linux-VM) bereitstellen und für die lokalen Container ausführen, testen und debuggen müssen.</span><span class="sxs-lookup"><span data-stu-id="5b161-269">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="5b161-270">Mithilfe des Befehls „docker build“ können Sie, wie in Abbildung 5-5 gezeigt, unter Verwendung der Docker-CLI und Ihrer Dockerfile-Datei ein benutzerdefiniertes Image in ihrer lokalen Umgebung erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-270">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Der Screenshot zeigt die Konsolenausgabe des Befehls „docker build“.](./media/docker-app-development-workflow/run-docker-build-command.png)

<span data-ttu-id="5b161-272">**Abbildung 5-5**.</span><span class="sxs-lookup"><span data-stu-id="5b161-272">**Figure 5-5**.</span></span> <span data-ttu-id="5b161-273">Erstellen eines benutzerdefinierten Docker-Images</span><span class="sxs-lookup"><span data-stu-id="5b161-273">Creating a custom Docker image</span></span>

<span data-ttu-id="5b161-274">Optional können Sie, anstatt „docker build“ über den Projektordner direkt auszuführen, zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken und Binärdateien generieren, indem Sie erst `dotnet publish` ausführen und dann den Befehl `docker build` verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b161-274">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="5b161-275">Dadurch wird ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` erstellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-275">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="5b161-276">In diesem Fall ist :first ein Tag, das eine bestimmte Version darstellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-276">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="5b161-277">Sie können diesen Schritt für jedes benutzerdefinierte Image wiederholen, das Sie für Ihre zusammengesetzte Docker-Anwendung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="5b161-277">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="5b161-278">Wenn eine Anwendung aus mehreren Containern besteht, können Sie auch den Befehl `docker-compose up --build` verwenden, um alle zugehörigen Images mit einem Befehl unter Verwendung der in den zugehörigen docker-compose.yml-Dateien verfügbar gemachten Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-278">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="5b161-279">Sie können die vorhandenen Images in Ihrem lokalen Repository suchen, indem Sie den „docker images“-Befehl, wie in Abbildung 5-6 dargestellt, verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b161-279">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Konsolenausgabe des Befehls „docker images“, gezeigt werden vorhandene Images.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="5b161-281">**Abbildung 5-6.**</span><span class="sxs-lookup"><span data-stu-id="5b161-281">**Figure 5-6.**</span></span> <span data-ttu-id="5b161-282">Anzeigen vorhandener Images mithilfe des Befehls „docker images“</span><span class="sxs-lookup"><span data-stu-id="5b161-282">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="5b161-283">Erstellen von Docker-Images mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-283">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="5b161-284">Wenn Sie Visual Studio zum Erstellen eines Projekts mit Docker-Unterstützung verwenden, erstellen Sie nicht explizit ein Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-284">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="5b161-285">Stattdessen wird das Image für Sie erstellt, wenn Sie **F5** (oder **STRG+F5**) drücken und die dockerisierte Anwendung oder den dockerisierten Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-285">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="5b161-286">Dieser Schritt wird in Visual Studio automatisch und für Sie nicht erkennbar ausgeführt, aber es ist wichtig, dass Sie wissen, was im Hintergrund passiert.</span><span class="sxs-lookup"><span data-stu-id="5b161-286">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Abbildung für den optionalen Schritt 4.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="5b161-288">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="5b161-288">Step 4.</span></span> <span data-ttu-id="5b161-289">Definieren Sie Ihre Dienste in der Datei docker-compose.yml beim Erstellen einer Docker-Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="5b161-289">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="5b161-290">Mithilfe der Datei [docker compose.yml](https://docs.docker.com/compose/compose-file/) können Sie mehrere verwandte Dienste definieren, die als zusammengesetzte Anwendung mit Bereitstellungsbefehlen bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5b161-290">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="5b161-291">Dadurch werden ebenso die Abhängigkeitsbeziehungen und die Laufzeitkonfiguration konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5b161-291">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="5b161-292">Wenn Sie eine docker-compose.yml-Datei verwenden möchten, müssen Sie die Datei in Ihrem Haupt- oder Stammlösungsordner mit Inhalt erstellen, der mit dem in dem folgenden Beispiel verwendeten vergleichbar ist:</span><span class="sxs-lookup"><span data-stu-id="5b161-292">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

<span data-ttu-id="5b161-293">Diese „docker-compose.yml“-Datei ist eine vereinfachte und zusammengeführte Version.</span><span class="sxs-lookup"><span data-stu-id="5b161-293">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="5b161-294">Sie enthält die statischen Konfigurationsdaten für jeden Container (z. B. den Namen des benutzerdefinierten Images), das erforderlich ist, sowie Konfigurationsinformationen, die sich nach der Bereitstellungsumgebung richten können, z. B. die Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5b161-294">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="5b161-295">In späteren Abschnitten erfahren Sie, wie Sie die Konfiguration der docker-compose.yml-Datei in mehrere docker-compose-Dateien aufteilen und Werte je nach Umgebung und Ausführungstyp (Debug oder Release) außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="5b161-295">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="5b161-296">Im Beispiel der Datei „docker-compose.yml“ werden vier Dienste definiert: der `webmvc`-Dienst (eine Webanwendung), zwei Microservices (`ordering.api` und `basket.api`) und ein Datenquellcontainer, `sql.data`, basierend auf von als Container ausgeführtem SQL Server für Linux.</span><span class="sxs-lookup"><span data-stu-id="5b161-296">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="5b161-297">Da jeder Dienst als ein Container bereitgestellt wird, ist für jeden ein Docker-Image erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5b161-297">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="5b161-298">Die docker-compose.yml-Datei gibt nicht nur an, welche Container verwendet werden, sondern auch, wie diese einzeln konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-298">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="5b161-299">Die `webmvc`-Containerdefinition in der .yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="5b161-299">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="5b161-300">Verwendet ein vorab erstelltes `eshop/web:latest`-Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-300">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="5b161-301">Sie können jedoch das als Teil der docker-compose-Ausführung zu erstellende Image mit einer zusätzlichen, auf einem build:-Abschnitt in der docker-compose-Datei basierenden Konfiguration konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-301">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="5b161-302">Initialisiert die beiden Umgebungsvariablen (CatalogUrl und OrderingUrl).</span><span class="sxs-lookup"><span data-stu-id="5b161-302">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="5b161-303">Leitet den verfügbar gemachten Port 80 für den Container an den externen Port 80 auf dem Hostcomputer weiter.</span><span class="sxs-lookup"><span data-stu-id="5b161-303">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="5b161-304">Verknüpft die Web-App mit dem Katalog- und Bestelldienst mit der depends_on-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="5b161-304">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="5b161-305">Dies bewirkt, dass der Dienst wartet, bis diese Dienste gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-305">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="5b161-306">Wir gehen in einem der folgenden Abschnitte erneut auf die Datei docker-compose.yml ein, wenn wir uns damit beschäftigen, wie Microservices und Apps mit mehreren Containern implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-306">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="5b161-307">Arbeiten mit docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5b161-307">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="5b161-308">Visual Studio 2017 (ab Version 15.8) kann, wie zuvor erwähnt, eine Dockerfile zu einem Projekt hinzufügen und zusätzlich noch Orchestratorunterstützung für Docker Compose zu einer Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="5b161-308">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="5b161-309">Wenn Sie zum ersten Mal Containerorchestratorunterstützung hinzufügen, wie in Abbildung 5.7 gezeigt, erstellt Visual Studio die Dockerfile für das Projekt sowie ein neues Projekt (Dienstbereich) in Ihrer Projektmappe mit mehreren globalen `docker-compose*.yml`-Dateien. Anschließend wird das Projekt diesen Dateien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b161-309">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="5b161-310">Sie können dann die docker-compose.yml-Dateien öffnen und mit zusätzlichen Features aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-310">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="5b161-311">Sie müssen diesen Vorgang für alle Projekte wiederholen, die Sie in die docker-compose.yml-Datei einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b161-311">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="5b161-312">Zum Zeitpunkt der Erstellung dieses Dokuments unterstützt Visual Studio Docker Compose- und Service Fabric-Orchestratoren.</span><span class="sxs-lookup"><span data-stu-id="5b161-312">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![Screenshot, der die Option „Unterstützung für Containerorchestrator“ im Kontextmenü des Projekts zeigt.](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

<span data-ttu-id="5b161-314">**Abbildung 5-7**.</span><span class="sxs-lookup"><span data-stu-id="5b161-314">**Figure 5-7**.</span></span> <span data-ttu-id="5b161-315">Hinzufügen von Docker-Unterstützung in Visual Studio 2017 durch Rechtsklick auf ein ASP.NET Core-Projekt</span><span class="sxs-lookup"><span data-stu-id="5b161-315">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="5b161-316">Nachdem Sie der Projektmappe in Visual Studio Orchestratorunterstützung hinzugefügt haben, sehen Sie auch einen neuen Knoten (in der `docker-compose.dcproj`Projektdatei) im Projektmappen-Explorer mit den hinzugefügten docker-compose.yml-Dateien, wie in Abbildung 5.8 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-316">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Screenshot des Knotens „docker-compose“ im Projektmappen-Explorer.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

<span data-ttu-id="5b161-318">**Abbildung 5-8**.</span><span class="sxs-lookup"><span data-stu-id="5b161-318">**Figure 5-8**.</span></span> <span data-ttu-id="5b161-319">Der im Projektmappen-Editor in Visual Studio 2017 hinzugefügte **docker-compose**-Strukturknoten</span><span class="sxs-lookup"><span data-stu-id="5b161-319">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="5b161-320">Eine Anwendung mit mehreren Containern kann unter Verwendung des Befehls `docker-compose up` mit einer einzelnen „docker-compose.yml“-Datei bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-320">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="5b161-321">Da Visual Studio jedoch eine Gruppe von Dateien hinzufügt, können Sie abhängig von der Umgebung (Entwicklung oder Produktion) und vom Ausführungstyp (Release oder Debug) Werte außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="5b161-321">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="5b161-322">Diese Funktion wird in späteren Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="5b161-322">This capability will be explained in later sections.</span></span>

![Abbildung für Schritt 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="5b161-324">Schritt 5.</span><span class="sxs-lookup"><span data-stu-id="5b161-324">Step 5.</span></span> <span data-ttu-id="5b161-325">Erstellen Sie Ihre Docker-Anwendung, und führen Sie sie aus</span><span class="sxs-lookup"><span data-stu-id="5b161-325">Build and run your Docker application</span></span>

<span data-ttu-id="5b161-326">Wenn die Anwendung nur über einen einzelnen Container verfügt, können Sie sie ausführen, indem Sie sie auf dem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-326">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="5b161-327">Enthält Ihre Anwendung dagegen mehrere Dienste, können Sie sie als zusammengesetzte Anwendung bereitstellen, indem Sie entweder einen einzelnen CLI-Befehl (docker-compose up) oder Visual Studio verwenden, wobei der Befehl dann im Hintergrund ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-327">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="5b161-328">Betrachten wir die unterschiedlichen Optionen.</span><span class="sxs-lookup"><span data-stu-id="5b161-328">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="5b161-329">Option A: Ausführen einer Anwendung mit einem einzelnen Container</span><span class="sxs-lookup"><span data-stu-id="5b161-329">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="5b161-330">Verwendung von Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="5b161-330">Using Docker CLI</span></span>

<span data-ttu-id="5b161-331">Sie können einen Docker-Container mit dem Befehl `docker run`, wie in Abbildung 5.9 dargestellt, ausführen:</span><span class="sxs-lookup"><span data-stu-id="5b161-331">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="5b161-332">Der obige Befehl erstellt bei jeder Ausführung eine neue Containerinstanz aus dem angegebenen Image.</span><span class="sxs-lookup"><span data-stu-id="5b161-332">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="5b161-333">Sie können den `--name`-Parameter verwenden, um dem Container einen Namen zu geben und anschließend `docker start {name}` (alternativ die Container-ID oder den automatischen Namen), um eine vorhandene Containerinstanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-333">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![Screenshot, in dem ein Docker-Container mithilfe des Befehls „docker run“ ausgeführt wird.](./media/docker-app-development-workflow/use-docker-run-command.png)

<span data-ttu-id="5b161-335">**Abbildung 5-9**.</span><span class="sxs-lookup"><span data-stu-id="5b161-335">**Figure 5-9**.</span></span> <span data-ttu-id="5b161-336">Ausführen eines Docker-Containers mithilfe des Befehls „docker run“</span><span class="sxs-lookup"><span data-stu-id="5b161-336">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="5b161-337">In diesem Fall bindet der Befehl den internen Port 5000 des Containers an Port 80 des Hostcomputers.</span><span class="sxs-lookup"><span data-stu-id="5b161-337">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="5b161-338">Dies bedeutet, dass der Host an Port 80 lauscht und an Port 5000 des Containers weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="5b161-338">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="5b161-339">Der dargestellte Hash ist die Container-ID, zudem wird ihm ein zufälliger lesbarer Name zugewiesen, wenn die `--name`-Option nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-339">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="5b161-340">Verwenden von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-340">Using Visual Studio</span></span>

<span data-ttu-id="5b161-341">Wenn Sie die Containerorchestratorunterstützung nicht hinzugefügt haben, können Sie auch eine einzelne Container-App in Visual Studio ausführen, indem Sie **STRG+F5** drücken. Sie können auch **F5** drücken, um die Anwendung innerhalb des Containers zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="5b161-341">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="5b161-342">Der Container wird lokal mit „docker run“ ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5b161-342">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="5b161-343">Option B: Ausführen einer Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="5b161-343">Option B: Running a multi-container application</span></span>

<span data-ttu-id="5b161-344">In den meisten Unternehmensszenarios setzt sich eine Docker-Anwendung aus mehreren Diensten zusammen. Dies bedeutet, dass Sie eine Anwendung mit mehreren Containern, wie in Abbildung 5-10 dargestellt, ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="5b161-344">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![VM mit mehreren Docker-Containern](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="5b161-346">**Abbildung 5-10**.</span><span class="sxs-lookup"><span data-stu-id="5b161-346">**Figure 5-10**.</span></span> <span data-ttu-id="5b161-347">VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="5b161-347">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="5b161-348">Verwendung von Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="5b161-348">Using Docker CLI</span></span>

<span data-ttu-id="5b161-349">Verwenden Sie den `docker-compose up`-Befehl, um eine Anwendung mit mehreren Containern mithilfe der Docker-CLI auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-349">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="5b161-350">Dieser Befehl stellt mithilfe der **docker-compose.yml**-Datei, die auf Projektmappenebene verfügbar ist, eine Anwendung mit mehreren Containern bereit.</span><span class="sxs-lookup"><span data-stu-id="5b161-350">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="5b161-351">Abbildung 5.11 zeigt die Ergebnisse an, wenn der Befehl aus Ihrem Hauptprojektmappenverzeichnis ausgeführt wird, das die docker-compose.yml-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="5b161-351">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Bildschirmansicht bei der Ausführung des Befehls „docker-compose up“](./media/docker-app-development-workflow/results-docker-compose-up.png)

<span data-ttu-id="5b161-353">**Abbildung 5-11**.</span><span class="sxs-lookup"><span data-stu-id="5b161-353">**Figure 5-11**.</span></span> <span data-ttu-id="5b161-354">Beispielergebnisse bei der Ausführung des Befehls „docker-compose up“</span><span class="sxs-lookup"><span data-stu-id="5b161-354">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="5b161-355">Nachdem der Befehl „docker-compose up“ ausgeführt wurde, werden wie in Abbildung 5.10 die Anwendung und ihre zugehörigen Container in Ihrem Docker-Host bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5b161-355">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="5b161-356">Verwenden von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-356">Using Visual Studio</span></span>

<span data-ttu-id="5b161-357">Das Ausführen einer Anwendung mit mehreren Containern mit Visual Studio 2017 ist denkbar einfach.</span><span class="sxs-lookup"><span data-stu-id="5b161-357">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="5b161-358">Drücken Sie einfach **STRG+F5** oder nur **F5**, um den Debugvorgang zu starten und wie üblich dabei das **docker-compose**-Projekt als Startprojekt festlegen.</span><span class="sxs-lookup"><span data-stu-id="5b161-358">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="5b161-359">Visual Studio kümmert sich um das erforderliche Setup. Sie können sich also darauf konzentrieren, Breakpoints zu erstellen und unabhängige Prozesse zu debuggen, die auf Remoteservern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-359">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="5b161-360">Wie bereits erwähnt, wird jedes Mal, wenn Sie Unterstützung für die Docker-Projektmappe einem Projekt in einer Projektmappe hinzufügen, das Projekt in der globalen docker-compose.yml-Datei (Projektmappenebene) konfiguriert wird, wodurch Sie die gesamte Projektmappe auf einmal ausführen oder debuggen können.</span><span class="sxs-lookup"><span data-stu-id="5b161-360">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="5b161-361">Visual Studio startet einen Container für jede Projektmappe, für die die Docker-Projektmappenunterstützung aktiviert ist, und führt alle internen Schritte aus (dotnet publish, docker build usw.).</span><span class="sxs-lookup"><span data-stu-id="5b161-361">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="5b161-362">Wenn Sie einen Blick auf Ihre bisherige Arbeit werfen möchten, sehen Sie sich diese Datei an:</span><span class="sxs-lookup"><span data-stu-id="5b161-362">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="5b161-363">Wichtig dabei ist, dass Visual Studio 2017, wie in Abbildung 5-12 dargestellt, über einen zusätzlichen **Docker**-Befehl für die Aktion der F5-Taste verfügt.</span><span class="sxs-lookup"><span data-stu-id="5b161-363">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="5b161-364">Diese Option ermöglicht Ihnen, eine Anwendung mit mehreren Containern auszuführen oder zu debuggen, indem Sie alle in den docker-compose.yml-Dateien auf Projektmappenebene definierten Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-364">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="5b161-365">Die Möglichkeit, Lösungen mit mehreren Containern zu debuggen, bedeutet, das Sie mehrere Haltepunkte festlegen und jeden Haltepunkt in einem anderen Projekt (Container) festlegen können. Während des Debuggings in Visual Studio halten Sie an Haltepunkten an, die in verschiedenen Projekten definiert sind und in verschiedenen Containern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-365">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Screenshot der Symbolleiste zum Debuggen, über die ein docker-compose-Projekt ausgeführt wird.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

<span data-ttu-id="5b161-367">**Abbildung 5-12**.</span><span class="sxs-lookup"><span data-stu-id="5b161-367">**Figure 5-12**.</span></span> <span data-ttu-id="5b161-368">Ausführen von Apps mit mehreren Containern in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5b161-368">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-369">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-369">Additional resources</span></span>

- <span data-ttu-id="5b161-370">**Deploy an ASP.NET container to a remote Docker host (Bereitstellen eines ASP.NET-Containers in einem Docker-Remotehost)**  </span><span class="sxs-lookup"><span data-stu-id="5b161-370">**Deploy an ASP.NET container to a remote Docker host** </span></span>\
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="5b161-371">Ein Hinweis zum Testen und Bereitstellen mit Orchestratoren</span><span class="sxs-lookup"><span data-stu-id="5b161-371">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="5b161-372">Die Befehle „docker-compose up“ und „docker run“ (oder Ausführen und Debuggen der Container in Visual Studio) sind zum Testen von Containern in der Entwicklungsumgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="5b161-372">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="5b161-373">Verwenden Sie diesen Ansatz jedoch nicht für Produktionsbereitstellungen. Für diese sollten Sie Orchestratoren wie [Kubernetes](https://kubernetes.io/) oder [Service Fabric](https://azure.microsoft.com/services/service-fabric/) anzielen.</span><span class="sxs-lookup"><span data-stu-id="5b161-373">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="5b161-374">Wenn Sie Kubernetes verwenden, müssen Sie [Pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) zum Organisieren von Container verwenden sowie [Dienste](https://kubernetes.io/docs/concepts/services-networking/service/), um diese zu vernetzen.</span><span class="sxs-lookup"><span data-stu-id="5b161-374">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="5b161-375">Sie können ebenso [Bereitstellungen](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) verwenden, um die Erstellung und Änderung von Pods zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-375">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![Abbildung für Schritt 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="5b161-377">Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="5b161-377">Step 6.</span></span> <span data-ttu-id="5b161-378">Testen Sie die Docker-Anwendung mithilfe des lokalen Docker-Hosts</span><span class="sxs-lookup"><span data-stu-id="5b161-378">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="5b161-379">Dieser Schritt hängt davon ab, welche Vorgänge die Anwendung ausführt.</span><span class="sxs-lookup"><span data-stu-id="5b161-379">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="5b161-380">In einer einfachen .NET Core-Webanwendung, die als einzelner Container oder Dienst bereitgestellt wird, können Sie auf den Dienst zugreifen, indem Sie einen Browser auf dem Docker-Host öffnen und, wie in Abbildung 5-13 gezeigt, zu dieser Site navigieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-380">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="5b161-381">(Wenn die Konfiguration in der Docker-Datei den Container einem anderen Port als Port 80 auf dem Host zuordnet, berücksichtigen Sie den Host-Port in der URL.)</span><span class="sxs-lookup"><span data-stu-id="5b161-381">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Screenshot der Antwort von „localhost/API/values“.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="5b161-383">**Abbildung 5-13**.</span><span class="sxs-lookup"><span data-stu-id="5b161-383">**Figure 5-13**.</span></span> <span data-ttu-id="5b161-384">Beispiel für das lokale Testen der Docker-Anwendung mithilfe von „localhost“</span><span class="sxs-lookup"><span data-stu-id="5b161-384">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="5b161-385">Wenn „localhost“ nicht auf die Docker-Host-IP verweist (was bei Verwendung von Docker CE jedoch standardmäßig der Fall sein sollte), verwenden Sie die IP-Adresse der Netzwerkkarte Ihres Computers, um zum Dienst zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="5b161-385">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="5b161-386">Beachten Sie, dass diese URL im Browser Port 80 für das besprochene Containerbeispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b161-386">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="5b161-387">Allerdings werden intern die Anforderungen zu Port 5000 umgeleitet, da die Bereitstellung, wie in einem vorherigen Schritt beschrieben, mit dem Befehl „docker run“ erfolgte.</span><span class="sxs-lookup"><span data-stu-id="5b161-387">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="5b161-388">Sie können die Anwendung auch mithilfe von „curl“ über das Terminal testen, was in Abbildung 5-14 dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b161-388">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="5b161-389">Bei einer Docker-Installation unter Windows lautet die standardmäßige Docker-Host-IP zusätzlich zur eigentlichen IP-Adresse Ihres Computers stets 10.0.75.1.</span><span class="sxs-lookup"><span data-stu-id="5b161-389">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Konsolenausgabe beim Abrufen von http://10.0.75.1/API/values mit curl.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="5b161-391">**Abbildung 5-14**.</span><span class="sxs-lookup"><span data-stu-id="5b161-391">**Figure 5-14**.</span></span> <span data-ttu-id="5b161-392">Beispiel für das Testen der Docker-Anwendung mithilfe von „curl“</span><span class="sxs-lookup"><span data-stu-id="5b161-392">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="5b161-393">Testen und Debuggen von Containern mit Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5b161-393">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="5b161-394">Beim Ausführen und Debuggen des Containers mit Visual Studio 2017 können Sie die .NET-Anwendung in etwa so debuggen wie ohne Ausführung von Containern.</span><span class="sxs-lookup"><span data-stu-id="5b161-394">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="5b161-395">Testen und Debuggen ohne Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-395">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="5b161-396">Wenn Sie mit dem Editor-/CLI-Ansatz entwickeln, ist das Debuggen von Containern schwieriger. Es ist ratsam zu debuggen, indem Traces generiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b161-396">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-397">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-397">Additional resources</span></span>

- <span data-ttu-id="5b161-398">**Debuggen von Apps in einem lokalen Docker-Container** </span><span class="sxs-lookup"><span data-stu-id="5b161-398">**Debugging apps in a local Docker container** </span></span>\
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="5b161-399">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker (Erstellen, Debuggen, Bereitstellen von ASP.NET Core-Apps mit Docker).**</span><span class="sxs-lookup"><span data-stu-id="5b161-399">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="5b161-400">Video.</span><span class="sxs-lookup"><span data-stu-id="5b161-400">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="5b161-401">Vereinfachter Workflow bei der Entwicklung von Containern mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-401">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="5b161-402">Der Workflow bei Verwendung von Visual Studio ist wesentlich einfacher als bei Verwendung des Editor/CLI-Ansatzes.</span><span class="sxs-lookup"><span data-stu-id="5b161-402">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="5b161-403">Die meisten der von Docker vorausgesetzten Schritte in Zusammenhang mit der Dockerfile-Datei und den docker-compose.yml-Dateien werden, wie in Abbildung 5-15 gezeigt, von Visual Studio ausgeblendet oder vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="5b161-403">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramm, das die vereinfachten fünf Schritte zum Erstellen einer App zeigt.":::
<span data-ttu-id="5b161-405">Der Entwicklungsprozess für Docker-Apps: 1. Programmieren der App, 2. Schreiben der Dockerfile(s), 3. Erstellen der in der Dockerfile definierten Images, 4. Erstellen von Diensten in der docker-compose.yml-Datei (optional), 5. Ausführen des Containers oder der docker-compose-App, 6. Testen der App oder des Microservices, 7. Mithilfe von Push an das Repository übertragen und Prozedur wiederholen</span><span class="sxs-lookup"><span data-stu-id="5b161-405">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="5b161-406">**Abbildung 5-15**.</span><span class="sxs-lookup"><span data-stu-id="5b161-406">**Figure 5-15**.</span></span> <span data-ttu-id="5b161-407">Vereinfachter Workflow bei der Entwicklung mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b161-407">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="5b161-408">Darüber hinaus müssen Sie Schritt 2 (Hinzufügen von Docker-Unterstützung in Ihren Projekten) nur einmal ausführen.</span><span class="sxs-lookup"><span data-stu-id="5b161-408">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="5b161-409">Aus diesem Grund ähnelt der Workflow den üblichen Entwicklungsaufgaben bei Verwendung von .NET für andere Entwicklungsarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b161-409">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="5b161-410">Sie müssen wissen, was im Hintergrund passiert (Imageerstellungsprozess, verwendete Basisimages, Bereitstellung von Containern usw.), und in einigen Fällen müssen Sie auch die Dockerfile oder die docker-compose.yml-Datei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b161-410">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="5b161-411">Aber der Großteil der Arbeit wird durch Verwendung von Visual Studio, stark vereinfacht, und Ihre Produktivität wird entscheidend erhöht.</span><span class="sxs-lookup"><span data-stu-id="5b161-411">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5b161-412">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-412">Additional resources</span></span>

- <span data-ttu-id="5b161-413">**Steve Lasker. .NET Docker Development with Visual Studio 2017 (.NET-Docker-Entwicklung mit Visual Studio 2017)**  </span><span class="sxs-lookup"><span data-stu-id="5b161-413">**Steve Lasker. .NET Docker Development with Visual Studio 2017** </span></span>\
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="5b161-414">Verwenden von PowerShell-Befehlen in einer Dockerfile-Datei zum Einrichten von Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="5b161-414">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="5b161-415">[Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/index) ermöglichen es Ihnen, Ihre vorhandenen Windows-Anwendungen in Docker-Images zu konvertieren und diese mit den gleichen Tools wie den Rest des Docker-Ökosystems bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5b161-415">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="5b161-416">Um Windows-Container zu verwenden, führen Sie PowerShell-Befehle in der Dockerfile-Datei aus, was im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="5b161-416">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="5b161-417">In diesem Fall wird ein Windows Server Core-Basisimage (FROM-Einstellung) verwendet und IIS wird mit einem PowerShell-Befehl ausgeführt (RUN-Einstellung).</span><span class="sxs-lookup"><span data-stu-id="5b161-417">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="5b161-418">Auf ähnliche Weise können Sie auch PowerShell-Befehle verwenden, um zusätzliche Komponenten wie ASP.NET 4.x, .NET 4.6 oder andere Windows-Software einzurichten.</span><span class="sxs-lookup"><span data-stu-id="5b161-418">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="5b161-419">Der folgende Befehl in einer Dockerfile-Datei richtet z.B. ASP.NET 4.5 ein:</span><span class="sxs-lookup"><span data-stu-id="5b161-419">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="5b161-420">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b161-420">Additional resources</span></span>

- <span data-ttu-id="5b161-421">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="5b161-421">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="5b161-422">PowerShell-Beispielbefehle, die über Dockerfile-Dateien ausgeführt werden, um Windows-Features zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="5b161-422">Example PowerShell commands to run from dockerfiles to include Windows features.</span></span>\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="5b161-423">[Zurück](index.md)
>[Weiter](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="5b161-423">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
