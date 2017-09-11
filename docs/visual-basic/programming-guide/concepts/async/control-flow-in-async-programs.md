---
title: Ablaufsteuerung in asynchronen Programmen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15e02fbc023db9ae2f3ee9f40598faa7c9c027a0
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="control-flow-in-async-programs-visual-basic"></a><span data-ttu-id="7aa49-102">Ablaufsteuerung in asynchronen Programmen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7aa49-102">Control Flow in Async Programs (Visual Basic)</span></span>
<span data-ttu-id="7aa49-103">Sie können asynchrone Programme mithilfe der Schlüsselwörter `Async` und `Await` einfacher schreiben und verwalten.</span><span class="sxs-lookup"><span data-stu-id="7aa49-103">You can write and maintain asynchronous programs more easily by using the `Async` and `Await` keywords.</span></span> <span data-ttu-id="7aa49-104">Möglicherweise könnten Sie jedoch die Ergebnisse überraschen, wenn Sie die Funktionsweise Ihres Programms nicht verstehen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-104">However, the results might surprise you if you don't understand how your program operates.</span></span> <span data-ttu-id="7aa49-105">In diesem Thema wird die Ablaufsteuerung durch ein einfaches asynchrones Programm nachvollzogen, um darzustellen, wann die Steuerung von einer Methode zu einer anderen springt und welche Informationen jedes Mal übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7aa49-105">This topic traces the flow of control through a simple async program to show you when control moves from one method to another and what information is transferred each time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aa49-106">Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-106">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="7aa49-107">Im Allgemeinen markieren Sie Methoden, die mit asynchronen Code enthalten die [Async](../../../../visual-basic/language-reference/modifiers/async.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="7aa49-107">In general, you mark methods that contain asynchronous code with the [Async](../../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="7aa49-108">In einer Methode, die mit einem asynchronen Modifizierer markiert ist, können Sie eine ["await" (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) Operator, um anzugeben, wo die Methode anhält, um zu warten, bis ein aufgerufener asynchroner Prozess abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-108">In a method that's marked with an async modifier, you can use an [Await (Visual Basic)](../../../../visual-basic/language-reference/operators/await-operator.md) operator to specify where the method pauses to wait for a called asynchronous process to complete.</span></span> <span data-ttu-id="7aa49-109">Weitere Informationen finden Sie unter [asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="7aa49-109">For more information, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="7aa49-110">Im folgenden Beispiel werden asynchrone Methoden verwendet, um den Inhalt einer angegebenen Website als Zeichenfolge herunterzuladen und um die Länge der Zeichenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-110">The following example uses async methods to download the contents of a specified website as a string and to display the length of the string.</span></span> <span data-ttu-id="7aa49-111">Das Beispiel enthält die folgenden beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="7aa49-111">The example contains the following two methods.</span></span>  
  
-   <span data-ttu-id="7aa49-112">`startButton_Click`, die `AccessTheWebAsync` aufruft und das Ergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-112">`startButton_Click`, which calls `AccessTheWebAsync` and displays the result.</span></span>  
  
-   <span data-ttu-id="7aa49-113">`AccessTheWebAsync`, die den Inhalt einer Website als Zeichenfolge herunterlädt und die Länge der Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-113">`AccessTheWebAsync`, which downloads the contents of a website as a string and returns the length of the string.</span></span> <span data-ttu-id="7aa49-114">`AccessTheWebAsync`verwendet eine asynchrone <xref:System.Net.Http.HttpClient>Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, um den Inhalt herunterzuladen.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="7aa49-114">`AccessTheWebAsync` uses an asynchronous <xref:System.Net.Http.HttpClient> method, <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, to download the contents.</span></span>  
  
 <span data-ttu-id="7aa49-115">Nummerierte Ausgabezeilen werden über das Programm verteilt an strategischen Stellen angezeigt, die dabei helfen sollen, die Ausführung des Programms nachzuvollziehen und zu verdeutlichen, was an den markierten Punkten geschieht.</span><span class="sxs-lookup"><span data-stu-id="7aa49-115">Numbered display lines appear at strategic points throughout the program to help you understand how the program runs and to explain what happens at each point that is marked.</span></span> <span data-ttu-id="7aa49-116">Die Ausgabezeilen werden durchgehend von "ONE" (Eins) bis "SIX" (Sechs) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7aa49-116">The display lines are labeled "ONE" through "SIX."</span></span> <span data-ttu-id="7aa49-117">Die Bezeichnungen entsprechen der Reihenfolge, in der das Programm diese Codezeilen erreicht.</span><span class="sxs-lookup"><span data-stu-id="7aa49-117">The labels represent the order in which the program reaches these lines of code.</span></span>  
  
 <span data-ttu-id="7aa49-118">Im folgenden Code wird die Gliederung des Programms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-118">The following code shows an outline of the program.</span></span>  
  
```vb  
Class MainWindow  
  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
        ' ONE  
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
        ' FOUR  
        Dim contentLength As Integer = Await getLengthTask  
  
        ' SIX  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
  
    End Sub  
  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' TWO  
        Dim client As HttpClient = New HttpClient()   
        Dim getStringTask As Task(Of String) =   
            client.GetStringAsync("http://msdn.microsoft.com")  
  
        ' THREE  
        Dim urlContents As String = Await getStringTask  
  
        ' FIVE  
        Return urlContents.Length  
    End Function  
  
End Class  
  
```  
  
 <span data-ttu-id="7aa49-119">An jeder der mit "ONE" bis "SIX" bezeichneten Stellen werden Informationen über den aktuellen Status des Programms angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-119">Each of the labeled locations, "ONE" through "SIX," displays information about the current state of the program.</span></span> <span data-ttu-id="7aa49-120">Es wird die folgende Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7aa49-120">The following output is produced.</span></span>  
  
```  
  
ONE:   Entering startButton_Click.  
           Calling AccessTheWebAsync.  
  
TWO:   Entering AccessTheWebAsync.  
           Calling HttpClient.GetStringAsync.  
  
THREE: Back in AccessTheWebAsync.  
           Task getStringTask is started.  
           About to await getStringTask & return a Task<int> to startButton_Click.  
  
FOUR:  Back in startButton_Click.  
           Task getLengthTask is started.  
           About to await getLengthTask -- no caller to return to.  
  
FIVE:  Back in AccessTheWebAsync.  
           Task getStringTask is complete.  
           Processing the return statement.  
           Exiting from AccessTheWebAsync.  
  
SIX:   Back in startButton_Click.  
           Task getLengthTask is finished.  
           Result from AccessTheWebAsync is stored in contentLength.  
           About to display contentLength and exit.  
  
Length of the downloaded string: 33946.  
```  
  
## <a name="set-up-the-program"></a><span data-ttu-id="7aa49-121">Das Programm einrichten</span><span class="sxs-lookup"><span data-stu-id="7aa49-121">Set Up the Program</span></span>  
 <span data-ttu-id="7aa49-122">Sie können den Code, der in diesem Thema verwendet wird, von MSDN herunterladen oder Sie können ihn selbst erstellen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-122">You can download the code that this topic uses from MSDN, or you can build it yourself.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aa49-123">Zum Ausführen des Beispiels müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7aa49-123">To run the example, you must have Visual Studio 2012 or newer and  the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
### <a name="download-the-program"></a><span data-ttu-id="7aa49-124">Das Programm herunterladen</span><span class="sxs-lookup"><span data-stu-id="7aa49-124">Download the Program</span></span>  
 <span data-ttu-id="7aa49-125">Sie können die Anwendung für dieses Thema von [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span><span class="sxs-lookup"><span data-stu-id="7aa49-125">You can download the application for this topic from [Async Sample: Control Flow in Async Programs](http://go.microsoft.com/fwlink/?LinkId=255285).</span></span> <span data-ttu-id="7aa49-126">Mithilfe der folgenden Schritte wird das Programm geöffnet und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-126">The following steps open and run the program.</span></span>  
  
1.  <span data-ttu-id="7aa49-127">Entzippen Sie die heruntergeladene Datei und starten Sie anschließend Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7aa49-127">Unzip the downloaded file, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7aa49-128">Klicken Sie in der Menüleiste auf **Datei**, dann auf **Öffnen**und **Projekt/Projektmappe**.</span><span class="sxs-lookup"><span data-stu-id="7aa49-128">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="7aa49-129">Navigieren Sie zu dem Ordner, der den entzippten Beispielcode enthält, öffnen Sie die Projektmappendatei (SLN) und drücken Sie dann die F5-TASTE, um das Projekt zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-129">Navigate to the folder that holds the unzipped sample code, open the solution (.sln) file, and then choose the F5 key to build and run the project.</span></span>  
  
### <a name="build-the-program-yourself"></a><span data-ttu-id="7aa49-130">Das Programm selbst erstellen</span><span class="sxs-lookup"><span data-stu-id="7aa49-130">Build the Program Yourself</span></span>  
 <span data-ttu-id="7aa49-131">Das folgende Windows Presentation Foundation (WPF)-Projekt enthält das Codebeispiel für dieses Thema.</span><span class="sxs-lookup"><span data-stu-id="7aa49-131">The following Windows Presentation Foundation (WPF) project contains the code example for this topic.</span></span>  
  
 <span data-ttu-id="7aa49-132">Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7aa49-132">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="7aa49-133">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7aa49-133">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7aa49-134">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="7aa49-134">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="7aa49-135">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-135">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7aa49-136">In der **installierte Vorlagen** Bereich wählen **Visual Basic**, und wählen Sie dann **WPF-Anwendung** aus der Liste der Projekttypen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-136">In the **Installed Templates** pane, choose **Visual Basic**, and then choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="7aa49-137">Geben Sie `AsyncTracer` als Namen für das Projekt, und wählen Sie dann die **OK** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="7aa49-137">Enter `AsyncTracer` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="7aa49-138">Das neue Projekt wird im **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7aa49-138">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="7aa49-139">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="7aa49-139">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="7aa49-140">Wenn die Registerkarte nicht angezeigt wird, öffnen Sie das Kontextmenü für "MainWindow.xaml" im **Projektmappen-Explorer**, und wählen Sie dann **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="7aa49-140">If the tab isn’t visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="7aa49-141">In der **XAML** Anzeigen von "MainWindow.xaml", ersetzen Sie den Code durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="7aa49-141">In the **XAML** view of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"  
        Title="Control Flow Trace" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>  
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="7aa49-142">Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird angezeigt, der **Design** Ansicht von "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="7aa49-142">A simple window that contains a text box and a button appears in the **Design** view of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="7aa49-143">Fügen Sie einen Verweis für <xref:System.Net.Http>.</xref:System.Net.Http></span><span class="sxs-lookup"><span data-stu-id="7aa49-143">Add a reference for <xref:System.Net.Http>.</span></span>  
  
8.  <span data-ttu-id="7aa49-144">In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Anzeigecode**.</span><span class="sxs-lookup"><span data-stu-id="7aa49-144">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
9. <span data-ttu-id="7aa49-145">Ersetzen Sie in "MainWindow.Xaml.vb" den Code durch den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="7aa49-145">In MainWindow.xaml.vb , replace the code with the following code.</span></span>  
  
    ```vb  
    ' Add an Imports statement and a reference for System.Net.Http.  
    Imports System.Net.Http  
  
    Class MainWindow  
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click  
  
            ' The display lines in the example lead you through the control shifts.  
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &  
                "           Calling AccessTheWebAsync." & vbCrLf  
  
            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()  
  
            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is started." & vbCrLf &  
                "           About to await getLengthTask -- no caller to return to." & vbCrLf  
  
            Dim contentLength As Integer = Await getLengthTask  
  
            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &  
                "           Task getLengthTask is finished." & vbCrLf &  
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &  
                "           About to display contentLength and exit." & vbCrLf  
  
            ResultsTextBox.Text &=  
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
        End Sub  
  
        Async Function AccessTheWebAsync() As Task(Of Integer)  
  
            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."  
  
            ' Declare an HttpClient object.  
            Dim client As HttpClient = New HttpClient()  
  
            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf  
  
            ' GetStringAsync returns a Task(Of String).   
            Dim getStringTask As Task(Of String) = client.GetStringAsync("http://msdn.microsoft.com")  
  
            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &  
                "           Task getStringTask is started."  
  
            ' AccessTheWebAsync can continue to work until getStringTask is awaited.  
  
            ResultsTextBox.Text &=  
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf  
  
            ' Retrieve the website contents when task is complete.  
            Dim urlContents As String = Await getStringTask  
  
            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &  
                vbCrLf & "           Task getStringTask is complete." &  
                vbCrLf & "           Processing the return statement." &  
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf  
  
            Return urlContents.Length  
        End Function  
  
    End Class  
    ```  
  
10. <span data-ttu-id="7aa49-146">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="7aa49-146">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="7aa49-147">Es sollte folgende Ausgabe angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7aa49-147">The following output should appear.</span></span>  
  
    ```  
    ONE:   Entering startButton_Click.  
               Calling AccessTheWebAsync.  
  
    TWO:   Entering AccessTheWebAsync.  
               Calling HttpClient.GetStringAsync.  
  
    THREE: Back in AccessTheWebAsync.  
               Task getStringTask is started.  
               About to await getStringTask & return a Task<int> to startButton_Click.  
  
    FOUR:  Back in startButton_Click.  
               Task getLengthTask is started.  
               About to await getLengthTask -- no caller to return to.  
  
    FIVE:  Back in AccessTheWebAsync.  
               Task getStringTask is complete.  
               Processing the return statement.  
               Exiting from AccessTheWebAsync.  
  
    SIX:   Back in startButton_Click.  
               Task getLengthTask is finished.  
               Result from AccessTheWebAsync is stored in contentLength.  
               About to display contentLength and exit.  
  
    Length of the downloaded string: 33946.  
    ```  
  
## <a name="trace-the-program"></a><span data-ttu-id="7aa49-148">Ablaufverfolgung für das Programm durchführen</span><span class="sxs-lookup"><span data-stu-id="7aa49-148">Trace the Program</span></span>  
  
### <a name="steps-one-and-two"></a><span data-ttu-id="7aa49-149">Schritte EINS und ZWEI</span><span class="sxs-lookup"><span data-stu-id="7aa49-149">Steps ONE and TWO</span></span>  
 <span data-ttu-id="7aa49-150">Die ersten beiden Ausgabezeilen wird der Pfad als verfolgt `startButton_Click` Aufrufe `AccessTheWebAsync`, und `AccessTheWebAsync` Ruft die asynchrone <xref:System.Net.Http.HttpClient>Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> </xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="7aa49-150">The first two display lines trace the path as `startButton_Click` calls `AccessTheWebAsync`, and `AccessTheWebAsync` calls the asynchronous <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>.</span></span> <span data-ttu-id="7aa49-151">Im folgenden Bild werden die Aufrufe von Methode zu Methode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-151">The following image outlines the calls from method to method.</span></span>  
  
 <span data-ttu-id="7aa49-152">![Schritte eins und zwei](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace ONETWO")</span><span class="sxs-lookup"><span data-stu-id="7aa49-152">![Steps ONE and TWO](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")</span></span>  
  
 <span data-ttu-id="7aa49-153">Der Rückgabetyp der beiden `AccessTheWebAsync` und `client.GetStringAsync` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> ist</span><span class="sxs-lookup"><span data-stu-id="7aa49-153">The return type of both `AccessTheWebAsync` and `client.GetStringAsync` is <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7aa49-154">Für `AccessTheWebAsync` ist TResult eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="7aa49-154">For `AccessTheWebAsync`, TResult is an integer.</span></span> <span data-ttu-id="7aa49-155">Für `GetStringAsync` ist TResult eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7aa49-155">For `GetStringAsync`, TResult is a string.</span></span> <span data-ttu-id="7aa49-156">Weitere Informationen über Rückgabetypen asynchroner Methoden finden Sie unter [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="7aa49-156">For more information about async method return types, see [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
 <span data-ttu-id="7aa49-157">Eine asynchrone Methode, die eine Aufgabe zurückgibt, gibt eine Aufgabeninstanz zurück, wenn die Steuerung wieder zum Aufrufer zurückwechselt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-157">A task-returning async method returns a task instance when control shifts back to the caller.</span></span> <span data-ttu-id="7aa49-158">Steuerung von einer asynchronen Methode zurückgegeben, an die aufrufende Wenn entweder ein `Await` Operator in der aufgerufenen Methode oder die aufgerufene Methode beendet gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-158">Control returns from an async method to its caller either when an `Await` operator is encountered in the called method or when the called method ends.</span></span> <span data-ttu-id="7aa49-159">Durch die durchgehend mit "THREE" (Drei) bis "SIX" (Sechs) bezeichneten Ausgabezeilen wird dieser Teil des Prozesses verfolgt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-159">The display lines that are labeled "THREE" through "SIX" trace this part of the process.</span></span>  
  
### <a name="step-three"></a><span data-ttu-id="7aa49-160">Schritt DREI</span><span class="sxs-lookup"><span data-stu-id="7aa49-160">Step THREE</span></span>  
 <span data-ttu-id="7aa49-161">In `AccessTheWebAsync`, die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>aufgerufen, um den Inhalt der Zielwebseite herunterzuladen.</xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29></span><span class="sxs-lookup"><span data-stu-id="7aa49-161">In `AccessTheWebAsync`, the asynchronous method <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> is called to download the contents of the target webpage.</span></span> <span data-ttu-id="7aa49-162">Die Steuerung kehrt von `client.GetStringAsync` zu `AccessTheWebAsync` zurück, wenn `client.GetStringAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-162">Control returns from `client.GetStringAsync` to `AccessTheWebAsync` when `client.GetStringAsync` returns.</span></span>  
  
 <span data-ttu-id="7aa49-163">Die `client.GetStringAsync`-Methode gibt eine Zeichenfolgenaufgabe zurück, die der `getStringTask`-Variablen in `AccessTheWebAsync` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-163">The `client.GetStringAsync` method returns a task of string that’s assigned to the `getStringTask` variable in `AccessTheWebAsync`.</span></span> <span data-ttu-id="7aa49-164">Die folgende Zeile im Beispielprogramm zeigt den Aufruf von `client.GetStringAsync` und die Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="7aa49-164">The following line in the example program shows the call to `client.GetStringAsync` and the assignment.</span></span>  
  
<span data-ttu-id="7aa49-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-165"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-166">Sie können sich die Aufgabe als eine Zusage von `client.GetStringAsync` vorstellen, schließlich eine tatsächliche Zeichenfolge zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-166">You can think of the task as a promise by `client.GetStringAsync` to produce an actual string eventually.</span></span> <span data-ttu-id="7aa49-167">In der Zwischenzeit, wenn `AccessTheWebAsync` auszuführende Aufgaben hat, die nicht von der zugesagten Zeichenfolge von `client.GetStringAsync` abhängen, können diese Aufgaben fortgesetzt werden, während `client.GetStringAsync` wartet.</span><span class="sxs-lookup"><span data-stu-id="7aa49-167">In the meantime, if `AccessTheWebAsync` has work to do that doesn't depend on the promised string from `client.GetStringAsync`, that work can continue while  `client.GetStringAsync` waits.</span></span> <span data-ttu-id="7aa49-168">Im Beispiel bieten die folgenden, mit „THREE“ bezeichneten Ausgabezeilen die Gelegenheit, um unabhängige Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7aa49-168">In the example, the following lines of output, which are labeled "THREE,” represent the opportunity to do independent work</span></span>  
  
<span data-ttu-id="7aa49-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-169"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-170">Durch die folgende Anweisung wird die Ausführung in `AccessTheWebAsync` angehalten, wenn `getStringTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-170">The following statement suspends progress in `AccessTheWebAsync` when `getStringTask` is awaited.</span></span>  
  
<span data-ttu-id="7aa49-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-171"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-172">Die folgende Abbildung zeigt den Ablauf der Steuerung von `client.GetStringAsync` bis zur Zuweisung von `getStringTask` und von der Erstellung des `getStringTask` an die Anwendung eines Await-Operators.</span><span class="sxs-lookup"><span data-stu-id="7aa49-172">The following image shows the flow of control from `client.GetStringAsync` to the assignment to `getStringTask` and from the creation of `getStringTask` to the application of an Await operator.</span></span>  
  
 <span data-ttu-id="7aa49-173">![Schritt&3;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-3")</span><span class="sxs-lookup"><span data-stu-id="7aa49-173">![Step THREE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-Three")</span></span>  
  
 <span data-ttu-id="7aa49-174">Durch den await-Ausdruck wird `AccessTheWebAsync` angehalten, bis `client.GetStringAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-174">The await expression suspends `AccessTheWebAsync` until `client.GetStringAsync` returns.</span></span> <span data-ttu-id="7aa49-175">In der Zwischenzeit kehrt die Steuerung zum Aufrufer von `AccessTheWebAsync`, `startButton_Click`, zurück.</span><span class="sxs-lookup"><span data-stu-id="7aa49-175">In the meantime, control returns to the caller of `AccessTheWebAsync`, `startButton_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aa49-176">In der Regel warten Sie sofort auf den Aufruf einer asynchronen Methode.</span><span class="sxs-lookup"><span data-stu-id="7aa49-176">Typically, you await the call to an asynchronous method immediately.</span></span> <span data-ttu-id="7aa49-177">Zum Beispiel die folgende Zuordnung konnte den vorherigen Code ersetzen, die erstellt und wartet dann auf `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span><span class="sxs-lookup"><span data-stu-id="7aa49-177">For example, the following assignment could replace the previous code that creates and then awaits `getStringTask`: `Dim urlContents As String = Await client.GetStringAsync("http://msdn.microsoft.com")`</span></span>  
>   
>  <span data-ttu-id="7aa49-178">In diesem Thema wird der await-Operator später angewendet, um die Ausgabezeilen anzupassen, die die Ablaufsteuerung durch das Programm markieren.</span><span class="sxs-lookup"><span data-stu-id="7aa49-178">In this topic, the await operator is applied later to accommodate the output lines that mark the flow of control through the program.</span></span>  
  
### <a name="step-four"></a><span data-ttu-id="7aa49-179">Schritt VIER</span><span class="sxs-lookup"><span data-stu-id="7aa49-179">Step FOUR</span></span>  
 <span data-ttu-id="7aa49-180">Der deklarierte Rückgabetyp von `AccessTheWebAsync` ist `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="7aa49-180">The declared return type of `AccessTheWebAsync` is `Task(Of Integer)`.</span></span> <span data-ttu-id="7aa49-181">Wenn `AccessTheWebAsync` angehalten wird, wird daher eine Ganzzahlaufgabe an `startButton_Click` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7aa49-181">Therefore, when `AccessTheWebAsync` is suspended, it returns a task of integer to `startButton_Click`.</span></span> <span data-ttu-id="7aa49-182">Sie sollten verstanden haben, dass die zurückgegebene Aufgabe nicht `getStringTask` ist.</span><span class="sxs-lookup"><span data-stu-id="7aa49-182">You should understand that the returned task isn’t `getStringTask`.</span></span> <span data-ttu-id="7aa49-183">Die zurückgegebene Aufgabe ist eine neue Ganzzahlaufgabe, die die verbleibenden Aufgaben in der angehaltenen Methode, `AccessTheWebAsync`, darstellt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-183">The returned task is a new task of integer that represents what remains to be done in the suspended method, `AccessTheWebAsync`.</span></span> <span data-ttu-id="7aa49-184">Die Aufgabe ist eine Zusage von `AccessTheWebAsync`, eine ganze Zahl zu erzeugen, wenn die Aufgabe abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-184">The task is a promise from `AccessTheWebAsync` to produce an integer when the task is complete.</span></span>  
  
 <span data-ttu-id="7aa49-185">Die folgende Anweisung weist diese Aufgabe der `getLengthTask`-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="7aa49-185">The following statement assigns this task to the `getLengthTask` variable.</span></span>  
  
<span data-ttu-id="7aa49-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-186"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-187">Wie in `AccessTheWebAsync` kann `startButton_Click` mit Aufgaben fortsetzen, die nicht von den Ergebnissen der asynchronen Aufgabe (`getLengthTask`) abhängen, bis diese Aufgabe erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-187">As in `AccessTheWebAsync`, `startButton_Click` can continue with work that doesn’t depend on the results of the asynchronous task (`getLengthTask`) until the task is awaited.</span></span> <span data-ttu-id="7aa49-188">Die folgenden Ausgabezeilen stellen diese Aufgaben dar.</span><span class="sxs-lookup"><span data-stu-id="7aa49-188">The following output lines represent that work.</span></span>  
  
<span data-ttu-id="7aa49-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-189"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-190">Die Ausführung von `startButton_Click` wird angehalten, wenn `getLengthTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-190">Progress in `startButton_Click` is suspended when `getLengthTask` is awaited.</span></span> <span data-ttu-id="7aa49-191">Durch die folgende Zuweisungsanweisung wird `startButton_Click` angehalten, bis `AccessTheWebAsync` abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7aa49-191">The following assignment statement suspends `startButton_Click` until `AccessTheWebAsync` is complete.</span></span>  
  
<span data-ttu-id="7aa49-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-192"><CodeContentPlaceHolder>10</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-193">In der folgenden Abbildung veranschaulichen die Pfeile die Ablaufsteuerung vom await-Ausdruck in `AccessTheWebAsync` zur Zuweisung eines Werts an `getLengthTask`, gefolgt von normaler Verarbeitung in `startButton_Click` bis `getLengthTask` erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="7aa49-193">In the following illustration, the arrows show the flow of control from the await expression in `AccessTheWebAsync` to the assignment of a value to `getLengthTask`, followed by normal processing in `startButton_Click` until `getLengthTask` is awaited.</span></span>  
  
 <span data-ttu-id="7aa49-194">![Schritt&4;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace vier")</span><span class="sxs-lookup"><span data-stu-id="7aa49-194">![Step FOUR](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-FOUR")</span></span>  
  
### <a name="step-five"></a><span data-ttu-id="7aa49-195">Schritt FÜNF</span><span class="sxs-lookup"><span data-stu-id="7aa49-195">Step FIVE</span></span>  
 <span data-ttu-id="7aa49-196">Wenn `client.GetStringAsync` signalisiert, dass es abgeschlossen ist, wird die Verarbeitung in `AccessTheWebAsync` aus dem Anhalten freigegeben und kann nach dem await-Ausdruck fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7aa49-196">When `client.GetStringAsync` signals that it’s complete, processing in `AccessTheWebAsync` is released from suspension and can continue past the await statement.</span></span> <span data-ttu-id="7aa49-197">Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung dar.</span><span class="sxs-lookup"><span data-stu-id="7aa49-197">The following lines of output represent the resumption of processing.</span></span>  
  
<span data-ttu-id="7aa49-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-198"><CodeContentPlaceHolder>11</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-199">Der Operand der return-Anweisung, `urlContents.Length`, wird in der Aufgabe gespeichert, die `AccessTheWebAsync` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-199">The operand of the return statement, `urlContents.Length`, is stored in the task that  `AccessTheWebAsync` returns.</span></span> <span data-ttu-id="7aa49-200">Der await-Ausdruck ruft diesen Wert von `getLengthTask` in `startButton_Click` ab.</span><span class="sxs-lookup"><span data-stu-id="7aa49-200">The await expression retrieves that value from `getLengthTask` in `startButton_Click`.</span></span>  
  
 <span data-ttu-id="7aa49-201">Im folgenden Bild wird die Übertragung der Steuerung gezeigt, nachdem `client.GetStringAsync` (und `getStringTask`) abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="7aa49-201">The following image shows the transfer of control after `client.GetStringAsync` (and `getStringTask`) are complete.</span></span>  
  
 <span data-ttu-id="7aa49-202">![Schritt&5;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace&5;")</span><span class="sxs-lookup"><span data-stu-id="7aa49-202">![Step FIVE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-FIVE")</span></span>  
  
 <span data-ttu-id="7aa49-203">`AccessTheWebAsync` wird bis zum Abschluss ausgeführt und die Steuerung kehrt zu `startButton_Click` zurück, das den Abschluss erwartet.</span><span class="sxs-lookup"><span data-stu-id="7aa49-203">`AccessTheWebAsync` runs to completion, and control returns to `startButton_Click`, which is awaiting the completion.</span></span>  
  
### <a name="step-six"></a><span data-ttu-id="7aa49-204">Schritt SECHS</span><span class="sxs-lookup"><span data-stu-id="7aa49-204">Step SIX</span></span>  
 <span data-ttu-id="7aa49-205">Wenn `AccessTheWebAsync` signalisiert, dass es abgeschlossen ist, kann die Verarbeitung nach der await-Anweisung in `startButton_Async` fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7aa49-205">When `AccessTheWebAsync` signals that it’s complete, processing can continue past the await statement in `startButton_Async`.</span></span> <span data-ttu-id="7aa49-206">Für das Programm gibt es eigentlich nichts mehr zu tun.</span><span class="sxs-lookup"><span data-stu-id="7aa49-206">In fact, the program has nothing more to do.</span></span>  
  
 <span data-ttu-id="7aa49-207">Die folgenden Ausgabezeilen stellen die Wiederaufnahme der Verarbeitung in `startButton_Async` dar:</span><span class="sxs-lookup"><span data-stu-id="7aa49-207">The following lines of output represent the resumption of processing in `startButton_Async`:</span></span>  
  
<span data-ttu-id="7aa49-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-208"><CodeContentPlaceHolder>12</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-209">Der await-Ausdruck ruft von `getLengthTask` den ganzzahligen Wert ab, der der Operand der return-Anweisung in `AccessTheWebAsync` ist.</span><span class="sxs-lookup"><span data-stu-id="7aa49-209">The await expression retrieves from `getLengthTask` the integer value that’s the operand of the return statement in `AccessTheWebAsync`.</span></span> <span data-ttu-id="7aa49-210">Die folgende Anweisung weist diesen Wert der `contentLength`-Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="7aa49-210">The following statement assigns that value to the `contentLength` variable.</span></span>  
  
<span data-ttu-id="7aa49-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="7aa49-211"><CodeContentPlaceHolder>13</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="7aa49-212">Im folgenden Bild wird die Rückgabe der Steuerung von `AccessTheWebAsync` an `startButton_Click` gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7aa49-212">The following image shows the return of control from `AccessTheWebAsync` to `startButton_Click`.</span></span>  
  
 <span data-ttu-id="7aa49-213">![Schritt&6;](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-sechs")</span><span class="sxs-lookup"><span data-stu-id="7aa49-213">![Step SIX](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-SIX")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa49-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aa49-214">See Also</span></span>  
 <span data-ttu-id="7aa49-215">[Asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="7aa49-215">[Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md) </span></span>  
<span data-ttu-id="7aa49-216"> [Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span><span class="sxs-lookup"><span data-stu-id="7aa49-216"> [Async Return Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md) </span></span>  
<span data-ttu-id="7aa49-217"> [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="7aa49-217"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="7aa49-218"> [Async Sample: Control Flow in Async-Programmen (C#- und Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span><span class="sxs-lookup"><span data-stu-id="7aa49-218"> [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=255285)</span></span>
