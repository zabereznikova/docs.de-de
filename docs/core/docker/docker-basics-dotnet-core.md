---
title: Erlernen von Grundlagen der Docker mit .NET Core
description: Ein Docker und .NET Core-Lernprogramm
keywords: .NET, .NET Core, Docker, Lernprogramm
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
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="6f3d2-104">Erlernen von Grundlagen der Docker mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="6f3d2-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="6f3d2-105">Dieses Lernprogramm vermittelt die Docker Container erstellen und Bereitstellen von Aufgaben für eine Anwendung .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="6f3d2-106">Im Verlauf dieses Lernprogramms erfahren Sie:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="6f3d2-107">Vorgehensweise: Erstellen Sie eine dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="6f3d2-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="6f3d2-108">Vorgehensweise: erstellen eine .NET Core-app.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="6f3d2-109">Zum Bereitstellen Ihrer app in einem Docker-Container.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="6f3d2-110">Die [die Plattform Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Modul](https://docs.docker.com/engine/docker-overview/#docker-engine) schnell erstellen und die Paket-apps als [Docker Images](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="6f3d2-111">Diese Abbilder werden geschrieben, der [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) Format bereitgestellt werden, und führen Sie in einer [Container in den Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="6f3d2-112">.NET Core: Die einfachste Möglichkeit für den Einstieg</span><span class="sxs-lookup"><span data-stu-id="6f3d2-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="6f3d2-113">Vor der Erstellung der Docker-Abbilds, benötigen Sie eine Anwendung containerize.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="6f3d2-114">Sie können es unter Linux, Mac OS oder Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="6f3d2-115">Die schnellste und einfachste Möglichkeit hierzu ist die Verwendung von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="6f3d2-116">Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="6f3d2-117">Sie können die Windows- und Linux-Containern mit erstellen [mit mehreren Arch basierend Tags](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="6f3d2-118">Die erste .NET Core Docker-app</span><span class="sxs-lookup"><span data-stu-id="6f3d2-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6f3d2-119">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="6f3d2-119">Prerequisites</span></span>

<span data-ttu-id="6f3d2-120">Um dieses Lernprogramm abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="6f3d2-121">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="6f3d2-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="6f3d2-122">Installieren Sie [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="6f3d2-123">Unter [.NET Core 2.x Supported OS Versions (Von .NET Core 2.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.x unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="6f3d2-124">Installieren Sie Ihre bevorzugten Code-Editor, sofern Sie noch nicht geschehen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="6f3d2-125">Zum Installieren von eines Code-Editors erforderlich?</span><span class="sxs-lookup"><span data-stu-id="6f3d2-125">Need to install a code editor?</span></span> <span data-ttu-id="6f3d2-126">Wiederholen Sie den [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="6f3d2-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="6f3d2-127">Installieren von Docker-Client</span><span class="sxs-lookup"><span data-stu-id="6f3d2-127">Installing Docker Client</span></span>

<span data-ttu-id="6f3d2-128">Installieren Sie [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) oder höher des Docker-Clients.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="6f3d2-129">In kann der Docker-Client installiert werden:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="6f3d2-130">Linux-Distributionen</span><span class="sxs-lookup"><span data-stu-id="6f3d2-130">Linux distributions</span></span>

   * [<span data-ttu-id="6f3d2-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="6f3d2-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="6f3d2-132">Debian</span><span class="sxs-lookup"><span data-stu-id="6f3d2-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="6f3d2-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="6f3d2-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="6f3d2-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f3d2-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="6f3d2-135">macOS</span><span class="sxs-lookup"><span data-stu-id="6f3d2-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="6f3d2-136">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="6f3d2-137">Erstellen einer Konsolen-app von .NET Core 2.0 für Dockerization</span><span class="sxs-lookup"><span data-stu-id="6f3d2-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="6f3d2-138">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="6f3d2-139">Navigieren Sie zu dem Ordner, den Sie erstellt haben, und geben Sie die folgenden Befehle:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="6f3d2-140">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="6f3d2-141">Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="6f3d2-142">Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="6f3d2-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="6f3d2-144">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="6f3d2-145">Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="6f3d2-146">Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="6f3d2-147">In einem erweiterten Szenario können Sie mehrere Zielframeworks angeben und auf den angegebenen Frameworks in einem einzigen Vorgang erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="6f3d2-148">In diesem Lernprogramm erstellen wir für .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="6f3d2-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-149">`Program.cs`:</span></span>

   <span data-ttu-id="6f3d2-150">Das Programm gestartet wird, indem Sie `using System`.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-150">The program starts by `using System`.</span></span> <span data-ttu-id="6f3d2-151">Diese Aussage beinhaltet, "schalten Sie alle Elemente in der `System` Namespace in den Bereich für diese Datei."</span><span class="sxs-lookup"><span data-stu-id="6f3d2-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="6f3d2-152">Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="6f3d2-153">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="6f3d2-154">Sie können auf einen gewünschten, Namespace ändern.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="6f3d2-155">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="6f3d2-156">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="6f3d2-157">In unserem Beispiel schreibt das Programm nur "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6f3d2-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="6f3d2-158">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="6f3d2-159">In .NET Core 2.x, **Dotnet neue** führt die [ `dotnet restore` ](../tools/dotnet-restore.md) Befehl.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="6f3d2-160">**Dotnet Wiederherstellung** stellt die Struktur von Abhängigkeiten mit einer [NuGet](https://www.nuget.org/)Aufruf (.NET Paket-Manager).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="6f3d2-161">NuGet führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="6f3d2-162">analysiert die *Hello.csproj* Datei</span><span class="sxs-lookup"><span data-stu-id="6f3d2-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="6f3d2-163">Download der Datei Abhängigkeiten (oder holt aus Ihrem Computer-Cache)</span><span class="sxs-lookup"><span data-stu-id="6f3d2-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="6f3d2-164">Schreibt die *obj/project.assets.json* Datei</span><span class="sxs-lookup"><span data-stu-id="6f3d2-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="6f3d2-165">Die *project.assets.json* Datei ist, einen vollständigen Satz von NuGet Abhängigkeiten Diagramm, Bindung Lösungen und andere app-Metadaten.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="6f3d2-166">Diese Datei wird von anderen Tools verwendet, z. B. erforderlichen [ `dotnet build` ](../tools/dotnet-build.md) und [ `dotnet run` ](../tools/dotnet-run.md), um den Quellcode ordnungsgemäß zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="6f3d2-167">[`dotnet run`](../tools/dotnet-run.md)Aufrufe [ `dotnet build` ](../tools/dotnet-build.md) zu einem erfolgreichen Build und ruft dann bestätigen `dotnet <assembly.dll>` um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="6f3d2-168">Erweiterte Szenarien finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md) Details.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="6f3d2-169">Die .NET Core-Anwendung dockerize</span><span class="sxs-lookup"><span data-stu-id="6f3d2-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="6f3d2-170">Die Hello .NET Core-Konsolen-app wird erfolgreich lokal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="6f3d2-171">Jetzt sehen wir führen, dass er einen Schritt weiter und erstellen und Ausführen der app in Docker.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="6f3d2-172">Die erste dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="6f3d2-172">Your first Dockerfile</span></span>

<span data-ttu-id="6f3d2-173">Öffnen Sie einen Text-Editor, und los geht!</span><span class="sxs-lookup"><span data-stu-id="6f3d2-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="6f3d2-174">Wir arbeiten weiterhin aus dem Hello-Verzeichnis, die wir die app in aufbauen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="6f3d2-175">Fügen Sie die folgenden Docker-Anweisungen für entweder Linux oder [Windows-Containern](https://docs.microsoft.com/virtualization/windowscontainers/about/) in eine neue Datei.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="6f3d2-176">Wenn Sie fertig sind, speichern Sie sie im Stammverzeichnis Ihres Verzeichnisses Hello als **Dockerfile**, ohne Erweiterung (müssen Sie möglicherweise auf dem Dateityp festgelegt `All types (*.*)` oder einer ähnlichen).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

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

<span data-ttu-id="6f3d2-177">Die dockerfile-Datei enthält Docker Build-Anweisungen, die sequenziell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="6f3d2-178">Die erste Anweisung muss [ **FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="6f3d2-179">Diese Anweisung initialisiert eine neue Stufe für den Build und legt die Basis-Image für die übrigen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="6f3d2-180">Die mit mehreren arch Tags pull Windows- oder Linux-Container abhängig von der Docker für Windows [containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="6f3d2-181">Die Basis-Image für unser Beispiel ist die 2.0-Sdk-Image aus dem Microsoft/Dotnet-Repository,</span><span class="sxs-lookup"><span data-stu-id="6f3d2-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="6f3d2-182">Die [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) Anweisung legt das Arbeitsverzeichnis für alle verbleibenden ausführen, CMD ENTRYPOINT, kopieren und hinzufügen Dockerfile Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="6f3d2-183">Wenn das Verzeichnis nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="6f3d2-184">In diesem Fall wird das app-Verzeichnis WORKDIR fest.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="6f3d2-185">Die [ **Kopie** ](https://docs.docker.com/engine/reference/builder/#copy) -Anweisung neue Dateien oder Verzeichnisse aus dem Quellpfad kopiert und in das Dateisystem der Ziel-Container hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="6f3d2-186">Mit dieser Anweisung werden wir die C#-Projektdatei für den Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="6f3d2-187">Die [ **ausführen** ](https://docs.docker.com/engine/reference/builder/#run) Anweisung führt alle Befehle in eine neue Schicht über das aktuelle Bild und übernehmen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="6f3d2-188">Das resultierende Image für die ein Commit ausgeführt wurde, wird für den nächsten Schritt in die dockerfile-Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="6f3d2-189">Wir arbeiten **Dotnet-Wiederherstellung** zum Abrufen der erforderlichen Abhängigkeiten der C#-Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="6f3d2-190">Dies **Kopie** -Anweisung kopiert die restlichen Dateien in unsere Container in neue [Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="6f3d2-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="6f3d2-191">Wir Veröffentlichen der app mit dieser **ausführen** Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="6f3d2-192">Die [ **Dotnet veröffentlichen** ](../tools/dotnet-publish.md) Befehl wird die Anwendung kompiliert, über dessen Abhängigkeiten in der Projektdatei angegebenen liest und die resultierende Menge der Dateien in einem Verzeichnis veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="6f3d2-193">Dieser app wird veröffentlicht, mit einem **Version** Konfiguration und die Ausgabe in das Standardverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="6f3d2-194">Die [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) Anweisung ermöglicht dem Container als ausführbare Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="6f3d2-195">Nachdem Sie eine dockerfile-Datei verfügen, die:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="6f3d2-196">Ihre app kopiert auf das Bild</span><span class="sxs-lookup"><span data-stu-id="6f3d2-196">copies your app to the image</span></span>
* <span data-ttu-id="6f3d2-197">Ihre app-Abhängigkeiten auf das Abbild</span><span class="sxs-lookup"><span data-stu-id="6f3d2-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="6f3d2-198">erstellt die app als ausführbare Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="6f3d2-199">Erstellen und Ausführen der app Hello .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6f3d2-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="6f3d2-200">Wichtige Docker-Befehle</span><span class="sxs-lookup"><span data-stu-id="6f3d2-200">Essential Docker commands</span></span>

<span data-ttu-id="6f3d2-201">Diese Befehle Docker sind wichtig:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="6f3d2-202">Docker build</span><span class="sxs-lookup"><span data-stu-id="6f3d2-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="6f3d2-203">"Docker run"</span><span class="sxs-lookup"><span data-stu-id="6f3d2-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="6f3d2-204">Docker ps</span><span class="sxs-lookup"><span data-stu-id="6f3d2-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="6f3d2-205">Docker stop</span><span class="sxs-lookup"><span data-stu-id="6f3d2-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="6f3d2-206">Docker rm</span><span class="sxs-lookup"><span data-stu-id="6f3d2-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="6f3d2-207">Docker rmi</span><span class="sxs-lookup"><span data-stu-id="6f3d2-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="6f3d2-208">Image von docker</span><span class="sxs-lookup"><span data-stu-id="6f3d2-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="6f3d2-209">Erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6f3d2-209">Build and run</span></span>

<span data-ttu-id="6f3d2-210">Sie wurde der dockerfile-Datei geschrieben; jetzt Docker Ihrer app erstellt und führt dann den Container.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="6f3d2-211">Die Ausgabe der `docker build` Befehl sollte ähnlich der folgenden Konsolenausgabe sein:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-211">The output from the `docker build` command should be similar to the following console output:</span></span>

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

<span data-ttu-id="6f3d2-212">Wie Sie aus der Ausgabe sehen können, verwendet das Docker-Modul die dockerfile-Datei um unsere Container zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="6f3d2-213">Die Ausgabe der `docker run` Befehl sollte ähnlich der folgenden Konsolenausgabe sein:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="6f3d2-214">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="6f3d2-214">Congratulations!</span></span> <span data-ttu-id="6f3d2-215">Sie haben soeben:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="6f3d2-216">Erstellt eine lokale .NET Core-app</span><span class="sxs-lookup"><span data-stu-id="6f3d2-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="6f3d2-217">Erstellt eine dockerfile-Datei zum Erstellen Ihres ersten Containers</span><span class="sxs-lookup"><span data-stu-id="6f3d2-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="6f3d2-218">Erstellt und ausgeführt haben Ihre app Dockerized</span><span class="sxs-lookup"><span data-stu-id="6f3d2-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="6f3d2-219">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6f3d2-219">Next Steps</span></span>

<span data-ttu-id="6f3d2-220">Hier sind die nächsten Schritte, die Sie ergreifen können:</span><span class="sxs-lookup"><span data-stu-id="6f3d2-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="6f3d2-221">Einführung in .NET Docker Images Video</span><span class="sxs-lookup"><span data-stu-id="6f3d2-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="6f3d2-222">Visual Studio, Docker & Azure-Container-Instanzen besser gemeinsam!</span><span class="sxs-lookup"><span data-stu-id="6f3d2-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="6f3d2-223">Docker für Azure-Quickstarts</span><span class="sxs-lookup"><span data-stu-id="6f3d2-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="6f3d2-224">Bereitstellen der app auf Docker für Azure</span><span class="sxs-lookup"><span data-stu-id="6f3d2-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="6f3d2-225">Wenn Sie nicht über ein Azure-Abonnement verfügen [registrieren Sie sich noch heute](https://azure.microsoft.com/free/?b=16.48) für eine kostenlose 30-Tage-Konto verhindern und $200 Azure-Guthaben auf eine beliebige Kombination von Azure-Dienste zu testen.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="6f3d2-226">In diesem Beispiel verwendete Docker-Images</span><span class="sxs-lookup"><span data-stu-id="6f3d2-226">Docker Images used in this sample</span></span>

<span data-ttu-id="6f3d2-227">In diesem Beispiel werden die folgenden Docker-Images verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f3d2-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="6f3d2-228">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6f3d2-228">Related Resources</span></span>

* [<span data-ttu-id="6f3d2-229">.NET Core Docker-Beispiele</span><span class="sxs-lookup"><span data-stu-id="6f3d2-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="6f3d2-230">Dockerfile unter Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="6f3d2-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="6f3d2-231">Docker für .NET Framework-Beispiele</span><span class="sxs-lookup"><span data-stu-id="6f3d2-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="6f3d2-232">ASP.NET Core unter DockerHub</span><span class="sxs-lookup"><span data-stu-id="6f3d2-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="6f3d2-233">Eine Anwendung für .NET Core - Docker-Lernprogramm dockerize</span><span class="sxs-lookup"><span data-stu-id="6f3d2-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="6f3d2-234">Arbeiten mit Docker-Tools für Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f3d2-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="6f3d2-235">Bereitstellen von Docker-Images aus der Registrierung des Azure-Container für Instanzen von Azure-Container</span><span class="sxs-lookup"><span data-stu-id="6f3d2-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)