---
title: Innere Schleife Entwicklungsworkflow für Docker-apps
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 9e578599c61053704202946772c43bdb5ef895c2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105588"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="e261d-103">Innere Schleife Entwicklungsworkflow für Docker-apps</span><span class="sxs-lookup"><span data-stu-id="e261d-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="e261d-104">Vor dem Auslösen des äußeren Schleife Workflows umfasst die gesamte DevOps durchlaufen, Ausgangspunkt für alle weiteren auf jeder Entwickler-Computer, codieren die app selbst, ihren bevorzugten Sprachen oder Plattformen verwenden und lokal testen (Abbildung 4-14).</span><span class="sxs-lookup"><span data-stu-id="e261d-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="e261d-105">In jedem Fall, müssen aber einen sehr wichtigen Punkt gemeinsam, unabhängig davon, welche Sprache, Framework oder Plattformen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="e261d-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="e261d-106">In diesem bestimmten Workflow immer entwickeln und Testen des Docker-Containern lokal.</span><span class="sxs-lookup"><span data-stu-id="e261d-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="e261d-107">Abbildung 4 – 14: innere Schleife Entwicklung Kontext</span><span class="sxs-lookup"><span data-stu-id="e261d-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="e261d-108">Der Container oder eine Instanz des Docker-Images werden diese Komponenten enthalten:</span><span class="sxs-lookup"><span data-stu-id="e261d-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="e261d-109">Eine Auswahl des Betriebssystems (z. B. eine Linux-Distribution oder Windows)</span><span class="sxs-lookup"><span data-stu-id="e261d-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="e261d-110">Dateien vom Entwickler (z. B. app Binärdateien) hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="e261d-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="e261d-111">Konfiguration (z. B. umgebungseinstellungen und Abhängigkeiten)</span><span class="sxs-lookup"><span data-stu-id="e261d-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="e261d-112">Anweisungen für welche Prozesse für die Ausführung von Docker</span><span class="sxs-lookup"><span data-stu-id="e261d-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="e261d-113">Sie können die innere Schleife Entwicklungsworkflow einrichten, auf dem Docker wie der Prozess (im nächsten Abschnitt beschrieben) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e261d-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="e261d-114">Berücksichtigen Sie, dass die ersten Schritte zum Einrichten der Umgebung ist nicht enthalten, da die, die nur einmal durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="e261d-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="e261d-115">Erstellen eine einzelne app in einem Docker-Container mithilfe von Visual Studio Code und Docker-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="e261d-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="e261d-116">Apps bestehen aus Ihrer eigenen Services plus zusätzliche Bibliotheken (Abhängigkeiten).</span><span class="sxs-lookup"><span data-stu-id="e261d-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="e261d-117">Abbildung 4-15 zeigt die grundlegenden Schritte, die Sie in der Regel beim Erstellen einer app Docker ein, gefolgt von detaillierten Beschreibungen der einzelnen Schritte ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="e261d-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="e261d-118">Abbildung 4 – 15: Allgemeine Workflow für den Lebenszyklus Anwendungsmöglichkeiten Docker-Containern mit Docker-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="e261d-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="e261d-119">Schritt 1: Beginnen Sie in Visual Studio-Code codieren, und erstellen Sie Ihre erste Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="e261d-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="e261d-120">Die Möglichkeit, die Entwicklung der Anwendung ist ziemlich ähnlich wie bei, die Sie dies, ohne Docker tun.</span><span class="sxs-lookup"><span data-stu-id="e261d-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="e261d-121">Der Unterschied besteht darin, dass beim Entwickeln, sind Sie bereitstellen und Testen Ihrer Anwendung oder ausgeführte dateiserverdienste Docker-Containern, die in Ihrer lokalen Umgebung (z. B. ein Linux-VM oder -Windows) platziert.</span><span class="sxs-lookup"><span data-stu-id="e261d-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="e261d-122">**Das Einrichten der lokalen Umgebung**</span><span class="sxs-lookup"><span data-stu-id="e261d-122">**Setting up your local environment**</span></span>

<span data-ttu-id="e261d-123">Mit den neuesten Versionen von Docker für Macintosh und Windows es ist einfacher als je, Docker-Anwendungen entwickeln, und das Setup ist einfach.</span><span class="sxs-lookup"><span data-stu-id="e261d-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="e261d-124">**Weitere Informationen** finden Sie eine Anleitung zum Einrichten von Docker für Windows [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="e261d-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="e261d-125">Anweisungen zum Einrichten von Docker für Mac, wechseln Sie zu <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="e261d-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="e261d-126">Darüber hinaus benötigen Sie einen Code-Editor, damit Sie Ihre Anwendung bei der Verwendung von Docker-Befehlszeilenschnittstelle tatsächlich entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="e261d-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="e261d-127">Microsoft bietet Visual Studio-Code, der eine einfache Code-Editor, die auf Windows, Mac und Linux unterstützt wird ist, und bietet IntelliSense mit [für viele Sprachen unterstützen](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET Go, Java, Ruby, Python, und die meisten modernen Sprachen), [Debuggen](https://code.visualstudio.com/Docs/editor/debugging), [Integration mit Git](https://code.visualstudio.com/Docs/editor/versioncontrol) und [unterstützen](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="e261d-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="e261d-128">Dieser Editor ist hervorragend für Mac und Linux-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="e261d-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="e261d-129">In Windows können Sie auch die vollständige Visual Studio-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e261d-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="e261d-130">**Weitere Informationen** finden Sie Anweisungen zum Installieren von Visual Studio für Windows, Mac und Linux [ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span><span class="sxs-lookup"><span data-stu-id="e261d-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="e261d-131">Sie können mit Docker-Befehlszeilenschnittstelle arbeiten und Ihren Code mit einem beliebigen Codeeditor schreiben, aber bei Verwendung von Visual Studio Code macht es einfach, zum Erstellen von dockerfile-Datei und Docker-compose.yml-Dateien in Ihrem Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="e261d-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="e261d-132">Darüber hinaus können Sie Aufgaben für Visual Studio-Code aus der IDE ausführen, die Skripts aufgefordert, die ausführlichen mit Docker-Befehlszeilenschnittstelle, darunter Vorgänge ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e261d-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="e261d-133">Visual Studio-Code ist durch eine Erweiterung bereitgestellt, die Sie installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="e261d-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="e261d-134">Drücken Sie STRG + UMSCHALT + P dazu geben **Ext installieren**, und führen Sie die Erweiterungen: Erweiterung installieren-Befehl, um die Liste der Marketplace-Erweiterung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e261d-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="e261d-135">Geben Sie als Nächstes **Docker** zum Filtern der Ergebnisse, und wählen Sie die dockerfile-Datei und Docker verfassen Datei (Yml) Support-Erweiterung, wie in Abbildung 4-16 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e261d-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="e261d-136">Abbildung 4 – 16: die Docker-Erweiterung in Visual Studio Code installieren</span><span class="sxs-lookup"><span data-stu-id="e261d-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="e261d-137">Schritt 2: Erstellen einer dockerfile-Datei im Zusammenhang mit einem vorhandenen Image (plain OS oder Dev Umgebungen wie .NET Core, Node.js und Ruby)</span><span class="sxs-lookup"><span data-stu-id="e261d-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="e261d-138">Sie benötigen eine dockerfile-Datei pro benutzerdefiniertes Bild erstellt werden sollen und Container bereitgestellt werden, daher, wenn Ihre app aus einem einzelnen benutzerdefinierten Dienst besteht, benötigen Sie eine einzelne dockerfile-Datei.</span><span class="sxs-lookup"><span data-stu-id="e261d-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="e261d-139">Aber wenn Ihre app aus mehreren Diensten (wie eine Microservices-Architektur) besteht, benötigen Sie eine dockerfile-Datei pro Dienst.</span><span class="sxs-lookup"><span data-stu-id="e261d-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="e261d-140">Die dockerfile-Datei befindet sich im Stammordner der Ihrer app oder Ihrem Dienst in der Regel und die erforderlichen Befehle enthält, damit diese Docker weiß, wie einrichten und Ausführen dieser app oder einen Dienst.</span><span class="sxs-lookup"><span data-stu-id="e261d-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="e261d-141">Sie können Ihr dockerfile-Datei erstellen und dem Projekt zusammen mit Ihrem Code hinzufügen (.NET Core, node.js usw.), oder wenn Sie mit der Umgebung vertraut sind, sehen Sie sich die folgenden Tipps.</span><span class="sxs-lookup"><span data-stu-id="e261d-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="e261d-142">Können Sie ein Befehlszeilentool namens [Handelsversion Docker](https://github.com/Microsoft/generator-docker), dem Gerüste Dateien aus Ihrem Projekt in der Sprache, die Sie auswählen, und fügt die erforderlichen Dateien der Docker-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e261d-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="e261d-143">Im Grunde um Entwicklern die ersten Schritte zu unterstützen, erstellt er die entsprechenden dockerfile-Datei Docker-compose.yml und anderen zugehörigen Skripts zum Erstellen und Ausführen von Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="e261d-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="e261d-144">Dieses Yeoman-Generators werden einige Fragen, Fragen die ausgewählte Sprache und Ziel Container Entwicklungshost aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="e261d-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![Handelsversion Docker](./media/image21.png)

<span data-ttu-id="e261d-146">Beispielsweise zeigt Abbildung 4 – 17 zwei Screenshots aus der Terminals in Windows und auf einem Mac, in beiden Fällen zu ausgeführt Handelsversion Docker, die den Code Beispielprojekte (derzeit .NET Core, Golang und Node.js als unterstützten Sprachen) bereits so konfiguriert, dass arbeiten generieren wird Anfang Docker.</span><span class="sxs-lookup"><span data-stu-id="e261d-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="e261d-147">Abbildung 4 – 17: Handelsversion Docker Befehl Tool in Windows (links) und auf einem Mac</span><span class="sxs-lookup"><span data-stu-id="e261d-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="e261d-148">Abbildung 4 – 18 zeigt ein Beispiel für verwendet werden, können Docker Nachdem Sie ein vorhandenes Projekt für .NET Core zu Gerüstbau werden verfügen.</span><span class="sxs-lookup"><span data-stu-id="e261d-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="e261d-149">Abbildung 4 – 18: Handelsversion Docker mit einer vorhandenen .NET Core Projekt vorhanden</span><span class="sxs-lookup"><span data-stu-id="e261d-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="e261d-150">Geben Sie aus der dockerfile-Datei welche Basis Docker-Image, das Sie verwenden (z. B. mit "von microsoft/dotnet:1.0.0-core") an.</span><span class="sxs-lookup"><span data-stu-id="e261d-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="e261d-151">In der Regel erstellen Sie Ihr benutzerdefinierte Bild eine Basis-Image, die Sie aus jeder offizielle Repository auf der [Docker Hub-Registrierung](https://hub.docker.com/) (z. B. ein [Bild für .NET Core](https://hub.docker.com/r/microsoft/dotnet/) oder einem [für Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="e261d-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="e261d-152">***Option A: Verwenden eines vorhandenen offizielle Docker-Images***</span><span class="sxs-lookup"><span data-stu-id="e261d-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="e261d-153">Mit einem offiziellen Repository Sprache Stapel mit einer Versionsnummer wird sichergestellt, dass die gleichen Sprachfunktionen auf allen Computern (einschließlich Entwicklungs-, Test- und Produktionszwecke) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e261d-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="e261d-154">Es folgt ein Beispiel für dockerfile-Datei für einen .NET Core-Container:</span><span class="sxs-lookup"><span data-stu-id="e261d-154">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="e261d-155">In diesem Fall wird die Version 1.0.1 des offiziellen ASP.NET Core Docker-Images für Linux mit dem Namen microsoft/aspnetcore:1.0.1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="e261d-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="e261d-156">Weitere Informationen finden Sie in der [ASP.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/aspnetcore/) und [.NET Core Docker-Image-Seite](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="e261d-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="e261d-157">Auch konnten verwenden Sie ein anderes vergleichbare Bild wie Knoten: 4-Onbuild für Node.js oder viele andere vorkonfigurierter Images für die Entwicklungssprachen, von denen in verfügbaren [Docker Hub](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="e261d-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="e261d-158">In der dockerfile-Datei müssen Sie auch weisen Docker an, den TCP-Port zu überwachen, die zur Laufzeit (z. B. Port 80) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e261d-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="e261d-159">Es gibt andere Zeilen Konfiguration, die Sie in die dockerfile-Datei je nach Sprache/Framework, die Sie verwenden, die hinzufügen können, damit Docker weiß, wie die app ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e261d-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="e261d-160">Sie benötigen beispielsweise die ENTRYPOINT-Zeile mit \["Dotnet", "MyCustomMicroservice.dll"\] eine app .NET Core ausgeführt wird, obwohl Sie mehrere Varianten abhängig von der Ansatz zum Erstellen und führen Sie den Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e261d-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="e261d-161">Wenn Sie verwenden das SDK und Dotnet CLI erstellen und Ausführen der app .NET, wäre es etwas anders.</span><span class="sxs-lookup"><span data-stu-id="e261d-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="e261d-162">Entscheidend ist, dass die ENTRYPOINT-Zeile plus zusätzliche Zeilen je nach der Sprachplattform unterschiedlich sind, die Sie für Ihre Anwendung auswählen.</span><span class="sxs-lookup"><span data-stu-id="e261d-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="e261d-163">**Weitere Informationen** finden Sie Informationen zum Erstellen von Docker-Images für .NET Core-Anwendungen, <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="e261d-163">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="e261d-164">Wechseln Sie zu, um weitere Informationen zur Erstellung Ihrer eigenen Abbilder [ https://docs.docker.com/engine/\ Lernprogramme/Dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="e261d-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="e261d-165">**Multiplattform-Image-Repositorys**</span><span class="sxs-lookup"><span data-stu-id="e261d-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="e261d-166">Windows-Containern häufiger verwendet, kann ein einzelnes Repository Plattform Varianten, z. B. ein Linux- und Windows-Image enthält.</span><span class="sxs-lookup"><span data-stu-id="e261d-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="e261d-167">Dies ist ein neues Feature eingehen, die Anbieter auf ein einzelnes Repository verwenden, z. B. mehrere Plattformen abdecken kann Docker [Microsoft/Aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Repository, die am DockerHub Registrierung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e261d-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="e261d-168">Sobald die Funktion aktiv ist, wird dieses Bild für das Ausführen von Pull aus einem Windows-Host die Windows-Variante einziehen während der gleiche Name für das Ausführen von Pull aus einem Linux-Host die Linux-Variante pull.</span><span class="sxs-lookup"><span data-stu-id="e261d-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="e261d-169">***Option B: Erstellen des Basis-Image von Grund auf neu***</span><span class="sxs-lookup"><span data-stu-id="e261d-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="e261d-170">Sie können eigene Docker-Basis-Image von Grund auf neu erstellen, wie in diesem erläutert [Artikel](https://docs.docker.com/engine/userguide/eng-image/baseimages/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="e261d-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="e261d-171">Dies ist ein Szenario, das ist wahrscheinlich nicht für Sie am besten geeignet, wenn Sie gerade mit Docker gestartet werden, aber wenn Sie die bestimmte Bits des eigene Basisimage festlegen möchten, können Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="e261d-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="e261d-172">Schritt 3: Erstellen Sie Ihre benutzerdefinierten Docker-Images, die Ihr Dienst darin einbetten</span><span class="sxs-lookup"><span data-stu-id="e261d-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="e261d-173">Für jeden benutzerdefinierten Dienst, der Ihrer app ausmacht, müssen Sie eine verwandte Image zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e261d-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="e261d-174">Wenn Ihre app von einem Einzelgerät oder Web-app vorgenommen wird, benötigen Sie nur ein einziges Bild.</span><span class="sxs-lookup"><span data-stu-id="e261d-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="e261d-175">Der Workflow"DevOps äußere Schleife" modellbasiert, die Bilder erstellt werden durch einen automatisierten Erstellungsprozess Wenn Quellcode in einem Git-Repository (Continuous Integration) übertragen, sodass die Bilder in der globalen Umgebung erstellt werden von Ihrem Quellcode.</span><span class="sxs-lookup"><span data-stu-id="e261d-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="e261d-176">Aber bevor wir diese Route für die äußere Schleife hörmal betrachten, müssen wir sicherstellen, dass die Docker-Anwendung, damit sie Code mithilfe von Push übertragen nicht, die unter Umständen nicht ordnungsgemäß auf dem Quellcodeverwaltungssystem (Git, usw.) funktionieren tatsächlich ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e261d-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="e261d-177">Daher muss jeder Entwickler zunächst müssen den gesamten Prozess der inneren Schleife um lokal testen und entwickeln, bis eine vollständige Funktion push oder ändern Sie in das Quellcodeverwaltungssystem werden soll.</span><span class="sxs-lookup"><span data-stu-id="e261d-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="e261d-178">Um ein Bild in Ihrer lokalen Umgebung und verwenden die dockerfile-Datei zu erstellen, können Sie den Befehl "Docker Build", wie in Abbildung 4-19 gezeigt (Sie können auch ausführen Docker verfassen – erstellen Sie für die Anwendungen aus, das mehrere Container/Dienste).</span><span class="sxs-lookup"><span data-stu-id="e261d-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="e261d-179">Abbildung 4 – 19: Ausführen von Docker build</span><span class="sxs-lookup"><span data-stu-id="e261d-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="e261d-180">Optional, statt direkt Docker "erstellen" aus dem Ordner des Projekts, Sie können einen bereitstellbaren Ordner zuerst generieren, mit der .NET-Bibliotheken, die erforderlich sind, veröffentlichen mithilfe der Laufzeit Dotnet Befehl, und führen Sie Docker Build.</span><span class="sxs-lookup"><span data-stu-id="e261d-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="e261d-181">In diesem Beispiel wird dies ein Docker Bild erstellt, mit dem Namen Cesardl/Netcore-Webapi-Microservice-Docker: erste (: zuerst wird ein Tag, wie eine bestimmte Version).</span><span class="sxs-lookup"><span data-stu-id="e261d-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="e261d-182">Sie können diesen Schritt für jeden benutzerdefinierten Abbilds nutzen, die Sie für die zusammengesetzte Docker-Anwendung mit mehreren Containern erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="e261d-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="e261d-183">Sie können vorhandenen Images in Ihr lokales Repository (Entwicklungscomputer) Suchbefehl mit Docker Images, wie in Abbildung 4-20 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e261d-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="e261d-184">Abbildung 4-20: Anzeigen von vorhandenen Images mit Docker-images</span><span class="sxs-lookup"><span data-stu-id="e261d-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="e261d-185">Schritt 4: (Optional) definieren Ihre Dienste in Docker-compose.yml beim Erstellen einer zusammengesetzten Docker-app mit mehreren Diensten</span><span class="sxs-lookup"><span data-stu-id="e261d-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="e261d-186">Mit der Docker-compose.yml-Datei können Sie einen Satz verwandter Dienste als einer zusammengesetzten Anwendung bereitgestellt werden, mit den Bereitstellungsbefehlen im nächsten Schritt Abschnitt erläuterten definieren.</span><span class="sxs-lookup"><span data-stu-id="e261d-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="e261d-187">Sie müssen diese Datei im Hauptfenster oder Stammordner für die Projektmappe zu erstellen. Sie müssen einen vergleichbaren Artikel in der folgenden Docker-compose.yml-Datei:</span><span class="sxs-lookup"><span data-stu-id="e261d-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="e261d-188">In diesem speziellen Fall diese Datei definiert zwei Dienste: der Webdienst (Ihr benutzerdefinierter Dienst) und den Redis-Dienst (eine beliebte Cachedienst).</span><span class="sxs-lookup"><span data-stu-id="e261d-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="e261d-189">Jeder Dienst wird als Container bereitgestellt werden, daher muss eine konkrete Docker Bild für jede zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e261d-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="e261d-190">Für diesen bestimmten Webdienst müssen das Abbild wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="e261d-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="e261d-191">Aus der dockerfile-Datei im aktuellen Verzeichnis erstellen</span><span class="sxs-lookup"><span data-stu-id="e261d-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="e261d-192">Weiterleiten Sie die verfügbar gemachten Port 80 für den Container an Port 81 auf dem Hostcomputer</span><span class="sxs-lookup"><span data-stu-id="e261d-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="e261d-193">Laden Sie das Projektverzeichnis auf dem Host /code innerhalb des Containers, wodurch Sie zum Ändern des Codes, ohne das Bild neu erstellen</span><span class="sxs-lookup"><span data-stu-id="e261d-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="e261d-194">Verknüpfen Sie den Webdienst für den Redis-Dienst</span><span class="sxs-lookup"><span data-stu-id="e261d-194">Link the web service to the redis service</span></span>

<span data-ttu-id="e261d-195">Der Redis-Dienst verwendet die [neueste öffentliche Redis-Image](https://hub.docker.com/_/redis/) von Docker Hub-Registrierung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e261d-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="e261d-196">[redis](https://redis.io/) ist eine sehr beliebte Cache-System für die serverseitigen Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e261d-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="e261d-197">Schritt 5: Erstellen und Ausführen der Docker-app</span><span class="sxs-lookup"><span data-stu-id="e261d-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="e261d-198">Wenn Ihre app nur einen einzelnen Container verfügt, müssen Sie nur ausführen, indem sie in der Docker-Host (VM oder physischer Server) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e261d-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="e261d-199">Wenn Ihre app aus mehreren Diensten besteht, Sie müssen jedoch *Verfassen sie*ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="e261d-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="e261d-200">Sehen Sie die verschiedenen Optionen an.</span><span class="sxs-lookup"><span data-stu-id="e261d-200">Let's see the different options.</span></span>

<span data-ttu-id="e261d-201">***Option A: Führen Sie einen einzelnen Container oder Dienst***</span><span class="sxs-lookup"><span data-stu-id="e261d-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="e261d-202">Sie können das Docker-Image ausführen, mithilfe von "Docker run" Befehl, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e261d-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="e261d-203">Beachten Sie, dass für diese bestimmte Bereitstellung wir Anforderungen an Port 80 mit den internen Port 5000 gesendet umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e261d-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="e261d-204">Nun wird die Anwendung den externen Port 80 auf der Hostebene überwacht.</span><span class="sxs-lookup"><span data-stu-id="e261d-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="e261d-205">***Option B: verfassen und Ausführen einer Anwendung mehrere container***</span><span class="sxs-lookup"><span data-stu-id="e261d-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="e261d-206">In den meisten Enterprise-Szenarios wird eine Docker-Anwendung mehrere Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e261d-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="e261d-207">In diesen Fällen können Sie den Befehl ausführen Docker verfassen einrichten (Abbildung 4 – 21), verwenden die Docker-compose.yml-Datei, die Sie zuvor erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e261d-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="e261d-208">Mit diesem Befehl wird eine zusammengesetzte Anwendung mit allen seine zugehörige Container bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e261d-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="e261d-209">Abbildung 4 – 21: Ergebnisse mit dem Befehl "Docker-verfassen einrichten"</span><span class="sxs-lookup"><span data-stu-id="e261d-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="e261d-210">Nach dem Ausführen des Docker-verfassen einrichten, die Bereitstellung der Anwendung und ihre zugehörigen Container in Ihrem Docker-Host, wie in Abbildung 4-22, in der VM-Darstellung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e261d-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="e261d-211">Abbildung 4 – 22: VM mit Docker-Containern bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="e261d-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="e261d-212">Hinweis Docker verfassen einrichten und "Docker run" möglicherweise hoch genug für die Container in der Entwicklungsumgebung testen, aber Sie möglicherweise verwenden sie überhaupt nicht, wenn Sie zur Arbeit mit Clustern Docker erwarten und Orchestrators wie Docker Containerhostclustern, Mesosphere DC/OS oder Kubernetes Damit skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="e261d-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="e261d-213">Bei Verwendung ein Clusters wie [Docker Containerhostclustern Modus](https://docs.docker.com/engine/swarm/) (verfügbar in Docker für Windows und Mac seit Version 1.12), müssen Sie zum Bereitstellen und Testen mit zusätzlichen Befehlen, z. B. Docker-Dienst für einzelne Dienste erstellen, oder Sie sind Bereitstellen einer app besteht aus mehreren Containern mit Docker Bundle verfassen und Docker bereitstellen MyBundleFile, durch die zusammengesetzte app als Stapel, bereitstellen, wie im Artikel erläutert [verteilte Anwendung Bündel](https://blog.docker.com/2016/06/docker-app-bundle/) von Docker.</span><span class="sxs-lookup"><span data-stu-id="e261d-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="e261d-214">Für [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) und [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) verwenden Sie unterschiedliche Bereitstellungsbefehlen und-Skripts sind auch.</span><span class="sxs-lookup"><span data-stu-id="e261d-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="e261d-215">Schritt 6: Testen der Docker-Anwendung (lokal, in Ihrer lokalen CD-VM)</span><span class="sxs-lookup"><span data-stu-id="e261d-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="e261d-216">Dieser Schritt hängen davon ab, welche Vorgänge die app ausführt.</span><span class="sxs-lookup"><span data-stu-id="e261d-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="e261d-217">In eine sehr einfache .NET Core Web-API "Hello World" als eine einzelne Container oder einen Dienst bereitgestellt haben müssten Sie einfach auf den Dienst zuzugreifen, durch die Bereitstellung des TCP-Ports in der dockerfile-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="e261d-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="e261d-218">Wenn Sie "localhost" nicht aktiviert ist, navigieren Sie zu dem Dienst finden Sie die IP-Adresse für den Computer mit diesem Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e261d-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="e261d-219">Docker-Computer-IP- *your Containername*</span><span class="sxs-lookup"><span data-stu-id="e261d-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="e261d-220">Öffnen Sie einen Browser, und navigieren Sie zu diesem Standort, auf dem Docker-Host; Ihre app/-Dienst ausgeführt wird, sollte angezeigt werden, wie in Abbildung 4 – 23 veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e261d-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="e261d-221">Abbildung 4 – 23: Testen der Docker-Anwendung, die lokal mithilfe von "localhost"</span><span class="sxs-lookup"><span data-stu-id="e261d-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="e261d-222">Beachten Sie, dass Port 80 verwendet wird, jedoch intern an Port 5000, umgeleitet wird wurde, da, wie mit "Docker run", bereitgestellt wurde wie zuvor beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="e261d-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="e261d-223">Sie können dies mithilfe von CURL aus der Terminaldienste testen.</span><span class="sxs-lookup"><span data-stu-id="e261d-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="e261d-224">Bei einer Installation Docker unter Windows ist die Standard-IP-10.0.75.1, wie in Abbildung 4 – 24 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e261d-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="e261d-225">Abbildung 4 – 24: Testen einer Docker-Anwendung lokal mithilfe von CURL</span><span class="sxs-lookup"><span data-stu-id="e261d-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="e261d-226">**Debuggen eines Containers, ausgeführt auf Docker**</span><span class="sxs-lookup"><span data-stu-id="e261d-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="e261d-227">Visual Studio-Code unterstützt Debuggen Docker, wenn Sie Node.js und anderen Plattformen wie .NET Core-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="e261d-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="e261d-228">Sie können auch .NET Core-Container in Docker Debuggen bei Verwendung von Visual Studio, wie im nächsten Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e261d-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="e261d-229">**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Debuggen von Node.js-Docker-Containern <https://blog.docker.com/2016/07/live-debugging-docker/> und [ https://blogs.msdn.microsoft.com/\ Benutzer\_Ed/2016/02/27 / Visual-Studio-Code-New-Features-13-Big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-Mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="e261d-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e261d-230">[Zurück](docker-apps-development-environment.md)
[Weiter](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="e261d-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
