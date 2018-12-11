---
title: Innere Schleife Entwicklungsworkflow für Docker-apps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: f7acb60e6136c0250d18bdce23ac21fb6aa80b34
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148860"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="b7a1e-103">Innere Schleife Entwicklungsworkflow für Docker-apps</span><span class="sxs-lookup"><span data-stu-id="b7a1e-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="b7a1e-104">Vor dem Auslösen des äußeren Schleife Workflows umfasst den gesamten DevOps-Zyklus, es beginnt alles auf dem Computer jedes Entwicklers, die app selbst zu codieren, verwenden ihren bevorzugten Sprachen oder Plattformen und diese lokal testen (Abbildung 4-14).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="b7a1e-105">In jedem Fall, müssen aber einen sehr wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="b7a1e-106">In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern, aber lokal.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="b7a1e-107">Abbildung 4-14: Innere Schleife Development-Kontext</span><span class="sxs-lookup"><span data-stu-id="b7a1e-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="b7a1e-108">Der Container oder eine Instanz eines Docker-Images werden diese Komponenten enthalten:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="b7a1e-109">Eine Betriebssystemauswahl (z.B. eine Linux-Distribution oder Windows)</span><span class="sxs-lookup"><span data-stu-id="b7a1e-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="b7a1e-110">Dateien, die vom Entwickler (z.B. app-Binärdateien) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="b7a1e-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="b7a1e-111">Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="b7a1e-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="b7a1e-112">Anweisungen für welche Aspekte Sie verarbeitet die Ausführung von Docker</span><span class="sxs-lookup"><span data-stu-id="b7a1e-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="b7a1e-113">Sie können die innere Schleife Entwicklungsworkflow einrichten, die Docker wie der Prozess (im nächsten Abschnitt beschrieben) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="b7a1e-114">Berücksichtigen Sie, dass die ersten Schritte zum Einrichten der Umgebung ist nicht eingeschlossen werden, da Sie nur einmal durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="b7a1e-115">Erstellen eine einzelne app in Docker-Container mit Visual Studio Code und Docker-CLI</span><span class="sxs-lookup"><span data-stu-id="b7a1e-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="b7a1e-116">Apps bestehen aus Ihren eigenen Diensten sowie zusätzlichen Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="b7a1e-117">Abbildung 4-15 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer Docker-app, gefolgt von ausführliche Beschreibungen der einzelnen Schritte ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="b7a1e-118">Abbildung 4-15: Allgemeiner Workflow für die Lebenszyklus von Docker-containeranwendungen mit Docker CLI</span><span class="sxs-lookup"><span data-stu-id="b7a1e-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="b7a1e-119">Schritt 1: Beginnen mit dem Programmieren in Visual Studio Code, und erstellen Sie Ihrer ersten app/des Diensts</span><span class="sxs-lookup"><span data-stu-id="b7a1e-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="b7a1e-120">Die Möglichkeit, die Sie bei der Entwicklung Ihrer Anwendung ist ganz ähnlich wie Sie es ohne Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="b7a1e-121">Der Unterschied ist, die beim Entwickeln, bereitstellen und Testen Ihre Anwendung oder Dienste, die in Docker-Containern platziert, die in Ihrer lokalen Umgebung (z.B. eine Linux-VM oder Windows) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="b7a1e-122">**Das Einrichten Ihrer lokalen Umgebung**</span><span class="sxs-lookup"><span data-stu-id="b7a1e-122">**Setting up your local environment**</span></span>

<span data-ttu-id="b7a1e-123">Mit den neuesten Versionen von Docker für Mac und Windows es ist einfacher als je zuvor zu Docker-Anwendungen entwickeln, und das Setup ist einfach.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="b7a1e-124">**Weitere Informationen** Anweisungen zum Einrichten von Docker für Windows finden Sie unter [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="b7a1e-125">Anweisungen zum Einrichten von Docker für Mac finden Sie unter <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="b7a1e-126">Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-CLI tatsächlich entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="b7a1e-127">Microsoft bietet Visual Studio Code, einem einfachen Code-Editor, die unter Mac, Windows und Linux unterstützt, und bietet IntelliSense mit [Unterstützung für viele Sprachen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python und die meisten Moderne Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [-Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="b7a1e-128">Dieser Editor ist ideal für Mac und Linux-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="b7a1e-129">In Windows können Sie auch die vollständige Visual Studio-Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="b7a1e-130">**Weitere Informationen** finden Sie Anweisungen zum Installieren von Visual Studio für Windows, Mac oder Linux <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>

<span data-ttu-id="b7a1e-131">Sie arbeiten mit Docker-CLI und Schreiben Sie Ihren Code ein Code-Editor verwenden können, aber wenn Sie Visual Studio Code verwenden, macht es einfach, Autor dockerfile-Datei und Docker-compose.yml-Dateien in Ihrem Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="b7a1e-132">Darüber hinaus können Sie Aufgaben für Visual Studio Code aus der IDE ausführen, die Skripts aufgefordert, die ausführliche Vorgänge, die mit Docker-CLI unter ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="b7a1e-133">Visual Studio Code wird von einer Erweiterung bereitgestellt, die Sie installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="b7a1e-134">Drücken Sie STRG + UMSCHALT + P, dazu geben **Ext installieren**, und führen Sie dann auf die Erweiterungen: Installieren Sie die Erweiterung-Befehl, um die Liste der Marketplace-Erweiterungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="b7a1e-135">Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie dann die Dockerfile und Docker Compose-Datei (Yml) Erweiterung "Support" aus, wie in Abbildung 4-16 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="b7a1e-136">Abbildung 4 – 16: Installieren der Docker-Erweiterungs in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b7a1e-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="b7a1e-137">Schritt 2: Erstellen Sie eine dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (einfaches Betriebssystem oder entwicklungsumgebungen wie .NET Core, Node.js und Ruby)</span><span class="sxs-lookup"><span data-stu-id="b7a1e-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="b7a1e-138">Sie benötigen eine dockerfile-Datei pro benutzerdefiniertes Image erstellt werden und Container bereitgestellt werden, daher, wenn Ihre app aus einen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="b7a1e-139">Aber wenn Ihre app aus mehreren Diensten (wie in einer Microservices-Architektur) besteht, benötigen Sie eine dockerfile-Datei pro Dienst.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="b7a1e-140">Die dockerfile-Datei befindet sich in der Regel im Stammordner Ihrer app oder Ihres Diensts und enthält die erforderlichen Befehle aus, damit Docker weiß, wie einrichten und Ausführen dieser app oder Ihres Diensts.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="b7a1e-141">Sie können die dockerfile-Datei zu erstellen und zu Ihrem Projekt zusammen mit Ihrem Code hinzufügen (.NET Core, node.js usw.), oder, wenn Sie in der Umgebung vertraut sind, sehen Sie sich den folgenden Tipp.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="b7a1e-142">Sie können ein Befehlszeilentool namens [yo Docker](https://github.com/Microsoft/generator-docker), der erstellt das Gerüst für die Dateien aus Ihrem Projekt in der Sprache Ihrer Wahl, und fügt die erforderlichen Docker-Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="b7a1e-143">Im Grunde genommen, um Entwicklern die ersten Schritte zu unterstützen, erstellt der entsprechenden dockerfile-Datei "Docker-Compose.yml", und die anderen zugehörigen Skripts zum Erstellen und Ausführen der Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="b7a1e-144">Diese Yeoman-Generators werden mit ein paar Fragen, Fragen Ihren ausgewählten Entwicklung Sprache und das Ziel der containerhost aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![yo Docker](./media/image21.png)

<span data-ttu-id="b7a1e-146">Beispielsweise zeigt die beiden Screenshots aus den Terminals Abbildung 4-17, in Windows und auf einem Mac in beiden Fällen "yo" denen Docker ausgeführt wird, die den Code Beispielprojekte (derzeit .NET Core, Golang und Node.js als unterstützten Sprachen) bereits so konfiguriert, dass die arbeiten generiert wird obere von Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="b7a1e-147">Abbildung 4-17: yo Docker Befehlstool in Windows (links) und auf einem Mac</span><span class="sxs-lookup"><span data-stu-id="b7a1e-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="b7a1e-148">Abbildung 4-18 zeigt ein Beispiel mit yo Docker nachdem man von einem vorhandenen .NET Core-Projekt einrichten, um das Gerüst erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="b7a1e-149">Abbildung 4-18: yo Docker mit einem vorhandenen .NET Core vorgesehenes Projekt</span><span class="sxs-lookup"><span data-stu-id="b7a1e-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="b7a1e-150">Geben Sie aus der dockerfile-Datei welche Docker-Basisimage Sie verwenden möchten (z. B. mit "von microsoft/dotnet:1.0.0-core") an.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="b7a1e-151">In der Regel erstellen Sie Ihr benutzerdefinierte Image auf einem Basisimage, das Sie über alle offiziellen-Repository in abrufen können die [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. eine [Images für .NET Core](https://hub.docker.com/r/microsoft/dotnet/) oder einem [für Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="b7a1e-152">***Option A: Verwenden Sie ein vorhandenes offizielles dockerimage***</span><span class="sxs-lookup"><span data-stu-id="b7a1e-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="b7a1e-153">Mit einem offiziellen-Repository eines Stapels Sprache mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklung, Tests und Produktion) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="b7a1e-154">Es folgt eine DockerFile-Beispieldatei für eine .NET Core-Container:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-154">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="b7a1e-155">In diesem Fall ist es die Version 1.0.1 des offiziellen ASP.NET Core-Docker-Image für Linux mit dem Namen microsoft/aspnetcore:1.0.1 verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="b7a1e-156">Weitere Informationen finden Sie in der [ASP.NET Core-Docker-Image-Seite](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core-Docker-Image-Seite](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="b7a1e-157">Außerdem können verwenden Sie einen anderen vergleichbares Bild wie Knoten: 4-Onbuild für Node.js oder vielen anderen vorkonfigurierten Images für Entwicklungssprachen erhältlich sind [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="b7a1e-158">In der dockerfile-Datei müssen Sie auch angeben, dass Docker zum TCP-Port zu lauschen, die Sie zur Laufzeit (z. B. Port 80) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="b7a1e-159">Es gibt andere Zeilen in der Konfiguration, die Sie in der dockerfile-Datei je nach Sprachen/Frameworks, die Sie verwenden, hinzufügen können, damit Docker weiß, wie Sie die app ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="b7a1e-160">Beispielsweise benötigen Sie die ENTRYPOINT-Zeile mit \["Dotnet", "MyCustomMicroservice.dll"\] eine .NET Core-app ausgeführt wird, obwohl Sie mehrere Varianten je nach den Ansatz zum Erstellen und Ausführen Ihres Diensts haben können.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="b7a1e-161">Wenn Sie verwenden das SDK und die Dotnet-CLI zum Erstellen und führen Sie die app .NET, wäre es etwas anders.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="b7a1e-162">Das Fazit ist, dass die ENTRYPOINT-Zeile sowie weitere Zeilen je nach Sprache/Plattform unterscheiden, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="b7a1e-163">**Weitere Informationen** Informationen über das Erstellen von Docker-Images für .NET Core-Anwendungen finden Sie unter <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-163">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="b7a1e-164">Wechseln Sie zu, um weitere Informationen zum Erstellen Ihrer eigenen Images [ https://docs.docker.com/engine/\ Tutorials/Dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="b7a1e-165">**Für mehrere Plattformen Image-Repositorys**</span><span class="sxs-lookup"><span data-stu-id="b7a1e-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="b7a1e-166">Wie Windows-Containern immer häufiger verwendet, kann ein einzelnes Repository Plattformvarianten, z. B. ein Linux- und Windows-Image enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="b7a1e-167">Dies ist ein neues Feature in Docker, das für die softwareaktualisierung ein einziges Repository für die verwenden mehrere Plattformen wie z. B. ermöglicht [Microsoft/Aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) -Repository, das an DockerHub-Registrierung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="b7a1e-168">Wie die Funktion aktiv ist, wird dieses Image von einem Windows-Host ziehen die Windows-Variante, rufen Sie während der gleiche ImageName von einem Linux-Host ziehen die Linux-Variante abruft.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="b7a1e-169">***Option B: Ihr Basisimage von Grund auf neu erstellen***</span><span class="sxs-lookup"><span data-stu-id="b7a1e-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="b7a1e-170">Sie können Ihre eigenen Docker-Basisimage von Grund auf neu erstellen, wie dies unter [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="b7a1e-171">Dies ist ein Szenario, das ist wahrscheinlich nicht für Sie am besten, wenn Sie nur mit Docker beginnen, aber wenn Sie die bestimmten Bits Ihres eigenen Basisimages festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="b7a1e-172">Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihrem Dienst darin einbetten</span><span class="sxs-lookup"><span data-stu-id="b7a1e-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="b7a1e-173">Für jeden benutzerdefinierten Dienst, die Ihre app umfasst, müssen Sie ein zugehöriges Image erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="b7a1e-174">Wenn Ihre app aus einem einzelnen Dienst oder Web-app besteht, benötigen Sie ein einziges Bild.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="b7a1e-175">Wenn die "outer-Loop-DevOps-Workflow" berücksichtigen, die Bilder erstellt durch einen automatisierten Buildprozess zu, wenn Sie Ihren Quellcode in einem Git-Repository (Continuous Integration) übertragen, sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="b7a1e-176">Aber bevor wir auf die äußere Schleife Route in Betracht ziehen, müssen wir sicherstellen, dass die Docker-Anwendung ordnungsgemäß funktioniert, damit sie Code nicht die Warteschlange übertragen, die auf das Quellcodeverwaltungssystem (Git, usw.) möglicherweise nicht ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="b7a1e-177">Jeder Entwickler muss daher zuerst führen Sie den gesamten Entwicklungsworkflow Prozess zum Testen lokal und weiterentwickeln, bis eine vollständige Funktion mithilfe von Push übertragen, oder ändern Sie in das Quellcodeverwaltungssystem werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="b7a1e-178">Um ein Image in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie die Docker-Erstellungsbefehl aus, wie in Abbildung 4-19 (Sie können auch ausführen Docker-compose up--build für Anwendungen besteht aus mehreren Containern/Diensten).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="b7a1e-179">Abbildung 4-19: Docker-Build ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b7a1e-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="b7a1e-180">Anstatt direkt mit Docker erstellen Sie optional aus dem Ordner des Projekts, Sie können zuerst einen bereitstellbaren Ordner mit den .NET-Bibliotheken erforderlich sind, mit der Ausführung Dotnet-publish-Befehl aus, und führen Sie Docker Build generieren.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="b7a1e-181">In diesem Beispiel ist dies ein Docker-Image erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: First (: zuerst wird ein Tag, wie eine bestimmte Version).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="b7a1e-182">Sie können diesen Schritt für jedes benutzerdefinierte Image nutzen, die Sie für Ihre zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="b7a1e-183">Die vorhandenen Images finden in Ihrem lokalen Repository (Entwicklungscomputer) Sie unter Verwendung von Docker Images-Befehl, wie in Abbildung 4-20 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="b7a1e-184">Abbildung 4-20: Anzeigen vorhandener Images, die mithilfe von Docker-images</span><span class="sxs-lookup"><span data-stu-id="b7a1e-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="b7a1e-185">Schritt 4: (Optional) Definieren Sie Ihre Dienste im Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten</span><span class="sxs-lookup"><span data-stu-id="b7a1e-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="b7a1e-186">Mit der Docker-compose.yml-Datei können Sie eine Reihe von verknüpften Diensten als zusammengesetzte Anwendung bereitgestellt werden, mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt erläutert definieren.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="b7a1e-187">Sie müssen diese Datei in Ihrem Haupt- oder stammlösungsordner erstellen; Sie müssen einen vergleichbaren Artikel in der folgenden Docker-compose.yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
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

<span data-ttu-id="b7a1e-188">In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und der Redis-Dienst (ein beliebten Cache-Dienst).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="b7a1e-189">Jeder Dienst wird als Container bereitgestellt werden, daher wir ein konkretes Docker-Image für die einzelnen zu verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="b7a1e-190">Für diesen bestimmten Webdienst muss das Image die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="b7a1e-191">Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="b7a1e-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="b7a1e-192">Weiterleiten von den verfügbar gemachten Port 80 im Container Port 81 auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="b7a1e-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="b7a1e-193">Bereitstellen Sie Verzeichnis des Projekts, auf dem Host /code innerhalb des Containers, und es ermöglicht, dass Sie den Code ändern, ohne das Abbild neu erstellen</span><span class="sxs-lookup"><span data-stu-id="b7a1e-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="b7a1e-194">Verknüpfen Sie den Webdienst mit Redis-Diensts</span><span class="sxs-lookup"><span data-stu-id="b7a1e-194">Link the web service to the redis service</span></span>

<span data-ttu-id="b7a1e-195">Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) mithilfe von Pull aus Docker Hub-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="b7a1e-196">[redis](https://redis.io/) ist ein sehr beliebtes Cache-System für serverseitige Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="b7a1e-197">Schritt 5: Erstellen und Ausführen der Docker-app</span><span class="sxs-lookup"><span data-stu-id="b7a1e-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="b7a1e-198">Wenn Ihre Anwendung nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in Ihrem Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="b7a1e-199">Wenn Ihre app aus mehreren Diensten besteht, müssen Sie jedoch *erstellen Sie sie*ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="b7a1e-200">Sehen Sie die verschiedenen Optionen an.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-200">Let's see the different options.</span></span>

<span data-ttu-id="b7a1e-201">***Option A: Führen Sie ein einzelner Container oder Dienst***</span><span class="sxs-lookup"><span data-stu-id="b7a1e-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="b7a1e-202">Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl aus, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="b7a1e-203">Beachten Sie, dass für diese bestimmte Bereitstellung, wir an Port 80 für den internen Port 5000 gesendete Anforderungen umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="b7a1e-204">Nun wird die Anwendung den externen Port 80 auf der Hostebene überwacht.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="b7a1e-205">***Option B: Erstellen und Ausführen einer Anwendung von mehreren Containern***</span><span class="sxs-lookup"><span data-stu-id="b7a1e-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="b7a1e-206">In den meisten unternehmensumgebungen wird eine Docker-Anwendung aus mehreren Diensten bestehen.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="b7a1e-207">In diesen Fällen können Sie den Befehl ausführen Docker-compose-einrichten (Abbildung 4-21), die verwenden der Docker-compose.yml-Datei, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="b7a1e-208">Mit diesem Befehl wird die zusammengesetzte Anwendung mit allen ihre zugehörigen Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="b7a1e-209">Abbildung 4-21: Ergebnisse der Ausführung des Befehls "Docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="b7a1e-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="b7a1e-210">Nach dem Ausführen von Docker-compose-einrichten, Sie bereitstellen Ihrer Anwendung und die zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-22, in der VM-Darstellung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="b7a1e-211">Abbildung 4-22: VM mit bereitgestellten Docker-Containern</span><span class="sxs-lookup"><span data-stu-id="b7a1e-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="b7a1e-212">Hinweis Docker-compose-einrichten und "Docker run" möglicherweise für Ihre Container in Ihrer Entwicklungsumgebung testen ausreichend, aber Sie möglicherweise verwenden sie überhaupt nicht, wenn Sie erwarten, arbeiten mit Docker-Cluster und orchestratoren wie Docker Swarm, Mesosphere DC/OS oder Kubernetes Damit Sie zentral hochskalieren können.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="b7a1e-213">Wenn Sie einen Cluster wie verwenden [Docker Swarm-Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker für Windows und Mac ab Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen, z. B. Docker-Dienst für einzelne Dienste erstellen, oder wenn Sie sich befinden Bereitstellen einer app, bestehend aus mehreren Containern mit Docker compose-Paket und Docker bereitstellen MyBundleFile, als Stapel, das Bereitstellen von der app aus, wie in diesem Artikel erläutert [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="b7a1e-214">Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) verwenden Sie unterschiedliche Bereitstellungsbefehle und Skripts, als auch.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="b7a1e-215">Schritt 6: Testen Sie Ihre Docker-Anwendung (lokal, in Ihre lokale CD-VM)</span><span class="sxs-lookup"><span data-stu-id="b7a1e-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="b7a1e-216">Dieser Schritt hängen davon ab, was den Status Ihrer app.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="b7a1e-217">In einer einfachen .NET Core Web-API "Hello World" als ein einzelner Container oder der Dienst bereitgestellt müssten Sie nur Zugriff auf den Dienst durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="b7a1e-218">Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl:</span><span class="sxs-lookup"><span data-stu-id="b7a1e-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="b7a1e-219">Docker-Machine-Ip *Container Name-Ihrer-*</span><span class="sxs-lookup"><span data-stu-id="b7a1e-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="b7a1e-220">Öffnen Sie einen Browser, und navigieren Sie zu dieser Website, auf dem Docker-Host; Ihre app/des Diensts ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4-23 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="b7a1e-221">Abbildung 4-23: Testen der Docker-Anwendung, die lokal mithilfe von "localhost"</span><span class="sxs-lookup"><span data-stu-id="b7a1e-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="b7a1e-222">Beachten Sie, dass Port 80 verwendet wird, aber er intern wird, an Port 5000 umgeleitet wurde, denn das ist wie mit "Docker run", bereitgestellt wurde wie weiter oben erläutert.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="b7a1e-223">Sie können dies testen, über das Terminal mithilfe von CURL.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="b7a1e-224">In einer Docker-Installation unter Windows ist die Standard-IP 10.0.75.1, an, wie in Abbildung 4-24 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="b7a1e-225">Abbildung 4-24: Testen eine Docker-Anwendung lokal mithilfe von CURL</span><span class="sxs-lookup"><span data-stu-id="b7a1e-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="b7a1e-226">**Debuggen eines Containers ausführen unter Docker**</span><span class="sxs-lookup"><span data-stu-id="b7a1e-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="b7a1e-227">Visual Studio Code unterstützt Debuggen Docker an, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="b7a1e-228">Sie können auch .NET Core in Docker-Container Debuggen bei Verwendung von Visual Studio, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7a1e-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="b7a1e-229">**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und [ https://blogs.msdn.microsoft.com/\ Benutzer\_Ed/2016/02/27 / Visual-Studio-Code-New-Features-13-Big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-Mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="b7a1e-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b7a1e-230">[Zurück](docker-apps-development-environment.md)
>[Weiter](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="b7a1e-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>