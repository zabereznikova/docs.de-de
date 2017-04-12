---
title: Des erneuten Eintretens in asynchronen Anwendungen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: ef3dc73d-13fb-4c5f-a686-6b84148bbffe
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 64a708e3b88f48ad30d3f3ad25141a31f3d8f73d
ms.lasthandoff: 03/13/2017

---
# <a name="handling-reentrancy-in-async-apps-visual-basic"></a>Des erneuten Eintretens in asynchronen Anwendungen (Visual Basic)
Wenn Sie asynchronen Code in der App einschließen, sollten Sie erneutes Eintreten, also den erneuten Beginn eines asynchronen Vorgangs vor seinem Abschließen, berücksichtigen und möglicherweise verhindern. Wenn Sie Möglichkeiten für erneutes Eintreten nicht identifizieren und behandeln, kann dies zu unerwarteten Ergebnissen führen.  
  
 **Inhalt**  
  
-   [Erkennen von Reentranz](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [Arbeiten mit Reentranz](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [Deaktivieren Sie die Schaltfläche "Start"](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [Abbrechen und Neustarten des Vorgangs](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
    -   [Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
-   [Überprüfen und Ausführen der Beispiel-App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
> [!NOTE]
>  Zum Ausführen des Beispiels müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.  
  
##  <a name="BKMK_RecognizingReentrancy"></a>Erkennen von Reentranz  
 Wählen Sie im Beispiel in diesem Thema Benutzer eine **Start** Schaltfläche zum Initiieren einer asynchronen app, die eine Reihe von Websites heruntergeladen und berechnet die Gesamtzahl der Bytes, die heruntergeladen werden. Eine synchrone Version des Beispiels würde auf die gleiche Weise reagieren, unabhängig davon, wie oft ein Benutzer die Schaltfläche auswählt, da diese Ereignisse nach dem ersten Mal vom UI-Thread ignoriert werden, bis die Anwendung ausgeführt wurde. In einer asynchronen App reagiert der UI-Thread weiterhin, und Sie können möglicherweise erneut in den asynchronen Vorgang eintreten, bevor er abgeschlossen ist.  
  
 Das folgende Beispiel zeigt die erwartete Ausgabe, wenn der Benutzer die **starten** Schaltfläche nur einmal. Eine Liste der heruntergeladenen Websites wird mit der Größe, in Bytes für jede Site, angezeigt. Die Gesamtanzahl von Bytes wird am Ende angezeigt.  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 Wenn der Benutzer die Schaltfläche allerdings mehrmals auswählt, wird der Ereignishandler wiederholt aufgerufen, und der Downloadvorgang beginnt jedes Mal erneut. Daher werden mehrere asynchrone Vorgänge gleichzeitig ausgeführt, die Ausgabe überlappt mit den Ergebnissen, und die Gesamtzahl der Bytes ist verwirrend.  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/en-us/library/jj155761.aspx                29019  
7. msdn.microsoft.com                                            42972  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
7. msdn.microsoft.com                                            42972  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 Sie können den Code, der diese Ausgabe erzeugt, überprüfen, indem Sie einen Bildlauf zum Ende dieses Themas durchführen. Sie können mit dem Code experimentieren, indem Sie die Lösung auf dem lokalen Computer herunterladen und das WebsiteDownload-Projekt oder mit dem Code am Ende dieses Themas, um Ihr eigenes Projekt Weitere Informationen und Anweisungen zu erstellen, finden Sie unter [überprüfen und Ausführen der Beispiel-App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645).  
  
##  <a name="BKMK_HandlingReentrancy"></a>Arbeiten mit Reentranz  
 Sie können das erneute Eintreten auf verschiedene Weise behandeln, je nachdem, was von der App ausgeführt werden soll. In diesem Thema werden die folgenden Beispiele zur Veranschaulichung verwendet:  
  
-   [Deaktivieren Sie die Schaltfläche "Start"](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     Deaktivieren der **Start** Schaltfläche während der Vorgang ausgeführt wird, sodass der Benutzer ihn nicht unterbrechen kann.  
  
-   [Abbrechen und Neustarten des Vorgangs](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     Abbrechen aller Vorgänge, die noch ausgeführt wird, wenn der Benutzer die **Start** erneut auf die Schaltfläche und anschließend fortfahren, sodass nur der zuletzt angeforderte Vorgang.  
  
-   [Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645)  
  
     Alle angeforderten Vorgänge asynchron ausführen lassen, die Anzeige der Ausgabe allerdings koordinieren, damit die Ergebnisse der einzelnen Vorgänge zusammen und in Reihenfolge angezeigt werden.  
  
###  <a name="BKMK_DisableTheStartButton"></a>Deaktivieren Sie die Schaltfläche "Start"  
 Sie blockieren, können die **starten** Schaltfläche während ein Vorgangs ausgeführt wird, deaktivieren Sie die Schaltfläche am oberen Rand der `StartButton_Click` -Ereignishandler. Sie können die Schaltfläche aus einem `Finally`-Block erneut aktivieren, sobald der Vorgang beendet ist, damit Benutzer die App erneut ausführen können.  
  
 Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt. Sie können die Änderungen am Code am Ende dieses Themas hinzufügen, oder Sie können die fertige app von herunterladen [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571). Der Projektname ist "DisableStartButton".  
  
```vb  
  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' This line is commented out to make the results clearer in the output.  
    'ResultsTextBox.Text = ""  
  
    ' ***Disable the Start button until the downloads are complete.   
    StartButton.IsEnabled = False  
  
    Try  
        Await AccessTheWebAsync()  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    ' ***Enable the Start button in case you want to run the program again.   
    Finally  
        StartButton.IsEnabled = True  
  
    End Try  
End Sub  
```  
  
 Aufgrund der Änderungen reagiert die Schaltfläche nicht, während die Websites von `AccessTheWebAsync` heruntergeladen werden, sodass ein erneutes Eintreten in den Prozess nicht möglich ist.  
  
###  <a name="BKMK_CancelAndRestart"></a>Abbrechen und Neustarten des Vorgangs  
 Anstatt Deaktivieren der **starten** Schaltfläche, Sie können die Schaltfläche aktiv bleiben, wenn der Benutzer die Schaltfläche erneut auswählt, brechen Sie den Vorgang, der bereits ausgeführt und lassen den zuletzt begonnenen Vorgang fortsetzen.  
  
 Weitere Informationen über das Abbrechen finden Sie unter [Optimieren der asynchronen Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md).  
  
 Um dieses Szenario einzurichten, nehmen Sie folgende Änderungen am grundlegenden Code, das im bereitgestellten [überprüfen und Ausführen der Beispiel-App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645). Die fertige app von können auch herunterladen [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571). Der Name dieses Projekts lautet "CancelAndRestart".  
  
1.  Deklarieren Sie eine <xref:System.Threading.CancellationTokenSource>-Variable `cts`, die im Bereich für alle Methoden liegt.</xref:System.Threading.CancellationTokenSource>  
  
    ```vb  
    Class MainWindow // Or Class MainPage  
  
        ' *** Declare a System.Threading.CancellationTokenSource.  
        Dim cts As CancellationTokenSource  
  
    ```  
  
2.  Bestimmen Sie im Element `StartButton_Click`, ob ein Vorgang bereits ausgeführt wird. Wenn der Wert der `cts` ist `Nothing`, kein Vorgang ist bereits aktiv. Wenn der Wert nicht `Nothing`, der Vorgang, der bereits ausgeführt wird, abgebrochen wird.  
  
    ```vb  
    ' *** If a download process is already underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
  
    ```  
  
3.  Legen Sie `cts` auf einen anderen Wert fest, der den aktuellen Prozess darstellt.  
  
    ```vb  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
  
    ```  
  
4.  Am Ende des `StartButton_Click`, der aktuelle Vorgang abgeschlossen ist, so legen Sie den Wert der `cts` an `Nothing`.  
  
    ```vb  
    ' *** When the process completes, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
  
    ```  
  
 Im folgende Code werden alle Änderungen in `StartButton_Click` dargestellt. Die Ergänzungen werden mit Sternchen gekennzeichnet.  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
    ' This line is commented out to make the results clearer.   
    'ResultsTextBox.Text = ""  
  
    ' *** If a download process is underway, cancel it.  
    If cts IsNot Nothing Then  
        cts.Cancel()  
    End If  
  
    ' *** Now set cts to cancel the current process if the button is chosen again.  
    Dim newCTS As CancellationTokenSource = New CancellationTokenSource()  
    cts = newCTS  
  
    Try  
        ' *** Send a token to carry the message if the operation is canceled.  
        Await AccessTheWebAsync(cts.Token)  
  
    Catch ex As OperationCanceledException  
        ResultsTextBox.Text &= vbCrLf & "Download canceled." & vbCrLf  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
    End Try  
  
    ' *** When the process is complete, signal that another process can proceed.  
    If cts Is newCTS Then  
        cts = Nothing  
    End If  
End Sub  
  
```  
  
 Nehmen Sie dazu in `AccessTheWebAsync`die folgenden Änderungen vor.  
  
-   Fügen Sie einen Parameter hinzu, um das Abbruchtoken von `StartButton_Click` zu akzeptieren.  
  
-   Verwenden der <xref:System.Net.Http.HttpClient.GetAsync%2A>-Methode zum Herunterladen der Websites, da `GetAsync` akzeptiert ein <xref:System.Threading.CancellationToken>Argument.</xref:System.Threading.CancellationToken> </xref:System.Net.Http.HttpClient.GetAsync%2A>  
  
-   Bevor Sie `DisplayResults` aufrufen, um die Ergebnisse für jede heruntergeladene Website anzuzeigen, aktivieren Sie `ct`, um sicherzustellen, dass der aktuelle Vorgang nicht abgebrochen wurde.  
  
 Im folgenden Code werden diese Änderungen mit Sternchen gekennzeichnet dargestellt.  
  
```vb  
' *** Provide a parameter for the CancellationToken from StartButton_Click.  
Private Async Function AccessTheWebAsync(ct As CancellationToken) As Task  
  
    ' Declare an HttpClient object.  
    Dim client = New HttpClient()  
  
    ' Make a list of web addresses.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    Dim total = 0  
    Dim position = 0  
  
    For Each url In urlList  
        ' *** Use the HttpClient.GetAsync method because it accepts a   
        ' cancellation token.  
        Dim response As HttpResponseMessage = Await client.GetAsync(url, ct)  
  
        ' *** Retrieve the website contents from the HttpResponseMessage.  
        Dim urlContents As Byte() = Await response.Content.ReadAsByteArrayAsync()  
  
        ' *** Check for cancellations before displaying information about the   
        ' latest site.   
        ct.ThrowIfCancellationRequested()  
  
        position += 1  
        DisplayResults(url, urlContents, position)  
  
        ' Update the total.  
        total += urlContents.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
  
```  
  
 Bei Auswahl der **Start** mehrmals die Schaltfläche während diese app ausgeführt wird, es sollten Ergebnisse erzeugen, die der folgenden Ausgabe ähneln.  
  
```  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               122505  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
Download canceled.  
  
1. msdn.microsoft.com/library/hh191443.aspx                83732  
2. msdn.microsoft.com/library/aa578028.aspx               205273  
3. msdn.microsoft.com/library/jj155761.aspx                29019  
4. msdn.microsoft.com/library/hh290140.aspx               117152  
5. msdn.microsoft.com/library/hh524395.aspx                68959  
6. msdn.microsoft.com/library/ms404677.aspx               197325  
7. msdn.microsoft.com                                            42972  
8. msdn.microsoft.com/library/ff730837.aspx               146159  
  
TOTAL bytes returned:  890591  
```  
  
 Zum Ausschließen der Teillisten entfernen Sie die Kommentarmarkierungen der ersten Codezeile in `StartButton_Click`, um das Textfeld bei jedem erneuten Start des Vorgangs zu löschen.  
  
###  <a name="BKMK_RunMultipleOperations"></a>Mehrere Vorgänge ausführen und die Ausgabe in eine Warteschlange  
 Das dritte Beispiel ist das schwierigste, dass die app ein anderer asynchronen Vorgang jedes Mal gestartet wird, die der Benutzer wählt die **Start** Schaltfläche, und alle Vorgänge, die bis zum Abschluss ausgeführt. Alle angeforderten Vorgänge laden Websites asynchron aus der Liste herunter, doch die Ausgabe der Vorgänge wird sequenziell dargestellt. D. h. die tatsächliche downloadaktivität, wie die Ausgabe in [Erkennen von Reentranz](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) zeigt jedoch die Liste der Ergebnisse für jede Gruppe getrennt angezeigt.  
  
 Die Vorgänge geben global <xref:System.Threading.Tasks.Task>, `pendingWork`, der als Gatekeeper für den anzeigenprozess dient.</xref:System.Threading.Tasks.Task>  
  
 Sie können dieses Beispiel ausführen, durch Einfügen die Änderungen in den Code in [Erstellen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder befolgen Sie die Anweisungen in [Herunterladen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) , laden Sie das Beispiel, und führen Sie dann das QueueResults-Projekt.  
  
 Die folgende Ausgabe zeigt dem Ergebnis, wenn der Benutzer die **Start** Schaltfläche nur einmal. Die buchstabenbezeichnung A gibt an, dass das Ergebnis von der ersten der **Start** Schaltfläche ausgewählt wird. Die Zahlen geben die Reihenfolge der URL in der Liste der Downloadziele wieder.  
  
```  
  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               209858  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
A-7. msdn.microsoft.com                                            53266  
A-8. msdn.microsoft.com/library/ff730837.aspx               148020  
  
TOTAL bytes returned:  918876  
  
#Group A is complete.  
```  
  
 Wenn der Benutzer die **Start** Schaltfläche dreimal, erzeugt die app eine Ausgabe, die die folgenden Zeilen ähnelt. Die Informationszeilen, die mit einem Nummernzeichen (#) beginnen, verfolgen den Status der Anwendung.  
  
```  
#Starting group A.  
#Task assigned for group A.  
  
A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
A-4. msdn.microsoft.com/library/hh290140.aspx               119027  
A-5. msdn.microsoft.com/library/hh524395.aspx                71259  
A-6. msdn.microsoft.com/library/ms404677.aspx               199185  
  
#Starting group B.  
#Task assigned for group B.  
  
A-7. msdn.microsoft.com                                            53266  
  
#Starting group C.  
#Task assigned for group C.  
  
A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916095  
  
B-1. msdn.microsoft.com/library/hh191443.aspx                87389  
B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
  
#Group A is complete.  
  
B-7. msdn.microsoft.com                                            53266  
B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  916097  
  
C-1. msdn.microsoft.com/library/hh191443.aspx                87389  
C-2. msdn.microsoft.com/library/aa578028.aspx               207089  
  
#Group B is complete.  
  
C-3. msdn.microsoft.com/library/jj155761.aspx                30870  
C-4. msdn.microsoft.com/library/hh290140.aspx               119027  
C-5. msdn.microsoft.com/library/hh524395.aspx                72765  
C-6. msdn.microsoft.com/library/ms404677.aspx               199186  
C-7. msdn.microsoft.com                                            56190  
C-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
TOTAL bytes returned:  920526  
  
#Group C is complete.  
  
```  
  
 Die Gruppen B und C starten, bevor Gruppe A beendet ist, doch die Ausgabe für jede Gruppe wird getrennt angezeigt. Die gesamte Ausgabe für Gruppe A wird zuerst angezeigt, gefolgt von der gesamten Ausgabe für Gruppe B und dann die gesamte Ausgabe für Gruppe C. Die app immer zeigt die Gruppen in der Reihenfolge und, für jede Gruppe, die Informationen zu den einzelnen Websites in der angegebenen Reihenfolge an, die URLs in der Liste der URLs immer angezeigt.  
  
 Sie können die Reihenfolge, in der die Downloads tatsächlich vorkommen, allerdings nicht vorhersagen. Nachdem mehrere Gruppen gestartet wurden, sind alle von ihnen generierten Downloadtasks aktiv. Sie können nicht davon ausgehen, dass A-1 vor B-1 heruntergeladen wird, und Sie können auch nicht davon ausgehen, dass A-1 vor A-2 heruntergeladen wird.  
  
#### <a name="global-definitions"></a>Globale Definitionen  
 Im Beispielcode sind die folgenden zwei globalen Deklarationen enthalten, die von allen Methoden sichtbar sind.  
  
```vb  
Class MainWindow    ' Class MainPage in Windows Store app.  
  
    ' ***Declare the following variables where all methods can access them.   
    Private pendingWork As Task = Nothing  
    Private group As Char = ChrW(AscW("A") - 1)  
```  
  
 Mit der `Task`-Variable `pendingWork` wird der Anzeigenprozess beaufsichtigt, und es wird verhindert, dass der Anzeigevorgang einer Gruppe zur Unterbrechung des Anzeigevorgangs einer anderen Gruppe führt. Die Zeichenvariable `group` bezeichnet die Ausgabe von unterschiedlichen Gruppen, um sicherzustellen, dass Ergebnisse in der erwarteten Reihenfolge angezeigt werden.  
  
#### <a name="the-click-event-handler"></a>Der Click-Ereignishandler  
 Der Ereignishandler `StartButton_Click`, erhöht den Buchstaben der Gruppe Jede Betätigung der **Start** Schaltfläche. Anschließend ruft der Handler zum Ausführen des Downloadingvorgangs das Element `AccessTheWebAsync` auf.  
  
```vb  
Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
    ' ***Verify that each group's results are displayed together, and that  
    ' the groups display in order, by marking each group with a letter.  
    group = ChrW(AscW(group) + 1)  
    ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Starting group {0}.", group)  
  
    Try  
        ' *** Pass the group value to AccessTheWebAsync.  
        Dim finishedGroup As Char = Await AccessTheWebAsync(group)  
  
        ' The following line verifies a successful return from the download and   
        ' display procedures.   
        ResultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "#Group {0} is complete." & vbCrLf, finishedGroup)  
  
    Catch ex As Exception  
        ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
    End Try  
End Sub  
```  
  
#### <a name="the-accessthewebasync-method"></a>Die AccessTheWebAsync-Methode  
 In diesem Beispiel wird `AccessTheWebAsync` in zwei Methoden aufgeteilt. Mit der erste Methode, `AccessTheWebAsync`, werden alle Downloadtasks für eine Gruppe gestartet und `pendingWork` wird zum Steuern des Anzeigenprozesses festgelegt. Die Methode verwendet eine Language Integrated Query (LINQ-Abfrage) und <xref:System.Linq.Enumerable.ToArray%2A>aller Downloadtasks zur selben Zeit gestartet.</xref:System.Linq.Enumerable.ToArray%2A>  
  
 `AccessTheWebAsync` ruft dann `FinishOneGroupAsync` auf, um den Abschluss jedes einzelnen Downloads zu erwarten und die Länge anzuzeigen.  
  
 `FinishOneGroupAsync` gibt einen Task zurück, der in `pendingWork` dem Element `AccessTheWebAsync` zugewiesen wird. Dieser Wert verhindert die Unterbrechung durch einen anderen Vorgang, bevor die Aufgabe abgeschlossen wurde.  
  
```vb  
Private Async Function AccessTheWebAsync(grp As Char) As Task(Of Char)  
  
    Dim client = New HttpClient()  
  
    ' Make a list of the web addresses to download.  
    Dim urlList As List(Of String) = SetUpURLList()  
  
    ' ***Kick off the downloads. The application of ToArray activates all the download tasks.  
    Dim getContentTasks As Task(Of Byte())() =  
        urlList.Select(Function(addr) client.GetByteArrayAsync(addr)).ToArray()  
  
    ' ***Call the method that awaits the downloads and displays the results.  
    ' Assign the Task that FinishOneGroupAsync returns to the gatekeeper task, pendingWork.  
    pendingWork = FinishOneGroupAsync(urlList, getContentTasks, grp)  
  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & "#Task assigned for group {0}. Download tasks are active." & vbCrLf, grp)  
  
    ' ***This task is complete when a group has finished downloading and displaying.  
    Await pendingWork  
  
    ' You can do other work here or just return.  
    Return grp  
End Function  
```  
  
#### <a name="the-finishonegroupasync-method"></a>Die FinishOneGroupAsync-Methode  
 Diese Methode durchläuft die Downloadaufgaben in einer Gruppe, erwartet dabei jeden einzelnen Task, zeigt die Länge der heruntergeladenen Website an und addiert diese Länge zur Summe.  
  
 Die erste Anweisung im `FinishOneGroupAsync` verwendet `pendingWork` sicherstellen, dass die Eingabe der Methode keine stört mit einem Vorgang, der sich bereits im Anzeige- oder im ist. Wenn ein solcher Vorgang ausgeführt wird, wird der eintretende Vorgang solange aufgeschoben, bis er an der Reihe ist.  
  
```vb  
Private Async Function FinishOneGroupAsync(urls As List(Of String), contentTasks As Task(Of Byte())(), grp As Char) As Task  
  
    ' Wait for the previous group to finish displaying results.  
    If pendingWork IsNot Nothing Then  
        Await pendingWork  
    End If  
  
    Dim total = 0  
  
    ' contentTasks is the array of Tasks that was created in AccessTheWebAsync.  
    For i As Integer = 0 To contentTasks.Length - 1  
        ' Await the download of a particular URL, and then display the URL and  
        ' its length.  
        Dim content As Byte() = Await contentTasks(i)  
        DisplayResults(urls(i), content, i, grp)  
        total += content.Length  
    Next  
  
    ' Display the total count for all of the websites.  
    ResultsTextBox.Text &=  
        String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
End Function  
```  
  
 Sie können dieses Beispiel ausführen, durch Einfügen die Änderungen in den Code in [Erstellen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder befolgen Sie die Anweisungen in [Herunterladen der App](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) , laden Sie das Beispiel, und führen Sie dann das QueueResults-Projekt.  
  
#### <a name="points-of-interest"></a>Relevante Punkte  
 Die Informationszeilen, die mit einem Nummernzeichen (#) in der Ausgabe beginnen, erläutern die Funktionsweise dieses Beispiels.  
  
 Die Ausgabe zeigt die folgenden Muster an.  
  
-   Eine Gruppe kann gestartet werden, während die Ausgabe einer vorherigen Gruppe angezeigt wird. Doch die Anzeige der Ausgabe der vorherigen Gruppe wird nicht unterbrochen.  
  
    ```  
    #Starting group A.  
    #Task assigned for group A. Download tasks are active.  
  
    A-1. msdn.microsoft.com/library/hh191443.aspx                87389  
    A-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    A-3. msdn.microsoft.com/library/jj155761.aspx                30870  
    A-4. msdn.microsoft.com/library/hh290140.aspx               119037  
    A-5. msdn.microsoft.com/library/hh524395.aspx                71260  
  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
  
    A-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    A-7. msdn.microsoft.com                                            53078  
    A-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915919  
  
    B-1. msdn.microsoft.com/library/hh191443.aspx                87388  
    B-2. msdn.microsoft.com/library/aa578028.aspx               207089  
    B-3. msdn.microsoft.com/library/jj155761.aspx                30870  
  
    #Group A is complete.  
  
    B-4. msdn.microsoft.com/library/hh290140.aspx               119027  
    B-5. msdn.microsoft.com/library/hh524395.aspx                71260  
    B-6. msdn.microsoft.com/library/ms404677.aspx               199186  
    B-7. msdn.microsoft.com                                            53078  
    B-8. msdn.microsoft.com/library/ff730837.aspx               148010  
  
    TOTAL bytes returned:  915908  
    ```  
  
-   Die `pendingWork` Aufgabe `Nothing` zu Beginn der `FinishOneGroupAsync` nur für Gruppe A, die zuerst gestartet. Gruppe A hat bei Erreichen von `FinishOneGroupAsync` einen Erwartungsausdruck noch nicht abgeschlossen. Daher wurde die Steuerung nicht an `AccessTheWebAsync` zurückgegeben, und die erste Zuweisung zu `pendingWork` ist nicht aufgetreten.  
  
-   Die folgenden zwei Zeilen werden immer zusammen in der Ausgabe angezeigt. Der Code wird zwischen dem Starten des Vorgangs einer Gruppe in `StartButton_Click` und dem Zuweisen eines Tasks für die Gruppe zu `pendingWork` nie unterbrochen.  
  
    ```  
    #Starting group B.  
    #Task assigned for group B. Download tasks are active.  
    ```  
  
     Nachdem eine Gruppe in `StartButton_Click` eintritt, schließt der Vorgang einen Erwartungsausdruck erst ab, wenn der Vorgang in `FinishOneGroupAsync` eintritt. Daher kann kein weiterer Vorgang während dieses Codeabschnitts die Steuerung übernehmen.  
  
##  <a name="BKMD_SettingUpTheExample"></a>Überprüfen und Ausführen der Beispiel-App  
 Zum besseren Verständnis der Beispiel-App können Sie sie herunterladen, sie selbst erstellen oder den Code am Ende dieses Themas überprüfen, ohne die App zu implementieren.  
  
> [!NOTE]
>  Zum Ausführen des Beispiels als eine Windows Presentation Foundation (WPF)-desktop-app müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.  
  
###  <a name="BKMK_DownloadingTheApp"></a>Herunterladen der App  
  
1.  Laden Sie die komprimierte Datei von [asynchrone Beispiele: Erneutes eintreten bei .NET-Desktop-Apps](http://go.microsoft.com/fwlink/?LinkId=266571).  
  
2.  Dekomprimieren Sie die heruntergeladene Datei, und starten Sie dann Visual Studio.  
  
3.  Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.  
  
4.  Navigieren Sie zu dem Ordner mit dem dekomprimierten Beispielcode, und öffnen Sie die Projektmappendatei (SLN-Datei).  
  
5.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für das Projekt, die Sie verwenden möchten, führen Sie aus, und wählen Sie dann **Set as StartUpProject**.  
  
6.  Drücken Sie zum Erstellen und Ausführen des Projekts die Tastenkombination "STRG+F5".  
  
###  <a name="BKMK_BuildingTheApp"></a>Erstellen der App  
 Der folgende Abschnitt enthält den Code, um das Beispiel als WPF-app zu erstellen.  
  
##### <a name="to-build-a-wpf-app"></a>So erstellen Sie eine WPF-App  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **installierte Vorlagen** Bereich, erweitern Sie **Visual Basic**, und erweitern Sie dann **Windows**.  
  
4.  Wählen Sie in der Liste der Projekttypen, **WPF-Anwendung**.  
  
5.  Nennen Sie das Projekt `WebsiteDownloadWPF`, und wählen Sie dann die **OK** Schaltfläche.  
  
     Das neue Projekt wird im **Projektmappen-Explorer**.  
  
6.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
     Wenn die Registerkarte nicht angezeigt wird, öffnen Sie das Kontextmenü für "MainWindow.xaml" im **Projektmappen-Explorer**, und wählen Sie dann **Anzeigecode**.  
  
7.  In der **XAML** Anzeigen von "MainWindow.xaml", ersetzen Sie den Code durch den folgenden Code.  
  
    ```vb  
    <Window x:Class="MainWindow"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:local="using:WebsiteDownloadWPF"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        mc:Ignorable="d">  
  
        <Grid Width="517" Height="360">  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="-1,0,0,0" VerticalAlignment="Top" Click="StartButton_Click" Height="53" Background="#FFA89B9B" FontSize="36" Width="518"  />  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" Margin="-1,53,0,-36" TextWrapping="Wrap" VerticalAlignment="Top" Height="343" FontSize="10" ScrollViewer.VerticalScrollBarVisibility="Visible" Width="518" FontFamily="Lucida Console" />  
        </Grid>  
    </Window>  
    ```  
  
     Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird angezeigt, der **Design** Ansicht von "MainWindow.xaml".  
  
8.  Fügen Sie einen Verweis für <xref:System.Net.Http>.</xref:System.Net.Http>  
  
9. In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Anzeigecode**.  
  
10. Ersetzen Sie in "MainWindow.Xaml.vb" den Code durch den folgenden Code ein.  
  
    ```vb  
    ' Add the following Imports statements, and add a reference for System.Net.Http.  
    Imports System.Net.Http  
    Imports System.Threading  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
            ' This line is commented out to make the results clearer in the output.  
            'ResultsTextBox.Text = ""  
  
            Try  
                Await AccessTheWebAsync()  
  
            Catch ex As Exception  
                ResultsTextBox.Text &= vbCrLf & "Downloads failed."  
  
            End Try  
        End Sub  
  
        Private Async Function AccessTheWebAsync() As Task  
  
            ' Declare an HttpClient object.  
            Dim client = New HttpClient()  
  
            ' Make a list of web addresses.  
            Dim urlList As List(Of String) = SetUpURLList()  
  
            Dim total = 0  
            Dim position = 0  
  
            For Each url In urlList  
                ' GetByteArrayAsync returns a task. At completion, the task  
                ' produces a byte array.  
                Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
                position += 1  
                DisplayResults(url, urlContents, position)  
  
                ' Update the total.  
                total += urlContents.Length  
            Next  
  
            ' Display the total count for all of the websites.  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & vbCrLf & "TOTAL bytes returned:  " & total & vbCrLf)  
        End Function  
  
        Private Function SetUpURLList() As List(Of String)  
            Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/hh191443.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/jj155761.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/hh524395.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
            Return urls  
        End Function  
  
        Private Sub DisplayResults(url As String, content As Byte(), pos As Integer)  
            ' Display the length of each website. The string format is designed  
            ' to be used with a monospaced font, such as Lucida Console or  
            ' Global Monospace.  
  
            ' Strip off the "http:'".  
            Dim displayURL = url.Replace("http://", "")  
            ' Display position in the URL list, the URL, and the number of bytes.  
            ResultsTextBox.Text &= String.Format(vbCrLf & "{0}. {1,-58} {2,8}", pos, displayURL, content.Length)  
        End Sub  
    End Class  
    ```  
  
11. Drücken Sie STRG + F5, um das Programm auszuführen, und wählen Sie dann die **Start** mehrmals die Schaltfläche.  
  
12. Ändern von [deaktivieren Sie die Schaltfläche "Start"](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), [Abbrechen und Neustarten des Vorgangs](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645), oder [mehrere Vorgänge ausführen und die Ausgabe-Warteschlange](http://msdn.microsoft.com/library/5b54de66-6be3-459e-b869-65070b020645) erneutem verarbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
