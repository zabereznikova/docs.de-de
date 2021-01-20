---
title: Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen
ms.date: 07/20/2015
ms.assetid: c928b5a1-622f-4441-8baf-adca1dde197f
ms.openlocfilehash: a0a04c62378ddf70ab3dee9a522e490b0a73b83e
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615957"
---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-visual-basic"></a>Cancel Remaining Async Tasks after One Is Complete (Visual Basic) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (Visual Basic))

Mit der <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>-Methode zusammen mit einem <xref:System.Threading.CancellationToken> können Sie alle verbleibenden Aufgaben abbrechen, wenn eine Aufgabe abgeschlossen wurde. Die `WhenAny`-Methode akzeptiert ein Argument, das eine Auflistung von Aufgaben ist. Die Methode startet alle Aufgaben und gibt eine einzelne Aufgabe zurück. Die einzelne Aufgabe ist abgeschlossen, wenn eine beliebige Aufgabe in der Auflistung abgeschlossen ist.

In diesem Beispiel wird veranschaulicht, wie ein Abbruchtoken in Verbindung mit `WhenAny` verwendet wird, um an der ersten Aufgabe festzuhalten, die in der Auflistung von Aufgaben beendet wird, und die übrigen Aufgaben abzubrechen. Jede Aufgabe lädt den Inhalt einer Website herunter. Im Beispiel wird die Länge des Inhalts des ersten abgeschlossenen Downloads angezeigt und die anderen Downloads abgebrochen.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="downloading-the-example"></a>Herunterladen des Beispiels

Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.

1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen** und **Projekt/Projektmappe**.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningVB.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterOneTask**-Projekt, und wählen Sie dann **Als Startprojekt festlegen** aus.

5. Drücken Sie die Taste F5, um das Projekt auszuführen.

    Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.

6. Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.

Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Datei „MainWindow.xaml.vb“ am Ende dieses Themas anschauen.

## <a name="building-the-example"></a>Erstellen des Beispiels

Das Beispiel in diesem Thema wird dem Projekt hinzugefügt, das in [Abbrechen einer asynchronen Aufgabe oder einer Liste von Aufgaben](cancel-an-async-task-or-a-list-of-tasks.md) zum Abbrechen einer Aufgabenliste entwickelt wurde. Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.

Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus. Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.

Starten Sie in der Datei "MainWindow. XAML. vb" des Projekts **cancelalistoftasks** den Übergang, indem Sie die Verarbeitungsschritte für jede Website aus der-Schleife in in `AccessTheWebAsync` die folgende Async-Methode verschieben.

```vb
' **_Bundle the processing steps for a website into one async method.
Async Function ProcessURLAsync(url As String, client As HttpClient, ct As CancellationToken) As Task(Of Integer)

    ' GetAsync returns a Task(Of HttpResponseMessage).
    Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

    ' Retrieve the website contents from the HttpResponseMessage.
    Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

    Return urlContents.Length
End Function
```

In `AccessTheWebAsync` wird in diesem Beispiel eine Abfrage, die <xref:System.Linq.Enumerable.ToArray%2A>-Methode und die `WhenAny`-Methode verwendet, um ein Array von Aufgaben zu erstellen und zu starten. Die Anwendung von `WhenAny` auf den Array gibt eine einzelne Aufgabe zurück, die, wenn sie erwartet wird, zur ersten Aufgabe auswertet wird, die im Array von Aufgaben zum Abschluss kommt.

Nehmen Sie in `AccessTheWebAsync` die folgenden Änderungen vor. Die Änderungen in der Codedatei sind mit Sternchen gekennzeichnet.

1. Kommentieren Sie die Schleife aus oder löschen Sie sie.

2. Erstellen Sie eine Abfrage, die eine Auflistung generischer Aufgaben erstellt, wenn sie ausgeführt wird. Jeder Aufruf von `ProcessURLAsync` gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.

    ```vb
    ' _*_Create a query that, when executed, returns a collection of tasks.
    Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
        From url In urlList Select ProcessURLAsync(url, client, ct)
    ```

3. Rufen Sie `ToArray` auf, um die Abfrage auszuführen und die Aufgaben zu starten. Die Anwendung der `WhenAny`-Methode im nächsten Schritt würde die Abfrage ohne `ToArray` ausführen und die Aufgaben starten, bei anderen Methoden ist dies möglicherweise nicht der Fall. Die sicherste Methode besteht darin, die Ausführung der Abfrage explizit zu erzwingen.

    ```vb
    ' _*_Use ToArray to execute the query and start the download tasks.
    Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()
    ```

4. Rufen Sie `WhenAny` mit der Auflistung von Aufgaben auf. `WhenAny` gibt `Task(Of Task(Of Integer))` oder `Task<Task<int>>` zurück.  Das bedeutet, dass `WhenAny` eine Aufgabe zurückgibt, die zu einem einzelnen `Task(Of Integer)` oder `Task<int>` ausgewertet wird, wenn sie erwartet wird. Diese einzelne Aufgabe ist die erste Aufgabe in der Auflistung, die beendet wird. Die Aufgabe, die als erste beendet wird, wird `finishedTask` zugewiesen. Der Typ von `finishedTask` ist <xref:System.Threading.Tasks.Task%601>, wobei `TResult` eine ganze Zahl ist, da dies der Rückgabetyp von `ProcessURLAsync` ist.

    ```vb
    ' _*_Call WhenAny and then await the result. The task that finishes
    ' first is assigned to finishedTask.
    Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)
    ```

5. In diesem Beispiel sind Sie nur an der Aufgabe interessiert, die zuerst beendet wird. Verwenden Sie daher <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType>, um die verbleibenden Aufgaben abzubrechen.

    ```vb
    ' _*_Cancel the rest of the downloads. You just want the first one.
    cts.Cancel()
    ```

6. Schließlich warten Sie ab, dass `finishedTask` die Länge des heruntergeladenen Inhalts abruft.

    ```vb
    Dim length = Await finishedTask
    resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    ```

Führen Sie das Programm mehrmals aus, um zu überprüfen, dass unterschiedliche Downloads als erste beendet werden.

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus der vollständigen Datei "MainWindow.xaml.cs" oder "MainWindow.xaml.vb" für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.

Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.

Sie können das Projekt hier herunterladen: [Async Sample: Fine Tuning Your Application (Async-Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).

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
        ''        vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        ''Next

        ' _*_Create a query that, when executed, returns a collection of tasks.
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =
            From url In urlList Select ProcessURLAsync(url, client, ct)

        ' _*_Use ToArray to execute the query and start the download tasks.
        Dim downloadTasks As Task(Of Integer)() = downloadTasksQuery.ToArray()

        ' _*_Call WhenAny and then await the result. The task that finishes
        ' first is assigned to finishedTask.
        Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)

        ' _*_Cancel the rest of the downloads. You just want the first one.
        cts.Cancel()

        ' _*_Await the first completed task and display the results
        ' Run the program several times to demonstrate that different
        ' websites can finish first.
        Dim length = Await finishedTask
        resultsTextBox.Text &= vbCrLf & $"Length of the downloaded website:  {length}" & vbCrLf
    End Function

    ' _**Bundle the processing steps for a website into one async method.
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
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/hh290138.aspx",
                "https://msdn.microsoft.com/library/hh290140.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            }
        Return urls
    End Function

End Class

' Sample output:

' Length of the downloaded website:  158856

' Download complete.
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Feinabstimmung der Async-Anwendung (Visual Basic))
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
