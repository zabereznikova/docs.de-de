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
# <a name="async-visual-basic"></a><span data-ttu-id="e7a36-102">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7a36-102">Async (Visual Basic)</span></span>
<span data-ttu-id="e7a36-103">Die `Async` Modifizierer gibt an, dass die Methode oder [Lambda-Ausdruck](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) ändert asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="e7a36-103">The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="e7a36-104">Solche Methoden werden als bezeichnet *Async-Methoden*.</span><span class="sxs-lookup"><span data-stu-id="e7a36-104">Such methods are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="e7a36-105">Mit einer Async-Methode können Aufgaben mit potenziell langer Laufzeit auf einfache Weise ausgeführt werden, ohne den Thread des Aufrufers zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="e7a36-105">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="e7a36-106">Der Aufrufer einer Async-Methode kann seine Arbeit fortsetzen, ohne auf die Fertigstellung der Async-Methode zu warten.</span><span class="sxs-lookup"><span data-stu-id="e7a36-106">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7a36-107">Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e7a36-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="e7a36-108">Eine Einführung in die asynchrone Programmierung, finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="e7a36-109">Im folgenden Beispiel wird die Struktur einer asynchronen Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e7a36-109">The following example shows the structure of an async method.</span></span> <span data-ttu-id="e7a36-110">Laut Konvention enden die Namen von asynchrone Methoden mit "Async."</span><span class="sxs-lookup"><span data-stu-id="e7a36-110">By convention, async method names end in "Async."</span></span>  
  
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
  
 <span data-ttu-id="e7a36-111">Eine Methode in der Regel wird geändert, indem die `Async` Schlüsselwort enthält mindestens ein ["await"](../../../visual-basic/language-reference/modifiers/async.md) Ausdruck oder Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e7a36-111">Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement.</span></span> <span data-ttu-id="e7a36-112">Die Methode wird bis zum ersten `Await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e7a36-112">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="e7a36-113">In der Zwischenzeit wird die Steuerung zum Aufrufer der Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7a36-113">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="e7a36-114">Wenn die Methode keinen `Await`-Ausdruck oder keine Await-Anweisung enthält, wird die Methode nicht angehalten und wie eine synchrone Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7a36-114">If the method doesn’t contain an `Await` expression or statement, the method isn’t suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="e7a36-115">Mit einer Compilerwarnung werden Sie auf alle Async-Methoden hingewiesen, die kein `Await` enthalten, da dies möglicherweise auf einen Fehler hindeutet.</span><span class="sxs-lookup"><span data-stu-id="e7a36-115">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="e7a36-116">Weitere Informationen finden Sie unter der [Compilerfehler](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-116">For more information, see the [compiler error](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).</span></span>  
  
 <span data-ttu-id="e7a36-117">Das Schlüsselwort `Async` ist ein nicht reserviertes Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e7a36-117">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="e7a36-118">Es ist ein Schlüsselwort, wenn eine Methode oder ein Lambda-Ausdruck geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e7a36-118">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="e7a36-119">In allen anderen Kontexten wird es als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e7a36-119">In all other contexts, it is interpreted as an identifier.</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="e7a36-120">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="e7a36-120">Return Types</span></span>  
 <span data-ttu-id="e7a36-121">Eine asynchrone Methode ist entweder ein [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Prozedur oder eine [Funktion](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) Prozedur, die einen Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e7a36-121">An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e7a36-122">Die Methode kann nicht deklariert werden alle [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Parameter.</span><span class="sxs-lookup"><span data-stu-id="e7a36-122">The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="e7a36-123">Geben Sie `Task(Of TResult)` für den Rückgabetyp einer Async-Methode Wenn die [zurückgeben](../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung der Methode wurde einen Operand vom Typ TResult enthält.</span><span class="sxs-lookup"><span data-stu-id="e7a36-123">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="e7a36-124">`Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e7a36-124">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="e7a36-125">Das bedeutet, dass ein Aufruf der Methode eine `Task` zurückgibt, aber wenn die `Task` abgeschlossen ist, erzeugt eine `Await`-Anweisung, die `Task` erwartet, keinen Ergebniswert.</span><span class="sxs-lookup"><span data-stu-id="e7a36-125">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>  
  
 <span data-ttu-id="e7a36-126">Asynchrone Unterroutinen werden hauptsächlich verwendet, um Ereignishandler zu definieren, in denen eine `Sub` Prozedur erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e7a36-126">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="e7a36-127">Der Aufrufer einer Async-Unterroutine kann diese nicht erwarten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e7a36-127">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="e7a36-128">Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-128">For more information and examples, see [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7a36-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7a36-129">Example</span></span>  
 <span data-ttu-id="e7a36-130">In den folgenden Beispielen werden ein asynchroner Ereignishandler, ein asynchroner Lambdaausdruck und eine asynchrone Methode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7a36-130">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="e7a36-131">Ein vollständiges Beispiel, die diese Elemente verwendet werden, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web durch Verwenden von Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="e7a36-131">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="e7a36-132">Sie können den Code der exemplarischen Vorgehensweise unter [Codebeispiele für Entwickler](http://go.microsoft.com/fwlink/?LinkId=255191) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="e7a36-132">You can download the walkthrough code from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=255191).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e7a36-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7a36-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [<span data-ttu-id="e7a36-134">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="e7a36-134">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="e7a36-135">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="e7a36-135">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="e7a36-136">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="e7a36-136">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
