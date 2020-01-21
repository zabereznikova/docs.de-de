---
title: Erstellen eines REST-Clients mithilfe von .NET Core
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 85a3c8e17e14db86786950380ba745ae286dccca
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115872"
---
# <a name="rest-client"></a><span data-ttu-id="ee2e8-103">REST-Client</span><span class="sxs-lookup"><span data-stu-id="ee2e8-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="ee2e8-104">Einführung</span><span class="sxs-lookup"><span data-stu-id="ee2e8-104">Introduction</span></span>

<span data-ttu-id="ee2e8-105">In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="ee2e8-106">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-106">You’ll learn:</span></span>

* <span data-ttu-id="ee2e8-107">Grundlagen der .NET Core-Befehlszeilenschnittstelle (CLI)</span><span class="sxs-lookup"><span data-stu-id="ee2e8-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="ee2e8-108">Eine Übersicht über die Features der Sprache C#</span><span class="sxs-lookup"><span data-stu-id="ee2e8-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="ee2e8-109">Verwalten von Abhängigkeiten mit NuGet</span><span class="sxs-lookup"><span data-stu-id="ee2e8-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="ee2e8-110">HTTP-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="ee2e8-110">HTTP Communications</span></span>
* <span data-ttu-id="ee2e8-111">Verarbeiten von JSON-Informationen</span><span class="sxs-lookup"><span data-stu-id="ee2e8-111">Processing JSON information</span></span>
* <span data-ttu-id="ee2e8-112">Verwalten der Konfiguration mit Attributen</span><span class="sxs-lookup"><span data-stu-id="ee2e8-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="ee2e8-113">Sie erstellen eine Anwendung, die HTTP-Anforderungen an einen REST-Dienst in GitHub ausgibt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="ee2e8-114">Sie lesen Informationen im JSON-Format ein und konvertieren das JSON-Paket in C#-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="ee2e8-115">Abschließend lernen Sie die Arbeit mit C#-Objekten kennen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="ee2e8-116">In diesem Tutorial werden viele Features abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-116">There are many features in this tutorial.</span></span> <span data-ttu-id="ee2e8-117">Gehen wir sie einzeln an.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-117">Let’s build them one by one.</span></span>

<span data-ttu-id="ee2e8-118">Wenn Sie lieber das [letzte Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) für dieses Thema befolgen möchten, können Sie es herunterladen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="ee2e8-119">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="ee2e8-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee2e8-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ee2e8-120">Prerequisites</span></span>

<span data-ttu-id="ee2e8-121">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="ee2e8-122">Die Installationsanweisungen finden Sie auf der Seite [.NET Core-Downloads](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ee2e8-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="ee2e8-123">Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="ee2e8-124">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="ee2e8-125">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="ee2e8-126">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="ee2e8-127">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="ee2e8-127">Create the Application</span></span>

<span data-ttu-id="ee2e8-128">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-128">The first step is to create a new application.</span></span> <span data-ttu-id="ee2e8-129">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="ee2e8-130">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-130">Make that the current directory.</span></span> <span data-ttu-id="ee2e8-131">Geben Sie den folgenden Befehl in ein Konsolenfenster ein:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="ee2e8-132">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="ee2e8-133">Der Projektname lautet „WebApiClient“.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="ee2e8-134">Da es sich hier um ein neues Projekt handelt, ist keine der Abhängigkeiten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="ee2e8-135">Mit der ersten Ausführung wird das .NET Core-Framework heruntergeladen, ein Entwicklungszertifikat installiert und der NuGet-Paket-Manager ausgeführt, um die fehlenden Abhängigkeiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="ee2e8-136">Bevor Sie beginnen, Änderungen vornehmen, geben Sie `dotnet run` ([siehe Hinweis](#dotnet-restore-note)) zum Ausführen der Anwendung an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="ee2e8-137">`dotnet run` führt automatisch `dotnet restore` aus, wenn Ihrer Umgebung Abhängigkeiten fehlen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="ee2e8-138">Wenn Ihre Anwendung neu erstellt werden muss, wird auch `dotnet build` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="ee2e8-139">Nach dem ersten Setup müssen Sie nur dann `dotnet restore` oder `dotnet build` ausführen, wenn es für Ihr Projekt sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="ee2e8-140">Hinzufügen von neuen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ee2e8-140">Adding New Dependencies</span></span>

<span data-ttu-id="ee2e8-141">Eines der wichtigsten Entwurfsziele für .NET Core ist die Minimierung der Größe der .NET-Installation.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="ee2e8-142">Wenn eine Anwendung zusätzliche Bibliotheken für bestimmte Features benötigt, fügen Sie diese abhängigen Komponenten Ihrer C#-Projektdatei (\*.csproj) hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="ee2e8-143">Beispielweise müssen Sie das `System.Runtime.Serialization.Json`-Paket hinzufügen, damit Ihre Anwendung JSON-Antworten verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="ee2e8-144">Sie benötigen das `System.Runtime.Serialization.Json`-Paket für diese Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="ee2e8-145">Fügen Sie es Ihrem Projekt hinzu, indem Sie den folgenden [.NET CLI](../../core/tools/dotnet-add-package.md)-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="ee2e8-146">Ausführen von Webanforderungen</span><span class="sxs-lookup"><span data-stu-id="ee2e8-146">Making Web Requests</span></span>

<span data-ttu-id="ee2e8-147">Jetzt können Sie damit beginnen, Daten aus dem Web abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="ee2e8-148">In dieser Anwendung lesen Sie Informationen aus der [GitHub-API](https://developer.github.com/v3/) ein.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="ee2e8-149">Beginnen wir damit, Informationen zu den Projekten unterhalb der Kategorie [.NET Foundation](https://www.dotnetfoundation.org/) einzulesen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="ee2e8-150">Hierzu senden Sie zunächst eine Anforderung an die GitHub-API, um Informationen zu den Projekten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="ee2e8-151">Der verwendete Endpunkt ist <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="ee2e8-152">Sie möchten alle Informationen zu diesen Projekten abrufen, deshalb verwenden Sie eine HTTP GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="ee2e8-153">Ihr Browser verwendet ebenfalls HTTP GET-Anforderungen, deshalb können Sie diese URL in Ihren Browser einfügen, um zu sehen, welche Informationen abgerufen und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="ee2e8-154">Sie verwenden die <xref:System.Net.Http.HttpClient> -Klasse zum Ausführen der Webanforderungen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="ee2e8-155">Wie alle modernen .NET-APIs unterstützt <xref:System.Net.Http.HttpClient> nur asynchrone Methoden für APIs mit langer Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="ee2e8-156">Sie beginnen mit dem Erstellen einer asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-156">Start by making an async method.</span></span> <span data-ttu-id="ee2e8-157">Sie vervollständigen die Implementierung, wenn Sie die Funktionalität der Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="ee2e8-158">Öffnen Sie zunächst die Datei `program.cs` in Ihrem Projektverzeichnis, und fügen Sie der `Program`-Klasse die folgende Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="ee2e8-159">Sie müssen am Anfang Ihrer `Main`-Methode eine `using`-Anweisung hinzufügen, damit der C#-Compiler den <xref:System.Threading.Tasks.Task> -Typ erkennt:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-159">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="ee2e8-160">Wenn Sie zu diesem Zeitpunkt Ihr Projekt erstellen, erhalten Sie eine Warnung für diese Methode, weil sie keine `await`-Operatoren enthält und synchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="ee2e8-161">Ignorieren Sie dies für den Moment. Sie fügen `await`-Operatoren hinzu, wenn Sie die Methode vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="ee2e8-162">Als Nächstes benennen Sie den in der `namespace`-Anweisung definierten Namespace vom Standardwert `ConsoleApp` in `WebAPIClient` um.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="ee2e8-163">Später definieren wir eine `repo`-Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="ee2e8-164">Aktualisieren Sie jetzt die `Main`-Methode, um diese Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="ee2e8-165">Die `ProcessRepositories`-Methode gibt einen Task zurück, und Sie dürfen das Programm nicht beenden, bevor dieser Task abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-165">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="ee2e8-166">Daher müssen Sie die Signatur von `Main` ändern.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="ee2e8-167">Fügen Sie den `async`-Modifizierer hinzu, und ändern Sie den Rückgabetyp in `Task`.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="ee2e8-168">Fügen Sie dann im Textkörper der Methode einen Aufruf von `ProcessRepositories`hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="ee2e8-169">Fügen Sie diesem Methodenaufruf das `await`-Schlüsselwort „when“ hinzu:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-169">Add the `await` keyword when to that method call:</span></span>

```csharp
static Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="ee2e8-170">Sie verfügen jetzt über ein Programm, das keinerlei Vorgänge ausführt, aber asynchron arbeitet.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="ee2e8-171">Es gibt aber noch Raum zur Verbesserung.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-171">Let's improve it.</span></span>

<span data-ttu-id="ee2e8-172">Zunächst benötigen Sie ein Objekt, das dazu fähig ist, Daten aus dem Web abzurufen. Hierfür können Sie <xref:System.Net.Http.HttpClient> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="ee2e8-173">Dieses Objekt verarbeitet die Anforderung und die Antworten.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-173">This object handles the request and the responses.</span></span> <span data-ttu-id="ee2e8-174">Instanziieren Sie eine einzelne Instanz dieses Typs in der Klasse `Program` innerhalb der Datei „Program.cs“.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="ee2e8-175">Kehren wir zur `ProcessRepositories`-Methode zurück und erstellen eine erste Version der Methode:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="ee2e8-176">Damit eine Kompilierung möglich ist, müssen Sie am Anfang der Datei außerdem zwei neue using-Anweisungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="ee2e8-177">Diese erste Version führt eine Webanforderung aus, um die Liste aller Repositorys unterhalb der dotnet foundation-Organisation einzulesen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="ee2e8-178">(Die GitHub-ID für die .NET Foundation lautet „dotnet“.)</span><span class="sxs-lookup"><span data-stu-id="ee2e8-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="ee2e8-179">In den ersten Zeilen wird <xref:System.Net.Http.HttpClient> für diese Anforderung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="ee2e8-180">Zunächst wird der HttpClient so konfiguriert, dass er die GitHub-JSON-Antworten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="ee2e8-181">Das Format ist einfach JSON.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-181">This format is simply JSON.</span></span> <span data-ttu-id="ee2e8-182">In der nächsten Zeile wird ein Benutzer-Agent-Header für alle Anforderungen von diesem Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="ee2e8-183">Diese zwei Header werden vom GitHub-Servercode überprüft und sind erforderlich, um Informationen aus GitHub abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="ee2e8-184">Nachdem Sie den <xref:System.Net.Http.HttpClient> konfiguriert haben, führen Sie eine Webanforderung aus und rufen die Antwort ab.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="ee2e8-185">In dieser ersten Version verwenden Sie die bequeme <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="ee2e8-186">Diese Hilfsmethode startet einen Task zum Ausführen der Webanforderung. Wenn die Anforderung zurückgegeben wird, liest sie den Antwortstream und extrahiert den Inhalt aus dem Stream.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="ee2e8-187">Der Antwortkörper wird als <xref:System.String> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="ee2e8-188">Die Zeichenfolge ist verfügbar, wenn der Task abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-188">The string is available when the task completes.</span></span>

<span data-ttu-id="ee2e8-189">Die letzten zwei Zeilen dieser Methode warten auf den Task und geben dann die Antwort an die Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="ee2e8-190">Erstellen Sie die App, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-190">Build the app, and run it.</span></span> <span data-ttu-id="ee2e8-191">Die Buildwarnung wird jetzt nicht mehr angezeigt, weil `ProcessRepositories` jetzt einen `await`-Operator enthält.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="ee2e8-192">Sie sehen eine umfangreiche Textanzeige im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="ee2e8-193">Verarbeiten des JSON-Ergebnisses</span><span class="sxs-lookup"><span data-stu-id="ee2e8-193">Processing the JSON Result</span></span>

<span data-ttu-id="ee2e8-194">Zu diesem Zeitpunkt haben Sie Code geschrieben, mit dem eine Antwort von einem Webserver abgerufen und der Text angezeigt wird, der in dieser Antwort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="ee2e8-195">Konvertieren wir jetzt diese JSON-Antwort in C#-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="ee2e8-196">Die <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType>-Klasse serialisiert Objekte in JSON und deserialisiert JSON in-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="ee2e8-197">Definieren Sie zunächst eine Klasse, die das `repo`-JSON-Objekt darstellt, das von der GitHub-API zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="ee2e8-198">Platzieren Sie den obigen Code in einer neuen Datei namens „repo.cs“.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="ee2e8-199">Diese Version der Klasse repräsentiert die einfachste Möglichkeit zum Verarbeiten von JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="ee2e8-200">Der Klassenname und der Membername stimmen mit den im JSON-Paket verwendeten Namen überein, statt den C#-Konventionen zu folgen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="ee2e8-201">Sie beheben dies später, indem Sie einige Konfigurationsattribute angeben.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="ee2e8-202">Diese Klasse veranschaulicht ein weiteres wichtiges Feature der JSON-Serialisierung und -Deserialisierung: Nicht alle Felder im JSON-Paket sind Teil dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="ee2e8-203">Das JSON-Serialisierungsprogramm ignoriert Informationen, die nicht im verwendeten Klassentyp enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="ee2e8-204">Dieses Feature vereinfacht es, Typen zu erstellen, die nur mit einem Teilsatz der Felder im JSON-Paket funktionieren.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="ee2e8-205">Nun, da Sie den Typ erstellt haben, deserialisieren wir ihn.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="ee2e8-206">Als Nächstes verwenden Sie das Serialisierungsprogramm, um JSON-Daten in C#-Objekte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="ee2e8-207">Ersetzen Sie den Aufruf von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in Ihrer `ProcessRepositories`-Methode durch die folgenden drei Zeilen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="ee2e8-208">Sie verwenden einen neuen Namespace, sodass Sie diesen ebenfalls am Anfang der Datei hinzufügen müssen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="ee2e8-209">Beachten Sie, dass Sie jetzt <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anstelle von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="ee2e8-210">Das Serialisierungsprogramm verwendet anstelle einer Zeichenfolge einen Stream als Quelle.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="ee2e8-211">Erläutern wir einige Features von C#, die in der zweiten Zeile des Codeausschnitts oben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="ee2e8-212">Das erste Argument für <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> ist ein `await`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="ee2e8-213">(Die anderen beiden Parameter sind optional und werden im Codeausschnitt ausgelassen.) Await-Ausdrücke können fast überall in Ihrem Code auftauchen, auch wenn sie bisher nur als Teil einer Zuweisungsanweisung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="ee2e8-214">Die `Deserialize`-Methode ist *generisch*. Dies bedeutet, dass Sie Typargumente für die Art von Objekten angeben müssen, die aus dem JSON-Text erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="ee2e8-215">In diesem Beispiel deserialisieren Sie in ein `List<Repository>`, bei dem es sich um ein weiteres generisches Objekt handelt, das <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee2e8-216">Die `List<>`-Klasse speichert eine Sammlung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="ee2e8-217">Das Typargument deklariert den Typ der in `List<>` gespeicherten Objekte.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="ee2e8-218">Der JSON-Text stellt eine Sammlung von Repositoryobjekten dar, sodass das Typargument `Repository` ist.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="ee2e8-219">Dieser Abschnitt ist fast fertig.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-219">You're almost done with this section.</span></span> <span data-ttu-id="ee2e8-220">Nachdem Sie nun die JSON-Daten in C#-Objekte konvertiert haben, lassen Sie uns den Namen jedes Repositorys anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="ee2e8-221">Ersetzen Sie diese Zeilen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="ee2e8-222">...durch die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="ee2e8-223">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-223">Compile and run the application.</span></span> <span data-ttu-id="ee2e8-224">Die Anwendung gibt die Namen der Repositorys aus, die Teil der .NET Foundation sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="ee2e8-225">Steuern der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ee2e8-225">Controlling Serialization</span></span>

<span data-ttu-id="ee2e8-226">Bevor Sie weitere Features hinzufügen, wenden wir uns der `name`-Eigenschaft mithilfe des `[JsonPropertyName]`-Attributs zu.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="ee2e8-227">Ändern Sie die Deklaration des `name`-Felds in „repo.cs“ folgendermaßen ab:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="ee2e8-228">Diese Änderung bedeutet, dass Sie den Code ändern müssen, mit dem der Name jedes Repositorys in „program.cs“ geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="ee2e8-229">Führen Sie `dotnet run` aus, um sicherzustellen, dass die Zuordnungen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="ee2e8-230">Es sollte dieselbe Ausgabe angezeigt werden wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-230">You should see the same output as before.</span></span>

<span data-ttu-id="ee2e8-231">Führen wir eine weitere Änderung durch, bevor wir neue Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="ee2e8-232">Die `ProcessRepositories`-Methode kann die asynchrone Arbeit erledigen und eine Auflistung der Repositorys zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="ee2e8-233">Geben wir die `List<Repository>` über diese Methode zurück, und verschieben wir den Code zum Schreiben dieser Informationen in die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="ee2e8-234">Ändern Sie die Signatur von `ProcessRepositories`, um einen Task zurückzugeben, dessen Ergebnis eine Liste mit `Repository`-Objekten ist:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="ee2e8-235">Geben Sie anschließend einfach die Repositorys zurück, nachdem die JSON-Antwort verarbeitet wurde:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="ee2e8-236">Der Compiler generiert das `Task<T>`-Objekt für die Rückgabe, weil Sie diese Methode als `async` markiert haben.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="ee2e8-237">Ändern wir dann die `Main`-Methode, sodass sie diese Ergebnisse erfasst und den Namen jedes Repositorys an die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="ee2e8-238">Ihre `Main`-Methode sieht nun folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-238">Your `Main` method now looks like this:</span></span>

```csharp
public static Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="ee2e8-239">Einlesen weiterer Informationen</span><span class="sxs-lookup"><span data-stu-id="ee2e8-239">Reading More Information</span></span>

<span data-ttu-id="ee2e8-240">Zum Abschluss verarbeiten wir einige weitere Eigenschaften im JSON-Paket, das von der GitHub-API gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="ee2e8-241">Sie müssen nicht alle Informationen abrufen, aber das Hinzufügen einiger Eigenschaften veranschaulicht einige weitere Features von C#.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="ee2e8-242">Beginnen wir damit, ein paar weitere einfache Typen in die Definition der `Repository`-Klasse einzufügen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="ee2e8-243">Fügen Sie diese Eigenschaften zu dieser Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="ee2e8-244">Diese Eigenschaften verfügen über integrierte Konvertierungen vom Zeichenfolgentyp (dieser ist in den JSON-Paketen enthalten) in den Zieltyp.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="ee2e8-245">Der <xref:System.Uri> -Typ ist Ihnen möglicherweise neu.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="ee2e8-246">Er repräsentiert einen URI, oder in diesem Fall eine URL.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="ee2e8-247">Im Fall der `Uri`- und `int`-Typen wird über die Serialisierungsaktion eine Ausnahme ausgelöst, wenn das JSON-Paket Daten enthält, die nicht in den Zieltyp konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="ee2e8-248">Aktualisieren Sie nach dem Hinzufügen die `Main`-Methode, um diese Elemente anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-248">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

<span data-ttu-id="ee2e8-249">Im letzten Schritt fügen wir jetzt die Informationen für den letzten Pushvorgang hinzu.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="ee2e8-250">Diese Informationen werden in der JSON-Antwort folgendermaßen formatiert:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="ee2e8-251">Dieses Format entspricht nicht den standardmäßigen .NET-<xref:System.DateTime> -Formaten.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-251">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="ee2e8-252">Deshalb müssen Sie eine benutzerdefinierte Konvertierungsmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-252">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="ee2e8-253">Darüber hinaus möchten Sie wahrscheinlich nicht, dass die unformatierte Zeichenfolge für Benutzer der `Repository`-Klasse verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-253">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="ee2e8-254">Dies kann ebenfalls mithilfe von Attributen gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-254">Attributes can help control that as well.</span></span> <span data-ttu-id="ee2e8-255">Definieren Sie zunächst eine `public`-Eigenschaft, die die Zeichenfolgendarstellung des Datums und der Uhrzeit in Ihrer `Repository`-Klasse enthält, und eine `LastPush` `readonly`-Eigenschaft, die eine formatierte Zeichenfolge zurückgibt, die das zurückgegebene Datum darstellt:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-255">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="ee2e8-256">Gehen wir die soeben definierten neuen Konstrukte einzeln durch.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-256">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="ee2e8-257">Die `LastPush`-Eigenschaft wird mit einem *Ausdruckskörpermember* für die `get`-Zugriffsmethode definiert.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-257">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="ee2e8-258">Es ist kein `set`-Accessor vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-258">There is no `set` accessor.</span></span> <span data-ttu-id="ee2e8-259">Durch Auslassen der `set`-Zugriffsmethode definieren Sie eine *schreibgeschützte* Eigenschaft in C#.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-259">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="ee2e8-260">(Ja, Sie können *lesegeschützte* Eigenschaften in C# erstellen, aber ihr Wert ist begrenzt.) Die <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)>-Methode analysiert eine Zeichenfolge und erstellt ein <xref:System.DateTime>-Objekt mit dem angegebenen Datumsformat. Außerdem werden mit einem `CultureInfo`-Objekt zusätzliche Metadaten zu `DateTime` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-260">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="ee2e8-261">Wenn die Analyse nicht erfolgreich ist, löst der Eigenschaftsaccessor eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-261">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="ee2e8-262">Zur Verwendung von <xref:System.Globalization.CultureInfo.InvariantCulture> müssen Sie den <xref:System.Globalization> -Namespace zu den `using`-Anweisungen in `repo.cs` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-262">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="ee2e8-263">Abschließend fügen Sie eine weitere Ausgabeanweisung in der Konsole hinzu. Jetzt können Sie diese Anwendung erstellen und erneut ausführen:</span><span class="sxs-lookup"><span data-stu-id="ee2e8-263">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="ee2e8-264">Ihre Version sollte nun der [abgeschlossenen Version](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-264">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="ee2e8-265">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="ee2e8-265">Conclusion</span></span>

<span data-ttu-id="ee2e8-266">In diesem Tutorial wurde gezeigt, wie Sie Webanforderungen ausführen, das Ergebnis analysieren und Eigenschaften dieser Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-266">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="ee2e8-267">Sie haben außerdem neue Pakete als abhängige Komponenten in Ihr Projekt eingefügt.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-267">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="ee2e8-268">Sie haben einige der Features von C# kennengelernt, die objektorientierte Verfahren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ee2e8-268">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
