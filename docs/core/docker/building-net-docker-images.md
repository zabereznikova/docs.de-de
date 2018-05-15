---
title: Erstellen von .NET Core Docker-Images
description: Grundlegendes zu Docker-Images und .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f539efe15ce68a77890538430a170da64ff325e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="2aed8-103">Erstellen von Docker-Images für .NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2aed8-103">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="2aed8-104">In diesem Tutorial liegt der Schwerpunkt auf der Verwendung von .NET Core in Docker.</span><span class="sxs-lookup"><span data-stu-id="2aed8-104">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="2aed8-105">Zunächst werden die unterschiedlichen Docker-Images erläutert, die von Microsoft angeboten und verwaltet werden, sowie einige Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="2aed8-105">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="2aed8-106">Sie erfahren, wie eine ASP.NET Core-App erstellt und in Docker bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2aed8-106">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="2aed8-107">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2aed8-107">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2aed8-108">Allgemeines zu Docker-Images in Microsoft .NET Core</span><span class="sxs-lookup"><span data-stu-id="2aed8-108">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="2aed8-109">das Abrufen einer ASP.NET Core-Beispiel-App für die Bereitstellung in Docker</span><span class="sxs-lookup"><span data-stu-id="2aed8-109">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="2aed8-110">das lokale Ausführen der ASP.NET-Beispiel-App</span><span class="sxs-lookup"><span data-stu-id="2aed8-110">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="2aed8-111">das Erstellen und Ausführen des Beispiels mit Docker für Linux-Container</span><span class="sxs-lookup"><span data-stu-id="2aed8-111">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="2aed8-112">das Erstellen und Ausführen des Beispiels mit Docker für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="2aed8-112">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="2aed8-113">Docker-Image-Optimierungen</span><span class="sxs-lookup"><span data-stu-id="2aed8-113">Docker Image Optimizations</span></span>

<span data-ttu-id="2aed8-114">Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:</span><span class="sxs-lookup"><span data-stu-id="2aed8-114">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="2aed8-115">Images zum Entwickeln von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="2aed8-115">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="2aed8-116">Images zum Erstellen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="2aed8-116">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="2aed8-117">Images zum Ausführen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="2aed8-117">Images used to run .NET Core apps</span></span>

<span data-ttu-id="2aed8-118">Warum drei Images?</span><span class="sxs-lookup"><span data-stu-id="2aed8-118">Why three images?</span></span>
<span data-ttu-id="2aed8-119">Beim Entwickeln, Erstellen und Ausführen von Containeranwendungen gibt es unterschiedliche Prioritäten.</span><span class="sxs-lookup"><span data-stu-id="2aed8-119">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="2aed8-120">**Entwicklung:** Die Priorität liegt hierbei auf dem schnellen Durchführen von Änderungen sowie auf dem Debuggen der Änderungen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-120">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="2aed8-121">Die Größe des Images ist nicht entscheidend, sondern ob Änderungen am Code vorgenommen und schnell angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="2aed8-121">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="2aed8-122">**Build:** Dieses Image enthält alle Bestandteile, die zum Kompilieren Ihrer App erforderlich sind. Dazu zählen der Compiler und alle anderen Abhängigkeiten, die zum Optimieren der Binärdateien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-122">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="2aed8-123">Sie verwenden das Buildimage zum Erstellen der Objekte, die Sie in einem Produktionsimage platzieren.</span><span class="sxs-lookup"><span data-stu-id="2aed8-123">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="2aed8-124">Dieses Image wird für die Continuous Integration oder in einer Buildumgebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2aed8-124">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="2aed8-125">Dieser Ansatz ermöglicht einem Build-Agent das Kompilieren und Erstellen der Anwendung (mit allen erforderlichen Abhängigkeiten) in einer Instanz des Buildimages.</span><span class="sxs-lookup"><span data-stu-id="2aed8-125">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="2aed8-126">Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2aed8-126">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="2aed8-127">**Produktion:** Wie schnell kann das Image bereitgestellt und gestartet werden?</span><span class="sxs-lookup"><span data-stu-id="2aed8-127">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="2aed8-128">Da dieses Image klein ist, ist die Netzwerkleistung von Ihrer Docker-Registrierung zu Ihren Docker-Hosts ideal.</span><span class="sxs-lookup"><span data-stu-id="2aed8-128">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="2aed8-129">Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-129">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="2aed8-130">Die dynamische Codekompilierung ist im Docker-Modell nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2aed8-130">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="2aed8-131">Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2aed8-131">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="2aed8-132">Die `dotnet publish`-Ausgabe enthält beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="2aed8-132">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="2aed8-133">die kompilierten Binärdateien</span><span class="sxs-lookup"><span data-stu-id="2aed8-133">the compiled binaries</span></span>
    * <span data-ttu-id="2aed8-134">JS- und CSS-Dateien</span><span class="sxs-lookup"><span data-stu-id="2aed8-134">.js and .css files</span></span>


<span data-ttu-id="2aed8-135">Sie sollten die `dotnet publish`-Befehlsausgabe zu Ihrem Produktionsimage hinzufügen, um die Größe so gering wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="2aed8-135">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="2aed8-136">Einige .NET Core-Images geben die Ebenen zwischen verschiedenen Tags frei, sodass es sich beim Herunterladen der aktuellen Tags um einen einfachen Vorgang handelt.</span><span class="sxs-lookup"><span data-stu-id="2aed8-136">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="2aed8-137">Wenn Sie bereits über eine ältere Version auf Ihrem Computer verfügen, verringert diese Architektur den erforderlichen Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="2aed8-137">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="2aed8-138">Wenn mehrere Anwendungen gemeinsame Images auf demselben Computer verwenden, wird der Arbeitsspeicher zwischen den gemeinsamen Images aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="2aed8-138">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="2aed8-139">Hierzu müssen die Images identisch sein.</span><span class="sxs-lookup"><span data-stu-id="2aed8-139">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="2aed8-140">Docker-Image-Varianten</span><span class="sxs-lookup"><span data-stu-id="2aed8-140">Docker image variations</span></span>

<span data-ttu-id="2aed8-141">Zum Erreichen der oben genannten Ziele werden unter [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/) Imagevarianten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2aed8-141">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="2aed8-142">`microsoft/dotnet:<version>-sdk` (`microsoft/dotnet:2.0.0-sdk`) Dieses Image enthält das .NET Core SDK, das die .NET Core- und CLI-Tools (Command Line Interface) enthält.</span><span class="sxs-lookup"><span data-stu-id="2aed8-142">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="2aed8-143">Dieses Image ist dem **Entwicklungsszenario** zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2aed8-143">This image maps to the **development scenario**.</span></span> <span data-ttu-id="2aed8-144">Dieses Image wird für die lokale Entwicklung sowie für das Debuggen und für Komponententests verwendet.</span><span class="sxs-lookup"><span data-stu-id="2aed8-144">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="2aed8-145">Dieses Image kann auch für **Build**-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-145">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="2aed8-146">Mithilfe von `microsoft/dotnet:sdk` können Sie jederzeit die aktuelle Version abrufen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-146">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="2aed8-147">Bei Unsicherheiten bezüglich Ihrer Anforderungen sollten Sie das `microsoft/dotnet:<version>-sdk`-Image verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-147">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="2aed8-148">Es wurde als allgemeines Image entwickelt, um als Basiscontainer (zum Einbinden Ihres Quellcodes und Starten des Containers, um die App zu starten) und als Basisimage zum Erstellen von anderen Images verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-148">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="2aed8-149">`microsoft/dotnet:<version>-runtime`: Dieses Image enthält die .NET Core-Runtime und -Bibliotheken und wurde für das Ausführen von .NET Core-Apps in der **Produktion** optimiert.</span><span class="sxs-lookup"><span data-stu-id="2aed8-149">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="2aed8-150">Alternative Images</span><span class="sxs-lookup"><span data-stu-id="2aed8-150">Alternative images</span></span>

<span data-ttu-id="2aed8-151">Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:</span><span class="sxs-lookup"><span data-stu-id="2aed8-151">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="2aed8-152">`microsoft/dotnet:<version>-runtime-deps`: Das Image **runtime-deps** enthält das Betriebssystem und alle für .NET Core erforderlichen nativen Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="2aed8-152">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="2aed8-153">Dieses Image ist für [eigenständige Anwendungen](../deploying/index.md) vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-153">This image is for [self-contained applications](../deploying/index.md).</span></span>

<span data-ttu-id="2aed8-154">Aktuelle Versionen jeder Variante:</span><span class="sxs-lookup"><span data-stu-id="2aed8-154">Latest versions of each variant:</span></span>

* <span data-ttu-id="2aed8-155">`microsoft/dotnet` oder `microsoft/dotnet:latest` (Alias für das SDK-Image)</span><span class="sxs-lookup"><span data-stu-id="2aed8-155">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="2aed8-156">Hilfreiche Beispiele</span><span class="sxs-lookup"><span data-stu-id="2aed8-156">Samples to explore</span></span>

* <span data-ttu-id="2aed8-157">Dieses [Beispiel zum ASP.NET Core-Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) stellt ein bewährtes Muster für die Erstellung von Docker-Images für ASP.NET Core-Apps für die Produktion vor.</span><span class="sxs-lookup"><span data-stu-id="2aed8-157">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="2aed8-158">Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.</span><span class="sxs-lookup"><span data-stu-id="2aed8-158">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="2aed8-159">In diesem Beispiel für .NET Core-Docker wird ein bewährtes Muster für die [Erstellung von Docker-Images für .NET Core-Apps für die Produktion](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="2aed8-159">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="2aed8-160">Ihre erste Docker-App mit ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2aed8-160">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="2aed8-161">In diesem Beispiel wird eine Docker-Beispielanwendung für ASP.NET-Core für die App verwendet, die in Docker bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2aed8-161">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="2aed8-162">Diese Docker-Beispielanwendung für ASP.NET Core veranschaulicht eine bewährte Methode zum Erstellen von Docker-Images für ASP.NET Core-Apps für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="2aed8-162">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="2aed8-163">Das Beispiel funktioniert sowohl mit Linux- als auch mit Windows-Containern.</span><span class="sxs-lookup"><span data-stu-id="2aed8-163">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="2aed8-164">Die Dockerfile-Beispieldatei erstellt ein Docker-Image einer ASP.NET Core-Anwendung, das auf dem Docker-Basisimage der ASP.NET Core-Runtime basiert.</span><span class="sxs-lookup"><span data-stu-id="2aed8-164">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="2aed8-165">Dieses verwendet das [Docker-Feature für mehrstufige Builds](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) für:</span><span class="sxs-lookup"><span data-stu-id="2aed8-165">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="2aed8-166">das Erstellen des Beispiels in einem Container, der auf dem **größeren** Docker-Basisimage für ASP.NET Core-Builds basiert</span><span class="sxs-lookup"><span data-stu-id="2aed8-166">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="2aed8-167">das Kopieren der finalen Buildergebnisse in ein Docker-Image, das auf dem **kleineren** Docker-Basisimage der ASP.NET Core-Runtime basiert</span><span class="sxs-lookup"><span data-stu-id="2aed8-167">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!NOTE]
> <span data-ttu-id="2aed8-168">Das Buildimage enthält im Gegensatz zum Runtimeimage die erforderlichen Tools zum Erstellen von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-168">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2aed8-169">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="2aed8-169">Prerequisites</span></span>

<span data-ttu-id="2aed8-170">Installieren Sie zum Erstellen und Ausführen folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="2aed8-170">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="2aed8-171">.NET Core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="2aed8-171">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="2aed8-172">Installieren Sie das [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="2aed8-172">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="2aed8-173">Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.</span><span class="sxs-lookup"><span data-stu-id="2aed8-173">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="2aed8-174">Benötigen Sie einen Code-Editor?</span><span class="sxs-lookup"><span data-stu-id="2aed8-174">Need to install a code editor?</span></span> <span data-ttu-id="2aed8-175">Testen Sie [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="2aed8-175">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="2aed8-176">Installieren des Docker-Clients</span><span class="sxs-lookup"><span data-stu-id="2aed8-176">Installing Docker Client</span></span>

<span data-ttu-id="2aed8-177">Installieren Sie den Docker-Client [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher.</span><span class="sxs-lookup"><span data-stu-id="2aed8-177">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="2aed8-178">Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="2aed8-178">The Docker client can be installed in:</span></span>

* <span data-ttu-id="2aed8-179">Linux-Verteilungen</span><span class="sxs-lookup"><span data-stu-id="2aed8-179">Linux distributions</span></span>

   * [<span data-ttu-id="2aed8-180">CentOS</span><span class="sxs-lookup"><span data-stu-id="2aed8-180">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="2aed8-181">Debian</span><span class="sxs-lookup"><span data-stu-id="2aed8-181">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="2aed8-182">Fedora</span><span class="sxs-lookup"><span data-stu-id="2aed8-182">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="2aed8-183">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2aed8-183">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="2aed8-184">macOS</span><span class="sxs-lookup"><span data-stu-id="2aed8-184">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="2aed8-185">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="2aed8-185">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="2aed8-186">Installieren von Git für Beispielrepositorys</span><span class="sxs-lookup"><span data-stu-id="2aed8-186">Installing Git for sample repository</span></span>

* <span data-ttu-id="2aed8-187">Installieren Sie [Git](https://git-scm.com/download), wenn Sie das Repository klonen möchten.</span><span class="sxs-lookup"><span data-stu-id="2aed8-187">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="2aed8-188">Abrufen der Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="2aed8-188">Getting the sample application</span></span>

<span data-ttu-id="2aed8-189">Sie können das Beispiel am einfachsten abrufen, indem Sie mithilfe der folgenden Anweisungen das [Beispielrepository](https://github.com/dotnet/dotnet-docker-samples) mit Git klonen:</span><span class="sxs-lookup"><span data-stu-id="2aed8-189">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="2aed8-190">Sie können das Repository ebenfalls als ZIP-Datei (die Datei ist klein) vom Docker-Beispielrepository für .NET Core herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-190">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="2aed8-191">Lokales Ausführen der ASP.NET-App</span><span class="sxs-lookup"><span data-stu-id="2aed8-191">Run the ASP.NET app locally</span></span>

<span data-ttu-id="2aed8-192">Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus.</span><span class="sxs-lookup"><span data-stu-id="2aed8-192">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="2aed8-193">Sie können die Anwendung mithilfe des .NET Core 2.0 SDK lokal erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):</span><span class="sxs-lookup"><span data-stu-id="2aed8-193">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="2aed8-194">Rufen Sie nach dem Starten der Anwendung **http://localhost:5000** im Webbrowser auf.</span><span class="sxs-lookup"><span data-stu-id="2aed8-194">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="2aed8-195">das Erstellen und Ausführen des Beispiels mit Docker für Linux-Container</span><span class="sxs-lookup"><span data-stu-id="2aed8-195">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="2aed8-196">Sie können das Beispiel in Docker mit Linux-Containern erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):</span><span class="sxs-lookup"><span data-stu-id="2aed8-196">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> <span data-ttu-id="2aed8-197">Das `docker run`-Argument „-p“ ordnet Port 5000 auf Ihrem lokalen Computer zu Port 80 im Container zu (das Format für die Zuordnung von Ports lautet `host:container`).</span><span class="sxs-lookup"><span data-stu-id="2aed8-197">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="2aed8-198">Weitere Informationen finden Sie unter den Befehlszeilenparametern in der Referenz zu [docker run](https://docs.docker.com/engine/reference/commandline/exec/).</span><span class="sxs-lookup"><span data-stu-id="2aed8-198">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="2aed8-199">Rufen Sie nach dem Starten der Anwendung **http://localhost:5000** im Webbrowser auf.</span><span class="sxs-lookup"><span data-stu-id="2aed8-199">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="2aed8-200">das Erstellen und Ausführen des Beispiels mit Docker für Windows-Container</span><span class="sxs-lookup"><span data-stu-id="2aed8-200">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="2aed8-201">Sie können das Beispiel in Docker mit Windows-Containern erstellen und ausführen, indem Sie folgende Befehle verwenden (die Anweisungen gehen vom Stamm des Repositorys aus):</span><span class="sxs-lookup"><span data-stu-id="2aed8-201">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="2aed8-202">Sie müssen direkt in Ihrem Browser zur **IP-Adresse des Containers** navigieren (im Gegensatz zu http://localhost)), wenn Sie Windows-Container verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-202">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="2aed8-203">Sie können die IP-Adresse Ihres Containers abrufen, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2aed8-203">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="2aed8-204">Öffnen Sie eine weitere Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="2aed8-204">Open up another command prompt.</span></span>
* <span data-ttu-id="2aed8-205">Führen Sie `docker ps` aus, um Ihre ausgeführten Container anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-205">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="2aed8-206">Der Container „aspnetcore_sample“ sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2aed8-206">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="2aed8-207">Führen Sie aus `docker exec aspnetcore_sample ipconfig`.</span><span class="sxs-lookup"><span data-stu-id="2aed8-207">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="2aed8-208">Kopieren Sie die IP-Adresse des Containers (z.B. 172.29.245.43), und fügen Sie diese in Ihrem Browser ein.</span><span class="sxs-lookup"><span data-stu-id="2aed8-208">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!NOTE]
> <span data-ttu-id="2aed8-209">„docker exec“ identifiziert Container per Name oder Hash.</span><span class="sxs-lookup"><span data-stu-id="2aed8-209">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="2aed8-210">In diesem Beispiel wird der Name (aspnetcore_sample) verwendet.</span><span class="sxs-lookup"><span data-stu-id="2aed8-210">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="2aed8-211">Im folgenden Beispiel wird dargestellt, wie Sie die IP-Adresse eines ausgeführten Windows-Containers abrufen können.</span><span class="sxs-lookup"><span data-stu-id="2aed8-211">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!NOTE]
> <span data-ttu-id="2aed8-212">„docker exec“ führt einen neuen Befehl in einem ausgeführten Container aus.</span><span class="sxs-lookup"><span data-stu-id="2aed8-212">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="2aed8-213">Weitere Informationen finden Sie unter den Befehlszeilenparametern in der [Referenz zu docker exec](https://docs.docker.com/engine/reference/commandline/exec/).</span><span class="sxs-lookup"><span data-stu-id="2aed8-213">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="2aed8-214">Sie können eine Anwendung, die für die Produktion bereitgestellt werden kann, lokal mithilfe des Befehls [dotnet publish](../tools/dotnet-publish.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-214">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!NOTE]
> <span data-ttu-id="2aed8-215">Das Argument „-c release“ erstellt die Anwendung im Releasemodus (der Standardwert ist der Debugmodus).</span><span class="sxs-lookup"><span data-stu-id="2aed8-215">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="2aed8-216">Weitere Informationen finden Sie unter den Befehlszeilenparametern in der [Referenz zu dotnet run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="2aed8-216">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="2aed8-217">Sie können die Anwendung mithilfe des folgenden Befehls unter **Windows** ausführen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-217">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="2aed8-218">Sie können die Anwendung mithilfe des folgenden Befehls unter **Linux** oder **macOS** ausführen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-218">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="2aed8-219">In diesem Beispiel verwendete Docker-Images</span><span class="sxs-lookup"><span data-stu-id="2aed8-219">Docker Images used in this sample</span></span>

<span data-ttu-id="2aed8-220">Folgende Docker-Images werden in diesem Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="2aed8-220">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="2aed8-221">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="2aed8-221">Congratulations!</span></span> <span data-ttu-id="2aed8-222">Sie haben gerade:</span><span class="sxs-lookup"><span data-stu-id="2aed8-222">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2aed8-223">Allgemeines zu Docker-Images in Microsoft .NET Core erfahren</span><span class="sxs-lookup"><span data-stu-id="2aed8-223">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="2aed8-224">eine ASP.NET Core-Beispiel-App für die Bereitstellung in Docker abgerufen</span><span class="sxs-lookup"><span data-stu-id="2aed8-224">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="2aed8-225">die ASP.NET-Beispiel-App lokal ausgeführt</span><span class="sxs-lookup"><span data-stu-id="2aed8-225">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="2aed8-226">das Beispiel mit Docker für Linux-Container erstellt und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="2aed8-226">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="2aed8-227">das Beispiel mit Docker für Windows-Container erstellt und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="2aed8-227">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="2aed8-228">**Nächste Schritte**</span><span class="sxs-lookup"><span data-stu-id="2aed8-228">**Next Steps**</span></span>

<span data-ttu-id="2aed8-229">Im Folgenden finden Sie weiterführende Schritte:</span><span class="sxs-lookup"><span data-stu-id="2aed8-229">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="2aed8-230">Arbeiten mit Visual Studio-Tools für Docker</span><span class="sxs-lookup"><span data-stu-id="2aed8-230">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="2aed8-231">Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="2aed8-231">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="2aed8-232">Debuggen mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2aed8-232">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="2aed8-233">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud (Erste Schritte mit Visual Studio für Mac, Container und serverlose Code in der Cloud)</span><span class="sxs-lookup"><span data-stu-id="2aed8-233">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="2aed8-234">Erste Schritte mit Docker und Visual Studio für Mac – Übung</span><span class="sxs-lookup"><span data-stu-id="2aed8-234">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!NOTE]
> <span data-ttu-id="2aed8-235">Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.</span><span class="sxs-lookup"><span data-stu-id="2aed8-235">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
