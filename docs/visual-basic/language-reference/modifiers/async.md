---
title: Async (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e11bb7eb29cefa627543e8ad0a9b061d5ad1e95c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="async-visual-basic"></a>Async (Visual Basic)
Die `Async` Modifizierer gibt an, dass die Methode oder [Lambda-Ausdruck](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) ändert asynchron ist. Solche Methoden werden als bezeichnet *Async-Methoden*.  
  
 Mit einer Async-Methode können Aufgaben mit potenziell langer Laufzeit auf einfache Weise ausgeführt werden, ohne den Thread des Aufrufers zu blockieren. Der Aufrufer einer Async-Methode kann seine Arbeit fortsetzen, ohne auf die Fertigstellung der Async-Methode zu warten.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt. Eine Einführung in die asynchrone Programmierung, finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Im folgenden Beispiel wird die Struktur einer asynchronen Methode veranschaulicht. Laut Konvention enden die Namen von asynchrone Methoden mit "Async."  
  
```vb  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 Eine Methode in der Regel wird geändert, indem die `Async` Schlüsselwort enthält mindestens ein ["await"](../../../visual-basic/language-reference/modifiers/async.md) Ausdruck oder Anweisung. Die Methode wird bis zum ersten `Await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist. In der Zwischenzeit wird die Steuerung zum Aufrufer der Methode zurückgegeben. Wenn die Methode keinen `Await`-Ausdruck oder keine Await-Anweisung enthält, wird die Methode nicht angehalten und wie eine synchrone Methode ausgeführt. Mit einer Compilerwarnung werden Sie auf alle Async-Methoden hingewiesen, die kein `Await` enthalten, da dies möglicherweise auf einen Fehler hindeutet. Weitere Informationen finden Sie unter der [Compilerfehler](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 Das Schlüsselwort `Async` ist ein nicht reserviertes Schlüsselwort. Es ist ein Schlüsselwort, wenn eine Methode oder ein Lambda-Ausdruck geändert wird. In allen anderen Kontexten wird es als Bezeichner interpretiert.  
  
## <a name="return-types"></a>Rückgabetypen  
 Eine asynchrone Methode ist entweder ein [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Prozedur oder eine [Funktion](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) Prozedur, die einen Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>. Die Methode kann nicht deklariert werden alle [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.  
  
 Geben Sie `Task(Of TResult)` für den Rückgabetyp einer Async-Methode Wenn die [zurückgeben](../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung der Methode wurde einen Operand vom Typ TResult enthält. `Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist. Das bedeutet, dass ein Aufruf der Methode eine `Task` zurückgibt, aber wenn die `Task` abgeschlossen ist, erzeugt eine `Await`-Anweisung, die `Task` erwartet, keinen Ergebniswert.  
  
 Asynchrone Unterroutinen werden hauptsächlich verwendet, um Ereignishandler zu definieren, in denen eine `Sub` Prozedur erforderlich ist. Der Aufrufer einer Async-Unterroutine kann diese nicht erwarten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.  
  
 Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen werden ein asynchroner Ereignishandler, ein asynchroner Lambdaausdruck und eine asynchrone Methode dargestellt. Ein vollständiges Beispiel, die diese Elemente verwendet werden, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web durch Verwenden von Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können den Code der exemplarischen Vorgehensweise unter [Codebeispiele für Entwickler](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.  
  
```vb  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("http://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)  
 [Asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md)  
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
