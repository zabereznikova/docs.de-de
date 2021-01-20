---
title: Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten
ms.date: 07/20/2015
ms.assetid: 57ffb748-af40-4794-bedd-bdb7fea062de
ms.openlocfilehash: 4eb4d15739da82cbfcc8dc5e03af4c1ae761d553
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615905"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-visual-basic"></a>Start Multiple Async Tasks and Process Them As They Complete (Visual Basic) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (Visual Basic))

Mit <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> können Sie mehrere Aufgaben gleichzeitig starten und diese nicht in der Reihenfolge, in der sie gestartet wurden, sondern zu dem Zeitpunkt, zu dem sie abgeschlossen werden, verarbeiten.  
  
 Im folgenden Beispiel wird eine Abfrage verwendet, um eine Auflistung von Aufgaben zu erstellen. Jede Aufgabe lädt den Inhalt einer angegebenen Website herunter. In jeder Iteration einer While-Schleife gibt ein erwarteter Aufruf von `WhenAny` die Aufgabe in der Auflistung von Aufgaben zurück, die ihren Download zuerst beendet. Diese Aufgabe wird aus der Auflistung entfernt und verarbeitet. Die Ausführung der Schleife wird wiederholt, bis die Auflistung keine Aufgaben mehr enthält.  
  
> [!NOTE]
> Zum Ausführen des Beispiels muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.  
  
## <a name="downloading-the-example"></a>Herunterladen des Beispiels  

 Sie können alle Windows Presentation Foundation (WPF)-Projekte von [Async Sample: Fine Tuning Your Application (Asynchrones Beispiel: Optimierung Ihrer Anwendung)](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und die folgenden Schritte ausführen.  
  
1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2. Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen** und **Projekt/Projektmappe**.  
  
3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningVB.  
  
4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt **ProcessTasksAsTheyFinish** und wählen dann **Als Startprojekt festlegen** aus.  
  
5. Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
6. Führen Sie das Projekt mehrmals aus, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.  
  
 Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Datei „MainWindow.xaml.vb“ am Ende dieses Themas anschauen.  
  
## <a name="building-the-example"></a>Erstellen des Beispiels  

 In diesem Beispiel wird der Code hinzugefügt, der in verbleibende asynchrone [Aufgaben abbrechen, nachdem ein Vorgang abgeschlossen wurde (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md) und die gleiche Benutzeroberfläche verwendet wird.  
  
 Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAfterOneTask** aus. Fügen Sie die Änderungen in diesem Thema zur `AccessTheWebAsync`-Methode in diesem Projekt hinzu. Die Änderungen sind mit Sternchen gekennzeichnet.  
  
 Das Projekt **CancelAfterOneTask** enthält bereits eine Abfrage, die eine Auflistung von Aufgaben erstellt, während sie ausgeführt wird. Jeder Aufruf von `ProcessURLAsync` im folgenden Code gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine ganze Zahl ist.  
  
```vb  
Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
    From url In urlList Select ProcessURLAsync(url, client, ct)  
```  
  
 Nehmen Sie in der Datei "MainWindow. XAML. vb" des Projekts die folgenden Änderungen an der- `AccessTheWebAsync` Methode vor.  
  
- Führen Sie die Abfrage aus, indem Sie <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anstelle von <xref:System.Linq.Enumerable.ToArray%2A> anwenden.  
  
    ```vb  
    Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
    ```  
  
- Fügen Sie eine While-Schleife hinzu, die die folgenden Schritte für jede Aufgabe in der Auflistung ausführt.  
  
    1. Erwartet einen Aufruf von `WhenAny`, um die erste Aufgabe in der Auflistung zu identifizieren, die ihren Download beendet.  
  
        ```vb  
        Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
        ```  
  
    2. Entfernt die entsprechende Aufgabe aus der Auflistung.  
  
        ```vb  
        downloadTasks.Remove(finishedTask)  
        ```  
  
    3. Erwartet `finishedTask`, das durch einen Aufruf von `ProcessURLAsync` zurückgegeben wird. Die Variable `finishedTask` ist eine <xref:System.Threading.Tasks.Task%601>, wobei `TReturn` eine ganze Zahl ist. Die Aufgabe ist bereits abgeschlossen, aber es darauf gewartet, dass von ihr die Länge der heruntergeladenen Website abgerufen wird, wie im folgenden Beispiel dargestellt.  
  
        ```vb  
        Dim length = Await finishedTask  
        resultsTextBox.Text &= String.Format(vbCrLf & "Length of the downloaded website:  {0}" & vbCrLf, length)  
        ```  
  
 Sie sollten das Projekt mehrmals ausführen, um zu überprüfen, dass die heruntergeladenen Längen nicht immer in der gleichen Reihenfolge angezeigt werden.  
  
> [!CAUTION]
> Sie können `WhenAny` in einer Schleife gemäß der Beschreibung im Beispiel verwenden, um Problemlösungen zu entwickeln, die nur wenige Aufgaben umfassen. Andere Ansätze sind jedoch effizienter, wenn viele Aufgaben verarbeitet werden müssen. Weitere Informationen und Beispiele finden Sie unter [Verarbeiten von Aufgaben](https://devblogs.microsoft.com/pfxteam/processing-tasks-as-they-complete/)nach deren Abschluss.  
  
## <a name="complete-example"></a>Vollständiges Beispiel  

 Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.vb“ für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.  
  
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
  
        ' **_Create a query that, when executed, returns a collection of tasks.  
        Dim downloadTasksQuery As IEnumerable(Of Task(Of Integer)) =  
            From url In urlList Select ProcessURLAsync(url, client, ct)  
  
        ' _*_Use ToList to execute the query and start the download tasks.
        Dim downloadTasks As List(Of Task(Of Integer)) = downloadTasksQuery.ToList()  
  
        ' _*_Add a loop to process the tasks one at a time until none remain.  
        While downloadTasks.Count > 0  
            ' _*_Identify the first task that completes.  
            Dim finishedTask As Task(Of Integer) = Await Task.WhenAny(downloadTasks)  
  
            ' _*_Remove the selected task from the list so that you don't  
            ' process it more than once.  
            downloadTasks.Remove(finishedTask)  
  
            ' _**Await the first completed task and display the results.  
            Dim length = Await finishedTask  
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
  
' Length of the download:  226093  
' Length of the download:  412588  
' Length of the download:  175490  
' Length of the download:  204890  
' Length of the download:  158855  
' Length of the download:  145790  
' Length of the download:  44908  
' Downloads complete.  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Fine-Tuning Your Async Application (Visual Basic)](fine-tuning-your-async-application.md) (Feinabstimmung der Async-Anwendung (Visual Basic))
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung Ihrer Anwendung)
