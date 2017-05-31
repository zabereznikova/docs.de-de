---
title: async (C# Reference) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- async_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 50e128137fde445f64e10cf7c2a1ee5fdecb34e6
ms.openlocfilehash: e7f4cfa81de3c4db41d9303abf65cfd0edc926a4
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="async-c-reference"></a>async (C#-Referenz)
Mit dem `async`-Modifizierer können Sie angeben, dass eine Methode, ein [Lambdaausdruck](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) oder eine [anonyme Methode](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) asynchron ist. Wenn Sie diesen Modifizierer auf Methoden oder Ausdrücke anwenden, werden sie als Async-Methoden bezeichnet.  
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
  
```  
  
 Wenn Sie mit der asynchronen Programmierung noch nicht vertraut sind oder nicht wissen, wie eine asynchrone Methode das `await`-Schlüsselwort verwendet, um Aufgaben mit potenziell langer Laufzeit auszuführen, ohne den Thread des Aufrufers zu blockieren, sollten Sie die Einführung unter [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md) lesen.  
  
```  
string contents = await contentsTask;  
```  
  
 Die Methode wird bis zum ersten `await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist. In der Zwischenzeit wird die Steuerung an den Aufrufer der Methode zurückgegeben, wie das Beispiel in nächsten Thema zeigt.  
  
 Wenn die Methode, die mit dem `async`-Schlüsselwort geändert wird, keinen `await`-Ausdruck oder keine await-Anweisung enthält, wird die Methode synchron ausgeführt. Mit einer Compilerwarnung werden Sie auf alle Async-Methoden hingewiesen, die kein `await` enthalten, da dies möglicherweise auf einen Fehler hindeutet. Siehe [Compilerwarnung (Stufe 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).  
  
 Das `async`-Schlüsselwort ist insofern kontextabhängig, dass es nur dann ein Schlüsselwort ist, wenn mit ihm eine Methode, ein Lambda-Ausdruck oder eine anonyme Methode geändert wird. In allen anderen Kontexten wird es als Bezeichner interpretiert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Struktur und Ablaufsteuerung zwischen einem asynchronen Ereignishandler, `StartButton_Click`, und einer asynchronen Methode, `ExampleMethodAsync`, veranschaulicht. Das Ergebnis der Async-Methode ist die Länge einer heruntergeladenen Website. Der Code ist für eine Windows Presentation Foundation (WPF)- oder Windows Store-Anwendung geeignet, die Sie in Visual Studio erstellen. Informationen zum Einrichten der Anwendung finden Sie in den Codekommentaren.  
  
```csharp  
// You can run this code in Visual Studio as a WPF app or a Windows Store app.  
// You need a button (StartButton) and a textbox (ResultsTextBox).  
// Remember to set the names and handler so that you have something like this:  
// <Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
//         Click="StartButton_Click" Name="StartButton"/>  
// <TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
//          Text="TextBox" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
  
// To run the code as a WPF app:  
//    paste this code into the MainWindow class in MainWindow.xaml.cs,  
//    add a reference to System.Net.Http, and  
//    add a using directive for System.Net.Http.  
  
// To run the code as a Windows Store app:  
//    paste this code into the MainPage class in MainPage.xaml.cs, and  
//    add using directives for System.Net.Http and System.Threading.Tasks.  
  
private async void StartButton_Click(object sender, RoutedEventArgs e)  
{  
    // ExampleMethodAsync returns a Task<int>, which means that the method  
    // eventually produces an int result. However, ExampleMethodAsync returns  
    // the Task<int> value as soon as it reaches an await.  
    ResultsTextBox.Text += "\n";  
    try  
    {  
        int length = await ExampleMethodAsync();  
        // Note that you could put "await ExampleMethodAsync()" in the next line where  
        // "length" is, but due to when '+=' fetches the value of ResultsTextBox, you  
        // would not see the global side effect of ExampleMethodAsync setting the text.  
        ResultsTextBox.Text += String.Format("Length: {0}\n", length);  
    }  
    catch (Exception)  
    {  
        // Process the exception if one occurs.  
    }  
}  
  
public async Task<int> ExampleMethodAsync()  
{  
    var httpClient = new HttpClient();  
    int exampleInt = (await httpClient.GetStringAsync("http://msdn.microsoft.com")).Length;  
    ResultsTextBox.Text += "Preparing to finish ExampleMethodAsync.\n";  
    // After the following return statement, any method that's awaiting  
    // ExampleMethodAsync (in this case, StartButton_Click) can get the   
    // integer result.  
    return exampleInt;  
}  
// Output:  
// Preparing to finish ExampleMethodAsync.  
// Length: 53292  
  
```  
  
> [!IMPORTANT]
>  Weitere Informationen zu Aufgaben und zum Code, der während des Wartens auf eine Aufgabe ausgeführt wird, finden Sie unter [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md). Ein vollständiges Beispiel für WPF, das ähnliche Elemente verwendet, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web durch Verwenden von Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können den Code der exemplarischen Vorgehensweise unter [Codebeispiele für Entwickler](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.  
  
## <a name="return-types"></a>Rückgabetypen  
 Eine asynchrone Methode kann den Rückgabetyp <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> oder [void](../../../csharp/language-reference/keywords/void.md) haben. Mit der Methode können keine [ref](../../../csharp/language-reference/keywords/ref.md)- oder [out](../../../csharp/language-reference/keywords/out.md)-Parameter deklariert, aber Methoden aufgerufen werden, die solche Parameter aufweisen.  
  
 `Task<TResult>` wird als Rückgabetyp einer Async-Methode angegeben, wenn mit der [return](../../../csharp/language-reference/keywords/return.md)-Anweisung der Methode ein Operand vom Typ `TResult` angegeben wird. `Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist. Das bedeutet, dass ein Aufruf der Methode einen `Task` zurückgibt. Wenn der `Task` aber abgeschlossen ist, wird jeder `await`-Ausdruck, der auf den `Task` wartet, als `void` ausgewertet.  
  
 Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, die diesen Rückgabetyp erfordern. Der Aufrufer einer Async-Methode, die `void` zurückgibt, kann auf ihn nicht warten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.  
  
 Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../../csharp/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [await](../../../csharp/language-reference/keywords/await.md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)   
 [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md)
