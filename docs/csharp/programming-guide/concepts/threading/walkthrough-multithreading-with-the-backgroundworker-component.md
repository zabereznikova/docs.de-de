---
title: 'Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 72d6e9ab42ca270ebe0691be23ebe181b973620d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a>Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie man eine Windows Forms-Multithreadanwendung erstellt, die in einer Textdatei nach dem Vorkommen eines Worts sucht. Folgendes wird veranschaulicht:  
  
-   Definieren einer Klasse mit einer Methode, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente aufgerufen werden kann  
  
-   Behandlung von Ereignissen, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente ausgelöst werden  
  
-   Starten einer <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Ausführen einer Methode  
  
-   Implementieren einer `Cancel`-Schaltfläche, die die <xref:System.ComponentModel.BackgroundWorker>-Komponente beendet  
  
### <a name="to-create-the-user-interface"></a>So erstellen Sie die Benutzeroberfläche  
  
1.  Öffnen Sie ein neues Anwendungsprojekt von C# Windows Forms, und erstellen Sie ein Formular mit dem Namen `Form1`.  
  
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
  
    |Objekt|Eigenschaft|Einstellung|  
    |------------|--------------|-------------|  
    |Erste Bezeichnung|`Text`|Quelldatei|  
    |Zweite Bezeichnung|`Text`|Zeichenfolge vergleichen|  
    |Dritte Bezeichnung|`Text`|Abgleich von Wörtern|  
    |Vierte Bezeichnung|`Text`|Gezählte Zeilen|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a>So erstellen Sie eine BackgroundWorker-Komponente und abonnieren deren Ereignisse  
  
1.  Fügen Sie dem Formular über den Abschnitt **Komponenten** im **Werkzeugkasten** eine <xref:System.ComponentModel.BackgroundWorker>-Komponente hinzu. Sie wird in der Komponentenleiste des Formulars angezeigt.  
  
2.  Legen Sie die folgenden Eigenschaften für das Objekt „backgroundWorker1“ fest.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|True|  
    |`WorkerSupportsCancellation`|True|  
  
3.  Abonnieren Sie die Ereignisse des Objekts „backgroundWorker1“. Klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse**. Doppelklicken Sie auf das Ereignis `RunWorkerCompleted`, um eine Ereignishandlermethode zu erstellen. Führen Sie das gleiche für die Ereignisse `ProgressChanged` und `DoWork` durch.  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a>So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird  
  
1.  Wählen Sie im Menü **Projekt** **Klasse hinzufügen** aus, um eine Klasse zum Projekt hinzuzufügen. Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
2.  Wählen Sie **Klasse** aus dem Fenster „Vorlagen“ aus, und geben Sie `Words.cs` in das Namensfeld ein.  
  
3.  Klicken Sie auf **Hinzufügen**. Die `Words`-Klasse wird angezeigt.  
  
4.  Fügen Sie der `Words` -Klasse folgenden Code hinzu:  
  
    ```csharp  
    public class Words  
    {  
        // Object to store the current state, for passing to the caller.  
        public class CurrentState  
        {  
            public int LinesCounted;  
            public int WordsMatched;  
        }  
  
        public string SourceFile;  
        public string CompareString;  
        private int WordCount;  
        private int LinesCounted;  
  
        public void CountWords(  
            System.ComponentModel.BackgroundWorker worker,  
            System.ComponentModel.DoWorkEventArgs e)  
        {  
            // Initialize the variables.  
            CurrentState state = new CurrentState();  
            string line = "";  
            int elapsedTime = 20;  
            DateTime lastReportDateTime = DateTime.Now;  
  
            if (CompareString == null ||  
                CompareString == System.String.Empty)  
            {  
                throw new Exception("CompareString not specified.");  
            }  
  
            // Open a new stream.  
            using (System.IO.StreamReader myStream = new System.IO.StreamReader(SourceFile))  
            {  
                // Process lines while there are lines remaining in the file.  
                while (!myStream.EndOfStream)  
                {  
                    if (worker.CancellationPending)  
                    {  
                        e.Cancel = true;  
                        break;  
                    }  
                    else  
                    {  
                        line = myStream.ReadLine();  
                        WordCount += CountInString(line, CompareString);  
                        LinesCounted += 1;  
  
                        // Raise an event so the form can monitor progress.  
                        int compare = DateTime.Compare(  
                            DateTime.Now, lastReportDateTime.AddMilliseconds(elapsedTime));  
                        if (compare > 0)  
                        {  
                            state.LinesCounted = LinesCounted;  
                            state.WordsMatched = WordCount;  
                            worker.ReportProgress(0, state);  
                            lastReportDateTime = DateTime.Now;  
                        }  
                    }  
                    // Uncomment for testing.  
                    //System.Threading.Thread.Sleep(5);  
                }  
  
                // Report the final count values.  
                state.LinesCounted = LinesCounted;  
                state.WordsMatched = WordCount;  
                worker.ReportProgress(0, state);  
            }  
        }  
  
        private int CountInString(  
            string SourceString,  
            string CompareString)  
        {  
            // This function counts the number of times  
            // a word is found in a line.  
            if (SourceString == null)  
            {  
                return 0;  
            }  
  
            string EscapedCompareString =  
                System.Text.RegularExpressions.Regex.Escape(CompareString);  
  
            System.Text.RegularExpressions.Regex regex;  
            regex = new System.Text.RegularExpressions.Regex(   
                // To count all occurrences of the string, even within words, remove  
                // both instances of @"\b" from the following line.  
                @"\b" + EscapedCompareString + @"\b",  
                System.Text.RegularExpressions.RegexOptions.IgnoreCase);  
  
            System.Text.RegularExpressions.MatchCollection matches;  
            matches = regex.Matches(SourceString);  
            return matches.Count;  
        }  
  
    }  
    ```  
  
### <a name="to-handle-events-from-the-thread"></a>So behandeln Sie Ereignisse aus dem Thread  
  
-   Fügen Sie dem Hauptformular die folgenden Ereignishandler hinzu:  
  
    ```csharp  
    private void backgroundWorker1_RunWorkerCompleted(object sender, RunWorkerCompletedEventArgs e)  
    {  
    // This event handler is called when the background thread finishes.  
    // This method runs on the main thread.  
    if (e.Error != null)  
        MessageBox.Show("Error: " + e.Error.Message);  
    else if (e.Cancelled)  
        MessageBox.Show("Word counting canceled.");  
    else  
        MessageBox.Show("Finished counting words.");  
    }  
  
    private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)  
    {  
        // This method runs on the main thread.  
        Words.CurrentState state =  
            (Words.CurrentState)e.UserState;  
        this.LinesCounted.Text = state.LinesCounted.ToString();  
        this.WordsCounted.Text = state.WordsMatched.ToString();  
    }  
    ```  
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a>So starten und rufen Sie einen neuen Thread auf, der die WordCount-Methode ausführt  
  
1.  Fügen Sie dem Programm die folgenden Verfahren hinzu:  
  
    ```csharp  
    private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)  
    {  
        // This event handler is where the actual work is done.  
        // This method runs on the background thread.  
  
        // Get the BackgroundWorker object that raised this event.  
        System.ComponentModel.BackgroundWorker worker;  
        worker = (System.ComponentModel.BackgroundWorker)sender;  
  
        // Get the Words object and call the main method.  
        Words WC = (Words)e.Argument;  
        WC.CountWords(worker, e);  
    }  
  
    private void StartThread()  
    {  
        // This method runs on the main thread.  
        this.WordsCounted.Text = "0";  
  
        // Initialize the object that the background worker calls.  
        Words WC = new Words();  
        WC.CompareString = this.CompareString.Text;  
        WC.SourceFile = this.SourceFile.Text;  
  
        // Start the asynchronous operation.  
        backgroundWorker1.RunWorkerAsync(WC);  
    }  
    ```  
  
2.  Rufen Sie die `StartThread`-Methode über die `Start`-Schaltfläche im Formular auf:  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a>So implementieren Sie eine Schaltfläche „Abbrechen“, die den Thread beendet  
  
    -   Rufen Sie die Prozedur `StopThread` aus dem Ereignishandler `Click` für die Schaltfläche `Cancel` auf.  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
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
 [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
