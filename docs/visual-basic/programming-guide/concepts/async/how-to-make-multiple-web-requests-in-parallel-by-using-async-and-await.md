---
title: 'Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await'
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 40bab392af94ba941c2562e885a8d2e08aeea5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396583"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="24c9f-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic) (Gewusst wie: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="24c9f-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>

<span data-ttu-id="24c9f-103">In einer asynchronen Methode werden Aufgaben gestartet, wenn sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="24c9f-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="24c9f-104">Der [Erwartungs Operator wird](../../../language-reference/operators/await-operator.md) auf die Aufgabe an dem Punkt in der Methode angewendet, an dem die Verarbeitung nicht fortgesetzt werden kann, bis die Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="24c9f-104">The [Await](../../../language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="24c9f-105">Häufig wird eine Aufgabe erwartet, sobald sie erstellt wird, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="24c9f-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>

```vb
Dim result = Await someWebAccessMethodAsync(url)
```

<span data-ttu-id="24c9f-106">Sie können das Erstellen der Aufgabe vom Erwarten der Aufgabe jedoch trennen, wenn das Programm weitere Arbeit durchführen muss, die nicht vom Abschluss der Aufgabe abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="24c9f-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>

```vb
' The following line creates and starts the task.
Dim myTask = someWebAccessMethodAsync(url)

' While the task is running, you can do other work that does not depend
' on the results of the task.
' . . . . .

' The application of Await suspends the rest of this method until the task is
' complete.
Dim result = Await myTask
```

<span data-ttu-id="24c9f-107">Zwischen dem Starten und dem Erwarten einer Aufgabe können Sie andere Aufgaben starten.</span><span class="sxs-lookup"><span data-stu-id="24c9f-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="24c9f-108">Die weiteren Aufgaben werden implizit parallel ausgeführt, es werden jedoch keine weiteren Threads erstellt.</span><span class="sxs-lookup"><span data-stu-id="24c9f-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>

<span data-ttu-id="24c9f-109">Das folgende Programm startet drei asynchrone Webdownloads und erwartet diese dann in der Reihenfolge, in der sie aufgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="24c9f-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="24c9f-110">Beachten Sie, dass die Aufgaben beim Ausführen des Programms nicht immer in der Reihenfolge abgeschlossen werden, in der sie erstellt und erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="24c9f-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="24c9f-111">Sie beginnen mit der Ausführung, wenn sie erstellt werden, und eine oder mehrere Aufgaben werden u. U. abgeschlossen, bevor die Methode die await-Ausdrucke erreicht.</span><span class="sxs-lookup"><span data-stu-id="24c9f-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="24c9f-112">Zum Fertigstellen dieses Projekts muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="24c9f-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>

<span data-ttu-id="24c9f-113">Ein weiteres Beispiel, in dem mehrere Aufgaben gleichzeitig gestartet werden, finden Sie unter Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise [mithilfe von "Task. alle" (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="24c9f-113">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>

<span data-ttu-id="24c9f-114">Sie können den Code für dieses Beispiel auf der Seite für [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="24c9f-114">You can download the code for this example from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e).</span></span>

### <a name="to-set-up-the-project"></a><span data-ttu-id="24c9f-115">So richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="24c9f-115">To set up the project</span></span>

1. <span data-ttu-id="24c9f-116">Führen Sie die folgenden Schritte aus, um eine WPF-Anwendung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="24c9f-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="24c9f-117">Ausführliche Anweisungen zu diesen Schritten finden Sie unter Exemplarische Vorgehensweise [: Zugreifen auf das Web mit Async und warten (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="24c9f-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>

    - <span data-ttu-id="24c9f-118">Erstellen Sie eine WPF-Anwendung, die ein Textfeld und eine Schaltfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="24c9f-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="24c9f-119">Benennen Sie die Schaltfläche mit `startButton` und das Textfeld mit `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="24c9f-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>

    - <span data-ttu-id="24c9f-120">Fügen Sie einen Verweis für <xref:System.Net.Http> hinzu.</span><span class="sxs-lookup"><span data-stu-id="24c9f-120">Add a reference for <xref:System.Net.Http>.</span></span>

    - <span data-ttu-id="24c9f-121">Fügen Sie in der Datei "MainWindow. XAML. vb" eine- `Imports` Anweisung für hinzu `System.Net.Http` .</span><span class="sxs-lookup"><span data-stu-id="24c9f-121">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>

### <a name="to-add-the-code"></a><span data-ttu-id="24c9f-122">So fügen Sie den Code hinzu</span><span class="sxs-lookup"><span data-stu-id="24c9f-122">To add the code</span></span>

1. <span data-ttu-id="24c9f-123">Doppelklicken Sie im Entwurfs Fenster MainWindow. XAML auf die Schaltfläche, um den `startButton_Click` Ereignishandler in "MainWindow. XAML. vb" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24c9f-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

2. <span data-ttu-id="24c9f-124">Kopieren Sie den folgenden Code, und fügen Sie ihn in " `startButton_Click` MainWindow. XAML. vb" in den Text von ein.</span><span class="sxs-lookup"><span data-stu-id="24c9f-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>

    ```vb
    resultsTextBox.Clear()
    Await CreateMultipleTasksAsync()
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    ```

     <span data-ttu-id="24c9f-125">Der Code ruft die asynchrone Methode `CreateMultipleTasksAsync` auf, die die Anwendung steuert.</span><span class="sxs-lookup"><span data-stu-id="24c9f-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>

3. <span data-ttu-id="24c9f-126">Fügen Sie dem Projekt die folgenden Unterstützungsmethoden hinzu:</span><span class="sxs-lookup"><span data-stu-id="24c9f-126">Add the following support methods to the project:</span></span>

    - <span data-ttu-id="24c9f-127">`ProcessURLAsync` verwendet eine <xref:System.Net.Http.HttpClient>-Methode, um die Inhalte einer Website als Bytearray herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="24c9f-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="24c9f-128">Die Unterstützungsmethode `ProcessURLAsync` wird daraufhin angezeigt und gibt die Länge des Arrays zurück.</span><span class="sxs-lookup"><span data-stu-id="24c9f-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>

    - <span data-ttu-id="24c9f-129">`DisplayResults` zeigt die Anzahl von Bytes im Bytearray für jede URL an.</span><span class="sxs-lookup"><span data-stu-id="24c9f-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="24c9f-130">Diese Anzeige wird aufgerufen, wenn alle Aufgaben den Download abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="24c9f-130">This display shows when each task has finished downloading.</span></span>

     <span data-ttu-id="24c9f-131">Kopieren Sie die folgenden Methoden, und fügen Sie Sie nach dem- `startButton_Click` Ereignishandler in MainWindow. XAML. vb ein.</span><span class="sxs-lookup"><span data-stu-id="24c9f-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
    ```

4. <span data-ttu-id="24c9f-132">Definieren Sie schließlich die `CreateMultipleTasksAsync`-Methode, die die folgenden Schritte ausführt.</span><span class="sxs-lookup"><span data-stu-id="24c9f-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>

    - <span data-ttu-id="24c9f-133">Die Methode deklariert ein `HttpClient`-Objekt, das Sie für den Zugriff auf die <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>-Methode in `ProcessURLAsync` benötigen.</span><span class="sxs-lookup"><span data-stu-id="24c9f-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>

    - <span data-ttu-id="24c9f-134">Die Methode erstellt und startet drei Aufgaben vom Typ <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="24c9f-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="24c9f-135">Beim Abschließen jeder Aufgabe zeigt `DisplayResults` die URL der Aufgabe sowie die Länge der heruntergeladenen Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="24c9f-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="24c9f-136">Da die Aufgaben asynchron ausgeführt werden, kann sich die Reihenfolge, in der die Ergebnisse angezeigt werden, von der Reihenfolge, in der sie deklariert wurden, unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="24c9f-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>

    - <span data-ttu-id="24c9f-137">Die Methode erwartet den Abschluss jeder Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="24c9f-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="24c9f-138">Jeder `Await`-Operator hält die Ausführung von `CreateMultipleTasksAsync` an, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="24c9f-138">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="24c9f-139">Der Operator ruft außerdem den Rückgabewert des Aufrufs von `ProcessURLAsync` von jeder abgeschlossenen Aufgabe ab.</span><span class="sxs-lookup"><span data-stu-id="24c9f-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>

    - <span data-ttu-id="24c9f-140">Wenn die Aufgaben abgeschlossen und die ganzzahligen Werte abgerufen wurden, werden die Längen der Websites von der Methode summiert, und das Ergebnis wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="24c9f-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>

     <span data-ttu-id="24c9f-141">Kopieren Sie die folgende Methode, und fügen Sie sie in Ihre Projektmappe ein.</span><span class="sxs-lookup"><span data-stu-id="24c9f-141">Copy the following method, and paste it into your solution.</span></span>

    ```vb
    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function
    ```

5. <span data-ttu-id="24c9f-142">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="24c9f-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="24c9f-143">Führen Sie das Programm mehrmals aus, um sicherzustellen, dass die drei Aufgaben nicht immer in derselben Reihenfolge abgeschlossen werden und dass die Reihenfolge, in der sie abgeschlossen werden, nicht notwendigerweise der Reihenfolge entspricht, in der sie erstellt und erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="24c9f-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>

## <a name="example"></a><span data-ttu-id="24c9f-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24c9f-144">Example</span></span>

<span data-ttu-id="24c9f-145">Der folgende Code umfasst das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="24c9f-145">The following code contains the full example.</span></span>

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click
        resultsTextBox.Clear()
        Await CreateMultipleTasksAsync()
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function CreateMultipleTasksAsync() As Task

        ' Declare an HttpClient object, and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Create and start the tasks. As each task finishes, DisplayResults
        ' displays its length.
        Dim download1 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com", client)
        Dim download2 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)
        Dim download3 As Task(Of Integer) =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client)

        ' Await each task.
        Dim length1 As Integer = Await download1
        Dim length2 As Integer = Await download2
        Dim length3 As Integer = Await download3

        Dim total As Integer = length1 + length2 + length3

        ' Display the total count for all of the websites.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Sub DisplayResults(url As String, content As Byte())

        ' Display the length of each website. The string format
        ' is designed to be used with a monospaced font, such as
        ' Lucida Console or Global Monospace.
        Dim bytes = content.Length
        ' Strip off the "https://".
        Dim displayURL = url.Replace("https://", "")
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="24c9f-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24c9f-146">See also</span></span>

- [<span data-ttu-id="24c9f-147">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24c9f-147">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="24c9f-148">Asynchronous Programming with Async and Await (Visual Basic) (Asynchrone Programmierung mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="24c9f-148">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="24c9f-149">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="24c9f-149">[How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)</span></span>
