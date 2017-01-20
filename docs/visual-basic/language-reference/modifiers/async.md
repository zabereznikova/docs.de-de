---
title: "Async (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Async"
helpviewer_keywords: 
  - "Async [Visual Basic]"
  - "Async keyword [Visual Basic]"
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
caps.latest.revision: 37
caps.handback.revision: 37
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Async (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der Modifizierer `Async` gibt an, dass die von ihm geänderte Methode oder der von ihm geänderte [Lambda\-Ausdruck](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) asynchron ist.  Solche Methoden werden als *asynchrone Methoden* bezeichnet.  
  
 Mit einer Async\-Methode können Aufgaben mit potenziell langer Laufzeit auf einfache Weise ausgeführt werden, ohne den Thread des Aufrufers zu blockieren.  Der Aufrufer einer Async\-Methode kann seine Arbeit fortsetzen, ohne auf die Fertigstellung der Async\-Methode zu warten.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.  Eine Einführung in die Grundlagen der asynchronen Programmierung finden Sie unter [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Im folgenden Beispiel wird die Struktur einer asynchronen Methode veranschaulicht.  Laut Konvention enden die Namen von asynchrone Methoden mit "Async."  
  
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
  
 In der Regel enthält eine Methode, die mit dem `Async`\-Schlüsselwort geändert wird, mindestens einen [Await](../../../visual-basic/language-reference/modifiers/async.md)\-Ausdruck oder eine Await\-Anweisung.  Die Methode wird bis zum ersten `Await`\-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.  In der Zwischenzeit wird die Steuerung zum Aufrufer der Methode zurückgegeben.  Wenn die Methode keinen `Await`\-Ausdruck oder keine Await\-Anweisung enthält, wird die Methode nicht angehalten und wie eine synchrone Methode ausgeführt.  Mit einer Compilerwarnung werden Sie auf alle Async\-Methoden hingewiesen, die kein `Await` enthalten, da dies möglicherweise auf einen Fehler hindeutet.  Weitere Informationen finden Sie unter [Compilerfehler](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 Das Schlüsselwort `Async` ist ein nicht reserviertes Schlüsselwort.  Es ist ein Schlüsselwort, wenn eine Methode oder ein Lambda\-Ausdruck geändert wird.  In allen anderen Kontexten wird es als Bezeichner interpretiert.  
  
## Rückgabetypen  
 Eine asynchrone Methode ist entweder eine [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)\- oder eine [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)\-Prozedur, die einen Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> hat.  Die Methode kann keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)\-Parameter deklarieren.  
  
 `Task(Of TResult)` wird als Rückgabetyp einer Async\-Methode angegeben, wenn die [Return](../../../visual-basic/language-reference/statements/return-statement.md)\-Anweisung der Methode einen Operanden vom Typ TResult enthält.  `Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist.  Das bedeutet, dass ein Aufruf der Methode eine `Task` zurückgibt, aber wenn die `Task` abgeschlossen ist, erzeugt eine `Await`\-Anweisung, die `Task` erwartet, keinen Ergebniswert.  
  
 Asynchrone Unterroutinen werden hauptsächlich verwendet, um Ereignishandler zu definieren, in denen eine `Sub` Prozedur erforderlich ist.  Der Aufrufer einer Async\-Unterroutine kann diese nicht erwarten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.  
  
 Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Beispiel  
 In den folgenden Beispielen werden ein asynchroner Ereignishandler, ein asynchroner Lambda\-Ausdruck und eine asynchrone Methode dargestellt.  Ein vollständiges Beispiel, in dem diese Elemente verwendet werden, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  Sie können den Code der exemplarischen Vorgehensweise auf der Seite für [Codebeispiele für Entwickler](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.  
  
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
  
## Siehe auch  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>   
 [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Asynchrone Programmierung mit Async und Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../Topic/Walkthrough:%20Accessing%20the%20Web%20by%20Using%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)