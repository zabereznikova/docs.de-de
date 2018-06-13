---
title: Da auf diesen Aufruf nicht gewartet wird, wird die aktuelle Methode vor Abschluss des Aufrufs fortgesetzt
ms.date: 07/20/2015
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
ms.openlocfilehash: 754fc6750e63f6d9f39da94041fc452829bca46d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591433"
---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a>Da auf diesen Aufruf nicht gewartet wird, wird die aktuelle Methode vor Abschluss des Aufrufs fortgesetzt
Da auf diesen Aufruf nicht gewartet wird, wird die Ausführung der aktuellen Methode vor Abschluss des Aufrufs fortgesetzt. Ziehen Sie ein Anwenden des „Await“-Operators auf das Ergebnis des Aufrufs in Betracht.  
  
 Die aktuelle Methode ruft eine asynchrone Methode auf, die ein <xref:System.Threading.Tasks.Task> oder ein <xref:System.Threading.Tasks.Task%601> zurückgibt und nicht den [Await](../../../visual-basic/language-reference/operators/await-operator.md) -Operator auf das Ergebnis anwendet. Der Aufruf der asynchronen Methode startet eine asynchrone Aufgabe. Da jedoch kein `Await` -Operator angewendet wird, wird das Programm fortgesetzt, ohne auf den Abschluss der Aufgabe zu warten. Dieses Verhalten wird in den meisten Fällen nicht erwartet. Andere Aspekte der aufrufenden Methode hängen in der Regel von den Ergebnissen des Aufrufs ab, mindestens jedoch wird erwartet, dass die aufgerufene Methode abgeschlossen wird, bevor Sie von der Methode zurückgegeben, die den Aufruf enthält.  
  
 Ein gleichermaßen wichtiges Problem besteht in der Behandlung von Ausnahmen, die in der aufgerufenen asynchrone Methode ausgelöst werden. Eine Ausnahme, die in einer Methode ausgelöst wird, die ein <xref:System.Threading.Tasks.Task> oder  <xref:System.Threading.Tasks.Task%601> zurückgibt, wird in der zurückgegebenen Aufgabe gespeichert. Wenn Sie nicht auf die Aufgabe warten oder explizit auf Ausnahmen hin prüfen, geht die Ausnahme verloren. Wenn Sie auf die Aufgabe warten, wird die Ausnahme erneut ausgelöst.  
  
 Als bewährte Methode sollten Sie immer auf den Aufruf warten.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42358  
  
### <a name="to-address-this-warning"></a>So reagieren Sie auf diese Warnung  
  
-   Ziehen Sie eine Unterdrückung der Warnung nur dann in Betracht, wenn Sie sicher sind, dass Sie nicht auf den Abschluss des asynchronen Aufrufs warten möchten und dass die aufgerufene Methode keine Ausnahmen auslösen wird. In diesem Fall können Sie die Warnung unterdrücken, indem Sie das Aufgabenergebnis des Aufrufs einer Variablen zuweisen.  
  
     Das folgende Beispiel zeigt, wie Sie die Warnung auslösen und unterdrücken können und wie Sie auf den Aufruf warten können.  
  
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
  
     Wenn Sie beispielsweise „Call #1“ oder „Call #2“ wählen, wird die unerwartete asynchrone Methode (`CalledMethodAsync`) beendet, nachdem der Aufrufer (`CallingMethodAsync`) und der Aufrufer des Aufrufers (`StartButton_Click`) abgeschlossen sind. Die letzte Zeile in der folgenden Ausgabe zeigt, wann die aufgerufene Methode beendet ist. Der Eingang und das Ende des Ereignishandlers, der `CallingMethodAsync` im vollständigen Beispiel aufruft, werden in der Ausgabe gekennzeichnet.  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a>Beispiel  
 Die folgende Windows Presentation Foundation (WPF)-Anwendung enthält die Methoden aus dem vorherigen Beispiel. Die folgenden Schritte richten die Anwendung ein.  
  
1.  Erstellen Sie eine WPF-Anwendung, und geben Sie Ihr den Namen `AsyncWarning`.  
  
2.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
     Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer**, und wählen Sie dann **Code anzeigen**aus.  
  
3.  Ersetzen Sie den Code in der **XAML** -Ansicht der MainWindow.xaml-Datei durch den folgenden Code.  
  
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
  
     Ein einfaches Fenster, das eine Schaltfläche und ein Textfeld enthält, wird in der **Entwurf** -Ansicht der MainWindow.xaml-Datei angezeigt.  
  
     Weitere Informationen zum XAML-Designer finden Sie unter [Erstellen einer Benutzeroberfläche mit dem XAML-Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio). Informationen zum Erstellen der eigenen einfachen Benutzeroberfläche finden Sie in den Abschnitten „So erstellen Sie eine WPF-Anwendung“ und „So entwerfen Sie ein einfaches WPF-MainWindow“ auf der Seite [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).  
  
4.  Ersetzen Sie den Code in „MainWindow.xaml.vb“ durch den folgenden Code.  
  
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
  
5.  Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
     Am Ende des Codes wird die erwartete Ausgabe angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)  
 [Asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md)
