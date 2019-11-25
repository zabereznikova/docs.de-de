---
title: Await-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: c2389ff0c94afc2156e594f5d93535d1ed0107a8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336265"
---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="7053a-102">Await-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7053a-102">Await Operator (Visual Basic)</span></span>

<span data-ttu-id="7053a-103">Sie wenden den Operator `Await` auf einen Operanden in einer asynchronen Methode oder einem Lambda-Ausdruck an, um die Ausführung der Methode anzuhalten, bis die erwartete Aufgabe ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7053a-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="7053a-104">Die Aufgabe stellt derzeit ausgeführte Arbeit dar.</span><span class="sxs-lookup"><span data-stu-id="7053a-104">The task represents ongoing work.</span></span>

<span data-ttu-id="7053a-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span><span class="sxs-lookup"><span data-stu-id="7053a-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="7053a-106">Eine solche mit dem `Async`-Modifizierer definierte Methode, die in der Regel mindestens einen `Await`-Ausdruck enthält, wird als *async-Methode* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7053a-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>

> [!NOTE]
> <span data-ttu-id="7053a-107">Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7053a-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="7053a-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="7053a-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="7053a-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="7053a-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=204847), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="7053a-110">Im folgenden Code gibt die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>`getContentsTask`, eine `Task(Of Byte())` zurück.</span><span class="sxs-lookup"><span data-stu-id="7053a-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="7053a-111">Die Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Operation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7053a-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="7053a-112">Der Operator `Await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="7053a-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="7053a-113">In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben.</span><span class="sxs-lookup"><span data-stu-id="7053a-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="7053a-114">Wenn `getContentsTask` beendet ist, wird der `Await`-Ausdruck in ein Bytearray ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7053a-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>

```vb
Private Async Function SumPageSizesAsync() As Task

    ' To use the HttpClient type in desktop apps, you must include a using directive and add a
    ' reference for the System.Net.Http namespace.
    Dim client As HttpClient = New HttpClient()
    ' . . .
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)
    Dim urlContents As Byte() = Await getContentsTask

    ' Equivalently, now that you see how it works, you can write the same thing in a single line.
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)
    ' . . .
End Function
```

> [!IMPORTANT]
> <span data-ttu-id="7053a-115">Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="7053a-115">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="7053a-116">Sie können das Beispiel aus den [Codebeispielen für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) der Microsoft-Website herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7053a-116">You can download the sample from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) on the Microsoft website.</span></span> <span data-ttu-id="7053a-117">Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.</span><span class="sxs-lookup"><span data-stu-id="7053a-117">The example is in the AsyncWalkthrough_HttpClient project.</span></span>

<span data-ttu-id="7053a-118">Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task(Of TResult)` zurückgibt, ist der Typ des `Await`-Ausdrucks TResult.</span><span class="sxs-lookup"><span data-stu-id="7053a-118">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="7053a-119">Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task` zurückgibt, gibt der `Await`-Ausdruck keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="7053a-119">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="7053a-120">Der Unterschied wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7053a-120">The following example illustrates the difference.</span></span>

```vb
' Await used with a method that returns a Task(Of TResult).
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()

' Await used with a method that returns a Task.
Await AsyncMethodThatReturnsTask()
```

<span data-ttu-id="7053a-121">Ein `Await`-Ausdruck oder eine Await-Anweisung blockiert nicht den Thread, auf dem sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7053a-121">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="7053a-122">Stattdessen wird damit verursacht, dass der Compiler den Rest der asynchronen Methode nach dem `Await`-Ausdruck als Fortsetzung der erwarteten Aufgabe registriert.</span><span class="sxs-lookup"><span data-stu-id="7053a-122">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="7053a-123">Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="7053a-123">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="7053a-124">Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="7053a-124">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>

<span data-ttu-id="7053a-125">Ein `Await`-Ausdruck kann nur im Text einer unmittelbar einschließenden Methode oder eines Lambda-Ausdrucks auftreten, die oder der durch einen `Async`-Modifizierer gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="7053a-125">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="7053a-126">The term *Await* serves as a keyword only in that context.</span><span class="sxs-lookup"><span data-stu-id="7053a-126">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="7053a-127">In anderen Kontexten wird er als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7053a-127">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="7053a-128">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span><span class="sxs-lookup"><span data-stu-id="7053a-128">Within the async method or lambda expression, an `Await` expression cannot occur in a query expression, in the `catch` or `finally` block of a [Try…Catch…Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) statement, in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) statement.</span></span>

## <a name="exceptions"></a><span data-ttu-id="7053a-129">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="7053a-129">Exceptions</span></span>

<span data-ttu-id="7053a-130">Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück.</span><span class="sxs-lookup"><span data-stu-id="7053a-130">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7053a-131">Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="7053a-131">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="7053a-132">Der Operator `Await` greift auf diese Eigenschaften zu.</span><span class="sxs-lookup"><span data-stu-id="7053a-132">The `Await` operator accesses those properties.</span></span>

<span data-ttu-id="7053a-133">Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `Await` die Ausnahme erneut aus.</span><span class="sxs-lookup"><span data-stu-id="7053a-133">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>

<span data-ttu-id="7053a-134">Wenn Sie eine asynchrone Methode erwarten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `Await` erneut eine <xref:System.OperationCanceledException> aus.</span><span class="sxs-lookup"><span data-stu-id="7053a-134">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="7053a-135">Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="7053a-135">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="7053a-136">Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein.</span><span class="sxs-lookup"><span data-stu-id="7053a-136">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7053a-137">Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus.</span><span class="sxs-lookup"><span data-stu-id="7053a-137">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="7053a-138">Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7053a-138">However, you can't predict which of the exceptions is rethrown.</span></span>

<span data-ttu-id="7053a-139">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7053a-139">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="7053a-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7053a-140">Example</span></span>

<span data-ttu-id="7053a-141">Im folgenden Windows Forms-Beispielen wird die Verwendung von `Await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7053a-141">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="7053a-142">Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="7053a-142">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="7053a-143">Ohne einen `Await`-Operator wird `WaitSynchronously` trotz der Verwendung des `Async`-Modifizierers in der Definition und in einem Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> im Text synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7053a-143">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> in its body.</span></span>

```vb
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
    ' Call the method that runs asynchronously.
    Dim result As String = Await WaitAsynchronouslyAsync()

    ' Call the method that runs synchronously.
    'Dim result As String = Await WaitSynchronously()

    ' Display the result.
    TextBox1.Text &= result
End Sub

' The following method runs asynchronously. The UI thread is not
' blocked during the delay. You can move or resize the Form1 window
' while Task.Delay is running.
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)
    Await Task.Delay(10000)
    Return "Finished"
End Function

' The following method runs synchronously, despite the use of Async.
' You cannot move or resize the Form1 window while Thread.Sleep
' is running because the UI thread is blocked.
Public Async Function WaitSynchronously() As Task(Of String)
    ' Import System.Threading for the Sleep method.
    Thread.Sleep(10000)
    Return "Finished"
End Function
```

## <a name="see-also"></a><span data-ttu-id="7053a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7053a-144">See also</span></span>

- [<span data-ttu-id="7053a-145">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="7053a-145">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="7053a-146">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="7053a-146">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="7053a-147">Async</span><span class="sxs-lookup"><span data-stu-id="7053a-147">Async</span></span>](../../../visual-basic/language-reference/modifiers/async.md)
