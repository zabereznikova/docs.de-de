---
title: Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)
description: Verwenden Sie die Task.WhenAny-Methode in diesem Beispiel zusammen mit einem CancellationToken in C#, um alle verbleibenden Aufgaben abzubrechen, sobald eine Aufgabe abgeschlossen wurde.
ms.date: 07/20/2015
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
ms.openlocfilehash: 6de60c8faa93752961e3703a042885a71972cc4a
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925279"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a><span data-ttu-id="46277-103">Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)</span><span class="sxs-lookup"><span data-stu-id="46277-103">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>
<span data-ttu-id="46277-104">Mit der <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methode zusammen mit einem <xref:System.Threading.CancellationToken> können Sie alle verbleibenden Aufgaben abbrechen, wenn eine Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="46277-104">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="46277-105">Die `WhenAny`-Methode akzeptiert ein Argument, das eine Auflistung von Aufgaben ist.</span><span class="sxs-lookup"><span data-stu-id="46277-105">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="46277-106">Die Methode startet alle Aufgaben und gibt eine einzelne Aufgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="46277-106">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="46277-107">Die einzelne Aufgabe ist abgeschlossen, wenn eine beliebige Aufgabe in der Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="46277-107">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="46277-108">In diesem Beispiel wird veranschaulicht, wie ein Abbruchtoken in Verbindung mit `WhenAny` verwendet wird, um an der ersten Aufgabe festzuhalten, die in der Auflistung von Aufgaben beendet wird, und die übrigen Aufgaben abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="46277-108">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="46277-109">Jede Aufgabe lädt den Inhalt einer Website herunter.</span><span class="sxs-lookup"><span data-stu-id="46277-109">Each task downloads the contents of a website.</span></span> <span data-ttu-id="46277-110">Im Beispiel wird die Länge des Inhalts des ersten abgeschlossenen Downloads angezeigt und die anderen Downloads abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="46277-110">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46277-111">Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="46277-111">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="46277-112">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="46277-112">Downloading the Example</span></span>  
 <span data-ttu-id="46277-113">Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="46277-113">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) and then follow these steps.</span></span>  
  
1. <span data-ttu-id="46277-114">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="46277-114">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2. <span data-ttu-id="46277-115">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="46277-115">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3. <span data-ttu-id="46277-116">Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningCS.</span><span class="sxs-lookup"><span data-stu-id="46277-116">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4. <span data-ttu-id="46277-117">Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterOneTask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="46277-117">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5. <span data-ttu-id="46277-118">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="46277-118">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="46277-119">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="46277-119">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6. <span data-ttu-id="46277-120">Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="46277-120">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="46277-121">Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Dateien „MainWindow.xaml.vb“ und „MainWindow.xaml.cs“ am Ende dieses Themas anschauen.</span><span class="sxs-lookup"><span data-stu-id="46277-121">If you don't want to download the project, you can review the MainWindow.xaml.cs file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="46277-122">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="46277-122">Building the Example</span></span>  
 <span data-ttu-id="46277-123">Das Beispiel in diesem Thema baut auf dem Projekt auf, das unter [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) entwickelt wurde, um eine Aufgabenliste abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="46277-123">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks (C#)](./cancel-an-async-task-or-a-list-of-tasks.md) to cancel a list of tasks.</span></span> <span data-ttu-id="46277-124">Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46277-124">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="46277-125">Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus.</span><span class="sxs-lookup"><span data-stu-id="46277-125">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="46277-126">Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.</span><span class="sxs-lookup"><span data-stu-id="46277-126">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="46277-127">Starten Sie in der Datei „MainWindow.xaml.cs“ des **CancelAListOfTasks**-Projekts den Übergang, indem Sie die Verarbeitungsschritte für jede Website von der Schleife in `AccessTheWebAsync` zur folgenden asynchronen Methode verschieben.</span><span class="sxs-lookup"><span data-stu-id="46277-127">In the MainWindow.xaml.cs file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```csharp  
// ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 <span data-ttu-id="46277-128">In `AccessTheWebAsync` wird in diesem Beispiel eine Abfrage, die <xref:System.Linq.Enumerable.ToArray%2A>-Methode und die `WhenAny`-Methode verwendet, um ein Array von Aufgaben zu erstellen und zu starten.</span><span class="sxs-lookup"><span data-stu-id="46277-128">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="46277-129">Die Anwendung von `WhenAny` auf den Array gibt eine einzelne Aufgabe zurück, die, wenn sie erwartet wird, zur ersten Aufgabe auswertet wird, die im Array von Aufgaben zum Abschluss kommt.</span><span class="sxs-lookup"><span data-stu-id="46277-129">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="46277-130">Nehmen Sie in `AccessTheWebAsync` die folgenden Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="46277-130">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="46277-131">Die Änderungen in der Codedatei sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="46277-131">Asterisks mark the changes in the code file.</span></span>  
  
1. <span data-ttu-id="46277-132">Kommentieren Sie die Schleife aus oder löschen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="46277-132">Comment out or delete the loop.</span></span>  
  
2. <span data-ttu-id="46277-133">Erstellen Sie eine Abfrage, die eine Auflistung generischer Aufgaben erstellt, wenn sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46277-133">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="46277-134">Jeder Aufruf von `ProcessURLAsync` gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="46277-134">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
    ```csharp  
    // ***Create a query that, when executed, returns a collection of tasks.  
    IEnumerable<Task<int>> downloadTasksQuery =  
        from url in urlList select ProcessURLAsync(url, client, ct);  
    ```  
  
3. <span data-ttu-id="46277-135">Rufen Sie `ToArray` auf, um die Abfrage auszuführen und die Aufgaben zu starten.</span><span class="sxs-lookup"><span data-stu-id="46277-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="46277-136">Die Anwendung der `WhenAny`-Methode im nächsten Schritt würde die Abfrage ohne `ToArray` ausführen und die Aufgaben starten, bei anderen Methoden ist dies möglicherweise nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="46277-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="46277-137">Die sicherste Methode besteht darin, die Ausführung der Abfrage explizit zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="46277-137">The safest practice is to force execution of the query explicitly.</span></span>  
  
    ```csharp  
    // ***Use ToArray to execute the query and start the download tasks.
    Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
    ```  
  
4. <span data-ttu-id="46277-138">Rufen Sie `WhenAny` mit der Auflistung von Aufgaben auf.</span><span class="sxs-lookup"><span data-stu-id="46277-138">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="46277-139">`WhenAny` gibt `Task(Of Task(Of Integer))` oder `Task<Task<int>>` zurück.</span><span class="sxs-lookup"><span data-stu-id="46277-139">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="46277-140">Das bedeutet, dass `WhenAny` eine Aufgabe zurückgibt, die zu einem einzelnen `Task(Of Integer)` oder `Task<int>` ausgewertet wird, wenn sie erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="46277-140">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="46277-141">Diese einzelne Aufgabe ist die erste Aufgabe in der Auflistung, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="46277-141">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="46277-142">Die Aufgabe, die als erste beendet wird, wird `firstFinishedTask` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="46277-142">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="46277-143">Der Typ von `firstFinishedTask` ist <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist, da dies der Rückgabetyp von `ProcessURLAsync` ist.</span><span class="sxs-lookup"><span data-stu-id="46277-143">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
    ```csharp  
    // ***Call WhenAny and then await the result. The task that finishes
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5. <span data-ttu-id="46277-144">In diesem Beispiel sind Sie nur an der Aufgabe interessiert, die zuerst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="46277-144">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="46277-145">Verwenden Sie daher <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, um die verbleibenden Aufgaben abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="46277-145">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> to cancel the remaining tasks.</span></span>  
  
    ```csharp  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6. <span data-ttu-id="46277-146">Schließlich warten Sie ab, dass `firstFinishedTask` die Länge des heruntergeladenen Inhalts abruft.</span><span class="sxs-lookup"><span data-stu-id="46277-146">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
    ```csharp  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
    ```  
  
 <span data-ttu-id="46277-147">Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="46277-147">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="46277-148">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="46277-148">Complete Example</span></span>  
 <span data-ttu-id="46277-149">Der folgende Code besteht aus der vollständigen Datei „MainWindow.xaml.cs“ für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="46277-149">The following code is the complete MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="46277-150">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="46277-150">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="46277-151">Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.</span><span class="sxs-lookup"><span data-stu-id="46277-151">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="46277-152">Sie können das Projekt hier herunterladen: [Async Sample: Fine Tuning Your Application (Async-Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span><span class="sxs-lookup"><span data-stu-id="46277-152">You can download the project from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
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
  
namespace CancelAfterOneTask  
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
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.
            //    // Argument ct carries the message if the Cancel button is chosen.
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        $"\r\nLength of the downloaded string: {urlContents.Length}.\r\n";
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += $"\r\nLength of the downloaded website:  {length}\r\n";
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",  
                "https://msdn.microsoft.com/library/hh290138.aspx",  
                "https://msdn.microsoft.com/library/hh290140.aspx",  
                "https://msdn.microsoft.com/library/dd470362.aspx",  
                "https://msdn.microsoft.com/library/aa578028.aspx",  
                "https://msdn.microsoft.com/library/ms404677.aspx",  
                "https://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="46277-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46277-153">See also</span></span>

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [<span data-ttu-id="46277-154">Feinabstimmung der Async-Anwendung (C#)</span><span class="sxs-lookup"><span data-stu-id="46277-154">Fine-Tuning Your Async Application (C#)</span></span>](./fine-tuning-your-async-application.md)
- [<span data-ttu-id="46277-155">Asynchrone Programmierung mit „async“ und „await“ (C#)</span><span class="sxs-lookup"><span data-stu-id="46277-155">Asynchronous Programming with async and await (C#)</span></span>](./index.md)
- <span data-ttu-id="46277-156">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)</span><span class="sxs-lookup"><span data-stu-id="46277-156">[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)</span></span>
