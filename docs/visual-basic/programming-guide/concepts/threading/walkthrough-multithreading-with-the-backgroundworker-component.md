---
title: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4cd9b2a-f924-470e-a16e-50274709b40e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb0734b4bbf3f8bf5b27305754829f1a9f29f42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="8c2b3-102">Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c2b3-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="8c2b3-103">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie man eine Windows Forms-Multithreadanwendung erstellt, die in einer Textdatei nach dem Vorkommen eines Worts sucht.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="8c2b3-104">Folgendes wird veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="8c2b3-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="8c2b3-105">Definieren einer Klasse mit einer Methode, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente aufgerufen werden kann</span><span class="sxs-lookup"><span data-stu-id="8c2b3-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="8c2b3-106">Behandlung von Ereignissen, die von der <xref:System.ComponentModel.BackgroundWorker>-Komponente ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="8c2b3-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="8c2b3-107">Starten einer <xref:System.ComponentModel.BackgroundWorker>-Komponente zum Ausführen einer Methode</span><span class="sxs-lookup"><span data-stu-id="8c2b3-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="8c2b3-108">Implementieren einer `Cancel`-Schaltfläche, die die <xref:System.ComponentModel.BackgroundWorker>-Komponente beendet</span><span class="sxs-lookup"><span data-stu-id="8c2b3-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="8c2b3-109">So erstellen Sie die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="8c2b3-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="8c2b3-110">Öffnen Sie ein neues Visual Basic Windows Forms-Anwendungsprojekt, und erstellen Sie ein Formular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="8c2b3-111">Fügen Sie zwei Schaltflächen und vier Textfelder zu `Form1` hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="8c2b3-112">Benennen Sie die Objekte wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="8c2b3-113">Objekt</span><span class="sxs-lookup"><span data-stu-id="8c2b3-113">Object</span></span>|<span data-ttu-id="8c2b3-114">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c2b3-114">Property</span></span>|<span data-ttu-id="8c2b3-115">Einstellung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="8c2b3-116">Erste Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="8c2b3-116">First button</span></span>|<span data-ttu-id="8c2b3-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-117">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-118">Start, Start</span><span class="sxs-lookup"><span data-stu-id="8c2b3-118">Start, Start</span></span>|  
    |<span data-ttu-id="8c2b3-119">Zweite Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="8c2b3-119">Second button</span></span>|<span data-ttu-id="8c2b3-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-120">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-121">Abbrechen, Abbrechen</span><span class="sxs-lookup"><span data-stu-id="8c2b3-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="8c2b3-122">Erstes Textfeld</span><span class="sxs-lookup"><span data-stu-id="8c2b3-122">First text box</span></span>|<span data-ttu-id="8c2b3-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-123">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="8c2b3-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="8c2b3-125">Zweites Textfeld</span><span class="sxs-lookup"><span data-stu-id="8c2b3-125">Second text box</span></span>|<span data-ttu-id="8c2b3-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-126">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-127">CompareString, „“</span><span class="sxs-lookup"><span data-stu-id="8c2b3-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="8c2b3-128">Drittes Textfeld</span><span class="sxs-lookup"><span data-stu-id="8c2b3-128">Third text box</span></span>|<span data-ttu-id="8c2b3-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-129">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-130">WordsCounted, „0“</span><span class="sxs-lookup"><span data-stu-id="8c2b3-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="8c2b3-131">Viertes Textfeld</span><span class="sxs-lookup"><span data-stu-id="8c2b3-131">Fourth text box</span></span>|<span data-ttu-id="8c2b3-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="8c2b3-132">`Name`, `Text`</span></span>|<span data-ttu-id="8c2b3-133">LinesCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="8c2b3-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="8c2b3-134">Fügen Sie neben jedem Textfeld eine Bezeichnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-134">Add a label next to each text box.</span></span> <span data-ttu-id="8c2b3-135">Legen Sie die Eigenschaft `Text` für jede Bezeichnung fest wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="8c2b3-136">Objekt</span><span class="sxs-lookup"><span data-stu-id="8c2b3-136">Object</span></span>|<span data-ttu-id="8c2b3-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c2b3-137">Property</span></span>|<span data-ttu-id="8c2b3-138">Einstellung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="8c2b3-139">Erste Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-139">First label</span></span>|`Text`|<span data-ttu-id="8c2b3-140">Quelldatei</span><span class="sxs-lookup"><span data-stu-id="8c2b3-140">Source File</span></span>|  
    |<span data-ttu-id="8c2b3-141">Zweite Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-141">Second label</span></span>|`Text`|<span data-ttu-id="8c2b3-142">Zeichenfolge vergleichen</span><span class="sxs-lookup"><span data-stu-id="8c2b3-142">Compare String</span></span>|  
    |<span data-ttu-id="8c2b3-143">Dritte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-143">Third label</span></span>|`Text`|<span data-ttu-id="8c2b3-144">Abgleich von Wörtern</span><span class="sxs-lookup"><span data-stu-id="8c2b3-144">Matching Words</span></span>|  
    |<span data-ttu-id="8c2b3-145">Vierte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-145">Fourth label</span></span>|`Text`|<span data-ttu-id="8c2b3-146">Gezählte Zeilen</span><span class="sxs-lookup"><span data-stu-id="8c2b3-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="8c2b3-147">So erstellen Sie eine BackgroundWorker-Komponente und abonnieren deren Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8c2b3-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="8c2b3-148">Fügen Sie dem Formular über den Abschnitt **Komponenten** im **Werkzeugkasten** eine <xref:System.ComponentModel.BackgroundWorker>-Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="8c2b3-149">Sie wird in der Komponentenleiste des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="8c2b3-150">Legen Sie die folgenden Eigenschaften für das BackgroundWorker1-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="8c2b3-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c2b3-151">Property</span></span>|<span data-ttu-id="8c2b3-152">Einstellung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="8c2b3-153">True</span><span class="sxs-lookup"><span data-stu-id="8c2b3-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="8c2b3-154">True</span><span class="sxs-lookup"><span data-stu-id="8c2b3-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="8c2b3-155">So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="8c2b3-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="8c2b3-156">Wählen Sie im Menü **Projekt** **Klasse hinzufügen** aus, um eine Klasse zum Projekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="8c2b3-157">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="8c2b3-158">Wählen Sie **Klasse** aus dem Fenster „Vorlagen“ aus, und geben Sie `Words.vb` in das Namensfeld ein.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="8c2b3-159">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-159">Click **Add**.</span></span> <span data-ttu-id="8c2b3-160">Die `Words`-Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="8c2b3-161">Fügen Sie der `Words` -Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="8c2b3-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="8c2b3-162">So behandeln Sie Ereignisse aus dem Thread</span><span class="sxs-lookup"><span data-stu-id="8c2b3-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="8c2b3-163">Fügen Sie dem Hauptformular die folgenden Ereignishandler hinzu:</span><span class="sxs-lookup"><span data-stu-id="8c2b3-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="8c2b3-164">So starten und rufen Sie einen neuen Thread auf, der die WordCount-Methode ausführt</span><span class="sxs-lookup"><span data-stu-id="8c2b3-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="8c2b3-165">Fügen Sie dem Programm die folgenden Verfahren hinzu:</span><span class="sxs-lookup"><span data-stu-id="8c2b3-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="8c2b3-166">Rufen Sie die `StartThread`-Methode über die `Start`-Schaltfläche im Formular auf:</span><span class="sxs-lookup"><span data-stu-id="8c2b3-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="8c2b3-167">So implementieren Sie eine Schaltfläche „Abbrechen“, die den Thread beendet</span><span class="sxs-lookup"><span data-stu-id="8c2b3-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="8c2b3-168">Rufen Sie die Prozedur `StopThread` aus dem Ereignishandler `Click` für die Schaltfläche `Cancel` auf.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="8c2b3-169">Test</span><span class="sxs-lookup"><span data-stu-id="8c2b3-169">Testing</span></span>  
 <span data-ttu-id="8c2b3-170">Sie können die Anwendung jetzt testen, um die korrekte Ausführung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="8c2b3-171">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="8c2b3-171">To test the application</span></span>  
  
1.  <span data-ttu-id="8c2b3-172">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="8c2b3-173">Wenn das Formular angezeigt wird, geben Sie den Dateipfad für die Datei ein, die Sie im Feld `sourceFile` testen möchten.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="8c2b3-174">Nehmen wir z.B. an, dass Ihre Testdatei den Namen „Test.txt“ hat; geben Sie „C:\Test.txt“ ein.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="8c2b3-175">Geben Sie im zweiten Textfeld ein Wort oder einen Satz für die Anwendung ein, nach der Sie im Textfeld suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="8c2b3-176">Klicken Sie auf die Schaltfläche `Start`.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-176">Click the `Start` button.</span></span> <span data-ttu-id="8c2b3-177">Die Schaltfläche `LinesCounted` sollte sofort mit dem Inkrementieren beginnen.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="8c2b3-178">Die Anwendung zeigt die Benachrichtigung „Finished Counting“ (Berechnung abgeschlossen) an, wenn der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="8c2b3-179">So testen Sie die Schaltfläche „Abbrechen“</span><span class="sxs-lookup"><span data-stu-id="8c2b3-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="8c2b3-180">Drücken Sie F5, um die Anwendung zu starten, und geben Sie den Dateinamen und das Suchwort ein, wie in der vorherigen Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="8c2b3-181">Stellen Sie sicher, dass die von Ihnen ausgewählte Datei groß genug ist, um sicherzustellen, dass Sie Zeit haben, den Vorgang abzubrechen, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="8c2b3-182">Klicken Sie auf die Schaltfläche `Start`, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="8c2b3-183">Klicken Sie auf die Schaltfläche `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-183">Click the `Cancel` button.</span></span> <span data-ttu-id="8c2b3-184">Die Anwendung sollte den Zählvorgang sofort beenden.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c2b3-185">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8c2b3-185">Next Steps</span></span>  
 <span data-ttu-id="8c2b3-186">Diese Anwendung enthält eine grundlegende Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-186">This application contains some basic error handling.</span></span> <span data-ttu-id="8c2b3-187">Sie erkennt leere Suchbegriffe.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-187">It detects blank search strings.</span></span> <span data-ttu-id="8c2b3-188">Sie können dieses Programm stabiler machen, indem Sie andere Fehler behandeln, z.B. das Überschreiten der maximalen Anzahl von Wörtern oder Linien, die gezählt werden können.</span><span class="sxs-lookup"><span data-stu-id="8c2b3-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c2b3-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c2b3-189">See Also</span></span>  
 [<span data-ttu-id="8c2b3-190">Threading (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c2b3-190">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="8c2b3-191">Exemplarische Vorgehensweise: Erstellen einer einfachen Multithreadkomponente mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c2b3-191">Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic</span></span>](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001)  
 [<span data-ttu-id="8c2b3-192">Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements</span><span class="sxs-lookup"><span data-stu-id="8c2b3-192">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)
