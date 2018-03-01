---
title: Da auf diesen Aufruf nicht gewartet wird, wird die aktuelle Methode vor Abschluss des Aufrufs fortgesetzt
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0d0a5e7c50bacc657a3f54a7f08036ede59cbfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a><span data-ttu-id="fa07f-102">Da auf diesen Aufruf nicht gewartet wird, wird die aktuelle Methode vor Abschluss des Aufrufs fortgesetzt</span><span class="sxs-lookup"><span data-stu-id="fa07f-102">Because this call is not awaited, the current method continues to run before the call is completed</span></span>
<span data-ttu-id="fa07f-103">Da auf diesen Aufruf nicht gewartet wird, wird die Ausführung der aktuellen Methode vor Abschluss des Aufrufs fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="fa07f-103">Because this call is not awaited, execution of the current method continues before the call is completed.</span></span> <span data-ttu-id="fa07f-104">Ziehen Sie ein Anwenden des „Await“-Operators auf das Ergebnis des Aufrufs in Betracht.</span><span class="sxs-lookup"><span data-stu-id="fa07f-104">Consider applying the 'Await' operator to the result of the call.</span></span>  
  
 <span data-ttu-id="fa07f-105">Die aktuelle Methode ruft eine asynchrone Methode auf, die ein <xref:System.Threading.Tasks.Task> oder ein <xref:System.Threading.Tasks.Task%601> zurückgibt und nicht den [Await](../../../visual-basic/language-reference/operators/await-operator.md) -Operator auf das Ergebnis anwendet.</span><span class="sxs-lookup"><span data-stu-id="fa07f-105">The current method calls an async method that returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601> and doesn’t apply the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator to the result.</span></span> <span data-ttu-id="fa07f-106">Der Aufruf der asynchronen Methode startet eine asynchrone Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="fa07f-106">The call to the async method starts an asynchronous task.</span></span> <span data-ttu-id="fa07f-107">Da jedoch kein `Await` -Operator angewendet wird, wird das Programm fortgesetzt, ohne auf den Abschluss der Aufgabe zu warten.</span><span class="sxs-lookup"><span data-stu-id="fa07f-107">However, because no `Await` operator is applied, the program continues without waiting for the task to complete.</span></span> <span data-ttu-id="fa07f-108">Dieses Verhalten wird in den meisten Fällen nicht erwartet.</span><span class="sxs-lookup"><span data-stu-id="fa07f-108">In most cases, that behavior isn't expected.</span></span> <span data-ttu-id="fa07f-109">Andere Aspekte der aufrufenden Methode hängen in der Regel von den Ergebnissen des Aufrufs ab, mindestens jedoch wird erwartet, dass die aufgerufene Methode abgeschlossen wird, bevor Sie von der Methode zurückgegeben, die den Aufruf enthält.</span><span class="sxs-lookup"><span data-stu-id="fa07f-109">Usually other aspects of the calling method depend on the results of the call or, minimally, the called method is expected to complete before you return from the method that contains the call.</span></span>  
  
 <span data-ttu-id="fa07f-110">Ein gleichermaßen wichtiges Problem besteht in der Behandlung von Ausnahmen, die in der aufgerufenen asynchrone Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="fa07f-110">An equally important issue is what happens with exceptions that are raised in the called async method.</span></span> <span data-ttu-id="fa07f-111">Eine Ausnahme, die in einer Methode ausgelöst wird, die ein <xref:System.Threading.Tasks.Task> oder  <xref:System.Threading.Tasks.Task%601> zurückgibt, wird in der zurückgegebenen Aufgabe gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fa07f-111">An exception that’s raised in a method that returns a <xref:System.Threading.Tasks.Task> or  <xref:System.Threading.Tasks.Task%601> is stored in the returned task.</span></span> <span data-ttu-id="fa07f-112">Wenn Sie nicht auf die Aufgabe warten oder explizit auf Ausnahmen hin prüfen, geht die Ausnahme verloren.</span><span class="sxs-lookup"><span data-stu-id="fa07f-112">If you don't await the task or explicitly check for exceptions, the exception is lost.</span></span> <span data-ttu-id="fa07f-113">Wenn Sie auf die Aufgabe warten, wird die Ausnahme erneut ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fa07f-113">If you await the task, its exception is rethrown.</span></span>  
  
 <span data-ttu-id="fa07f-114">Als bewährte Methode sollten Sie immer auf den Aufruf warten.</span><span class="sxs-lookup"><span data-stu-id="fa07f-114">As a best practice, you should always await the call.</span></span>  
  
 <span data-ttu-id="fa07f-115">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="fa07f-115">By default, this message is a warning.</span></span> <span data-ttu-id="fa07f-116">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fa07f-116">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="fa07f-117">**Fehler-ID:** BC42358</span><span class="sxs-lookup"><span data-stu-id="fa07f-117">**Error ID:** BC42358</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="fa07f-118">So reagieren Sie auf diese Warnung</span><span class="sxs-lookup"><span data-stu-id="fa07f-118">To address this warning</span></span>  
  
-   <span data-ttu-id="fa07f-119">Ziehen Sie eine Unterdrückung der Warnung nur dann in Betracht, wenn Sie sicher sind, dass Sie nicht auf den Abschluss des asynchronen Aufrufs warten möchten und dass die aufgerufene Methode keine Ausnahmen auslösen wird.</span><span class="sxs-lookup"><span data-stu-id="fa07f-119">You should consider suppressing the warning only if you're sure that you don't want to wait for the asynchronous call to complete and that the called method won't raise any exceptions.</span></span> <span data-ttu-id="fa07f-120">In diesem Fall können Sie die Warnung unterdrücken, indem Sie das Aufgabenergebnis des Aufrufs einer Variablen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fa07f-120">In that case, you can suppress the warning by assigning the task result of the call to a variable.</span></span>  
  
     <span data-ttu-id="fa07f-121">Das folgende Beispiel zeigt, wie Sie die Warnung auslösen und unterdrücken können und wie Sie auf den Aufruf warten können.</span><span class="sxs-lookup"><span data-stu-id="fa07f-121">The following example shows how to cause the warning, how to suppress it, and how to await the call.</span></span>  
  
    ```vb  
    Async Function CallingMethodAsync() As Task  
  
        ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
        ' Variable delay is used to slow down the called method so that you  
        ' can distinguish between awaiting and not awaiting in the program's output.   
        ' You can adjust the value to produce the output that this topic shows   
        ' after the code.  
        Dim delay = 5000  
  
        ' Call #1.  
        ' Call an async method. Because you don't await it, its completion isn't   
        ' coordinated with the current method, CallingMethodAsync.  
        ' The following line causes the warning.  
        CalledMethodAsync(delay)  
  
        ' Call #2.  
        ' To suppress the warning without awaiting, you can assign the   
        ' returned task to a variable. The assignment doesn't change how  
        ' the program runs. However, the recommended practice is always to  
        ' await a call to an async method.  
        ' Replace Call #1 with the following line.  
        'Task delayTask = CalledMethodAsync(delay)  
  
        ' Call #3  
        ' To contrast with an awaited call, replace the unawaited call   
        ' (Call #1 or Call #2) with the following awaited call. The best   
        ' practice is to await the call.  
  
        'Await CalledMethodAsync(delay)  
  
        ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
        ' continues to run and, in this example, finishes its work and returns  
        ' to its caller.  
        ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
    End Function  
  
    Async Function CalledMethodAsync(howLong As Integer) As Task  
  
        ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
        ' Slow the process down a little so you can distinguish between awaiting  
        ' and not awaiting. Adjust the value for howLong if necessary.  
        Await Task.Delay(howLong)  
        ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
    End Function  
    ```  
  
     <span data-ttu-id="fa07f-122">Wenn Sie beispielsweise „Call #1“ oder „Call #2“ wählen, wird die unerwartete asynchrone Methode (`CalledMethodAsync`) beendet, nachdem der Aufrufer (`CallingMethodAsync`) und der Aufrufer des Aufrufers (`StartButton_Click`) abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="fa07f-122">In the example, if you choose Call #1 or Call #2, the unawaited async method (`CalledMethodAsync`) finishes after both its caller (`CallingMethodAsync`) and the caller's caller (`StartButton_Click`) are complete.</span></span> <span data-ttu-id="fa07f-123">Die letzte Zeile in der folgenden Ausgabe zeigt, wann die aufgerufene Methode beendet ist.</span><span class="sxs-lookup"><span data-stu-id="fa07f-123">The last line in the following output shows you when the called method finishes.</span></span> <span data-ttu-id="fa07f-124">Der Eingang und das Ende des Ereignishandlers, der `CallingMethodAsync` im vollständigen Beispiel aufruft, werden in der Ausgabe gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="fa07f-124">Entry to and exit from the event handler that calls `CallingMethodAsync` in the full example are marked in the output.</span></span>  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a><span data-ttu-id="fa07f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa07f-125">Example</span></span>  
 <span data-ttu-id="fa07f-126">Die folgende Windows Presentation Foundation (WPF)-Anwendung enthält die Methoden aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fa07f-126">The following Windows Presentation Foundation (WPF) application contains the methods from the previous example.</span></span> <span data-ttu-id="fa07f-127">Die folgenden Schritte richten die Anwendung ein.</span><span class="sxs-lookup"><span data-stu-id="fa07f-127">The following steps set up the application.</span></span>  
  
1.  <span data-ttu-id="fa07f-128">Erstellen Sie eine WPF-Anwendung, und geben Sie Ihr den Namen `AsyncWarning`.</span><span class="sxs-lookup"><span data-stu-id="fa07f-128">Create a WPF application, and name it `AsyncWarning`.</span></span>  
  
2.  <span data-ttu-id="fa07f-129">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="fa07f-129">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="fa07f-130">Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="fa07f-130">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
3.  <span data-ttu-id="fa07f-131">Ersetzen Sie den Code in der **XAML** -Ansicht der MainWindow.xaml-Datei durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="fa07f-131">Replace the code in the **XAML** view of MainWindow.xaml with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="StartButton_Click" />  
            <TextBox x:Name="ResultsTextBox" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="fa07f-132">Ein einfaches Fenster, das eine Schaltfläche und ein Textfeld enthält, wird in der **Entwurf** -Ansicht der MainWindow.xaml-Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa07f-132">A simple window that contains a button and a text box appears in the **Design** view of MainWindow.xaml.</span></span>  
  
     <span data-ttu-id="fa07f-133">Weitere Informationen zum XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="fa07f-133">For more information about the XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span> <span data-ttu-id="fa07f-134">Informationen zum Erstellen der eigenen einfachen Benutzeroberfläche finden Sie in den Abschnitten „So erstellen Sie eine WPF-Anwendung“ und „So entwerfen Sie ein einfaches WPF-MainWindow“ auf der Seite [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span><span class="sxs-lookup"><span data-stu-id="fa07f-134">For information about how to build your own simple UI, see the "To create a WPF application" and "To design a simple WPF MainWindow" sections of [Walkthrough: Accessing the Web by Using Async and Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span></span>  
  
4.  <span data-ttu-id="fa07f-135">Ersetzen Sie den Code in „MainWindow.xaml.vb“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="fa07f-135">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow   
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
            ResultsTextBox.Text &= vbCrLf & "Entering the Click event handler."  
            Await CallingMethodAsync()  
            ResultsTextBox.Text &= vbCrLf & "Exiting the Click event handler."  
        End Sub  
  
        Async Function CallingMethodAsync() As Task  
  
            ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
            ' Variable delay is used to slow down the called method so that you  
            ' can distinguish between awaiting and not awaiting in the program's output.   
            ' You can adjust the value to produce the output that this topic shows   
            ' after the code.  
            Dim delay = 5000  
  
            ' Call #1.  
            ' Call an async method. Because you don't await it, its completion isn't   
            ' coordinated with the current method, CallingMethodAsync.  
            ' The following line causes the warning.  
            CalledMethodAsync(delay)  
  
            ' Call #2.  
            ' To suppress the warning without awaiting, you can assign the   
            ' returned task to a variable. The assignment doesn't change how  
            ' the program runs. However, the recommended practice is always to  
            ' await a call to an async method.  
  
            ' Replace Call #1 with the following line.  
            'Task delayTask = CalledMethodAsync(delay)  
  
            ' Call #3  
            ' To contrast with an awaited call, replace the unawaited call   
            ' (Call #1 or Call #2) with the following awaited call. The best   
            ' practice is to await the call.  
  
            'Await CalledMethodAsync(delay)  
  
            ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
            ' continues to run and, in this example, finishes its work and returns  
            ' to its caller.  
            ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
        End Function  
  
        Async Function CalledMethodAsync(howLong As Integer) As Task  
  
            ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
            ' Slow the process down a little so you can distinguish between awaiting  
            ' and not awaiting. Adjust the value for howLong if necessary.  
            Await Task.Delay(howLong)  
            ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
        End Function  
  
    End Class  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    '     Task.Delay is finished--returning from called method.  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '     Task.Delay is finished--returning from called method.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    ```  
  
5.  <span data-ttu-id="fa07f-136">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="fa07f-136">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="fa07f-137">Am Ende des Codes wird die erwartete Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa07f-137">The expected output appears at the end of the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa07f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa07f-138">See Also</span></span>  
 [<span data-ttu-id="fa07f-139">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="fa07f-139">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="fa07f-140">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="fa07f-140">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
