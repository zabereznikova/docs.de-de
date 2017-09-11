---
title: Erstellen von .NET Core Docker-Images
description: Grundlegendes zu Docker-Images und .NET Core
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: de-de
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="8c471-104">Erstellen von Docker-Images für .NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8c471-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="8c471-105">Wir aktualisieren gerade .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="8c471-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="8c471-106">Die folgenden Anweisungen sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="8c471-106">The instructions below are out of date.</span></span> <span data-ttu-id="8c471-107">Wir entschuldigen uns aufrichtig für die Unannehmlichkeiten!</span><span class="sxs-lookup"><span data-stu-id="8c471-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="8c471-108">Docker und .NET Core werden zusammen verwendet. Hierzu sollten Sie die verschiedenen Docker-Images kennen, die angeboten werden, und wann der richtige Anwendungsfall für sie ist.</span><span class="sxs-lookup"><span data-stu-id="8c471-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="8c471-109">Die angebotenen Variationen sind nachfolgend aufgeführt. Sie erfahren, wie Sie eine ASP.NET Core-Web-API oder mithilfe von Yeoman Docker-Tools einen debugfähigen Container erstellen, und wie Visual Studio Code diesen Prozess unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="8c471-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="8c471-110">Docker-Image-Optimierungen</span><span class="sxs-lookup"><span data-stu-id="8c471-110">Docker Image Optimizations</span></span>

<span data-ttu-id="8c471-111">Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:</span><span class="sxs-lookup"><span data-stu-id="8c471-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="8c471-112">Images zum Entwickeln von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="8c471-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="8c471-113">Images zum Erstellen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="8c471-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="8c471-114">Images zum Ausführen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="8c471-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="8c471-115">Warum drei Images?</span><span class="sxs-lookup"><span data-stu-id="8c471-115">Why three images?</span></span>
<span data-ttu-id="8c471-116">Beim Entwickeln, Erstellen und Ausführen von Container-Anwendungen gibt es unterschiedliche Prioritäten.</span><span class="sxs-lookup"><span data-stu-id="8c471-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="8c471-117">**Entwicklung:** Wie schnell Änderungen durchgeführt und ob sie debugged werden können.</span><span class="sxs-lookup"><span data-stu-id="8c471-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="8c471-118">Die Größe des Images ist nicht so wichtig. Entscheidend ist, dass Sie Änderungen am Code vornehmen und diese schnell sehen können.</span><span class="sxs-lookup"><span data-stu-id="8c471-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="8c471-119">Einige der Tools zur Verwendung in Visual Studio Code, z.B. [yo docker](https://aka.ms/yodocker), nutzen dieses Image während der Entwicklungszeit.</span><span class="sxs-lookup"><span data-stu-id="8c471-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="8c471-120">**Build:** Was Sie benötigen, um Ihre App zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="8c471-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="8c471-121">Dies schließt den Compiler und alle anderen Abhängigkeiten zum Optimieren der Binärdateien ein.</span><span class="sxs-lookup"><span data-stu-id="8c471-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="8c471-122">Dieses Image ist nicht das Image, das Sie bereitstellen, es handelt sich vielmehr um ein Image, das Sie verwenden, um den Inhalt zu erstellen, den Sie in einem Produktions-Image platzieren.</span><span class="sxs-lookup"><span data-stu-id="8c471-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="8c471-123">Dieses Image wird in der fortlaufenden Integration oder Buildumgebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c471-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="8c471-124">Anstatt alle Abhängigkeiten direkt auf einem Build-Agent zu installieren, würde der Build-Agent beispielsweise ein Build-Image erstellen, um die Anwendung mit allen Abhängigkeiten zu kompilieren, die zum Erstellen der in dem Image enthaltenen App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8c471-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="8c471-125">Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c471-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="8c471-126">**Produktion:** Wie schnell Sie das Image bereitstellen und starten können.</span><span class="sxs-lookup"><span data-stu-id="8c471-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="8c471-127">Dieses Image ist klein, sodass es schnell über das Netzwerk aus der Docker-Registrierung zu den Docker-Hosts übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c471-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="8c471-128">Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="8c471-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="8c471-129">Im unveränderlichen Docker-Modell besteht keine Notwendigkeit zur dynamischen Kompilierung des Codes.</span><span class="sxs-lookup"><span data-stu-id="8c471-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="8c471-130">Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8c471-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="8c471-131">Zum Beispiel die veröffentlichte Ausgabe mit `dotnet publish`, die die kompilierten Binärdateien, Images, JS- und CSS-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="8c471-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="8c471-132">Im Laufe der Zeit sehen Sie Images, die JIT-kompilierte Pakete enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c471-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="8c471-133">Obwohl mehrere Versionen des .NET Core-Images verfügbar sind, verwenden alle eine oder mehrere Ebenen gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="8c471-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="8c471-134">Der benötigte Speicherplatz oder das Delta, das aus der Registrierung abgerufen wird, ist wesentlich kleiner als das gesamte Image, da alle Images eine oder mehrere Ebenen teilen.</span><span class="sxs-lookup"><span data-stu-id="8c471-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="8c471-135">Docker-Image-Varianten</span><span class="sxs-lookup"><span data-stu-id="8c471-135">Docker image variations</span></span>

<span data-ttu-id="8c471-136">Um die oben genannten Ziele zu erreichen, stehen Image-Varianten unter [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8c471-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="8c471-137">`microsoft/dotnet:<version>-sdk`: das Image **microsoft/dotnet:1.0.0-preview2-sdk** enthält das .NET Core SDK, .NET Core und Befehlszeilentools (CLI).</span><span class="sxs-lookup"><span data-stu-id="8c471-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="8c471-138">Dieses Image ist dem **Entwicklungsszenario** zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8c471-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="8c471-139">Dieses Image wird für lokale Entwicklung, Debuggen und Testen von Einheiten verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c471-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="8c471-140">Beispielsweise für alle Entwicklungen, bevor Sie Ihren Code einchecken.</span><span class="sxs-lookup"><span data-stu-id="8c471-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="8c471-141">Dieses Image kann auch für **Build**-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="8c471-142">`microsoft/dotnet:<version>-core`: Das Image **microsoft/dotnet:1.0.0-core** führt [portable .NET Core-Anwendungen](../deploying/index.md) aus und ist für die Ausführung von Anwendungen in der **Produktion** optimiert.</span><span class="sxs-lookup"><span data-stu-id="8c471-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="8c471-143">Es enthält nicht das SDK und soll die optimierte Ausgabe von `dotnet publish` übernehmen.</span><span class="sxs-lookup"><span data-stu-id="8c471-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="8c471-144">Die portable Laufzeit ist gut geeignet für Docker-Container-Szenarios, da mehrere laufende Container von gemeinsamen Image-Ebenen profitieren.</span><span class="sxs-lookup"><span data-stu-id="8c471-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="8c471-145">Alternative Images</span><span class="sxs-lookup"><span data-stu-id="8c471-145">Alternative images</span></span>

<span data-ttu-id="8c471-146">Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:</span><span class="sxs-lookup"><span data-stu-id="8c471-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="8c471-147">`microsoft/dotnet:<version>-onbuild`: Das Image **microsoft/dotnet:1.0.0-preview2-onbuild** enthält [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) Trigger.</span><span class="sxs-lookup"><span data-stu-id="8c471-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="8c471-148">Der Buildvorgang [KOPIERT](https://docs.docker.com/engine/reference/builder/#/copy) die Anwendung, führt `dotnet restore` aus und erstellt eine [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` Anweisung, um die Anwendung auszuführen, wenn das Docker-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c471-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="8c471-149">Auch wenn es kein optimiertes Image für die Produktion ist, können einige es hilfreich finden, einfach ihren Quellcode in ein Image zu kopieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c471-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="8c471-150">`microsoft/dotnet:<version>-core-deps`: Das Image **microsoft/dotnet:1.0.0-core-deps** zum Ausführen eigenständiger Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8c471-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="8c471-151">Es enthält das Betriebssystem mit allen nativen Abhängigkeiten, die von .NET Core benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="8c471-152">Dieses Image kann auch als Basisimage verwendet werden, für Ihre eigenen benutzerdefinierten CoreFX oder CoreCLR Builds.</span><span class="sxs-lookup"><span data-stu-id="8c471-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="8c471-153">Während die Variante **onbuild** so optimiert ist, dass Sie einfach Code in einem Image platzieren und ausführen können, ist dieses Image dafür optimiert, dass nur die benötigten Betriebssystemabhängigkeiten zum Ausführen von .NET Core-Apps bereitgestellt werden, bei denen die .NET Runtime im Anwendungspaket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="8c471-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="8c471-154">Dieses Image ist im Allgemeinen nicht für das Ausführen mehrerer .NET Core-Container auf dem gleichen Host optimiert, da jedes Image die .NET Core Runtime in der Anwendung hat und eine Image-Überlagerung keinen Vorteil bringt.</span><span class="sxs-lookup"><span data-stu-id="8c471-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="8c471-155">Aktuelle Versionen jeder Variante:</span><span class="sxs-lookup"><span data-stu-id="8c471-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="8c471-156">`microsoft/dotnet`oder `microsoft/dotnet:latest` (einschließlich SDK)</span><span class="sxs-lookup"><span data-stu-id="8c471-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="8c471-157">Es folgt eine Liste der Images nach einem `docker pull <imagename>` auf einem Entwicklungscomputer mit den verschiedenen Größen.</span><span class="sxs-lookup"><span data-stu-id="8c471-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="8c471-158">Beachten Sie, dass die Entwicklungs/Build-Variante `microsoft/dotnet:1.0.0-preview2-sdk` größer ist, da sie das SDK zum Entwickeln und Erstellen der Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="8c471-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="8c471-159">Die Produktionsvariante `microsoft/dotnet:core` ist kleiner, da sie nur die .NET Core Runtime enthält.</span><span class="sxs-lookup"><span data-stu-id="8c471-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="8c471-160">Das minimale Image `core-deps`, das unter Linux verwendet werden kann, ist sehr viel kleiner, jedoch muss die Anwendung eine private Kopie der .NET Runtime enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c471-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="8c471-161">Da Container bereits private Isolationsbarrieren sind, verlieren Sie diese Optimierung, wenn mehrere Dotnet-basierte Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="8c471-162">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="8c471-162">Prerequisites</span></span>

<span data-ttu-id="8c471-163">Zum Erstellen und Ausführen benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8c471-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="8c471-164">.NET Core</span><span class="sxs-lookup"><span data-stu-id="8c471-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="8c471-165">[Docker](https://www.docker.com/products/docker) zum lokalen Ausführen der Docker-Container</span><span class="sxs-lookup"><span data-stu-id="8c471-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="8c471-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="8c471-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="8c471-167">[Yeoman-Generator für ASP.NET](https://github.com/omnisharp/generator-aspnet) zum Erstellen der Web-API-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c471-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="8c471-168">[Yeoman-Generator für Docker](http://aka.ms/yodocker) von Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c471-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="8c471-169">Installieren Sie die Yeoman-Generatoren für ASP.NET Core und Docker mithilfe von npm</span><span class="sxs-lookup"><span data-stu-id="8c471-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="8c471-170">In diesem Beispiel wird [Visual Studio Code](http://code.visualstudio.com) für den Editor verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c471-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="8c471-171">Erstellen der Web-API-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c471-171">Creating the Web API application</span></span>

<span data-ttu-id="8c471-172">Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus.</span><span class="sxs-lookup"><span data-stu-id="8c471-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="8c471-173">Die fertige Anwendung befindet sich im [Repository „dotnet/docs“ auf GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="8c471-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="8c471-174">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="8c471-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="8c471-175">Erstellen Sie ein Verzeichnis für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8c471-175">Create a directory for your application.</span></span>

<span data-ttu-id="8c471-176">Öffnen Sie einen Befehl oder eine Terminal-Sitzung in diesem Verzeichnis, und verwenden Sie den ASP.NET Yeoman-Generator, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="8c471-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="8c471-177">Wählen Sie **Web-API-Anwendung**, geben Sie **api** für den Namen der App ein, und tippen Sie auf die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8c471-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="8c471-178">Sobald das Gerüst der Anwendung steht, wechseln Sie in das Verzeichnis `/api`, und stellen Sie die NuGet-Abhängigkeiten mithilfe von `dotnet restore` wieder her.</span><span class="sxs-lookup"><span data-stu-id="8c471-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="8c471-179">Testen Sie die Anwendung mit `dotnet run`, und gehen Sie zu **http://localhost:5000/api/values**</span><span class="sxs-lookup"><span data-stu-id="8c471-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="8c471-180">Verwenden Sie `Ctrl+C`, um die Anwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8c471-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="8c471-181">Hinzufügen der Docker-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8c471-181">Adding Docker support</span></span>

<span data-ttu-id="8c471-182">Hinzufügen der Docker-Unterstützung für das Projekt durch die Verwendung des Yeoman-Generators von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c471-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="8c471-183">Er unterstützt derzeit .NET Core-, Node.js- und Go-Projekte durch Erstellen einer Docker-Datei und Skripts, mit deren Hilfe Projekte in Containern erstellt und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="8c471-184">Visual Studio Code-spezifische Dateien werden ebenfalls hinzugefügt (launch.json, tasks.json), für Editor-Debuggen und Befehlspalettenunterstützung.</span><span class="sxs-lookup"><span data-stu-id="8c471-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="8c471-185">Wählen Sie `.NET Core` als Projekttyp</span><span class="sxs-lookup"><span data-stu-id="8c471-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="8c471-186">`rtm` für die Version von .NET Core</span><span class="sxs-lookup"><span data-stu-id="8c471-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="8c471-187">`Y` das Projekt verwendet einen Webserver</span><span class="sxs-lookup"><span data-stu-id="8c471-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="8c471-188">`5000` ist der Port, der von der Web-API-Anwendung (http://localhost:5000) überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="8c471-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="8c471-189">`api` für den Image-Namen</span><span class="sxs-lookup"><span data-stu-id="8c471-189">`api` for the image name</span></span>
- <span data-ttu-id="8c471-190">`api` für den Dienstnamen</span><span class="sxs-lookup"><span data-stu-id="8c471-190">`api` for the service name</span></span>
- <span data-ttu-id="8c471-191">`api` für das Verfassen-Projekt</span><span class="sxs-lookup"><span data-stu-id="8c471-191">`api` for the compose project</span></span> 
- <span data-ttu-id="8c471-192">`Y` zum Überschreiben der aktuellen Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="8c471-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="8c471-193">Nach Abschluss des Generators werden die folgenden Dateien zum Projekt hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="8c471-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="8c471-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="8c471-194">.vscode/launch.json</span></span>
- <span data-ttu-id="8c471-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="8c471-195">Dockerfile.debug</span></span>
- <span data-ttu-id="8c471-196">Docker-Datei</span><span class="sxs-lookup"><span data-stu-id="8c471-196">Dockerfile</span></span>
- <span data-ttu-id="8c471-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="8c471-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="8c471-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="8c471-198">docker-compose.yml</span></span>
- <span data-ttu-id="8c471-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="8c471-199">dockerTask.ps1</span></span>
- <span data-ttu-id="8c471-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="8c471-200">dockerTask.sh</span></span>
- <span data-ttu-id="8c471-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="8c471-201">.vscode/tasks.json</span></span>

<span data-ttu-id="8c471-202">Der Generator erstellt zwei Docker-Dateien.</span><span class="sxs-lookup"><span data-stu-id="8c471-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="8c471-203">Die Datei **Dockerfile.Debug** basiert auf dem Image **microsoft/dotnet:1.0.0-preview2-sdk**, das wie in der Liste der Varianten aufgeführt SDK, CLI und .NET Core umfasst, und das Image für Entwicklung und Debuggen (F5) ist.</span><span class="sxs-lookup"><span data-stu-id="8c471-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="8c471-204">Mit all diesen Komponenten hat das Image eine Größe von ungefähr 540 MB.</span><span class="sxs-lookup"><span data-stu-id="8c471-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="8c471-205">**Dockerfile** ist das Release-Image basierend auf dem Image **microsoft/dotnet:1.0.0-core**, und soll für die Produktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="8c471-206">Dieses Image ist nach dem Erstellen etwa 253 MB groß.</span><span class="sxs-lookup"><span data-stu-id="8c471-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="8c471-207">Erstellen der Docker-Images</span><span class="sxs-lookup"><span data-stu-id="8c471-207">Creating the Docker images</span></span>
<span data-ttu-id="8c471-208">Mithilfe des Skripts `dockerTask.sh` oder `dockerTask.ps1` können Image und Container für die **api**-Anwendung für eine bestimmte Umgebung erstellt oder verfasst werden.</span><span class="sxs-lookup"><span data-stu-id="8c471-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="8c471-209">Erstellen des **debug**-Image durch Ausführen des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="8c471-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="8c471-210">Das Image erstellt die ASP.NET-Anwendung, führt `dotnet restore` aus, fügt den Debugger dem Image hinzu, setzt einen `ENTRYPOINT`, und kopiert die App in das Image.</span><span class="sxs-lookup"><span data-stu-id="8c471-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="8c471-211">Das Ergebnis ist ein Docker-Image mit dem Namen *api* mit einem `TAG` von *debug*.</span><span class="sxs-lookup"><span data-stu-id="8c471-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="8c471-212">Sehen Sie sich die Images auf dem Computer mit `docker images` an.</span><span class="sxs-lookup"><span data-stu-id="8c471-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="8c471-213">Alternativ können Sie durch Öffnen der Anwendung in Visual Studio Code und Verwenden der Debugging-Tools das Image erstellen und die Anwendung innerhalb des Docker-Containers ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c471-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="8c471-214">Wählen Sie das Debug-Symbol in der Ansichtsleiste auf der linken Seite von Visual Studio Code aus.</span><span class="sxs-lookup"><span data-stu-id="8c471-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![vscode-Debug-Symbol](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="8c471-216">Tippen Sie dann auf das Wiedergabesymbol oder F5, um das Image zu generieren, und starten Sie die Anwendung innerhalb des Containers.</span><span class="sxs-lookup"><span data-stu-id="8c471-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="8c471-217">Die Web-API wird unter http://localhost:5000 mit Ihrem Standard-Webbrowser gestartet.</span><span class="sxs-lookup"><span data-stu-id="8c471-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![VSCode Docker-Tools Debug](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="8c471-219">Sie können Haltepunkte in Ihrer Anwendung setzen, durchlaufen usw., als ob die Anwendung lokal auf dem Entwicklungscomputer statt in dem Container ausgeführt würde.</span><span class="sxs-lookup"><span data-stu-id="8c471-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="8c471-220">Der Vorteil beim Debuggen innerhalb des Containers ist, dass dies das gleiche Image ist, das in einer Produktionsumgebung bereitgestellt würde.</span><span class="sxs-lookup"><span data-stu-id="8c471-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="8c471-221">Erstellen des Releases oder Produktions-Images erfordert einfach das Ausführen des Befehls über das Terminal und die Übergabe des Namens der `release`-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="8c471-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="8c471-222">Der Befehl erstellt das Image basierend auf dem kleineren Basis-Image **microsoft/dotnet:core**, macht Port 5000 [verfügbar](https://docs.docker.com/engine/reference/builder/#/expose), legt den [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) für `dotnet api.dll` fest und kopiert diesen in das Verzeichnis `/app`.</span><span class="sxs-lookup"><span data-stu-id="8c471-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="8c471-223">Es gibt keinen Debugger, kein SDK oder `dotnet restore`, die zu einem viel kleineren Image führen.</span><span class="sxs-lookup"><span data-stu-id="8c471-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="8c471-224">Das Image wird **api** benannt mit einem `TAG` **aktuell**.</span><span class="sxs-lookup"><span data-stu-id="8c471-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="8c471-225">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8c471-225">Summary</span></span>

<span data-ttu-id="8c471-226">Mithilfe des Docker-Generators können Sie erforderliche Dateien für eine Web-API-Anwendung hinzufügen. Dies vereinfacht die Erstellung von Entwicklungs- und Produktionsversionen der Images.</span><span class="sxs-lookup"><span data-stu-id="8c471-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="8c471-227">Die Tools sind plattformübergreifend. Durch die Bereitstellung eines PowerShell-Skripts können die gleichen Ergebnisse für Windows und Visual Studio Code erreicht werden mit schrittweisem Debuggen der Anwendung innerhalb des Containers.</span><span class="sxs-lookup"><span data-stu-id="8c471-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="8c471-228">Wenn Sie die Imagevarianten und die Zielszenarios kennen, können Sie Ihre Entwicklungsschleifen verbessern und optimierte Images für Produktionsbereitstellungen erreichen.</span><span class="sxs-lookup"><span data-stu-id="8c471-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



