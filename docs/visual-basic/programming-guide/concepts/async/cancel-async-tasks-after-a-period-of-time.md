---
title: Asynchrone Aufgaben nach einer Zeitperiode abbrechen
ms.date: 07/20/2015
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
ms.openlocfilehash: 4b1cfe03e0bbcc0e601a1ec641c95bd68266b7c8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347949"
---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>Asynchrone Aufgaben nach einer Zeitperiode abbrechen (Visual Basic)

Sie können einen asynchronen Vorgang nach einem gewissen Zeitraum mithilfe der <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=nameWithType>-Methode abbrechen, wenn Sie nicht auf das Ende des Vorgangs warten möchten. Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.

Dieses Beispiel fügt dem in [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) entwickelten Code Funktionen zum Herunterladen einer Liste von Websites und Anzeigen der Länge der Inhalte jeder Site hinzu.

> [!NOTE]
> Zum Ausführen der Beispiele müssen Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf dem Computer installiert sein.

## <a name="downloading-the-example"></a>Herunterladen des Beispiels

Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen und anschließend die folgenden Schritte ausführen.

1. Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.

2. Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.

3. Öffnen Sie im Dialogfeld **Projekt öffnen** den Ordner, der den von Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (SLN-Datei) für AsyncFineTuningVB.

4. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das **CancelAfterTime**-Projekt und wählen dann **Als Startprojekt festlegen** aus.

5. Drücken Sie die Taste F5, um das Projekt auszuführen.

     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.

6. Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird.

 Wenn Sie das Projekt nicht herunterladen möchten, können Sie sich die Datei „MainWindow.xaml.vb“ am Ende dieses Themas anschauen.

## <a name="building-the-example"></a>Erstellen des Beispiels

Das Beispiel in diesem Thema baut auf dem Projekt auf, das unter [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) entwickelt wurde, um eine Aufgabenliste abzubrechen. Im Beispiel wird die gleiche UI verwendet, obwohl die Schaltfläche **Abbrechen** nicht explizit verwendet wird.

Um das Beispiel selbst schrittweise zu erstellen, befolgen Sie die Anweisungen im Abschnitt „Herunterladen des Beispiels“. Wählen Sie als **Startprojekt** aber **CancelAListOfTasks** aus. Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.

Zum Angeben einer maximalen Zeitspanne bis zum Abbrechen der Aufgaben fügen Sie den Aufruf von `CancelAfter` in `startButton_Click` hinzu, wie im folgenden Beispiel gezeigt. Die Ergänzung ist mit Sternchen gekennzeichnet.

```vb
Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)

    ' Instantiate the CancellationTokenSource.
    cts = New CancellationTokenSource()

    resultsTextBox.Clear()

    Try
        ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
        ' can adjust the time.)
        cts.CancelAfter(2500)

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
```

Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird. The following output is a sample:

```console
Length of the downloaded string: 35990.

Length of the downloaded string: 407399.

Length of the downloaded string: 226091.

Downloads canceled.
```

## <a name="complete-example"></a>Vollständiges Beispiel

Der folgende Code besteht aus dem vollständigen Text der Datei „MainWindow.xaml.vb“ für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.

Beachten Sie, dass Sie einen Verweis für <xref:System.Net.Http> hinzufügen müssen.

Sie können das Projekt von [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) herunterladen.

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
            ' ***Set up the CancellationTokenSource to cancel after 2.5 seconds. (You
            ' can adjust the time.)
            cts.CancelAfter(2500)

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

        ' Process each element in the list of web addresses.
        For Each url In urlList
            ' GetAsync returns a Task(Of HttpResponseMessage).
            ' Argument ct carries the message if the Cancel button is chosen.
            ' Note that the Cancel button can cancel all remaining downloads.
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)

            ' Retrieve the website contents from the HttpResponseMessage.
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()

            resultsTextBox.Text &=
                vbCrLf & $"Length of the downloaded string: {urlContents.Length}." & vbCrLf
        Next
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

' Length of the downloaded string: 35990.

' Length of the downloaded string: 407399.

' Length of the downloaded string: 226091.

' Downloads canceled.
```

## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
- [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic))
- [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)
- [Fine-Tuning Your Async Application (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) (Feinabstimmung der Async-Anwendung (Visual Basic))
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Asynchrones Beispiel: Feinabstimmung der Anwendung)
