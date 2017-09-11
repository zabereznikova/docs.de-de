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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d0711c8e417ae5c95b0e109504b69882015241
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-multithreading-with-the-backgroundworker-component-visual-basic"></a><span data-ttu-id="0dcf5-102">Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0dcf5-102">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>
<span data-ttu-id="0dcf5-103">Diese exemplarische Vorgehensweise veranschaulicht, wie eine Windows Forms-Multithreadanwendung erstellt, die eine Textdatei nach Vorkommen eines Worts durchsucht.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-103">This walkthrough demonstrates how to create a multithreaded Windows Forms application that searches a text file for occurrences of a word.</span></span> <span data-ttu-id="0dcf5-104">Es veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0dcf5-104">It demonstrates:</span></span>  
  
-   <span data-ttu-id="0dcf5-105">Definieren einer Klasse mit einer Methode, die aufgerufen werden kann, indem die <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0dcf5-105">Defining a class with a method that can be called by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="0dcf5-106">Behandlung von Ereignissen, die ausgelöst wird, indem die <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0dcf5-106">Handling events raised by the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
-   <span data-ttu-id="0dcf5-107">Starten einer <xref:System.ComponentModel.BackgroundWorker>Komponente eine Methode auszuführen.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0dcf5-107">Starting a <xref:System.ComponentModel.BackgroundWorker> component to run a method.</span></span>  
  
-   <span data-ttu-id="0dcf5-108">Implementieren einer `Cancel` Schaltfläche, die beendet der <xref:System.ComponentModel.BackgroundWorker>Komponente.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0dcf5-108">Implementing a `Cancel` button that stops the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="0dcf5-109">So erstellen Sie die Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="0dcf5-109">To create the user interface</span></span>  
  
1.  <span data-ttu-id="0dcf5-110">Öffnen Sie ein neues Windows Forms-Anwendung von Visual Basic-Projekt, und erstellen Sie ein Formular mit dem Namen `Form1`.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-110">Open a new Visual Basic Windows Forms Application project, and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="0dcf5-111">Fügen Sie zwei Schaltflächen und vier Textfelder hinzu `Form1`.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-111">Add two buttons and four text boxes to `Form1`.</span></span>  
  
3.  <span data-ttu-id="0dcf5-112">Benennen Sie die Objekte, wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-112">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="0dcf5-113">Objekt</span><span class="sxs-lookup"><span data-stu-id="0dcf5-113">Object</span></span>|<span data-ttu-id="0dcf5-114">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0dcf5-114">Property</span></span>|<span data-ttu-id="0dcf5-115">Einstellung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-115">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="0dcf5-116">Erste Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0dcf5-116">First button</span></span>|<span data-ttu-id="0dcf5-117">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-117">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-118">Start und Start</span><span class="sxs-lookup"><span data-stu-id="0dcf5-118">Start, Start</span></span>|  
    |<span data-ttu-id="0dcf5-119">Zweite Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="0dcf5-119">Second button</span></span>|<span data-ttu-id="0dcf5-120">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-120">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-121">"Abbrechen", "Abbrechen"</span><span class="sxs-lookup"><span data-stu-id="0dcf5-121">Cancel, Cancel</span></span>|  
    |<span data-ttu-id="0dcf5-122">Erste Textfeld</span><span class="sxs-lookup"><span data-stu-id="0dcf5-122">First text box</span></span>|<span data-ttu-id="0dcf5-123">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-123">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-124">SourceFile, ""</span><span class="sxs-lookup"><span data-stu-id="0dcf5-124">SourceFile, ""</span></span>|  
    |<span data-ttu-id="0dcf5-125">Zweite Textfeld</span><span class="sxs-lookup"><span data-stu-id="0dcf5-125">Second text box</span></span>|<span data-ttu-id="0dcf5-126">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-126">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-127">CompareString, ""</span><span class="sxs-lookup"><span data-stu-id="0dcf5-127">CompareString, ""</span></span>|  
    |<span data-ttu-id="0dcf5-128">Dritte Textfeld</span><span class="sxs-lookup"><span data-stu-id="0dcf5-128">Third text box</span></span>|<span data-ttu-id="0dcf5-129">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-129">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-130">WordsCounted, "0"</span><span class="sxs-lookup"><span data-stu-id="0dcf5-130">WordsCounted, "0"</span></span>|  
    |<span data-ttu-id="0dcf5-131">Vierte Textfeld</span><span class="sxs-lookup"><span data-stu-id="0dcf5-131">Fourth text box</span></span>|<span data-ttu-id="0dcf5-132">`Name`, `Text`</span><span class="sxs-lookup"><span data-stu-id="0dcf5-132">`Name`, `Text`</span></span>|<span data-ttu-id="0dcf5-133">LinesCounted "0"</span><span class="sxs-lookup"><span data-stu-id="0dcf5-133">LinesCounted, "0"</span></span>|  
  
4.  <span data-ttu-id="0dcf5-134">Fügen Sie eine Bezeichnung neben jedem Textfeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-134">Add a label next to each text box.</span></span> <span data-ttu-id="0dcf5-135">Legen Sie die `Text` -Eigenschaft für jede Bezeichnung wie in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-135">Set the `Text` property for each label as shown in the following table.</span></span>  
  
    |<span data-ttu-id="0dcf5-136">Objekt</span><span class="sxs-lookup"><span data-stu-id="0dcf5-136">Object</span></span>|<span data-ttu-id="0dcf5-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0dcf5-137">Property</span></span>|<span data-ttu-id="0dcf5-138">Einstellung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-138">Setting</span></span>|  
    |------------|--------------|-------------|  
    |<span data-ttu-id="0dcf5-139">Erste Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-139">First label</span></span>|`Text`|<span data-ttu-id="0dcf5-140">Quelldatei</span><span class="sxs-lookup"><span data-stu-id="0dcf5-140">Source File</span></span>|  
    |<span data-ttu-id="0dcf5-141">Zweite Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-141">Second label</span></span>|`Text`|<span data-ttu-id="0dcf5-142">Zeichenfolge vergleichen</span><span class="sxs-lookup"><span data-stu-id="0dcf5-142">Compare String</span></span>|  
    |<span data-ttu-id="0dcf5-143">Dritte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-143">Third label</span></span>|`Text`|<span data-ttu-id="0dcf5-144">Wörter</span><span class="sxs-lookup"><span data-stu-id="0dcf5-144">Matching Words</span></span>|  
    |<span data-ttu-id="0dcf5-145">Vierte Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-145">Fourth label</span></span>|`Text`|<span data-ttu-id="0dcf5-146">Zeilen gezählt</span><span class="sxs-lookup"><span data-stu-id="0dcf5-146">Lines Counted</span></span>|  
  
### <a name="to-create-a-backgroundworker-component-and-subscribe-to-its-events"></a><span data-ttu-id="0dcf5-147">Erstellen eine BackgroundWorker-Komponente und die zugehörigen Ereignisse abonnieren</span><span class="sxs-lookup"><span data-stu-id="0dcf5-147">To create a BackgroundWorker component and subscribe to its events</span></span>  
  
1.  <span data-ttu-id="0dcf5-148">Hinzufügen einer <xref:System.ComponentModel.BackgroundWorker>-Komponente aus der **Komponenten** Teil der **ToolBox** in das Formular.</xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="0dcf5-148">Add a <xref:System.ComponentModel.BackgroundWorker> component from the **Components** section of the **ToolBox** to the form.</span></span> <span data-ttu-id="0dcf5-149">Es wird im Komponentenfach des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-149">It will appear in the form's component tray.</span></span>  
  
2.  <span data-ttu-id="0dcf5-150">Legen Sie die folgenden Eigenschaften für das BackgroundWorker1-Objekt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-150">Set the following properties for the BackgroundWorker1 object.</span></span>  
  
    |<span data-ttu-id="0dcf5-151">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0dcf5-151">Property</span></span>|<span data-ttu-id="0dcf5-152">Einstellung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-152">Setting</span></span>|  
    |--------------|-------------|  
    |`WorkerReportsProgress`|<span data-ttu-id="0dcf5-153">True</span><span class="sxs-lookup"><span data-stu-id="0dcf5-153">True</span></span>|  
    |`WorkerSupportsCancellation`|<span data-ttu-id="0dcf5-154">True</span><span class="sxs-lookup"><span data-stu-id="0dcf5-154">True</span></span>|  
  
### <a name="to-define-the-method-that-will-run-on-a-separate-thread"></a><span data-ttu-id="0dcf5-155">So definieren Sie die Methode, die in einem separaten Thread ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="0dcf5-155">To define the method that will run on a separate thread</span></span>  
  
1.  <span data-ttu-id="0dcf5-156">Aus der **Projekt** Menü wählen **Klasse hinzufügen** eine Klasse zum Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-156">From the **Project** menu, choose **Add Class** to add a class to the project.</span></span> <span data-ttu-id="0dcf5-157">Die **neues Element hinzufügen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-157">The **Add New Item** dialog box is displayed.</span></span>  
  
2.  <span data-ttu-id="0dcf5-158">Wählen Sie **Klasse** aus, und geben Sie `Words.vb` in das Feld Name ein.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-158">Select **Class** from the templates window and enter `Words.vb` in the name field.</span></span>  
  
3.  <span data-ttu-id="0dcf5-159">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-159">Click **Add**.</span></span> <span data-ttu-id="0dcf5-160">Die `Words` -Klasse wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-160">The `Words` class is displayed.</span></span>  
  
4.  <span data-ttu-id="0dcf5-161">Fügen Sie der `Words` -Klasse folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="0dcf5-161">Add the following code to the `Words` class:</span></span>  
  
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
  
### <a name="to-handle-events-from-the-thread"></a><span data-ttu-id="0dcf5-162">So behandeln Sie Ereignisse aus dem thread</span><span class="sxs-lookup"><span data-stu-id="0dcf5-162">To handle events from the thread</span></span>  
  
-   <span data-ttu-id="0dcf5-163">Fügen Sie auf dem Hauptformular die folgenden Ereignishandler hinzu:</span><span class="sxs-lookup"><span data-stu-id="0dcf5-163">Add the following event handlers to your main form:</span></span>  
  
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
  
### <a name="to-start-and-call-a-new-thread-that-runs-the-wordcount-method"></a><span data-ttu-id="0dcf5-164">So starten und rufen einen neuen Thread ausgeführt wird, die WordCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0dcf5-164">To start and call a new thread that runs the WordCount method</span></span>  
  
1.  <span data-ttu-id="0dcf5-165">Fügen Sie die folgenden Verfahren, mit dem Programm:</span><span class="sxs-lookup"><span data-stu-id="0dcf5-165">Add the following procedures to your program:</span></span>  
  
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
  
2.  <span data-ttu-id="0dcf5-166">Rufen Sie die `StartThread` Methode aus der `Start` Schaltfläche im Formular:</span><span class="sxs-lookup"><span data-stu-id="0dcf5-166">Call the `StartThread` method from the `Start` button on your form:</span></span>  
  
    ```vb  
    Private Sub Start_Click() Handles Start.Click  
        StartThread()  
    End Sub  
    ```  
  
### <a name="to-implement-a-cancel-button-that-stops-the-thread"></a><span data-ttu-id="0dcf5-167">Eine Schaltfläche zum Abbrechen zu implementieren, die den Thread beendet wird.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-167">To implement a Cancel button that stops the thread</span></span>  
  
-   <span data-ttu-id="0dcf5-168">Rufen Sie die `StopThread` Prozedur aus der `Click` -Ereignishandler für die `Cancel` Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-168">Call the `StopThread` procedure from the `Click` event handler for the `Cancel` button.</span></span>  
  
    ```vb  
    Private Sub Cancel_Click() Handles Cancel.Click  
        ' Cancel the asynchronous operation.  
        Me.BackgroundWorker1.CancelAsync()  
    End Sub  
    ```  
  
## <a name="testing"></a><span data-ttu-id="0dcf5-169">Test</span><span class="sxs-lookup"><span data-stu-id="0dcf5-169">Testing</span></span>  
 <span data-ttu-id="0dcf5-170">Sie können nun testen die Anwendung, um sicherzustellen, dass sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-170">You can now test the application to make sure it works correctly.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="0dcf5-171">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="0dcf5-171">To test the application</span></span>  
  
1.  <span data-ttu-id="0dcf5-172">Drücken Sie F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-172">Press F5 to run the application.</span></span>  
  
2.  <span data-ttu-id="0dcf5-173">Wenn das Formular angezeigt wird, geben Sie den Dateipfad für die Datei, die Sie in testen möchten die `sourceFile` Feld.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-173">When the form is displayed, enter the file path for the file you want to test in the `sourceFile` box.</span></span> <span data-ttu-id="0dcf5-174">Vorausgesetzt, dass die Testdatei mit der Bezeichnung Test.txt, geben Sie beispielsweise C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-174">For example, assuming your test file is named Test.txt, enter C:\Test.txt.</span></span>  
  
3.  <span data-ttu-id="0dcf5-175">Geben Sie in das zweite Textfeld ein Wort oder Ausdruck für die Anwendung, die in der Datei gesucht.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-175">In the second text box, enter a word or phrase for the application to search for in the text file.</span></span>  
  
4.  <span data-ttu-id="0dcf5-176">Klicken Sie auf die Schaltfläche `Start`.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-176">Click the `Start` button.</span></span> <span data-ttu-id="0dcf5-177">Die `LinesCounted` Schaltfläche inkrementieren sofort beginnen soll.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-177">The `LinesCounted` button should begin incrementing immediately.</span></span> <span data-ttu-id="0dcf5-178">Die Anwendung zeigt die Meldung "Zählen abgeschlossen", danach.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-178">The application displays the message "Finished Counting" when it is done.</span></span>  
  
#### <a name="to-test-the-cancel-button"></a><span data-ttu-id="0dcf5-179">So testen Sie die Schaltfläche "Abbrechen"</span><span class="sxs-lookup"><span data-stu-id="0dcf5-179">To test the Cancel button</span></span>  
  
1.  <span data-ttu-id="0dcf5-180">Drücken Sie F5, um die Anwendung zu starten, und geben die Datei und die Suchliste Word wie im vorherigen Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-180">Press F5 to start the application, and enter the file name and search word as described in the previous procedure.</span></span> <span data-ttu-id="0dcf5-181">Stellen Sie sicher, dass die von Ihnen ausgewählte Datei ist groß genug, um sicherzustellen, dass Sie Zeit haben, den Vorgang abzubrechen, bevor er abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-181">Make sure that the file you choose is large enough to ensure you will have time to cancel the procedure before it is finished.</span></span>  
  
2.  <span data-ttu-id="0dcf5-182">Klicken Sie auf die `Start` Schaltfläche, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-182">Click the `Start` button to start the application.</span></span>  
  
3.  <span data-ttu-id="0dcf5-183">Klicken Sie auf die Schaltfläche `Cancel`.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-183">Click the `Cancel` button.</span></span> <span data-ttu-id="0dcf5-184">Die Anwendung sollte Zählvorgang sofort beenden.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-184">The application should stop counting immediately.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0dcf5-185">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0dcf5-185">Next Steps</span></span>  
 <span data-ttu-id="0dcf5-186">Diese Anwendung enthält eine grundlegende Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-186">This application contains some basic error handling.</span></span> <span data-ttu-id="0dcf5-187">Es erkennt leere Suchzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-187">It detects blank search strings.</span></span> <span data-ttu-id="0dcf5-188">Sie können dieses Programm robuster machen, durch die Behandlung andere Fehler, z. B. Überschreitung der maximalen Anzahl von Wörtern oder Zeilen, die gezählt werden können.</span><span class="sxs-lookup"><span data-stu-id="0dcf5-188">You can make this program more robust by handling other errors, such as exceeding the maximum number of words or lines that can be counted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcf5-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dcf5-189">See Also</span></span>  
 <span data-ttu-id="0dcf5-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="0dcf5-190">[Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="0dcf5-191"> [Exemplarische Vorgehensweise: Erstellen einer einfachen Multithreadkomponente mit Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span><span class="sxs-lookup"><span data-stu-id="0dcf5-191"> [Walkthrough: Authoring a Simple Multithreaded Component with Visual Basic](http://msdn.microsoft.com/library/05693b70-3566-4d91-9f2c-c9bc4ccb3001) </span></span>  
<span data-ttu-id="0dcf5-192"> [Gewusst wie: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="0dcf5-192"> [How to: Subscribe to and Unsubscribe from Events](../../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span></span>
