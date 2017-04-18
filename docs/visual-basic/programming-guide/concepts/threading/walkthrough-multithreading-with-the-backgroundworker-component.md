---
title: Multithreading mit der BackgroundWorker-Komponente (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
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
ms.openlocfilehash: 3686eb230349876f6cfffd2ad94ed1f547779ab1
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a>Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht, wie eine Windows Forms-Multithreadanwendung erstellt, die eine Textdatei nach Vorkommen eines Worts durchsucht. Es veranschaulicht:  
  
-   Definieren einer Klasse mit einer Methode, die aufgerufen werden kann, indem die <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Behandlung von Ereignissen, die ausgelöst wird, indem die <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Starten einer <xref:System.ComponentModel.BackgroundWorker>Komponente eine Methode auszuführen.</xref:System.ComponentModel.BackgroundWorker>  
  
-   Implementieren einer `Cancel` Schaltfläche, die beendet der <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker>  
  
### <a name="to-create-the-user-interface"></a>So erstellen Sie die Benutzeroberfläche  
  
1.  Öffnen Sie ein neues Windows Forms-Anwendung von Visual Basic-Projekt, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
2.  Fügen Sie zwei Schaltflächen und vier Textfelder hinzu `Form1`.  
  
3.  Benennen Sie die Objekte, wie in der folgenden Tabelle dargestellt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |Erste Schaltfläche|`Name`, `Text`|Start und Start|  
    |Zweite Schaltfläche|`Name`, `Text`|"Abbrechen", "Abbrechen"|  
    |Erste Textfeld|`Name`, `Text`|SourceFile, ""|  
    |Zweite Textfeld|`Name`, `Text`|CompareString, ""|  
    |Dritte Textfeld|`Name`, `Text`|WordsCounted, "0"|  
    |Vierte Textfeld|`Name`, `Text`|LinesCounted "0"|  
  
4.  Fügen Sie eine Bezeichnung neben jedem Textfeld hinzu. Legen Sie die `Text` -Eigenschaft für jede Bezeichnung wie in der folgenden Tabelle dargestellt.  
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |Erste Bezeichnung|`Text`|Quelldatei|  
    |Zweite Bezeichnung|`Text`|Zeichenfolge vergleichen|  
    |Dritte Bezeichnung|`Text`|Wörter|  
    |Vierte Bezeichnung|`Text`|Zeilen gezählt|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>Erstellen eine BackgroundWorker-Komponente und die zugehörigen Ereignisse abonnieren  
  
1.  Hinzufügen einer <xref:System.ComponentModel.BackgroundWorker>-Komponente aus der **Komponenten** Teil der **ToolBox** in das Formular.</xref:System.ComponentModel.BackgroundWorker> Es wird im Komponentenfach des Formulars angezeigt.  
  
2.  Legen Sie die folgenden Eigenschaften für das BackgroundWorker1-Objekt.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird  
  
1.  Aus der **Projekt** Menü wählen **Klasse hinzufügen** eine Klasse zum Projekt hinzufügen. Die **neues Element hinzufügen** Dialogfeld wird angezeigt.  
  
2.  Wählen Sie **Klasse** aus, und geben Sie `Words.vb` in das Feld Name ein.  
  
3.  Klicken Sie auf **Hinzufügen**. Die `Words` -Klasse wird angezeigt.  
  
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
  
### <a name="to-handle-events-from-the-thread"></a>So behandeln Sie Ereignisse aus dem thread  
  
-   Fügen Sie auf dem Hauptformular die folgenden Ereignishandler hinzu:  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>So starten und rufen einen neuen Thread ausgeführt wird, die WordCount-Methode  
  
1.  Fügen Sie die folgenden Verfahren, mit dem Programm:  
  
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
  
2.  Rufen Sie die `StartThread` Methode aus der `Start` Schaltfläche im Formular:  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>Eine Schaltfläche zum Abbrechen zu implementieren, die den Thread beendet wird.  
  
-   Rufen Sie die `StopThread` Prozedur aus der `Click` -Ereignishandler für die `Cancel` Schaltfläche.  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a>Test  
 Sie können nun testen die Anwendung, um sicherzustellen, dass sie ordnungsgemäß funktioniert.  
  
#### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1.  Drücken Sie F5, um die Anwendung auszuführen.  
  
2.  Wenn das Formular angezeigt wird, geben Sie den Dateipfad für die Datei, die Sie in testen möchten die `sourceFile` Feld. Vorausgesetzt, dass die Testdatei mit der Bezeichnung Test.txt, geben Sie beispielsweise C:\Test.txt.  
  
3.  Geben Sie in das zweite Textfeld ein Wort oder Ausdruck für die Anwendung, die in der Datei gesucht.  
  
4.  Klicken Sie auf die Schaltfläche `Start`. Die `LinesCounted` Schaltfläche inkrementieren sofort beginnen soll. Die Anwendung zeigt die Meldung "Zählen abgeschlossen", danach.  
  
#### <a name="to-test-the-cancel-button"></a>So testen Sie die Schaltfläche "Abbrechen"  
  
1.  Drücken Sie F5, um die Anwendung zu starten, und geben die Datei und die Suchliste Word wie im vorherigen Verfahren beschrieben. Stellen Sie sicher, dass die von Ihnen ausgewählte Datei ist groß genug, um sicherzustellen, dass Sie Zeit haben, den Vorgang abzubrechen, bevor er abgeschlossen ist.  
  
2.  Klicken Sie auf die `Start` Schaltfläche, um die Anwendung zu starten.  
  
3.  Klicken Sie auf die Schaltfläche `Cancel`. Die Anwendung sollte Zählvorgang sofort beenden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung enthält eine grundlegende Fehlerbehandlung. Es erkennt leere Suchzeichenfolgen. Sie können dieses Programm robuster machen, durch die Behandlung andere Fehler, z. B. Überschreitung der maximalen Anzahl von Wörtern oder Zeilen, die gezählt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Exemplarische Vorgehensweise: Erstellen einer einfachen Multithreadkomponente mit Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)   
 [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
