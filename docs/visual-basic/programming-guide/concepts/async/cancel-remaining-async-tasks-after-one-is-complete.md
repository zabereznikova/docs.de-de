---
title: "Verbleibende asynchrone Aufgaben abbrechen nach einer vollständigen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
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
ms.openlocfilehash: 1b70822edd972ac33614ab49faad6ff50b0e80b7
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a><span data-ttu-id="f0658-102">Abbrechen Sie verbleibende asynchrone Aufgaben nach einer vollständigen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0658-102">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>
<span data-ttu-id="f0658-103">Mithilfe der <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>-Methode zusammen mit einem <xref:System.Threading.CancellationToken>, können Sie alle verbleibenden Aufgaben abbrechen, wenn eine Aufgabe abgeschlossen ist.</xref:System.Threading.CancellationToken> </xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f0658-103">By using the <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> method together with a <xref:System.Threading.CancellationToken>, you can cancel all remaining tasks when one task is complete.</span></span> <span data-ttu-id="f0658-104">Die `WhenAny`-Methode akzeptiert ein Argument, das eine Auflistung von Aufgaben ist.</span><span class="sxs-lookup"><span data-stu-id="f0658-104">The `WhenAny` method takes an argument that’s a collection of tasks.</span></span> <span data-ttu-id="f0658-105">Die Methode startet alle Aufgaben und gibt eine einzelne Aufgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="f0658-105">The method starts all the tasks and returns a single task.</span></span> <span data-ttu-id="f0658-106">Die einzelne Aufgabe ist abgeschlossen, wenn eine beliebige Aufgabe in der Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f0658-106">The single task is complete when any task in the collection is complete.</span></span>  
  
 <span data-ttu-id="f0658-107">In diesem Beispiel wird veranschaulicht, wie ein Abbruchtoken in Verbindung mit `WhenAny` verwendet wird, um an der ersten Aufgabe festzuhalten, die in der Auflistung von Aufgaben beendet wird, und die übrigen Aufgaben abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="f0658-107">This example demonstrates how to use a cancellation token in conjunction with `WhenAny` to hold onto the first task to finish from the collection of tasks and to cancel the remaining tasks.</span></span> <span data-ttu-id="f0658-108">Jede Aufgabe lädt den Inhalt einer Website herunter.</span><span class="sxs-lookup"><span data-stu-id="f0658-108">Each task downloads the contents of a website.</span></span> <span data-ttu-id="f0658-109">Im Beispiel wird die Länge des Inhalts des ersten abgeschlossenen Downloads angezeigt und die anderen Downloads abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="f0658-109">The example displays the length of the contents of the first download to complete and cancels the other downloads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0658-110">Zum Ausführen der Beispiele müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f0658-110">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
## <a name="downloading-the-example"></a><span data-ttu-id="f0658-111">Herunterladen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="f0658-111">Downloading the Example</span></span>  
 <span data-ttu-id="f0658-112">Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="f0658-112">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="f0658-113">Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f0658-113">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f0658-114">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="f0658-114">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f0658-115">In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.</span><span class="sxs-lookup"><span data-stu-id="f0658-115">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningVB.</span></span>  
  
4.  <span data-ttu-id="f0658-116">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelAfterOneTask** Projekt, und wählen Sie dann **Set as StartUp Project**.</span><span class="sxs-lookup"><span data-stu-id="f0658-116">In **Solution Explorer**, open the shortcut menu for the **CancelAfterOneTask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="f0658-117">Drücken Sie die Taste F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0658-117">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="f0658-118">Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="f0658-118">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
6.  <span data-ttu-id="f0658-119">Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0658-119">Run the program several times to verify that different downloads finish first.</span></span>  
  
 <span data-ttu-id="f0658-120">Wenn Sie das Projekt herunterladen möchten, können Sie die Datei "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f0658-120">If you don't want to download the project, you can review the MainWindow.xaml.vb file at the end of this topic.</span></span>  
  
## <a name="building-the-example"></a><span data-ttu-id="f0658-121">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="f0658-121">Building the Example</span></span>  
 <span data-ttu-id="f0658-122">Im Beispiel in diesem Thema wird das Projekt, das in entwickelt wird hinzugefügt [eine asynchrone Aufgabe oder eine Liste von Tasks Abbrechen](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) , eine Liste von Aufgaben abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="f0658-122">The example in this topic adds to the project that's developed in [Cancel an Async Task or a List of Tasks](http://msdn.microsoft.com/library/d6e4e801-df64-4705-98fc-df725a577fb0) to cancel a list of tasks.</span></span> <span data-ttu-id="f0658-123">Im Beispiel wird die gleiche UI verwendet, obwohl die **Abbrechen** Schaltfläche nicht explizit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0658-123">The example uses the same UI, although the **Cancel** button isn’t used explicitly.</span></span>  
  
 <span data-ttu-id="f0658-124">So erstellen Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **CancelAListOfTasks** als die **Startprojekt**.</span><span class="sxs-lookup"><span data-stu-id="f0658-124">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelAListOfTasks** as the **StartUp Project**.</span></span> <span data-ttu-id="f0658-125">Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0658-125">Add the changes in this topic to that project.</span></span>  
  
 <span data-ttu-id="f0658-126">In der Datei "MainWindow.Xaml.vb", der die **CancelAListOfTasks** Projekt, starten Sie den Übergang durch Verschieben die Verarbeitungsschritte für jede Website, von der Schleife in `AccessTheWebAsync` zur folgenden asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="f0658-126">In the MainWindow.xaml.vb file of the **CancelAListOfTasks** project, start the transition by moving the processing steps for each website from the loop in `AccessTheWebAsync` to the following async method.</span></span>  
  
```vb  
' ***Bundle the processing steps for a website into one async method.  
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)  
  
    ' GetAsync returns a Task(Of HttpResponseMessage).   
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
    ' Retrieve the website contents from the HttpResponseMessage.  
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
    Return urlContents.Length  
End Function  
```  
  
 <span data-ttu-id="f0658-127">In `AccessTheWebAsync`, in diesem Beispiel wird eine Abfrage verwendet die <xref:System.Linq.Enumerable.ToArray%2A>-Methode, und die `WhenAny` Methode zum Erstellen und starten ein Array von Aufgaben.</xref:System.Linq.Enumerable.ToArray%2A></span><span class="sxs-lookup"><span data-stu-id="f0658-127">In `AccessTheWebAsync`, this example uses a query, the  <xref:System.Linq.Enumerable.ToArray%2A> method, and the `WhenAny` method to create and start an array of tasks.</span></span> <span data-ttu-id="f0658-128">Die Anwendung von `WhenAny` auf den Array gibt eine einzelne Aufgabe zurück, die, wenn sie erwartet wird, zur ersten Aufgabe auswertet wird, die im Array von Aufgaben zum Abschluss kommt.</span><span class="sxs-lookup"><span data-stu-id="f0658-128">The application of `WhenAny` to the array returns a single task that, when awaited, evaluates to the first task to reach completion in the array of tasks.</span></span>  
  
 <span data-ttu-id="f0658-129">Nehmen Sie in `AccessTheWebAsync` die folgenden Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="f0658-129">Make the following changes in `AccessTheWebAsync`.</span></span> <span data-ttu-id="f0658-130">Die Änderungen in der Codedatei sind mit Sternchen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0658-130">Asterisks mark the changes in the code file.</span></span>  
  
1.  <span data-ttu-id="f0658-131">Kommentieren Sie die Schleife aus oder löschen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="f0658-131">Comment out or delete the loop.</span></span>  
  
2.  <span data-ttu-id="f0658-132">Erstellen Sie eine Abfrage, die eine Auflistung generischer Aufgaben erstellt, wenn sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0658-132">Create a query that, when executed, produces a collection of generic tasks.</span></span> <span data-ttu-id="f0658-133">Jeder Aufruf von `ProcessURLAsync` gibt eine <xref:System.Threading.Tasks.Task%601>, in denen `TResult` ist eine ganze Zahl.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="f0658-133">Each call to `ProcessURLAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer.</span></span>  
  
<span data-ttu-id="f0658-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f0658-134"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
3.  <span data-ttu-id="f0658-135">Rufen Sie `ToArray` auf, um die Abfrage auszuführen und die Aufgaben zu starten.</span><span class="sxs-lookup"><span data-stu-id="f0658-135">Call `ToArray` to execute the query and start the tasks.</span></span> <span data-ttu-id="f0658-136">Die Anwendung der `WhenAny`-Methode im nächsten Schritt würde die Abfrage ohne `ToArray` ausführen und die Aufgaben starten, bei anderen Methoden ist dies möglicherweise nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="f0658-136">The application of the `WhenAny` method in the next step would execute the query and start the tasks without using `ToArray`, but other methods might not.</span></span> <span data-ttu-id="f0658-137">Die sicherste Methode besteht darin, die Ausführung der Abfrage explizit zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f0658-137">The safest practice is to force execution of the query explicitly.</span></span>  
  
<span data-ttu-id="f0658-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f0658-138"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
4.  <span data-ttu-id="f0658-139">Rufen Sie `WhenAny` mit der Auflistung von Aufgaben auf.</span><span class="sxs-lookup"><span data-stu-id="f0658-139">Call `WhenAny` on the collection of tasks.</span></span> <span data-ttu-id="f0658-140">`WhenAny` gibt `Task(Of Task(Of Integer))` oder `Task<Task<int>>` zurück.</span><span class="sxs-lookup"><span data-stu-id="f0658-140">`WhenAny` returns a `Task(Of Task(Of Integer))` or `Task<Task<int>>`.</span></span>  <span data-ttu-id="f0658-141">Das bedeutet, dass `WhenAny` eine Aufgabe zurückgibt, die zu einem einzelnen `Task(Of Integer)` oder `Task<int>` ausgewertet wird, wenn sie erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="f0658-141">That is, `WhenAny` returns a task that evaluates to a single `Task(Of Integer)` or `Task<int>` when it’s awaited.</span></span> <span data-ttu-id="f0658-142">Diese einzelne Aufgabe ist die erste Aufgabe in der Auflistung, die beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0658-142">That single task is the first task in the collection to finish.</span></span> <span data-ttu-id="f0658-143">Die Aufgabe, die als erste beendet wird, wird `firstFinishedTask` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f0658-143">The task that finished first is assigned to `firstFinishedTask`.</span></span> <span data-ttu-id="f0658-144">Der Typ des `firstFinishedTask` ist <xref:System.Threading.Tasks.Task%601>, `TResult` eine ganze Zahl ist, da dies der Rückgabetyp der `ProcessURLAsync`.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="f0658-144">The type of `firstFinishedTask` is <xref:System.Threading.Tasks.Task%601> where `TResult` is an integer because that's the return type of `ProcessURLAsync`.</span></span>  
  
```vb  
' ***Call WhenAny and then await the result. The task that finishes   
' first is assigned to firstFinishedTask.  
Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
```  
  
5.  <span data-ttu-id="f0658-145">In diesem Beispiel sind Sie nur an der Aufgabe interessiert, die zuerst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0658-145">In this example, you’re interested only in the task that finishes first.</span></span> <span data-ttu-id="f0658-146">Verwenden Sie daher <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>die verbleibenden Aufgaben abzubrechen.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f0658-146">Therefore, use <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> to cancel the remaining tasks.</span></span>  
  
```vb  
' ***Cancel the rest of the downloads. You just want the first one.  
cts.Cancel()  
```  
  
6.  <span data-ttu-id="f0658-147">Schließlich warten Sie ab, dass `firstFinishedTask` die Länge des heruntergeladenen Inhalts abruft.</span><span class="sxs-lookup"><span data-stu-id="f0658-147">Finally, await `firstFinishedTask` to retrieve the length of the downloaded content.</span></span>  
  
```vb  
Dim length = Await firstFinishedTask  
resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
```  
  
 <span data-ttu-id="f0658-148">Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0658-148">Run the program several times to verify that different downloads finish first.</span></span>  
  
## <a name="complete-example"></a><span data-ttu-id="f0658-149">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0658-149">Complete Example</span></span>  
 <span data-ttu-id="f0658-150">Der folgende Code besteht aus der vollständigen Datei "MainWindow.xaml.cs" oder "MainWindow.xaml.vb" für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f0658-150">The following code is the complete MainWindow.xaml.vb or MainWindow.xaml.cs file for the example.</span></span> <span data-ttu-id="f0658-151">Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f0658-151">Asterisks mark the elements that were added for this example.</span></span>  
  
 <span data-ttu-id="f0658-152">Beachten Sie, dass Sie eine Referenz für <xref:System.Net.Http>.</xref:System.Net.Http> hinzufügen müssen</span><span class="sxs-lookup"><span data-stu-id="f0658-152">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="f0658-153">Sie können das Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="f0658-153">You can download the project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
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
            resultsTextBox.Text &= vbCrLf & "Download complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
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
  
        '' Comment out or delete the loop.  
        ''For Each url In urlList  
        ''    ' GetAsync returns a Task(Of HttpResponseMessage).   
        ''    ' Argument ct carries the message if the Cancel button is chosen.   
        ''    ' Note that the Cancel button can cancel all remaining downloads.  
        ''    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ''    ' Retrieve the website contents from the HttpResponseMessage.  
        ''    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ''    resultsTextBox.Text &=  
        ''        String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        ''Next  
  
        ' ***Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' ***Use ToArray to execute the query and start the download tasks.   
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()  
  
        ' ***Call WhenAny and then await the result. The task that finishes   
        ' first is assigned to firstFinishedTask.  
        Dim firstFinishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
        ' ***Cancel the rest of the downloads. You just want the first one.  
        cts.Cancel()  
  
        ' ***Await the first completed task and display the results  
        ' Run the program several times to demonstrate that different  
        ' websites can finish first.  
        Dim length = Await firstFinishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
    End Function  
  
    ' ***Bundle the processing steps for a website into one async method.  
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
  
' Length of the downloaded website:  158856  
  
' Download complete.  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0658-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0658-154">See Also</span></span>  
 <span data-ttu-id="f0658-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></xref:System.Threading.Tasks.Task.WhenAny%2A></span><span class="sxs-lookup"><span data-stu-id="f0658-155"><xref:System.Threading.Tasks.Task.WhenAny%2A></span></span>   
<span data-ttu-id="f0658-156"> [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="f0658-156"> [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
<span data-ttu-id="f0658-157"> [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0658-157"> [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="f0658-158"> [ASYNC-Beispiel: Feinabstimmung der Anwendung](http://go.microsoft.com/fwlink/?LinkId=255046)</span><span class="sxs-lookup"><span data-stu-id="f0658-158"> [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046)</span></span>
