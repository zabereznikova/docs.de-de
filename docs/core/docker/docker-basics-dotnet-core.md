---
title: Bereitstellen einer App im Container mit Docker
description: Dieses Tutorial zeigt das Erstellen einer einfachen .NET Core-Anwendung und ihr Bereitstellen im Container mit Docker.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: eed72553576f4154fe63b2e5cf035a781afe4b7c
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169585"
---
# <a name="how-to-containerize-a-net-core-application"></a><span data-ttu-id="37ecf-103">Bereitstellen einer .NET Core-Anwendung im Container</span><span class="sxs-lookup"><span data-stu-id="37ecf-103">How to containerize a .NET Core application</span></span>

<span data-ttu-id="37ecf-104">In diesem Tutorial werden die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung erläutert.</span><span class="sxs-lookup"><span data-stu-id="37ecf-104">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="37ecf-105">Die [Docker-Plattform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) verwendet die [Docker-Engine](https://docs.docker.com/engine/docker-overview/#docker-engine), um Pakete schnell als [Docker-Images](https://docs.docker.com/glossary/?term=image) zu erstellen und zu packen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-105">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="37ecf-106">Diese Images werden im [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile)-Format geschrieben, um in einem [mehrstufigen Container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers) bereitgestellt und ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="37ecf-106">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="37ecf-107">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="37ecf-107">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="37ecf-108">das Erstellen einer Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="37ecf-108">How to create a Dockerfile</span></span>
> * <span data-ttu-id="37ecf-109">das Erstellen einer .NET Core-App</span><span class="sxs-lookup"><span data-stu-id="37ecf-109">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="37ecf-110">das Bereitstellen Ihrer App in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="37ecf-110">How to deploy your app into a Docker container.</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="37ecf-111">.NET Core: Einfacher Einstieg</span><span class="sxs-lookup"><span data-stu-id="37ecf-111">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="37ecf-112">Bevor Sie ein Docker-Image erstellen, benötigen Sie eine Anwendung, die containerisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="37ecf-112">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="37ecf-113">Diese können Sie unter Linux, macOS oder Windows erstellen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-113">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="37ecf-114">Die schnellste und einfachste Methode hierfür ist die Verwendung von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37ecf-114">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="37ecf-115">Wenn Sie mit dem Toolset der .NET Core-Befehlszeilenschnittstelle nicht vertraut sind, finden Sie entsprechende Informationen in der [Übersicht über das .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="37ecf-115">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="37ecf-116">Sie können Windows- und Linux-Container mit [Tags, die auf mehreren Architekturen basieren](https://github.com/dotnet/announcements/issues/14), erstellen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-116">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="37ecf-117">Ihre erste Docker-App mit .NET Core</span><span class="sxs-lookup"><span data-stu-id="37ecf-117">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="37ecf-118">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="37ecf-118">Prerequisites</span></span>

<span data-ttu-id="37ecf-119">Zum Abschließen dieses Tutorials benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="37ecf-119">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="37ecf-120">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="37ecf-120">.NET Core SDK</span></span>

* <span data-ttu-id="37ecf-121">Installieren Sie [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) oder höher.</span><span class="sxs-lookup"><span data-stu-id="37ecf-121">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="37ecf-122">Unter [.NET Core 2.1.x Supported OS Versions (Von .NET Core 2.1.x unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, die von .NET Core 2.1 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="37ecf-122">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="37ecf-123">Installieren Sie Ihren bevorzugten Code-Editor, wenn Sie dies nicht bereits erledigt haben.</span><span class="sxs-lookup"><span data-stu-id="37ecf-123">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="37ecf-124">Benötigen Sie einen Code-Editor?</span><span class="sxs-lookup"><span data-stu-id="37ecf-124">Need to install a code editor?</span></span> <span data-ttu-id="37ecf-125">Probieren Sie [Visual Studio Code](https://code.visualstudio.com/download) aus!</span><span class="sxs-lookup"><span data-stu-id="37ecf-125">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="37ecf-126">Installieren des Docker-Clients</span><span class="sxs-lookup"><span data-stu-id="37ecf-126">Installing Docker Client</span></span>

<span data-ttu-id="37ecf-127">Installieren Sie den Docker-Client [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) oder höher.</span><span class="sxs-lookup"><span data-stu-id="37ecf-127">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="37ecf-128">Der Docker-Client kann unter folgenden Betriebssystemen installiert werden:</span><span class="sxs-lookup"><span data-stu-id="37ecf-128">The Docker client can be installed in:</span></span>

* <span data-ttu-id="37ecf-129">Linux-Verteilungen</span><span class="sxs-lookup"><span data-stu-id="37ecf-129">Linux distributions</span></span>

   * [<span data-ttu-id="37ecf-130">CentOS</span><span class="sxs-lookup"><span data-stu-id="37ecf-130">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="37ecf-131">Debian</span><span class="sxs-lookup"><span data-stu-id="37ecf-131">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="37ecf-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="37ecf-132">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="37ecf-133">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="37ecf-133">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="37ecf-134">macOS</span><span class="sxs-lookup"><span data-stu-id="37ecf-134">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="37ecf-135">[Windows](https://docs.docker.com/docker-for-windows/install/)</span><span class="sxs-lookup"><span data-stu-id="37ecf-135">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="37ecf-136">Erstellen einer .NET Core 2.1-Konsolen-App für das Bereitstellen in Docker</span><span class="sxs-lookup"><span data-stu-id="37ecf-136">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="37ecf-137">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie einen Ordner mit dem Namen *Hello*.</span><span class="sxs-lookup"><span data-stu-id="37ecf-137">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="37ecf-138">Navigieren Sie zum erstellten Ordner, und geben Sie folgende Befehle ein:</span><span class="sxs-lookup"><span data-stu-id="37ecf-138">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="37ecf-139">Hier eine kurze Beschreibung der Schritte:</span><span class="sxs-lookup"><span data-stu-id="37ecf-139">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="37ecf-140">Mit [`dotnet new`](../tools/dotnet-new.md) wird eine aktuelle Projektdatei `Hello.csproj` mit den Abhängigkeiten erstellt, die zum Erstellen einer Konsolen-App benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="37ecf-140">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="37ecf-141">Zudem wird `Program.cs` erstellt. Hierbei handelt es sich um eine einfache Datei, die den Einstiegspunkt für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="37ecf-141">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="37ecf-142">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="37ecf-142">`Hello.csproj`:</span></span>

   <span data-ttu-id="37ecf-143">Die Projektdatei gibt alle Elemente an, die zum Wiederherstellen von Abhängigkeiten und erstellen des Programms erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="37ecf-143">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="37ecf-144">Das Tag `OutputType` gibt an, dass wir eine ausführbare Datei, also eine Konsolenanwendung, erstellen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-144">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="37ecf-145">Das Tag `TargetFramework` gibt an, welche .NET-Implementierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="37ecf-145">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="37ecf-146">In einem komplexen Szenario können Sie mehrere Zielframeworks angeben und die Erstellung für die angegebenen Frameworks in einem einzigen Vorgang vornehmen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-146">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="37ecf-147">In diesem Tutorial werden Projekte für .NET Core 2.1 erstellt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-147">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="37ecf-148">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="37ecf-148">`Program.cs`:</span></span>

   <span data-ttu-id="37ecf-149">Das Programm wird durch `using System` gestartet.</span><span class="sxs-lookup"><span data-stu-id="37ecf-149">The program starts by `using System`.</span></span> <span data-ttu-id="37ecf-150">Diese Anweisung bedeutet: „Alle Elemente im `System`-Namespace müssen in den Bereich dieser Datei gebracht werden.“</span><span class="sxs-lookup"><span data-stu-id="37ecf-150">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="37ecf-151">Der Namespace `System` enthält grundlegende Konstrukte, wie z.B. `string`, oder numerische Typen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-151">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="37ecf-152">Wir definieren dann einen Namespace namens `Hello`.</span><span class="sxs-lookup"><span data-stu-id="37ecf-152">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="37ecf-153">Sie können den Namespace beliebig ändern.</span><span class="sxs-lookup"><span data-stu-id="37ecf-153">You can change namespace to anything you want.</span></span> <span data-ttu-id="37ecf-154">Eine Klasse namens `Program` wird in diesem Namespace mit einer `Main`-Methode definiert, welche ein Array von Zeichenfolgen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="37ecf-154">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="37ecf-155">Dieses Array enthält die Liste mit Argumenten, die übergeben werden, wenn das kompilierte Programm aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="37ecf-155">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="37ecf-156">In diesem Beispiel gibt das Programm lediglich „Hallo Welt!“</span><span class="sxs-lookup"><span data-stu-id="37ecf-156">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="37ecf-157">auf der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="37ecf-157">to the console.</span></span>

   <span data-ttu-id="37ecf-158">**dotnet new** führt den [`dotnet restore`](../tools/dotnet-restore.md)-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="37ecf-158">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="37ecf-159">Durch **dotnet restore** wird die Struktur der Abhängigkeiten durch einen Aufruf von [NuGet](https://www.nuget.org/) (.NET-Paket-Manager) wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-159">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="37ecf-160">NuGet führt folgende Ausgaben aus:</span><span class="sxs-lookup"><span data-stu-id="37ecf-160">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="37ecf-161">Analyse der *Hello.csproj*-Datei.</span><span class="sxs-lookup"><span data-stu-id="37ecf-161">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="37ecf-162">Download der Abhängigkeiten der Datei (oder Abrufen aus dem Cache des Computers).</span><span class="sxs-lookup"><span data-stu-id="37ecf-162">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="37ecf-163">Schreiben der *obj/project.assets.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="37ecf-163">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="37ecf-164">Die Datei *project.assets.json* stellt einen vollständigen Satz von App-Metadaten (z.B. Diagramme, Bindungsauflösungen usw.) für NuGet-Abhängigkeiten dar.</span><span class="sxs-lookup"><span data-stu-id="37ecf-164">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="37ecf-165">Diese Datei wird von anderen Tools wie [`dotnet build`](../tools/dotnet-build.md) und [`dotnet run`](../tools/dotnet-run.md) verwendet, um den Quellcode ordnungsgemäß zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="37ecf-165">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="37ecf-166">[`dotnet run`](../tools/dotnet-run.md) ruft [`dotnet build`](../tools/dotnet-build.md) auf, um einen erfolgreichen Build zu bestätigen. Anschließend wird `dotnet <assembly.dll>` aufgerufen, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="37ecf-166">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="37ecf-167">Weitere Informationen zu erweiterten Szenarios finden Sie unter [.NET Core-Anwendungsbereitstellung](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="37ecf-167">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="37ecf-168">Bereitstellen der .NET Core-Anwendung in Docker</span><span class="sxs-lookup"><span data-stu-id="37ecf-168">Dockerize the .NET Core application</span></span>

<span data-ttu-id="37ecf-169">Die Konsolen-App „Hello .NET Core“ wird erfolgreich lokal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-169">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="37ecf-170">Im nächsten Schritt wird die App in Docker erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-170">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="37ecf-171">Ihre erste Dockerfile-Datei</span><span class="sxs-lookup"><span data-stu-id="37ecf-171">Your first Dockerfile</span></span>

<span data-ttu-id="37ecf-172">Öffnen Sie Ihren Text-Editor, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-172">Open your text editor and let's get started!</span></span> <span data-ttu-id="37ecf-173">Sie arbeiten weiterhin mit dem Hello-Verzeichnis, in dem die App erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ecf-173">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="37ecf-174">Fügen Sie folgende Docker-Anweisungen für Linux- oder [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) zu einer neuen Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="37ecf-174">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="37ecf-175">Wenn dieser Vorgang abgeschlossen ist, speichern Sie die Datei ohne Erweiterung im Stammverzeichnis Ihres Hello-Verzeichnisses als **Dockerfile**. Sie müssen den Dateityp möglicherweise auf `All types (*.*)` (oder etwas ähnliches) festlegen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-175">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="37ecf-176">Die Dockerfile-Datei enthält die Buildanweisungen für Docker, die nacheinander ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="37ecf-176">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="37ecf-177">Die erste Anweisung muss [**FROM**](https://docs.docker.com/engine/reference/builder/#from) sein.</span><span class="sxs-lookup"><span data-stu-id="37ecf-177">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="37ecf-178">Diese Anweisung initialisiert eine neue Stufe des Builds und legt das Basisimage für die übrigen Anweisungen fest.</span><span class="sxs-lookup"><span data-stu-id="37ecf-178">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="37ecf-179">Die Tags für mehrere Architekturen pullen abhängig vom [Containermodus](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) von Docker für Windows entweder Windows- oder Linux-Container.</span><span class="sxs-lookup"><span data-stu-id="37ecf-179">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="37ecf-180">Das Basisimage für dieses Beispiel ist das 2.1-sdk-Image aus dem Repository „microsoft/dotnet“.</span><span class="sxs-lookup"><span data-stu-id="37ecf-180">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="37ecf-181">Die [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir)-Anweisung legt das Arbeitsverzeichnis für die übrigen Dockerfile-Anweisungen RUN, CMD, ENTRYPOINT, COPY und ADD fest.</span><span class="sxs-lookup"><span data-stu-id="37ecf-181">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="37ecf-182">Wenn das Verzeichnis noch nicht vorhanden ist, wird es erstellt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-182">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="37ecf-183">In diesem Fall ist WORKDIR auf das App-Verzeichnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37ecf-183">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="37ecf-184">Die [**COPY**](https://docs.docker.com/engine/reference/builder/#copy)-Anweisung kopiert neue Dateien oder Verzeichnisse aus dem Quellpfad und fügt diese dem Zieldateisystem des Containers hinzu.</span><span class="sxs-lookup"><span data-stu-id="37ecf-184">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="37ecf-185">Mit dieser Anweisung wird die C#-Projektdatei in den Container kopiert.</span><span class="sxs-lookup"><span data-stu-id="37ecf-185">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="37ecf-186">Die [**RUN**](https://docs.docker.com/engine/reference/builder/#run)-Anweisung führt jeden Befehl in einer neuen Ebene über dem aktuellen Image aus und committet die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="37ecf-186">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="37ecf-187">Das resultierende committete Image wird im nächsten Schritt in der Dockerdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="37ecf-187">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="37ecf-188">Führen Sie **dotnet restore** aus, um die erforderlichen Abhängigkeiten der C#-Projektdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-188">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="37ecf-189">Diese **COPY**-Anweisung kopiert die restlichen Dateien in neue [Ebenen](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) des Containers.</span><span class="sxs-lookup"><span data-stu-id="37ecf-189">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="37ecf-190">Veröffentlichen Sie die App mit der **RUN**-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="37ecf-190">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="37ecf-191">Der Befehl [**dotnet publish**](../tools/dotnet-publish.md) kompiliert die Anwendung, liest die Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="37ecf-191">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="37ecf-192">Die App wird mit einer **Releasekonfiguration** und einer Ausgabe in das Standardverzeichnis veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="37ecf-192">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="37ecf-193">Die [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint)-Anweisung ermöglicht die Ausführung des Containers als ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="37ecf-193">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="37ecf-194">Sie verfügen nun über eine Dockerfile-Datei, die:</span><span class="sxs-lookup"><span data-stu-id="37ecf-194">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="37ecf-195">Ihre App in das Image kopiert</span><span class="sxs-lookup"><span data-stu-id="37ecf-195">copies your app to the image</span></span>
* <span data-ttu-id="37ecf-196">die Abhängigkeiten Ihrer App in das Image kopiert</span><span class="sxs-lookup"><span data-stu-id="37ecf-196">your app's dependencies to the image</span></span>
* <span data-ttu-id="37ecf-197">die App für die Ausführung als ausführbare Datei erstellt</span><span class="sxs-lookup"><span data-stu-id="37ecf-197">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="37ecf-198">Erstellen und Ausführen der Hello-.NET Core-App</span><span class="sxs-lookup"><span data-stu-id="37ecf-198">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="37ecf-199">Grundlegende Docker-Befehle</span><span class="sxs-lookup"><span data-stu-id="37ecf-199">Essential Docker commands</span></span>

<span data-ttu-id="37ecf-200">Diese Docker-Befehle sind grundlegend:</span><span class="sxs-lookup"><span data-stu-id="37ecf-200">These Docker commands are essential:</span></span>

* [<span data-ttu-id="37ecf-201">docker build</span><span class="sxs-lookup"><span data-stu-id="37ecf-201">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="37ecf-202">docker run</span><span class="sxs-lookup"><span data-stu-id="37ecf-202">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="37ecf-203">docker ps</span><span class="sxs-lookup"><span data-stu-id="37ecf-203">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="37ecf-204">docker stop</span><span class="sxs-lookup"><span data-stu-id="37ecf-204">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="37ecf-205">docker rm</span><span class="sxs-lookup"><span data-stu-id="37ecf-205">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="37ecf-206">docker rmi</span><span class="sxs-lookup"><span data-stu-id="37ecf-206">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="37ecf-207">docker image</span><span class="sxs-lookup"><span data-stu-id="37ecf-207">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="37ecf-208">Erstellen und Ausführen</span><span class="sxs-lookup"><span data-stu-id="37ecf-208">Build and run</span></span>

<span data-ttu-id="37ecf-209">Nachdem Sie die Dockerfile-Datei geschrieben haben, erstellt Docker Ihre App und führt anschließend den Container aus.</span><span class="sxs-lookup"><span data-stu-id="37ecf-209">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="37ecf-210">Die Ausgabe des `docker build`-Befehls sollte folgender Konsolenausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="37ecf-210">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="37ecf-211">Wie Sie an der Ausgabe erkennen können, verwendet die Docker-Engine die Dockerfile-Datei, um Ihren Container zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-211">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="37ecf-212">Die Ausgabe des `docker run`-Befehls sollte folgender Konsolenausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="37ecf-212">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="37ecf-213">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="37ecf-213">Congratulations!</span></span> <span data-ttu-id="37ecf-214">Sie haben gerade:</span><span class="sxs-lookup"><span data-stu-id="37ecf-214">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="37ecf-215">eine lokale .NET Core-App erstellt</span><span class="sxs-lookup"><span data-stu-id="37ecf-215">Created a local .NET Core app</span></span>
> * <span data-ttu-id="37ecf-216">eine Dockerfile-Datei erstellt, um Ihren ersten Container zu erstellen</span><span class="sxs-lookup"><span data-stu-id="37ecf-216">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="37ecf-217">die in Docker bereitgestellte App erstellt und ausgeführt</span><span class="sxs-lookup"><span data-stu-id="37ecf-217">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="37ecf-218">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="37ecf-218">Next steps</span></span>

<span data-ttu-id="37ecf-219">Im Folgenden finden Sie weiterführende Schritte:</span><span class="sxs-lookup"><span data-stu-id="37ecf-219">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="37ecf-220">Introduction to .NET Docker Images Video(Video: Einführung in .NET-Docker-Images)</span><span class="sxs-lookup"><span data-stu-id="37ecf-220">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="37ecf-221">Visual Studio, Docker & Azure Container Instances better together! (Wie sich Visual Studio, Docker und Azure Container Instances ergänzen)</span><span class="sxs-lookup"><span data-stu-id="37ecf-221">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [<span data-ttu-id="37ecf-222">Docker for Azure Quickstarts (Docker für Azure-Schnellstarts)</span><span class="sxs-lookup"><span data-stu-id="37ecf-222">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="37ecf-223">Deploy your app on Docker for Azure (Bereitstellen Ihrer App in Docker für Azure)</span><span class="sxs-lookup"><span data-stu-id="37ecf-223">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="37ecf-224">Wenn Sie kein Azure-Abonnement besitzen, [registrieren Sie sich noch heute für ein kostenloses 30-Tage-Konto](https://azure.microsoft.com/free/?b=16.48), und erhalten Sie ein Azure-Guthaben in Höhe von 200 US-Dollar, um eine beliebige Kombination von Azure-Diensten zu testen.</span><span class="sxs-lookup"><span data-stu-id="37ecf-224">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="37ecf-225">In diesem Beispiel verwendete Docker-Images</span><span class="sxs-lookup"><span data-stu-id="37ecf-225">Docker Images used in this sample</span></span>

<span data-ttu-id="37ecf-226">Folgende Docker-Images werden in diesem Beispiel verwendet:</span><span class="sxs-lookup"><span data-stu-id="37ecf-226">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="37ecf-227">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37ecf-227">Related resources</span></span>

* [<span data-ttu-id="37ecf-228">.NET Core Docker samples (Docker-Beispiele für .NET Core)</span><span class="sxs-lookup"><span data-stu-id="37ecf-228">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [<span data-ttu-id="37ecf-229">Dockerfile-Datei in Windows-Containern</span><span class="sxs-lookup"><span data-stu-id="37ecf-229">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="37ecf-230">.NET Framework Docker samples (Docker-Beispiele für .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="37ecf-230">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="37ecf-231">ASP.NET Core auf DockerHub</span><span class="sxs-lookup"><span data-stu-id="37ecf-231">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="37ecf-232">Dockerize a .NET Core application - Docker Tutorial (Docker-Tutorial: Bereitstellen einer .NET Core-Anwendung in Docker)</span><span class="sxs-lookup"><span data-stu-id="37ecf-232">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="37ecf-233">Arbeiten mit Visual Studio-Tools für Docker</span><span class="sxs-lookup"><span data-stu-id="37ecf-233">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="37ecf-234">Deploying Docker Images from the Azure Container Registry to Azure Container Instances (Bereitstellen von Docker-Images aus Azure Container Registry für Azure Container Instances)</span><span class="sxs-lookup"><span data-stu-id="37ecf-234">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)