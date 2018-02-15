---
title: "Innere Schleife Entwicklungsworkflow für Docker-apps"
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3605a6cd53db695de3af015a777e3c1a0e92af58
ms.sourcegitcommit: 672c9cd122c13c9813f57f022c86ebdf6dd69b4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="fd990-104">Innere Schleife Entwicklungsworkflow für Docker-apps</span><span class="sxs-lookup"><span data-stu-id="fd990-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="fd990-105">Vor dem Auslösen des äußeren Schleife Workflows umfasst die gesamte DevOps durchlaufen, Ausgangspunkt für alle weiteren auf jeder Entwickler-Computer, codieren die app selbst, ihren bevorzugten Sprachen oder Plattformen verwenden und lokal testen (Abbildung 4-14).</span><span class="sxs-lookup"><span data-stu-id="fd990-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="fd990-106">In jedem Fall, müssen aber einen sehr wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="fd990-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="fd990-107">In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern lokal.</span><span class="sxs-lookup"><span data-stu-id="fd990-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="fd990-108">Abbildung 4 – 14: innere Schleife Entwicklung Kontext</span><span class="sxs-lookup"><span data-stu-id="fd990-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="fd990-109">Der Container oder eine Instanz des Docker-Images werden diese Komponenten enthalten:</span><span class="sxs-lookup"><span data-stu-id="fd990-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="fd990-110">Eine Auswahl des Betriebssystems (z. B. eine Linux-Distribution oder Windows)</span><span class="sxs-lookup"><span data-stu-id="fd990-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="fd990-111">Dateien vom Entwickler (z. B. app Binärdateien) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="fd990-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="fd990-112">Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="fd990-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="fd990-113">Anweisungen für welche Prozesse für die Ausführung von Docker</span><span class="sxs-lookup"><span data-stu-id="fd990-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="fd990-114">Sie können die innere Schleife Entwicklungsworkflow einrichten, auf dem Docker wie der Prozess (im nächsten Abschnitt beschrieben) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd990-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="fd990-115">Berücksichtigen Sie, dass die ersten Schritte zum Einrichten der Umgebung ist nicht enthalten, da die, die nur einmal durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="fd990-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="fd990-116">Erstellen eine einzelne app in einem Docker-Container mithilfe von Visual Studio Code und Docker-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd990-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="fd990-117">Apps bestehen aus Ihrer eigenen Services plus zusätzliche Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="fd990-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="fd990-118">Abbildung 4-15 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer app Docker ein, gefolgt von detaillierten Beschreibungen der einzelnen Schritte ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="fd990-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="fd990-119">Abbildung 4 – 15: Allgemeine Workflow für den Lebenszyklus Anwendungsmöglichkeiten Docker-Containern mit Docker-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd990-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="fd990-120">Schritt 1: Beginnen Sie in Visual Studio-Code codieren, und erstellen Sie Ihre erste Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="fd990-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="fd990-121">Die Möglichkeit, die Entwicklung der Anwendung ist ziemlich ähnlich wie bei, die Sie dies, ohne Docker tun.</span><span class="sxs-lookup"><span data-stu-id="fd990-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="fd990-122">Der Unterschied besteht darin, dass beim Entwickeln, sind Sie bereitstellen und Testen Ihrer Anwendung oder ausgeführte dateiserverdienste Docker-Containern, die in Ihrer lokalen Umgebung (z. B. ein Linux-VM oder -Windows) platziert.</span><span class="sxs-lookup"><span data-stu-id="fd990-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="fd990-123">**Das Einrichten der lokalen Umgebung**</span><span class="sxs-lookup"><span data-stu-id="fd990-123">**Setting up your local environment**</span></span>

<span data-ttu-id="fd990-124">Mit den neuesten Versionen von Docker für Macintosh und Windows es ist einfacher als je, Docker-Anwendungen entwickeln, und das Setup ist einfach.</span><span class="sxs-lookup"><span data-stu-id="fd990-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="fd990-125">**Weitere Informationen** finden Sie eine Anleitung zum Einrichten von Docker für Windows [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="fd990-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="fd990-126">Anweisungen zum Einrichten von Docker für Mac, wechseln Sie zu <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="fd990-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="fd990-127">Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-Befehlszeilenschnittstelle tatsächlich entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="fd990-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="fd990-128">Microsoft bietet Visual Studio-Code, der eine einfache Code-Editor, die auf Windows, Mac und Linux unterstützt wird ist, und bietet IntelliSense mit [für viele Sprachen unterstützen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET Go, Java, Ruby, Python, und die meisten modernen Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="fd990-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="fd990-129">Dieser Editor ist hervorragend für Mac und Linux-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="fd990-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="fd990-130">In Windows können Sie auch die vollständige Visual Studio-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fd990-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="fd990-131">**Weitere Informationen** finden Sie Anweisungen zum Installieren von Visual Studio für Windows, Mac und Linux [Http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span><span class="sxs-lookup"><span data-stu-id="fd990-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="fd990-132">Sie können mit Docker-Befehlszeilenschnittstelle arbeiten und Ihren Code mit einem beliebigen Codeeditor schreiben, aber bei Verwendung von Visual Studio Code macht es einfach, zum Erstellen von dockerfile-Datei und Docker-compose.yml-Dateien in Ihrem Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="fd990-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="fd990-133">Darüber hinaus können Sie Aufgaben für Visual Studio-Code aus der IDE ausführen, die Skripts aufgefordert, die ausführlichen mit Docker-Befehlszeilenschnittstelle, darunter Vorgänge ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="fd990-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="fd990-134">Visual Studio-Code ist durch eine Erweiterung bereitgestellt, die Sie installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fd990-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="fd990-135">Drücken Sie STRG + UMSCHALT + P dazu geben **Ext installieren**, und führen Sie die Erweiterungen: Erweiterung installieren-Befehl, um die Liste der Marketplace-Erweiterung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fd990-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="fd990-136">Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie die dockerfile-Datei und Docker verfassen Datei (Yml) Support-Erweiterung, wie in Abbildung 4-16 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fd990-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="fd990-137">Abbildung 4 – 16: die Docker-Erweiterung in Visual Studio Code installieren</span><span class="sxs-lookup"><span data-stu-id="fd990-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="fd990-138">Schritt 2: Erstellen einer dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (plain OS oder Dev Umgebungen wie .NET Core, Node.js und Ruby)</span><span class="sxs-lookup"><span data-stu-id="fd990-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="fd990-139">Sie benötigen eine dockerfile-Datei pro benutzerdefiniertes Bild erstellt werden sollen und Container bereitgestellt werden, daher, wenn Ihre app aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="fd990-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="fd990-140">Aber wenn Ihre app aus mehreren Diensten (wie eine Microservices-Architektur) besteht, benötigen Sie eine dockerfile-Datei pro Dienst.</span><span class="sxs-lookup"><span data-stu-id="fd990-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="fd990-141">Die dockerfile-Datei befindet sich im Stammordner der Ihrer app oder Ihrem Dienst in der Regel und die erforderlichen Befehle enthält, damit diese Docker weiß, wie einrichten und Ausführen dieser app oder einen Dienst.</span><span class="sxs-lookup"><span data-stu-id="fd990-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="fd990-142">Sie können Ihr dockerfile-Datei erstellen und dem Projekt zusammen mit Ihrem Code hinzufügen (.NET Core, node.js usw.), oder wenn Sie mit der Umgebung vertraut sind, sehen Sie sich die folgenden Tipps.</span><span class="sxs-lookup"><span data-stu-id="fd990-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="fd990-143">Können Sie ein Befehlszeilentool namens [Handelsversion Docker](https://github.com/Microsoft/generator-docker), dem Gerüste Dateien aus Ihrem Projekt in der Sprache, die Sie auswählen, und fügt die erforderlichen Dateien der Docker-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="fd990-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="fd990-144">Im Grunde um Entwicklern die ersten Schritte zu unterstützen, erstellt er die entsprechenden dockerfile-Datei Docker-compose.yml und anderen zugehörigen Skripts zum Erstellen und Ausführen von Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="fd990-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="fd990-145">Dieses Yeoman-Generators werden einige Fragen, Fragen die ausgewählte Sprache und Ziel Container Entwicklungshost aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="fd990-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![Handelsversion Docker](./media/image21.png)

<span data-ttu-id="fd990-147">Beispielsweise zeigt Abbildung 4 – 17 zwei Screenshots aus der Terminals in Windows und auf einem Mac, in beiden Fällen zu ausgeführt Handelsversion Docker, die den Code Beispielprojekte (derzeit .NET Core, Golang und Node.js als unterstützten Sprachen) bereits so konfiguriert, dass arbeiten generieren wird Anfang Docker.</span><span class="sxs-lookup"><span data-stu-id="fd990-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="fd990-148">Abbildung 4 – 17: Handelsversion Docker Befehl Tool in Windows (links) und auf einem Mac</span><span class="sxs-lookup"><span data-stu-id="fd990-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="fd990-149">Abbildung 4 – 18 zeigt ein Beispiel für verwendet werden, können Docker Nachdem Sie ein vorhandenes Projekt für .NET Core zu Gerüstbau werden verfügen.</span><span class="sxs-lookup"><span data-stu-id="fd990-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="fd990-150">Abbildung 4 – 18: Handelsversion Docker mit einer vorhandenen .NET Core Projekt vorhanden</span><span class="sxs-lookup"><span data-stu-id="fd990-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="fd990-151">Geben Sie aus der dockerfile-Datei welche Basis Docker-Image, das Sie verwenden (z. B. mit "von microsoft/dotnet:1.0.0-core") an.</span><span class="sxs-lookup"><span data-stu-id="fd990-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="fd990-152">In der Regel erstellen Sie Ihr benutzerdefinierte Bild eine Basis-Image, die Sie aus jeder offizielle Repository auf der [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. ein [Bild für .NET Core](https://hub.docker.com/r/microsoft/dotnet/) oder einem [für Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="fd990-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="fd990-153">***Option A: Verwenden eines vorhandenen offizielle Docker-Images***</span><span class="sxs-lookup"><span data-stu-id="fd990-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="fd990-154">Mit einem offiziellen Repository Sprache Stapel mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklungs-, Test- und Produktionszwecke) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fd990-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="fd990-155">Es folgt ein Beispiel für dockerfile-Datei für einen .NET Core-Container:</span><span class="sxs-lookup"><span data-stu-id="fd990-155">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="fd990-156">In diesem Fall wird die Version 1.0.1 des offiziellen ASP.NET Core Docker-Images für Linux mit dem Namen microsoft/aspnetcore:1.0.1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd990-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="fd990-157">Weitere Informationen finden Sie in der [ASP.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="fd990-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="fd990-158">Auch konnten verwenden Sie ein anderes vergleichbare Bild wie Knoten: 4-Onbuild für Node.js oder viele andere vorkonfigurierter Images für die Entwicklungssprachen, von denen in verfügbaren [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="fd990-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="fd990-159">In der dockerfile-Datei müssen Sie auch weisen Docker an, den TCP-Port zu überwachen, die zur Laufzeit (z. B. Port 80) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd990-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="fd990-160">Es gibt andere Zeilen Konfiguration, die Sie in die dockerfile-Datei je nach Sprache/Framework, die Sie verwenden, die hinzufügen können, damit Docker weiß, wie die app ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd990-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="fd990-161">Sie benötigen beispielsweise die ENTRYPOINT-Zeile mit \["Dotnet", "MyCustomMicroservice.dll"\] eine app .NET Core ausgeführt wird, obwohl Sie mehrere Varianten abhängig von der Ansatz zum Erstellen und führen Sie den Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fd990-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="fd990-162">Wenn Sie verwenden das SDK und Dotnet CLI erstellen und Ausführen der app .NET, wäre es etwas anders.</span><span class="sxs-lookup"><span data-stu-id="fd990-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="fd990-163">Entscheidend ist, dass die ENTRYPOINT-Zeile plus zusätzliche Zeilen je nach der Sprachplattform unterschiedlich sind, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="fd990-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="fd990-164">**Weitere Informationen** finden Sie Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen, <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="fd990-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/articles/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="fd990-165">Wechseln Sie zu, um weitere Informationen zur Erstellung Ihrer eigenen Abbilder [https://docs.docker.com/engine/ \Lernprogramme/Dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="fd990-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="fd990-166">**Multiplattform-Image-Repositorys**</span><span class="sxs-lookup"><span data-stu-id="fd990-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="fd990-167">Windows-Containern häufiger verwendet, kann ein einzelnes Repository Plattform Varianten, z. B. ein Linux- und Windows-Image enthält.</span><span class="sxs-lookup"><span data-stu-id="fd990-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="fd990-168">Dies ist ein neues Feature eingehen, die Anbieter auf ein einzelnes Repository verwenden, z. B. mehrere Plattformen abdecken kann Docker [Microsoft/Aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Repository, die am DockerHub Registrierung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fd990-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="fd990-169">Sobald die Funktion aktiv ist, wird dieses Bild für das Ausführen von Pull aus einem Windows-Host die Windows-Variante einziehen während der gleiche Name für das Ausführen von Pull aus einem Linux-Host die Linux-Variante pull.</span><span class="sxs-lookup"><span data-stu-id="fd990-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="fd990-170">***Option B: Erstellen des Basis-Image von Grund auf neu***</span><span class="sxs-lookup"><span data-stu-id="fd990-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="fd990-171">Sie können eigene Docker-Basis-Image von Grund auf neu erstellen, wie in diesem erläutert [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="fd990-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="fd990-172">Dies ist ein Szenario, das ist wahrscheinlich nicht für Sie am besten geeignet, wenn Sie gerade mit Docker gestartet werden, aber wenn Sie die bestimmte Bits des eigene Basisimage festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="fd990-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="fd990-173">Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihr Dienst darin einbetten</span><span class="sxs-lookup"><span data-stu-id="fd990-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="fd990-174">Für jeden benutzerdefinierten Dienst, der Ihrer app ausmacht, müssen Sie eine verwandte Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd990-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="fd990-175">Wenn Ihre app von einem Einzelgerät oder Web-app vorgenommen wird, benötigen Sie nur ein einziges Bild.</span><span class="sxs-lookup"><span data-stu-id="fd990-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="fd990-176">Der Workflow"DevOps äußere Schleife" modellbasiert, die Bilder erstellt werden durch einen automatisierten Erstellungsprozess Wenn Quellcode in einem Git-Repository (Continuous Integration) übertragen, sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem Quellcode.</span><span class="sxs-lookup"><span data-stu-id="fd990-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="fd990-177">Aber bevor wir diese Route für die äußere Schleife hörmal betrachten, müssen wir sicherstellen, dass die Docker-Anwendung, damit sie Code mithilfe von Push übertragen nicht, die unter Umständen nicht ordnungsgemäß auf dem Quellcodeverwaltungssystem (Git, usw.) funktionieren tatsächlich ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="fd990-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="fd990-178">Daher muss jeder Entwickler zunächst müssen den gesamten Prozess der inneren Schleife um lokal testen und entwickeln, bis eine vollständige Funktion push oder ändern Sie in das Quellcodeverwaltungssystem werden soll.</span><span class="sxs-lookup"><span data-stu-id="fd990-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="fd990-179">Um ein Bild in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie den Befehl "Docker Build", wie in Abbildung 4-19 gezeigt (Sie können auch ausführen Docker verfassen – erstellen Sie für die Anwendungen aus, das mehrere Container/Dienste).</span><span class="sxs-lookup"><span data-stu-id="fd990-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="fd990-180">Abbildung 4 – 19: Ausführen von Docker build</span><span class="sxs-lookup"><span data-stu-id="fd990-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="fd990-181">Optional, statt direkt Docker "erstellen" aus dem Ordner des Projekts, Sie können einen bereitstellbaren Ordner zuerst generieren, mit der .NET-Bibliotheken, die erforderlich sind, veröffentlichen mithilfe der Laufzeit Dotnet Befehl, und führen Sie Docker Build.</span><span class="sxs-lookup"><span data-stu-id="fd990-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="fd990-182">In diesem Beispiel wird dies ein Docker Bild erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: erste (: zuerst wird ein Tag, wie eine bestimmte Version).</span><span class="sxs-lookup"><span data-stu-id="fd990-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="fd990-183">Sie können diesen Schritt für jeden benutzerdefinierten Abbilds nutzen, die Sie für die zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="fd990-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="fd990-184">Sie können vorhandenen Images in Ihr lokales Repository (Entwicklungscomputer) Suchbefehl mit Docker Images, wie in Abbildung 4-20 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fd990-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="fd990-185">Abbildung 4-20: Anzeigen von vorhandenen Images mit Docker-images</span><span class="sxs-lookup"><span data-stu-id="fd990-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="fd990-186">Schritt 4: (Optional) definieren Ihre Dienste in Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten</span><span class="sxs-lookup"><span data-stu-id="fd990-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="fd990-187">Mit der Docker-compose.yml-Datei können Sie einen Satz verwandter Dienste als einer zusammengesetzten Anwendung bereitgestellt werden, mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt erläuterten definieren.</span><span class="sxs-lookup"><span data-stu-id="fd990-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="fd990-188">Sie müssen diese Datei im Hauptfenster oder Stammordner für die Projektmappe zu erstellen. Sie müssen einen vergleichbaren Artikel in der folgenden Docker-compose.yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="fd990-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="fd990-189">In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und den Redis-Dienst (eine beliebte Cachedienst).</span><span class="sxs-lookup"><span data-stu-id="fd990-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="fd990-190">Jeder Dienst wird als Container bereitgestellt werden, daher muss eine konkrete Docker Bild für jede zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd990-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="fd990-191">Für diesen bestimmten Webdienst müssen das Abbild wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="fd990-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="fd990-192">Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="fd990-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="fd990-193">Weiterleiten Sie die verfügbar gemachten Port 80 für den Container an Port 81 auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="fd990-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="fd990-194">Laden Sie das Projektverzeichnis auf dem Host /code innerhalb des Containers, wodurch Sie zum Ändern des Codes, ohne das Bild neu erstellen</span><span class="sxs-lookup"><span data-stu-id="fd990-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="fd990-195">Verknüpfen Sie den Webdienst für den Redis-Dienst</span><span class="sxs-lookup"><span data-stu-id="fd990-195">Link the web service to the redis service</span></span>

<span data-ttu-id="fd990-196">Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) von Docker Hub-Registrierung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fd990-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="fd990-197">[redis](http://redis.io/) ist eine sehr beliebte Cache-System für die serverseitigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fd990-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="fd990-198">Schritt 5: Erstellen und Ausführen der Docker-app</span><span class="sxs-lookup"><span data-stu-id="fd990-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="fd990-199">Wenn Ihre app nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in der Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fd990-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="fd990-200">Wenn Ihre app aus mehreren Diensten besteht, Sie müssen jedoch *Verfassen sie*ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="fd990-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="fd990-201">Sehen Sie die verschiedenen Optionen an.</span><span class="sxs-lookup"><span data-stu-id="fd990-201">Let's see the different options.</span></span>

<span data-ttu-id="fd990-202">***Option A: Führen Sie einen einzelnen Container oder Dienst***</span><span class="sxs-lookup"><span data-stu-id="fd990-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="fd990-203">Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fd990-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="fd990-204">Beachten Sie, dass für diese bestimmte Bereitstellung wir Anforderungen an Port 80 mit den internen Port 5000 gesendet umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fd990-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="fd990-205">Nun wird die Anwendung den externen Port 80 auf der Hostebene überwacht.</span><span class="sxs-lookup"><span data-stu-id="fd990-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="fd990-206">***Option B: verfassen und Ausführen einer Anwendung mehrere container***</span><span class="sxs-lookup"><span data-stu-id="fd990-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="fd990-207">In den meisten Enterprise-Szenarios wird eine Docker-Anwendung mehrere Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fd990-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="fd990-208">In diesen Fällen können Sie den Befehl ausführen Docker verfassen einrichten (Abbildung 4 – 21), verwenden die Docker-compose.yml-Datei, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="fd990-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="fd990-209">Mit diesem Befehl wird eine zusammengesetzte Anwendung mit allen seine zugehörige Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fd990-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="fd990-210">Abbildung 4 – 21: Ergebnisse mit dem Befehl "Docker-verfassen einrichten"</span><span class="sxs-lookup"><span data-stu-id="fd990-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="fd990-211">Nach dem Ausführen des Docker-verfassen einrichten, die Bereitstellung der Anwendung und ihre zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-22, in der VM-Darstellung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fd990-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="fd990-212">Abbildung 4 – 22: VM mit Docker-Containern bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="fd990-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="fd990-213">Hinweis Docker verfassen einrichten und "Docker run" möglicherweise hoch genug für die Container in der Entwicklungsumgebung testen, aber Sie möglicherweise verwenden sie überhaupt nicht, wenn Sie zur Arbeit mit Clustern Docker erwarten und Orchestrators wie Docker Containerhostclustern, Mesosphere DC/OS oder Kubernetes Damit skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="fd990-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="fd990-214">Bei Verwendung ein Clusters wie [Docker Containerhostclustern Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker für Windows und Mac seit Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen, z. B. Docker-Dienst für einzelne Dienste erstellen, oder Sie sind Bereitstellen einer app besteht aus mehreren Containern mit Docker Bundle verfassen und Docker bereitstellen MyBundleFile, durch die zusammengesetzte app als Stapel, bereitstellen, wie im Artikel erläutert [verteilte Anwendung Bündel](https://blog.docker.com/2016/06/docker-app-bundle/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="fd990-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="fd990-215">Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) verwenden Sie unterschiedliche Bereitstellungsbefehlen und-Skripts sind auch.</span><span class="sxs-lookup"><span data-stu-id="fd990-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="fd990-216">Schritt 6: Testen der Docker-Anwendung (lokal, in Ihrer lokalen CD-VM)</span><span class="sxs-lookup"><span data-stu-id="fd990-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="fd990-217">Dieser Schritt hängen davon ab, welche Vorgänge die app ausführt.</span><span class="sxs-lookup"><span data-stu-id="fd990-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="fd990-218">In eine sehr einfache .NET Core Web-API "Hello World" als eine einzelne Container oder einen Dienst bereitgestellt haben müssten Sie einfach auf den Dienst zuzugreifen, durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="fd990-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="fd990-219">Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="fd990-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="fd990-220">Docker-Computer-IP- *your Containername*</span><span class="sxs-lookup"><span data-stu-id="fd990-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="fd990-221">Öffnen Sie einen Browser, und navigieren Sie zu diesem Standort, auf dem Docker-Host; Ihre app/-Dienst ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4 – 23 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fd990-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="fd990-222">Abbildung 4 – 23: Testen der Docker-Anwendung, die lokal mithilfe von "localhost"</span><span class="sxs-lookup"><span data-stu-id="fd990-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="fd990-223">Beachten Sie, dass Port 80 verwendet wird, jedoch intern an Port 5000, umgeleitet wird wurde, da, wie mit "Docker run", bereitgestellt wurde wie zuvor beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="fd990-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="fd990-224">Sie können dies mithilfe von CURL aus der Terminaldienste testen.</span><span class="sxs-lookup"><span data-stu-id="fd990-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="fd990-225">Bei einer Installation Docker unter Windows ist die Standard-IP-10.0.75.1, wie in Abbildung 4 – 24 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fd990-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="fd990-226">Abbildung 4 – 24: Testen einer Docker-Anwendung lokal mithilfe von CURL</span><span class="sxs-lookup"><span data-stu-id="fd990-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="fd990-227">**Debuggen eines Containers, ausgeführt auf Docker**</span><span class="sxs-lookup"><span data-stu-id="fd990-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="fd990-228">Visual Studio-Code unterstützt Debuggen Docker, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="fd990-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="fd990-229">Sie können auch .NET Core-Container in Docker Debuggen bei Verwendung von Visual Studio, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fd990-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="fd990-230">**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und [https://blogs.msdn.microsoft.com/ \ Benutzer\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="fd990-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fd990-231">[Vorherigen] (Docker-apps-Development-environment.md) [weiter] (Visual-Studio-Tools-für-docker.md)</span><span class="sxs-lookup"><span data-stu-id="fd990-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
