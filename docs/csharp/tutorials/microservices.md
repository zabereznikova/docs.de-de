---
title: In Docker gehostete Microservices – C#
description: Erfahren Sie, wie Sie ASP.NET Core-Dienste erstellen, die in Docker-Containern ausgeführt werden.
ms.date: 02/03/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 7428051c1d9a29ba98ca1f28288b3c50ea36ae1a
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="49f35-103">In Docker gehostete Microservices</span><span class="sxs-lookup"><span data-stu-id="49f35-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="49f35-104">In diesem Tutorial werden die erforderlichen Aufgaben zum Erstellen und Bereitstellen eines ASP.NET Core-Microservice in einem Docker-Container erläutert.</span><span class="sxs-lookup"><span data-stu-id="49f35-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="49f35-105">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="49f35-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="49f35-106">Generieren einer ASP.NET Core-Anwendung mit Yeoman</span><span class="sxs-lookup"><span data-stu-id="49f35-106">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="49f35-107">Erstellen einer Docker-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="49f35-107">How to create a development Docker environment</span></span>
* <span data-ttu-id="49f35-108">Erstellen eines Docker-Images basierend auf einem vorhandenen Image</span><span class="sxs-lookup"><span data-stu-id="49f35-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="49f35-109">Bereitstellen Ihres Diensts in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="49f35-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="49f35-110">Dabei lernen Sie auch einige C#-Sprachfunktionen kennen:</span><span class="sxs-lookup"><span data-stu-id="49f35-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="49f35-111">Konvertieren von C#-Objekten in JSON-Nutzlasten</span><span class="sxs-lookup"><span data-stu-id="49f35-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="49f35-112">Erstellen unveränderlicher Datenübertragungsobjekte</span><span class="sxs-lookup"><span data-stu-id="49f35-112">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="49f35-113">Verarbeiten eingehender HTTP-Anforderungen und Generieren der HTTP-Antwort</span><span class="sxs-lookup"><span data-stu-id="49f35-113">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="49f35-114">Arbeiten mit Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="49f35-114">How to work with nullable value types</span></span>

<span data-ttu-id="49f35-115">Sie können die Beispiel-App für dieses Thema [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice).</span><span class="sxs-lookup"><span data-stu-id="49f35-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="49f35-116">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="49f35-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="49f35-117">Warum Docker?</span><span class="sxs-lookup"><span data-stu-id="49f35-117">Why Docker?</span></span>

<span data-ttu-id="49f35-118">Docker erleichtert das Erstellen von standardmäßigen Computerimages zum Hosten Ihrer Dienste in einem Rechenzentrum oder der öffentlichen Cloud.</span><span class="sxs-lookup"><span data-stu-id="49f35-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="49f35-119">Mit Docker können Sie das Image konfigurieren und nach Bedarf replizieren, um die Installation der Anwendung zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="49f35-120">Der gesamte Code in diesem Tutorial ist in einer beliebigen .NET Core-Umgebung einsetzbar.</span><span class="sxs-lookup"><span data-stu-id="49f35-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="49f35-121">Die zusätzlichen Aufgaben für eine Docker-Installation funktionieren in Verbindung mit einer ASP.NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="49f35-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="49f35-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="49f35-122">Prerequisites</span></span>
<span data-ttu-id="49f35-123">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="49f35-123">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="49f35-124">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="49f35-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="49f35-125">Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="49f35-125">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="49f35-126">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="49f35-127">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="49f35-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="49f35-128">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="49f35-129">Sie müssen auch die Docker-Engine installieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="49f35-130">Anweisungen für Ihre Plattform finden Sie auf der [Docker-Installationsseite](http://www.docker.com/products/docker).</span><span class="sxs-lookup"><span data-stu-id="49f35-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="49f35-131">Docker kann in vielen Linux-Distributionen, unter macOS oder Windows installiert werden.</span><span class="sxs-lookup"><span data-stu-id="49f35-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="49f35-132">Die oben erwähnte Seite enthält Abschnitte zu jeder verfügbaren Installation.</span><span class="sxs-lookup"><span data-stu-id="49f35-132">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="49f35-133">Die meisten zu installierenden Komponenten sind einem Paket-Manager zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="49f35-133">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="49f35-134">Wenn Sie den Node.js-Paket-Manager `npm` installiert haben, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="49f35-134">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="49f35-135">Installieren Sie andernfalls das aktuelle NodeJS von [nodejs.org](https://nodejs.org), sodass der npm-Paket-Manager installiert wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-135">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="49f35-136">An diesem Punkt müssen Sie eine Reihe von Befehlszeilentools installieren, die die ASP.NET Core-Entwicklung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="49f35-136">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="49f35-137">Die Befehlszeilenvorlagen verwenden Yeoman, Bower, Grunt und Gulp.</span><span class="sxs-lookup"><span data-stu-id="49f35-137">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="49f35-138">Sie haben sie bereits installiert? Hervorragend – geben Sie andernfalls Folgendes in Ihre bevorzugte Shell ein:</span><span class="sxs-lookup"><span data-stu-id="49f35-138">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="49f35-139">Die `-g`-Option gibt an, dass dies eine globale Installation ist, und diese Tools im gesamten System verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-139">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="49f35-140">(Eine lokale Installation beschränkt das Paket auf ein einzelnes Projekt).</span><span class="sxs-lookup"><span data-stu-id="49f35-140">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="49f35-141">Nachdem Sie diese wesentlichen Tools installiert haben, müssen Sie die ASP.NET-Vorlagengeneratoren installieren:</span><span class="sxs-lookup"><span data-stu-id="49f35-141">Once you've installed those core tools, you need to install the yeoman ASP.NET template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="49f35-142">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="49f35-142">Create the Application</span></span>

<span data-ttu-id="49f35-143">Da Sie nun alle Tools installiert haben, können Sie eine neue ASP.NET Core-Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="49f35-143">Now that you've installed all the tools, create a new ASP.NET Core application.</span></span> <span data-ttu-id="49f35-144">Um den Befehlszeilengenerator zu verwenden, führen Sie den folgenden Yeoman-Befehl in Ihrer bevorzugten Shell aus:</span><span class="sxs-lookup"><span data-stu-id="49f35-144">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="49f35-145">Dieser Befehl fordert Sie auf, auszuwählen, welchen Anwendungstyp Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="49f35-145">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="49f35-146">Für diesen Microservice sollten Sie die unkomplizierteste Webanwendung wählen, also wählen Sie „Leere Web-Anwendung“ aus.</span><span class="sxs-lookup"><span data-stu-id="49f35-146">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="49f35-147">Die Vorlage fordert Sie zur Eingabe eines Namens auf.</span><span class="sxs-lookup"><span data-stu-id="49f35-147">The template will prompt you for a name.</span></span> <span data-ttu-id="49f35-148">Wählen Sie „WeatherMicroservice“.</span><span class="sxs-lookup"><span data-stu-id="49f35-148">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="49f35-149">Die Vorlage erstellt acht Dateien für Sie:</span><span class="sxs-lookup"><span data-stu-id="49f35-149">The template creates eight files for you:</span></span>

* <span data-ttu-id="49f35-150">Eine für ASP.NET Core-Anwendungen angepasste GITIGNORE-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-150">A .gitignore, customized for ASP.NET Core applications.</span></span>
* <span data-ttu-id="49f35-151">Eine Startup.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-151">A Startup.cs file.</span></span> <span data-ttu-id="49f35-152">Diese enthält die Grundlage für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="49f35-152">This contains the basis of the application.</span></span>
* <span data-ttu-id="49f35-153">Eine Program.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-153">A Program.cs file.</span></span> <span data-ttu-id="49f35-154">Diese enthält den Einstiegspunkt für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="49f35-154">This contains the entry point of the application.</span></span>
* <span data-ttu-id="49f35-155">Eine WeatherMicroservice.csproj-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-155">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="49f35-156">Dies ist die Build-Datei für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="49f35-156">This is the build file for the application.</span></span>
* <span data-ttu-id="49f35-157">Die Docker-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-157">A Dockerfile.</span></span> <span data-ttu-id="49f35-158">Dieses Skript erstellt ein Docker-Image für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="49f35-158">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="49f35-159">Eine README.md-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-159">A README.md.</span></span> <span data-ttu-id="49f35-160">Diese enthält Links zu anderen ASP.NET Core-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="49f35-160">This contains links to other ASP.NET Core resources.</span></span>
* <span data-ttu-id="49f35-161">Eine web.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-161">A web.config file.</span></span> <span data-ttu-id="49f35-162">Diese enthält grundlegende Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="49f35-162">This contains basic configuration information.</span></span>
* <span data-ttu-id="49f35-163">Eine runtimeconfig.template.json-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-163">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="49f35-164">Diese enthält von IDEs verwendete Debugeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="49f35-164">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="49f35-165">Jetzt können Sie die von der Vorlage generierte Anwendung ausführen.</span><span class="sxs-lookup"><span data-stu-id="49f35-165">Now you can run the template generated application.</span></span> <span data-ttu-id="49f35-166">Dies geschieht mithilfe einer Reihe von Tools von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="49f35-166">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="49f35-167">Der `dotnet`-Befehl führt die erforderlichen Tools für die .NET-Entwicklung aus.</span><span class="sxs-lookup"><span data-stu-id="49f35-167">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="49f35-168">Jedes Verb führt einen anderen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="49f35-168">Each verb executes a different command</span></span>

<span data-ttu-id="49f35-169">Der erste Schritt besteht im Wiederherstellen aller Abhängigkeiten:</span><span class="sxs-lookup"><span data-stu-id="49f35-169">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="49f35-170">Die Dotnet-Wiederherstellung verwendet den NuGet-Paket-Manager, um alle erforderlichen Pakete im Verzeichnis der Anwendung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-170">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="49f35-171">Sie generiert außerdem eine project.json.lock-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-171">It also generates a project.json.lock file.</span></span> <span data-ttu-id="49f35-172">Diese Datei enthält Informationen zu jedem Paket, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-172">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="49f35-173">Nach der Wiederherstellung alle Abhängigkeiten erstellen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="49f35-173">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="49f35-174">Sobald Sie die Anwendung erstellen, führen Sie sie über die Befehlszeile aus:</span><span class="sxs-lookup"><span data-stu-id="49f35-174">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="49f35-175">Die Standardkonfiguration lauscht auf `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="49f35-175">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="49f35-176">Wenn Sie den Browser öffnen und zu dieser Seite navigieren, sehen Sie ein „Hello World!“.</span><span class="sxs-lookup"><span data-stu-id="49f35-176">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="49f35-177">Vorgang nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="49f35-177">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="49f35-178">Anatomie einer ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="49f35-178">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="49f35-179">Da Sie jetzt die Anwendung erstellt haben, können wir nun die Implementierung dieser Funktionalität betrachten.</span><span class="sxs-lookup"><span data-stu-id="49f35-179">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="49f35-180">Zwei der generierten Dateien sind hier besonders interessant: „project.json“ und „Startup.cs“.</span><span class="sxs-lookup"><span data-stu-id="49f35-180">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="49f35-181">„project.json“ enthält Informationen zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="49f35-181">Project.json contains information about the project.</span></span> <span data-ttu-id="49f35-182">Sie werden häufig mit den beiden Knoten „Abhängigkeiten“ und „Frameworks“ arbeiten.</span><span class="sxs-lookup"><span data-stu-id="49f35-182">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="49f35-183">Der Abhängigkeiten-Knoten listet alle Pakete auf, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-183">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="49f35-184">Im Moment ist dies ein kleiner Knoten, der nur die Pakete benötigt, die den Webserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="49f35-184">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="49f35-185">Der frameworks-Knoten gibt die Versionen und Konfigurationen des .NET Framework an, das diese Anwendung ausführen wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-185">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="49f35-186">Die Anwendung wird in „Startup.cs“ implementiert.</span><span class="sxs-lookup"><span data-stu-id="49f35-186">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="49f35-187">Diese Datei enthält die Startklasse.</span><span class="sxs-lookup"><span data-stu-id="49f35-187">This file contains the startup class.</span></span>

<span data-ttu-id="49f35-188">Die beiden Methoden werden von der ASP.NET Core-Infrastruktur zum Konfigurieren und Ausführen der Anwendung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="49f35-188">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="49f35-189">Die `ConfigureServices`-Methode beschreibt die Dienste, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-189">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="49f35-190">Sie erstellen einen einfachen Microservice, sodass keine Abhängigkeiten konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="49f35-190">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="49f35-191">Die `Configure`-Methode konfiguriert die Handler für eingehende HTTP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="49f35-191">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="49f35-192">Die Vorlage erstellt einen einfachen Handler, der auf jede Anforderung mit dem Text „Hello World!“ reagiert.</span><span class="sxs-lookup"><span data-stu-id="49f35-192">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="49f35-193">Erstellen eines Microservice</span><span class="sxs-lookup"><span data-stu-id="49f35-193">Build a microservice</span></span>

<span data-ttu-id="49f35-194">Sie werden einen Dienst erstellen, der Wetterberichte aus aller Welt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="49f35-194">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="49f35-195">In einer Produktionsanwendung würden Sie einen Dienst aufrufen, um Wetterdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="49f35-195">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="49f35-196">In diesem Beispiel generieren wir einen zufälligen Wetterbericht.</span><span class="sxs-lookup"><span data-stu-id="49f35-196">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="49f35-197">Sie müssen eine Reihe von Aufgaben ausführen, um unseren zufälligen Wetterdienst zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="49f35-197">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="49f35-198">Analysieren der eingehenden Anforderung, um den Breiten- und Längengrad zu lesen.</span><span class="sxs-lookup"><span data-stu-id="49f35-198">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="49f35-199">Generieren einiger zufälliger Vorhersagedaten.</span><span class="sxs-lookup"><span data-stu-id="49f35-199">Generate some random forecast data.</span></span>
* <span data-ttu-id="49f35-200">Konvertieren dieser zufälligen Vorhersagedaten von C#-Objekten in JSON-Pakete.</span><span class="sxs-lookup"><span data-stu-id="49f35-200">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="49f35-201">Festlegen des Antwortheaders, um anzugeben, dass Ihr Dienst JSON-Daten zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="49f35-201">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="49f35-202">Schreiben der Antwort.</span><span class="sxs-lookup"><span data-stu-id="49f35-202">Write the response.</span></span>

<span data-ttu-id="49f35-203">In den nächsten Abschnitten werden diese Schritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="49f35-203">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="49f35-204">Analyse der Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49f35-204">Parsing the Query String.</span></span>

<span data-ttu-id="49f35-205">Sie beginnen mit der Analyse der Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49f35-205">You'll begin by parsing the query string.</span></span> <span data-ttu-id="49f35-206">Der Dienst nimmt die Argumente „lat“ und „long“ in der Abfragezeichenfolge in diesem Formular entgegen:</span><span class="sxs-lookup"><span data-stu-id="49f35-206">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="49f35-207">Alle Änderungen, die Sie vornehmen müssen, sind in dem Lambdaausdruck enthalten, der in Ihrer Startklasse als Argument für `app.Run` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="49f35-207">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="49f35-208">Das Argument des Lambdaausdrucks ist der `HttpContext` für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="49f35-208">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="49f35-209">Eine seiner Eigenschaften ist das `Request`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="49f35-209">One of its properties is the `Request` object.</span></span> <span data-ttu-id="49f35-210">Das `Request`-Objekt verfügt über eine `Query`-Eigenschaft, die ein Wörterbuch aller Werte in der Abfragezeichenfolge für die Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="49f35-210">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="49f35-211">Die erste Addition besteht darin, die Werte für Breiten- und Längengrad zu finden:</span><span class="sxs-lookup"><span data-stu-id="49f35-211">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="49f35-212">Die Abfrage-Wörterbuchwerte sind vom Typ `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="49f35-212">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="49f35-213">Dieser Typ kann eine Auflistung von Zeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="49f35-213">That type can contain a collection of strings.</span></span> <span data-ttu-id="49f35-214">Für Ihren Wetterdienst ist jeder Wert eine einzelne Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49f35-214">For your weather service, each value is a single string.</span></span> <span data-ttu-id="49f35-215">Daher erfolgt der Aufruf von `FirstOrDefault()` im obigen Code.</span><span class="sxs-lookup"><span data-stu-id="49f35-215">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="49f35-216">Als Nächstes müssen Sie die Zeichenfolgen in Double-Werte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-216">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="49f35-217">Die Methode, mit der Sie die Zeichenfolge in einen Double-Wert konvertieren, ist `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="49f35-217">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="49f35-218">Diese Methode nutzt C#-out-Parameter, um anzugeben, ob die Eingabezeichenfolge in einen Double-Wert konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="49f35-218">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="49f35-219">Wenn die Zeichenfolge einen gültigen Double-Wert darstellt, gibt die Methode „true“ zurück, und das `result`-Argument enthält den Wert.</span><span class="sxs-lookup"><span data-stu-id="49f35-219">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="49f35-220">Wenn die Zeichenfolge keinen gültigen Double-Wert darstellt, gibt die Methode „false“ zurück.</span><span class="sxs-lookup"><span data-stu-id="49f35-220">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="49f35-221">Sie können diese API mithilfe einer *Erweiterungsmethode* anpassen, die einen *Nullable-Double-Wert*  zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="49f35-221">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="49f35-222">Ein *Nullable-Werttyp* ist ein Typ, der einen Werttyp darstellt und auch einen fehlenden, d.h. NULL-Wert enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="49f35-222">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="49f35-223">Ein Nullable-Typ wird durch Anhängen des `?`-Zeichens an die Typdeklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="49f35-223">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="49f35-224">Erweiterungsmethoden sind als statische Methoden definierte Methoden, können aber durch Hinzufügen des `this`-Modifizierers zum ersten Parameter so aufgerufen werden, als ob sie Member dieser Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-224">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="49f35-225">Erweiterungsmethoden können nur in statischen Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="49f35-225">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="49f35-226">Hier ist die Definition der Klasse, die die Erweiterungsmethode für die Analyse enthält:</span><span class="sxs-lookup"><span data-stu-id="49f35-226">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="49f35-227">Der `default(double?)`-Ausdruck gibt den Standardwert für den `double?`-Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="49f35-227">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="49f35-228">Dieser Standardwert ist der NULL-Wert (oder nicht vorhandener Wert).</span><span class="sxs-lookup"><span data-stu-id="49f35-228">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="49f35-229">Sie können diese Erweiterungsmethode verwenden, um die Abfragezeichenfolgen-Argumente in den Double-Typ zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="49f35-229">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="49f35-230">Um den Analysecode mühelos zu testen, aktualisieren Sie die Antwort so, dass sie die Werte der Argumente enthält:</span><span class="sxs-lookup"><span data-stu-id="49f35-230">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="49f35-231">An diesem Punkt können Sie die Webanwendung ausführen und prüfen, ob Ihr Analysecode funktioniert.</span><span class="sxs-lookup"><span data-stu-id="49f35-231">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="49f35-232">Fügen Sie der Webanforderung in einem Browser Werte hinzu, und Sie sollten die aktualisierten Ergebnisse sehen.</span><span class="sxs-lookup"><span data-stu-id="49f35-232">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="49f35-233">Erstellen einer zufälligen Wettervorhersage</span><span class="sxs-lookup"><span data-stu-id="49f35-233">Build a random weather forecast</span></span>

<span data-ttu-id="49f35-234">Ihre nächste Aufgabe ist das Erstellen einer zufälligen Wettervorhersage.</span><span class="sxs-lookup"><span data-stu-id="49f35-234">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="49f35-235">Wir beginnen mit einem Datencontainer, der die Werte enthält, die Sie für einen Wetterbericht wünschen:</span><span class="sxs-lookup"><span data-stu-id="49f35-235">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

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

<span data-ttu-id="49f35-236">Als Nächstes erstellen Sie einen Konstruktor, der diese Werte nach dem Zufallsprinzip festlegt.</span><span class="sxs-lookup"><span data-stu-id="49f35-236">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="49f35-237">Dieser Konstruktor verwendet die Werte für den Breiten- und Längengrad, um den Zufallszahlengenerator zu starten.</span><span class="sxs-lookup"><span data-stu-id="49f35-237">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="49f35-238">Das bedeutet, dass die Vorhersage für den gleichen Ort identisch ist.</span><span class="sxs-lookup"><span data-stu-id="49f35-238">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="49f35-239">Wenn Sie die Argumente für den Breiten- und Längengrad ändern, erhalten Sie eine andere Vorhersage (weil Sie mit einem anderen Startwert beginnen.)</span><span class="sxs-lookup"><span data-stu-id="49f35-239">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="49f35-240">Sie können jetzt die 5-Tage-Wettervorhersage in Ihrer Antwortmethode generieren:</span><span class="sxs-lookup"><span data-stu-id="49f35-240">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="49f35-241">Erstellen Sie die JSON-Antwort.</span><span class="sxs-lookup"><span data-stu-id="49f35-241">Build the JSON response.</span></span>

<span data-ttu-id="49f35-242">Die letzte Codierungsaufgabe auf dem Server ist, das WeatherReport-Array in ein JSON-Paket zu konvertieren und dieses an den Client zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="49f35-242">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="49f35-243">Wir erstellen zunächst das JSON-Paket.</span><span class="sxs-lookup"><span data-stu-id="49f35-243">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="49f35-244">Sie fügen das NewtonSoft JSON-Serialisierungsprogramm der Liste der Abhängigkeiten hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f35-244">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="49f35-245">Verwenden Sie hierzu die `dotnet`-CLI:</span><span class="sxs-lookup"><span data-stu-id="49f35-245">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="49f35-246">Anschließend können Sie das Objekt mithilfe der `JsonConvert`-Klasse in eine Zeichenfolge schreiben:</span><span class="sxs-lookup"><span data-stu-id="49f35-246">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="49f35-247">Der obige Code konvertiert das Vorhersageobjekt (eine Liste der `WeatherForecast`-Objekte) in ein JSON-Paket.</span><span class="sxs-lookup"><span data-stu-id="49f35-247">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="49f35-248">Nachdem Sie das Antwortpaket erstellt haben, legen Sie den Inhaltstyp auf `application/json` fest, und schreiben Sie die Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="49f35-248">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="49f35-249">Die Anwendung wird jetzt ausgeführt und gibt zufällige Vorhersagen zurück.</span><span class="sxs-lookup"><span data-stu-id="49f35-249">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="49f35-250">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="49f35-250">Build a Docker image</span></span>

<span data-ttu-id="49f35-251">Unsere letzte Aufgabe ist das Ausführen der Anwendung in Docker.</span><span class="sxs-lookup"><span data-stu-id="49f35-251">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="49f35-252">Wir erstellen einen Docker-Container, der ein Docker-Image ausführt, das die Anwendung darstellt.</span><span class="sxs-lookup"><span data-stu-id="49f35-252">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="49f35-253">Ein ***Docker-Image*** ist eine Datei, die die Umgebung für die Ausführung der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="49f35-253">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="49f35-254">Ein ***Docker-Container*** stellt eine ausgeführte Instanz eines Docker-Images dar.</span><span class="sxs-lookup"><span data-stu-id="49f35-254">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="49f35-255">Entsprechend können Sie sich das *Docker-Image* als eine *Klasse* und den *Docker-Container* als ein Objekt oder eine Instanz dieser Klasse vorstellen.</span><span class="sxs-lookup"><span data-stu-id="49f35-255">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="49f35-256">Die von der ASP.NET-Vorlage erstellte Docker-Datei ist für unsere Zwecke geeignet.</span><span class="sxs-lookup"><span data-stu-id="49f35-256">The Dockerfile created by the ASP.NET template will serve for our purposes.</span></span> <span data-ttu-id="49f35-257">Betrachten wir ihren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="49f35-257">Let's go over its contents.</span></span>

<span data-ttu-id="49f35-258">Die erste Zeile gibt das Quellimage an:</span><span class="sxs-lookup"><span data-stu-id="49f35-258">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="49f35-259">Mit Docker können Sie ein Computerimage auf Basis einer Quellvorlage konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49f35-259">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="49f35-260">Das bedeutet, Sie müssen beim Start nicht alle Computerparameter, sondern nur Änderungen angeben.</span><span class="sxs-lookup"><span data-stu-id="49f35-260">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="49f35-261">Hier dienen die Änderungen dazu, unsere Anwendung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="49f35-261">The changes here will be to include our application.</span></span>

<span data-ttu-id="49f35-262">In diesem ersten Beispiel verwenden wir die `1.1-sdk-msbuild`-Version des Dotnet-Images.</span><span class="sxs-lookup"><span data-stu-id="49f35-262">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="49f35-263">Dies ist die einfachste Möglichkeit zum Erstellen einer funktionierenden Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="49f35-263">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="49f35-264">Dieses Image enthält die Dotnet Core-Laufzeit und das Dotnet SDK.</span><span class="sxs-lookup"><span data-stu-id="49f35-264">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="49f35-265">Dies vereinfacht den Einstieg und das Erstellen, erstellt aber kein größeres Image.</span><span class="sxs-lookup"><span data-stu-id="49f35-265">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="49f35-266">Die nächsten fünf Zeilen richten die Anwendung ein und erstellen sie:</span><span class="sxs-lookup"><span data-stu-id="49f35-266">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroService.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="49f35-267">Dadurch wird die Projektdatei aus dem aktuellen Verzeichnis in die Docker-VM kopiert, und alle Pakete werden wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="49f35-267">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="49f35-268">Die Verwendung der Dotnet-CLI bedeutet, dass das Docker-Image das .NET Core-SDK einbeziehen muss.</span><span class="sxs-lookup"><span data-stu-id="49f35-268">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="49f35-269">Danach wird der Rest der Anwendung kopiert, und der Dotnet-publish-Befehl erstellt Ihre Anwendung und macht daraus ein Paket.</span><span class="sxs-lookup"><span data-stu-id="49f35-269">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="49f35-270">Die letzte Zeile der Datei führt die Anwendung aus:</span><span class="sxs-lookup"><span data-stu-id="49f35-270">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroService.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="49f35-271">Auf diesen konfigurierten Port wird im `--server.urls`-Argument für `dotnet` in der letzten Zeile der Docker-Datei verwiesen.</span><span class="sxs-lookup"><span data-stu-id="49f35-271">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="49f35-272">Der `ENTRYPOINT`-Befehl teilt Docker mit, welcher Befehl und welche Befehlszeilenoptionen den Dienst starten.</span><span class="sxs-lookup"><span data-stu-id="49f35-272">The `ENTRYPOINT` command informs Docker what command and command-line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="49f35-273">Erstellen und Ausführen des Images in einem Container</span><span class="sxs-lookup"><span data-stu-id="49f35-273">Building and running the image in a container.</span></span>

<span data-ttu-id="49f35-274">Wir erstellen ein Image und führen den Dienst in einem Docker-Container aus.</span><span class="sxs-lookup"><span data-stu-id="49f35-274">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="49f35-275">Nicht alle Dateien in Ihrem lokalen Verzeichnis sollen in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="49f35-275">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="49f35-276">Stattdessen erstellen Sie die Anwendung im Container.</span><span class="sxs-lookup"><span data-stu-id="49f35-276">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="49f35-277">Sie erstellen eine `.dockerignore`-Datei, um die Verzeichnisse festzulegen, die nicht in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="49f35-277">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="49f35-278">Kein Buildobjekt soll kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="49f35-278">You don't want any of the build assets copied.</span></span> <span data-ttu-id="49f35-279">Geben Sie die Verzeichnisse für Build und Veröffentlichung in der `.dockerignore`-Datei an:</span><span class="sxs-lookup"><span data-stu-id="49f35-279">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="49f35-280">Sie erstellen das Image mithilfe des `docker build`-Befehls.</span><span class="sxs-lookup"><span data-stu-id="49f35-280">You build the image using the `docker build` command.</span></span> <span data-ttu-id="49f35-281">Führen Sie den folgenden Befehl in dem Verzeichnis aus, das Ihren Code enthält.</span><span class="sxs-lookup"><span data-stu-id="49f35-281">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="49f35-282">Dieser Befehl erstellt das Containerimage basierend auf allen Informationen in Ihrer Docker-Datei.</span><span class="sxs-lookup"><span data-stu-id="49f35-282">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="49f35-283">Das `-t`-Argument liefert ein Tag, d.h. einen Namen, für dieses Containerimage.</span><span class="sxs-lookup"><span data-stu-id="49f35-283">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="49f35-284">In der Befehlszeile oben wird das Tag `weather-microservice` für den Docker-Container verwendet.</span><span class="sxs-lookup"><span data-stu-id="49f35-284">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="49f35-285">Nach Abschluss dieses Befehls verfügen Sie über einen Container, in dem Sie den neuen Dienst ausführen können.</span><span class="sxs-lookup"><span data-stu-id="49f35-285">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="49f35-286">Führen Sie den folgenden Befehl zum Starten des Containers aus, und starten Sie Ihren Dienst:</span><span class="sxs-lookup"><span data-stu-id="49f35-286">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="49f35-287">Die `-d`-Option bedeutet, den Container unabhängig vom aktuellen Terminal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="49f35-287">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="49f35-288">Dies bedeutet, dass die Ausgabe des Befehls nicht auf Ihrem Terminal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-288">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="49f35-289">Die `-p`-Option gibt die Portzuordnung zwischen dem Dienst und dem Host an.</span><span class="sxs-lookup"><span data-stu-id="49f35-289">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="49f35-290">Hier gibt sie an, dass jede an Port 80 eingehende Anforderung an Port 5000 im Container weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="49f35-290">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="49f35-291">5000 entspricht dem Port, auf den der Dienst über die Befehlszeilenargumente lauscht, die in der oben genannten Docker-Datei angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="49f35-291">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="49f35-292">Das `--name`-Argument benennt den ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="49f35-292">The `--name` argument names your running container.</span></span> <span data-ttu-id="49f35-293">Es ist ein praktischer Name, den Sie zum Arbeiten mit dem betreffenden Container verwenden können.</span><span class="sxs-lookup"><span data-stu-id="49f35-293">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="49f35-294">Sie können sehen, ob das Image ausgeführt wird, indem Sie den Befehl überprüfen:</span><span class="sxs-lookup"><span data-stu-id="49f35-294">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="49f35-295">Wenn der Container ausgeführt wird, sehen Sie eine Zeile, in der er als ausgeführter Prozess aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-295">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="49f35-296">(Vielleicht ist er der einzige).</span><span class="sxs-lookup"><span data-stu-id="49f35-296">(It may be the only one).</span></span>

<span data-ttu-id="49f35-297">Sie können Ihren Dienst testen, indem Sie einen Browser öffnen, zu „localhost“ navigieren und einen Breiten- und Längengrad angeben:</span><span class="sxs-lookup"><span data-stu-id="49f35-297">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="49f35-298">Anfügen an einen ausgeführten Container</span><span class="sxs-lookup"><span data-stu-id="49f35-298">Attaching to a running container</span></span>

<span data-ttu-id="49f35-299">Bei der Ausführung Ihres Diensts in einem Befehlsfenster konnten Sie sehen, dass für jede Anforderung Diagnoseinformationen ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="49f35-299">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="49f35-300">Diese Informationen werden nicht angezeigt, wenn der Container im getrennten Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49f35-300">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="49f35-301">Der Docker-attach-Befehl ermöglicht Ihnen das Anfügen an einen ausgeführten Container, sodass Sie die Protokollinformationen sehen können.</span><span class="sxs-lookup"><span data-stu-id="49f35-301">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="49f35-302">Führen Sie diesen Befehl in einem Befehlsfenster aus:</span><span class="sxs-lookup"><span data-stu-id="49f35-302">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="49f35-303">Das `--sig-proxy=false`-Argument bedeutet, dass `Ctrl-C`-Befehle nicht an den Containerprozess gesendet werden, aber stattdessen den `docker attach`-Befehl beenden.</span><span class="sxs-lookup"><span data-stu-id="49f35-303">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="49f35-304">Das letzte Argument ist der Name, den der Container im `docker run`-Befehl erhält.</span><span class="sxs-lookup"><span data-stu-id="49f35-304">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="49f35-305">Sie können auch die von Docker zugewiesene Container-ID verwenden, um auf einen Container zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="49f35-305">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="49f35-306">Wenn Sie in `docker run` keinen Namen für den Container angegeben haben, müssen Sie die Container-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="49f35-306">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="49f35-307">Öffnen Sie einen Browser, und navigieren Sie zu Ihrem Dienst.</span><span class="sxs-lookup"><span data-stu-id="49f35-307">Open a browser and navigate to your service.</span></span> <span data-ttu-id="49f35-308">Sie sehen die Diagnosemeldungen des angefügten ausgeführten Containers in den Befehlsfenstern.</span><span class="sxs-lookup"><span data-stu-id="49f35-308">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="49f35-309">Drücken Sie `Ctrl-C`, um den Anfügungsprozess zu beenden.</span><span class="sxs-lookup"><span data-stu-id="49f35-309">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="49f35-310">Wenn Sie die Arbeit mit Ihrem Container abgeschlossen haben, können Sie ihn stoppen:</span><span class="sxs-lookup"><span data-stu-id="49f35-310">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="49f35-311">Container und Image stehen weiterhin für einen Neustart zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49f35-311">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="49f35-312">Wenn Sie den Container von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="49f35-312">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="49f35-313">Wenn Sie nicht benutzte Images von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="49f35-313">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="49f35-314">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="49f35-314">Conclusion</span></span> 

<span data-ttu-id="49f35-315">In diesem Tutorial haben Sie einen ASP.NET Core-Microservice erstellt und einige einfache Features hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="49f35-315">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="49f35-316">Sie haben ein Docker-Containerimage für diesen Dienst erstellt und diesen Container auf dem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="49f35-316">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="49f35-317">Sie haben dem Dienst ein Terminalfenster angefügt und die Diagnosemeldungen Ihres Diensts gesehen.</span><span class="sxs-lookup"><span data-stu-id="49f35-317">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="49f35-318">Nebenbei haben Sie verschiedene Features der C#-Sprache in Aktion gesehen.</span><span class="sxs-lookup"><span data-stu-id="49f35-318">Along the way, you saw several features of the C# language in action.</span></span>
