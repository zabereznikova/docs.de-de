---
title: Eine asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic) Abbrechen | Microsoft-Dokumentation
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
ms.assetid: a9ee1b71-5bec-4736-a1e9-448042dd7215
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
ms.openlocfilehash: fe2df73aaf49f1b61dafcad9a6c6e0f3d014f8ec
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-visual-basic"></a>Abbrechen einer asynchrone Aufgabe oder eine Liste von Aufgaben (Visual Basic)
Sie können eine Schaltfläche einrichten, über die Sie eine asynchrone Anwendung abbrechen können, wenn Sie nicht darauf warten möchten, bis diese beendet wird. Anhand der Beispiele in diesem Thema können Sie einer Anwendung, über die der Inhalt einer Website oder einer Liste von Websites heruntergeladen wird, eine Schaltfläche zum Abbrechen hinzufügen.  
  
 Die Beispiele verwenden die Benutzeroberfläche, [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md) beschreibt.  
  
> [!NOTE]
>  Zum Ausführen der Beispiele müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.  
  
##  <a name="BKMK_CancelaTask"></a>Eine Aufgabe abbrechen  
 Im ersten Beispiel wird die **Abbrechen** Schaltfläche Aufgabe mit einem einzigen Download. Wenn Sie die Schaltfläche auswählen, während die Anwendung Inhalt herunterlädt, wird der Download abgebrochen.  
  
### <a name="downloading-the-example"></a>Herunterladen des Beispiels  
 Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.  
  
1.  Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2.  Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
3.  In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.  
  
4.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelATask** Projekt, und wählen Sie dann **Set as StartUp Project**.  
  
5.  Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
 Wenn Sie das Projekt herunterladen möchten, können Sie die Dateien "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.  
  
### <a name="building-the-example"></a>Erstellen des Beispiels  
 Fügen Sie die folgenden Änderungen eine **Abbrechen** Schaltfläche, um eine Anwendung, die eine Website herunterlädt. Wenn Sie das Beispiel nicht herunterladen oder erstellen möchten, können Sie sich das Endprodukt im Abschnitt „Vollständige Beispiele“ am Ende dieses Themas ansehen. Die Änderungen im Code sind mit Sternchen gekennzeichnet.  
  
 So erstellen Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **StarterCode** als die **Startprojekt** anstelle von **CancelATask**.  
  
 Anschließend fügen Sie der Datei "MainWindow.Xaml.vb" des Projekts.  
  
1.  Deklarieren Sie eine `CancellationTokenSource`-Variable, `cts`, die im Bereich für alle Methoden liegt, die darauf zugreifen.  
  
    ```vb  
    Class MainWindow  
  
        ' ***Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
    ```  
  
2.  Fügen Sie den folgenden Ereignishandler für das **Abbrechen** Schaltfläche. Der Ereignishandler verwendet die <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>-Methode benachrichtigt `cts` Wenn der Benutzer den Abbruch anfordert.</xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>  
  
    ```vb  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
    ```  
  
3.  Nehmen Sie die folgenden im Handler für Änderungen das **Start** Schaltfläche `startButton_Click`.  
  
    -   Instanziieren Sie die `CancellationTokenSource`, `cts`.  
  
        ```vb  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
        ```  
  
    -   Im Aufruf von `AccessTheWebAsync`, wodurch der Inhalt einer bestimmten Website heruntergeladen, senden die <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName>Eigenschaft `cts` als Argument.</xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> Die `Token`-Eigenschaft gibt die Meldung weiter, wenn ein Abbruch angefordert wird. Fügen Sie einen catch-Block hinzu, der eine Meldung angezeigt, wenn der Benutzer den Downloadvorgang abbrechen möchte. Im folgende Code sind alle Änderungen dargestellt.  
  
        ```vb  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
        ```  
  
4.  In `AccessTheWebAsync`, verwenden Sie die <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName>Überladung von der `GetAsync` -Methode in der <xref:System.Net.Http.HttpClient>Typ, um den Inhalt einer Website herunterzuladen.</xref:System.Net.Http.HttpClient> </xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> Übergeben Sie `ct`der <xref:System.Threading.CancellationToken>Parameter von `AccessTheWebAsync`, als zweites Argument.</xref:System.Threading.CancellationToken> Das Token enthält die Meldung, wenn der Benutzer die **Abbrechen** Schaltfläche.  
  
     Im folgende Code sind die Änderungen in `AccessTheWebAsync` dargestellt.  
  
    ```vb  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
    ```  
  
5.  Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     Bei Auswahl der **Abbrechen** Schaltfläche, bevor das Programm beendet wird, Herunterladen des Inhalts, das Programm erzeugt die folgende Ausgabe.  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <a name="BKMK_CancelaListofTasks"></a>Eine Aufgabenliste Abbrechen  
 Sie können das vorherige Beispiel so erweitern, dass viele Aufgaben abgebrochen werden, indem Sie jeder Aufgabe die gleiche `CancellationTokenSource`-Instanz zuordnen. Bei Auswahl der **Abbrechen** klicken, brechen Sie alle Aufgaben, die noch nicht abgeschlossen sind.  
  
### <a name="downloading-the-example"></a>Herunterladen des Beispiels  
 Sie können das vollständige Windows Presentation Foundation (WPF)-Projekt aus [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) und führen Sie dann die folgenden Schritte aus.  
  
1.  Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
2.  Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
3.  In der **Projekt öffnen** im Dialogfeld Öffnen den Ordner, der Ihnen dekomprimierten Beispielcode enthält, und öffnen Sie anschließend die Projektmappendatei (sln) für AsyncFineTuningVB.  
  
4.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **CancelAListOfTasks** Projekt, und wählen Sie dann **Set as StartUp Project**.  
  
5.  Drücken Sie die Taste F5, um das Projekt auszuführen.  
  
     Drücken Sie STRG+F5, um das Projekt auszuführen, ohne es zu debuggen.  
  
 Wenn Sie das Projekt herunterladen möchten, können Sie die Dateien "MainWindow.Xaml.vb" am Ende dieses Themas überprüfen.  
  
### <a name="building-the-example"></a>Erstellen des Beispiels  
 Erweitern Sie das Beispiel selbst, Schritt für Schritt führen Sie die Schritte im Abschnitt "Herunterladen des Beispiels", aber wählen Sie **CancelATask** als die **Startprojekt**. Fügen Sie die folgenden Änderungen zu diesem Projekt hinzu. Die Änderungen im Programm sind mit Sternchen gekennzeichnet.  
  
1.  Fügen Sie eine Methode hinzu, um eine Liste von Webadressen zu erstellen.  
  
    ```vb  
    ' ***Add a method that creates a list of web addresses.  
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
    ```  
  
2.  Rufen Sie die Methode in `AccessTheWebAsync` auf.  
  
    ```vb  
    ' ***Call SetUpURLList to make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
    ```  
  
3.  Fügen Sie die folgende Schleife in `AccessTheWebAsync` hinzu, um jede Webadresse in der Liste zu verarbeiten.  
  
    ```vb  
    ' ***Add a loop to process the list of web addresses.  
    For Each url In urlList  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' Argument ct carries the message if the Cancel button is chosen.   
        ' ***Note that the Cancel button can cancel all remaining downloads.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
    Next  
    ```  
  
4.  Da `AccessTheWebAsync` die Längen anzeigt, muss die Methode nichts zurückzugeben. Entfernen Sie die return-Anweisung, und ändern Sie den Rückgabetyp der Methode in <xref:System.Threading.Tasks.Task>statt <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
     Rufen Sie die Methode über `startButton_Click` auf, indem Sie eine Anweisung anstelle eines Ausdrucks verwenden.  
  
    ```vb  
    Await AccessTheWebAsync(cts.Token)  
    ```  
  
5.  Wenn Sie das Programm nicht abbrechen, wird folgende Ausgabe erzeugt.  
  
    ```  
  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
  
    ```  
  
     Bei Auswahl der **Abbrechen** klicken, bevor die Downloads abgeschlossen sind, enthält die Ausgabe die Längen der Downloads, die vor dem Abbruch abgeschlossen wurden.  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
  
    ```  
  
##  <a name="BKMK_CompleteExamples"></a>Vollständige Beispiele  
 Die folgenden Abschnitte enthalten den Code für jedes der vorherigen Beispiele. Beachten Sie, dass Sie eine Referenz für <xref:System.Net.Http>.</xref:System.Net.Http> hinzufügen müssen  
  
 Sie können die Projekte vom herunterladen [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).  
  
### <a name="cancel-a-task-example"></a>Beispiel zum Abbrechen einer Aufgabe  
 Der folgende Code ist die vollständige "MainWindow.Xaml.vb"-Datei für das Beispiel, das eine einzelne Aufgabe abgebrochen.  
  
```vb  
' Add an Imports directive and a reference for System.Net.Http.  
Imports System.Net.Http  
  
' Add the following Imports directive for System.Threading.  
Imports System.Threading  
  
Class MainWindow  
  
    ' ***Declare a System.Threading.CancellationTokenSource.  
    Dim cts As CancellationTokenSource  
  
    Private Async Sub startButton_Click(sender As Object, e As RoutedEventArgs)  
        ' ***Instantiate the CancellationTokenSource.  
        cts = New CancellationTokenSource()  
  
        resultsTextBox.Clear()  
  
        Try  
            ' ***Send a token to carry the message if cancellation is requested.  
            Dim contentLength As Integer = Await AccessTheWebAsync(cts.Token)  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
            ' *** If cancellation is requested, an OperationCanceledException results.  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Download failed." & vbCrLf  
        End Try  
  
        ' ***Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' ***Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' ***Provide a parameter for the CancellationToken.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task(Of Integer)  
  
        Dim client As HttpClient = New HttpClient()  
  
        resultsTextBox.Text &=  
            String.Format(vbCrLf & "Ready to download." & vbCrLf)  
  
        ' You might need to slow things down to have a chance to cancel.  
        Await Task.Delay(250)  
  
        ' GetAsync returns a Task(Of HttpResponseMessage).   
        ' ***The ct argument carries the message if the Cancel button is chosen.  
        Dim response As HttpResponseMessage = Await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct)  
  
        ' Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' The result of the method is the length of the downloaded website.  
        Return urlContents.Length  
    End Function  
End Class  
  
' Output for a successful download:  
  
' Ready to download.  
  
' Length of the downloaded string: 158125.  
  
' Or, if you cancel:  
  
' Ready to download.  
  
' Download canceled.  
```  
  
### <a name="cancel-a-list-of-tasks-example"></a>Beispiel zum Abbrechen einer Aufgabenliste  
 Der folgende Code ist die vollständige "MainWindow.Xaml.vb"-Datei für das Beispiel, das eine Liste von Aufgaben abgebrochen.  
  
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
            ' ***AccessTheWebAsync returns a Task, not a Task(Of Integer).  
            Await AccessTheWebAsync(cts.Token)  
            '  ***Small change in the display lines.  
            resultsTextBox.Text &= vbCrLf & "Downloads complete."  
  
        Catch ex As OperationCanceledException  
            resultsTextBox.Text &= vbCrLf & "Downloads canceled." & vbCrLf  
  
        Catch ex As Exception  
            resultsTextBox.Text &= vbCrLf & "Downloads failed." & vbCrLf  
        End Try  
  
        ' Set the CancellationTokenSource to Nothing when the download is complete.  
        cts = Nothing  
    End Sub  
  
    ' Add an event handler for the Cancel button.  
    Private Sub cancelButton_Click(sender As Object, e As RoutedEventArgs)  
  
        If cts IsNot Nothing Then  
            cts.Cancel()  
        End If  
    End Sub  
  
    ' Provide a parameter for the CancellationToken.  
    ' ***Change the return type to Task because the method has no return statement.  
    Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
        Dim client As HttpClient = New HttpClient()  
  
        ' ***Call SetUpURLList to make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        ' ***Add a loop to process the list of web addresses.  
        For Each url In urlList  
            ' GetAsync returns a Task(Of HttpResponseMessage).   
            ' Argument ct carries the message if the Cancel button is chosen.   
            ' ***Note that the Cancel button can cancel all remaining downloads.  
            Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
            ' Retrieve the website contents from the HttpResponseMessage.  
            Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
            resultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, urlContents.Length)  
        Next  
    End Function  
  
    ' ***Add a method that creates a list of web addresses.  
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
  
' Output if you do not choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Length of the downloaded string: 158124.  
  
' Length of the downloaded string: 204890.  
  
' Length of the downloaded string: 175488.  
  
' Length of the downloaded string: 145790.  
  
' Downloads complete.  
  
'  Sample output if you choose to cancel:  
  
' Length of the downloaded string: 35939.  
  
' Length of the downloaded string: 237682.  
  
' Length of the downloaded string: 128607.  
  
' Downloads canceled.  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.CancellationTokenSource></xref:System.Threading.CancellationTokenSource>   
 <xref:System.Threading.CancellationToken></xref:System.Threading.CancellationToken>   
 [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)   
 [Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [ASYNC-Beispiel: Feinabstimmung der Anwendung](http://go.microsoft.com/fwlink/?LinkId=255046)
