---
title: Inner-Loop-Entwicklungsworkflow für Docker-Apps
description: Erfahren Sie, die "innere Schleife"-Workflow für die Entwicklung von Docker-Anwendungen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58920908"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="cd463-103">Inner-Loop-Entwicklungsworkflow für Docker-Apps</span><span class="sxs-lookup"><span data-stu-id="cd463-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="cd463-104">Vor dem Auslösen des äußeren Schleife Workflows umfasst den gesamten DevOps-Zyklus, es beginnt alles auf dem Computer jedes Entwicklers, die app selbst zu codieren, verwenden ihren bevorzugten Sprachen oder Plattformen und diese lokal testen (Abbildung 4-21).</span><span class="sxs-lookup"><span data-stu-id="cd463-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="cd463-105">In jedem Fall müssen Sie aber einen wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="cd463-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="cd463-106">In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern, aber lokal.</span><span class="sxs-lookup"><span data-stu-id="cd463-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Schritt 1: Code, Ausführungs-und Debuggen](./media/image18.png)

<span data-ttu-id="cd463-108">**Abbildung 4-21:**</span><span class="sxs-lookup"><span data-stu-id="cd463-108">**Figure 4-21**.</span></span> <span data-ttu-id="cd463-109">Innere Schleife Development-Kontext</span><span class="sxs-lookup"><span data-stu-id="cd463-109">Inner-loop development context</span></span>

<span data-ttu-id="cd463-110">Der Container oder eine Instanz eines Docker-Images werden diese Komponenten enthalten:</span><span class="sxs-lookup"><span data-stu-id="cd463-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="cd463-111">Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)</span><span class="sxs-lookup"><span data-stu-id="cd463-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="cd463-112">Dateien, die vom Entwickler (z.B. app-Binärdateien) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="cd463-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="cd463-113">Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="cd463-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="cd463-114">Anweisungen für welche Aspekte Sie verarbeitet die Ausführung von Docker</span><span class="sxs-lookup"><span data-stu-id="cd463-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="cd463-115">Sie können die innere Schleife Entwicklungsworkflow einrichten, die Docker wie der Prozess (im nächsten Abschnitt beschrieben) verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd463-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="cd463-116">Erwägen Sie, dass die ersten Schritte zum Einrichten der Umgebung nicht eingeschlossen werden, da Sie nur einmal tun müssen.</span><span class="sxs-lookup"><span data-stu-id="cd463-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="cd463-117">Erstellen eine einzelne app in Docker-Container mit Visual Studio Code und Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="cd463-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="cd463-118">Apps bestehen aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="cd463-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="cd463-119">Abbildung 4-22 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-app, gefolgt von ausführliche Beschreibungen der einzelnen Schritte ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="cd463-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Übersicht über Workflow –: Schritt 1: Code, Schritt2: Schreiben von dockerfile-Dateien, Schritt 3: Erstellen von Images mit docker-Dateien, Schritt 4 definiert – definieren Sie mit Schritt 5: Ausführen von Containern docker-Compose-Datei, Dienste oder zusammengesetzte Anwendungen, Schritt 6 – Test-apps, Schritt 7: per Push übertragen, um zu beginnen die äußere Schleife (CI/CD-Pipelines), oder de Veloping.](./media/image19.png)

<span data-ttu-id="cd463-121">**Abbildung 4-22.**</span><span class="sxs-lookup"><span data-stu-id="cd463-121">**Figure 4-22**.</span></span> <span data-ttu-id="cd463-122">Allgemeiner Workflow für die Lebenszyklus von Docker-containeranwendungen mit Docker CLI</span><span class="sxs-lookup"><span data-stu-id="cd463-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="cd463-123">Schritt 1: Beginnen mit dem Programmieren in Visual Studio Code, und erstellen Sie Ihrer ersten app/des Diensts</span><span class="sxs-lookup"><span data-stu-id="cd463-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="cd463-124">Die Möglichkeit, die Sie bei der Entwicklung Ihrer Anwendung ist ähnlich wie Sie es ohne Docker.</span><span class="sxs-lookup"><span data-stu-id="cd463-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="cd463-125">Der Unterschied besteht darin, dass beim Entwickeln, sind Sie bereitstellen und Testen Ihre Anwendung oder Dienste, die in Docker-Containern platziert, die in Ihrer lokalen Umgebung (z.B. eine Linux-VM oder Windows) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd463-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="cd463-126">**Das Einrichten Ihrer lokalen Umgebung**</span><span class="sxs-lookup"><span data-stu-id="cd463-126">**Setting up your local environment**</span></span>

<span data-ttu-id="cd463-127">Mit den neuesten Versionen von Docker für Mac und Windows es ist einfacher als je zuvor zu Docker-Anwendungen entwickeln, und das Setup ist einfach.</span><span class="sxs-lookup"><span data-stu-id="cd463-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="cd463-129">Anweisungen zum Einrichten von Docker für Windows finden Sie unter <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="cd463-130">Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="cd463-131">Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-CLI tatsächlich entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="cd463-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="cd463-132">Microsoft bietet Visual Studio Code, einem einfachen Code-Editor, die unter Mac, Windows und Linux unterstützt, und bietet IntelliSense mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten Moderne Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [-Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="cd463-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="cd463-133">Dieser Editor ist ideal für Mac und Linux-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="cd463-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="cd463-134">In Windows können Sie auch die vollständige Visual Studio-Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd463-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="cd463-136">Anweisungen zum Installieren von Visual Studio Code für Windows, Mac oder Linux finden Sie unter <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="cd463-137">Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="cd463-138">Sie können Arbeit mit Docker-CLI und Schreiben Sie Ihren Code mit jedem Code-Editor, aber mit Visual Studio Code mit der Docker-Erweiterung vereinfacht Autor `Dockerfile` und `docker-compose.yml` Dateien in Ihrem Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="cd463-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="cd463-139">Sie können auch Aufgaben und Skripts aus Visual Studio Code-IDE zum Ausführen von Docker-Befehlen, die mit der Docker CLI unter ausführen.</span><span class="sxs-lookup"><span data-stu-id="cd463-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="cd463-140">Die Docker-Erweiterung für Visual Studio Code bietet die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="cd463-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="cd463-141">Automatische `Dockerfile` und `docker-compose.yml` Datei generieren</span><span class="sxs-lookup"><span data-stu-id="cd463-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="cd463-142">Hervorhebung und zeigen Sie Tipps zur Syntax für `docker-compose.yml` und `Dockerfile` Dateien</span><span class="sxs-lookup"><span data-stu-id="cd463-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="cd463-143">IntelliSense (vervollständigungen) für `Dockerfile` und `docker-compose.yml` Dateien</span><span class="sxs-lookup"><span data-stu-id="cd463-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="cd463-144">Linting (Fehler und Warnungen) für `Dockerfile` Dateien</span><span class="sxs-lookup"><span data-stu-id="cd463-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="cd463-145">Befehl Palette (F1)-Integration für die am häufigsten verwendeten Docker-Befehle</span><span class="sxs-lookup"><span data-stu-id="cd463-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="cd463-146">Explorer-Integration für die Verwaltung von Images und Containern</span><span class="sxs-lookup"><span data-stu-id="cd463-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="cd463-147">Bereitstellen von Images von DockerHub und Azure-Containerregistrierungen in Azure App Service</span><span class="sxs-lookup"><span data-stu-id="cd463-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="cd463-148">Zum Installieren der Docker-Erweiterung, drücken Sie STRG + UMSCHALT + P, geben `ext install`, und führen Sie den Befehl "Erweiterung installieren", um die Liste der Marketplace-Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd463-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="cd463-149">Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie dann die Erweiterung für Docker-Unterstützung, wie in Abbildung 4-23 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd463-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Ansicht der Docker-Erweiterung für Visual Studio Code.](./media/image20.png)

<span data-ttu-id="cd463-151">**Abbildung 4-23.**</span><span class="sxs-lookup"><span data-stu-id="cd463-151">**Figure 4-23**.</span></span> <span data-ttu-id="cd463-152">Installieren der Docker-Erweiterungs in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cd463-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="cd463-153">Schritt 2: Erstellen Sie eine dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (einfaches Betriebssystem oder entwicklungsumgebungen wie .NET Core, Node.js und Ruby)</span><span class="sxs-lookup"><span data-stu-id="cd463-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="cd463-154">Sie müssen eine `DockerFile` pro benutzerdefiniertes Image erstellt werden und Container bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd463-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="cd463-155">Wenn Ihre app aus einen benutzerdefinierten Dienst besteht, benötigen Sie ein einzelnes `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="cd463-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="cd463-156">Aber wenn Ihre app aus mehreren Diensten (wie in einer Microservices-Architektur) besteht, benötigen Sie ein `Dockerfile` pro Dienst.</span><span class="sxs-lookup"><span data-stu-id="cd463-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="cd463-157">Die `DockerFile` wird häufig im Stammordner Ihrer app oder Ihres Diensts und enthält die erforderlichen Befehle aus, damit Docker weiß, wie einrichten und Ausführen dieser app oder Ihres Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd463-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="cd463-158">Sie erstellen Ihre `DockerFile` und fügen sie dem Projekt zusammen mit Ihrem Code hinzu (.NET Core, node.js usw.), oder, wenn Sie in der Umgebung vertraut sind, sehen Sie sich den folgenden Tipp.</span><span class="sxs-lookup"><span data-stu-id="cd463-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="cd463-159">Können Sie die Docker-Erweiterung Anleitung für die Verwendung der `Dockerfile` und `docker-compose.yml` Dateien im Zusammenhang mit der Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="cd463-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="cd463-160">Schließlich schreiben Sie wahrscheinlich diese Arten von Dateien ohne dieses Tool, aber mit der Docker-Erweiterung ist ein guter Ausgangspunkt, der mit der Lernprozess beschleunigt wird.</span><span class="sxs-lookup"><span data-stu-id="cd463-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="cd463-161">In Abbildung 4-24, können Sie sehen, wie ein Docker-compose-Datei wird mithilfe der Docker-Erweiterung für Visual Studio Code hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cd463-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Die Konsolenansicht der Docker-Erweiterung für Visual Studio Code.](./media/image24.png)

<span data-ttu-id="cd463-163">**Abbildung 4-24.**</span><span class="sxs-lookup"><span data-stu-id="cd463-163">**Figure 4-24**.</span></span> <span data-ttu-id="cd463-164">Docker-Dateien hinzugefügt, mit der **Hinzufügen von Docker-Dateien auf Workspace-Befehl**</span><span class="sxs-lookup"><span data-stu-id="cd463-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="cd463-165">Wenn Sie eine dockerfile-Datei hinzufügen, geben Sie welche Docker-Basisimage Sie verwenden (wie die Verwendung von `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span><span class="sxs-lookup"><span data-stu-id="cd463-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="cd463-166">Erstellen Sie in der Regel Ihr benutzerdefinierte Image auf einem Basisimage, die Sie aus einem offiziellen-Repository auf erhalten die [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. eine [Images für .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) oder der [für Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="cd463-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="cd463-167">***Verwenden Sie ein vorhandenes offizielles dockerimage***</span><span class="sxs-lookup"><span data-stu-id="cd463-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="cd463-168">Mit einem offiziellen-Repository eines Stapels Sprache mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklung, Tests und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cd463-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="cd463-169">Im folgenden finden eine DockerFile-Beispieldatei für eine .NET Core-Container:</span><span class="sxs-lookup"><span data-stu-id="cd463-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="cd463-170">Das Bild in diesem Fall basiert auf Version 2.1 von der offiziellen ASP.NET Core-Docker-Image (Multi-Arch für Linux und Windows), gemäß der Zeile `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span><span class="sxs-lookup"><span data-stu-id="cd463-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`.</span></span> <span data-ttu-id="cd463-171">(Weitere Informationen zu diesem Thema finden Sie unter den [ASP.NET Core-Docker-Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Seite und die [.NET Core-Docker-Image](https://hub.docker.com/_/microsoft-dotnet-core/) Seite).</span><span class="sxs-lookup"><span data-stu-id="cd463-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="cd463-172">In der dockerfile-Datei können Sie auch weisen Docker an zum TCP-Port zu lauschen, die Sie zur Laufzeit (z. B. Port 80) verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd463-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="cd463-173">Je nach Sprache und Framework, die Sie verwenden, können Sie zusätzliche Konfigurationseinstellungen in der Dockerfile angeben.</span><span class="sxs-lookup"><span data-stu-id="cd463-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="cd463-174">Z. B. die `ENTRYPOINT` Linie mit `["dotnet", "MySingleContainerWebApp.dll"]` teilt Docker zum Ausführen einer .NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="cd463-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="cd463-175">Wenn Sie das SDK und .NET Core-CLI nutzen (`dotnet CLI`) zum Erstellen, und führen Sie die Anwendung .NET, diese Einstellung wären unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="cd463-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="cd463-176">Der ausschlaggebende Punkt hierbei ist, dass die ENTRYPOINT-Zeile und andere Einstellungen hängen von der Sprache und Plattform, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="cd463-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="cd463-178">Weitere Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="cd463-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="cd463-179">Wechseln Sie zu, um weitere Informationen zum Erstellen Ihrer eigenen Images <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="cd463-180">**Verwenden Sie die Repositorys für Images für mehrere Architekturen**</span><span class="sxs-lookup"><span data-stu-id="cd463-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="cd463-181">Ein einzelnes Image-Name in einem Repository kann Plattformvarianten, z. B. ein Linux-Image und ein Windows-Image enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd463-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="cd463-182">Dieses Feature ermöglicht Anbietern wie Microsoft (basisimageentwickler), um ein Repository für mehrere Plattformen (d. h., Linux und Windows) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd463-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="cd463-183">Z. B. die [Dotnet/Core/Aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Repository zur Verfügung, in der Docker-Hub-Registrierung bietet Unterstützung für Linux und Windows Nano Server mit denselben imagenamen ein.</span><span class="sxs-lookup"><span data-stu-id="cd463-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="cd463-184">Abrufen der [Dotnet/Core/Aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Image von einem Windows-Host Ruft die Windows-Variante, während der gleiche ImageName von einem Linux-Host ziehen die Linux-Variante abruft.</span><span class="sxs-lookup"><span data-stu-id="cd463-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="cd463-185">***Ihr Basisimage von Grund auf neu erstellen***</span><span class="sxs-lookup"><span data-stu-id="cd463-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="cd463-186">Sie können Ihre eigenen Docker-Basisimage von Grund auf neu erstellen, wie dies unter [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="cd463-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="cd463-187">Dieses Szenario ist wahrscheinlich nicht für Sie am besten geeignet, wenn Sie gerade mit Docker beginnen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="cd463-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="cd463-188">Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihrem Dienst darin einbetten</span><span class="sxs-lookup"><span data-stu-id="cd463-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="cd463-189">Für jeden benutzerdefinierten Dienst, die Ihre app umfasst, müssen Sie ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="cd463-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="cd463-190">Wenn Ihre app aus einem einzelnen Dienst oder Web-app besteht, benötigen Sie ein einziges Bild.</span><span class="sxs-lookup"><span data-stu-id="cd463-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="cd463-191">Wenn die "outer-Loop-DevOps-Workflow" berücksichtigen, die Bilder erstellt durch einen automatisierten Buildprozess zu, wenn Sie mithilfe von Push Ihren Quellcode in einem Git-Repository (Continuous Integration), übertragen sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="cd463-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="cd463-192">Aber bevor wir auf die äußere Schleife Route in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung ordnungsgemäß funktioniert, damit sie Code nicht die Warteschlange übertragen, die auf das Quellcodeverwaltungssystem (Git, usw.) möglicherweise nicht ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cd463-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="cd463-193">Jeder Entwickler muss daher zuerst führen Sie den gesamten Entwicklungsworkflow Prozess zum Testen lokal und weiterentwickeln, bis eine vollständige Funktion mithilfe von Push übertragen, oder ändern Sie in das Quellcodeverwaltungssystem werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd463-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="cd463-194">Um ein Image in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie die Docker-Erstellungsbefehl aus, wie in Abbildung 4-25 dargestellt (Sie können auch ausführen `docker-compose up --build` für Anwendungen besteht aus mehreren Containern/Diensten).</span><span class="sxs-lookup"><span data-stu-id="cd463-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Die Konsolenausgabe von der docker-Compose Build, zeigt die Bilder Fortschritt herunterladen.](./media/image25.png)

<span data-ttu-id="cd463-196">**Abbildung 4-25.**</span><span class="sxs-lookup"><span data-stu-id="cd463-196">**Figure 4-25**.</span></span> <span data-ttu-id="cd463-197">Docker-Build ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="cd463-197">Running docker build</span></span>

<span data-ttu-id="cd463-198">Optional, anstatt direkt `docker build` aus dem Projektordner, Sie zuerst können generieren einen bereitstellbaren Ordner mit den mithilfe der erforderlichen .NET-Bibliotheken `dotnet publish` Befehl aus, und führen Sie `docker build`.</span><span class="sxs-lookup"><span data-stu-id="cd463-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="cd463-199">In diesem Beispiel erstellt ein Docker-Image mit dem Namen `cesardl/netcore-webapi-microservice-docker:first` (`:first` ist ein Tag, wie eine bestimmte Version).</span><span class="sxs-lookup"><span data-stu-id="cd463-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="cd463-200">Sie können diesen Schritt für jedes benutzerdefinierte Image nutzen, die Sie für Ihre zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="cd463-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="cd463-201">Die vorhandenen Images finden in Ihrem lokalen Repository (Entwicklungscomputer) Sie unter Verwendung von der Docker Images-Befehl, wie in Abbildung 4-26 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cd463-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Konsolenausgabe Befehl Docker-Images, mit der vorhandenen Bilder.](./media/image26.png)

<span data-ttu-id="cd463-203">**Abbildung 4-26.**</span><span class="sxs-lookup"><span data-stu-id="cd463-203">**Figure 4-26**.</span></span> <span data-ttu-id="cd463-204">Anzeigen vorhandener Images, die mithilfe von Docker-images</span><span class="sxs-lookup"><span data-stu-id="cd463-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="cd463-205">Schritt 4: Definieren Sie Ihre Dienste im Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten</span><span class="sxs-lookup"><span data-stu-id="cd463-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="cd463-206">Mit der `docker-compose.yml` -Datei, Sie können definieren eine Gruppe von verwandten Diensten als zusammengesetzte Anwendung mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt beschrieben bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cd463-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="cd463-207">Erstellen Sie diese Datei in Ihrem Haupt- oder stammlösungsordner; Er sollte ähnlichen Inhalt wie in diesem angezeigten haben `docker-compose.yml` Datei:</span><span class="sxs-lookup"><span data-stu-id="cd463-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="cd463-208">In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und der Redis-Dienst (ein beliebten Cache-Dienst).</span><span class="sxs-lookup"><span data-stu-id="cd463-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="cd463-209">Jeder Dienst wird als Container bereitgestellt werden, daher wir ein konkretes Docker-Image für die einzelnen zu verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd463-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="cd463-210">Für diesen bestimmten Webdienst muss das Image die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cd463-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="cd463-211">Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="cd463-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="cd463-212">Weiterleiten von den verfügbar gemachten Port 80 im Container Port 81 auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="cd463-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="cd463-213">Bereitstellen Sie Verzeichnis des Projekts, auf dem Host /code innerhalb des Containers, und es ermöglicht, dass Sie den Code ändern, ohne das Abbild neu erstellen</span><span class="sxs-lookup"><span data-stu-id="cd463-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="cd463-214">Verknüpfen Sie den Webdienst mit Redis-Diensts</span><span class="sxs-lookup"><span data-stu-id="cd463-214">Link the web service to the redis service</span></span>

<span data-ttu-id="cd463-215">Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) mithilfe von Pull aus Docker Hub-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="cd463-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="cd463-216">[redis](https://redis.io/) ist ein beliebter Cache-System für serverseitige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="cd463-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="cd463-217">Schritt 5: Erstellen und Ausführen der Docker-app</span><span class="sxs-lookup"><span data-stu-id="cd463-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="cd463-218">Wenn Ihre Anwendung nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in Ihrem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cd463-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="cd463-219">Wenn Ihre app aus mehreren Diensten besteht, müssen Sie jedoch *erstellen Sie sie*ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="cd463-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="cd463-220">Sehen Sie die verschiedenen Optionen an.</span><span class="sxs-lookup"><span data-stu-id="cd463-220">Let's see the different options.</span></span>

<span data-ttu-id="cd463-221">***Option A: Führen Sie ein einzelner Container oder Dienst***</span><span class="sxs-lookup"><span data-stu-id="cd463-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="cd463-222">Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl aus, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cd463-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="cd463-223">Für diese bestimmte Bereitstellung müssen wir Umleiten von Anforderungen an Port 80 für den internen Port 5000 gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd463-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="cd463-224">Jetzt wird die Anwendung den externen Port 80 auf der Hostebene überwacht.</span><span class="sxs-lookup"><span data-stu-id="cd463-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="cd463-225">***Option B: Erstellen und Ausführen einer Anwendung von mehreren Containern***</span><span class="sxs-lookup"><span data-stu-id="cd463-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="cd463-226">In den meisten unternehmensumgebungen wird eine Docker-Anwendung aus mehreren Diensten bestehen.</span><span class="sxs-lookup"><span data-stu-id="cd463-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="cd463-227">Sie können in diesen Fällen Ausführen der `docker-compose up` Befehl (Abbildung 4-27), der die Docker-compose.yml-Datei verwendet wird, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="cd463-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="cd463-228">Mit diesem Befehl wird die zusammengesetzte Anwendung mit allen ihre zugehörigen Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cd463-228">Running this command deploys a composed application with all of its related containers.</span></span>

![Konsolenausgabe aus dem Docker-compose-Befehl.](./media/image27.png)

<span data-ttu-id="cd463-230">**Abbildung 4-27.**</span><span class="sxs-lookup"><span data-stu-id="cd463-230">**Figure 4-27**.</span></span> <span data-ttu-id="cd463-231">Ergebnisse der Ausführung des Befehls "Docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="cd463-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="cd463-232">Nach der Ausführung `docker-compose up`, Sie bereitstellen Ihrer Anwendung und die zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-28, in der VM-Darstellung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd463-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![VM, die Anwendungen mit mehreren Containern ausgeführt werden.](./media/image28.png)

<span data-ttu-id="cd463-234">**Abbildung 4-28.**</span><span class="sxs-lookup"><span data-stu-id="cd463-234">**Figure 4-28**.</span></span> <span data-ttu-id="cd463-235">VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="cd463-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="cd463-236">Schritt 6: Testen Sie Ihre Docker-Anwendung (lokal, in Ihre lokale CD-VM)</span><span class="sxs-lookup"><span data-stu-id="cd463-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="cd463-237">Dieser Schritt hängen davon ab, was den Status Ihrer app.</span><span class="sxs-lookup"><span data-stu-id="cd463-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="cd463-238">In einer einfachen .NET Core-Web-API "Hello World" als ein einzelner Container oder der Dienst bereitgestellt müssten Sie nur Zugriff auf den Dienst durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd463-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="cd463-239">Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="cd463-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="cd463-240">Öffnen Sie einen Browser, und navigieren Sie zu dieser Website, auf dem Docker-Host; Ihre app/des Diensts ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4-29 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd463-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Browseransicht der Antwort von "localhost" / API/Values.](./media/image29.png)

<span data-ttu-id="cd463-242">**Abbildung 4-29.**</span><span class="sxs-lookup"><span data-stu-id="cd463-242">**Figure 4-29**.</span></span> <span data-ttu-id="cd463-243">Testen der Docker-Anwendung, die lokal mithilfe von "localhost"</span><span class="sxs-lookup"><span data-stu-id="cd463-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="cd463-244">Beachten Sie, dass Port 80 verwendet wird, aber intern zu Port 5000 umgeleitet werden wird, da es sich handelt, wie er bereitgestellt wurde, mit `docker run`, wie weiter oben erläutert.</span><span class="sxs-lookup"><span data-stu-id="cd463-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="cd463-245">Sie können dies testen, über das Terminal mithilfe von CURL.</span><span class="sxs-lookup"><span data-stu-id="cd463-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="cd463-246">In einer Docker-Installation unter Windows ist die Standard-IP 10.0.75.1, an, wie in Abbildung 4-30 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cd463-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Konsolenausgabe an der Erledigung der http://10.0.75.1/API/values mit Curl](./media/image30.png)

<span data-ttu-id="cd463-248">**Abbildung 4-30.**</span><span class="sxs-lookup"><span data-stu-id="cd463-248">**Figure 4-30**.</span></span> <span data-ttu-id="cd463-249">Testen eine Docker-Anwendung lokal mithilfe von CURL</span><span class="sxs-lookup"><span data-stu-id="cd463-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="cd463-250">**Debuggen eines Containers ausführen unter Docker**</span><span class="sxs-lookup"><span data-stu-id="cd463-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="cd463-251">Visual Studio Code unterstützt Debuggen Docker an, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd463-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="cd463-252">Sie können auch .NET Core oder .NET Framework-Containern in Docker Debuggen bei Verwendung von Visual Studio für Windows oder Mac zu erstellen, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd463-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!INFORMATION]
>
> <span data-ttu-id="cd463-254">Wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span><span class="sxs-lookup"><span data-stu-id="cd463-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cd463-255">[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="cd463-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
