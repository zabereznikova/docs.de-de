---
title: Asynchrone Aufgaben nach einiger Zeit (Visual Basic) Abbrechen | Microsoft-Dokumentation
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
ms.assetid: a48045a3-6a99-42af-b824-af340f0b9a5d
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6708bd92d8dc2455b9dcb8e02dcc0a4455e00cda
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-async-tasks-after-a-period-of-time-visual-basic"></a>Brechen Sie asynchrone Aufgaben ab, nachdem eine bestimmte Zeitspanne (Visual Basic)
Sie können einen asynchronen Vorgang nach einiger Zeit abbrechen, indem die <xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName>Methode, wenn Sie zum Abschluss des Vorgangs warten möchten.</xref:System.Threading.CancellationTokenSource.CancelAfter%2A?displayProperty=fullName> Diese Methode plant den Abbruch aller zugeordneten Aufgaben, die innerhalb des vom `CancelAfter`-Ausdruck festgelegten Zeitraums nicht abgeschlossen sind.  
  
 Diesem Beispiel wird der Code, der in Entwicklung [Abbrechen, eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) eine Liste von Websites heruntergeladen und die Länge des Inhalts der einzelnen anzuzeigen.  
  
> [!NOTE]
>  Zum Ausführen der Beispiele benötigen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.  
  
## <a name="downloading-the-example"></a>Herunterladen des Beispiels  
 Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.  
  
1.  Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2.  Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
3.  In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.  
  
4.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelAfterTime** Projekt, und wählen Sie dann **Set as StartUp Project**.  
  
5.  Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
6.  Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird.  
  
 Wenn Sie das Projekt herunterladen möchten, können Sie die Datei "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.  
  
## <a name="building-the-example"></a>Erstellen des Beispiels  
 Im Beispiel in diesem Thema wird das Projekt, das in entwickelt wird hinzugefügt [Abbrechen, eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) , eine Liste von Aufgaben abzubrechen. Im Beispiel wird die gleiche UI verwendet, obwohl die **Abbrechen** Schaltfläche nicht explizit verwendet wird.  
  
 So erstellen Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **CancelAListOfTasks** als die **Startprojekt**. Fügen Sie diesem Projekt die Änderungen in diesem Thema hinzu.  
  
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
  
 Führen Sie das Programm mehrmals aus, und überprüfen Sie dabei, ob die Ausgabe für alle, keine oder einige Websites angezeigt wird. Die folgende Ausgabe ist beispielhaft.  
  
```  
Length of the downloaded string: 35990.  
  
Length of the downloaded string: 407399.  
  
Length of the downloaded string: 226091.  
  
Downloads canceled.  
```  
  
## <a name="complete-example"></a>Vollständiges Beispiel  
 Im folgende Code wird der vollständige Text der Datei "MainWindow.Xaml.vb" für das Beispiel. Sternchen markieren die Elemente, die für dieses Beispiel hinzugefügt wurden.  
  
 Beachten Sie, dass Sie eine Referenz für <xref:System.Net.Http>.</xref:System.Net.Http> hinzufügen müssen  
  
 Sie können das Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
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
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
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
  
' Length of the downloaded string: 35990.  
  
' Length of the downloaded string: 407399.  
  
' Length of the downloaded string: 226091.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Abbrechen einer asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)   
 [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [ASYNC-Beispiel: Feinabstimmung der Anwendung](http://go.microsoft.com/fwlink/?LinkId=255046)
