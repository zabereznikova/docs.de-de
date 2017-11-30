---
title: 'Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 84fd047f-fab8-4d89-8ced-104fb7310a91
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de1219de72be5ddc022d898c904663bf92ca5ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-accessing-the-web-by-using-async-and-await-visual-basic"></a>Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await ( Visual Basic)
Sie können asynchrone Programme mit den Funktionen „Async/Await“ einfacher und intuitiver schreiben. Sie können asynchronen Code schreiben, der wie synchroner Code aussieht und veranlassen, dass der Compiler die komplizierten Rückruffunktionen und Fortsetzungen verarbeitet, die durch den asynchronen Code für gewöhnlich verursacht werden.  
  
 Weitere Informationen über das Feature Async finden Sie unter [asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Diese exemplarische Vorgehensweise beginnt mit einer synchronen WPF-Anwendung (Windows Presentation Foundation), die die Anzahl der Bytes in einer Liste von Websites summiert. In der exemplarischen Vorgehensweise wird die Anwendung dann mithilfe der neuen Funktionen in eine asynchrone Lösung umgewandelt.  
  
 Wenn Sie die Anwendungen nicht selbst erstellen möchten, können Sie das „Thema mit einem asynchronen Beispiel für die exemplarische Vorgehensweise für den Internetzugriff (C# und Visual Basic)“ in englischer Sprache über [Entwickler-Codebeispiele](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   [So erstellen Sie eine WPF-Anwendung](#CreateWPFApp)  
  
-   [So entwerfen Sie ein einfaches WPF-MainWindow](#MainWindow)  
  
-   [So fügen Sie einen Verweis hinzu](#AddRef)  
  
-   [So fügen Sie erforderliche Imports-Anweisungen hinzu](#ImportsState)  
  
-   [So erstellen Sie eine synchrone Anwendung](#synchronous)  
  
-   [So testen Sie die synchrone Lösung](#testSynch)  
  
-   [So konvertieren Sie „GetURLContents“ in eine asynchrone Methode](#GetURLContents)  
  
-   [So konvertieren Sie „SumPageSizes“ in eine asynchrone Methode](#SumPageSizes)  
  
-   [So konvertieren Sie „startButton_Click“ in eine asynchrone Methode](#startButton)  
  
-   [So testen Sie die asynchrone Lösung](#testAsynch)  
  
-   [So ersetzen Sie die Methode „GetURLContentsAsync“ durch eine .NET Framework-Methode](#GetURLContentsAsync)  
  
-   [Beispiel](#BKMK_CompleteCodeExamples)  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Visual Studio 2012 oder höher muss auf dem Computer installiert sein. Weitere Informationen finden Sie auf der [Microsoft-Website](http://go.microsoft.com/fwlink/?LinkId=235233).  
  
###  <a name="CreateWPFApp"></a> So erstellen Sie eine WPF-Anwendung  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **installierte Vorlagen** Bereich Visual Basic auswählen, und wählen Sie dann **WPF-Anwendung** aus der Liste der Projekttypen zur Verfügung.  
  
4.  Geben Sie im Textfeld **Name** `AsyncExampleWPF` ein, und wählen Sie dann die Schaltfläche **OK** aus.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
##  <a name="BKMK_DesignWPFMainWin"></a>   
###  <a name="MainWindow"></a> So entwerfen Sie ein einfaches WPF-MainWindow  
  
1.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
2.  Wenn das Fenster **Toolbox** nicht sichtbar ist, öffnen Sie das Menü **Ansicht**, und wählen Sie dann **Toolbox** aus.  
  
3.  Fügen Sie dem Fenster **MainWindow** ein **Button**-Steuerelement und ein **TextBox**-Steuerelement hinzu.  
  
4.  Markieren Sie das **TextBox**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:  
  
    -   Legen Sie die Eigenschaft **Name** auf `resultsTextBox` fest.  
  
    -   Legen Sie die Eigenschaft **Height** auf „250“ fest.  
  
    -   Legen Sie die Eigenschaft **Width** auf „500“ fest.  
  
    -   Geben Sie auf der Registerkarte **Text** eine Festbreitenschriftart wie Lucida Console oder Global Monospace an.  
  
5.  Markieren Sie das **Button**-Steuerelement, und legen Sie im Fenster **Eigenschaften** die folgenden Werte fest:  
  
    -   Legen Sie die Eigenschaft **Name** auf `startButton` fest.  
  
    -   Ändern Sie den Wert der Eigenschaft **Content** von **Button** zu **Start**.  
  
6.  Positionieren Sie das Textfeld und die Schaltfläche so, dass beide im Fenster **MainWindow** angezeigt werden.  
  
     Weitere Informationen über den WPF-XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).  
  
##  <a name="BKMK_AddReference"></a>   
###  <a name="AddRef"></a> So fügen Sie einen Verweis hinzu  
  
1.  Markieren Sie im **Projektmappen-Explorer** den Namen des Projekts.  
  
2.  Wählen Sie in der Menüleiste die Optionen **Projekt** und **Verweis hinzufügen** aus.  
  
     Das Dialogfeld **Verweis-Manager** wird angezeigt.  
  
3.  Stellen Sie oben im Dialogfeld sicher, dass Ihr Projekt auf .NET Framework 4.5 oder höher abzielt.  
  
4.  Wählen Sie im Bereich **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.  
  
5.  Aktivieren Sie in der Liste der Namen das Kontrollkästchen **System.Net.Http**.  
  
6.  Wählen Sie die Schaltfläche **OK** aus, um das Dialogfeld zu schließen.  
  
##  <a name="BKMK_AddStatesandDirs"></a>   
###  <a name="ImportsState"></a>So fügen Sie erforderliche Imports-Anweisungen hinzu  
  
1.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Code anzeigen**.  
  
2.  Fügen Sie die folgenden `Imports` Anweisungen am Anfang der Codedatei ein, wenn sie nicht bereits vorhanden sind.  
  
    ```vb  
    Imports System.Net.Http  
    Imports System.Net  
    Imports System.IO  
    ```  
  
##  <a name="BKMK_CreatSynchApp"></a>   
###  <a name="synchronous"></a> So erstellen Sie eine synchrone Anwendung  
  
1.  Doppelklicken Sie im Entwurfsfenster "MainWindow.xaml", auf die **starten** Schaltfläche zum Erstellen der `startButton_Click` -Ereignishandler in "MainWindow.Xaml.vb".  
  
2.  In "MainWindow.Xaml.vb", kopieren Sie den folgenden Code in den Text der `startButton_Click`:  
  
    ```vb  
    resultsTextBox.Clear()  
    SumPageSizes()  
    resultsTextBox.Text &= vbCrLf & "Control returned to startButton_Click."  
    ```  
  
     Der Code ruft die Methode `SumPageSizes` auf, die die Anwendung steuert und zeigt eine Meldung an, wenn das Steuerelement zu `startButton_Click` zurückgegeben wird.  
  
3.  Der Code für die synchrone Lösung enthält die folgenden vier Methoden:  
  
    -   `SumPageSizes`. Enthält eine Liste von Webseiten-URLs aus `SetUpURLList` und ruft dann `GetURLContents` und `DisplayResults` auf, um jede URL zu verarbeiten.  
  
    -   `SetUpURLList`. Erstellt und gibt eine Liste der Webadressen zurück.  
  
    -   `GetURLContents`. Lädt Inhalte jeder Website herunter und gibt die Inhalte als ein Bytearray zurück.  
  
    -   `DisplayResults`. Zeigt die Anzahl der Bytes im Bytearray für jede URL an.  
  
     Kopieren Sie die folgenden vier Methoden, und fügen Sie sie in der `startButton_Click` -Ereignishandler in "MainWindow.Xaml.vb":  
  
    ```vb  
    Private Sub SumPageSizes()  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetURLContents returns the contents of url as a byte array.  
            Dim urlContents As Byte() = GetURLContents(url)  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the web addresses.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf & "Total bytes returned:  {0}" & vbCrLf, total)  
    End Sub  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Function GetURLContents(url As String) As Byte()  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        ' Note: you can't use HttpWebRequest.GetResponse in a Windows Store app.  
        Using response As WebResponse = webReq.GetResponse()  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                responseStream.CopyTo(content)  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
##  <a name="BKMK_TestSynchSol"></a>   
###  <a name="testSynch"></a> So testen Sie die synchrone Lösung  
  
1.  Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
     Die Ausgabe sollte der folgenden Liste gleichen.  
  
    ```  
    msdn.microsoft.com/library/windows/apps/br211380.aspx        383832  
    msdn.microsoft.com                                            33964  
    msdn.microsoft.com/library/hh290136.aspx               225793  
    msdn.microsoft.com/library/ee256749.aspx               143577  
    msdn.microsoft.com/library/hh290138.aspx               237372  
    msdn.microsoft.com/library/hh290140.aspx               128279  
    msdn.microsoft.com/library/dd470362.aspx               157649  
    msdn.microsoft.com/library/aa578028.aspx               204457  
    msdn.microsoft.com/library/ms404677.aspx               176405  
    msdn.microsoft.com/library/ff730837.aspx               143474  
  
    Total bytes returned:  1834802  
  
    Control returned to startButton_Click.  
    ```  
  
     Beachten Sie, dass es ein paar Sekunden dauert, bis die Zahlen angezeigt werden. Während dieser Zeit ist der Benutzeroberflächenthread blockiert, während auf das Herunterladen von angeforderten Ressourcen gewartet wird. Daher können Sie das Anzeigefenster weder verschieben, maximieren, minimieren noch schließen, nachdem Sie die Schaltfläche **Start** ausgewählt haben. Diese Bemühungen sind nicht erfolgreich, bis der Bytezähler angezeigt wird. Wenn eine Website nicht antwortet, erhalten Sie keinen Hinweis darüber, welche Site fehlerhaft ist. Es ist sogar schwierig, mit dem Warten aufzuhören und das Programm zu schließen.  
  
##  <a name="BKMK_ConvertGtBtArr"></a>   
###  <a name="GetURLContents"></a> So konvertieren Sie „GetURLContents“ in eine asynchrone Methode  
  
1.  Für das Konvertieren der synchronen Projektmappe in eine asynchrone Projektmappe empfiehlt es sich, in `GetURLContents` zu beginnen, da die Aufrufe der <xref:System.Net.HttpWebRequest>-Methode <xref:System.Net.HttpWebRequest.GetResponse%2A> und der <xref:System.IO.Stream>-Methode <xref:System.IO.Stream.CopyTo%2A> dort erfolgen, wo die Anwendung auf das Web zugreift. .NET Framework erleichtert die Konvertierung, indem asynchrone Versionen beider Methoden bereitgestellt werden.  
  
     Weitere Informationen über die in `GetURLContents` verwendeten Methoden finden Sie unter <xref:System.Net.WebRequest>.  
  
    > [!NOTE]
    >  Beim Befolgen der Schritte in dieser exemplarischen Vorgehensweise treten verschiedene Compilerfehler auf. Sie können diese ignorieren und mit der exemplarischen Vorgehensweise fortfahren.  
  
     Ändern Sie die Methode, die aufgerufen wird, in der dritten Zeile von `GetURLContents` von `GetResponse` zur asynchronen, aufgabenbasierten <xref:System.Net.WebRequest.GetResponseAsync%2A>-Methode.  
  
    ```vb  
    Using response As WebResponse = webReq.GetResponseAsync()  
    ```  
  
2.  `GetResponseAsync` gibt einen Wert vom Typ <xref:System.Threading.Tasks.Task%601> zurück. In diesem Fall weist die *Aufgabenrückgabevariable*, `TResult`, den Typ <xref:System.Net.WebResponse> auf. Mit dieser Aufgabe soll ein tatsächliches `WebResponse`-Objekt erstellt werden, nachdem die angeforderten Daten heruntergeladen und das Ausführen der Aufgabe abgeschlossen wurde.  
  
     Zum Abrufen der `WebResponse` aus der Aufgabe, Anwenden einer ["await"](../../../../visual-basic/language-reference/operators/await-operator.md) Operator, um den Aufruf von `GetResponseAsync`, wie der folgende Code zeigt.  
  
    ```vb  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
    ```  
  
     Der `Await`-Operator hält die Ausführung der aktuellen Methode `GetURLContents` an, bis die Aufgabe abgeschlossen ist. In der Zwischenzeit kehrt die Steuerung zum Aufrufer der aktuellen Methode zurück. In diesem Beispiel lautet die aktuelle Methode `GetURLContents`, und der Aufrufer ist `SumPageSizes`. Wenn die Aufgabe abgeschlossen ist, wird das zugesicherte `WebResponse`-Objekt als Wert der erwarteten Aufgabe erstellt und zur Variable `response` zugewiesen.  
  
     Die vorherige Anweisung kann in die folgenden zwei Anweisungen getrennt werden, um zu verdeutlichen, was geschieht.  
  
    ```vb  
    'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
    'Using response As WebResponse = Await responseTask  
    ```  
  
     Durch den Aufruf von `webReq.GetResponseAsync` wird `Task(Of WebResponse)` oder `Task<WebResponse>` zurückgegeben. Ein `Await` Operator angewendet wird, für den Task zum Abrufen der `WebResponse` Wert.  
  
     Wenn Ihre asynchrone Methode Aktionen vornehmen muss, die nicht von der Fertigstellung der Aufgabe abhängen, kann die Methode diese Aktionen zwischen zwei Anweisungen fortsetzen, und zwar nach dem Aufruf der asynchronen Methode und vor dem Anwenden des await-Operators. Beispiele finden Sie unter [Vorgehensweise: Erstellen mehrerer Webanforderungen durch Verwenden von Async und Await (Visual Basic) parallel](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) und [wie: Erweitern der asynchronen Walkthrough mithilfe von "Task.WhenAll" (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).  
  
3.  Da Sie den Operator `Await` im vorherigen Schritt hinzugefügt haben, tritt ein Compilerfehler auf. Der Operator kann verwendet werden, nur in Methoden, die mit markiert sind die [Async](../../../../visual-basic/language-reference/modifiers/async.md) Modifizierer. Ignorieren Sie den Fehler, während Sie die Konvertierungsschritte zum Ersetzen des Aufrufs von `CopyTo` mit einem Aufruf von `CopyToAsync` wiederholen.  
  
    -   Ändern Sie den Namen der Methode, die für <xref:System.IO.Stream.CopyToAsync%2A> aufgerufen wird.  
  
    -   Die Methode `CopyTo` oder `CopyToAsync` kopiert Bytes zu ihrem Argument `content` und gibt keinen sinnvollen Wert zurück. In der synchronen Version ist der Aufruf von `CopyTo` eine einfache Anweisung, die keinen Wert zurückgibt. Die asynchrone Version `CopyToAsync` gibt ein <xref:System.Threading.Tasks.Task> zurück. Die Aufgabe funktioniert wie „Task(void)“ und ermöglicht, dass auf die Methode gewartet wird. Wenden Sie `Await` oder `await` auf den Aufruf von `CopyToAsync` an, wie dies im folgenden Code gezeigt wird.  
  
        ```vb  
        Await responseStream.CopyToAsync(content)  
        ```  
  
         Die vorherige Anweisung kürzt die folgenden zwei Codezeilen.  
  
        ```vb  
        ' CopyToAsync returns a Task, not a Task<T>.  
        'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
        ' When copyTask is completed, content contains a copy of  
        ' responseStream.  
        'Await copyTask  
        ```  
  
4.  Somit muss nur noch die Methodensignatur in `GetURLContents` angepasst werden. Können Sie die `Await` Operator nur in Methoden, die mit markiert sind die [Async](../../../../visual-basic/language-reference/modifiers/async.md) Modifizierer. Fügen Sie den Modifizierer hinzu, um die Methode als eine *async*-Methode zu markieren, wie im folgenden Code gezeigt wird.  
  
    ```vb  
    Private Async Function GetURLContents(url As String) As Byte()  
    ```  
  
5.  Der Rückgabetyp einer Async-Methode kann nur <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>. In Visual Basic muss die Methode eine `Function` sein, die eine `Task` oder eine `Task(Of T)` zurückgibt, oder die Methode muss ein `Sub` sein. In der Regel eine `Sub` Methode ist nur in einem asynchronen Ereignishandler verwendet, in denen `Sub` ist erforderlich. In anderen Fällen verwenden Sie `Task(T)` , wenn die abgeschlossene Methode eine [zurückgeben](../../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung, die einen Wert zurückgibt Typ T, und Sie `Task` , wenn die abgeschlossene Methode keinen sinnvollen Wert zurückgibt.  
  
     Weitere Informationen finden Sie unter [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
     Die Methode `GetURLContents` verfügt über eine return-Anweisung, und die Anweisung gibt ein Bytearray zurück. Daher ist der Rückgabetyp der der asynchronen Version „Task(T)“, wobei „T“ ein Bytearray ist. Nehmen Sie folgende Änderungen in der Methodensignatur vor:  
  
    -   Ändern Sie den Rückgabetyp zu `Task(Of Byte())`.  
  
    -   Asynchrone Methoden verfügen gemäß der Konvention über Namen, die auf „Async“ enden. Benennen Sie also die Methode `GetURLContentsAsync` um.  
  
     Im folgenden Code sind diese Änderungen dargestellt.  
  
    ```vb  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
    ```  
  
     Mit diesen wenigen Änderungen ist die Konvertierung von `GetURLContents` zu einer asynchronen Methode abgeschlossen.  
  
##  <a name="BKMK_ConvertSumPagSzs"></a>   
###  <a name="SumPageSizes"></a> So konvertieren Sie „SumPageSizes“ in eine asynchrone Methode  
  
1.  Wiederholen Sie die Schritte des vorherigen Verfahrens für `SumPageSizes`. Ändern Sie zunächst den Aufruf von `GetURLContents` zu einem asynchronen Aufruf.  
  
    -   Ändern Sie den Namen der Methode, die aufgerufen wird, von `GetURLContents` zu `GetURLContentsAsync`, sofern Sie dies nicht bereits getan haben.  
  
    -   Wenden Sie `Await` auf die Aufgabe an, die durch `GetURLContentsAsync` zurückgegeben wird, um den Bytearraywert abzurufen.  
  
     Im folgenden Code sind diese Änderungen dargestellt.  
  
    ```vb  
    Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
    ```  
  
     Die vorherige Zuweisung kürzt die folgenden zwei Codezeilen.  
  
    ```vb  
    ' GetURLContentsAsync returns a task. At completion, the task   
    ' produces a byte array.   
    'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)   
    'Dim urlContents As Byte() = Await getContentsTask  
    ```  
  
2.  Nehmen Sie folgende Änderungen in der Methodensignatur vor:  
  
    -   Markieren Sie die Methode mit dem Modifizierer `Async`.  
  
    -   Fügen Sie dem Methodennamen „Async“ hinzu.  
  
    -   Es ist dieses Mal keine Aufgabenrückgabevariable „T“ vorhanden, da `SumPageSizesAsync` keinen Wert für „T“ zurückgibt. (Die Methode weist keine `Return`-Anweisung auf.) Die Methode muss jedoch eine `Task` zurückgeben, die awaitable ist. Daher ändern Sie den Methodentyp von `Sub` auf `Function`. Der Rückgabetyp der Funktion lautet `Task`.  
  
     Im folgenden Code sind diese Änderungen dargestellt.  
  
    ```vb  
    Private Async Function SumPageSizesAsync() As Task  
    ```  
  
     Die Konvertierung von `SumPageSizes` zu `SumPageSizesAsync` ist abgeschlossen.  
  
##  <a name="BKMK_Cnvrtbttn1"></a>   
###  <a name="startButton"></a> So konvertieren Sie „startButton_Click“ in eine asynchrone Methode  
  
1.  Ändern Sie im Ereignishandler den Namen der aufgerufenen Methode von `SumPageSizes` zu `SumPageSizesAsync`, sofern Sie dies nicht bereits vorgenommen haben.  
  
2.  Da es sich bei `SumPageSizesAsync` um eine asynchrone Methode handelt, ändern Sie den Code im Ereignishandler, um auf das Ergebnis zu warten.  
  
     Der Aufruf von `SumPageSizesAsync` spiegelt den Aufruf von `CopyToAsync` in `GetURLContentsAsync` wider. Der Aufruf gibt eine `Task` und keine `Task(T)` zurück.  
  
     Analog zu den vorherigen Vorgehensweisen können Sie den Aufruf mithilfe von einer oder zwei Anweisungen konvertieren. Im folgenden Code sind diese Änderungen dargestellt.  
  
    ```vb  
    '' One-step async call.  
    Await SumPageSizesAsync()  
  
    ' Two-step async call.  
    'Dim sumTask As Task = SumPageSizesAsync()  
    'Await sumTask  
    ```  
  
3.  Um den versehentlichen Neustart des Vorgangs zu verhindern, fügen Sie oben in `startButton_Click` die folgende Anweisung ein, um die Schaltfläche **Start** zu deaktivieren.  
  
    ```vb  
    ' Disable the button until the operation is complete.  
    startButton.IsEnabled = False  
    ```  
  
     Sie können die Schaltfläche am Ende des Ereignishandlers wieder aktivieren.  
  
    ```vb  
    ' Reenable the button in case you want to run the operation again.  
    startButton.IsEnabled = True  
    ```  
  
     Weitere Informationen über das erneute eintreten finden Sie unter [Eintretens in asynchronen Anwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md).  
  
4.  Fügen Sie der Deklaration abschließend den Modifizierer `Async` hinzu, sodass der Ereignishandler auf `SumPagSizesAsync` warten kann.  
  
    ```vb  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
    ```  
  
     In der Regel werden die Namen der Ereignishandler nicht geändert. Der Rückgabetyp wird nicht geändert, um `Task` da Ereignishandler Transportservers `Sub` -Prozeduren in Visual Basic.  
  
     Die Konvertierung des Projekts von der synchronen zu asynchronen Verarbeitung ist abgeschlossen.  
  
##  <a name="BKMK_testAsynchSolution"></a>   
###  <a name="testAsynch"></a> So testen Sie die asynchrone Lösung  
  
1.  Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
2.  Es sollte eine Ausgabe angezeigt werden, die der Ausgabe der synchronen Lösung gleicht. Folgende Unterschiede sind jedoch zu berücksichtigen.  
  
    -   Die Ergebnisse treten nicht alle gleichzeitig auf, nachdem die Verarbeitung abgeschlossen wurde. Beispielsweise enthalten beide Programme eine Zeile in `startButton_Click`, die das Textfeld löscht. Es ist vorgesehen, das Textfeld zwischen zwei Ausführungen zu löschen, wenn Sie die Schaltfläche **Start** ein zweites Mal auswählen, nachdem ein Ergebnissatz angezeigt wurde. In der synchronen Version wird das Textfeld unmittelbar vor der zweiten Anzeige des Zählers gelöscht, wenn die Downloads abgeschlossen sind und der UI-Thread für die Verarbeitung anderer Aktionen frei ist. In der asynchronen Version wird das Textfeld unmittelbar gelöscht, nachdem Sie die Schaltfläche **Start** ausgewählt haben.  
  
    -   Das Wichtigste ist jedoch, dass der UI-Thread nicht blockiert wird, während Downloads vorgenommen werden. Sie können das Fenster verschieben oder dessen Größe anpassen, während die Webressourcen heruntergeladen, gezählt und angezeigt werden. Wenn eine der Websites langsam ist oder nicht antwortet, können Sie den Vorgang abbrechen, indem Sie die Schaltfläche **Schließen** (das x im roten Feld in der oberen rechten Ecke) auswählen.  
  
##  <a name="BKMK_ReplaceGetByteArrayAsync"></a>   
###  <a name="GetURLContentsAsync"></a> So ersetzen Sie die Methode „GetURLContentsAsync“ durch eine .NET Framework-Methode  
  
1.  .NET Framework 4.5 bietet viele asynchrone Methoden, die Sie verwenden können. Eine davon, die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%28System.String%29> erfüllt genau das, was in dieser exemplarischen Vorgehensweise nötig ist. Sie können sie anstelle der `GetURLContentsAsync`-Methode verwenden, die Sie in einer vorherigen Vorgehensweise erstellt haben.  
  
     Der erste Schritt besteht darin, ein `HttpClient`-Objekt in der Methode `SumPageSizesAsync` zu erstellen. Fügen Sie am Anfang der Methode die folgende Deklaration hinzu.  
  
    ```vb  
    ' Declare an HttpClient object and increase the buffer size. The  
    ' default buffer size is 65,536.  
    Dim client As HttpClient =  
        New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
    ```  
  
2.  Ersetzen Sie in `SumPageSizesAsync,` den Aufruf zu Ihrer `GetURLContentsAsync`-Methode durch einen Aufruf zur Methode `HttpClient`.  
  
    ```vb  
    Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ```  
  
3.  Entfernen Sie die von Ihnen geschriebene `GetURLContentsAsync`-Methode, oder kommentieren Sie sie aus.  
  
4.  Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
     Das Verhalten dieser Version des Projekts sollte mit dem Verhalten übereinstimmen, das in der Vorgehensweise „So testen Sie die asynchrone Lösung“ beschrieben wird, es sollte aber weniger Aufwand Ihrerseits nötig sein.  
  
##  <a name="BKMK_CompleteCodeExamples"></a> Beispiel  
 Der folgende Code enthält das vollständige Beispiel der Konvertierung von einer synchronen zu einer asynchronen Lösung mithilfe der von Ihnen geschriebenen asynchronen `GetURLContentsAsync`-Methode. Beachten Sie, dass sie der ursprünglichen synchronen Lösung sehr stark ähnelt.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        resultsTextBox.Clear()  
  
        '' One-step async call.  
        Await SumPageSizesAsync()  
  
        ' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            Dim urlContents As Byte() = Await GetURLContentsAsync(url)  
  
            ' The previous line abbreviates the following two assignment statements.  
  
            '//<snippet21>  
            ' GetURLContentsAsync returns a task. At completion, the task  
            ' produces a byte array.  
            'Dim getContentsTask As Task(Of Byte()) = GetURLContentsAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
        ' The downloaded resource ends up in the variable named content.  
        Dim content = New MemoryStream()  
  
        ' Initialize an HttpWebRequest for the current URL.  
        Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
        ' Send the request to the Internet resource and wait for  
        ' the response.  
        Using response As WebResponse = Await webReq.GetResponseAsync()  
  
            ' The previous statement abbreviates the following two statements.  
  
            'Dim responseTask As Task(Of WebResponse) = webReq.GetResponseAsync()  
            'Using response As WebResponse = Await responseTask  
  
            ' Get the data stream that is associated with the specified URL.  
            Using responseStream As Stream = response.GetResponseStream()  
                ' Read the bytes in responseStream and copy them to content.    
                Await responseStream.CopyToAsync(content)  
  
                ' The previous statement abbreviates the following two statements.  
  
                ' CopyToAsync returns a Task, not a Task<T>.  
                'Dim copyTask As Task = responseStream.CopyToAsync(content)  
  
                ' When copyTask is completed, content contains a copy of  
                ' responseStream.  
                'Await copyTask  
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
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
 Der folgende Code umfasst das vollständige Beispiel der Lösung, die die `HttpClient`-Methode `GetByteArrayAsync` verwendet.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
Imports System.Net  
Imports System.IO  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
  
        resultsTextBox.Clear()  
  
        ' Disable the button until the operation is complete.  
        startButton.IsEnabled = False  
  
        ' One-step async call.  
        Await SumPageSizesAsync()  
  
        '' Two-step async call.  
        'Dim sumTask As Task = SumPageSizesAsync()  
        'Await sumTask  
  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
  
        ' Reenable the button in case you want to run the operation again.  
        startButton.IsEnabled = True  
    End Sub  
  
    Private Async Function SumPageSizesAsync() As Task  
  
        ' Declare an HttpClient object and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Make a list of web addresses.  
        Dim urlList As List(Of String) = SetUpURLList()  
  
        Dim total = 0  
        For Each url In urlList  
            ' GetByteArrayAsync returns a task. At completion, the task  
            ' produces a byte array.  
            Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
  
            ' The following two lines can replace the previous assignment statement.  
            'Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
            'Dim urlContents As Byte() = Await getContentsTask  
  
            DisplayResults(url, urlContents)  
  
            ' Update the total.  
            total += urlContents.Length  
        Next  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Function SetUpURLList() As List(Of String)  
  
        Dim urls = New List(Of String) From  
            {  
                "http://msdn.microsoft.com/library/windows/apps/br211380.aspx",  
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290136.aspx",  
                "http://msdn.microsoft.com/library/ee256749.aspx",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            }  
        Return urls  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ASYNC-Beispiel: Zugreifen auf die exemplarische Vorgehensweise (C#- und Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255191)  
 [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md)  
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)  
 [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) (Asynchrone Rückgabetypen (Visual Basic))  
 [Aufgabenbasierte asynchrone Programmierung (TAP)](http://go.microsoft.com/fwlink/?LinkId=204847)  
 [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Gewusst wie: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (Visual Basic))  
 [How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md) (Gewusst wie: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (Visual Basic))
