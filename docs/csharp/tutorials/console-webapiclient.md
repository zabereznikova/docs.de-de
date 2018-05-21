---
title: Erstellen eines REST-Clients mithilfe von .NET Core
description: In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: bc3c23b277b233efba9f32cc49b29ac905f3abc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="rest-client"></a><span data-ttu-id="135c6-103">REST-Client</span><span class="sxs-lookup"><span data-stu-id="135c6-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="135c6-104">Einführung</span><span class="sxs-lookup"><span data-stu-id="135c6-104">Introduction</span></span>
<span data-ttu-id="135c6-105">In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="135c6-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="135c6-106">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="135c6-106">You’ll learn:</span></span>
*   <span data-ttu-id="135c6-107">Grundlagen der .NET Core-Befehlszeilenschnittstelle (CLI)</span><span class="sxs-lookup"><span data-stu-id="135c6-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="135c6-108">Eine Übersicht über die Features der Sprache C#</span><span class="sxs-lookup"><span data-stu-id="135c6-108">An overview of C# Language features.</span></span>
*   <span data-ttu-id="135c6-109">Verwalten von Abhängigkeiten mit NuGet</span><span class="sxs-lookup"><span data-stu-id="135c6-109">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="135c6-110">HTTP-Kommunikation</span><span class="sxs-lookup"><span data-stu-id="135c6-110">HTTP Communications</span></span>
*   <span data-ttu-id="135c6-111">Verarbeiten von JSON-Informationen</span><span class="sxs-lookup"><span data-stu-id="135c6-111">Processing JSON information</span></span>
*   <span data-ttu-id="135c6-112">Verwalten der Konfiguration mit Attributen</span><span class="sxs-lookup"><span data-stu-id="135c6-112">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="135c6-113">Sie erstellen eine Anwendung, die HTTP-Anforderungen an einen REST-Dienst in GitHub ausgibt.</span><span class="sxs-lookup"><span data-stu-id="135c6-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="135c6-114">Sie lesen Informationen im JSON-Format ein und konvertieren das JSON-Paket in C#-Objekte.</span><span class="sxs-lookup"><span data-stu-id="135c6-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="135c6-115">Abschließend lernen Sie die Arbeit mit C#-Objekten kennen.</span><span class="sxs-lookup"><span data-stu-id="135c6-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="135c6-116">In diesem Tutorial werden viele Features abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="135c6-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="135c6-117">Gehen wir sie einzeln an.</span><span class="sxs-lookup"><span data-stu-id="135c6-117">Let’s build them one by one.</span></span>

<span data-ttu-id="135c6-118">Wenn Sie lieber das [letzte Beispiel](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) für dieses Thema befolgen möchten, können Sie es herunterladen.</span><span class="sxs-lookup"><span data-stu-id="135c6-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="135c6-119">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="135c6-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="135c6-120">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="135c6-120">Prerequisites</span></span>
<span data-ttu-id="135c6-121">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="135c6-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="135c6-122">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="135c6-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="135c6-123">Sie können diese Anwendung unter Windows, Linux, macOS oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="135c6-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="135c6-124">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="135c6-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="135c6-125">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="135c6-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="135c6-126">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="135c6-126">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="135c6-127">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="135c6-127">Create the Application</span></span>
<span data-ttu-id="135c6-128">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="135c6-128">The first step is to create a new application.</span></span> <span data-ttu-id="135c6-129">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="135c6-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="135c6-130">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="135c6-130">Make that the current directory.</span></span> <span data-ttu-id="135c6-131">Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="135c6-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="135c6-132">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="135c6-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="135c6-133">Bevor Sie damit beginnen, Änderungen durchzuführen, gehen wir die Schritte zur Ausführung der einfachen Hello World-Anwendung durch.</span><span class="sxs-lookup"><span data-stu-id="135c6-133">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="135c6-134">Geben Sie nach dem Erstellen der Anwendung den Befehl `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) bei Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="135c6-134">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="135c6-135">Mit diesem Befehl wird der Prozess zur NuGet-Paketwiederherstellung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="135c6-135">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="135c6-136">NuGet ist ein .NET-Paket-Manager.</span><span class="sxs-lookup"><span data-stu-id="135c6-136">NuGet is a .NET package manager.</span></span> <span data-ttu-id="135c6-137">Mit diesem Befehl werden alle fehlenden abhängigen Komponenten für Ihr Projekt heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="135c6-137">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="135c6-138">Da es sich um ein neues Projekt handelt, ist keine der abhängigen Komponenten vorhanden, deshalb wird zunächst das .NET Core-Framework heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="135c6-138">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="135c6-139">Nach diesem ersten Schritt müssen Sie `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) nur ausführen, wenn Sie neue abhängige Pakete hinzufügen oder die Versionen abhängiger Komponenten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="135c6-139">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="135c6-140">Nach dem Wiederherstellen der Pakete führen Sie `dotnet build` aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="135c6-141">Hiermit wird die Build-Engine ausgeführt und Ihre Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="135c6-141">This executes the build engine and creates your application.</span></span> <span data-ttu-id="135c6-142">Abschließend führen Sie `dotnet run` aus, um Ihre Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="135c6-142">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="135c6-143">Hinzufügen von neuen Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="135c6-143">Adding New Dependencies</span></span>
<span data-ttu-id="135c6-144">Eines der wichtigsten Entwurfsziele für .NET Core ist die Minimierung der Größe der .NET Framework-Installation.</span><span class="sxs-lookup"><span data-stu-id="135c6-144">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="135c6-145">Das .NET Core-Anwendungsframework enthält nur die am häufigsten verwendeten Elemente der vollständigen .NET Framework-Version.</span><span class="sxs-lookup"><span data-stu-id="135c6-145">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="135c6-146">Wenn eine Anwendung zusätzliche Bibliotheken für bestimmte Features benötigt, fügen Sie diese abhängigen Komponenten Ihrer C#-Projektdatei (\*.csproj) hinzu.</span><span class="sxs-lookup"><span data-stu-id="135c6-146">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="135c6-147">Beispielweise müssen Sie das `System.Runtime.Serialization.Json`-Paket hinzufügen, damit Ihre Anwendung JSON-Antworten verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="135c6-147">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="135c6-148">Öffnen Sie Ihre `csproj`-Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="135c6-148">Open your `csproj` project file.</span></span> <span data-ttu-id="135c6-149">Die erste Zeile der Datei sollte so aussehen:</span><span class="sxs-lookup"><span data-stu-id="135c6-149">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="135c6-150">Fügen Sie direkt nach dieser Zeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="135c6-150">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="135c6-151">Die meisten Code-Editoren bieten Codevervollständigung für verschiedene Versionen dieser Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="135c6-151">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="135c6-152">Sie werden in der Regel die neueste Version der hinzugefügten Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="135c6-152">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="135c6-153">Es ist jedoch wichtig, sicherzustellen, dass die Versionen aller Pakete übereinstimmen und auch der Version des .NET Core-Anwendungsframeworks entsprechen.</span><span class="sxs-lookup"><span data-stu-id="135c6-153">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="135c6-154">Nachdem Sie diese Änderungen durchgeführt haben, sollten Sie erneut `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) ausführen, damit das Paket auf Ihrem System installiert wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-154">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="135c6-155">Ausführen von Webanforderungen</span><span class="sxs-lookup"><span data-stu-id="135c6-155">Making Web Requests</span></span>
<span data-ttu-id="135c6-156">Jetzt können Sie damit beginnen, Daten aus dem Web abzurufen.</span><span class="sxs-lookup"><span data-stu-id="135c6-156">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="135c6-157">In dieser Anwendung lesen Sie Informationen aus der [GitHub-API](https://developer.github.com/v3/) ein.</span><span class="sxs-lookup"><span data-stu-id="135c6-157">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="135c6-158">Beginnen wir damit, Informationen zu den Projekten unterhalb der Kategorie [.NET Foundation](http://www.dotnetfoundation.org/) einzulesen.</span><span class="sxs-lookup"><span data-stu-id="135c6-158">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="135c6-159">Hierzu senden Sie zunächst eine Anforderung an die GitHub-API, um Informationen zu den Projekten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="135c6-159">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="135c6-160">Der verwendete Endpunkt ist [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="135c6-160">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="135c6-161">Sie möchten alle Informationen zu diesen Projekten abrufen, deshalb verwenden Sie eine HTTP GET-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="135c6-161">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="135c6-162">Ihr Browser verwendet ebenfalls HTTP GET-Anforderungen, deshalb können Sie diese URL in Ihren Browser einfügen, um zu sehen, welche Informationen abgerufen und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="135c6-162">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="135c6-163">Sie verwenden die <xref:System.Net.Http.HttpClient> -Klasse zum Ausführen der Webanforderungen.</span><span class="sxs-lookup"><span data-stu-id="135c6-163">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="135c6-164">Wie alle modernen .NET-APIs unterstützt <xref:System.Net.Http.HttpClient> nur asynchrone Methoden für APIs mit langer Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="135c6-164">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="135c6-165">Sie beginnen mit dem Erstellen einer asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="135c6-165">Start by making an async method.</span></span> <span data-ttu-id="135c6-166">Sie vervollständigen die Implementierung, wenn Sie die Funktionalität der Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="135c6-166">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="135c6-167">Öffnen Sie zunächst die Datei `program.cs` in Ihrem Projektverzeichnis, und fügen Sie der `Program`-Klasse die folgende Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="135c6-167">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="135c6-168">Sie müssen am Anfang Ihrer `Main`-Methode eine `using`-Anweisung hinzufügen, damit der C#-Compiler den <xref:System.Threading.Tasks.Task> -Typ erkennt:</span><span class="sxs-lookup"><span data-stu-id="135c6-168">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="135c6-169">Wenn Sie zu diesem Zeitpunkt Ihr Projekt erstellen, erhalten Sie eine Warnung für diese Methode, weil sie keine `await`-Operatoren enthält und synchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-169">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="135c6-170">Ignorieren Sie dies für den Moment. Sie fügen `await`-Operatoren hinzu, wenn Sie die Methode vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="135c6-170">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="135c6-171">Als Nächstes benennen Sie den in der `namespace`-Anweisung definierten Namespace vom Standardwert `ConsoleApp` in `WebAPIClient` um.</span><span class="sxs-lookup"><span data-stu-id="135c6-171">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="135c6-172">Später definieren wir eine `repo`-Klasse in diesem Namespace.</span><span class="sxs-lookup"><span data-stu-id="135c6-172">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="135c6-173">Aktualisieren Sie jetzt die `Main`-Methode, um diese Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="135c6-173">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="135c6-174">Die `ProcessRepositories`-Methode gibt einen Task zurück, und Sie dürfen das Programm nicht beenden, bevor dieser Task abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="135c6-174">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="135c6-175">Deshalb müssen Sie die `Wait` -Methode verwenden, um eine Blockierung einzurichten und auf den Abschluss des Tasks zu warten:</span><span class="sxs-lookup"><span data-stu-id="135c6-175">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="135c6-176">Sie verfügen jetzt über ein Programm, das keinerlei Vorgänge ausführt, aber asynchron arbeitet.</span><span class="sxs-lookup"><span data-stu-id="135c6-176">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="135c6-177">Es gibt aber noch Raum zur Verbesserung.</span><span class="sxs-lookup"><span data-stu-id="135c6-177">Let's improve it.</span></span>

<span data-ttu-id="135c6-178">Zunächst benötigen Sie ein Objekt, das dazu fähig ist, Daten aus dem Web abzurufen. Hierfür können Sie <xref:System.Net.Http.HttpClient> verwenden.</span><span class="sxs-lookup"><span data-stu-id="135c6-178">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="135c6-179">Dieses Objekt verarbeitet die Anforderung und die Antworten.</span><span class="sxs-lookup"><span data-stu-id="135c6-179">This object handles the request and the responses.</span></span> <span data-ttu-id="135c6-180">Instanziieren Sie eine einzelne Instanz dieses Typs in der Klasse `Program` innerhalb der Datei „Program.cs“.</span><span class="sxs-lookup"><span data-stu-id="135c6-180">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="135c6-181">Kehren wir zur `ProcessRepositories`-Methode zurück und erstellen eine erste Version der Methode:</span><span class="sxs-lookup"><span data-stu-id="135c6-181">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="135c6-182">Damit eine Kompilierung möglich ist, müssen Sie am Anfang der Datei außerdem zwei neue using-Anweisungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="135c6-182">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="135c6-183">Diese erste Version führt eine Webanforderung aus, um die Liste aller Repositorys unterhalb der dotnet foundation-Organisation einzulesen.</span><span class="sxs-lookup"><span data-stu-id="135c6-183">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="135c6-184">(Die GitHub-ID für die .NET Foundation lautet „dotnet“.)</span><span class="sxs-lookup"><span data-stu-id="135c6-184">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="135c6-185">In den ersten Zeilen wird <xref:System.Net.Http.HttpClient> für diese Anforderung eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="135c6-185">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="135c6-186">Zunächst wird der HttpClient so konfiguriert, dass er die GitHub-JSON-Antworten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="135c6-186">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="135c6-187">Das Format ist einfach JSON.</span><span class="sxs-lookup"><span data-stu-id="135c6-187">This format is simply JSON.</span></span> <span data-ttu-id="135c6-188">In der nächsten Zeile wird ein Benutzer-Agent-Header für alle Anforderungen von diesem Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="135c6-188">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="135c6-189">Diese zwei Header werden vom GitHub-Servercode überprüft und sind erforderlich, um Informationen aus GitHub abzurufen.</span><span class="sxs-lookup"><span data-stu-id="135c6-189">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="135c6-190">Nachdem Sie den <xref:System.Net.Http.HttpClient> konfiguriert haben, führen Sie eine Webanforderung aus und rufen die Antwort ab.</span><span class="sxs-lookup"><span data-stu-id="135c6-190">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="135c6-191">In dieser ersten Version verwenden Sie die bequeme <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="135c6-191">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="135c6-192">Diese Hilfsmethode startet einen Task zum Ausführen der Webanforderung. Wenn die Anforderung zurückgegeben wird, liest sie den Antwortstream und extrahiert den Inhalt aus dem Stream.</span><span class="sxs-lookup"><span data-stu-id="135c6-192">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="135c6-193">Der Antwortkörper wird als <xref:System.String> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="135c6-193">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="135c6-194">Die Zeichenfolge ist verfügbar, wenn der Task abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="135c6-194">The string is available when the task completes.</span></span> 

<span data-ttu-id="135c6-195">Die letzten zwei Zeilen dieser Methode warten auf den Task und geben dann die Antwort an die Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-195">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="135c6-196">Erstellen Sie die App, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-196">Build the app, and run it.</span></span> <span data-ttu-id="135c6-197">Die Buildwarnung wird jetzt nicht mehr angezeigt, weil `ProcessRepositories` jetzt einen `await`-Operator enthält.</span><span class="sxs-lookup"><span data-stu-id="135c6-197">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="135c6-198">Sie sehen eine umfangreiche Textanzeige im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="135c6-198">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="135c6-199">Verarbeiten des JSON-Ergebnisses</span><span class="sxs-lookup"><span data-stu-id="135c6-199">Processing the JSON Result</span></span>

<span data-ttu-id="135c6-200">Zu diesem Zeitpunkt haben Sie Code geschrieben, mit dem eine Antwort von einem Webserver abgerufen und der Text angezeigt wird, der in dieser Antwort enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="135c6-200">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="135c6-201">Konvertieren wir jetzt diese JSON-Antwort in C#-Objekte.</span><span class="sxs-lookup"><span data-stu-id="135c6-201">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="135c6-202">Das JSON-Serialisierungsprogramm konvertiert JSON-Daten in C#-Objekte.</span><span class="sxs-lookup"><span data-stu-id="135c6-202">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="135c6-203">Ihre erste Aufgabe ist es, einen C#-Klassentyp zur Aufnahme der Informationen zu definieren, die Sie aus dieser Antwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="135c6-203">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="135c6-204">Gehen wir langsam vor und beginnen mit einem einfachen C#-Typ, der den Namen des Repositorys enthält:</span><span class="sxs-lookup"><span data-stu-id="135c6-204">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="135c6-205">Platzieren Sie den obigen Code in einer neuen Datei namens „repo.cs“.</span><span class="sxs-lookup"><span data-stu-id="135c6-205">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="135c6-206">Diese Version der Klasse repräsentiert die einfachste Möglichkeit zum Verarbeiten von JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="135c6-206">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="135c6-207">Der Klassenname und der Membername stimmen mit den im JSON-Paket verwendeten Namen überein, statt den C#-Konventionen zu folgen.</span><span class="sxs-lookup"><span data-stu-id="135c6-207">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="135c6-208">Sie beheben dies später, indem Sie einige Konfigurationsattribute angeben.</span><span class="sxs-lookup"><span data-stu-id="135c6-208">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="135c6-209">Diese Klasse veranschaulicht ein weiteres wichtiges Feature der JSON-Serialisierung und -Deserialisierung: Nicht alle Felder im JSON-Paket sind Teil dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="135c6-209">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="135c6-210">Das JSON-Serialisierungsprogramm ignoriert Informationen, die nicht im verwendeten Klassentyp enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="135c6-210">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="135c6-211">Dieses Feature vereinfacht es, Typen zu erstellen, die nur mit einem Teilsatz der Felder im JSON-Paket funktionieren.</span><span class="sxs-lookup"><span data-stu-id="135c6-211">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="135c6-212">Nun, da Sie den Typ erstellt haben, deserialisieren wir ihn.</span><span class="sxs-lookup"><span data-stu-id="135c6-212">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="135c6-213">Sie müssen ein <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> -Objekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="135c6-213">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="135c6-214">Dieses Objekt muss den CLR-Typ kennen, der für das abgerufene JSON-Paket erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-214">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="135c6-215">Das Paket aus GitHub enthält eine Sequenz aus Repositorys, deshalb ist `List<repo>` der richtige Typ.</span><span class="sxs-lookup"><span data-stu-id="135c6-215">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="135c6-216">Fügen Sie Ihrer `ProcessRepositories`-Methode die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="135c6-216">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="135c6-217">Sie verwenden jetzt zwei neue Namespaces, deshalb müssen Sie diese auch hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="135c6-217">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="135c6-218">Als Nächstes verwenden Sie das Serialisierungsprogramm, um JSON-Daten in C#-Objekte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="135c6-218">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="135c6-219">Ersetzen Sie den Aufruf von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in Ihrer `ProcessRepositories`-Methode durch die folgenden zwei Zeilen:</span><span class="sxs-lookup"><span data-stu-id="135c6-219">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="135c6-220">Beachten Sie, dass Sie jetzt <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anstelle von <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> verwenden.</span><span class="sxs-lookup"><span data-stu-id="135c6-220">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="135c6-221">Das Serialisierungsprogramm verwendet anstelle einer Zeichenfolge einen Stream als Quelle.</span><span class="sxs-lookup"><span data-stu-id="135c6-221">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="135c6-222">Erläutern wir einige Features von C#, die oben in der zweiten Zeile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="135c6-222">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="135c6-223">Das Argument für <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> ist ein `await`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="135c6-223">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="135c6-224">Await-Ausdrücke können fast überall in Ihrem Code auftauchen, auch wenn sie bisher nur als Teil einer Zuweisungsanweisung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="135c6-224">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="135c6-225">Zweitens wird der `as`-Operator vom Kompilierzeittyp `object` in `List<repo>` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="135c6-225">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="135c6-226">Die Deklaration von <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> gibt an, dass ein Objekt vom Typ <xref:System.Object?displayProperty=nameWithType> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-226">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="135c6-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> gibt den Typ zurück, den Sie bei der Erstellung angegeben haben (in diesem Tutorial `List<repo>`).</span><span class="sxs-lookup"><span data-stu-id="135c6-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="135c6-228">Wenn die Konvertierung nicht erfolgreich ist, wird der `as`-Operator als `null` ausgewertet, statt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="135c6-228">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="135c6-229">Dieser Abschnitt ist fast fertig.</span><span class="sxs-lookup"><span data-stu-id="135c6-229">You're almost done with this section.</span></span> <span data-ttu-id="135c6-230">Nachdem Sie nun die JSON-Daten in C#-Objekte konvertiert haben, lassen Sie uns den Namen jedes Repositorys anzeigen.</span><span class="sxs-lookup"><span data-stu-id="135c6-230">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="135c6-231">Ersetzen Sie diese Zeilen:</span><span class="sxs-lookup"><span data-stu-id="135c6-231">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="135c6-232">...durch die folgenden:</span><span class="sxs-lookup"><span data-stu-id="135c6-232">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="135c6-233">Kompilieren Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-233">Compile and run the application.</span></span> <span data-ttu-id="135c6-234">Die Anwendung gibt die Namen der Repositorys aus, die Teil der .NET Foundation sind.</span><span class="sxs-lookup"><span data-stu-id="135c6-234">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="135c6-235">Steuern der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="135c6-235">Controlling Serialization</span></span>

<span data-ttu-id="135c6-236">Bevor Sie weitere Features hinzufügen, lassen Sie uns den `repo`-Typ bearbeiten, sodass er eher den Standardkonventionen von C# entspricht.</span><span class="sxs-lookup"><span data-stu-id="135c6-236">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="135c6-237">Sie erreichen dies, indem Sie den `repo`-Typ mit *Attributen* versehen, die die Funktionsweise des JSON-Serialisierungsprogramms steuern.</span><span class="sxs-lookup"><span data-stu-id="135c6-237">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="135c6-238">In diesem Fall verwenden Sie die Attribute, um eine Zuordnung zwischen den JSON-Schlüsselnamen und den Namen der C#-Klassen und -Members zu definieren.</span><span class="sxs-lookup"><span data-stu-id="135c6-238">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="135c6-239">Die zwei verwendeten Attribute sind `DataContract` und `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="135c6-239">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="135c6-240">Laut Konvention enden alle Attributklassen auf das Suffix `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="135c6-240">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="135c6-241">Sie müssen dieses Suffix jedoch nicht verwenden, wenn Sie ein Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="135c6-241">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="135c6-242">Die Attribute `DataContract` und `DataMember` befinden sich in einer anderen Bibliothek, deshalb müssen Sie Ihrer C#-Projektdatei diese Bibliothek als abhängige Komponente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="135c6-242">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="135c6-243">Fügen Sie dem Abschnitt `<ItemGroup>` Ihrer Projektdatei die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="135c6-243">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="135c6-244">Führen Sie nach dem Speichern der Datei `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) aus, um dieses Paket abzurufen.</span><span class="sxs-lookup"><span data-stu-id="135c6-244">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="135c6-245">Öffnen Sie dann die Datei `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="135c6-245">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="135c6-246">Jetzt ändern wir den Namen in die Pascal-Schreibweise und schreiben den Namen `Repository` vollständig aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-246">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="135c6-247">JSON-repo-Knoten sollen weiterhin diesem Typ zugeordnet werden, deshalb müssen Sie das `DataContract`-Attribut zur Klassendeklaration hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="135c6-247">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="135c6-248">Sie legen die `Name`-Eigenschaft des Attributs auf den Namen der JSON-Knoten fest, die diesem Typ zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="135c6-248">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="135c6-249"><xref:System.Runtime.Serialization.DataContractAttribute> ist ein Member des <xref:System.Runtime.Serialization> -Namespace, deshalb müssen Sie oben in der Datei die geeignete `using` -Anweisung hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="135c6-249">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="135c6-250">Sie haben den Namen der `repo`-Klasse in `Repository` geändert, deshalb müssen Sie die gleiche Namensänderung in „Program.cs“ durchführen (einige Editoren unterstützen möglicherweise ein Refactoring mit Umbenennung, wodurch diese Änderung automatisch durchgeführt wird):</span><span class="sxs-lookup"><span data-stu-id="135c6-250">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="135c6-251">Führen wir jetzt die gleiche Änderung mit dem `name`-Feld unter Verwendung der <xref:System.Runtime.Serialization.DataMemberAttribute> -Klasse durch.</span><span class="sxs-lookup"><span data-stu-id="135c6-251">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="135c6-252">Ändern Sie die Deklaration des `name`-Felds in „repo.cs“ folgendermaßen ab:</span><span class="sxs-lookup"><span data-stu-id="135c6-252">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="135c6-253">Diese Änderung bedeutet, dass Sie den Code ändern müssen, mit dem der Name jedes Repositorys in „program.cs“ geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="135c6-253">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="135c6-254">Führen Sie `dotnet build` und anschließend `dotnet run` aus, um sicherzustellen, dass die Zuordnungen korrekt sind.</span><span class="sxs-lookup"><span data-stu-id="135c6-254">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="135c6-255">Es sollte dieselbe Ausgabe angezeigt werden wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="135c6-255">You should see the same output as before.</span></span> <span data-ttu-id="135c6-256">Bevor wir weitere Eigenschaften vom Webserver verarbeiten, lassen Sie uns eine weitere Änderung an der `Repository`-Klasse durchführen.</span><span class="sxs-lookup"><span data-stu-id="135c6-256">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="135c6-257">Der `Name`-Member ist ein Feld mit öffentlichem Zugriff.</span><span class="sxs-lookup"><span data-stu-id="135c6-257">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="135c6-258">Dies ist keine bewährte Vorgehensweise in der objektorientierten Programmierung, deshalb führen wir eine Änderung in eine Eigenschaft durch.</span><span class="sxs-lookup"><span data-stu-id="135c6-258">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="135c6-259">Für unsere Zwecke ist kein spezifischer Code zum Abrufen oder Festlegen der Eigenschaft erforderlich, aber die Änderung in eine Eigenschaft macht es leichter, diese Änderungen später hinzuzufügen, ohne die Lauffähigkeit von Code zu beeinträchtigen, der die `Repository`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="135c6-259">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="135c6-260">Entfernen Sie die Felddefinition, und ersetzen Sie sie durch eine [automatisch implementierte Eigenschaft](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="135c6-260">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="135c6-261">Der Compiler generiert den Körper der `get`- und `set`-Accessors sowie ein privates Feld zum Speichern des Namens.</span><span class="sxs-lookup"><span data-stu-id="135c6-261">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="135c6-262">Dies ähnelt dem folgenden Code, den Sie per Hand eingeben könnten:</span><span class="sxs-lookup"><span data-stu-id="135c6-262">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="135c6-263">Führen wir eine weitere Änderung durch, bevor wir neue Features hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="135c6-263">Let's make one more change before adding new features.</span></span> <span data-ttu-id="135c6-264">Die `ProcessRepositories`-Methode kann die asynchrone Arbeit erledigen und eine Auflistung der Repositorys zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="135c6-264">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="135c6-265">Geben wir die `List<Repository>` über diese Methode zurück, und verschieben wir den Code zum Schreiben dieser Informationen in die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="135c6-265">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="135c6-266">Ändern Sie die Signatur von `ProcessRepositories`, um einen Task zurückzugeben, dessen Ergebnis eine Liste mit `Repository`-Objekten ist:</span><span class="sxs-lookup"><span data-stu-id="135c6-266">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="135c6-267">Geben Sie anschließend einfach die Repositorys zurück, nachdem die JSON-Antwort verarbeitet wurde:</span><span class="sxs-lookup"><span data-stu-id="135c6-267">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="135c6-268">Der Compiler generiert das `Task<T>`-Objekt für die Rückgabe, weil Sie diese Methode als `async` markiert haben.</span><span class="sxs-lookup"><span data-stu-id="135c6-268">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="135c6-269">Ändern wir dann die `Main`-Methode, sodass sie diese Ergebnisse erfasst und den Namen jedes Repositorys an die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="135c6-269">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="135c6-270">Ihre `Main`-Methode sieht nun folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="135c6-270">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="135c6-271">Der Zugriff auf die `Result`-Eigenschaft ist bis zum Abschluss des Tasks blockiert.</span><span class="sxs-lookup"><span data-stu-id="135c6-271">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="135c6-272">Normalerweise wäre es vorzuziehen, wie in der `ProcessRepositories`-Methode mit `await` auf den Abschluss des Tasks zu warten, aber das ist in der `Main`-Methode nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="135c6-272">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="135c6-273">Einlesen weiterer Informationen</span><span class="sxs-lookup"><span data-stu-id="135c6-273">Reading More Information</span></span>

<span data-ttu-id="135c6-274">Zum Abschluss verarbeiten wir einige weitere Eigenschaften im JSON-Paket, das von der GitHub-API gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-274">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="135c6-275">Sie müssen nicht alle Informationen abrufen, aber das Hinzufügen einiger Eigenschaften veranschaulicht einige weitere Features von C#.</span><span class="sxs-lookup"><span data-stu-id="135c6-275">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="135c6-276">Beginnen wir damit, ein paar weitere einfache Typen in die Definition der `Repository`-Klasse einzufügen.</span><span class="sxs-lookup"><span data-stu-id="135c6-276">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="135c6-277">Fügen Sie diese Eigenschaften zu dieser Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="135c6-277">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="135c6-278">Diese Eigenschaften verfügen über integrierte Konvertierungen vom Zeichenfolgentyp (dieser ist in den JSON-Paketen enthalten) in den Zieltyp.</span><span class="sxs-lookup"><span data-stu-id="135c6-278">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="135c6-279">Der <xref:System.Uri> -Typ ist Ihnen möglicherweise neu.</span><span class="sxs-lookup"><span data-stu-id="135c6-279">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="135c6-280">Er repräsentiert einen URI, oder in diesem Fall eine URL.</span><span class="sxs-lookup"><span data-stu-id="135c6-280">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="135c6-281">Im Fall der `Uri`- und `int`-Typen wird über die Serialisierungsaktion eine Ausnahme ausgelöst, wenn das JSON-Paket Daten enthält, die nicht in den Zieltyp konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="135c6-281">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="135c6-282">Aktualisieren Sie nach dem Hinzufügen die `Main`-Methode, um diese Elemente anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="135c6-282">Once you've added these, update the `Main` method to display those elements:</span></span>

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
<span data-ttu-id="135c6-283">Im letzten Schritt fügen wir jetzt die Informationen für den letzten Pushvorgang hinzu.</span><span class="sxs-lookup"><span data-stu-id="135c6-283">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="135c6-284">Diese Informationen werden in der JSON-Antwort folgendermaßen formatiert:</span><span class="sxs-lookup"><span data-stu-id="135c6-284">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="135c6-285">Dieses Format entspricht nicht den standardmäßigen .NET-<xref:System.DateTime> -Formaten.</span><span class="sxs-lookup"><span data-stu-id="135c6-285">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="135c6-286">Deshalb müssen Sie eine benutzerdefinierte Konvertierungsmethode schreiben.</span><span class="sxs-lookup"><span data-stu-id="135c6-286">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="135c6-287">Darüber hinaus möchten Sie wahrscheinlich nicht, dass die unformatierte Zeichenfolge für Benutzer der `Repository`-Klasse verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="135c6-287">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="135c6-288">Dies kann ebenfalls mithilfe von Attributen gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="135c6-288">Attributes can help control that as well.</span></span> <span data-ttu-id="135c6-289">Definieren Sie zunächst eine `private`-Eigenschaft, die die Zeichenfolgendarstellung des DateTime-Werts in Ihrer `Repository`-Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="135c6-289">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="135c6-290">Das `DataMember`-Attribut informiert das Serialisierungsprogramm, dass eine Verarbeitung durchgeführt werden soll, obwohl es sich nicht um einen öffentlichen Member handelt.</span><span class="sxs-lookup"><span data-stu-id="135c6-290">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="135c6-291">Erstellen Sie als Nächstes eine schreibgeschützte öffentliche Eigenschaft, mit der die Zeichenfolge in ein gültiges <xref:System.DateTime>-Objekt konvertiert wird und diesen <xref:System.DateTime>-Wert zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="135c6-291">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="135c6-292">Gehen wir die neuen Konstrukte von oben durch.</span><span class="sxs-lookup"><span data-stu-id="135c6-292">Let's go over the new constructs above.</span></span> <span data-ttu-id="135c6-293">Das `IgnoreDataMember`-Attribut weist das Serialisierungsprogramm an, dass dieser Typ nicht aus einem JSON-Objekt gelesen oder geschrieben werden darf.</span><span class="sxs-lookup"><span data-stu-id="135c6-293">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="135c6-294">Diese Eigenschaft enthält nur einen `get`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="135c6-294">This property contains only a `get` accessor.</span></span> <span data-ttu-id="135c6-295">Es ist kein `set`-Accessor vorhanden.</span><span class="sxs-lookup"><span data-stu-id="135c6-295">There is no `set` accessor.</span></span> <span data-ttu-id="135c6-296">So wird eine *schreibgeschützte* Eigenschaft in C# definiert.</span><span class="sxs-lookup"><span data-stu-id="135c6-296">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="135c6-297">(Ja, Sie können *lesegeschützte* Eigenschaften in C# erstellen, aber ihr Wert ist begrenzt.) Die <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)>-Methode analysiert eine Zeichenfolge und erstellt ein <xref:System.DateTime>-Objekt mit dem angegebenen Datumsformat. Außerdem werden mit einem `CultureInfo`-Objekt zusätzliche Metadaten zu `DateTime` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="135c6-297">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="135c6-298">Wenn die Analyse nicht erfolgreich ist, löst der Eigenschaftsaccessor eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="135c6-298">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="135c6-299">Zur Verwendung von <xref:System.Globalization.CultureInfo.InvariantCulture> müssen Sie den <xref:System.Globalization> -Namespace zu den `using`-Anweisungen in `repo.cs` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="135c6-299">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="135c6-300">Abschließend fügen Sie eine weitere Ausgabeanweisung in der Konsole hinzu. Jetzt können Sie diese Anwendung erstellen und erneut ausführen:</span><span class="sxs-lookup"><span data-stu-id="135c6-300">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="135c6-301">Ihre Version sollte nun der [abgeschlossenen Version](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="135c6-301">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="135c6-302">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="135c6-302">Conclusion</span></span>

<span data-ttu-id="135c6-303">In diesem Tutorial wurde gezeigt, wie Sie Webanforderungen ausführen, das Ergebnis analysieren und Eigenschaften dieser Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="135c6-303">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="135c6-304">Sie haben außerdem neue Pakete als abhängige Komponenten in Ihr Projekt eingefügt.</span><span class="sxs-lookup"><span data-stu-id="135c6-304">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="135c6-305">Sie haben einige der Features von C# kennengelernt, die objektorientierte Verfahren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="135c6-305">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
