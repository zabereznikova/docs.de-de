---
title: Verarbeiten asynchroner Aufgaben nach Abschluss
description: In diesem Beispiel wird gezeigt, wie Sie mit Task.WhenAny in C# mehrere Tasks starten und deren Ergebnisse jeweils nach Abschluss der Durchführung verarbeiten, anstatt sie in der Reihenfolge zu verarbeiten, in der sie gestartet wurden.
ms.date: 08/19/2020
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 4cdd35af900863895911ea5c2c9772af362951ec
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615970"
---
# <a name="process-asynchronous-tasks-as-they-complete-c"></a><span data-ttu-id="cbdd5-103">Verarbeiten asynchroner Aufgaben nach Abschluss (C#)</span><span class="sxs-lookup"><span data-stu-id="cbdd5-103">Process asynchronous tasks as they complete (C#)</span></span>

<span data-ttu-id="cbdd5-104">Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-104">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they're completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="cbdd5-105">Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-105">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="cbdd5-106">Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-106">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="cbdd5-107">In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von <xref:System.Threading.Tasks.Task.WhenAny%2A> die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-107">In each iteration of a while loop, an awaited call to <xref:System.Threading.Tasks.Task.WhenAny%2A> returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="cbdd5-108">Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-108">That task is removed from the collection and processed.</span></span> <span data-ttu-id="cbdd5-109">Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-109">The loop repeats until the collection contains no more tasks.</span></span>

## <a name="create-example-application"></a><span data-ttu-id="cbdd5-110">Erstellen einer Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="cbdd5-110">Create example application</span></span>

<span data-ttu-id="cbdd5-111">Erstellen Sie eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-111">Create a new .NET Core console application.</span></span> <span data-ttu-id="cbdd5-112">Sie können mithilfe des [dotnet new console](../../../../core/tools/dotnet-new.md#console)-Befehls oder über [Visual Studio](/visualstudio/install/install-visual-studio) eine solche Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-112">You can create one by using the [dotnet new console](../../../../core/tools/dotnet-new.md#console) command or from [Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="cbdd5-113">Öffnen Sie die *Program.cs*-Datei in Ihrem bevorzugten Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-113">Open the *Program.cs* file in your favorite code editor.</span></span>

### <a name="replace-using-statements"></a><span data-ttu-id="cbdd5-114">Ersetzen von using-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="cbdd5-114">Replace using statements</span></span>

<span data-ttu-id="cbdd5-115">Ersetzen Sie die vorhandenen using-Anweisungen durch diese Deklarationen:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-115">Replace the existing using statements with these declarations:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;
```

## <a name="add-fields"></a><span data-ttu-id="cbdd5-116">Hinzufügen von Feldern</span><span class="sxs-lookup"><span data-stu-id="cbdd5-116">Add fields</span></span>

<span data-ttu-id="cbdd5-117">Fügen Sie in der `Program`-Klassendefinition die folgenden beiden Felder hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-117">In the `Program` class definition, add the following two fields:</span></span>

```csharp
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

<span data-ttu-id="cbdd5-118">Der `HttpClient` ermöglicht das Senden von HTTP-Anforderungen und das Empfangen von HTTP-Antworten.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-118">The `HttpClient` exposes the ability to send HTTP requests and receive HTTP responses.</span></span> <span data-ttu-id="cbdd5-119">Die `s_urlList` enthält alle URLs, die von der Anwendung verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-119">The `s_urlList` holds all of the URLs that the application plans to process.</span></span>

## <a name="update-application-entry-point"></a><span data-ttu-id="cbdd5-120">Aktualisieren des Einstiegspunkts der Anwendung</span><span class="sxs-lookup"><span data-stu-id="cbdd5-120">Update application entry point</span></span>

<span data-ttu-id="cbdd5-121">Der Haupteinstiegspunkt in die Konsolenanwendung ist die `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-121">The main entry point into the console application is the `Main` method.</span></span> <span data-ttu-id="cbdd5-122">Ersetzen Sie die vorhandene Methode durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-122">Replace the existing method with the following:</span></span>

```csharp
static Task Main() => SumPageSizesAsync();
```

<span data-ttu-id="cbdd5-123">Die aktualisierte `Main`-Methode wird jetzt als [Async main](../../../whats-new/csharp-7.md#async-main)-Methode betrachtet, die einen asynchronen Einstiegspunkt in die ausführbare Datei ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-123">The updated `Main` method is now considered an [Async main](../../../whats-new/csharp-7.md#async-main), which allows for an asynchronous entry point into the executable.</span></span> <span data-ttu-id="cbdd5-124">Sie wird mit einem Aufruf von `SumPageSizesAsync` angegeben.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-124">It is expressed a call to `SumPageSizesAsync`.</span></span>

## <a name="create-the-asynchronous-sum-page-sizes-method"></a><span data-ttu-id="cbdd5-125">Erstellen der SumPageSizesAsync-Methode</span><span class="sxs-lookup"><span data-stu-id="cbdd5-125">Create the asynchronous sum page sizes method</span></span>

<span data-ttu-id="cbdd5-126">Fügen Sie unter der `Main`-Methode die `SumPageSizesAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-126">Below the `Main` method, add the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task SumPageSizesAsync()
{
    var stopwatch = Stopwatch.StartNew();

    IEnumerable<Task<int>> downloadTasksQuery =
        from url in s_urlList
        select ProcessUrlAsync(url, s_client);

    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

    int total = 0;
    while (downloadTasks.Any())
    {
        Task<int> finishedTask = await Task.WhenAny(downloadTasks);
        downloadTasks.Remove(finishedTask);
        total += await finishedTask;
    }

    stopwatch.Stop();

    Console.WriteLine($"\nTotal bytes returned:  {total:#,#}");
    Console.WriteLine($"Elapsed time:          {stopwatch.Elapsed}\n");
}
```

<span data-ttu-id="cbdd5-127">Die Methode beginnt mit dem Instanziieren und Starten einer <xref:System.Diagnostics.Stopwatch>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-127">The method starts by instantiating and starting a <xref:System.Diagnostics.Stopwatch>.</span></span> <span data-ttu-id="cbdd5-128">Dann ist eine Abfrage enthalten, die eine Auflistung von Aufgaben erstellt, wenn sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-128">It then includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="cbdd5-129">Jeder Aufruf von `ProcessUrlAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-129">Each call to `ProcessUrlAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery =
    from url in s_urlList
    select ProcessUrlAsync(url, s_client);
```

<span data-ttu-id="cbdd5-130">Aufgrund der [verzögerten Ausführung](../../../../standard/linq/deferred-execution-example.md) mit LINQ wird <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> aufgerufen, um die einzelnen Aufgaben zu starten.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-130">Due to [deferred execution](../../../../standard/linq/deferred-execution-example.md) with the LINQ, you call <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> to start each task.</span></span>

```csharp
List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
```

<span data-ttu-id="cbdd5-131">Die `while`-Schleife führt die folgenden Schritte für jede Aufgabe in der Auflistung aus:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-131">The `while` loop performs the following steps for each task in the collection:</span></span>

1. <span data-ttu-id="cbdd5-132">Es wird ein Aufruf von `WhenAny` erwartet, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet hat.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-132">Awaits a call to `WhenAny` to identify the first task in the collection that has finished its download.</span></span>

    ```csharp
    Task<int> finishedTask = await Task.WhenAny(downloadTasks);
    ```

1. <span data-ttu-id="cbdd5-133">Entfernt die entsprechende Aufgabe aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-133">Removes that task from the collection.</span></span>

    ```csharp
    downloadTasks.Remove(finishedTask);
    ```

1. <span data-ttu-id="cbdd5-134">Erwartet `finishedTask`, das durch einen Aufruf von `ProcessUrlAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-134">Awaits `finishedTask`, which is returned by a call to `ProcessUrlAsync`.</span></span> <span data-ttu-id="cbdd5-135">Die Variable `finishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-135">The `finishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span> <span data-ttu-id="cbdd5-136">Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-136">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="cbdd5-137">Wenn für die Aufgabe ein Fehler auftritt, löst `await` im Gegensatz zum Lesen der <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>-Eigenschaft, die die `AggregateException` auslösen würde, die erste untergeordnete Ausnahme aus, die in der `AggregateException` gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-137">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> property, which would throw the `AggregateException`.</span></span>

    ```csharp
    total += await finishedTask;
    ```

## <a name="add-process-method"></a><span data-ttu-id="cbdd5-138">Hinzufügen der Prozessmethode</span><span class="sxs-lookup"><span data-stu-id="cbdd5-138">Add process method</span></span>

<span data-ttu-id="cbdd5-139">Fügen Sie die folgende `ProcessUrlAsync`-Methode unterhalb der `SumPageSizesAsync`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="cbdd5-139">Add the following `ProcessUrlAsync` method below the `SumPageSizesAsync` method:</span></span>

```csharp
static async Task<int> ProcessUrlAsync(string url, HttpClient client)
{
    byte[] content = await client.GetByteArrayAsync(url);
    Console.WriteLine($"{url,-60} {content.Length,10:#,#}");

    return content.Length;
}
```

<span data-ttu-id="cbdd5-140">Für eine beliebige URL verwendet die Methode die `client`-Instanz, die bereitgestellt wird, um die Antwort als `byte[]` zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-140">For any given URL, the method will use the `client` instance provided to get the response as a `byte[]`.</span></span> <span data-ttu-id="cbdd5-141">Die Länge wird zurückgegeben, nachdem die URL und die Länge in die Konsole geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-141">The length is returned after the URL and length is written to the console.</span></span>

<span data-ttu-id="cbdd5-142">Führen Sie das Programm mehrmals aus, um zu bestätigen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-142">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="cbdd5-143">Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-143">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="cbdd5-144">Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-144">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="cbdd5-145">Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span><span class="sxs-lookup"><span data-stu-id="cbdd5-145">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete).</span></span>

## <a name="complete-example"></a><span data-ttu-id="cbdd5-146">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbdd5-146">Complete example</span></span>

<span data-ttu-id="cbdd5-147">Der folgende Code besteht aus dem vollständigen Text der *Program.cs*-Datei für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cbdd5-147">The following code is the complete text of the *Program.cs* file for the example.</span></span>

:::code language="csharp" source="snippets/multiple-tasks/Program.cs":::

## <a name="see-also"></a><span data-ttu-id="cbdd5-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbdd5-148">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="cbdd5-149">Asynchrone Programmierung mit Async und Await (C#)</span><span class="sxs-lookup"><span data-stu-id="cbdd5-149">Asynchronous programming with async and await (C#)</span></span>](index.md)
