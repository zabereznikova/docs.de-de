---
title: 'Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ff670fbf-a0ac-40c1-ab08-9ed53768f880
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 541a1ec788c337eea9965b8a46155e5c6606ea2f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-c"></a><span data-ttu-id="ec3aa-102">Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)</span><span class="sxs-lookup"><span data-stu-id="ec3aa-102">Walkthrough: Multithreading with the BackgroundWorker Component (C#)</span></span>
<span data-ttu-id="ec3aa-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie man eine Windows Forms-Multithreadanwendung erstellt, die in einer Textdatei nach dem Vorkommen eines Worts sucht.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="ec3aa-104">Folgendes wird veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ec3aa-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="ec3aa-105">Definieren einer Klasse mit einer Methode, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente aufgerufen werden kann</span><span class="sxs-lookup"><span data-stu-id="ec3aa-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="ec3aa-106">Behandlung von Ereignissen, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="ec3aa-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="ec3aa-107">Starten einer <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Ausführen einer Methode</span><span class="sxs-lookup"><span data-stu-id="ec3aa-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="ec3aa-108">Implementieren einer `Cancel`-Schaltfläche, die die <xref:System.ComponentModel.BackgroundWorker>-Komponente beendet</span><span class="sxs-lookup"><span data-stu-id="ec3aa-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="ec3aa-109">So erstellen Sie die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="ec3aa-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="ec3aa-110">Öffnen Sie ein neues Anwendungsprojekt von C# Windows Forms, und erstellen Sie ein Formular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-110">Open a new C# Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="ec3aa-111">Fügen Sie zwei Schaltflächen und vier Textfelder zu `Form1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="ec3aa-112">Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="ec3aa-113">Objekt</span><span class="sxs-lookup"><span data-stu-id="ec3aa-113">Object</span></span>|<span data-ttu-id="ec3aa-114">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ec3aa-114">Property</span></span>|<span data-ttu-id="ec3aa-115">Einstellung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="ec3aa-116">Erste Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ec3aa-116">First button</span></span>|<span data-ttu-id="ec3aa-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-117">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-118">Start, Start</span><span class="sxs-lookup"><span data-stu-id="ec3aa-118">Start, Start</span></span>|  
    |<span data-ttu-id="ec3aa-119">Zweite Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="ec3aa-119">Second button</span></span>|<span data-ttu-id="ec3aa-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-120">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-121">Abbrechen, Abbrechen</span><span class="sxs-lookup"><span data-stu-id="ec3aa-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="ec3aa-122">Erstes Textfeld</span><span class="sxs-lookup"><span data-stu-id="ec3aa-122">First text box</span></span>|<span data-ttu-id="ec3aa-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-123">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="ec3aa-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="ec3aa-125">Zweites Textfeld</span><span class="sxs-lookup"><span data-stu-id="ec3aa-125">Second text box</span></span>|<span data-ttu-id="ec3aa-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-126">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-127">CompareString, „“</span><span class="sxs-lookup"><span data-stu-id="ec3aa-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="ec3aa-128">Drittes Textfeld</span><span class="sxs-lookup"><span data-stu-id="ec3aa-128">Third text box</span></span>|<span data-ttu-id="ec3aa-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-129">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-130">WordsCounted, „0“</span><span class="sxs-lookup"><span data-stu-id="ec3aa-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="ec3aa-131">Viertes Textfeld</span><span class="sxs-lookup"><span data-stu-id="ec3aa-131">Fourth text box</span></span>|<span data-ttu-id="ec3aa-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="ec3aa-132">`Name`, `Text`</span></span>|<span data-ttu-id="ec3aa-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="ec3aa-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="ec3aa-134">Fügen Sie neben jedem Textfeld eine Bezeichnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-134">Add a label next to each text box.</span></span> <span data-ttu-id="ec3aa-135">Legen Sie die Eigenschaft `Text` für jede Bezeichnung fest wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="ec3aa-136">Objekt</span><span class="sxs-lookup"><span data-stu-id="ec3aa-136">Object</span></span>|<span data-ttu-id="ec3aa-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ec3aa-137">Property</span></span>|<span data-ttu-id="ec3aa-138">Einstellung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="ec3aa-139">Erste Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-139">First label</span></span>|`Text`|<span data-ttu-id="ec3aa-140">Quelldatei</span><span class="sxs-lookup"><span data-stu-id="ec3aa-140">Source File</span></span>|  
    |<span data-ttu-id="ec3aa-141">Zweite Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-141">Second label</span></span>|`Text`|<span data-ttu-id="ec3aa-142">Zeichenfolge vergleichen</span><span class="sxs-lookup"><span data-stu-id="ec3aa-142">Compare String</span></span>|  
    |<span data-ttu-id="ec3aa-143">Dritte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-143">Third label</span></span>|`Text`|<span data-ttu-id="ec3aa-144">Abgleich von Wörtern</span><span class="sxs-lookup"><span data-stu-id="ec3aa-144">Matching Words</span></span>|  
    |<span data-ttu-id="ec3aa-145">Vierte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-145">Fourth label</span></span>|`Text`|<span data-ttu-id="ec3aa-146">Gezählte Zeilen</span><span class="sxs-lookup"><span data-stu-id="ec3aa-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="ec3aa-147">So erstellen Sie eine BackgroundWorker-Komponente und abonnieren deren Ereignisse</span><span class="sxs-lookup"><span data-stu-id="ec3aa-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="ec3aa-148">Fügen Sie dem Formular über den Abschnitt **Komponenten** im **Werkzeugkasten** eine <xref:System.ComponentModel.BackgroundWorker>-Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="ec3aa-149">Sie wird in der Komponentenleiste des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="ec3aa-150">Legen Sie die folgenden Eigenschaften für das Objekt „backgroundWorker1“ fest.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-150">Set the following properties for the backgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="ec3aa-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ec3aa-151">Property</span></span>|<span data-ttu-id="ec3aa-152">Einstellung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="ec3aa-153">True</span><span class="sxs-lookup"><span data-stu-id="ec3aa-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="ec3aa-154">True</span><span class="sxs-lookup"><span data-stu-id="ec3aa-154">True</span></span>|  
  
3.  <span data-ttu-id="ec3aa-155">Abonnieren Sie die Ereignisse des Objekts „backgroundWorker1“.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-155">Subscribe to the events of the backgroundWorker1 object.</span></span> <span data-ttu-id="ec3aa-156">Klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-156">At the top of the **Properties** window, click the **Events** icon.</span></span> <span data-ttu-id="ec3aa-157">Doppelklicken Sie auf das Ereignis `RunWorkerCompleted`, um eine Ereignishandlermethode zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-157">Double-click the `RunWorkerCompleted` event to create an event handler method.</span></span> <span data-ttu-id="ec3aa-158">Führen Sie das gleiche für die Ereignisse `ProgressChanged` und `DoWork` durch.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-158">Do the same for the `ProgressChanged` and `DoWork` events.</span></span>  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="ec3aa-159">So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="ec3aa-159">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="ec3aa-160">Wählen Sie im Menü **Projekt** **Klasse hinzufügen** aus, um eine Klasse zum Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-160">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="ec3aa-161">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-161">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="ec3aa-162">Wählen Sie **Klasse** aus dem Fenster „Vorlagen“ aus, und geben Sie `Words.cs` in das Namensfeld ein.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-162">Select **Class** from the templates window and enter `Words.cs` in the name field.</span></span>  
  
3.  <span data-ttu-id="ec3aa-163">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-163">Click **Add**.</span></span> <span data-ttu-id="ec3aa-164">Die `Words`-Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-164">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="ec3aa-165">Fügen Sie der `Words` -Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="ec3aa-165">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="ec3aa-166">So behandeln Sie Ereignisse aus dem Thread</span><span class="sxs-lookup"><span data-stu-id="ec3aa-166">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="ec3aa-167">Fügen Sie dem Hauptformular die folgenden Ereignishandler hinzu:</span><span class="sxs-lookup"><span data-stu-id="ec3aa-167">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="ec3aa-168">So starten und rufen Sie einen neuen Thread auf, der die WordCount-Methode ausführt</span><span class="sxs-lookup"><span data-stu-id="ec3aa-168">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="ec3aa-169">Fügen Sie dem Programm die folgenden Verfahren hinzu:</span><span class="sxs-lookup"><span data-stu-id="ec3aa-169">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="ec3aa-170">Rufen Sie die `StartThread`-Methode über die `Start`-Schaltfläche im Formular auf:</span><span class="sxs-lookup"><span data-stu-id="ec3aa-170">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```csharp  
    private void Start_Click(object sender, EventArgs e)  
    {  
        StartThread();  
    }  
    ```  
  
    ##### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="ec3aa-171">So implementieren Sie eine Schaltfläche „Abbrechen“, die den Thread beendet</span><span class="sxs-lookup"><span data-stu-id="ec3aa-171">To implement a Cancel button that stops the thread</span></span>  
  
    -   <span data-ttu-id="ec3aa-172">Rufen Sie die Prozedur `StopThread` aus dem Ereignishandler `Click` für die Schaltfläche `Cancel` auf.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-172">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
        ```csharp  
        private void Cancel_Click(object sender, EventArgs e)  
        {  
            // Cancel the asynchronous operation.  
            this.backgroundWorker1.CancelAsync();  
        }  
        ```  
  
## <a name="testing"></a><span data-ttu-id="ec3aa-173">Test</span><span class="sxs-lookup"><span data-stu-id="ec3aa-173">Testing</span></span>  
 <span data-ttu-id="ec3aa-174">Sie können die Anwendung jetzt testen, um die korrekte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-174">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="ec3aa-175">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="ec3aa-175">To test the application</span></span>  
  
1.  <span data-ttu-id="ec3aa-176">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-176">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="ec3aa-177">Wenn das Formular angezeigt wird, geben Sie den Dateipfad für die Datei ein, die Sie im Feld `sourceFile` testen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-177">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="ec3aa-178">Nehmen wir z.B. an, dass Ihre Testdatei den Namen „Test.txt“ hat; geben Sie „C:\Test.txt“ ein.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-178">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="ec3aa-179">Geben Sie im zweiten Textfeld ein Wort oder einen Satz für die Anwendung ein, nach der Sie im Textfeld suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-179">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="ec3aa-180">Klicken Sie auf die Schaltfläche `Start`.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-180">Click the `Start` button.</span></span> <span data-ttu-id="ec3aa-181">Die Schaltfläche `LinesCounted` sollte sofort mit dem Inkrementieren beginnen.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-181">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="ec3aa-182">Die Anwendung zeigt die Benachrichtigung „Finished Counting“ (Berechnung abgeschlossen) an, wenn der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-182">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="ec3aa-183">So testen Sie die Schaltfläche „Abbrechen“</span><span class="sxs-lookup"><span data-stu-id="ec3aa-183">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="ec3aa-184">Drücken Sie F5, um die Anwendung zu starten, und geben Sie den Dateinamen und das Suchwort ein, wie in der vorherigen Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-184">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="ec3aa-185">Stellen Sie sicher, dass die von Ihnen ausgewählte Datei groß genug ist, um sicherzustellen, dass Sie Zeit haben, den Vorgang abzubrechen, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-185">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="ec3aa-186">Klicken Sie auf die Schaltfläche `Start`, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-186">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="ec3aa-187">Klicken Sie auf die Schaltfläche `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-187">Click the `Cancel` button.</span></span> <span data-ttu-id="ec3aa-188">Die Anwendung sollte den Zählvorgang sofort beenden.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-188">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ec3aa-189">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ec3aa-189">Next Steps</span></span>  
 <span data-ttu-id="ec3aa-190">Diese Anwendung enthält eine grundlegende Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-190">This application contains some basic error handling.</span></span> <span data-ttu-id="ec3aa-191">Sie erkennt leere Suchbegriffe.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-191">It detects blank search strings.</span></span> <span data-ttu-id="ec3aa-192">Sie können dieses Programm stabiler machen, indem Sie andere Fehler behandeln, z.B. das Überschreiten der maximalen Anzahl von Wörtern oder Linien, die gezählt werden können.</span><span class="sxs-lookup"><span data-stu-id="ec3aa-192">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3aa-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec3aa-193">See Also</span></span>  
 <span data-ttu-id="ec3aa-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec3aa-194">[Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) </span></span>  
 [<span data-ttu-id="ec3aa-195">Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="ec3aa-195">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)

