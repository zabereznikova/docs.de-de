---
title: "Mehrere asynchrone Aufgaben starten und Abschließen von (Visual Basic) verarbeiten | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fbf4611ecd64abfd016963dff887d82aad333b7
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a><span data-ttu-id="661ae-102">Mehrere asynchrone Aufgaben starten und Abschließen von (Visual Basic) verarbeiten</span><span class="sxs-lookup"><span data-stu-id="661ae-102">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>
<span data-ttu-id="661ae-103">Mithilfe von <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, können Sie mehrere Aufgaben gleichzeitig starten und diese einzeln zu verarbeiten, sobald sie abgeschlossen sind nicht in der Reihenfolge, in der sie gestartet, zu verarbeiten.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="661ae-103">By using <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>, you can start multiple tasks at the same time and process them one by one as they’re completed rather than process them in the order in which they're started.</span></span>  
  
 <span data-ttu-id="661ae-104">Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="661ae-104">The following example uses a query to create a collection of tasks.</span></span> <span data-ttu-id="661ae-105">Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter.</span><span class="sxs-lookup"><span data-stu-id="661ae-105">Each task downloads the contents of a specified website.</span></span> <span data-ttu-id="661ae-106">In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet.</span><span class="sxs-lookup"><span data-stu-id="661ae-106">In each iteration of a while loop, an awaited call to `WhenAny` returns the task in the collection of tasks that finishes its download first.</span></span> <span data-ttu-id="661ae-107">Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="661ae-107">That task is removed from the collection and processed.</span></span> <span data-ttu-id="661ae-108">Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.</span><span class="sxs-lookup"><span data-stu-id="661ae-108">The loop repeats until the collection contains no more tasks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="661ae-109">Zum Ausführen der Beispiele müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="661ae-109">To run the examples, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="661ae-110">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="661ae-110">Downloading the Example</span></span>  
 <span data-ttu-id="661ae-111">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="661ae-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="661ae-112">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="661ae-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="661ae-113">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="661ae-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="661ae-114">In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="661ae-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="661ae-115">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **ProcessTasksAsTheyFinish** Projekt, und wählen Sie dann **Set as StartUp Project**.</span><span class="sxs-lookup"><span data-stu-id="661ae-115">In **Solution Explorer**, open the shortcut menu for the **ProcessTasksAsTheyFinish** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="661ae-116">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="661ae-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="661ae-117">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="661ae-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="661ae-118">Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="661ae-118">Run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
 <span data-ttu-id="661ae-119">Wenn Sie das Projekt herunterladen möchten, können Sie die Datei "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="661ae-119">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="661ae-120">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="661ae-120">Building the Example</span></span>  
 <span data-ttu-id="661ae-121">Diesem Beispiel wird der Code, der in Entwicklung [Abbrechen verbleibende asynchrone Aufgaben nach einem abgeschlossen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) und verwendet die gleiche UI.</span><span class="sxs-lookup"><span data-stu-id="661ae-121">This example adds to the code that’s developed in [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and uses the same UI.</span></span>  
  
 <span data-ttu-id="661ae-122">So erstellen Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **CancelAfterOneTask** als die **Startprojekt**.</span><span class="sxs-lookup"><span data-stu-id="661ae-122">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAfterOneTask** as the **StartUp Project**.</span></span> <span data-ttu-id="661ae-123">Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="661ae-123">Add the changes in this topic to the `AccessTheWebAsync` method in that project.</span></span> <span data-ttu-id="661ae-124">Die Änderungen sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="661ae-124">The changes are marked with asterisks.</span></span>  
  
 <span data-ttu-id="661ae-125">Die **CancelAfterOneTask** Projekt enthält bereits eine Abfrage, die bei der Ausführung erstellt eine Auflistung von Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="661ae-125">The **CancelAfterOneTask** project already includes a query that, when executed, creates a collection of tasks.</span></span> <span data-ttu-id="661ae-126">Jeder Aufruf von `ProcessURLAsync` in den folgenden Code gibt eine <xref:System.Threading.Tasks.Task%601>, in denen `TResult` ist eine ganze Zahl.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="661ae-126">Each call to `ProcessURLAsync` in the following code returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="661ae-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="661ae-127"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="661ae-128">Stellen Sie in der Datei "MainWindow.Xaml.vb" des Projekts die folgenden Änderungen an der `AccessTheWebAsync` Methode.</span><span class="sxs-lookup"><span data-stu-id="661ae-128">In the MainWindow.xaml.vb file of the  project, make the following changes to the `AccessTheWebAsync` method.</span></span>  
  
-   <span data-ttu-id="661ae-129">Führen Sie die Abfrage durch Anwenden <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>statt <xref:System.Linq.Enumerable.ToArray%2A>.</xref:System.Linq.Enumerable.ToArray%2A> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="661ae-129">Execute the query by applying <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> instead of <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
<span data-ttu-id="661ae-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="661ae-130"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
-   <span data-ttu-id="661ae-131">Fügen Sie eine While-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt.</span><span class="sxs-lookup"><span data-stu-id="661ae-131">Add a while loop that performs the following steps for each task in the collection.</span></span>  
  
    1.  <span data-ttu-id="661ae-132">Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.</span><span class="sxs-lookup"><span data-stu-id="661ae-132">Awaits a call to `WhenAny` to identify the first task in the collection to finish its download.</span></span>  
  
<span data-ttu-id="661ae-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="661ae-133"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
    2.  <span data-ttu-id="661ae-134">Entfernt die entsprechende Aufgabe aus der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="661ae-134">Removes that task from the collection.</span></span>  
  
<span data-ttu-id="661ae-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="661ae-135"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
    3.  <span data-ttu-id="661ae-136">Erwartet `firstFinishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="661ae-136">Awaits `firstFinishedTask`, which is returned by a call to `ProcessURLAsync`.</span></span> <span data-ttu-id="661ae-137">Die `firstFinishedTask` Variable ist ein <xref:System.Threading.Tasks.Task%601>, in denen `TReturn` ist eine ganze Zahl.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="661ae-137">The `firstFinishedTask` variable is a <xref:System.Threading.Tasks.Task%601> where `TReturn` is an integer.</span></span> <span data-ttu-id="661ae-138">Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="661ae-138">The task is already complete, but you await it to retrieve the length of the downloaded website, as the following example shows.</span></span>  
  
        ```vb  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 <span data-ttu-id="661ae-139">Sie sollten das Projekt mehrmals ausführen, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="661ae-139">You should run the project several times to verify that the downloaded lengths don't always appear in the same order.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="661ae-140">Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen.</span><span class="sxs-lookup"><span data-stu-id="661ae-140">You can use `WhenAny` in a loop, as described in the example, to solve problems that involve a small number of tasks.</span></span> <span data-ttu-id="661ae-141">Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="661ae-141">However, other approaches are more efficient if you have a large number of tasks to process.</span></span> <span data-ttu-id="661ae-142">Weitere Informationen und Beispiele finden Sie unter [Verarbeitung von Aufgaben nach deren Abschluss](http://go.microsoft.com/fwlink/?LinkId=260810).</span><span class="sxs-lookup"><span data-stu-id="661ae-142">For more information and examples, see [Processing Tasks as they complete](http://go.microsoft.com/fwlink/?LinkId=260810).</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="661ae-143">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="661ae-143">Complete Example</span></span>  
 <span data-ttu-id="661ae-144">Im folgende Code wird der vollständige Text der Datei "MainWindow.Xaml.vb" für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="661ae-144">The following code is the complete text of the MainWindow.xaml.vb file for the example.</span></span> <span data-ttu-id="661ae-145">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="661ae-145">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="661ae-146">Beachten Sie, dass Sie eine Referenz für <xref:System.Net.Http>.</xref:System.Net.Http> hinzufügen müssen</span><span class="sxs-lookup"><span data-stu-id="661ae-146">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="661ae-147">Sie können das Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="661ae-147">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            Await AccessTheWebAsync(cts.Token)  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' You can still include a Cancel button if you want to.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToList to execute the query and start the download tasks.   
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' ***Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' ***Identify the first task that completes.  
            Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' ***Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(firstFinishedTask)  
  
            ' ***Await the first completed task and display the results.  
            Dim length = Await firstFinishedTask  
            resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        End While  
  
    End Function  
  
    ' Bundle the processing steps for a website into one async method.  
    Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        Return urlContents.Length  
    End Function  
  
    ' Add a method that creates a list of web addresses.  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
End Class  
  
' Sample output:  
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="661ae-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="661ae-148">See Also</span></span>  
 <span data-ttu-id="661ae-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="661ae-149"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="661ae-150"> [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="661ae-150"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="661ae-151"> [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="661ae-151"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="661ae-152"> [ASYNC-Beispiel: Feinabstimmung der Anwendung](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="661ae-152"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
