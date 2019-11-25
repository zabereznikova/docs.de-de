---
title: 'Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)'
ms.date: 07/20/2015
ms.assetid: f6927ef2-dc6c-43f8-bc82-bbeac42de423
ms.openlocfilehash: afd7dda4e876b7faa54ae4a8e62d640d2b9aaf07
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970025"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-c"></a><span data-ttu-id="b9538-102">Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)</span><span class="sxs-lookup"><span data-stu-id="b9538-102">How to extend the async walkthrough by using Task.WhenAll (C#)</span></span>

<span data-ttu-id="b9538-103">Sie können die Leistung der asynchronen Projektmappe in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) verbessern, indem Sie die <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9538-103">You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b9538-104">Diese Methode wartet auf mehrere asynchrone Vorgänge, die als Auflistung von Aufgaben dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b9538-104">This method asynchronously awaits multiple asynchronous operations, which are represented as a collection of tasks.</span></span>

<span data-ttu-id="b9538-105">Sie haben möglicherweise in der exemplarischen Vorgehensweise bemerkt, dass die Websites Downloads in verschiedenen Geschwindigkeiten anbieten.</span><span class="sxs-lookup"><span data-stu-id="b9538-105">You might have noticed in the walkthrough that the websites download at different rates.</span></span> <span data-ttu-id="b9538-106">Manchmal ist eine Website sehr langsam und verzögert alle verbleibenden Downloads.</span><span class="sxs-lookup"><span data-stu-id="b9538-106">Sometimes one of the websites is very slow, which delays all the remaining downloads.</span></span> <span data-ttu-id="b9538-107">Wenn Sie die asynchronen Projektmappen ausführen, die Sie in der exemplarischen Vorgehensweise erstellt haben, können Sie das Programm einfach beenden, wenn Sie nicht warten möchten. Eine bessere Option wäre jedoch, alle Downloads gleichzeitig zu starten und schnellere Downloads einfach fortfahren, ohne auf langsamere zu warten.</span><span class="sxs-lookup"><span data-stu-id="b9538-107">When you run the asynchronous solutions that you build in the walkthrough, you can end the program easily if you don't want to wait, but a better option would be to start all the downloads at the same time and let faster downloads continue without waiting for the one that’s delayed.</span></span>

<span data-ttu-id="b9538-108">Sie wenden die `Task.WhenAll`-Methode auf eine Aufgabenauflistung an.</span><span class="sxs-lookup"><span data-stu-id="b9538-108">You apply the `Task.WhenAll` method to a collection of tasks.</span></span> <span data-ttu-id="b9538-109">Die Anwendung von `WhenAll` gibt eine einzelne Aufgabe zurück, die nicht abgeschlossen ist, bevor jede Aufgabe in der Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b9538-109">The application of `WhenAll` returns a single task that isn’t complete until every task in the collection is completed.</span></span> <span data-ttu-id="b9538-110">Die Aufgaben scheinen parallel ausgeführt zu werden, es werden jedoch keine weiteren Threads erstellt.</span><span class="sxs-lookup"><span data-stu-id="b9538-110">The tasks appear to run in parallel, but no additional threads are created.</span></span> <span data-ttu-id="b9538-111">Die Aufgaben können in jeder Reihenfolge abschließen.</span><span class="sxs-lookup"><span data-stu-id="b9538-111">The tasks can complete in any order.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9538-112">Die folgenden Prozeduren beschreiben Erweiterungen zu asynchronen Anwendungen, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9538-112">The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="b9538-113">Sie können die Anwendungen entwickeln, indem Sie entweder die exemplarische Vorgehensweise durcharbeiten oder den Code von [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b9538-113">You can develop the applications by either completing the walkthrough or downloading the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>
>
> <span data-ttu-id="b9538-114">Für die Ausführung des Beispiels muss Visual Studio 2012 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b9538-114">To run the example, you must have Visual Studio 2012 or later installed on your computer.</span></span>

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a><span data-ttu-id="b9538-115">So fügen Sie der GetURLContentsAsync-Lösung Task.WhenAll hinzu</span><span class="sxs-lookup"><span data-stu-id="b9538-115">To add Task.WhenAll to your GetURLContentsAsync solution</span></span>

1. <span data-ttu-id="b9538-116">Fügen Sie die `ProcessURLAsync`-Methode der ersten Anwendung hinzu, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9538-116">Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="b9538-117">Wenn Sie die [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) heruntergeladen haben, öffnen Sie das „AsyncWalkthrough“-Projekt, und fügen Sie dann `ProcessURLAsync` der Datei „MainWindow.xaml.cs“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9538-117">If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="b9538-118">Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `GetURLContentsAsync`-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="b9538-118">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that includes the `GetURLContentsAsync` method.</span></span> <span data-ttu-id="b9538-119">Die Datei „MainWindow.xaml.cs“ für diese Anwendung ist das erste Beispiel im Abschnitt „Vollständige Codebeispiele der exemplarischen Vorgehensweise“.</span><span class="sxs-lookup"><span data-stu-id="b9538-119">The MainWindow.xaml.cs file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="b9538-120">Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `foreach`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="b9538-120">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="b9538-121">Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.</span><span class="sxs-lookup"><span data-stu-id="b9538-121">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    ```csharp
    private async Task<int> ProcessURLAsync(string url)
    {
        var byteArray = await GetURLContentsAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="b9538-122">Kommentieren Sie die Schleife `foreach` in `SumPageSizesAsync` aus, oder löschen Sie sie, wie der folgenden Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="b9538-122">Comment out or delete the `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    byte[] urlContents = await GetURLContentsAsync(url);

    //    // The previous line abbreviates the following two assignment statements.
    //    // GetURLContentsAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
    //    //byte[] urlContents = await getContentsTask;

    //    DisplayResults(url, urlContents);

    //    // Update the total.
    //    total += urlContents.Length;
    //}
    ```

3. <span data-ttu-id="b9538-123">Erstellen Sie eine Auflistung von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="b9538-123">Create a collection of tasks.</span></span> <span data-ttu-id="b9538-124">Der folgende Code definiert eine [Abfrage](../linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="b9538-124">The following code defines a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="b9538-125">Die Aufgaben werden beim Auswerten der Abfrage gestartet.</span><span class="sxs-lookup"><span data-stu-id="b9538-125">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="b9538-126">Fügen Sie nach der Deklaration von `SumPageSizesAsync` den folgenden Code der `urlList`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b9538-126">Add the following code to method `SumPageSizesAsync` after the declaration of `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="b9538-127">Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben `downloadTasks` an.</span><span class="sxs-lookup"><span data-stu-id="b9538-127">Apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="b9538-128">`Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="b9538-128">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="b9538-129">Im folgenden Beispiel erwartet der `await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b9538-129">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="b9538-130">Der Ausdruck wird gegen ein Array mit ganzen Zahlen ausgewertet, wobei jede ganze Zahl die Länge einer heruntergeladenen Website ist.</span><span class="sxs-lookup"><span data-stu-id="b9538-130">The expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="b9538-131">Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.</span><span class="sxs-lookup"><span data-stu-id="b9538-131">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="b9538-132">Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b9538-132">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to calculate the sum of the lengths of all the websites.</span></span> <span data-ttu-id="b9538-133">Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9538-133">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a><span data-ttu-id="b9538-134">So fügen Sie der HttpClient.GetByteArrayAsync-Lösung Task.WhenAll hinzu</span><span class="sxs-lookup"><span data-stu-id="b9538-134">To add Task.WhenAll to the HttpClient.GetByteArrayAsync solution</span></span>

1. <span data-ttu-id="b9538-135">Fügen Sie die folgende Version von `ProcessURLAsync` der zweiten Anwendung hinzu, die in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="b9538-135">Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="b9538-136">Wenn Sie den Code von [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) heruntergeladen haben, öffnen Sie das „AsyncWalkthrough_HttpClient“-Projekt und fügen dann `ProcessURLAsync` entweder der „MainWindow.xaml.cs“-Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9538-136">If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.cs file.</span></span>

    - <span data-ttu-id="b9538-137">Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `HttpClient.GetByteArrayAsync`-Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9538-137">If you developed the code by completing the walkthrough, add `ProcessURLAsync` to the application that uses the `HttpClient.GetByteArrayAsync` method.</span></span> <span data-ttu-id="b9538-138">Die „MainWindow.xaml.cs“-Datei für diese Anwendung ist das zweite Beispiel im Abschnitt „Vollständige Codebeispiele der exemplarischen Vorgehensweise“.</span><span class="sxs-lookup"><span data-stu-id="b9538-138">The MainWindow.xaml.cs file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.</span></span>

    <span data-ttu-id="b9538-139">Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `foreach`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="b9538-139">The `ProcessURLAsync` method consolidates the actions in the body of the `foreach` loop in `SumPageSizesAsync` in the original walkthrough.</span></span> <span data-ttu-id="b9538-140">Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.</span><span class="sxs-lookup"><span data-stu-id="b9538-140">The method asynchronously downloads the contents of a specified website as a byte array, and then displays and returns the length of the byte array.</span></span>

    <span data-ttu-id="b9538-141">Der einzige Unterschied der `ProcessURLAsync`-Methode in der vorherigen Prozedur ist die Verwendung der <xref:System.Net.Http.HttpClient>-Instanz, `client`.</span><span class="sxs-lookup"><span data-stu-id="b9538-141">The only difference from the `ProcessURLAsync` method in the previous procedure is the use of the <xref:System.Net.Http.HttpClient> instance, `client`.</span></span>

    ```csharp
    async Task<int> ProcessURLAsync(string url, HttpClient client)
    {
        byte[] byteArray = await client.GetByteArrayAsync(url);
        DisplayResults(url, byteArray);
        return byteArray.Length;
    }
    ```

2. <span data-ttu-id="b9538-142">Kommentieren Sie die Schleife `For Each` oder `foreach` in `SumPageSizesAsync` aus oder löschen Sie sie, wie der folgenden Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="b9538-142">Comment out or delete the `For Each` or `foreach` loop in `SumPageSizesAsync`, as the following code shows.</span></span>

    ```csharp
    //var total = 0;
    //foreach (var url in urlList)
    //{
    //    // GetByteArrayAsync returns a Task<T>. At completion, the task
    //    // produces a byte array.
    //    byte[] urlContent = await client.GetByteArrayAsync(url);

    //    // The previous line abbreviates the following two assignment
    //    // statements.
    //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
    //    byte[] urlContent = await getContentTask;

    //    DisplayResults(url, urlContent);

    //    // Update the total.
    //    total += urlContent.Length;
    //}
    ```

3. <span data-ttu-id="b9538-143">Definieren Sie eine [Abfrage](../linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="b9538-143">Define a [query](../linq/index.md) that, when executed by the <xref:System.Linq.Enumerable.ToArray%2A> method, creates a collection of tasks that download the contents of each website.</span></span> <span data-ttu-id="b9538-144">Die Aufgaben werden beim Auswerten der Abfrage gestartet.</span><span class="sxs-lookup"><span data-stu-id="b9538-144">The tasks are started when the query is evaluated.</span></span>

    <span data-ttu-id="b9538-145">Fügen Sie nach der Deklaration von `SumPageSizesAsync` und `client` den folgenden Code der `urlList`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b9538-145">Add the following code to method `SumPageSizesAsync` after the declaration of `client` and `urlList`.</span></span>

    ```csharp
    // Create a query.
    IEnumerable<Task<int>> downloadTasksQuery =
        from url in urlList select ProcessURLAsync(url, client);

    // Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();
    ```

4. <span data-ttu-id="b9538-146">Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben an, `downloadTasks`.</span><span class="sxs-lookup"><span data-stu-id="b9538-146">Next, apply `Task.WhenAll` to the collection of tasks, `downloadTasks`.</span></span> <span data-ttu-id="b9538-147">`Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="b9538-147">`Task.WhenAll` returns a single task that finishes when all the tasks in the collection of tasks have completed.</span></span>

    <span data-ttu-id="b9538-148">Im folgenden Beispiel erwartet der `await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b9538-148">In the following example, the `await` expression awaits the completion of the single task that `WhenAll` returns.</span></span> <span data-ttu-id="b9538-149">Wenn vollständig, wertet der `await`-Ausdruck als Ergebnis ein Array von ganzen Zahlen aus, wobei jede ganze Zahl die Länge einer heruntergeladenen Website hat.</span><span class="sxs-lookup"><span data-stu-id="b9538-149">When complete, the `await` expression evaluates to an array of integers, where each integer is the length of a downloaded website.</span></span> <span data-ttu-id="b9538-150">Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.</span><span class="sxs-lookup"><span data-stu-id="b9538-150">Add the following code to `SumPageSizesAsync`, just after the code that you added in the previous step.</span></span>

    ```csharp
    // Await the completion of all the running tasks.
    int[] lengths = await Task.WhenAll(downloadTasks);

    //// The previous line is equivalent to the following two statements.
    //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
    //int[] lengths = await whenAllTask;
    ```

5. <span data-ttu-id="b9538-151">Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b9538-151">Finally, use the <xref:System.Linq.Enumerable.Sum%2A> method to get the sum of the lengths of all the websites.</span></span> <span data-ttu-id="b9538-152">Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="b9538-152">Add the following line to `SumPageSizesAsync`.</span></span>

    ```csharp
    int total = lengths.Sum();
    ```

### <a name="to-test-the-taskwhenall-solutions"></a><span data-ttu-id="b9538-153">So testen Sie die Task.WhenAll-Lösungen</span><span class="sxs-lookup"><span data-stu-id="b9538-153">To test the Task.WhenAll solutions</span></span>

- <span data-ttu-id="b9538-154">Drücken Sie in beiden Projektmappen F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten**.</span><span class="sxs-lookup"><span data-stu-id="b9538-154">For either solution, choose the F5 key to run the program, and then choose the **Start** button.</span></span> <span data-ttu-id="b9538-155">Die Ausgabe sollte der Ausgabe der asynchronen Projektmappen in [Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b9538-155">The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using async and await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="b9538-156">Beachten Sie jedoch, dass die Websites in einer jeweils anderen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b9538-156">However, notice that the websites appear in a different order each time.</span></span>

## <a name="example"></a><span data-ttu-id="b9538-157">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9538-157">Example</span></span>

<span data-ttu-id="b9538-158">Der folgende Code zeigt die Erweiterungen des Projekts, das die `GetURLContentsAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b9538-158">The following code shows the extensions to the project that uses the `GetURLContentsAsync` method to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Two-step async call.
            Task sumTask = SumPageSizesAsync();
            await sumTask;

            // One-step async call.
            //await SumPageSizesAsync();

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    byte[] urlContents = await GetURLContentsAsync(url);

            //    // The previous line abbreviates the following two assignment statements.
            //    // GetURLContentsAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    //Task<byte[]> getContentsTask = GetURLContentsAsync(url);
            //    //byte[] urlContents = await getContentsTask;

            //    DisplayResults(url, urlContents);

            //    // Update the total.
            //    total += urlContents.Length;
            //}

            // Display the total count for all of the websites.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        private async Task<int> ProcessURLAsync(string url)
        {
            var byteArray = await GetURLContentsAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private async Task<byte[]> GetURLContentsAsync(string url)
        {
            // The downloaded resource ends up in the variable named content.
            var content = new MemoryStream();

            // Initialize an HttpWebRequest for the current URL.
            var webReq = (HttpWebRequest)WebRequest.Create(url);

            // Send the request to the Internet resource and wait for
            // the response.
            using (WebResponse response = await webReq.GetResponseAsync())
            {
                // Get the data stream that is associated with the specified url.
                using (Stream responseStream = response.GetResponseStream())
                {
                    await responseStream.CopyToAsync(content);
                }
            }

            // Return the result as a byte array.
            return content.ToArray();

        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="example"></a><span data-ttu-id="b9538-159">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9538-159">Example</span></span>

<span data-ttu-id="b9538-160">Der folgende Code zeigt die Erweiterungen des Projekts, das die `HttpClient.GetByteArrayAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.</span><span class="sxs-lookup"><span data-stu-id="b9538-160">The following code shows the extensions to the project that uses method `HttpClient.GetByteArrayAsync` to download content from the web.</span></span>

```csharp
// Add the following using directives, and add a reference for System.Net.Http.
using System.Net.Http;
using System.IO;
using System.Net;

namespace AsyncExampleWPF_HttpClient_WhenAll
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // One-step async call.
            await SumPageSizesAsync();

            // Two-step async call.
            //Task sumTask = SumPageSizesAsync();
            //await sumTask;

            resultsTextBox.Text += "\r\nControl returned to startButton_Click.\r\n";
        }

        private async Task SumPageSizesAsync()
        {
            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // Declare an HttpClient object and increase the buffer size. The
            // default buffer size is 65,536.
            HttpClient client = new HttpClient() { MaxResponseContentBufferSize = 1000000 };

            // Create a query.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURLAsync(url, client);

            // Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();

            // You can do other work here before awaiting.

            // Await the completion of all the running tasks.
            int[] lengths = await Task.WhenAll(downloadTasks);

            //// The previous line is equivalent to the following two statements.
            //Task<int[]> whenAllTask = Task.WhenAll(downloadTasks);
            //int[] lengths = await whenAllTask;

            int total = lengths.Sum();

            //var total = 0;
            //foreach (var url in urlList)
            //{
            //    // GetByteArrayAsync returns a Task<T>. At completion, the task
            //    // produces a byte array.
            //    byte[] urlContent = await client.GetByteArrayAsync(url);

            //    // The previous line abbreviates the following two assignment
            //    // statements.
            //    Task<byte[]> getContentTask = client.GetByteArrayAsync(url);
            //    byte[] urlContent = await getContentTask;

            //    DisplayResults(url, urlContent);

            //    // Update the total.
            //    total += urlContent.Length;
            //}

            // Display the total count for all of the web addresses.
            resultsTextBox.Text +=
                $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        // The actions from the foreach loop are moved to this async method.
        async Task<int> ProcessURLAsync(string url, HttpClient client)
        {
            byte[] byteArray = await client.GetByteArrayAsync(url);
            DisplayResults(url, byteArray);
            return byteArray.Length;
        }

        private void DisplayResults(string url, byte[] content)
        {
            // Display the length of each web site. The string format
            // is designed to be used with a monospaced font, such as
            // Lucida Console or Global Monospace.
            var bytes = content.Length;
            // Strip off the "https://".
            var displayURL = url.Replace("https://", "");
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b9538-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9538-161">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b9538-162">Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)</span><span class="sxs-lookup"><span data-stu-id="b9538-162">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](./walkthrough-accessing-the-web-by-using-async-and-await.md)
