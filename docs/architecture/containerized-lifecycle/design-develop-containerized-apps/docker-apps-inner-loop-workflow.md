---
title: Inner-Loop-Entwicklungsworkflow für Docker-Apps
description: Lernen Sie den Workflow der „inneren Schleife“ bei der Entwicklung von Docker-Anwendungen kennen.
ms.date: 02/15/2019
ms.openlocfilehash: 3d2fc889d22dbf02acccfbf9231ad98fca224cff
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936813"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="6c4ee-103">Inner-Loop-Entwicklungsworkflow für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="6c4ee-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="6c4ee-104">Bevor der Workflow der äußeren Schleife ausgelöst wird, der den gesamten DevOps-Zyklus umspannt, beginnt alle auf den Computern der einzelnen Entwickler, die den eigentlichen Code für die App in den bevorzugten Sprachen oder auf den bevorzugten Plattformen erstellen und ihn lokal testen (Abbildung 4–21).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="6c4ee-105">In jedem Fall haben Sie aber einen wichtigen Punkt gemein, unabhängig von Ihrer Wahl von Sprache, Framework oder Plattform.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="6c4ee-106">In diesem besonderen Workflow entwickeln und testen Sie stets Docker-Container, das aber lokal.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Abbildung, die das Konzept einer Entwicklungsumgebung mit innerer Schleife zeigt.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

<span data-ttu-id="6c4ee-108">**Abbildung 4-21:**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-108">**Figure 4-21**.</span></span> <span data-ttu-id="6c4ee-109">Entwicklungskontext der inneren Schleife</span><span class="sxs-lookup"><span data-stu-id="6c4ee-109">Inner-loop development context</span></span>

<span data-ttu-id="6c4ee-110">Der Container oder die Instanz eines Docker-Images enthält diese Komponenten:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="6c4ee-111">Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="6c4ee-112">Vom Entwickler hinzugefügte Dateien (z.B. Anwendungsbinärdateien)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="6c4ee-113">Konfiguration (z.B. Umgebungseinstellungen und Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="6c4ee-114">Anweisungen für die von Docker auszuführenden Prozesse</span><span class="sxs-lookup"><span data-stu-id="6c4ee-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="6c4ee-115">Sie können den Entwicklungsworkflow der inneren Schleife, dr Docker verwendet, als Prozess einrichten (im nächsten Abschnitt beschrieben).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="6c4ee-116">Beachten Sie, dass die anfänglichen Schritte zum Einrichten der Umgebung nicht enthalten sind, da sie nur einmal ausgeführt werden müssenC.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="6c4ee-117">Erstellen einer einzelnen App innerhalb eines Docker-Containers mithilfe von Visual Studio Code und Docker CLI</span><span class="sxs-lookup"><span data-stu-id="6c4ee-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="6c4ee-118">Apps bestehen aus Ihren eigenen Diensten zuzüglich zusätzlicher Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="6c4ee-119">Abbildung 4–22 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-App ausführen müssen, gefolgt von ausführlichen Beschreibungen der einzelnen Schritte.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Das Diagramm zeigt die erforderlichen sieben Schritte zum Erstellen einer Container-App.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

<span data-ttu-id="6c4ee-121">**Abbildung 4-22.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-121">**Figure 4-22**.</span></span> <span data-ttu-id="6c4ee-122">Allgemeiner Workflow für den Lebenszyklus von in Containern verpackten Docker-Anwendungen unter Verwendung der Docker CLI</span><span class="sxs-lookup"><span data-stu-id="6c4ee-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="6c4ee-123">Schritt 1: Beginn der Codeerstellung in Visual Studio Code und Erstellen der anfänglichen App/Dienstbaseline</span><span class="sxs-lookup"><span data-stu-id="6c4ee-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="6c4ee-124">Die Art, wie Sie Ihre Anwendung entwickeln, ähnelt der Weise, wie Sie das ohne Docker erledigen würden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="6c4ee-125">Der Unterschied besteht darin, dass Sie beim Entwickeln eine Anwendung oder Dienste bereitstellen und testen, die in Docker-Containern ausgeführt werden, die in Ihrer lokalen Umgebung (wie einer Linux-VM oder Windows) platziert sind.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="6c4ee-126">**Einrichten Ihrer lokalen Umgebung**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-126">**Setting up your local environment**</span></span>

<span data-ttu-id="6c4ee-127">Mit den neuesten Versionen von Docker für Mac und Windows ist es einfacher denn je, Docker-Anwendungen zu entwickeln, und die Einrichtung ist geradlinig.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!TIP]
> <span data-ttu-id="6c4ee-128">Anweisungen zum Einrichten von Docker für Windows finden Sie unter <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-128">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="6c4ee-129">Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-129">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="6c4ee-130">Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung tatsächlich entwickeln können, während Sie die Docker CLI verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-130">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="6c4ee-131">Microsoft stellt Visual Studio Code zur Verfügung, einen schlanken Code-Editor. Dieser wird unter Windows, Linux und macOS unterstützt und bietet IntelliSense-Funktionen mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten modernen Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [Integration in Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [Unterstützung für Erweiterungen](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-131">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Windows, Linux, and macOS, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="6c4ee-132">Dieser Editor eignet sich hervorragend für macOS- and Linux-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-132">This editor is a great fit for macOS and Linux developers.</span></span> <span data-ttu-id="6c4ee-133">Unter Windows können Sie auch Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-133">In Windows, you also can use Visual Studio.</span></span>

> [!TIP]
> <span data-ttu-id="6c4ee-134">Anweisungen zum Installieren von Visual Studio Code für Windows, Linux oder macOS finden Sie unter <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-134">For instructions on installing Visual Studio Code for Windows, Linux, or macOS, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="6c4ee-135">Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-135">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="6c4ee-136">Sie können mit Docker CLI arbeiten und Ihren Code mithilfe eines beliebigen Code-Editors erstellen, die Verwendung von Visual Studio Code mit der Docker-Erweiterung macht es aber einfacher, `Dockerfile` und `docker-compose.yml`-Dateien in Ihrem Arbeitsbereich zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-136">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="6c4ee-137">Sie können darüber hinaus Aufgaben und Skripts aus der Visual Studio Code IDE ausführen, um Docker-Befehle mithilfe der zugrunde liegenden Docker CLI auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-137">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="6c4ee-138">Die Docker-Erweiterung für VS Code bietet die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-138">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="6c4ee-139">Automatische Erstellung von `Dockerfile` und `docker-compose.yml`-Dateien</span><span class="sxs-lookup"><span data-stu-id="6c4ee-139">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="6c4ee-140">Syntaxhervorhebung und QuickInfo-Hinweise für `docker-compose.yml` und `Dockerfile`-Dateien</span><span class="sxs-lookup"><span data-stu-id="6c4ee-140">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="6c4ee-141">IntelliSense (Vervollständigungen) für `Dockerfile` und `docker-compose.yml`-Dateien</span><span class="sxs-lookup"><span data-stu-id="6c4ee-141">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="6c4ee-142">Linting (Fehler und Warnungen) für `Dockerfile`-Dateien</span><span class="sxs-lookup"><span data-stu-id="6c4ee-142">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="6c4ee-143">Integration der Befehlspalette (F1) für die gängigsten Docker-Befehle</span><span class="sxs-lookup"><span data-stu-id="6c4ee-143">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="6c4ee-144">Explorer-Integration für die Verwaltung von Images und Containern</span><span class="sxs-lookup"><span data-stu-id="6c4ee-144">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="6c4ee-145">Bereitstellen von Images von DockerHub und Azure-Containerregistrierungen in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="6c4ee-145">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="6c4ee-146">Drücken Sie zum Installieren der Docker-Erweiterung STRG+UMSCHALT+P, geben Sie `ext install` ein, und führen Sie den Befehl „Erweiterung installieren“ aus, um die Liste der Marketplace-Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-146">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="6c4ee-147">Geben Sie dann **Docker** ein, um die Ergebnisse zu filtern, und wählen Sie dann die Docker Support-Erweiterung aus, wie in Abbildung 4–23 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-147">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Ansicht der Docker-Erweiterung für Visual Studio Code.](./media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

<span data-ttu-id="6c4ee-149">**Abbildung 4-23.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-149">**Figure 4-23**.</span></span> <span data-ttu-id="6c4ee-150">Installieren der Docker-Erweiterung in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6c4ee-150">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="6c4ee-151">Schritt 2: Erstellen eines DockerFile zu einem vorhandenen Image (einfaches Betriebssystem oder Entwicklungsumgebungen wie .NET Core, Node.js und Ruby)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-151">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="6c4ee-152">Sie benötigen ein `DockerFile` pro erstelltem benutzerdefiniertem Image und pro bereitzustellendem Container.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-152">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="6c4ee-153">Wenn Ihre App aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie ein einzelnes `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-153">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="6c4ee-154">Wenn Ihre App sich jedoch aus mehreren Diensten zusammensetzt (wie bei einer Microservices-Architektur), benötigen Sie ein `Dockerfile` pro Dienst.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-154">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="6c4ee-155">Das `DockerFile` Dockerfile wird üblicherweise im Stammordner Ihrer App oder Ihres Dienstes platziert und enthält die erforderlichen Befehle, um Docker anzuweisen, wie der betreffende Dienst einzurichten und auszuführen ist.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-155">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="6c4ee-156">Sie können Ihr `DockerFile` erstellen und es Ihrem Projekt zusammen mit Ihrem Code (node.js, .NET Core usw.) hinzufügen, oder sich den folgenden Tipp ansehen, wenn Sie gerade erst in die Umgebung einsteigen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-156">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="6c4ee-157">Sie können die Docker-Erweiterung zur Führung beim Verwenden der `Dockerfile`- und `docker-compose.yml`-Dateien zu Ihren Docker-Containern verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-157">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="6c4ee-158">Im Lauf der Zeit werden Sie diese Art von Dateien wahrscheinlich ohne dieses Tool schreiben, die Verwendung der Docker-Erweiterung bildet aber einen guten Ausgangspunkt, der Ihren Lernprozess beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-158">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="6c4ee-159">In Abbildung 4–24 können Sie sehen, wie eine docker-compose-Datei mithilfe der Docker-Erweiterung für VS Code hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-159">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Konsolenansicht der Docker-Erweiterung für VS Code.](./media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

<span data-ttu-id="6c4ee-161">**Abbildung 4-24.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-161">**Figure 4-24**.</span></span> <span data-ttu-id="6c4ee-162">Mithilfe des Befehls **Add Docker files to Workspace** (Docker-Dateien zu Arbeitsbereich hinzufügen) hinzugefügte Docker-Dateien</span><span class="sxs-lookup"><span data-stu-id="6c4ee-162">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="6c4ee-163">Wenn Sie ein DockerFile hinzufügen, geben Sie an, welches Docker-Basisimage Sie verwenden (wie bei der Verwendung von `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-163">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="6c4ee-164">Normalerweise erstellen Sie Ihr benutzerdefiniertes Image auf der Grundlage einem Basisimage, das Sie aus einem beliebigen offiziellen Repository in der [Docker Hub-Registrierung](https://hub.docker.com/) beziehen (wie ein [Image für .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) oder das Image [für Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-164">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="6c4ee-165">***Verwenden eines vorhandenen offiziellen Docker-Images***</span><span class="sxs-lookup"><span data-stu-id="6c4ee-165">***Use an existing official Docker image***</span></span>

<span data-ttu-id="6c4ee-166">Durch Verwendung eines offiziellen Repositorys eines Sprachstapels mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (Entwicklung, Test und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-166">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="6c4ee-167">Das Folgende ist ein Beispiel-DockerFile für einen .NET Core-Container:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-167">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="6c4ee-168">In diesem Fall basiert das Image auf Version 2.2 des offiziellen ASP.NET Core-Docker-Images (mehrere Architekturen für Linux und Windows), gemäß der Zeile `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-168">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="6c4ee-169">(Weitere Informationen zu diesem Thema finden Sie unter [ASP.NET Core Docker Image (ASP.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) und [.NET Core Docker Image (.NET Core-Docker-Image)](https://hub.docker.com/_/microsoft-dotnet-core/).)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-169">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="6c4ee-170">In dem DockerFile können Sie Docker außerdem anweisen, an dem TCP-Port zu lauschen, den Sie zur Laufzeit verwenden möchten (z.B. Port 80).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-170">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="6c4ee-171">Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-171">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="6c4ee-172">Beispielsweise weist die `ENTRYPOINT`-Zeile mit `["dotnet", "MySingleContainerWebApp.dll"]` Docker an, eine .NET Core-Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-172">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="6c4ee-173">Wenn Sie das SDK und die .NET Core-CLI (`dotnet CLI`) verwenden, um die .NET-Anwendung zu entwickeln und auszuführen, wird eine andere Einstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-173">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="6c4ee-174">Entscheidend ist, dass die ENTRYPOINT-Zeile und andere Einstellungen von der Sprache und Plattform abhängen, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-174">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!TIP]
> <span data-ttu-id="6c4ee-175">Weitere Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-175">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="6c4ee-176">Weitere Informationen über das Erstellen eigener Images finden Sie unter <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-176">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="6c4ee-177">**Verwenden von Repositorys für Images für mehrere Architekturen**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-177">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="6c4ee-178">Der Name eines einzelnen Images in einem Repository kann Plattformvarianten enthalten, wie z.B. ein Linux-Image und ein Windows-Image.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-178">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="6c4ee-179">Dieses Feature ermöglicht Anbietern wie Microsoft (Basisimageentwickler), ein Repository für mehrere Plattformen (Linux und Windows) zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-179">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="6c4ee-180">Das in der Docker Hub-Registrierung verfügbare [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)-Repository bietet beispielsweise Unterstützung für Linux und Windows Nano Server dadurch, dass der gleiche Imagename verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-180">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="6c4ee-181">Beim Pullen des [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)-Images von einem Windows-Host wird die Windows-Variante gepullt, während das Pullen des gleichen Imagenamens von einem Linux-Host ein Pullen der Linux-Variante bewirkt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-181">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="6c4ee-182">***Erstellen eines Basisimages von Grund auf***</span><span class="sxs-lookup"><span data-stu-id="6c4ee-182">***Create your base image from scratch***</span></span>

<span data-ttu-id="6c4ee-183">Sie können Ihr eigenes Docker-Basisimage von Grund auf neu erstellen, wie in diesem [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker erläutert.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-183">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="6c4ee-184">Dieses Szenario ist für Sie vermutlich nicht ideal, wenn Sie gerade erst in Docker einsteigen, aber wenn Sie die spezifischen Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-184">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="6c4ee-185">Schritt 3: Erstellen eines angepassten Docker-Images durch Einbetten eines Diensts</span><span class="sxs-lookup"><span data-stu-id="6c4ee-185">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="6c4ee-186">Für jeden benutzerdefinierten Dienst, den Ihre App beinhaltet, müssen Sie ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-186">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="6c4ee-187">Wenn Ihre App aus einem einzelnen Dienst oder einer einzelnen Web-App besteht, benötigen Sie nur ein einzelnes Image.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-187">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="6c4ee-188">Wenn Sie die „DevOps-Workflow der äußeren Schleife“ berücksichtigen, werden immer, wenn Sie Ihren Quellcode per Push in ein Git-Repository übertragen (Continuous Integration), die Images mithilfe eines automatisierten Buildprozesses erstellt, sodass die Images in der globalen Umgebung aus Ihrem Quellcode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-188">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="6c4ee-189">Bevor wir aber den Weg in die äußere Schleife in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung tatsächlich ordnungsgemäß arbeitet, sodass kein Code an das Quellcodeverwaltungssystem (Git usw.) übertragen wird, der möglicherweise nicht ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-189">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="6c4ee-190">Daher muss jeder Entwickler zuerst den gesamten Prozess der inneren Schleife absolvieren, um lokal zu testen und mit der Entwicklung fortzufahren, bis er eine vollständige Funktion oder Änderung an das Quellcodeverwaltungssystem übertragen möchte.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-190">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="6c4ee-191">Um ein Image in Ihrer lokalen Umgebung zu erstellen und das DockerFile zu verwenden, können Sie den Docker-Erstellungsbefehl verwenden, wie in Abbildung 4–25 veranschaulicht (Sie können auch `docker-compose up --build` für Anwendungen ausführen, die aus mehreren Containern/Diensten zusammengesetzt sind).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-191">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Der Screenshot zeigt die Konsolenausgabe des Befehls „docker build“.](./media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

<span data-ttu-id="6c4ee-193">**Abbildung 4-25.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-193">**Figure 4-25**.</span></span> <span data-ttu-id="6c4ee-194">Ausführen des Docker-Erstellungsbefehls</span><span class="sxs-lookup"><span data-stu-id="6c4ee-194">Running docker build</span></span>

<span data-ttu-id="6c4ee-195">Statt `docker build` direkt aus dem Projektordner auszuführen, können Sie optional auch zuerst einen bereitstellbaren Ordner mit den erforderlichen .NET-Bibliotheken generieren, indem Sie den `dotnet publish`-Ausführungsbefehl verwenden und dann `docker build` ausführen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-195">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="6c4ee-196">Dieses Beispiel erstellt ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` (`:first` ist ein Tag, wie eine spezifische Version).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-196">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="6c4ee-197">Sie können diesen Schritt für jedes benutzerdefinierte Image ausführen, das Sie für Ihre aus mehreren Containern zusammengesetzte Docker-Anwendung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-197">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="6c4ee-198">Sie können die vorhandenen Images in Ihrem lokalen Repository (Ihrem Bereitstellungscomputer) suchen, indem Sie den „docker images“-Befehl verwenden, wie in Abbildung 4–26 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-198">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Konsolenausgabe des Befehls „docker images“, gezeigt werden vorhandene Images.](./media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="6c4ee-200">**Abbildung 4-26.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-200">**Figure 4-26**.</span></span> <span data-ttu-id="6c4ee-201">Anzeigen vorhandener Images mithilfe des Befehls „docker images“</span><span class="sxs-lookup"><span data-stu-id="6c4ee-201">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="6c4ee-202">Schritt 4: Definieren Ihrer Dienste in der Datei „docker-compose.yml“ beim Erstellen einer zusammengesetzten Docker-Anwendung mit mehreren Diensten</span><span class="sxs-lookup"><span data-stu-id="6c4ee-202">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="6c4ee-203">Mit der Datei `docker-compose.yml` können Sie einen Satz verwandter Dienste definieren, die mit den im nächsten Schritt beschriebenen Bereitstellungsbefehlen als zusammengesetzte Anwendung bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-203">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="6c4ee-204">Erstellen Sie die betreffende Datei in Ihrem Haupt- oder Stamm-Projektmappenordner; seine Inhalte sollten ähnlich den in dieser `docker-compose.yml`-Datei dargestellten sein:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-204">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="6c4ee-205">In diesem speziellen Fall definiert diese Datei zwei Dienste: den Webdienst (Ihren benutzerdefinierten Dienst) und den Redis-Dienst (einen beliebten Cachedienst).</span><span class="sxs-lookup"><span data-stu-id="6c4ee-205">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="6c4ee-206">Jeder Dienst wird als Container bereitgestellt, wir müssen also für jeden ein konkretes Docker-Image verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-206">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="6c4ee-207">Für diesen speziellen Webdienst muss das Image Folgendes leisten:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-207">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="6c4ee-208">Einen Build aus dem DockerFile im aktuellen Verzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="6c4ee-208">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="6c4ee-209">Den verfügbar gemachten Port 80 des Containers an Port 81 auf dem Hostcomputer weiterleiten</span><span class="sxs-lookup"><span data-stu-id="6c4ee-209">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="6c4ee-210">Das Projektverzeichnis auf dem Host für „/code“ innerhalb des Containers einzubinden, was es Ihnen ermöglicht, den Code zu ändern, ohne das Image neu erstellen zu müssen</span><span class="sxs-lookup"><span data-stu-id="6c4ee-210">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="6c4ee-211">Den Webdienst mit dem Redis-Dienst verknüpfen</span><span class="sxs-lookup"><span data-stu-id="6c4ee-211">Link the web service to the redis service</span></span>

<span data-ttu-id="6c4ee-212">Der Redis-Dienst verwendet die [neuesten öffentliche Redis-Image](https://hub.docker.com/_/redis/), die er mithilfe von Pull aus Docker Hub-Registrierung abruft.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-212">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="6c4ee-213">[Redis](https://redis.io/) ist ein beliebtes Cachesystem für serverseitige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-213">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="6c4ee-214">Schritt 5: Erstellen und Ausführen Ihrer Docker-App</span><span class="sxs-lookup"><span data-stu-id="6c4ee-214">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="6c4ee-215">Wenn Ihre App nur einen einzelnen Container aufweist, müssen Sie ihn lediglich ausführen, indem Sie ihn auf Ihrem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-215">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="6c4ee-216">Wenn sich Ihre App jedoch aus mehreren Diensten zusammensetzt, müssen Sie sie außerdem *zusammenstellen*.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-216">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="6c4ee-217">Betrachten wir die verschiedenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-217">Let's see the different options.</span></span>

<span data-ttu-id="6c4ee-218">***Option A: Ausführen eines einzelnen Containers oder Diensts***</span><span class="sxs-lookup"><span data-stu-id="6c4ee-218">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="6c4ee-219">Sie können das Docker-Image mithilfe des Ausführen-Befehls von Docker ausführen, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-219">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="6c4ee-220">Für diese spezielle Bereitstellung leiten wir Anforderungen, die an Port 80 gesendet werden, an den internen Port 5000 um.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-220">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="6c4ee-221">Jetzt lauscht die Anwendung am externen Port 80 auf der Hostebene.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-221">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="6c4ee-222">***Option B: Zusammenstellen und Ausführen einer aus mehreren Containern bestehenden Anwendung***</span><span class="sxs-lookup"><span data-stu-id="6c4ee-222">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="6c4ee-223">In den meisten Unternehmensszenarien ist eine Docker-Anwendung aus mehreren Diensten zusammengesetzt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-223">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="6c4ee-224">In diesen Fällen können Sie den `docker-compose up`-Befehl (Abbildung 4–27) ausführen, der die docker-compose.yml-Datei verwendet, die Sie möglicherweise bereits zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-224">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="6c4ee-225">Durch Ausführen dieses Befehls wird eine zusammengesetzte Anwendung mit allen zugehörigen Containern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-225">Running this command deploys a composed application with all of its related containers.</span></span>

![Konsolenausgabe des Befehls „docker-compose up“.](./media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

<span data-ttu-id="6c4ee-227">**Abbildung 4-27.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-227">**Figure 4-27**.</span></span> <span data-ttu-id="6c4ee-228">Ergebnisse der Ausführung des Befehls „docker-compose up“</span><span class="sxs-lookup"><span data-stu-id="6c4ee-228">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="6c4ee-229">Nach dem Ausführen von `docker-compose up` stellen Sie Ihre Anwendung und ihre zugehörigen Container auf Ihrem Docker-Host bereit, wie in Abbildung 4–28 in der VM-Darstellung abgebildet.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-229">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![VM, die Anwendungen aus mehreren Containern ausführt.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="6c4ee-231">**Abbildung 4-28.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-231">**Figure 4-28**.</span></span> <span data-ttu-id="6c4ee-232">VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="6c4ee-232">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="6c4ee-233">Schritt 6: Testen der Docker-Anwendung (lokal, auf Ihrer lokalen CD-VM)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-233">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="6c4ee-234">Dieser Schritt unterscheidet sich je nachdem, welche Aktionen Ihre App ausführt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-234">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="6c4ee-235">In einer einfachen .NET Core-Web-API „Hallo Welt“, die als einzelner Container oder Dienst bereitgestellt wird, müssen Sie lediglich auf den Dienst zugreifen, indem Sie den im DockerFile angegebenen TCP-Port übergeben.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-235">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="6c4ee-236">Wenn localhost nicht aktiviert ist, navigieren Sie zu Ihrem Dienst, indem Sie die IP-Adresse für den Computer mithilfe dieses Befehls ermitteln:</span><span class="sxs-lookup"><span data-stu-id="6c4ee-236">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="6c4ee-237">Öffnen Sie auf dem Docker-Host einen Browser, und navigieren Sie zu der betreffenden Website; Sie sollten Ihre aktiv ausgeführte App/Ihren ausgeführten Webdienst sehen, wie in Abbildung 4–29 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-237">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Browseransicht der Antwort von „localhost/API/values“.](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="6c4ee-239">**Abbildung 4-29.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-239">**Figure 4-29**.</span></span> <span data-ttu-id="6c4ee-240">Lokales Testen Ihrer Docker-Anwendung mithilfe von localhost</span><span class="sxs-lookup"><span data-stu-id="6c4ee-240">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="6c4ee-241">Beachten Sie, dass sie Port 80 verwendet, der aber intern an Port 5000 umgeleitet wird, weil es in dieser Weise mit `docker run` bereitgestellt wurde, wie bereits zuvor erläutert.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-241">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="6c4ee-242">Sie können dies mithilfe von CURL am Terminal testen.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-242">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="6c4ee-243">In einer Docker-Installation unter Windows ist die Standard-IP-Adresse 10.0.75.1, wie in Abbildung 4–30 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-243">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Konsolenausgabe beim Abrufen von http://10.0.75.1/API/values mit curl](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="6c4ee-245">**Abbildung 4-30.**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-245">**Figure 4-30**.</span></span> <span data-ttu-id="6c4ee-246">Lokales Testen einer Docker-Anwendung mithilfe von CURL</span><span class="sxs-lookup"><span data-stu-id="6c4ee-246">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="6c4ee-247">**Debuggen eines in Docker ausgeführten Containers**</span><span class="sxs-lookup"><span data-stu-id="6c4ee-247">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="6c4ee-248">Visual Studio Code unterstützt das Debuggen von Docker, wenn Sie Node.js und andere Plattformen wie .NET Core-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-248">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="6c4ee-249">Wenn Sie Visual Studio für Windows oder Mac verwenden, können Sie darüber hinaus .NET Core- oder .NET Framework-Container in Docker debuggen, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-249">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!TIP]
> <span data-ttu-id="6c4ee-250">Weitere Informationen zum Debuggen von Node.js-Docker-Containern finden Sie unter <https://blog.docker.com/2016/07/live-debugging-docker/> und <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span><span class="sxs-lookup"><span data-stu-id="6c4ee-250">To learn more about debugging Node.js Docker containers, see <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6c4ee-251">[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="6c4ee-251">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
