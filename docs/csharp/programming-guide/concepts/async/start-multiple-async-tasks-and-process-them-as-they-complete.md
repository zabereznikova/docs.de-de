---
title: Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)
ms.date: 07/20/2015
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 29dc629abae13bb7ba3a9b0cb87300e6d1cbe2d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a><span data-ttu-id="875ab-102">Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)</span><span class="sxs-lookup"><span data-stu-id="875ab-102">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>
<span data-ttu-id="875ab-103">Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="875ab-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="875ab-104">Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="875ab-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="875ab-105">Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter.</span><span class="sxs-lookup"><span data-stu-id="875ab-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="875ab-106">In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet.</span><span class="sxs-lookup"><span data-stu-id="875ab-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="875ab-107">Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="875ab-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="875ab-108">Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.</span><span class="sxs-lookup"><span data-stu-id="875ab-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="875ab-109">Zum Ausführen des Beispiels muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="875ab-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="875ab-110">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="875ab-110">Downloading the Example</span></span>  
 <span data-ttu-id="875ab-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="875ab-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="875ab-112">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="875ab-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="875ab-113">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="875ab-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="875ab-114">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="875ab-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="875ab-115">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt **ProcessTasksAsTheyFinish** und wählen dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="875ab-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="875ab-116">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="875ab-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="875ab-117">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="875ab-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="875ab-118">Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="875ab-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="875ab-119">Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Datei „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.</span><span class="sxs-lookup"><span data-stu-id="875ab-119">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="875ab-120">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="875ab-120">Building the Example</span></span>  
 <span data-ttu-id="875ab-121">In diesem Beispiel wird ein Code hinzugefügt, der in [Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) entwickelt wurde und die gleiche Benutzeroberfläche verwendet.</span><span class="sxs-lookup"><span data-stu-id="875ab-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)[Cancel Remaining Async Tasks after One Is Complete](http://msdn.microsoft.com/library/8e800b58-235a-44b7-a02c-fa4375591d76) and uses the same UI.</span></span>  
  
 <span data-ttu-id="875ab-122">Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAfterOneTask** aus.</span><span class="sxs-lookup"><span data-stu-id="875ab-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="875ab-123">Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="875ab-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="875ab-124">Die Änderungen sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="875ab-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="875ab-125">Das Projekt **CancelAfterOneTask** enthält bereits eine Abfrage, die eine Auflistung von Aufgaben erstellt, während sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="875ab-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="875ab-126">Jeder Aufruf von `ProcessURLAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="875ab-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
```csharp  
IEnumerable<Task<int>> downloadTasksQuery =  
    from url in urlList select ProcessURL(url, client, ct);  
```  
  
 <span data-ttu-id="875ab-127">Nehmen Sie in der Datei „MainWindow.xaml.cs“ des Projekts die folgenden Änderungen an der `AccessTheWebAsync`-Methode vor.</span><span class="sxs-lookup"><span data-stu-id="875ab-127">In the MainWindow.xaml.cs file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="875ab-128">Führen Sie die Abfrage aus, indem Sie <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anstelle von <xref:System.Linq.Enumerable.ToArray%2A> anwenden.</span><span class="sxs-lookup"><span data-stu-id="875ab-128">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
    ```csharp  
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();  
    ```  
  
-   <span data-ttu-id="875ab-129">Fügen Sie eine While-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt.</span><span class="sxs-lookup"><span data-stu-id="875ab-129">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="875ab-130">Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.</span><span class="sxs-lookup"><span data-stu-id="875ab-130">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
        ```csharp  
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
        ```  
  
    2.  <span data-ttu-id="875ab-131">Entfernt die entsprechende Aufgabe aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="875ab-131">Removes that task from the collection.</span></span>  
  
        ```csharp  
        downloadTasks.Remove(firstFinishedTask);  
        ```  
  
    3.  <span data-ttu-id="875ab-132">Erwartet `firstFinishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="875ab-132">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="875ab-133">Die Variable `firstFinishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TReturn` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="875ab-133">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="875ab-134">Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="875ab-134">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```csharp  
        int length = await firstFinishedTask;  
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
        ```  
  
 <span data-ttu-id="875ab-135">Sie sollten das Projekt mehrmals ausführen, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="875ab-135">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="875ab-136">Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen.</span><span class="sxs-lookup"><span data-stu-id="875ab-136">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="875ab-137">Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="875ab-137">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="875ab-138">Weitere Informationen und Beispiele finden Sie unter [Processing Tasks as they complete (Verarbeitung von Aufgaben nach deren Abschluss)](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/).</span><span class="sxs-lookup"><span data-stu-id="875ab-138">For more information and examples, see [Processing tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="875ab-139">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="875ab-139">Complete Example</span></span>  
 <span data-ttu-id="875ab-140">Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.cs“ für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="875ab-140">The following code is the complete text of the MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="875ab-141">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="875ab-141">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="875ab-142">Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="875ab-142">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="875ab-143">Sie können das Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="875ab-143">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);  
            }  
        }  
  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
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
  
## <a name="see-also"></a><span data-ttu-id="875ab-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="875ab-144">See Also</span></span>  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>  
 [<span data-ttu-id="875ab-145">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="875ab-145">Fine-Tuning Your Async Application (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)  
 [<span data-ttu-id="875ab-146">Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))</span><span class="sxs-lookup"><span data-stu-id="875ab-146">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="875ab-147">Async Sample: Fine Tuning Your Application (Async-Beispiel: Feinabstimmung der Anwendung)</span><span class="sxs-lookup"><span data-stu-id="875ab-147">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)
