---
title: Erlernen der Docker-Grundlagen mit .NET Core
description: "Ein Tutorial für die Grundlagen von Docker und .NET Core"
keywords: .NET, .NET Core, Docker, Tutorial
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
ms.workload: dotnetcore
ms.openlocfilehash: 79ded2ce5de5100c18301127a2654f8791b8ed76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="5ab1b-104">Erlernen der Docker-Grundlagen mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="5ab1b-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="5ab1b-105">In diesem Tutorial werden die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung erläutert.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="5ab1b-106">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5ab1b-107">das Erstellen einer Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="5ab1b-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="5ab1b-108">das Erstellen einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="5ab1b-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="5ab1b-109">das Bereitstellen Ihrer App in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="5ab1b-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="5ab1b-110">Die [Docker-Plattform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Engine](https://docs.docker.com/engine/docker-overview/#docker-engine), um Pakete schnell als [Docker-Images](https://docs.docker.com/glossary/?term=image) zu erstellen und zu packen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="5ab1b-111">Diese Images werden im [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)-Format geschrieben, um in einem [mehrstufigen Container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers) bereitgestellt und ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="5ab1b-112">Einfacher Einstieg in .NET Core</span><span class="sxs-lookup"><span data-stu-id="5ab1b-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="5ab1b-113">Bevor Sie ein Docker-Image erstellen, benötigen Sie eine Anwendung, die containerisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="5ab1b-114">Diese können Sie unter Linux, macOS oder Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="5ab1b-115">Die schnellste und einfachste Methode hierfür ist die Verwendung von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="5ab1b-116">Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ab1b-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="5ab1b-117">Sie können Windows- und Linux-Container mit [Tags, die auf mehreren Architekturen basieren](https://github.com/dotnet/announcements/issues/14), erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="5ab1b-118">Ihre erste Docker-App mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="5ab1b-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5ab1b-119">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="5ab1b-119">Prerequisites</span></span>

<span data-ttu-id="5ab1b-120">Zum Abschließen dieses Tutorials benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="5ab1b-121">.NET Core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="5ab1b-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="5ab1b-122">Installieren Sie das [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="5ab1b-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="5ab1b-123">Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="5ab1b-124">Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="5ab1b-125">Benötigen Sie einen Code-Editor?</span><span class="sxs-lookup"><span data-stu-id="5ab1b-125">Need to install a code editor?</span></span> <span data-ttu-id="5ab1b-126">Testen Sie [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="5ab1b-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="5ab1b-127">Installieren des Docker-Clients</span><span class="sxs-lookup"><span data-stu-id="5ab1b-127">Installing Docker Client</span></span>

<span data-ttu-id="5ab1b-128">Installieren Sie den Docker-Client [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="5ab1b-129">Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="5ab1b-130">Linux-Verteilungen</span><span class="sxs-lookup"><span data-stu-id="5ab1b-130">Linux distributions</span></span>

   * [<span data-ttu-id="5ab1b-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="5ab1b-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="5ab1b-132">Debian</span><span class="sxs-lookup"><span data-stu-id="5ab1b-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="5ab1b-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="5ab1b-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="5ab1b-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5ab1b-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="5ab1b-135">macOS</span><span class="sxs-lookup"><span data-stu-id="5ab1b-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="5ab1b-136">[Windows](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="5ab1b-137">Erstellen einer .NET Core 2.0-Konsolen-App für das Bereitstellen in Docker</span><span class="sxs-lookup"><span data-stu-id="5ab1b-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="5ab1b-138">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="5ab1b-139">Navigieren Sie zum erstellten Ordner, und geben Sie folgende Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="5ab1b-140">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="5ab1b-141">Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="5ab1b-142">Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="5ab1b-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="5ab1b-144">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="5ab1b-145">Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="5ab1b-146">Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="5ab1b-147">In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für die angegebenen Frameworks in einem einzigen Vorgang vornehmen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="5ab1b-148">In diesem Tutorial werden Projekte für .NET Core 2.0 erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="5ab1b-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-149">`Program.cs`:</span></span>

   <span data-ttu-id="5ab1b-150">Das Programm wird durch `using System` gestartet.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-150">The program starts by `using System`.</span></span> <span data-ttu-id="5ab1b-151">Diese Anweisung bedeutet: „Alle Elemente im `System`-Namespace müssen in den Bereich dieser Datei gebracht werden.“</span><span class="sxs-lookup"><span data-stu-id="5ab1b-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="5ab1b-152">Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="5ab1b-153">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="5ab1b-154">Sie können den Namespace beliebig ändern.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="5ab1b-155">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="5ab1b-156">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="5ab1b-157">In diesem Beispiel gibt das Programm lediglich „Hallo Welt!“</span><span class="sxs-lookup"><span data-stu-id="5ab1b-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="5ab1b-158">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="5ab1b-159">In .NET Core 2.x wird der [`dotnet restore`](../tools/dotnet-restore.md)-Befehl durch **dotnet new** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="5ab1b-160">Durch **dotnet restore** wird die Struktur der Abhängigkeiten durch einen Aufruf von [NuGet](https://www.nuget.org/) (.NET-Paket-Manager) wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="5ab1b-161">NuGet führt folgende Ausgaben aus:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="5ab1b-162">Analyse der *Hello.csproj*-Datei</span><span class="sxs-lookup"><span data-stu-id="5ab1b-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="5ab1b-163">Download der Abhängigkeiten der Datei (oder Abrufen aus dem Cache des Computers)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="5ab1b-164">Schreiben der *obj/project.assets.json*-Datei</span><span class="sxs-lookup"><span data-stu-id="5ab1b-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="5ab1b-165">Die Datei *project.assets.json* stellt einen vollständigen Satz von App-Metadaten (z.B. Diagramme, Bindungsauflösungen usw.) für NuGet-Abhängigkeiten dar.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="5ab1b-166">Diese Datei wird von anderen Tools wie [`dotnet build`](../tools/dotnet-build.md) und [`dotnet run`](../tools/dotnet-run.md) verwendet, um den Quellcode ordnungsgemäß zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="5ab1b-167">[`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um einen erfolgreichen Build zu bestätigen. Anschließend wird `dotnet <assembly.dll>` aufgerufen, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="5ab1b-168">Weitere Informationen zu erweiterten Szenarios finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ab1b-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="5ab1b-169">Bereitstellen der .NET Core-Anwendung in Docker</span><span class="sxs-lookup"><span data-stu-id="5ab1b-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="5ab1b-170">Die Konsolen-App „Hello .NET Core“ wird erfolgreich lokal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="5ab1b-171">Im nächsten Schritt wird die App in Docker erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="5ab1b-172">Ihre erste Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="5ab1b-172">Your first Dockerfile</span></span>

<span data-ttu-id="5ab1b-173">Öffnen Sie Ihren Text-Editor, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="5ab1b-174">Sie arbeiten weiterhin mit dem Hello-Verzeichnis, in dem die App erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="5ab1b-175">Fügen Sie folgende Docker-Anweisungen für Linux- oder [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) zu einer neuen Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="5ab1b-176">Wenn dieser Vorgang abgeschlossen ist, speichern Sie die Datei ohne Erweiterung im Stammverzeichnis Ihres Hello-Verzeichnisses als **Dockerfile**. Sie müssen den Dateityp möglicherweise auf `All types (*.*)` (oder etwas ähnliches) festlegen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="5ab1b-177">Die Dockerfile-Datei enthält die Buildanweisungen für Docker, die nacheinander ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="5ab1b-178">Die erste Anweisung muss [**FROM**](https://docs.docker.com/engine/reference/builder/#from) sein.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="5ab1b-179">Diese Anweisung initialisiert eine neue Stufe des Builds und legt das Basisimage für die übrigen Anweisungen fest.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="5ab1b-180">Die Tags für mehrere Architekturen pullen abhängig vom [Containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) von Docker für Windows entweder Windows- oder Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="5ab1b-181">Das Basisimage für dieses Beispiel ist „2.0-sdk image“ aus dem Repository „microsoft/dotnet“.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="5ab1b-182">Die [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir)-Anweisung legt das Arbeitsverzeichnis für die übrigen Dockerfile-Anweisungen RUN, CMD, ENTRYPOINT, COPY und ADD fest.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="5ab1b-183">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="5ab1b-184">In diesem Fall ist WORKDIR auf das App-Verzeichnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="5ab1b-185">Die [**COPY**](https://docs.docker.com/engine/reference/builder/#copy)-Anweisung kopiert neue Dateien oder Verzeichnisse aus dem Quellpfad und fügt diese dem Zieldateisystem des Containers hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="5ab1b-186">Mit dieser Anweisung wird die C#-Projektdatei in den Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="5ab1b-187">Die [**RUN**](https://docs.docker.com/engine/reference/builder/#run)-Anweisung führt jeden Befehl in einer neuen Ebene über dem aktuellen Image aus und committet die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="5ab1b-188">Das resultierende committete Image wird im nächsten Schritt in der Dockerdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="5ab1b-189">Führen Sie **dotnet restore** aus, um die erforderlichen Abhängigkeiten der C#-Projektdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="5ab1b-190">Diese **COPY**-Anweisung kopiert die restlichen Dateien in neue [Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) des Containers.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="5ab1b-191">Veröffentlichen Sie die App mit der **RUN**-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="5ab1b-192">Der Befehl [**dotnet publish**](../tools/dotnet-publish.md) kompiliert die Anwendung, liest die Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="5ab1b-193">Die App wird mit einer **Releasekonfiguration** und einer Ausgabe in das Standardverzeichnis veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="5ab1b-194">Die [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint)-Anweisung ermöglicht die Ausführung des Containers als ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="5ab1b-195">Sie verfügen nun über eine Dockerfile-Datei, die:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="5ab1b-196">Ihre App in das Image kopiert</span><span class="sxs-lookup"><span data-stu-id="5ab1b-196">copies your app to the image</span></span>
* <span data-ttu-id="5ab1b-197">die Abhängigkeiten Ihrer App in das Image kopiert</span><span class="sxs-lookup"><span data-stu-id="5ab1b-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="5ab1b-198">die App für die Ausführung als ausführbare Datei erstellt</span><span class="sxs-lookup"><span data-stu-id="5ab1b-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="5ab1b-199">Erstellen und Ausführen der Hello .NET Core 2.0-App</span><span class="sxs-lookup"><span data-stu-id="5ab1b-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="5ab1b-200">Grundlegende Docker-Befehle</span><span class="sxs-lookup"><span data-stu-id="5ab1b-200">Essential Docker commands</span></span>

<span data-ttu-id="5ab1b-201">Diese Docker-Befehle sind grundlegend:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="5ab1b-202">docker build</span><span class="sxs-lookup"><span data-stu-id="5ab1b-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="5ab1b-203">docker run</span><span class="sxs-lookup"><span data-stu-id="5ab1b-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="5ab1b-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="5ab1b-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="5ab1b-205">docker stop</span><span class="sxs-lookup"><span data-stu-id="5ab1b-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="5ab1b-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="5ab1b-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="5ab1b-207">docker rmi</span><span class="sxs-lookup"><span data-stu-id="5ab1b-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="5ab1b-208">docker image</span><span class="sxs-lookup"><span data-stu-id="5ab1b-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="5ab1b-209">Erstellen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="5ab1b-209">Build and run</span></span>

<span data-ttu-id="5ab1b-210">Nachdem Sie die Dockerfile-Datei geschrieben haben, erstellt Docker Ihre App und führt anschließend den Container aus.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="5ab1b-211">Die Ausgabe des `docker build`-Befehls sollte folgender Konsolenausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-211">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="5ab1b-212">Wie Sie an der Ausgabe erkennen können, verwendet die Docker-Engine die Dockerfile-Datei, um Ihren Container zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="5ab1b-213">Die Ausgabe des `docker run`-Befehls sollte folgender Konsolenausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="5ab1b-214">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="5ab1b-214">Congratulations!</span></span> <span data-ttu-id="5ab1b-215">Sie haben gerade:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5ab1b-216">eine lokale .NET Core-App erstellt</span><span class="sxs-lookup"><span data-stu-id="5ab1b-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="5ab1b-217">eine Dockerfile-Datei erstellt, um Ihren ersten Container zu erstellen</span><span class="sxs-lookup"><span data-stu-id="5ab1b-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="5ab1b-218">die in Docker bereitgestellte App erstellt und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="5ab1b-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="5ab1b-219">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5ab1b-219">Next Steps</span></span>

<span data-ttu-id="5ab1b-220">Im Folgenden finden Sie weiterführende Schritte:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="5ab1b-221">Introduction to .NET Docker Images Video(Video: Einführung in .NET-Docker-Images)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="5ab1b-222">Visual Studio, Docker & Azure Container Instances better together! (Wie sich Visual Studio, Docker und Azure Container Instances ergänzen)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="5ab1b-223">Docker for Azure Quickstarts (Docker für Azure-Schnellstarts)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="5ab1b-224">Deploy your app on Docker for Azure (Bereitstellen Ihrer App in Docker für Azure)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="5ab1b-225">Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.</span><span class="sxs-lookup"><span data-stu-id="5ab1b-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="5ab1b-226">In diesem Beispiel verwendete Docker-Images</span><span class="sxs-lookup"><span data-stu-id="5ab1b-226">Docker Images used in this sample</span></span>

<span data-ttu-id="5ab1b-227">Folgende Docker-Images werden in diesem Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="5ab1b-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="5ab1b-228">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5ab1b-228">Related Resources</span></span>

* [<span data-ttu-id="5ab1b-229">.NET Core Docker samples (Docker-Beispiele für .NET Core)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="5ab1b-230">Dockerfile-Datei in Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="5ab1b-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="5ab1b-231">.NET Framework Docker samples (Docker-Beispiele für .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="5ab1b-232">ASP.NET Core auf DockerHub</span><span class="sxs-lookup"><span data-stu-id="5ab1b-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="5ab1b-233">Dockerize a .NET Core application - Docker Tutorial (Docker-Tutorial: Bereitstellen einer .NET Core-Anwendung in Docker)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="5ab1b-234">Arbeiten mit Visual Studio-Tools für Docker</span><span class="sxs-lookup"><span data-stu-id="5ab1b-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="5ab1b-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="5ab1b-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)