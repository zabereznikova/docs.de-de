---
title: Erstellen von .NET Core Docker-Images
description: Grundlegendes zu Docker-Images und .NET Core
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="d2639-104">Erstellen von Docker-Images für .NET Core-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d2639-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="d2639-105">In diesem Lernprogramm liegt der Schwerpunkt auf wie .NET Core in Docker verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2639-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="d2639-106">Zunächst untersuchen wir die verschiedenen Docker-Images bereitgestellt und verwaltet von Microsoft und Anwendungsfälle.</span><span class="sxs-lookup"><span data-stu-id="d2639-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="d2639-107">Wir Informationen klicken Sie dann zum Erstellen und dockerize eine ASP.NET Core-app.</span><span class="sxs-lookup"><span data-stu-id="d2639-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="d2639-108">Im Verlauf dieses Lernprogramms erfahren Sie:</span><span class="sxs-lookup"><span data-stu-id="d2639-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d2639-109">Erfahren Sie mehr über Microsoft .NET Core Docker-images</span><span class="sxs-lookup"><span data-stu-id="d2639-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="d2639-110">Abrufen einer ASP.NET Core Beispiel-app zu Dockerize</span><span class="sxs-lookup"><span data-stu-id="d2639-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="d2639-111">Der ASP.NET-beispielanwendung lokal ausführen</span><span class="sxs-lookup"><span data-stu-id="d2639-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="d2639-112">Erstellen Sie und führen Sie das Beispiel für Linux-Containern mit Docker</span><span class="sxs-lookup"><span data-stu-id="d2639-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="d2639-113">Erstellen Sie und führen Sie das Beispiel mit Docker für Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="d2639-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="d2639-114">Docker-Image-Optimierungen</span><span class="sxs-lookup"><span data-stu-id="d2639-114">Docker Image Optimizations</span></span>

<span data-ttu-id="d2639-115">Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:</span><span class="sxs-lookup"><span data-stu-id="d2639-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="d2639-116">Images zum Entwickeln von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="d2639-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="d2639-117">Images zum Erstellen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="d2639-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="d2639-118">Images zum Ausführen von .NET Core-Apps</span><span class="sxs-lookup"><span data-stu-id="d2639-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="d2639-119">Warum drei Images?</span><span class="sxs-lookup"><span data-stu-id="d2639-119">Why three images?</span></span>
<span data-ttu-id="d2639-120">Beim Entwickeln, erstellen und Ausführen von Sammelartikeleinheit, haben wir die unterschiedliche Prioritäten.</span><span class="sxs-lookup"><span data-stu-id="d2639-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="d2639-121">**Entwicklung:** der Priorität konzentriert sich auf Änderungen und die Fähigkeit zum Debuggen der Änderungen schnell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d2639-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="d2639-122">Nicht die Größe des Bilds wird so wichtig ist, sondern können Sie Änderungen am Code vornehmen und schnell?</span><span class="sxs-lookup"><span data-stu-id="d2639-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="d2639-123">**Build:** dieses Image enthält alles, was zum Kompilieren der app, die der Compiler und alle anderen Abhängigkeiten zur Optimierung der Binärdateien umfasst benötigen.</span><span class="sxs-lookup"><span data-stu-id="d2639-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="d2639-124">Sie verwenden das Build-Image, um Objekte zu erstellen, die Sie in einer Produktions-Bild platzieren.</span><span class="sxs-lookup"><span data-stu-id="d2639-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="d2639-125">Das Image Build würde für die fortlaufende Integration oder in einer Buildumgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2639-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="d2639-126">Dieser Ansatz ermöglicht, einen Build-Agent zum Kompilieren und erstellen Sie die Anwendung (mit allen erforderlichen Abhängigkeiten) in einem Build bildinstanz.</span><span class="sxs-lookup"><span data-stu-id="d2639-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="d2639-127">Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d2639-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="d2639-128">**Produktion:** wie schnell Sie bereitstellen und starten Sie das Abbild?</span><span class="sxs-lookup"><span data-stu-id="d2639-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="d2639-129">Dieses Image ist klein, damit die Leistung des Netzwerks aus der Docker-Registrierung für die Docker-Hosts optimiert ist.</span><span class="sxs-lookup"><span data-stu-id="d2639-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="d2639-130">Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="d2639-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="d2639-131">Dynamischen Codekompilierung ist nicht in der Docker-Modell erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d2639-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="d2639-132">Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d2639-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="d2639-133">Z. B. die `dotnet publish` Ausgabe enthält:</span><span class="sxs-lookup"><span data-stu-id="d2639-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="d2639-134">die kompilierten Binärdateien</span><span class="sxs-lookup"><span data-stu-id="d2639-134">the compiled binaries</span></span>
    * <span data-ttu-id="d2639-135">js und CSS-Dateien</span><span class="sxs-lookup"><span data-stu-id="d2639-135">.js and .css files</span></span>


<span data-ttu-id="d2639-136">Der Grund für das Schließen der `dotnet publish` Ausgabe des Befehls in die Produktion Abbildung ist die Beibehaltung seiner "Größe auf ein Minimum.</span><span class="sxs-lookup"><span data-stu-id="d2639-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="d2639-137">Einige .NET Core-Abbilder freigeben Ebenen zwischen verschiedenen Tags damit Herunterladen der neuesten Tags eine relativ einfache Prozess ist.</span><span class="sxs-lookup"><span data-stu-id="d2639-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="d2639-138">Wenn Sie bereits über eine ältere Version auf dem Computer verfügen, verringert diese Architektur des erforderlichen Speicherplatzes.</span><span class="sxs-lookup"><span data-stu-id="d2639-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="d2639-139">Wenn mehrere Anwendungen allgemeine Images auf dem gleichen Computer verwenden, ist die allgemeine Bilder Arbeitsspeicher freigegeben.</span><span class="sxs-lookup"><span data-stu-id="d2639-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="d2639-140">Die Bilder müssen die weiterzuleitenden identisch sein.</span><span class="sxs-lookup"><span data-stu-id="d2639-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="d2639-141">Docker-Image-Varianten</span><span class="sxs-lookup"><span data-stu-id="d2639-141">Docker image variations</span></span>

<span data-ttu-id="d2639-142">Um die oben aufgeführten Ziele zu erreichen, bieten wir Image Varianten unter [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="d2639-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="d2639-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Dieses Image enthält .NET Core SDK, das die .NET Core und über die Befehlszeile Tools (CLI) enthält.</span><span class="sxs-lookup"><span data-stu-id="d2639-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="d2639-144">Dieses Image ist dem **Entwicklungsszenario** zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d2639-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="d2639-145">Verwenden Sie dieses Image für lokale Entwicklung, Debuggen und Komponententests.</span><span class="sxs-lookup"><span data-stu-id="d2639-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="d2639-146">Dieses Image kann auch für **Build**-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2639-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="d2639-147">Mithilfe von `microsoft/dotnet:sdk` erhalten Sie immer die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="d2639-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="d2639-148">Wenn Sie über Ihren Anforderungen nicht sicher sind, möchten Sie verwenden die `microsoft/dotnet:<version>-sdk` Bild.</span><span class="sxs-lookup"><span data-stu-id="d2639-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="d2639-149">Als "de facto"-Image, es wurde entwickelt, als ein Throw verwendet werden soll beseitigen Container (Quellcode bereitgestellt, und starten Sie den Container aus, um die app zu starten), und als Basis-Image zum Erstellen von anderen Bildern aus.</span><span class="sxs-lookup"><span data-stu-id="d2639-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="d2639-150">`microsoft/dotnet:<version>-runtime`: Dieses Image enthält die .NET Core (Common Language Runtime und Bibliotheken) und ist optimiert für die Ausführung von .NET Core-apps in **Produktion**.</span><span class="sxs-lookup"><span data-stu-id="d2639-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="d2639-151">Alternative Images</span><span class="sxs-lookup"><span data-stu-id="d2639-151">Alternative images</span></span>

<span data-ttu-id="d2639-152">Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:</span><span class="sxs-lookup"><span data-stu-id="d2639-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="d2639-153">`microsoft/dotnet:<version>-runtime-deps`: Der **Runtime Einzahlgn** Abbild enthält das Betriebssystem mit alle systemeigenen Abhängigkeiten von .NET Core benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2639-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="d2639-154">Dieses Image ist für [eigenständige Anwendungen](https://docs.microsoft.com/dotnet/core/deploying/index).</span><span class="sxs-lookup"><span data-stu-id="d2639-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="d2639-155">Aktuelle Versionen jeder Variante:</span><span class="sxs-lookup"><span data-stu-id="d2639-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="d2639-156">`microsoft/dotnet`oder `microsoft/dotnet:latest` (Alias für das SDK-Image)</span><span class="sxs-lookup"><span data-stu-id="d2639-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="d2639-157">Beispiele zum Durchsuchen</span><span class="sxs-lookup"><span data-stu-id="d2639-157">Samples to explore</span></span>

* <span data-ttu-id="d2639-158">[In diesem Beispiel ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) veranschaulicht ein best Practice-Muster für die Erstellung von Docker-Abbilder für ASP.NET Core apps für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="d2639-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="d2639-159">Das Beispiel funktioniert mit Linux und Windows-Containern.</span><span class="sxs-lookup"><span data-stu-id="d2639-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="d2639-160">Diese .NET Core Docker demonstriert eine best Practice-Muster für [Docker-Images für .NET Core-apps für die Produktion zu erstellen.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="d2639-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="d2639-161">Ihre erste ASP.NET Core Docker-app</span><span class="sxs-lookup"><span data-stu-id="d2639-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="d2639-162">Für dieses Lernprogramm können eine ASP.NET Core Docker-beispielanwendung für die app verwenden wir dockerize möchten.</span><span class="sxs-lookup"><span data-stu-id="d2639-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="d2639-163">Diese beispielanwendung für ASP.NET Core Docker veranschaulicht ein best Practice-Muster für die Erstellung von Docker-Abbilder für ASP.NET Core apps für die Produktion.</span><span class="sxs-lookup"><span data-stu-id="d2639-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="d2639-164">Das Beispiel funktioniert mit Linux und Windows-Containern.</span><span class="sxs-lookup"><span data-stu-id="d2639-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="d2639-165">Im Beispiel dockerfile-Datei wird ein ASP.NET Core Docker anwendungsimage basierend auf ASP.NET Core Runtime Docker-Basis-Image erstellt.</span><span class="sxs-lookup"><span data-stu-id="d2639-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="d2639-166">Er verwendet die [mehrstufiger Docker build Funktion](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) an:</span><span class="sxs-lookup"><span data-stu-id="d2639-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="d2639-167">Erstellen Sie das Beispiel in einem Container auf Grundlage der **größere** ASP.NET Core erstellen Docker-Basis-Image</span><span class="sxs-lookup"><span data-stu-id="d2639-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="d2639-168">kopiert das Ergebnis des letzten Builds in ein Docker Bild auf der Grundlage der **kleinere** ASP.NET Core Docker-Laufzeit-Basis-Image</span><span class="sxs-lookup"><span data-stu-id="d2639-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="d2639-169">Der Build-Image enthält erforderlichen Tools zum Erstellen von Anwendungen, während der Laufzeit-Image nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="d2639-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d2639-170">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="d2639-170">Prerequisites</span></span>

<span data-ttu-id="d2639-171">Zum Erstellen und ausführen, installieren Sie die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="d2639-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="d2639-172">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="d2639-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="d2639-173">Installieren Sie [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="d2639-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="d2639-174">Installieren Sie Ihre bevorzugten Code-Editor, sofern Sie noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="d2639-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="d2639-175">Zum Installieren von eines Code-Editors erforderlich?</span><span class="sxs-lookup"><span data-stu-id="d2639-175">Need to install a code editor?</span></span> <span data-ttu-id="d2639-176">Wiederholen Sie den [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="d2639-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="d2639-177">Installieren von Docker-Client</span><span class="sxs-lookup"><span data-stu-id="d2639-177">Installing Docker Client</span></span>

<span data-ttu-id="d2639-178">Installieren Sie [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher des Docker-Clients.</span><span class="sxs-lookup"><span data-stu-id="d2639-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="d2639-179">In kann der Docker-Client installiert werden:</span><span class="sxs-lookup"><span data-stu-id="d2639-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="d2639-180">Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="d2639-180">Linux distributions</span></span>

   * [<span data-ttu-id="d2639-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="d2639-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="d2639-182">Debian</span><span class="sxs-lookup"><span data-stu-id="d2639-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="d2639-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="d2639-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="d2639-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="d2639-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="d2639-185">macOS</span><span class="sxs-lookup"><span data-stu-id="d2639-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="d2639-186">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="d2639-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="d2639-187">Installieren Git für die beispielrepository</span><span class="sxs-lookup"><span data-stu-id="d2639-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="d2639-188">Installieren Sie [Git](https://git-scm.com/download) Wenn Sie das Repository klonen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2639-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="d2639-189">Abrufen der beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="d2639-189">Getting the sample application</span></span>

<span data-ttu-id="d2639-190">Die einfachste Möglichkeit zum Abrufen des Beispiels wird durch das Klonen der [beispielrepository](https://github.com/dotnet/dotnet-docker-samples) mit Git, verwenden Sie die folgenden Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="d2639-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="d2639-191">Sie können auch das Repository (er ist klein) herunterladen, als eine ZIP-Datei aus dem beispielrepository .NET Core Docker.</span><span class="sxs-lookup"><span data-stu-id="d2639-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="d2639-192">Die ASP.NET app lokal ausführen</span><span class="sxs-lookup"><span data-stu-id="d2639-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="d2639-193">Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus.</span><span class="sxs-lookup"><span data-stu-id="d2639-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="d2639-194">Sie können erstellen und führen Sie die Anwendung lokal mit dem .NET Core 2.0 SDK mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):</span><span class="sxs-lookup"><span data-stu-id="d2639-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="d2639-195">Nachdem die Anwendung gestartet wird, besuchen Sie **http://localhost: 5000** in Ihrem Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="d2639-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="d2639-196">Erstellen Sie und führen Sie das Beispiel für Linux-Containern mit Docker</span><span class="sxs-lookup"><span data-stu-id="d2639-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="d2639-197">Sie können erstellen und führen Sie das Beispiel in Docker mithilfe von Linux-Container mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):</span><span class="sxs-lookup"><span data-stu-id="d2639-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="d2639-198">Die `docker run` "-p"-Argument Maps port 5000 auf dem lokalen Computer an Port 80 im Container (Port Zuordnung ist `host:container`).</span><span class="sxs-lookup"><span data-stu-id="d2639-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="d2639-199">Weitere Informationen finden Sie unter der ["Docker run"](https://docs.docker.com/engine/reference/commandline/exec/) Verweis auf Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="d2639-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="d2639-200">Nachdem die Anwendung gestartet wird, besuchen Sie **http://localhost: 5000** in Ihrem Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="d2639-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="d2639-201">Erstellen Sie und führen Sie das Beispiel mit Docker für Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="d2639-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="d2639-202">Sie können erstellen und führen Sie das Beispiel in Docker mithilfe von Windows-Container mit den folgenden Befehlen (die Anweisungen gehen davon aus den Stamm des Repositorys):</span><span class="sxs-lookup"><span data-stu-id="d2639-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="d2639-203">Sie müssen zu navigieren, die **Container IP-Adresse** (im Gegensatz zu http://localhost) in Ihrem Browser direkt bei Verwendung der Windows-Containern.</span><span class="sxs-lookup"><span data-stu-id="d2639-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="d2639-204">Sie erhalten die IP-Adresse des Containers mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="d2639-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="d2639-205">Öffnen Sie eine andere Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="d2639-205">Open up another command prompt.</span></span>
* <span data-ttu-id="d2639-206">Führen Sie `docker ps` auf Ihre ausgeführten Container angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2639-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="d2639-207">Der Container "Aspnetcore_sample" sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2639-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="d2639-208">Führen Sie `docker exec aspnetcore_sample ipconfig` aus.</span><span class="sxs-lookup"><span data-stu-id="d2639-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="d2639-209">Kopieren Sie die Container-IP-Adresse ein, und fügen Sie in Ihrem Browser (z. B. 172.29.245.43).</span><span class="sxs-lookup"><span data-stu-id="d2639-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="d2639-210">Docker Exec unterstützt identifizierende Container mit dem Namen "oder" Hash.</span><span class="sxs-lookup"><span data-stu-id="d2639-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="d2639-211">In unserem Beispiel wird der Name (Aspnetcore_sample) verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2639-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="d2639-212">Sehen Sie im folgenden Beispiel des Abrufs der IP-Adresse von ausgeführten Windows-Container.</span><span class="sxs-lookup"><span data-stu-id="d2639-212">See the following example of how to get the IP address of a running Windows container.</span></span>

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

> [!Note]
> <span data-ttu-id="d2639-213">Docker Exec führt einen neuen Befehl in einem ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="d2639-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="d2639-214">Weitere Informationen finden Sie unter der [Referenz zu Docker Exec](https://docs.docker.com/engine/reference/commandline/exec/) auf Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="d2639-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="d2639-215">Sie können eine Anwendung, die bereit für die Bereitstellung bis hin zur Produktion, die lokal mithilfe von erzeugen die [Dotnet veröffentlichen](../tools/dotnet-publish.md) Befehl.</span><span class="sxs-lookup"><span data-stu-id="d2639-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="d2639-216">Arguments - C Release wird die Anwendung im Releasemodus (der Standardwert ist Debug-Modus).</span><span class="sxs-lookup"><span data-stu-id="d2639-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="d2639-217">Weitere Informationen finden Sie unter der [Dotnet Referenz run](../tools/dotnet-run.md) auf Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="d2639-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="d2639-218">Führen Sie die Anwendung auf **Windows** mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="d2639-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="d2639-219">Führen Sie die Anwendung auf **Linux** oder **MacOS** mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="d2639-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="d2639-220">In diesem Beispiel verwendete Docker-Images</span><span class="sxs-lookup"><span data-stu-id="d2639-220">Docker Images used in this sample</span></span>

<span data-ttu-id="d2639-221">In diesem Beispiel werden die folgenden Docker-Images verwendet.</span><span class="sxs-lookup"><span data-stu-id="d2639-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="d2639-222">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="d2639-222">Congratulations!</span></span> <span data-ttu-id="d2639-223">Sie haben soeben:</span><span class="sxs-lookup"><span data-stu-id="d2639-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d2639-224">Microsoft .NET Core Docker Images gelernt</span><span class="sxs-lookup"><span data-stu-id="d2639-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="d2639-225">Erhalten eine ASP.NET Core Beispiel-app zu Dockerize</span><span class="sxs-lookup"><span data-stu-id="d2639-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="d2639-226">Wurde der ASP.NET-beispielanwendung lokal ausgeführt</span><span class="sxs-lookup"><span data-stu-id="d2639-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="d2639-227">Erstellt und die Ausführung des Beispiels mit Docker für Linux-Container</span><span class="sxs-lookup"><span data-stu-id="d2639-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="d2639-228">Erstellt und im Beispiel mit Docker für Windows-Container ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d2639-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="d2639-229">**Nächste Schritte**</span><span class="sxs-lookup"><span data-stu-id="d2639-229">**Next Steps**</span></span>

<span data-ttu-id="d2639-230">Hier sind die nächsten Schritte, die Sie ergreifen können:</span><span class="sxs-lookup"><span data-stu-id="d2639-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="d2639-231">Arbeiten mit Docker-Tools für Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d2639-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="d2639-232">Bereitstellen von Docker-Images aus der Registrierung des Azure-Container für Instanzen von Azure-Container</span><span class="sxs-lookup"><span data-stu-id="d2639-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="d2639-233">Debuggen mit Visual Studio-Code</span><span class="sxs-lookup"><span data-stu-id="d2639-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="d2639-234">Beim Abrufen der Hände für mit Visual Studio für Mac, Container und serverlose Code in der cloud</span><span class="sxs-lookup"><span data-stu-id="d2639-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="d2639-235">Erste Schritte mit Docker und Visual Studio für Mac-Lab</span><span class="sxs-lookup"><span data-stu-id="d2639-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="d2639-236">Wenn Sie nicht über ein Azure-Abonnement verfügen [registrieren Sie sich noch heute](https://azure.microsoft.com/free/?b=16.48) für eine kostenlose 30-Tage-Konto verhindern und $200 Azure-Guthaben auf eine beliebige Kombination von Azure-Dienste zu testen.</span><span class="sxs-lookup"><span data-stu-id="d2639-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
