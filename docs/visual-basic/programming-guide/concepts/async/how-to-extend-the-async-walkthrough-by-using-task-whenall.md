---
title: 'Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll'
ms.date: 07/20/2015
ms.assetid: c06d386d-e996-4da9-bf3d-05a3b6c0a258
ms.openlocfilehash: 6df29a90ff0012564c6d966c8156434d25cacdb1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354246"
---
# <a name="how-to-extend-the-async-walkthrough-by-using-taskwhenall-visual-basic"></a>How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)

You can improve the performance of the async solution in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) by using the <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> method. Diese Methode wartet auf mehrere asynchrone Vorgänge, die als Auflistung von Aufgaben dargestellt werden.

Sie haben möglicherweise in der exemplarischen Vorgehensweise bemerkt, dass die Websites Downloads in verschiedenen Geschwindigkeiten anbieten. Manchmal ist eine Website sehr langsam und verzögert alle verbleibenden Downloads. Wenn Sie die asynchronen Projektmappen ausführen, die Sie in der exemplarischen Vorgehensweise erstellt haben, können Sie das Programm einfach beenden, wenn Sie nicht warten möchten. Eine bessere Option wäre jedoch, alle Downloads gleichzeitig zu starten und schnellere Downloads einfach fortfahren, ohne auf langsamere zu warten.

Sie wenden die `Task.WhenAll`-Methode auf eine Aufgabenauflistung an. Die Anwendung von `WhenAll` gibt eine einzelne Aufgabe zurück, die nicht abgeschlossen ist, bevor jede Aufgabe in der Auflistung abgeschlossen ist. Die Aufgaben scheinen parallel ausgeführt zu werden, es werden jedoch keine weiteren Threads erstellt. Die Aufgaben können in jeder Reihenfolge abschließen.

> [!IMPORTANT]
> The following procedures describe extensions to the async applications that are developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können die Anwendungen entwickeln, indem Sie entweder die exemplarische Vorgehensweise durcharbeiten oder den Code von [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.
>
> Für die Ausführung des Beispiels muss Visual Studio 2012 oder höher auf dem Computer installiert sein.

### <a name="to-add-taskwhenall-to-your-geturlcontentsasync-solution"></a>So fügen Sie der GetURLContentsAsync-Lösung Task.WhenAll hinzu

1. Add the `ProcessURLAsync` method to the first application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).

    - If you downloaded the code from  [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.

    - Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `GetURLContentsAsync`-Methode enthält. The MainWindow.xaml.vb file for this application is the first example in the "Complete Code Examples from the Walkthrough" section.

     Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `For Each`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise. Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.

    ```vb
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Kommentieren Sie die Schleife `For Each` in `SumPageSizesAsync` aus, oder löschen Sie sie, wie der folgenden Code zeigt.

    ```vb
    'Dim total = 0
    'For Each url In urlList

    '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

    '    ' The previous line abbreviates the following two assignment statements.

    '    ' GetURLContentsAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Erstellen Sie eine Auflistung von Aufgaben. Der folgende Code definiert eine [Abfrage](../../../../visual-basic/programming-guide/concepts/linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt. Die Aufgaben werden beim Auswerten der Abfrage gestartet.

     Fügen Sie nach der Deklaration von `SumPageSizesAsync` den folgenden Code der `urlList`-Methode hinzu:

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben `downloadTasks` an. `Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.

     Im folgenden Beispiel erwartet der `Await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt. Der Ausdruck wird gegen ein Array mit ganzen Zahlen ausgewertet, wobei jede ganze Zahl die Länge einer heruntergeladenen Website ist. Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen. Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-add-taskwhenall-to-the-httpclientgetbytearrayasync-solution"></a>So fügen Sie der HttpClient.GetByteArrayAsync-Lösung Task.WhenAll hinzu

1. Add the following version of `ProcessURLAsync` to the second application that's developed in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).

    - If you downloaded the code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f), open the AsyncWalkthrough_HttpClient project, and then add `ProcessURLAsync` to the MainWindow.xaml.vb file.

    - Wenn Sie den Code innerhalb der exemplarische Vorgehensweise entwickelt haben, fügen Sie `ProcessURLAsync` der Anwendung hinzu, die die `HttpClient.GetByteArrayAsync`-Methode verwendet. The MainWindow.xaml.vb file for this application is the second example in the "Complete Code Examples from the Walkthrough" section.

     Die `ProcessURLAsync`-Methode konsolidiert die Aktionen im Text der `For Each`-Schleife in `SumPageSizesAsync` in der ersten exemplarischen Vorgehensweise. Die Methode lädt asynchron den angegebenen Inhalt einer Website als Bytearray und gibt dann die Länge des Bytearrays zurück.

     Der einzige Unterschied der `ProcessURLAsync`-Methode in der vorherigen Prozedur ist die Verwendung der <xref:System.Net.Http.HttpClient>-Instanz, `client`.

    ```vb
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)

        Dim byteArray = Await client.GetByteArrayAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function
    ```

2. Kommentieren Sie die Schleife `For Each` in `SumPageSizesAsync` aus, oder löschen Sie sie, wie der folgenden Code zeigt.

    ```vb
    'Dim total = 0
    'For Each url In urlList
    '    ' GetByteArrayAsync returns a task. At completion, the task
    '    ' produces a byte array.
    '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)

    '    ' The following two lines can replace the previous assignment statement.
    '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    '    'Dim urlContents As Byte() = Await getContentsTask

    '    DisplayResults(url, urlContents)

    '    ' Update the total.
    '    total += urlContents.Length
    'Next
    ```

3. Definieren Sie eine [Abfrage](../../../../visual-basic/programming-guide/concepts/linq/index.md), die beim Ausführen durch die <xref:System.Linq.Enumerable.ToArray%2A>-Methode eine Aufgabenauflistung erstellt, die die Inhalte jeder Website herunterlädt. Die Aufgaben werden beim Auswerten der Abfrage gestartet.

     Fügen Sie nach der Deklaration von `SumPageSizesAsync` und `client` den folgenden Code der `urlList`-Methode hinzu:

    ```vb
    ' Create a query.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client)

    ' Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Wenden Sie `Task.WhenAll` auf die Auflistung von Aufgaben an, `downloadTasks`. `Task.WhenAll` gibt eine einzelne abgeschlossene Aufgabe zurück, wenn alle Aufgaben in der Auflistung abgeschlossen wurden.

     Im folgenden Beispiel erwartet der `Await`-Ausdruck den Abschluss der einzelnen Aufgabe, die `WhenAll` zurückgibt. Wenn vollständig, wertet der `Await`-Ausdruck als Ergebnis ein Array von ganzen Zahlen aus, wobei jede ganze Zahl die Länge einer heruntergeladenen Website hat. Fügen Sie `SumPageSizesAsync` den folgenden Code hinzu, direkt nach dem im vorherigen Schritt hinzugefügten Code.

    ```vb
    ' Await the completion of all the running tasks.
    Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

    '' The previous line is equivalent to the following two statements.
    'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
    'Dim lengths As Integer() = Await whenAllTask
    ```

5. Abschließend verwenden Sie die <xref:System.Linq.Enumerable.Sum%2A>-Methode, um die Summe der Größen aller Websites zu berechnen. Fügen Sie `SumPageSizesAsync` die folgende Zeile hinzu.

    ```vb
    Dim total = lengths.Sum()
    ```

### <a name="to-test-the-taskwhenall-solutions"></a>So testen Sie die Task.WhenAll-Lösungen

Drücken Sie in beiden Projektmappen F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten**. The output should resemble the output from the async solutions in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Beachten Sie jedoch, dass die Websites in einer jeweils anderen Reihenfolge angezeigt werden.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Erweiterungen des Projekts, das die `GetURLContentsAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        ' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        'Dim total = 0
        'For Each url In urlList

        '    Dim urlContents As Byte() = Await GetURLContentsAsync(url)

        '    ' The previous line abbreviates the following two assignment statements.

        '    ' GetURLContentsAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
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
            }
        Return urls
    End Function

    ' The actions from the foreach loop are moved to this async method.
    Private Async Function ProcessURLAsync(url As String) As Task(Of Integer)

        Dim byteArray = Await GetURLContentsAsync(url)
        DisplayResults(url, byteArray)
        Return byteArray.Length
    End Function

    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

        ' The downloaded resource ends up in the variable named content.
        Dim content = New MemoryStream()

        ' Initialize an HttpWebRequest for the current URL.
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

        ' Send the request to the Internet resource and wait for
        ' the response.
        Using response As WebResponse = Await webReq.GetResponseAsync()
            ' Get the data stream that is associated with the specified URL.
            Using responseStream As Stream = response.GetResponseStream()
                ' Read the bytes in responseStream and copy them to content.
                ' CopyToAsync returns a Task, not a Task<T>.
                Await responseStream.CopyToAsync(content)
            End Using
        End Using

        ' Return the result as a byte array.
        Return content.ToArray()
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

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Erweiterungen des Projekts, das die `HttpClient.GetByteArrayAsync`-Methode verwendet, um Inhalt aus dem Web herunterladen.

```vb
' Add the following Imports statements, and add a reference for System.Net.Http.
Imports System.Net.Http
Imports System.Net
Imports System.IO

Class MainWindow

    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click

        resultsTextBox.Clear()

        '' One-step async call.
        Await SumPageSizesAsync()

        '' Two-step async call.
        'Dim sumTask As Task = SumPageSizesAsync()
        'Await sumTask

        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."
    End Sub

    Private Async Function SumPageSizesAsync() As Task

        ' Declare an HttpClient object and increase the buffer size. The
        ' default buffer size is 65,536.
        Dim client As HttpClient =
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}

        ' Make a list of web addresses.
        Dim urlList As List(Of String) = SetUpURLList()

        ' Create a query.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client)

        ' Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' You can do other work here before awaiting.

        ' Await the completion of all the running tasks.
        Dim lengths As Integer() = Await Task.WhenAll(downloadTasks)

        '' The previous line is equivalent to the following two statements.
        'Dim whenAllTask As Task(Of Integer()) = Task.WhenAll(downloadTasks)
        'Dim lengths As Integer() = Await whenAllTask

        Dim total = lengths.Sum()

        ''<snippet7>
        'Dim total = 0
        'For Each url In urlList
        '    ' GetByteArrayAsync returns a task. At completion, the task
        '    ' produces a byte array.
        '    '<snippet31>
        '    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
        '    '</snippet31>

        '    ' The following two lines can replace the previous assignment statement.
        '    'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
        '    'Dim urlContents As Byte() = Await getContentsTask

        '    DisplayResults(url, urlContents)

        '    ' Update the total.
        '    total += urlContents.Length
        'NextNext

        ' Display the total count for all of the web addresses.
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &
                                             "Total bytes returned:  {0}" & vbCrLf, total)
    End Function

    Private Function SetUpURLList() As List(Of String)

        Dim urls = New List(Of String) From
            {
                "https://www.msdn.com",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/ee256749.aspx",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
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

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>
- [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic))
