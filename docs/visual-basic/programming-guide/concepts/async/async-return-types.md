---
title: "Asynchrone Rückgabetypen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a>Asynchrone Rückgabetypen (Visual Basic)
Asynchrone Methoden haben drei mögliche Rückgabetypen: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, und void.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> In Visual Basic wird der void-Rückgabetyp als geschrieben ein [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Verfahren. Weitere Informationen über asynchrone Methoden finden Sie unter [asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Jeder Rückgabetyp wird in einem der folgenden Abschnitte untersucht und am Ende des Themas wird ein vollständiges Beispiel aller drei Typen verwenden.  
  
> [!NOTE]
>  Zum Ausführen des Beispiels müssen Sie Visual Studio 2012 oder höher und .NET Framework 4.5 oder höher auf Ihrem Computer installiert.  
  
##  <a name="BKMK_TaskTReturnType"></a>Task(t)-Rückgabetyp  
 Die <xref:System.Threading.Tasks.Task%601>Rückgabetyp wird für eine asynchrone Methode, die enthält verwendet eine [zurückgeben](../../../../visual-basic/language-reference/statements/return-statement.md) Anweisung, in der der Operand weist den Typ `TResult`.</xref:System.Threading.Tasks.Task%601>  
  
 Im folgenden Beispiel enthält die asynchrone `TaskOfT_MethodAsync`-Methode eine "return"-Anweisung, die eine ganze Zahl zurückgibt. Daher muss die Methodendeklaration einen Rückgabetyp angeben `Task(Of Integer)`.  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 Wenn `TaskOfT_MethodAsync` aus einem "await"-Ausdruck aufgerufen wird, ruft der "await"-Ausdruck den ganzzahligen Wert ab (der Wert von `leisureHours`), der in der Aufgabe gespeichert wird, die von `TaskOfT_MethodAsync` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken, finden Sie unter [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md).  
  
 Der folgende Code ruft auf und erwartet die `TaskOfT_MethodAsync`-Methode. Das Ergebnis wird der `result1`-Variablen zugewiesen.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 Sie können besser verstehen, wie dies geschieht durch die Trennung des Aufrufs von `TaskOfT_MethodAsync` aus der Anwendung von `Await`, wie der folgende Code zeigt. Ein Aufruf der Methode `TaskOfT_MethodAsync` , die nicht sofort eine Antwort erwartet gibt eine `Task(Of Integer)`, wie Sie in der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen. Da `integerTask` ist eine <xref:System.Threading.Tasks.Task%601>, er enthält eine <xref:System.Threading.Tasks.Task%601.Result>Eigenschaft vom Typ `TResult`.</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601> In diesem Fall stellt TResult einen ganzzahligen Typ dar. Wenn `Await` gilt für `integerTask`, der Await-Ausdruck wertet den Inhalt von der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft des `integerTask`.</xref:System.Threading.Tasks.Task%601.Result%2A> Der Wert wird der `result2`-Variablen zugewiesen.  
  
> [!WARNING]
>  Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine blocking-Eigenschaft.</xref:System.Threading.Tasks.Task%601.Result%2A> Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie den Wert zugreifen, indem Sie mithilfe von `Await` anstatt direkt auf die Eigenschaft.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 Die Anzeigeanweisungen im folgenden Code überprüfen, dass die Werte der `result1`-Variable, der `result2`-Variable und der `Result`-Eigenschaft gleich sind. Beachten Sie, dass die `Result`-Eigenschaft eine Blocking-Eigenschaft ist und nicht darauf zugegriffen werden sollte, bevor die Aufgabe abgeschlossen wurde.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a>Aufgabenrückgabetyp  
 Async-Methoden, die eine return-Anweisung keine enthalten oder eine return-Anweisung, die einen Operanden in der Regel zurückgibt enthalten, haben einen Rückgabetyp <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> Solche Methoden wäre [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Verfahren aus, wenn sie eine synchrone Ausführung geschrieben wurden. Bei Verwendung einer `Task` Rückgabetyp für eine asynchrone Methode eine Aufrufmethode können eine `Await` Operator, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode abgeschlossen ist.  
  
 Im folgenden Beispiel enthält die asynchrone `Task_MethodAsync`-Methode keine "return"-Anweisung. Daher geben Sie einen `Task`-Rückgabetyp für die Methode an, die `Task_MethodAsync` ein Warten ermöglicht. Die Definition des `Task`-Typs enthält keine `Result`-Eigenschaft, um einen Rückgabewert zu speichern.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync` wird aufgerufen und erwartet, indem eine "await"-Anweisung anstelle eines "await"-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung für ein synchrones `Sub` oder eine Methode, die "void" zurückgibt. Die Anwendung von einer `Await` Operator erzeugt in diesem Fall nicht Wert.  
  
 Der folgende Code ruft auf und erwartet die `Task_MethodAsync`-Methode.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 Wie im vorherigen <xref:System.Threading.Tasks.Task%601>beispielsweise können Sie den Aufruf von trennen `Task_MethodAsync` aus der Anwendung von einer `Await` -Operator, wie im folgenden Code gezeigt.</xref:System.Threading.Tasks.Task%601> Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.  
  
 Der folgende Code trennt Aufrufe von `Task_MethodAsync` vom Erwarten der Aufgabe, die `Task_MethodAsync` zurückgibt.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a>Rückgabetyp "void"  
 Der Hauptverwendungszweck des `Sub` Verfahren ist im Ereignishandler keinen Rückgabetyp (bezeichnet als einen void-Rückgabetyp in anderen Sprachen) vorhanden ist. Eine "void"-Rückgabe kann auch verwendet werden, um Methoden mit einer "void"-Rückgabe zu überschreiben, oder auch für Methoden, die "Fire-and-Forget"-Aktivitäten ausführen. Sie sollten nach Möglichkeit immer eine `Task` zurückgeben, da eine "void" zurückgebende asynchrone Methode nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss in der Lage sein, in seiner Ausführung bis zum Abschluss fortzufahren, ohne auf die aufgerufene asynchrone Methode zu warten, und der Aufrufer muss unabhängig von den Werten oder Ausnahmen sein, die die asynchrone Methode generiert.  
  
 Der Aufrufer einer "void" zurückgebenden asynchronen Methode kann die von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Ausnahme in einer asynchronen Methode auftritt, der gibt ein <xref:System.Threading.Tasks.Task>oder <xref:System.Threading.Tasks.Task%601>, wird die Ausnahme in der zurückgegebenen Aufgabe gespeichert und erneut ausgelöst, wenn die Aufgabe erwartet wird.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task> Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann einen Rückgabetyp hat <xref:System.Threading.Tasks.Task>oder <xref:System.Threading.Tasks.Task%601>und die Aufrufe der Methode erwartet werden.</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task>  
  
 Weitere Informationen zum Abfangen von Ausnahmen in Async-Methoden finden Sie unter [versuchen... Catch... Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
 Der folgende Code definiert einen asynchrone Ereignishandler.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a>Vollständiges Beispiel  
 Das nächste Windows Presentation Foundation (WPF)-Projekt enthält die Codebeispiele aus diesem Thema.  
  
 Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **installierte**, **Vorlagen** (Kategorie), wählen Sie **Visual Basic**, und wählen Sie dann **Windows**. Wählen Sie **WPF-Anwendung** aus der Liste der Projekttypen.  
  
4.  Geben Sie `AsyncReturnTypes` als Namen für das Projekt, und wählen Sie dann die **OK** Schaltfläche.  
  
     Das neue Projekt wird im **Projektmappen-Explorer**.  
  
5.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
     Wenn die Registerkarte nicht angezeigt wird, öffnen Sie das Kontextmenü für "MainWindow.xaml" im **Projektmappen-Explorer**, und wählen Sie dann **öffnen**.  
  
6.  In der **XAML** Fenster von "MainWindow.xaml", ersetzen Sie den Code durch den folgenden Code.  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird angezeigt, der **Design** im Fenster.  
  
7.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Anzeigecode**.  
  
8.  Ersetzen Sie den Code in „MainWindow.xaml.vb“ durch den folgenden Code.  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
     Es sollte folgende Ausgabe angezeigt werden.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [Async](../../../../visual-basic/language-reference/modifiers/async.md)   
 [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md)
