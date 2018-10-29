---
title: In Docker gehostete Microservices – C#
description: Erfahren Sie, wie Sie ASP.NET Core-Dienste erstellen, die in Docker-Containern ausgeführt werden.
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: b1f7159a222ab4d68715844e9997ca922676bc80
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454485"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="ee7bb-103">In Docker gehostete Microservices</span><span class="sxs-lookup"><span data-stu-id="ee7bb-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="ee7bb-104">In diesem Tutorial werden die erforderlichen Aufgaben zum Erstellen und Bereitstellen eines ASP.NET Core-Microservice in einem Docker-Container erläutert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="ee7bb-105">Im Verlauf dieses Tutorials lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="ee7bb-106">Erstellen einer ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee7bb-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="ee7bb-107">Erstellen einer Docker-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="ee7bb-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="ee7bb-108">Erstellen eines Docker-Images basierend auf einem vorhandenen Image</span><span class="sxs-lookup"><span data-stu-id="ee7bb-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="ee7bb-109">Bereitstellen Ihres Diensts in einem Docker-Container</span><span class="sxs-lookup"><span data-stu-id="ee7bb-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="ee7bb-110">Dabei lernen Sie auch einige C#-Sprachfunktionen kennen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="ee7bb-111">Konvertieren von C#-Objekten in JSON-Nutzlasten</span><span class="sxs-lookup"><span data-stu-id="ee7bb-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="ee7bb-112">Erstellen unveränderlicher Datenübertragungsobjekte</span><span class="sxs-lookup"><span data-stu-id="ee7bb-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="ee7bb-113">Verarbeiten eingehender HTTP-Anforderungen und Erstellen der HTTP-Antwort</span><span class="sxs-lookup"><span data-stu-id="ee7bb-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="ee7bb-114">Arbeiten mit Nullable-Werttypen</span><span class="sxs-lookup"><span data-stu-id="ee7bb-114">How to work with nullable value types.</span></span>

<span data-ttu-id="ee7bb-115">Sie können die Beispiel-App für dieses Thema [anzeigen oder herunterladen](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice).</span><span class="sxs-lookup"><span data-stu-id="ee7bb-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="ee7bb-116">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ee7bb-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="ee7bb-117">Warum Docker?</span><span class="sxs-lookup"><span data-stu-id="ee7bb-117">Why Docker?</span></span>

<span data-ttu-id="ee7bb-118">Docker erleichtert das Erstellen von standardmäßigen Computerimages zum Hosten Ihrer Dienste in einem Rechenzentrum oder der öffentlichen Cloud.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="ee7bb-119">Mit Docker können Sie das Image konfigurieren und nach Bedarf replizieren, um die Installation der Anwendung zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="ee7bb-120">Der gesamte Code in diesem Tutorial ist in einer beliebigen .NET Core-Umgebung einsetzbar.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="ee7bb-121">Die zusätzlichen Aufgaben für eine Docker-Installation funktionieren in Verbindung mit einer ASP.NET Core-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ee7bb-122">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ee7bb-122">Prerequisites</span></span>

<span data-ttu-id="ee7bb-123">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="ee7bb-124">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="ee7bb-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="ee7bb-125">Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="ee7bb-126">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="ee7bb-127">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="ee7bb-128">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="ee7bb-129">Sie müssen auch die Docker-Engine installieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="ee7bb-130">Anweisungen für Ihre Plattform finden Sie auf der [Docker-Installationsseite](https://docs.docker.com/install/overview/).</span><span class="sxs-lookup"><span data-stu-id="ee7bb-130">See the [Docker Installation page](https://docs.docker.com/install/overview/) for instructions for your platform.</span></span>
<span data-ttu-id="ee7bb-131">Docker kann in vielen Linux-Distributionen, unter macOS oder Windows installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="ee7bb-132">Die oben erwähnte Seite enthält Abschnitte zu jeder verfügbaren Installation.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="ee7bb-133">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee7bb-133">Create the Application</span></span>

<span data-ttu-id="ee7bb-134">Da Sie nun alle Tools installiert haben, erstellen Sie eine neue ASP.NET Core-Anwendung in einem Verzeichnis namens „WeatherMicroservice“, indem Sie den folgenden Befehl in Ihrer bevorzugten Shell ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="ee7bb-135">Der `dotnet`-Befehl führt die erforderlichen Tools für die .NET-Entwicklung aus.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="ee7bb-136">Jedes Verb führt einen anderen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-136">Each verb executes a different command.</span></span>

<span data-ttu-id="ee7bb-137">Mit dem `dotnet new`-Befehl werden .NET Core-Projekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="ee7bb-138">Die Option `-o WeatherMicroservice` nach dem Befehl `dotnet new` wird verwendet, um den Speicherort für die Erstellung der ASP.NET Core-Anwendung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="ee7bb-139">Da für diesen Microservice eine möglichst einfache und kompakte Webanwendung zum Einsatz kommen soll, wurde die Vorlage „ASP.NET Core leer“ durch Angabe des Kurznamens `web` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="ee7bb-140">Die Vorlage erstellt vier Dateien:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-140">The template creates four files for you:</span></span>

* <span data-ttu-id="ee7bb-141">Eine Startup.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-141">A Startup.cs file.</span></span> <span data-ttu-id="ee7bb-142">Diese enthält die Grundlage für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="ee7bb-143">Eine Program.cs-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-143">A Program.cs file.</span></span> <span data-ttu-id="ee7bb-144">Diese enthält den Einstiegspunkt für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="ee7bb-145">Eine WeatherMicroservice.csproj-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="ee7bb-146">Dies ist die Build-Datei für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-146">This is the build file for the application.</span></span>
* <span data-ttu-id="ee7bb-147">Die Datei „launchSettings.json“ im Ordner „Properties“.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="ee7bb-148">Diese enthält von IDEs verwendete Debugeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="ee7bb-149">Jetzt können Sie die von der Vorlage generierte Anwendung ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="ee7bb-150">Durch diesen Befehl werden zuerst die Abhängigkeiten wiederhergestellt, die zur Erstellung der Anwendung benötigt werden. Anschließend wird die Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="ee7bb-151">Die Standardkonfiguration lauscht auf `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="ee7bb-152">Wenn Sie den Browser öffnen und zu dieser Seite navigieren, sehen Sie ein „Hello World!“.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="ee7bb-153">Vorgang nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-153">message.</span></span>

<span data-ttu-id="ee7bb-154">Abschließend können Sie die Anwendung beenden, indem Sie <kbd>STRG</kbd>+<kbd>C</kbd> drücken.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="ee7bb-155">Anatomie einer ASP.NET Core-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee7bb-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="ee7bb-156">Da Sie jetzt die Anwendung erstellt haben, können wir nun die Implementierung dieser Funktionalität betrachten.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="ee7bb-157">Zwei der generierten Dateien sind hier besonders interessant: „WeatherMicroservice.csproj“ und „Startup.cs“.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="ee7bb-158">Die CSPROJ-Datei enthält Informationen zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="ee7bb-159">Besonders interessant sind die beiden Knoten `<TargetFramework>` und `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="ee7bb-160">Im Knoten `<TargetFramework>` wird die Version von .NET festgelegt, unter der diese Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="ee7bb-161">Mit den `<PackageReference>`-Knoten werden Pakete angegeben, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="ee7bb-162">Die Anwendung wird in „Startup.cs“ implementiert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="ee7bb-163">Diese Datei enthält die Startklasse.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-163">This file contains the startup class.</span></span>

<span data-ttu-id="ee7bb-164">Die beiden Methoden werden von der ASP.NET Core-Infrastruktur zum Konfigurieren und Ausführen der Anwendung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="ee7bb-165">Die `ConfigureServices`-Methode beschreibt die Dienste, die für diese Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="ee7bb-166">Sie erstellen einen einfachen Microservice, sodass keine Abhängigkeiten konfiguriert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="ee7bb-167">Die `Configure`-Methode konfiguriert die Handler für eingehende HTTP-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="ee7bb-168">Die Vorlage erstellt einen einfachen Handler, der auf jede Anforderung mit dem Text „Hello World!“ reagiert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="ee7bb-169">Erstellen eines Microservice</span><span class="sxs-lookup"><span data-stu-id="ee7bb-169">Build a microservice</span></span>

<span data-ttu-id="ee7bb-170">Sie werden einen Dienst erstellen, der Wetterberichte aus aller Welt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="ee7bb-171">In einer Produktionsanwendung würden Sie einen Dienst aufrufen, um Wetterdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="ee7bb-172">In diesem Beispiel generieren wir einen zufälligen Wetterbericht.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="ee7bb-173">Sie müssen eine Reihe von Aufgaben ausführen, um unseren zufälligen Wetterdienst zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="ee7bb-174">Analysieren der eingehenden Anforderung, um den Breiten- und Längengrad zu lesen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="ee7bb-175">Generieren einiger zufälliger Vorhersagedaten.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="ee7bb-176">Konvertieren dieser zufälligen Vorhersagedaten von C#-Objekten in JSON-Pakete.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="ee7bb-177">Festlegen des Antwortheaders, um anzugeben, dass Ihr Dienst JSON-Daten zurücksendet.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="ee7bb-178">Schreiben der Antwort.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-178">Write the response.</span></span>

<span data-ttu-id="ee7bb-179">In den nächsten Abschnitten werden diese Schritte erläutert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="ee7bb-180">Analysieren der Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ee7bb-180">Parsing the Query String</span></span>

<span data-ttu-id="ee7bb-181">Sie beginnen mit der Analyse der Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="ee7bb-182">Der Dienst nimmt die Argumente „lat“ und „long“ in der Abfragezeichenfolge in diesem Formular entgegen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="ee7bb-183">Alle Änderungen, die Sie vornehmen müssen, sind in dem Lambdaausdruck enthalten, der in Ihrer Startklasse als Argument für `app.Run` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="ee7bb-184">Das Argument des Lambdaausdrucks ist der `HttpContext` für die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="ee7bb-185">Eine seiner Eigenschaften ist das `Request`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="ee7bb-186">Das `Request`-Objekt verfügt über eine `Query`-Eigenschaft, die ein Wörterbuch aller Werte in der Abfragezeichenfolge für die Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="ee7bb-187">Die erste Addition besteht darin, die Werte für Breiten- und Längengrad zu finden:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="ee7bb-188">Die `Query`-Wörterbuchwerte sind vom Typ `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="ee7bb-189">Dieser Typ kann eine Auflistung von Zeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="ee7bb-190">Für Ihren Wetterdienst ist jeder Wert eine einzelne Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="ee7bb-191">Daher erfolgt der Aufruf von `FirstOrDefault()` im obigen Code.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="ee7bb-192">Als Nächstes müssen Sie die Zeichenfolgen in Double-Werte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="ee7bb-193">Die Methode, mit der Sie die Zeichenfolge in einen Double-Wert konvertieren, ist `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="ee7bb-194">Diese Methode nutzt C#-out-Parameter, um anzugeben, ob die Eingabezeichenfolge in einen Double-Wert konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="ee7bb-195">Wenn die Zeichenfolge einen gültigen Double-Wert darstellt, gibt die Methode „true“ zurück, und das `result`-Argument enthält den Wert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="ee7bb-196">Wenn die Zeichenfolge keinen gültigen Double-Wert darstellt, gibt die Methode „false“ zurück.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="ee7bb-197">Sie können diese API mithilfe einer *Erweiterungsmethode* anpassen, die einen *Nullable-Double-Wert*  zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="ee7bb-198">Ein *Nullable-Werttyp* ist ein Typ, der einen Werttyp darstellt und auch einen fehlenden, d.h. NULL-Wert enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="ee7bb-199">Ein Nullable-Typ wird durch Anhängen des `?`-Zeichens an die Typdeklaration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="ee7bb-200">Erweiterungsmethoden sind als statische Methoden definierte Methoden, können aber durch Hinzufügen des `this`-Modifizierers zum ersten Parameter so aufgerufen werden, als ob sie Member dieser Klasse sind.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="ee7bb-201">Erweiterungsmethoden können nur in statischen Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="ee7bb-202">Hier ist die Definition der Klasse, die die Erweiterungsmethode für die Analyse enthält:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="ee7bb-203">Ändern Sie vor dem Aufruf der Erweiterungsmethode die aktuelle Kultur in eine invariante Kultur:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="ee7bb-204">Dadurch wird sichergestellt, dass Ihre Anwendung Zahlen auf einem beliebigen Server unabhängig von der Standardkultur immer gleich analysiert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="ee7bb-205">Sie können die Erweiterungsmethode nun verwenden, um die Abfragezeichenfolgen-Argumente in den Double-Typ zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="ee7bb-206">Um den Analysecode mühelos zu testen, aktualisieren Sie die Antwort so, dass sie die Werte der Argumente enthält:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="ee7bb-207">An diesem Punkt können Sie die Webanwendung ausführen und prüfen, ob Ihr Analysecode funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="ee7bb-208">Fügen Sie der Webanforderung in einem Browser Werte hinzu, und Sie sollten die aktualisierten Ergebnisse sehen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="ee7bb-209">Erstellen einer zufälligen Wettervorhersage</span><span class="sxs-lookup"><span data-stu-id="ee7bb-209">Build a random weather forecast</span></span>

<span data-ttu-id="ee7bb-210">Ihre nächste Aufgabe ist das Erstellen einer zufälligen Wettervorhersage.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="ee7bb-211">Wir beginnen mit einem Datencontainer, der die Werte enthält, die Sie für einen Wetterbericht wünschen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="ee7bb-212">Als Nächstes erstellen Sie einen Konstruktor, der diese Werte nach dem Zufallsprinzip festlegt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="ee7bb-213">Dieser Konstruktor verwendet die Werte für den Breiten- und Längengrad, um den Zufallszahlengenerator `Random` mit einem Startwert zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="ee7bb-214">Das bedeutet, dass die Vorhersage für den gleichen Ort identisch ist.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="ee7bb-215">Wenn Sie die Argumente für den Breiten- und Längengrad ändern, erhalten Sie eine andere Vorhersage, weil Sie mit einem anderen Startwert beginnen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="ee7bb-216">Sie können jetzt die 5-Tage-Wettervorhersage in Ihrer Antwortmethode generieren:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="ee7bb-217">Erstellen der JSON-Antwort</span><span class="sxs-lookup"><span data-stu-id="ee7bb-217">Build the JSON response</span></span>

<span data-ttu-id="ee7bb-218">Die letzte Codeaufgabe auf dem Server besteht darin, die `WeatherReport`-Liste in ein JSON-Dokument zu konvertieren und dieses an den Client zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="ee7bb-219">Zunächst erstellen Sie ein JSON-Dokument.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="ee7bb-220">Fügen Sie das Newtonsoft-JSON-Serialisierungsmodul der Liste der Abhängigkeiten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="ee7bb-221">Hierzu können Sie den Befehl `dotnet` verwenden:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="ee7bb-222">Anschließend können Sie das Objekt mithilfe der `JsonConvert`-Klasse in eine Zeichenfolge schreiben:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="ee7bb-223">Der obige Code konvertiert das Vorhersageobjekt (eine Liste der `WeatherForecast`-Objekte) in ein JSON-Dokument.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="ee7bb-224">Nachdem Sie das Antwortdokument erstellt haben, legen Sie den Inhaltstyp auf `application/json` fest und schreiben die Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="ee7bb-225">Die Anwendung wird jetzt ausgeführt und gibt zufällige Vorhersagen zurück.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="ee7bb-226">Erstellen eines Docker-Images</span><span class="sxs-lookup"><span data-stu-id="ee7bb-226">Build a Docker image</span></span>

<span data-ttu-id="ee7bb-227">Unsere letzte Aufgabe ist das Ausführen der Anwendung in Docker.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="ee7bb-228">Wir erstellen einen Docker-Container, der ein Docker-Image ausführt, das die Anwendung darstellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="ee7bb-229">Ein ***Docker-Image*** ist eine Datei, die die Umgebung für die Ausführung der Anwendung definiert.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="ee7bb-230">Ein ***Docker-Container*** stellt eine ausgeführte Instanz eines Docker-Images dar.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="ee7bb-231">Entsprechend können Sie sich das *Docker-Image* als eine *Klasse* und den *Docker-Container* als ein Objekt oder eine Instanz dieser Klasse vorstellen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="ee7bb-232">Die folgende Docker-Datei ist für Ihre Anforderungen ausreichend:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="ee7bb-233">Betrachten wir ihren Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-233">Let's go over its contents.</span></span>

<span data-ttu-id="ee7bb-234">In der ersten Zeile wird das Quellimage angegeben, mit dem die Anwendung erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="ee7bb-235">Mit Docker können Sie ein Computerimage auf Basis einer Quellvorlage konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="ee7bb-236">Das bedeutet, Sie müssen beim Start nicht alle Computerparameter, sondern nur Änderungen angeben.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="ee7bb-237">Hier dienen die Änderungen dazu, unsere Anwendung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="ee7bb-238">In diesem Beispiel wird die `2.1-sdk`-Version des `dotnet`-Images verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="ee7bb-239">Dies ist die einfachste Möglichkeit zum Erstellen einer funktionierenden Docker-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="ee7bb-240">Dieses Image enthält die .NET Core-Runtime und das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="ee7bb-241">Dies erleichtert die ersten Schritte mit dem Image und dessen Erstellung. Das Image ist jedoch größer, weshalb dieses Image zur Erstellung der Anwendung und ein anderes Image für dessen Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="ee7bb-242">Mit den folgenden Zeilen wird die Anwendung eingerichtet und erstellt:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="ee7bb-243">Dadurch wird die Projektdatei aus dem aktuellen Verzeichnis in die Docker-VM kopiert, und alle Pakete werden wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="ee7bb-244">Die Verwendung der Dotnet-CLI bedeutet, dass das Docker-Image das .NET Core-SDK einbeziehen muss.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="ee7bb-245">Danach werden die verbleibenden Anwendungsteile kopiert, und der `dotnet
publish`-Befehl erstellt Ihre Anwendung und erzeugt daraus ein Paket.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="ee7bb-246">Abschließend erstellen Sie ein zweites Docker-Image, mit dem die Anwendung ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="ee7bb-247">Für dieses Image wird die `2.1-aspnetcore-runtime`-Version des `dotnet`-Images verwendet, das alle erforderlichen Inhalte zum Ausführen von ASP.NET Core Anwendungen enthält, jedoch nicht das .NET Core SDK beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="ee7bb-248">Dieses Image kann daher nicht zum Erstellen von .NET Core-Anwendungen verwendet werden. Gleichzeitig wird das endgültige Image dadurch allerdings kleiner.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="ee7bb-249">Kopieren Sie zum Ausführen des Vorgangs die erstellte Anwendung aus dem ersten Image, und fügen Sie es in das zweite ein.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="ee7bb-250">Durch den `ENTRYPOINT`-Befehl wird Docker darüber informiert, mit welchem Befehl der Dienst gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="ee7bb-251">Erstellen und Ausführen des Images in einem Container</span><span class="sxs-lookup"><span data-stu-id="ee7bb-251">Building and running the image in a container</span></span>

<span data-ttu-id="ee7bb-252">Wir erstellen ein Image und führen den Dienst in einem Docker-Container aus.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="ee7bb-253">Nicht alle Dateien in Ihrem lokalen Verzeichnis sollen in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="ee7bb-254">Stattdessen erstellen Sie die Anwendung im Container.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="ee7bb-255">Sie erstellen eine `.dockerignore`-Datei, um die Verzeichnisse festzulegen, die nicht in das Image kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="ee7bb-256">Kein Buildobjekt soll kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="ee7bb-257">Geben Sie die Verzeichnisse für Build und Veröffentlichung in der `.dockerignore`-Datei an:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="ee7bb-258">Sie erstellen das Image mithilfe des `docker build`-Befehls.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="ee7bb-259">Führen Sie den folgenden Befehl in dem Verzeichnis aus, das Ihren Code enthält.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="ee7bb-260">Dieser Befehl erstellt das Containerimage basierend auf allen Informationen in Ihrer Docker-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="ee7bb-261">Das `-t`-Argument liefert ein Tag, d.h. einen Namen, für dieses Containerimage.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="ee7bb-262">In der Befehlszeile oben wird das Tag `weather-microservice` für den Docker-Container verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="ee7bb-263">Nach Abschluss dieses Befehls verfügen Sie über einen Container, in dem Sie den neuen Dienst ausführen können.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="ee7bb-264">Führen Sie den folgenden Befehl zum Starten des Containers aus, und starten Sie Ihren Dienst:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="ee7bb-265">Die `-d`-Option bedeutet, den Container unabhängig vom aktuellen Terminal auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="ee7bb-266">Dies bedeutet, dass die Ausgabe des Befehls nicht auf Ihrem Terminal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="ee7bb-267">Die `-p`-Option gibt die Portzuordnung zwischen dem Dienst und dem Host an.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="ee7bb-268">In diesem Fall wird angegeben, dass jede an Port 80 eingehende Anforderung an Port 80 im Container weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="ee7bb-269">Port 80 ist der Port, auf dem Ihre Anwendung lauscht. Hierbei handelt es sich um den Standardport für Produktionsanwendungen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="ee7bb-270">Das `--name`-Argument benennt den ausgeführten Container.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="ee7bb-271">Es ist ein praktischer Name, den Sie zum Arbeiten mit dem betreffenden Container verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="ee7bb-272">Sie können sehen, ob das Image ausgeführt wird, indem Sie den Befehl überprüfen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="ee7bb-273">Wenn der Container ausgeführt wird, sehen Sie eine Zeile, in der er als ausgeführter Prozess aufgelistet wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="ee7bb-274">Möglicherweise wird dort nur ein Prozess angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-274">(It may be the only one.)</span></span>

<span data-ttu-id="ee7bb-275">Sie können Ihren Dienst testen, indem Sie einen Browser öffnen, zu „localhost“ navigieren und einen Breiten- und Längengrad angeben:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="ee7bb-276">Anfügen an einen ausgeführten Container</span><span class="sxs-lookup"><span data-stu-id="ee7bb-276">Attaching to a running container</span></span>

<span data-ttu-id="ee7bb-277">Bei der Ausführung des Diensts in einem Befehlsfenster wurden für jede Anforderung Diagnoseinformationen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="ee7bb-278">Diese Informationen werden nicht angezeigt, wenn der Container im getrennten Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="ee7bb-279">Der Docker-attach-Befehl ermöglicht Ihnen das Anfügen an einen ausgeführten Container, sodass Sie die Protokollinformationen sehen können.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="ee7bb-280">Führen Sie diesen Befehl in einem Befehlsfenster aus:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="ee7bb-281">Durch das `--sig-proxy=false`-Argument wird festgelegt, dass <kbd>STRG</kbd>+<kbd>C</kbd>-Befehle nicht an den Containerprozess gesendet werden, sondern stattdessen den `docker attach`-Befehl beenden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="ee7bb-282">Das letzte Argument ist der Name, den der Container im `docker run`-Befehl erhält.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="ee7bb-283">Sie können auch die von Docker zugewiesene Container-ID verwenden, um auf einen Container zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="ee7bb-284">Wenn Sie in `docker run` keinen Namen für den Container angegeben haben, müssen Sie die Container-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="ee7bb-285">Öffnen Sie einen Browser, und navigieren Sie zu Ihrem Dienst.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="ee7bb-286">Sie sehen die Diagnosemeldungen des angefügten ausgeführten Containers in den Befehlsfenstern.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="ee7bb-287">Drücken Sie <kbd>STRG</kbd>+<kbd>C</kbd>, um den Anfügungsprozess zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="ee7bb-288">Wenn Sie die Arbeit mit Ihrem Container abgeschlossen haben, können Sie ihn stoppen:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="ee7bb-289">Container und Image stehen weiterhin für einen Neustart zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="ee7bb-290">Wenn Sie den Container von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="ee7bb-291">Wenn Sie nicht benutzte Images von Ihrem Computer entfernen möchten, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="ee7bb-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="ee7bb-292">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="ee7bb-292">Conclusion</span></span> 

<span data-ttu-id="ee7bb-293">In diesem Tutorial haben Sie einen ASP.NET Core-Microservice erstellt und einige einfache Features hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="ee7bb-294">Sie haben ein Docker-Containerimage für diesen Dienst erstellt und diesen Container auf dem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="ee7bb-295">Sie haben dem Dienst ein Terminalfenster angefügt und die Diagnosemeldungen Ihres Diensts gesehen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="ee7bb-296">Nebenbei haben Sie verschiedene Features der C#-Sprache in Aktion gesehen.</span><span class="sxs-lookup"><span data-stu-id="ee7bb-296">Along the way, you saw several features of the C# language in action.</span></span>
