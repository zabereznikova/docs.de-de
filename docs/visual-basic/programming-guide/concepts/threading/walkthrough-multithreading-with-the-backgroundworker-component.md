---
title: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
ms.openlocfilehash: 07700aa526866729f1ba1a8d846f22ce333c356d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie man eine Windows Forms-Multithreadanwendung erstellt, die in einer Textdatei nach dem Vorkommen eines Worts sucht. Folgendes wird veranschaulicht:  
  
-   Definieren einer Klasse mit einer Methode, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente aufgerufen werden kann  
  
-   Behandlung von Ereignissen, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente ausgelöst werden  
  
-   Starten einer <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Ausführen einer Methode  
  
-   Implementieren einer `Cancel`-Schaltfläche, die die <xref:System.ComponentModel.BackgroundWorker>-Komponente beendet  
  
### <a name="to-create-the-user-interface"></a>So erstellen Sie die Benutzeroberfläche  
  
1.  Öffnen Sie ein neues Visual Basic Windows Forms-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2.  Fügen Sie zwei Schaltflächen und vier Textfelder zu `Form1` hinzu.  
  
3.  Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |Erste Schaltfläche|`Name`, `Text`|Start, Start|  
    |Zweite Schaltfläche|`Name`, `Text`|Abbrechen, Abbrechen|  
    |Erstes Textfeld|`Name`, `Text`|SourceFile, ""|  
    |Zweites Textfeld|`Name`, `Text`|CompareString, „“|  
    |Drittes Textfeld|`Name`, `Text`|WordsCounted, „0“|  
    |Viertes Textfeld|`Name`, `Text`|LinesCounted, "0"|  
  
4.  Fügen Sie neben jedem Textfeld eine Bezeichnung hinzu. Legen Sie die Eigenschaft `Text` für jede Bezeichnung fest wie in der folgenden Tabelle gezeigt.  
  
    |Object|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |Erste Bezeichnung|`Text`|Quelldatei|  
    |Zweite Bezeichnung|`Text`|Zeichenfolge vergleichen|  
    |Dritte Bezeichnung|`Text`|Abgleich von Wörtern|  
    |Vierte Bezeichnung|`Text`|Gezählte Zeilen|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>So erstellen Sie eine BackgroundWorker-Komponente und abonnieren deren Ereignisse  
  
1.  Fügen Sie dem Formular über den Abschnitt **Komponenten** im **Werkzeugkasten** eine <xref:System.ComponentModel.BackgroundWorker>-Komponente hinzu. Sie wird in der Komponentenleiste des Formulars angezeigt.  
  
2.  Legen Sie die folgenden Eigenschaften für das BackgroundWorker1-Objekt.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird  
  
1.  Wählen Sie im Menü **Projekt** **Klasse hinzufügen** aus, um eine Klasse zum Projekt hinzuzufügen. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie **Klasse** aus dem Fenster „Vorlagen“ aus, und geben Sie `Words.vb` in das Namensfeld ein.  
  
3.  Klicken Sie auf **Hinzufügen**. Die `Words`-Klasse wird angezeigt.  
  
4.  Fügen Sie der `Words` -Klasse folgenden Code hinzu:  
  
    ```vb  
    Public Class Words  
        ' Object to store the current state, for passing to the caller.  
        Public Class CurrentState  
            Public LinesCounted As Integer  
            Public WordsMatched As Integer  
        End Class  
  
        Public SourceFile As String  
        Public CompareString As String  
        Private WordCount As Integer = 0  
        Private LinesCounted As Integer = 0  
  
        Public Sub CountWords(  
            ByVal worker As System.ComponentModel.BackgroundWorker,  
            ByVal e As System.ComponentModel.DoWorkEventArgs  
        )  
            ' Initialize the variables.  
            Dim state As New CurrentState  
            Dim line = ""  
            Dim elapsedTime = 20  
            Dim lastReportDateTime = Now  
  
            If CompareString Is Nothing OrElse  
               CompareString = System.String.Empty Then  
  
               Throw New Exception("CompareString not specified.")  
            End If  
  
            Using myStream As New System.IO.StreamReader(SourceFile)  
  
                ' Process lines while there are lines remaining in the file.  
                Do While Not myStream.EndOfStream  
                    If worker.CancellationPending Then  
                        e.Cancel = True  
                        Exit Do  
                    Else  
                        line = myStream.ReadLine  
                        WordCount += CountInString(line, CompareString)  
                        LinesCounted += 1  
  
                        ' Raise an event so the form can monitor progress.  
                        If Now > lastReportDateTime.AddMilliseconds(elapsedTime) Then  
                            state.LinesCounted = LinesCounted  
                            state.WordsMatched = WordCount  
                            worker.ReportProgress(0, state)  
                            lastReportDateTime = Now  
                        End If  
  
                        ' Uncomment for testing.  
                        'System.Threading.Thread.Sleep(5)  
                    End If  
                Loop  
  
                ' Report the final count values.  
                state.LinesCounted = LinesCounted  
                state.WordsMatched = WordCount  
                worker.ReportProgress(0, state)  
            End Using  
        End Sub  
  
        Private Function CountInString(  
            ByVal SourceString As String,  
            ByVal CompareString As String  
        ) As Integer  
            ' This function counts the number of times  
            ' a word is found in a line.  
            If SourceString Is Nothing Then  
                Return 0  
            End If  
  
            Dim EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString)  
  
            ' To count all occurrences of the string, even within words, remove  
            ' both instances of "\b".  
            Dim regex As New System.Text.RegularExpressions.Regex(  
                "\b" + EscapedCompareString + "\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase)  
  
            Dim matches As System.Text.RegularExpressions.MatchCollection  
            matches = regex.Matches(SourceString)  
            Return matches.Count  
        End Function  
    End Class  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>So behandeln Sie Ereignisse aus dem Thread  
  
-   Fügen Sie dem Hauptformular die folgenden Ereignishandler hinzu:  
  
    ```vb  
    Private Sub BackgroundWorker1_RunWorkerCompleted(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
      ) Handles BackgroundWorker1.RunWorkerCompleted  
  
        ' This event handler is called when the background thread finishes.  
        ' This method runs on the main thread.  
        If e.Error IsNot Nothing Then  
            MessageBox.Show("Error: " & e.Error.Message)  
        ElseIf e.Cancelled Then  
            MessageBox.Show("Word counting canceled.")  
        Else  
            MessageBox.Show("Finished counting words.")  
        End If  
    End Sub  
  
    Private Sub BackgroundWorker1_ProgressChanged(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.ProgressChangedEventArgs  
      ) Handles BackgroundWorker1.ProgressChanged  
  
        ' This method runs on the main thread.  
        Dim state As Words.CurrentState =   
            CType(e.UserState, Words.CurrentState)  
        Me.LinesCounted.Text = state.LinesCounted.ToString  
        Me.WordsCounted.Text = state.WordsMatched.ToString  
    End Sub  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>So starten und rufen Sie einen neuen Thread auf, der die WordCount-Methode ausführt  
  
1.  Fügen Sie dem Programm die folgenden Verfahren hinzu:  
  
    ```vb  
    Private Sub BackgroundWorker1_DoWork(   
        ByVal sender As Object,   
        ByVal e As System.ComponentModel.DoWorkEventArgs  
      ) Handles BackgroundWorker1.DoWork  
  
        ' This event handler is where the actual work is done.  
        ' This method runs on the background thread.  
  
        ' Get the BackgroundWorker object that raised this event.  
        Dim worker As System.ComponentModel.BackgroundWorker  
        worker = CType(sender, System.ComponentModel.BackgroundWorker)  
  
        ' Get the Words object and call the main method.  
        Dim WC As Words = CType(e.Argument, Words)  
        WC.CountWords(worker, e)  
    End Sub  
  
    Sub StartThread()  
        ' This method runs on the main thread.  
        Me.WordsCounted.Text = "0"  
  
        ' Initialize the object that the background worker calls.  
        Dim WC As New Words  
        WC.CompareString = Me.CompareString.Text  
        WC.SourceFile = Me.SourceFile.Text  
  
        ' Start the asynchronous operation.  
        BackgroundWorker1.RunWorkerAsync(WC)  
    End Sub  
    ```  
  
2.  Rufen Sie die `StartThread`-Methode über die `Start`-Schaltfläche im Formular auf:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>So implementieren Sie eine Schaltfläche „Abbrechen“, die den Thread beendet  
  
-   Rufen Sie die Prozedur `StopThread` aus dem Ereignishandler `Click` für die Schaltfläche `Cancel` auf.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Test  
 Sie können die Anwendung jetzt testen, um die korrekte Ausführung sicherzustellen.  
  
#### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1.  Drücken Sie F5, um die Anwendung auszuführen.  
  
2.  Wenn das Formular angezeigt wird, geben Sie den Dateipfad für die Datei ein, die Sie im Feld `sourceFile` testen möchten. Nehmen wir z.B. an, dass Ihre Testdatei den Namen „Test.txt“ hat; geben Sie „C:\Test.txt“ ein.  
  
3.  Geben Sie im zweiten Textfeld ein Wort oder einen Satz für die Anwendung ein, nach der Sie im Textfeld suchen möchten.  
  
4.  Klicken Sie auf die Schaltfläche `Start`. Die Schaltfläche `LinesCounted` sollte sofort mit dem Inkrementieren beginnen. Die Anwendung zeigt die Benachrichtigung „Finished Counting“ (Berechnung abgeschlossen) an, wenn der Vorgang abgeschlossen ist.  
  
#### <a name="to-test-the-cancel-button"></a>So testen Sie die Schaltfläche „Abbrechen“  
  
1.  Drücken Sie F5, um die Anwendung zu starten, und geben Sie den Dateinamen und das Suchwort ein, wie in der vorherigen Prozedur beschrieben. Stellen Sie sicher, dass die von Ihnen ausgewählte Datei groß genug ist, um sicherzustellen, dass Sie Zeit haben, den Vorgang abzubrechen, bevor er abgeschlossen ist.  
  
2.  Klicken Sie auf die Schaltfläche `Start`, um die Anwendung zu starten.  
  
3.  Klicken Sie auf die Schaltfläche `Cancel`. Die Anwendung sollte den Zählvorgang sofort beenden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung enthält eine grundlegende Fehlerbehandlung. Sie erkennt leere Suchbegriffe. Sie können dieses Programm stabiler machen, indem Sie andere Fehler behandeln, z.B. das Überschreiten der maximalen Anzahl von Wörtern oder Linien, die gezählt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Exemplarische Vorgehensweise: Erstellen einer einfachen Multithreadkomponente mit Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
