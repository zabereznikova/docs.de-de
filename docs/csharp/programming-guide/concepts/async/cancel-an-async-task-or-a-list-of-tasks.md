---
title: Abbrechen einer Aufgabenliste (C#)
description: In diesem Artikel erfahren Sie, wie Sie Abbruchtoken verwenden, um eine Abbruchanforderung für eine Aufgabenliste zu signalisieren.
ms.date: 08/19/2020
ms.topic: tutorial
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
ms.openlocfilehash: 84cd1bb413d20b6c13be8415c13c72b57873b1cf
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654704"
---
# <a name="cancel-a-list-of-tasks-c"></a><span data-ttu-id="a278e-103">Abbrechen einer Aufgabenliste (C#)</span><span class="sxs-lookup"><span data-stu-id="a278e-103">Cancel a list of tasks (C#)</span></span>

<span data-ttu-id="a278e-104">Sie können eine asynchrone Konsolenanwendung abbrechen, wenn Sie nicht auf den Abschluss ihrer Ausführung warten möchten.</span><span class="sxs-lookup"><span data-stu-id="a278e-104">You can cancel an async console application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="a278e-105">Anhand des in diesem Artikel veranschaulichten Beispiels können Sie einen Abbruch zu einer Anwendung hinzufügen, die die Inhalte von einer Liste von Websites herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="a278e-105">By following the example in this topic, you can add a cancellation to an application that downloads the contents of a list of websites.</span></span> <span data-ttu-id="a278e-106">Sie können viele Aufgaben abbrechen, indem Sie die <xref:System.Threading.CancellationTokenSource>-Instanz jeder Aufgabe zuordnen.</span><span class="sxs-lookup"><span data-stu-id="a278e-106">You can cancel many tasks by associating the <xref:System.Threading.CancellationTokenSource> instance with each task.</span></span> <span data-ttu-id="a278e-107">Wenn Sie die <kbd>EINGABETASTE</kbd> drücken, brechen Sie alle Aufgaben ab, die noch nicht abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="a278e-107">If you select the <kbd>Enter</kbd> key, you cancel all tasks that aren't yet complete.</span></span>

<span data-ttu-id="a278e-108">In diesem Lernprogramm wird Folgendes behandelt:</span><span class="sxs-lookup"><span data-stu-id="a278e-108">This tutorial covers:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="a278e-109">Erstellen einer .NET-Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="a278e-109">Creating a .NET console application</span></span>
> - <span data-ttu-id="a278e-110">Schreiben einer asynchronen Anwendung, die einen Abbruch unterstützt</span><span class="sxs-lookup"><span data-stu-id="a278e-110">Writing an async application that supports cancellation</span></span>
> - <span data-ttu-id="a278e-111">Veranschaulichung der Signalisierung eines Abbruchs</span><span class="sxs-lookup"><span data-stu-id="a278e-111">Demonstrating signaling cancellation</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a278e-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a278e-112">Prerequisites</span></span>

<span data-ttu-id="a278e-113">Für dieses Lernprogramm ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="a278e-113">This tutorial requires the following:</span></span>

- [<span data-ttu-id="a278e-114">.NET SDK 5.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="a278e-114">.NET 5.0 or later SDK</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- <span data-ttu-id="a278e-115">Integrierte Entwicklungsumgebung (Integrated Development Environment, IDE)</span><span class="sxs-lookup"><span data-stu-id="a278e-115">Integrated development environment (IDE)</span></span>
  - [<span data-ttu-id="a278e-116">Es wird empfohlen, Visual Studio, Visual Studio Code oder Visual Studio für Mac zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a278e-116">We recommend Visual Studio, Visual Studio Code, or Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com)

### <a name="create-example-application"></a><span data-ttu-id="a278e-117">Erstellen einer Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="a278e-117">Create example application</span></span>

<span data-ttu-id="a278e-118">Erstellen Sie eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="a278e-118">Create a new .NET Core console application.</span></span> <span data-ttu-id="a278e-119">Sie können eine solche Anwendung mithilfe des Befehls [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) oder über [Visual Studio](/visualstudio/install/install-visual-studio) erstellen.</span><span class="sxs-lookup"><span data-stu-id="a278e-119">You can create one by using the [`dotnet new console`](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="a278e-120">Öffnen Sie die *Program.cs*-Datei in Ihrem bevorzugten Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="a278e-120">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="a278e-121">Ersetzen von using-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a278e-121">Replace using statements</span></span>

<span data-ttu-id="a278e-122">Ersetzen Sie die vorhandenen using-Anweisungen durch diese Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="a278e-122">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Net.Http;
using System.Threading;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="a278e-123">Hinzufügen von Feldern</span><span class="sxs-lookup"><span data-stu-id="a278e-123">Add fields</span></span>

<span data-ttu-id="a278e-124">Fügen Sie die folgenden drei Felder in der `Program`-Klassendefinition hinzu:</span><span class="sxs-lookup"><span data-stu-id="a278e-124">In the `Program` class definition, add these three fields:</span></span>

```csharp
static readonly CancellationTokenSource s_cts = new CancellationTokenSource();

static readonly HttpClient s_client = new HttpClient
{
    MaxResponseContentBufferSize = 1_000_000
};

static readonly IEnumerable<string> s_urlList = new string[]
{
    "https://docs.microsoft.com",
    "https://docs.microsoft.com/aspnet/core",
    "https://docs.microsoft.com/azure",
    "https://docs.microsoft.com/azure/devops",
    "https://docs.microsoft.com/dotnet",
    "https://docs.microsoft.com/dynamics365",
    "https://docs.microsoft.com/education",
    "https://docs.microsoft.com/enterprise-mobility-security",
    "https://docs.microsoft.com/gaming",
    "https://docs.microsoft.com/graph",
    "https://docs.microsoft.com/microsoft-365",
    "https://docs.microsoft.com/office",
    "https://docs.microsoft.com/powershell",
    "https://docs.microsoft.com/sql",
    "https://docs.microsoft.com/surface",
    "https://docs.microsoft.com/system-center",
    "https://docs.microsoft.com/visualstudio",
    "https://docs.microsoft.com/windows",
    "https://docs.microsoft.com/xamarin"
};
```

<span data-ttu-id="a278e-125"><xref:System.Threading.CancellationTokenSource> wird dazu verwendet, einen angeforderten Abbruch für <xref:System.Threading.CancellationToken> zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="a278e-125">The <xref:System.Threading.CancellationTokenSource> is used to signal a requested cancellation to a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="a278e-126">`HttpClient` ermöglicht das Senden und Empfangen von HTTP-Antworten.</span><span class="sxs-lookup"><span data-stu-id="a278e-126">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="a278e-127">`s_urlList` enthält alle URLs, die von der Anwendung verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a278e-127">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="a278e-128">Aktualisieren des Einstiegspunkts der Anwendung</span><span class="sxs-lookup"><span data-stu-id="a278e-128">Update application entry point</span></span>

<span data-ttu-id="a278e-129">Der Haupteinstiegspunkt in die Konsolenanwendung ist die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="a278e-129">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="a278e-130">Ersetzen Sie die vorhandene Methode durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a278e-130">Replace the existing method with the following:</span></span>

```csharp
static async Task Main()
{
    Console.WriteLine("Application started.");
    Console.WriteLine("Press the ENTER key to cancel...\n");

    Task cancelTask = Task.Run(() =>
    {
        while (Console.ReadKey().Key != ConsoleKey.Enter)
        {
            Console.WriteLine("Press the ENTER key to cancel...");
        }

        Console.WriteLine("\nENTER key pressed: cancelling downloads.\n");
        s_cts.Cancel();
    });

    Task sumPageSizesTask = SumPageSizesAsync();

    await Task.WhenAny(new[] { cancelTask, sumPageSizesTask });

    Console.WriteLine("Application ending.");
}
```

<span data-ttu-id="a278e-131">Die aktualisierte `Main`-Methode wird jetzt als [Async main](../../../whats-new/csharp-7-1.md#async-main)-Methode betrachtet, die einen asynchronen Einstiegspunkt in die ausführbare Datei ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a278e-131">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7-1.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="a278e-132">Sie schreibt einige Anweisungsnachrichten an die Konsole und deklariert dann eine <xref:System.Threading.Tasks.Task>-Instanz namens `cancelTask`, die Tastatureingaben in die Konsole liest.</span><span class="sxs-lookup"><span data-stu-id="a278e-132">It writes a few instructional messages to the console, then declares a <xref:System.Threading.Tasks.Task> instance named `cancelTask`, which will read console key strokes.</span></span> <span data-ttu-id="a278e-133">Wenn die <kbd>EINGABETASTE</kbd> gedrückt wird, wird ein Aufruf an <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a278e-133">If the <kbd>Enter</kbd> key is pressed, a call to <xref:System.Threading.CancellationTokenSource.Cancel?displayProperty=nameWithType> is made.</span></span> <span data-ttu-id="a278e-134">Dies signalisiert den Abbruch.</span><span class="sxs-lookup"><span data-stu-id="a278e-134">This will signal cancellation.</span></span> <span data-ttu-id="a278e-135">Dann wird eine `sumPageSizesTask`-Variable der `SumPageSizesAsync`-Methode zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a278e-135">Next, the `sumPageSizesTask` variable is assigned from the `SumPageSizesAsync` method.</span></span> <span data-ttu-id="a278e-136">Beide Aufgaben werden dann an <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType> übergeben, was fortgesetzt wird, wenn eine der beiden Aufgaben abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a278e-136">Both tasks are then passed to <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])?displayProperty=nameWithType>, which will continue when any of the two tasks have completed.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="a278e-137">Erstellen der SumPageSizesAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="a278e-137">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="a278e-138">Fügen Sie unter der `Main`-Methode die `SumPageSizesAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="a278e-138">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    int total = 0;
    foreach (string url in s_urlList)
    {
        int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
        total += contentLength;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="a278e-139">Die Methode beginnt mit dem Instanziieren und Starten einer <xref:System.Diagnostics.Stopwatch>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a278e-139">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="a278e-140">Anschließend durchläuft sie alle URLs in `s_urlList` und ruft `ProcessUrlAsync` auf.</span><span class="sxs-lookup"><span data-stu-id="a278e-140">It then loops through each URL in the `s_urlList` and calls `ProcessUrlAsync`.</span></span> <span data-ttu-id="a278e-141">Mit jeder Iteration wird `s_cts.Token` an die `ProcessUrlAsync`-Methode übergeben, und der Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` ein Integer ist:</span><span class="sxs-lookup"><span data-stu-id="a278e-141">With each iteration, the `s_cts.Token` is passed into the `ProcessUrlAsync` method and the code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
int total = 0;
foreach (string url in s_urlList)
{
    int contentLength = await ProcessUrlAsync(url, s_client, s_cts.Token);
    total += contentLength;
}
```

## <a name="add-process-method"></a><span data-ttu-id="a278e-142">Hinzufügen der Prozessmethode</span><span class="sxs-lookup"><span data-stu-id="a278e-142">Add process method</span></span>

<span data-ttu-id="a278e-143">Fügen Sie die folgende `ProcessUrlAsync`-Methode unterhalb der `SumPageSizesAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="a278e-143">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client, CancellationToken token)
{
    HttpResponseMessage response = await client.GetAsync(url, token);
    byte[] content = await response.Content.ReadAsByteArrayAsync();
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="a278e-144">Für eine beliebige URL verwendet die Methode die `client`-Instanz, die bereitgestellt wird, um die Antwort als `byte[]` zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a278e-144">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="a278e-145">Die <xref:System.Threading.CancellationToken>-Instanz wird an die Methoden <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> und <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> übergeben.</span><span class="sxs-lookup"><span data-stu-id="a278e-145">The <xref:System.Threading.CancellationToken> instance is passed into the <xref:System.Net.Http.HttpClient.GetAsync(System.String,System.Threading.CancellationToken)?displayProperty=nameWithType> and <xref:System.Net.Http.HttpContent.ReadAsByteArrayAsync?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a278e-146">`token` wird dazu verwendet, den angeforderten Abbruch zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="a278e-146">The `token` is used to register for requested cancellation.</span></span> <span data-ttu-id="a278e-147">Die Länge wird zurückgegeben, nachdem die URL und die Länge in die Konsole geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="a278e-147">The length is returned after the URL and length is written to the console.</span></span>

### <a name="example-application-output"></a><span data-ttu-id="a278e-148">Ausgabe der Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="a278e-148">Example application output</span></span>

```console
Application started.
Press the ENTER key to cancel...

https://docs.microsoft.com                                       37,357
https://docs.microsoft.com/aspnet/core                           85,589
https://docs.microsoft.com/azure                                398,939
https://docs.microsoft.com/azure/devops                          73,663
https://docs.microsoft.com/dotnet                                67,452
https://docs.microsoft.com/dynamics365                           48,582
https://docs.microsoft.com/education                             22,924

ENTER key pressed: cancelling downloads.

Application ending.
```

## <a name="complete-example"></a><span data-ttu-id="a278e-149">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="a278e-149">Complete example</span></span>

<span data-ttu-id="a278e-150">Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a278e-150">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/cancel-tasks/cancel-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="a278e-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a278e-151">See also</span></span>

- <xref:System.Threading.CancellationToken>
- <xref:System.Threading.CancellationTokenSource>
- [<span data-ttu-id="a278e-152">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="a278e-152">Asynchronous programming with async and await (C#)</span></span>](index.md)

## <a name="next-steps"></a><span data-ttu-id="a278e-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a278e-153">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a278e-154">Abbrechen asynchroner Aufgaben nach einem bestimmten Zeitraum (C#)</span><span class="sxs-lookup"><span data-stu-id="a278e-154">Cancel async tasks after a period of time (C#)</span></span>](cancel-async-tasks-after-a-period-of-time.md)
