---
title: "Asynchrone Rückgabetypen (C#) | Microsoft-Dokumentation"
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
ms.assetid: ddb2539c-c898-48c1-ad92-245e4a996df8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4c1bab99fc1139f03e5f754cfecaee392b947171
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-c"></a>Asynchrone Rückgabetypen (C#)
Asynchrone Methoden haben drei mögliche Rückgabetypen: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> und „void“. In Visual Basic wird der void-Rückgabetyp als [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)-Prozedur geschrieben. Weitere Informationen über die Methode „Async“ finden Sie unter [Asynchronous Programming with async and await (C#) (Asynchrone Programmierung mit Async und Await (C#))](../../../../csharp/programming-guide/concepts/async/index.md).  
  
 Jeder Rückgabetyp wird in einem der folgenden Abschnitte untersucht und am Ende des Themas wird ein vollständiges Beispiel aller drei Typen verwenden.  
  
> [!NOTE]
>  Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.  
  
##  <a name="BKMK_TaskTReturnType"></a> Task(T)-Rückgabetyp  
 Der <xref:System.Threading.Tasks.Task%601>-Rückgabetyp wird für eine asynchrone Methode verwendet, die eine [return](../../../../csharp/language-reference/keywords/return.md)-Anweisung (C#) enthält, in der der Operand den Typ `TResult` hat.  
  
 Im folgenden Beispiel enthält die asynchrone `TaskOfT_MethodAsync`-Methode eine "return"-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task<int>` haben.  
  
```cs  
// TASK<T> EXAMPLE  
async Task<int> TaskOfT_MethodAsync()  
{  
    // The body of the method is expected to contain an awaited asynchronous  
    // call.  
    // Task.FromResult is a placeholder for actual work that returns a string.  
    var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
    // The method then can process the result in some way.  
    int leisureHours;  
    if (today.First() == 'S')  
        leisureHours = 16;  
    else  
        leisureHours = 5;  
  
    // Because the return statement specifies an operand of type int, the  
    // method must have a return type of Task<int>.  
    return leisureHours;  
}  
```  
  
 Wenn `TaskOfT_MethodAsync` aus einem "await"-Ausdruck aufgerufen wird, ruft der "await"-Ausdruck den ganzzahligen Wert ab (der Wert von `leisureHours`), der in der Aufgabe gespeichert wird, die von `TaskOfT_MethodAsync` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken finden Sie unter [await](../../../../csharp/language-reference/keywords/await.md).  
  
 Der folgende Code ruft auf und erwartet die `TaskOfT_MethodAsync`-Methode. Das Ergebnis wird der `result1`-Variablen zugewiesen.  
  
```cs  
// Call and await the Task<T>-returning async method in the same statement.  
int result1 = await TaskOfT_MethodAsync();  
```  
  
 Sie können die Vorgehensweise besser verstehen, wenn Sie den Aufruf von `TaskOfT_MethodAsync` von der Anwendung von `await` trennen, wie der folgenden Code zeigt. Ein Aufruf der `TaskOfT_MethodAsync`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task<int>` zurück, wie Sie es von der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen. Weil `integerTask` ein <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`. In diesem Fall stellt TResult einen ganzzahligen Typ dar. Wenn `await` auf `integerTask` angewendet wird, ergibt der await-Ausdruck die Inhalte der <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft von `integerTask`. Der Wert wird der `result2`-Variablen zugewiesen.  
  
> [!WARNING]
>  Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft. Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen.  
  
```cs  
// Call and await in separate statements.  
Task<int> integerTask = TaskOfT_MethodAsync();  
  
// You can do other work that does not rely on integerTask before awaiting.  
textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
int result2 = await integerTask;  
```  
  
 Die Anzeigeanweisungen im folgenden Code überprüfen, dass die Werte der `result1`-Variable, der `result2`-Variable und der `Result`-Eigenschaft gleich sind. Beachten Sie, dass die `Result`-Eigenschaft eine Blocking-Eigenschaft ist und nicht darauf zugegriffen werden sollte, bevor die Aufgabe abgeschlossen wurde.  
  
```cs  
// Display the values of the result1 variable, the result2 variable, and  
// the integerTask.Result property.  
textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
```  
  
##  <a name="BKMK_TaskReturnType"></a> Aufgabenrückgabetyp  
 Asynchrone Methoden, die keine return-Anweisung enthalten oder eine return-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>. Solche Methoden würden „void“ als Rückgabewert liefern, wenn sie für eine synchrone Ausführung geschrieben wurden. Wenn Sie einen `Task`-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen Erwartungsoperator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.  
  
 Im folgenden Beispiel enthält die asynchrone `Task_MethodAsync`-Methode keine "return"-Anweisung. Daher geben Sie einen `Task`-Rückgabetyp für die Methode an, die `Task_MethodAsync` ein Warten ermöglicht. Die Definition des `Task`-Typs enthält keine `Result`-Eigenschaft, um einen Rückgabewert zu speichern.  
  
```cs  
// TASK EXAMPLE  
async Task Task_MethodAsync()  
{  
    // The body of an async method is expected to contain an awaited   
    // asynchronous call.  
    // Task.Delay is a placeholder for actual work.  
    await Task.Delay(2000);  
    // Task.Delay delays the following line by two seconds.  
    textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
    // This method has no return statement, so its return type is Task.    
}  
```  
  
 `Task_MethodAsync` wird aufgerufen und erwartet, indem eine „await“-Anweisung anstelle eines „await“-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung einer Methode, die „void“ zurückgibt. Die Anwendung eines Erwartungsoperators erzeugt in diesem Fall keinen Wert.  
  
 Der folgende Code ruft auf und erwartet die `Task_MethodAsync`-Methode.  
  
```cs  
// Call and await the Task-returning async method in the same statement.  
await Task_MethodAsync();  
```  
  
 Wie im vorherigen Beispiel <xref:System.Threading.Tasks.Task%601> können Sie den Aufruf von `Task_MethodAsync` mit einem await-Operator trennen, wie der folgende Code zeigt. Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.  
  
 Der folgende Code trennt Aufrufe von `Task_MethodAsync` vom Erwarten der Aufgabe, die `Task_MethodAsync` zurückgibt.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
##  <a name="BKMK_VoidReturnType"></a> Rückgabetyp „Void“  
 Der Hauptverwendungszweck des „void“-Rückgabetyps liegt in den Ereignishandlern, für die ein „void“-Rückgabetyp erforderlich ist. Eine "void"-Rückgabe kann auch verwendet werden, um Methoden mit einer "void"-Rückgabe zu überschreiben, oder auch für Methoden, die "Fire-and-Forget"-Aktivitäten ausführen. Sie sollten nach Möglichkeit immer eine `Task` zurückgeben, da eine "void" zurückgebende asynchrone Methode nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss in der Lage sein, in seiner Ausführung bis zum Abschluss fortzufahren, ohne auf die aufgerufene asynchrone Methode zu warten, und der Aufrufer muss unabhängig von den Werten oder Ausnahmen sein, die die asynchrone Methode generiert.  
  
 Der Aufrufer einer "void" zurückgebenden asynchronen Methode kann die von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Ausnahme in einer asynchronen Methode auftritt, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, wird die Ausnahme in der zurückgegebenen Aufgabe gespeichert und erneut ausgelöst, wenn die Aufgabe erwartet wird. Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt, und die Aufrufe der Methode erwartet werden.  
  
 Weitere Informationen zum Auffangen von Ausnahmen in async-Methoden finden Sie unter [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).  
  
 Der folgende Code definiert einen asynchrone Ereignishandler.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
##  <a name="BKMK_Example"></a> Vollständiges Beispiel  
 Das nächste Windows Presentation Foundation (WPF)-Projekt enthält die Codebeispiele aus diesem Thema.  
  
 Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  Wählen Sie in **Installiert** die Kategorie **Vorlagen** aus, wählen Sie Visual C# und dann **Windows** aus. Wählen Sie in der Liste der Projekttypen die **WPF-Anwendung** aus.  
  
4.  Geben Sie `AsyncReturnTypes` als Namen für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
5.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
     Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer** und wählen dann **Öffnen** aus.  
  
6.  Ersetzen Sie den Code im Fenster **XAML** von „MainWindow.xaml“ durch den folgenden Code.  
  
    ```cs  
    <Window x:Class="AsyncReturnTypes.MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird im Fenster **Entwurf** von „MainWindow.xaml“ angezeigt.  
  
7.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für „MainWindow.xaml.cs“, und wählen Sie dann **Code anzeigen** aus.  
  
8.  Ersetzen Sie den Code in „MainWindow.xaml.cs“ durch den folgenden Code.  
  
    ```cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.Threading.Tasks;  
    using System.Windows;  
    using System.Windows.Controls;  
    using System.Windows.Data;  
    using System.Windows.Documents;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    using System.Windows.Media.Imaging;  
    using System.Windows.Navigation;  
    using System.Windows.Shapes;  
  
    namespace AsyncReturnTypes  
    {  
        public partial class MainWindow : Window  
        {  
            public MainWindow()  
            {  
                InitializeComponent();  
            }  
  
            // VOID EXAMPLE  
            private async void button1_Click(object sender, RoutedEventArgs e)  
            {  
                textBox1.Clear();  
  
                // Start the process and await its completion. DriverAsync is a   
                // Task-returning async method.  
                await DriverAsync();  
  
                // Say goodbye.  
                textBox1.Text += "\r\nAll done, exiting button-click event handler.";  
            }  
  
            async Task DriverAsync()  
            {  
                // Task<T>   
                // Call and await the Task<T>-returning async method in the same statement.  
                int result1 = await TaskOfT_MethodAsync();  
  
                // Call and await in separate statements.  
                Task<int> integerTask = TaskOfT_MethodAsync();  
  
                // You can do other work that does not rely on integerTask before awaiting.  
                textBox1.Text += String.Format("Application can continue working while the Task<T> runs. . . . \r\n");  
  
                int result2 = await integerTask;  
  
                // Display the values of the result1 variable, the result2 variable, and  
                // the integerTask.Result property.  
                textBox1.Text += String.Format("\r\nValue of result1 variable:   {0}\r\n", result1);  
                textBox1.Text += String.Format("Value of result2 variable:   {0}\r\n", result2);  
                textBox1.Text += String.Format("Value of integerTask.Result: {0}\r\n", integerTask.Result);  
  
                // Task  
                // Call and await the Task-returning async method in the same statement.  
                await Task_MethodAsync();  
  
                // Call and await in separate statements.  
                Task simpleTask = Task_MethodAsync();  
  
                // You can do other work that does not rely on simpleTask before awaiting.  
                textBox1.Text += String.Format("\r\nApplication can continue working while the Task runs. . . .\r\n");  
  
                await simpleTask;  
            }  
  
            // TASK<T> EXAMPLE  
            async Task<int> TaskOfT_MethodAsync()  
            {  
                // The body of the method is expected to contain an awaited asynchronous  
                // call.  
                // Task.FromResult is a placeholder for actual work that returns a string.  
                var today = await Task.FromResult<string>(DateTime.Now.DayOfWeek.ToString());  
  
                // The method then can process the result in some way.  
                int leisureHours;  
                if (today.First() == 'S')  
                    leisureHours = 16;  
                else  
                    leisureHours = 5;  
  
                // Because the return statement specifies an operand of type int, the  
                // method must have a return type of Task<int>.  
                return leisureHours;  
            }  
  
            // TASK EXAMPLE  
            async Task Task_MethodAsync()  
            {  
                // The body of an async method is expected to contain an awaited   
                // asynchronous call.  
                // Task.Delay is a placeholder for actual work.  
                await Task.Delay(2000);  
                // Task.Delay delays the following line by two seconds.  
                textBox1.Text += String.Format("\r\nSorry for the delay. . . .\r\n");  
  
                // This method has no return statement, so its return type is Task.    
            }  
        }  
    }  
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
 <xref:System.Threading.Tasks.Task.FromResult%2A>   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit async und await (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Ablaufsteuerung in asynchronen Programmen](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)   
 [async](../../../../csharp/language-reference/keywords/async.md)   
 [await](../../../../csharp/language-reference/keywords/await.md)
