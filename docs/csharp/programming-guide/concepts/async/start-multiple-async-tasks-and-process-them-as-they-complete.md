---
title: Verarbeiten asynchroner Aufgaben nach Abschluss
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: b618fd6bf80551231d2b285fd0e8aef688d00d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "71736731"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="5c137-102">Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)</span><span class="sxs-lookup"><span data-stu-id="5c137-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>

<span data-ttu-id="5c137-103">Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5c137-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>

<span data-ttu-id="5c137-104">Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c137-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="5c137-105">Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter.</span><span class="sxs-lookup"><span data-stu-id="5c137-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="5c137-106">In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet.</span><span class="sxs-lookup"><span data-stu-id="5c137-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="5c137-107">Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5c137-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="5c137-108">Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.</span><span class="sxs-lookup"><span data-stu-id="5c137-108">The loop repeats until the collection contains no more tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="5c137-109">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="5c137-109">To run the examples, you must have Visual Studio (2012 or newer) and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="download-an-example-solution"></a><span data-ttu-id="5c137-110">Herunterladen einer Beispielprojektmappe</span><span class="sxs-lookup"><span data-stu-id="5c137-110">Download an example solution</span></span>

<span data-ttu-id="5c137-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="5c137-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>

> [!TIP]
> <span data-ttu-id="5c137-112">Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich stattdessen die Datei *MainWindow.xaml.cs* am Ende dieses Themas ansehen.</span><span class="sxs-lookup"><span data-stu-id="5c137-112">If you don't want to download the project, you can review the *MainWindow.xaml.cs* file at the end of this topic instead.</span></span>

1. <span data-ttu-id="5c137-113">Extrahieren Sie die heruntergeladenen Dateien aus der *ZIP*-Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5c137-113">Extract the files that you downloaded from the *.zip* file, and then start Visual Studio.</span></span>

2. <span data-ttu-id="5c137-114">Wählen Sie auf der Menüleiste **Datei** > **Öffnen** > **Projekt/Projektmappe** aus.</span><span class="sxs-lookup"><span data-stu-id="5c137-114">On the menu bar, choose **File** > **Open** > **Project/Solution**.</span></span>

3. <span data-ttu-id="5c137-115">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen heruntergeladenen Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (*SLN*) für *AsyncFineTuningCS*/*AsyncFineTuningVB*.</span><span class="sxs-lookup"><span data-stu-id="5c137-115">In the **Open Project** dialog box, open the folder that holds the sample code you downloaded, and then open the solution (*.sln*) file for *AsyncFineTuningCS*/*AsyncFineTuningVB*.</span></span>

4. <span data-ttu-id="5c137-116">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt **ProcessTasksAsTheyFinish** und wählen dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="5c137-116">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>

5. <span data-ttu-id="5c137-117">Drücken Sie die Taste <kbd>F5</kbd>, um das Programm mit Debuggen auszuführen, oder drücken Sie die Tasten <kbd>STRG</kbd>+<kbd>F5</kbd>, um das Programm ohne Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5c137-117">Choose the <kbd>F5</kbd> key to run the program with debugging or, press <kbd>Ctrl</kbd>+<kbd>F5</kbd> keys to run the program without debugging it.</span></span>

6. <span data-ttu-id="5c137-118">Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5c137-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

## <a name="create-the-program-yourself"></a><span data-ttu-id="5c137-119">Das Programm selbst erstellen</span><span class="sxs-lookup"><span data-stu-id="5c137-119">Create the program yourself</span></span>

<span data-ttu-id="5c137-120">Dieses Beispiel stellt eine Ergänzung des Codes dar, der in [Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)](cancel-remaining-async-tasks-after-one-is-complete.md) entwickelt wird, und verwendet die gleiche Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="5c137-120">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](cancel-remaining-async-tasks-after-one-is-complete.md), and it uses the same UI.</span></span>

<span data-ttu-id="5c137-121">Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt [Herunterladen des Beispiels](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), wählen Sie als Startprojekt aber **CancelAfterOneTask** aus.</span><span class="sxs-lookup"><span data-stu-id="5c137-121">To build the example yourself, step by step, follow the instructions in the [Downloading the Example](cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example) section, but set **CancelAfterOneTask** as the startup project.</span></span> <span data-ttu-id="5c137-122">Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="5c137-122">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="5c137-123">Die Änderungen sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="5c137-123">The changes are marked with asterisks.</span></span>

<span data-ttu-id="5c137-124">Das Projekt **CancelAfterOneTask** enthält bereits eine Abfrage, die eine Auflistung von Aufgaben erstellt, während sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c137-124">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="5c137-125">Jeder Aufruf von `ProcessURLAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist:</span><span class="sxs-lookup"><span data-stu-id="5c137-125">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer:</span></span>

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

<span data-ttu-id="5c137-126">Nehmen Sie in der Datei *MainWindow.xaml.cs* des Projekts die folgenden Änderungen an der `AccessTheWebAsync`-Methode vor:</span><span class="sxs-lookup"><span data-stu-id="5c137-126">In the *MainWindow.xaml.cs* file of the project, make the following changes to the `AccessTheWebAsync` method:</span></span>

- <span data-ttu-id="5c137-127">Führen Sie die Abfrage aus, indem Sie <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anstelle von <xref:System.Linq.Enumerable.ToArray%2A> anwenden.</span><span class="sxs-lookup"><span data-stu-id="5c137-127">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

- <span data-ttu-id="5c137-128">Fügen Sie eine `while`-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt:</span><span class="sxs-lookup"><span data-stu-id="5c137-128">Add a `while` loop that performs the following steps for each task in the collection:</span></span>

    1. <span data-ttu-id="5c137-129">Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.</span><span class="sxs-lookup"><span data-stu-id="5c137-129">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2. <span data-ttu-id="5c137-130">Entfernt die entsprechende Aufgabe aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="5c137-130">Removes that task from the collection.</span></span>

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3. <span data-ttu-id="5c137-131">Erwartet `firstFinishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c137-131">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="5c137-132">Die Variable `firstFinishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TReturn` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="5c137-132">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="5c137-133">Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5c137-133">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span> <span data-ttu-id="5c137-134">Wenn für die Aufgabe ein Fehler auftritt, löst `await` die erste untergeordnete Ausnahme aus, die in der `AggregateException` gespeichert ist, im Gegensatz zum Lesen der `Result`-Eigenschaft, die die `AggregateException` auslösen würde.</span><span class="sxs-lookup"><span data-stu-id="5c137-134">If the task is faulted, `await` will throw the first child exception stored in the `AggregateException`, unlike reading the `Result` property which would throw the `AggregateException`.</span></span>

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += $"\r\nLength of the download:  {length}";
        ```

<span data-ttu-id="5c137-135">Führen Sie das Programm mehrmals aus, um zu bestätigen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5c137-135">Run the program several times to verify that the downloaded lengths don't always appear in the same order.</span></span>

> [!CAUTION]
> <span data-ttu-id="5c137-136">Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen.</span><span class="sxs-lookup"><span data-stu-id="5c137-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="5c137-137">Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5c137-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="5c137-138">Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span><span class="sxs-lookup"><span data-stu-id="5c137-138">For more information and examples, see [Processing tasks as they complete](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/).</span></span>

## <a name="complete-example"></a><span data-ttu-id="5c137-139">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c137-139">Complete example</span></span>

<span data-ttu-id="5c137-140">Der folgende Code besteht aus dem vollständigen Text der Datei *MainWindow.xaml.cs* für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5c137-140">The following code is the complete text of the *MainWindow.xaml.cs* file for the example.</span></span> <span data-ttu-id="5c137-141">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="5c137-141">Asterisks mark the elements that were added for this example.</span></span> <span data-ttu-id="5c137-142">Beachten Sie ferner, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="5c137-142">Also, take note that you must add a reference for <xref:System.Net.Http>.</span></span>

<span data-ttu-id="5c137-143">Sie können das Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5c137-143">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
{
    public partial class MainWindow : Window
    {
        // Declare a System.Threading.CancellationTokenSource.
        CancellationTokenSource cts;

        public MainWindow()
        {
            InitializeComponent();
        }

        private async void startButton_Click(object sender, RoutedEventArgs e)
        {
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += $"\r\nLength of the download:  {length}";
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a><span data-ttu-id="5c137-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c137-144">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="5c137-145">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="5c137-145">Fine-Tuning Your Async Application (C#)</span></span>](fine-tuning-your-async-application.md)
- [<span data-ttu-id="5c137-146">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="5c137-146">Asynchronous Programming with async and await (C#)</span></span>](index.md)
- [<span data-ttu-id="5c137-147">Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)</span><span class="sxs-lookup"><span data-stu-id="5c137-147">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
