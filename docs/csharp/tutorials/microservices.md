---
title: "In Docker gehostete Microservices – C#"
description: "Erfahren Sie, wie Sie ASP.NET Core-Dienste erstellen, die in Docker-Containern ausgeführt werden."
keywords: .NET, .NET Core, Docker, C#, ASP.NET, Microservice
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5585db33fb5020ed18c26f32ce0b63f97353d20f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="8d7dc-104">In Docker gehostete Microservices</span><span class="sxs-lookup"><span data-stu-id="8d7dc-104">Microservices hosted in Docker</span></span>

## <a name="introduction"></a><span data-ttu-id="8d7dc-105">Einführung</span><span class="sxs-lookup"><span data-stu-id="8d7dc-105">Introduction</span></span>

<span data-ttu-id="8d7dc-106">In diesem Tutorial werden die erforderlichen Aufgaben zum Erstellen und Bereitstellen eines ASP.NET Core-Microservice in einem Docker-Container erläutert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-106">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="8d7dc-107">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-107">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="8d7dc-108">Generieren einer ASP.NET Core-Anwendung mit Yeoman</span><span class="sxs-lookup"><span data-stu-id="8d7dc-108">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="8d7dc-109">Erstellen einer Docker-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="8d7dc-109">How to create a development Docker environment</span></span>
* <span data-ttu-id="8d7dc-110">Erstellen eines Docker-Images basierend auf einem vorhandenen Image</span><span class="sxs-lookup"><span data-stu-id="8d7dc-110">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="8d7dc-111">Bereitstellen Ihres Diensts in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="8d7dc-111">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="8d7dc-112">Dabei lernen Sie auch einige C#-Sprachfunktionen kennen:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-112">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="8d7dc-113">Konvertieren von C#-Objekten in JSON-Nutzlasten</span><span class="sxs-lookup"><span data-stu-id="8d7dc-113">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="8d7dc-114">Erstellen unveränderlicher Datenübertragungsobjekte</span><span class="sxs-lookup"><span data-stu-id="8d7dc-114">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="8d7dc-115">Verarbeiten eingehender HTTP-Anforderungen und Generieren der HTTP-Antwort</span><span class="sxs-lookup"><span data-stu-id="8d7dc-115">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="8d7dc-116">Arbeiten mit Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="8d7dc-116">How to work with nullable value types</span></span>

<span data-ttu-id="8d7dc-117">Sie können die Beispiel-App für dieses Thema [anzeigen oder herunterladen](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-117">You can [view or download the sample app](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="8d7dc-118">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="8d7dc-119">Warum Docker?</span><span class="sxs-lookup"><span data-stu-id="8d7dc-119">Why Docker?</span></span>

<span data-ttu-id="8d7dc-120">Docker erleichtert das Erstellen von standardmäßigen Computerimages zum Hosten Ihrer Dienste in einem Rechenzentrum oder der öffentlichen Cloud.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-120">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="8d7dc-121">Mit Docker können Sie das Image konfigurieren und nach Bedarf replizieren, um die Installation der Anwendung zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-121">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="8d7dc-122">Der gesamte Code in diesem Tutorial ist in einer beliebigen .NET Core-Umgebung einsetzbar.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-122">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="8d7dc-123">Die zusätzlichen Aufgaben für eine Docker-Installation funktionieren in Verbindung mit einer ASP.NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-123">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8d7dc-124">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="8d7dc-124">Prerequisites</span></span>
<span data-ttu-id="8d7dc-125">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-125">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="8d7dc-126">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-126">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="8d7dc-127">Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-127">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="8d7dc-128">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-128">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="8d7dc-129">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-129">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="8d7dc-130">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-130">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="8d7dc-131">Sie müssen auch das Docker-Modul installieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-131">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="8d7dc-132">Anweisungen für Ihre Plattform finden Sie auf der [Docker-Installationsseite](http://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-132">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="8d7dc-133">Docker kann in vielen Linux-Distributionen, unter macOS oder Windows installiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-133">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="8d7dc-134">Die oben erwähnte Seite enthält Abschnitte zu jeder verfügbaren Installation.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-134">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="8d7dc-135">Die meisten zu installierenden Komponenten sind einem Paket-Manager zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-135">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="8d7dc-136">Wenn Sie den Node.js-Paket-Manager `npm` installiert haben, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-136">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="8d7dc-137">Installieren Sie andernfalls das aktuelle NodeJS von [nodejs.org](https://nodejs.org), sodass der npm-Paket-Manager installiert wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-137">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="8d7dc-138">An diesem Punkt müssen Sie eine Reihe von Befehlszeilentools installieren, die die ASP.NET Core-Entwicklung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-138">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="8d7dc-139">Die Befehlszeilenvorlagen verwenden Yeoman, Bower, Grunt und Gulp.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-139">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="8d7dc-140">Sie haben sie bereits installiert? Hervorragend – geben Sie andernfalls Folgendes in Ihre bevorzugte Shell ein:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-140">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="8d7dc-141">Die `-g`-Option gibt an, dass dies eine globale Installation ist, und diese Tools im gesamten System verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-141">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="8d7dc-142">(Eine lokale Installation beschränkt das Paket auf ein einzelnes Projekt).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-142">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="8d7dc-143">Nachdem Sie diese wesentlichen Tools installiert haben, müssen Sie die Yeoman-ASP.NET-Vorlagengeneratoren installieren:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-143">Once you've installed those core tools, you need to install the yeoman asp.net template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="8d7dc-144">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="8d7dc-144">Create the Application</span></span>

<span data-ttu-id="8d7dc-145">Jetzt haben Sie alle Tools installiert und können eine neue ASP.NET Core-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-145">Now that you've installed all the tools, create a new asp.net core application.</span></span> <span data-ttu-id="8d7dc-146">Um den Befehlszeilengenerator zu verwenden, führen Sie den folgenden Yeoman-Befehl in Ihrer bevorzugten Shell aus:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-146">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="8d7dc-147">Dieser Befehl fordert Sie auf, auszuwählen, welchen Anwendungstyp Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-147">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="8d7dc-148">Für diesen Microservice sollten Sie die unkomplizierteste Webanwendung wählen, also wählen Sie „Leere Web-Anwendung“ aus.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-148">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="8d7dc-149">Die Vorlage fordert Sie zur Eingabe eines Namens auf.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-149">The template will prompt you for a name.</span></span> <span data-ttu-id="8d7dc-150">Wählen Sie „WeatherMicroservice“.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-150">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="8d7dc-151">Die Vorlage erstellt acht Dateien für Sie:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-151">The template creates eight files for you:</span></span>

* <span data-ttu-id="8d7dc-152">Eine für ASP.NET Core-Anwendungen angepasste .gitignore-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-152">A .gitignore, customized for asp.net core applications.</span></span>
* <span data-ttu-id="8d7dc-153">Eine Startup.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-153">A Startup.cs file.</span></span> <span data-ttu-id="8d7dc-154">Diese enthält die Grundlage für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-154">This contains the basis of the application.</span></span>
* <span data-ttu-id="8d7dc-155">Eine Program.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-155">A Program.cs file.</span></span> <span data-ttu-id="8d7dc-156">Diese enthält den Einstiegspunkt für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-156">This contains the entry point of the application.</span></span>
* <span data-ttu-id="8d7dc-157">Eine WeatherMicroservice.csproj-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-157">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="8d7dc-158">Dies ist die Build-Datei für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-158">This is the build file for the application.</span></span>
* <span data-ttu-id="8d7dc-159">Die Docker-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-159">A Dockerfile.</span></span> <span data-ttu-id="8d7dc-160">Dieses Skript erstellt ein Docker-Image für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-160">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="8d7dc-161">Eine README.md-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-161">A README.md.</span></span> <span data-ttu-id="8d7dc-162">Diese enthält Links zu anderen ASP.NET Core-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-162">This contains links to other asp.net core resources.</span></span>
* <span data-ttu-id="8d7dc-163">Eine web.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-163">A web.config file.</span></span> <span data-ttu-id="8d7dc-164">Diese enthält grundlegende Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-164">This contains basic configuration information.</span></span>
* <span data-ttu-id="8d7dc-165">Eine runtimeconfig.template.json-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-165">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="8d7dc-166">Diese enthält von IDEs verwendete Debugeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-166">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="8d7dc-167">Jetzt können Sie die von der Vorlage generierte Anwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-167">Now you can run the template generated application.</span></span> <span data-ttu-id="8d7dc-168">Dies geschieht mithilfe einer Reihe von Tools von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-168">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="8d7dc-169">Der `dotnet`-Befehl führt die erforderlichen Tools für die .NET-Entwicklung aus.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-169">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="8d7dc-170">Jedes Verb führt einen anderen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-170">Each verb executes a different command</span></span>

<span data-ttu-id="8d7dc-171">Der erste Schritt besteht im Wiederherstellen aller Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-171">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="8d7dc-172">Die Dotnet-Wiederherstellung verwendet den NuGet-Paket-Manager, um alle erforderlichen Pakete im Verzeichnis der Anwendung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-172">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="8d7dc-173">Sie generiert außerdem eine project.json.lock-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-173">It also generates a project.json.lock file.</span></span> <span data-ttu-id="8d7dc-174">Diese Datei enthält Informationen zu jedem Paket, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-174">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="8d7dc-175">Nach der Wiederherstellung alle Abhängigkeiten erstellen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-175">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```

<span data-ttu-id="8d7dc-176">Sobald Sie die Anwendung erstellen, führen Sie sie über die Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-176">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="8d7dc-177">Die Standardkonfiguration lauscht auf http://localhost:5000.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-177">The default configuration listens to http://localhost:5000.</span></span> <span data-ttu-id="8d7dc-178">Wenn Sie den Browser öffnen und zu dieser Seite navigieren, sehen Sie ein „Hello World!“.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-178">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="8d7dc-179">Vorgang nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-179">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="8d7dc-180">Anatomie einer ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8d7dc-180">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="8d7dc-181">Da Sie jetzt die Anwendung erstellt haben, können wir nun die Implementierung dieser Funktionalität betrachten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-181">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="8d7dc-182">Zwei der generierten Dateien sind hier besonders interessant: „project.json“ und „Startup.cs“.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-182">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="8d7dc-183">„project.json“ enthält Informationen zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-183">Project.json contains information about the project.</span></span> <span data-ttu-id="8d7dc-184">Sie werden häufig mit den beiden Knoten „Abhängigkeiten“ und „Frameworks“ arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-184">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="8d7dc-185">Der Abhängigkeiten-Knoten listet alle Pakete auf, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-185">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="8d7dc-186">Im Moment ist dies ein kleiner Knoten, der nur die Pakete benötigt, die den Webserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-186">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="8d7dc-187">Der frameworks-Knoten gibt die Versionen und Konfigurationen des .NET Framework an, das diese Anwendung ausführen wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-187">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="8d7dc-188">Die Anwendung wird in „Startup.cs“ implementiert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-188">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="8d7dc-189">Diese Datei enthält die Startklasse.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-189">This file contains the startup class.</span></span>

<span data-ttu-id="8d7dc-190">Die beiden Methoden werden von der ASP.NET Core-Infrastruktur zum Konfigurieren und Ausführen der Anwendung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-190">The two methods are called by the asp.net core infrastructure to configure and run the application.</span></span> <span data-ttu-id="8d7dc-191">Die `ConfigureServices`-Methode beschreibt die Dienste, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-191">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="8d7dc-192">Sie erstellen einen einfachen Microservice, sodass keine Abhängigkeiten konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-192">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="8d7dc-193">Die `Configure`-Methode konfiguriert die Handler für eingehende HTTP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-193">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="8d7dc-194">Die Vorlage erstellt einen einfachen Handler, der auf jede Anforderung mit dem Text „Hello World!“ reagiert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-194">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="8d7dc-195">Erstellen eines Microservice</span><span class="sxs-lookup"><span data-stu-id="8d7dc-195">Build a microservice</span></span>

<span data-ttu-id="8d7dc-196">Sie werden einen Dienst erstellen, der Wetterberichte aus aller Welt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-196">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="8d7dc-197">In einer Produktionsanwendung würden Sie einen Dienst aufrufen, um Wetterdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-197">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="8d7dc-198">In diesem Beispiel generieren wir einen zufälligen Wetterbericht.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-198">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="8d7dc-199">Sie müssen eine Reihe von Aufgaben ausführen, um unseren zufälligen Wetterdienst zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-199">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="8d7dc-200">Analysieren der eingehenden Anforderung, um den Breiten- und Längengrad zu lesen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-200">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="8d7dc-201">Generieren einiger zufälliger Vorhersagedaten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-201">Generate some random forecast data.</span></span>
* <span data-ttu-id="8d7dc-202">Konvertieren dieser zufälligen Vorhersagedaten von C#-Objekten in JSON-Pakete.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-202">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="8d7dc-203">Festlegen des Antwortheaders, um anzugeben, dass Ihr Dienst JSON-Daten zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-203">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="8d7dc-204">Schreiben der Antwort.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-204">Write the response.</span></span>

<span data-ttu-id="8d7dc-205">In den nächsten Abschnitten werden diese Schritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-205">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="8d7dc-206">Analyse der Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-206">Parsing the Query String.</span></span>

<span data-ttu-id="8d7dc-207">Sie beginnen mit der Analyse der Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-207">You'll begin by parsing the query string.</span></span> <span data-ttu-id="8d7dc-208">Der Dienst nimmt die Argumente „lat“ und „long“ in der Abfragezeichenfolge in diesem Formular entgegen:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-208">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="8d7dc-209">Alle Änderungen, die Sie vornehmen müssen, sind in dem Lambdaausdruck enthalten, der in Ihrer Startklasse als Argument für `app.Run` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-209">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="8d7dc-210">Das Argument des Lambdaausdrucks ist der `HttpContext` für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-210">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="8d7dc-211">Eine seiner Eigenschaften ist das `Request`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-211">One of its properties is the `Request` object.</span></span> <span data-ttu-id="8d7dc-212">Das `Request`-Objekt verfügt über eine `Query`-Eigenschaft, die ein Wörterbuch aller Werte in der Abfragezeichenfolge für die Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-212">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="8d7dc-213">Die erste Addition besteht darin, die Werte für Breiten- und Längengrad zu finden:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-213">The first addition is to find the latitude and longitude values:</span></span>

<span data-ttu-id="8d7dc-214">[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "Lesen von Variablen aus der Abfragezeichenfolge")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-214">[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]</span></span>

<span data-ttu-id="8d7dc-215">Die Abfrage-Wörterbuchwerte sind vom Typ `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-215">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="8d7dc-216">Dieser Typ kann eine Auflistung von Zeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-216">That type can contain a collection of strings.</span></span> <span data-ttu-id="8d7dc-217">Für Ihren Wetterdienst ist jeder Wert eine einzelne Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-217">For your weather service, each value is a single string.</span></span> <span data-ttu-id="8d7dc-218">Daher erfolgt der Aufruf von `FirstOrDefault()` im obigen Code.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-218">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="8d7dc-219">Als Nächstes müssen Sie die Zeichenfolgen in Double-Werte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-219">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="8d7dc-220">Die Methode, mit der Sie die Zeichenfolge in einen Double-Wert konvertieren, ist `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-220">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="8d7dc-221">Diese Methode nutzt C#-out-Parameter, um anzugeben, ob die Eingabezeichenfolge in einen Double-Wert konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-221">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="8d7dc-222">Wenn die Zeichenfolge einen gültigen Double-Wert darstellt, gibt die Methode „true“ zurück, und das `result`-Argument enthält den Wert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-222">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="8d7dc-223">Wenn die Zeichenfolge keinen gültigen Double-Wert darstellt, gibt die Methode „false“ zurück.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-223">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="8d7dc-224">Sie können diese API mithilfe einer *Erweiterungsmethode* anpassen, die einen *Nullable-Double-Wert*  zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-224">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="8d7dc-225">Ein *Nullable-Werttyp* ist ein Typ, der einen Werttyp darstellt und auch einen fehlenden, d.h. NULL-Wert enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-225">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="8d7dc-226">Ein Nullable-Typ wird durch Anhängen des `?`-Zeichens an die Typdeklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-226">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="8d7dc-227">Erweiterungsmethoden sind als statische Methoden definierte Methoden, können aber durch Hinzufügen des `this`-Modifizierers zum ersten Parameter so aufgerufen werden, als ob sie Member dieser Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-227">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="8d7dc-228">Erweiterungsmethoden können nur in statischen Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-228">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="8d7dc-229">Hier ist die Definition der Klasse, die die Erweiterungsmethode für die Analyse enthält:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-229">Here's the definition of the class containing the extension method for parse:</span></span>

<span data-ttu-id="8d7dc-230">[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "Versuch der Analyse in einen Nullable-Wert")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-230">[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]</span></span>

<span data-ttu-id="8d7dc-231">Der `default(double?)`-Ausdruck gibt den Standardwert für den `double?`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-231">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="8d7dc-232">Dieser Standardwert ist der NULL-Wert (oder nicht vorhandener Wert).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-232">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="8d7dc-233">Sie können diese Erweiterungsmethode verwenden, um die Abfragezeichenfolgen-Argumente in den Double-Typ zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-233">You can use this extension method to convert the query string arguments into the double type:</span></span>

<span data-ttu-id="8d7dc-234">[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Verwenden der TryParse-Erweiterungsmethode")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-234">[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]</span></span>

<span data-ttu-id="8d7dc-235">Um den Analysecode mühelos zu testen, aktualisieren Sie die Antwort so, dass sie die Werte der Argumente enthält:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-235">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

<span data-ttu-id="8d7dc-236">[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Schreiben der Ausgabeantwort")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-236">[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]</span></span>

<span data-ttu-id="8d7dc-237">An diesem Punkt können Sie die Webanwendung ausführen und prüfen, ob Ihr Analysecode funktioniert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-237">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="8d7dc-238">Fügen Sie der Webanforderung in einem Browser Werte hinzu, und Sie sollten die aktualisierten Ergebnisse sehen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-238">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="8d7dc-239">Erstellen einer zufälligen Wettervorhersage</span><span class="sxs-lookup"><span data-stu-id="8d7dc-239">Build a random weather forecast</span></span>

<span data-ttu-id="8d7dc-240">Ihre nächste Aufgabe ist das Erstellen einer zufälligen Wettervorhersage.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-240">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="8d7dc-241">Wir beginnen mit einem Datencontainer, der die Werte enthält, die Sie für einen Wetterbericht wünschen:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-241">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="8d7dc-242">Als Nächstes erstellen Sie einen Konstruktor, der diese Werte nach dem Zufallsprinzip festlegt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-242">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="8d7dc-243">Dieser Konstruktor verwendet die Werte für den Breiten- und Längengrad, um den Zufallszahlengenerator zu starten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-243">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="8d7dc-244">Das bedeutet, dass die Vorhersage für den gleichen Ort identisch ist.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-244">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="8d7dc-245">Wenn Sie die Argumente für den Breiten- und Längengrad ändern, erhalten Sie eine andere Vorhersage (weil Sie mit einem anderen Startwert beginnen.)</span><span class="sxs-lookup"><span data-stu-id="8d7dc-245">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

<span data-ttu-id="8d7dc-246">[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Wetterberichtkonstruktor")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-246">[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]</span></span>

<span data-ttu-id="8d7dc-247">Sie können jetzt die 5-Tage-Wettervorhersage in Ihrer Antwortmethode generieren:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-247">You can now generate the 5-day forecast in your response method:</span></span>

<span data-ttu-id="8d7dc-248">[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generieren eines zufälligen Wetterberichts")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-248">[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]</span></span>

### <a name="build-the-json-response"></a><span data-ttu-id="8d7dc-249">Erstellen Sie die JSON-Antwort.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-249">Build the JSON response.</span></span>

<span data-ttu-id="8d7dc-250">Die letzte Codierungsaufgabe auf dem Server ist, das WeatherReport-Array in ein JSON-Paket zu konvertieren und dieses an den Client zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-250">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="8d7dc-251">Wir erstellen zunächst das JSON-Paket.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-251">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="8d7dc-252">Sie fügen das NewtonSoft JSON-Serialisierungsprogramm der Liste der Abhängigkeiten hinzu.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-252">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="8d7dc-253">Verwenden Sie hierzu die `dotnet`-CLI:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-253">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="8d7dc-254">Anschließend können Sie das Objekt mithilfe der `JsonConvert`-Klasse in eine Zeichenfolge schreiben:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-254">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

<span data-ttu-id="8d7dc-255">[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Konvertieren von Objekten in JSON")]</span><span class="sxs-lookup"><span data-stu-id="8d7dc-255">[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]</span></span>

<span data-ttu-id="8d7dc-256">Der obige Code konvertiert das Vorhersageobjekt (eine Liste der `WeatherForecast`-Objekte) in ein JSON-Paket.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-256">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="8d7dc-257">Nachdem Sie das Antwortpaket erstellt haben, legen Sie den Inhaltstyp auf `application/json` fest, und schreiben Sie die Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-257">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="8d7dc-258">Die Anwendung wird jetzt ausgeführt und gibt zufällige Vorhersagen zurück.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-258">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="8d7dc-259">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="8d7dc-259">Build a Docker image</span></span>

<span data-ttu-id="8d7dc-260">Unsere letzte Aufgabe ist das Ausführen der Anwendung in Docker.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-260">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="8d7dc-261">Wir erstellen einen Docker-Container, der ein Docker-Image ausführt, das die Anwendung darstellt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-261">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="8d7dc-262">Ein ***Docker-Image*** ist eine Datei, die die Umgebung für die Ausführung der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-262">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="8d7dc-263">Ein ***Docker-Container*** stellt eine ausgeführte Instanz eines Docker-Images dar.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-263">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="8d7dc-264">Entsprechend können Sie sich das *Docker-Image* als eine *Klasse* und den *Docker-Container* als ein Objekt oder eine Instanz dieser Klasse vorstellen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-264">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="8d7dc-265">Die von der ASP.NET-Vorlage erstellte Docker-Datei ist für unsere Zwecke geeignet.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-265">The Dockerfile created by the asp.net template will serve for our purposes.</span></span> <span data-ttu-id="8d7dc-266">Betrachten wir ihren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-266">Let's go over its contents.</span></span>

<span data-ttu-id="8d7dc-267">Die erste Zeile gibt das Quellimage an:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-267">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="8d7dc-268">Mit Docker können Sie ein Computerimage auf Basis einer Quellvorlage konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-268">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="8d7dc-269">Das bedeutet, Sie müssen beim Start nicht alle Computerparameter, sondern nur Änderungen angeben.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-269">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="8d7dc-270">Hier dienen die Änderungen dazu, unsere Anwendung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-270">The changes here will be to include our application.</span></span>

<span data-ttu-id="8d7dc-271">In diesem ersten Beispiel verwenden wir die `1.1-sdk-msbuild`-Version des Dotnet-Images.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-271">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="8d7dc-272">Dies ist die einfachste Möglichkeit zum Erstellen einer funktionierenden Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-272">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="8d7dc-273">Dieses Image enthält die Dotnet Core-Laufzeit und das Dotnet SDK.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-273">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="8d7dc-274">Dies vereinfacht den Einstieg und das Erstellen, erstellt aber kein größeres Image.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-274">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="8d7dc-275">Die nächsten fünf Zeilen richten die Anwendung ein und erstellen sie:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-275">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="8d7dc-276">Hiermit wird die Projektdatei aus dem aktuellen Verzeichnis in die Docker-VM kopiert und werden alle Pakete wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-276">This will copy the project file from the  current directory to the docker VM, and restore all the packages.</span></span> <span data-ttu-id="8d7dc-277">Die Verwendung der Dotnet-CLI bedeutet, dass das Docker-Image das .NET Core-SDK einbeziehen muss.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-277">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="8d7dc-278">Danach wird der Rest der Anwendung kopiert, und der Dotnet-publish-Befehl erstellt Ihre Anwendung und macht daraus ein Paket.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-278">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="8d7dc-279">Die letzte Zeile der Datei führt die Anwendung aus:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-279">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="8d7dc-280">Auf diesen konfigurierten Port wird im `--server.urls`-Argument für `dotnet` in der letzten Zeile der Docker-Datei verwiesen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-280">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="8d7dc-281">Die `ENTRYPOINT`-Befehl teilt Docker mit, welcher Befehl und welche Befehlszeilenoptionen den Dienst starten.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-281">The `ENTRYPOINT` command informs Docker  what command and command line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="8d7dc-282">Erstellen und Ausführen des Images in einem Container</span><span class="sxs-lookup"><span data-stu-id="8d7dc-282">Building and running the image in a container.</span></span>

<span data-ttu-id="8d7dc-283">Wir erstellen ein Image und führen den Dienst in einem Docker-Container aus.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-283">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="8d7dc-284">Nicht alle Dateien in Ihrem lokalen Verzeichnis sollen in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-284">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="8d7dc-285">Stattdessen erstellen Sie die Anwendung im Container.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-285">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="8d7dc-286">Sie erstellen eine `.dockerignore`-Datei, um die Verzeichnisse festzulegen, die nicht in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-286">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="8d7dc-287">Kein Buildobjekt soll kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-287">You don't want any of the build assets copied.</span></span> <span data-ttu-id="8d7dc-288">Geben Sie die Verzeichnisse für Build und Veröffentlichung in der `.dockerignore`-Datei an:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-288">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="8d7dc-289">Sie erstellen das Image mithilfe des Docker-build-Befehls.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-289">You build the image using the docker build command.</span></span> <span data-ttu-id="8d7dc-290">Führen Sie den folgenden Befehl in dem Verzeichnis aus, das Ihren Code enthält.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-290">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="8d7dc-291">Dieser Befehl erstellt das Containerimage basierend auf allen Informationen in Ihrer Docker-Datei.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-291">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="8d7dc-292">Das `-t`-Argument liefert ein Tag, d.h. einen Namen, für dieses Containerimage.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-292">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="8d7dc-293">In der Befehlszeile oben wird das Tag `weather-microservice` für den Docker-Container verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-293">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="8d7dc-294">Nach Abschluss dieses Befehls verfügen Sie über einen Container, in dem Sie den neuen Dienst ausführen können.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-294">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="8d7dc-295">Führen Sie den folgenden Befehl zum Starten des Containers aus, und starten Sie Ihren Dienst:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-295">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="8d7dc-296">Die `-d`-Option bedeutet, den Container unabhängig vom aktuellen Terminal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-296">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="8d7dc-297">Dies bedeutet, dass die Ausgabe des Befehls nicht auf Ihrem Terminal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-297">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="8d7dc-298">Die `-p`-Option gibt die Portzuordnung zwischen dem Dienst und dem Host an.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-298">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="8d7dc-299">Hier gibt sie an, dass jede an Port 80 eingehende Anforderung an Port 5000 im Container weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-299">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="8d7dc-300">5000 entspricht dem Port, auf den der Dienst über die Befehlszeilenargumente lauscht, die in der oben genannten Docker-Datei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-300">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="8d7dc-301">Das `--name`-Argument benennt den ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-301">The `--name` argument names your running container.</span></span> <span data-ttu-id="8d7dc-302">Es ist ein praktischer Name, den Sie zum Arbeiten mit dem betreffenden Container verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-302">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="8d7dc-303">Sie können sehen, ob das Image ausgeführt wird, indem Sie den Befehl überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-303">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="8d7dc-304">Wenn der Container ausgeführt wird, sehen Sie eine Zeile, in der er als ausgeführter Prozess aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-304">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="8d7dc-305">(Vielleicht ist er der einzige).</span><span class="sxs-lookup"><span data-stu-id="8d7dc-305">(It may be the only one).</span></span>

<span data-ttu-id="8d7dc-306">Sie können Ihren Dienst testen, indem Sie einen Browser öffnen, zu „localhost“ navigieren und einen Breiten- und Längengrad angeben:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-306">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="8d7dc-307">Anfügen an einen ausgeführten Container</span><span class="sxs-lookup"><span data-stu-id="8d7dc-307">Attaching to a running container</span></span>

<span data-ttu-id="8d7dc-308">Bei der Ausführung Ihres Diensts in einem Befehlsfenster konnten Sie sehen, dass für jede Anforderung Diagnoseinformationen ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-308">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="8d7dc-309">Diese Informationen werden nicht angezeigt, wenn der Container im getrennten Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-309">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="8d7dc-310">Der Docker-attach-Befehl ermöglicht Ihnen das Anfügen an einen ausgeführten Container, sodass Sie die Protokollinformationen sehen können.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-310">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="8d7dc-311">Führen Sie diesen Befehl in einem Befehlsfenster aus:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-311">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="8d7dc-312">Das `--sig-proxy=false`-Argument bedeutet, dass `Ctrl-C`-Befehle nicht an den Containerprozess gesendet werden, aber stattdessen den `docker attach`-Befehl beenden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-312">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="8d7dc-313">Das letzte Argument ist der Name, den der Container im `docker run`-Befehl erhält.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-313">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d7dc-314">Sie können auch die Docker zugewiesene Container-ID verwenden, um auf einen Container zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-314">You can also use the docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="8d7dc-315">Wenn Sie in `docker run` keinen Namen für den Container angegeben haben, müssen Sie die Container-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-315">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="8d7dc-316">Öffnen Sie einen Browser, und navigieren Sie zu Ihrem Dienst.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-316">Open a browser and navigate to your service.</span></span> <span data-ttu-id="8d7dc-317">Sie sehen die Diagnosemeldungen des angefügten ausgeführten Containers in den Befehlsfenstern.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-317">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="8d7dc-318">Drücken Sie `Ctrl-C`, um den Anfügungsprozess zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-318">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="8d7dc-319">Wenn Sie die Arbeit mit Ihrem Container abgeschlossen haben, können Sie ihn stoppen:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-319">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="8d7dc-320">Container und Image stehen weiterhin für einen Neustart zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-320">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="8d7dc-321">Wenn Sie den Container von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-321">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="8d7dc-322">Wenn Sie nicht benutzte Images von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="8d7dc-322">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="8d7dc-323">Schlussfolgerung</span><span class="sxs-lookup"><span data-stu-id="8d7dc-323">Conclusion</span></span> 

<span data-ttu-id="8d7dc-324">In diesem Tutorial haben Sie einen ASP.NET Core-Microservice erstellt und einige einfache Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-324">In this tutorial, you built an asp.net core microservice, and added a few simple features.</span></span>

<span data-ttu-id="8d7dc-325">Sie haben ein Docker-Containerimage für diesen Dienst erstellt und diesen Container auf dem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-325">You built a docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="8d7dc-326">Sie haben dem Dienst ein Terminalfenster angefügt und die Diagnosemeldungen Ihres Diensts gesehen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-326">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="8d7dc-327">Nebenbei haben Sie verschiedene Features der C#-Sprache in Aktion gesehen.</span><span class="sxs-lookup"><span data-stu-id="8d7dc-327">Along the way, you saw several features of the C# language in action.</span></span>

