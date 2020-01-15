---
title: Await-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: b5943e509bb850abc6c74e1b97ccd5fb0038f1e0
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964337"
---
# <a name="await-operator-visual-basic"></a><span data-ttu-id="f8572-102">Await-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8572-102">Await Operator (Visual Basic)</span></span>

<span data-ttu-id="f8572-103">Sie wenden den Operator `Await` auf einen Operanden in einer asynchronen Methode oder einem Lambda-Ausdruck an, um die Ausführung der Methode anzuhalten, bis die erwartete Aufgabe ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f8572-103">You apply the `Await` operator to an operand in an asynchronous method or lambda expression to suspend execution of the method until the awaited task completes.</span></span> <span data-ttu-id="f8572-104">Die Aufgabe stellt derzeit ausgeführte Arbeit dar.</span><span class="sxs-lookup"><span data-stu-id="f8572-104">The task represents ongoing work.</span></span>

<span data-ttu-id="f8572-105">Die Methode, in der `Await` verwendet wird, muss einen [Async](../../../visual-basic/language-reference/modifiers/async.md) -Modifizierer aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f8572-105">The method in which `Await` is used must have an [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier.</span></span> <span data-ttu-id="f8572-106">Eine solche mit dem `Async`-Modifizierer definierte Methode, die in der Regel mindestens einen `Await`-Ausdruck enthält, wird als *async-Methode* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f8572-106">Such a method, defined by using the `Async` modifier, and usually containing one or more `Await` expressions, is referred to as an *async method*.</span></span>

> [!NOTE]
> <span data-ttu-id="f8572-107">Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f8572-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="f8572-108">Eine Einführung in die asynchrone Programmierung finden Sie unter [asynchrone Programmierung mit Async und warten](../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="f8572-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="f8572-109">In der Regel ist die Aufgabe, auf die Sie den `Await`-Operator anwenden, der Rückgabewert eines Aufrufes einer Methode, die das [aufgabenbasierte asynchrone Muster](https://www.microsoft.com/download/details.aspx?id=19957)implementiert, d. h. eine <xref:System.Threading.Tasks.Task> oder eine <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="f8572-109">Typically, the task to which you apply the `Await` operator is the return value from a call to a method that implements the [Task-Based Asynchronous Pattern](https://www.microsoft.com/download/details.aspx?id=19957), that is, a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="f8572-110">Im folgenden Code gibt die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>`getContentsTask`, eine `Task(Of Byte())` zurück.</span><span class="sxs-lookup"><span data-stu-id="f8572-110">In the following code, the <xref:System.Net.Http.HttpClient> method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> returns `getContentsTask`, a `Task(Of Byte())`.</span></span> <span data-ttu-id="f8572-111">Die Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Operation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f8572-111">The task is a promise to produce the actual byte array when the operation is complete.</span></span> <span data-ttu-id="f8572-112">Der Operator `Await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f8572-112">The `Await` operator is applied to `getContentsTask` to suspend execution in `SumPageSizesAsync` until `getContentsTask` is complete.</span></span> <span data-ttu-id="f8572-113">In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben.</span><span class="sxs-lookup"><span data-stu-id="f8572-113">In the meantime, control is returned to the caller of `SumPageSizesAsync`.</span></span> <span data-ttu-id="f8572-114">Wenn `getContentsTask` beendet ist, wird der `Await`-Ausdruck in ein Bytearray ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f8572-114">When `getContentsTask` is finished, the `Await` expression evaluates to a byte array.</span></span>

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
> <span data-ttu-id="f8572-115">Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="f8572-115">For the complete example, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="f8572-116">Sie können das Beispiel aus den [Codebeispielen für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) der Microsoft-Website herunterladen.</span><span class="sxs-lookup"><span data-stu-id="f8572-116">You can download the sample from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) on the Microsoft website.</span></span> <span data-ttu-id="f8572-117">Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.</span><span class="sxs-lookup"><span data-stu-id="f8572-117">The example is in the AsyncWalkthrough_HttpClient project.</span></span>

<span data-ttu-id="f8572-118">Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task(Of TResult)` zurückgibt, ist der Typ des `Await`-Ausdrucks TResult.</span><span class="sxs-lookup"><span data-stu-id="f8572-118">If `Await` is applied to the result of a method call that returns a `Task(Of TResult)`, the type of the `Await` expression is TResult.</span></span> <span data-ttu-id="f8572-119">Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task` zurückgibt, gibt der `Await`-Ausdruck keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f8572-119">If `Await` is applied to the result of a method call that returns a `Task`, the `Await` expression doesn't return a value.</span></span> <span data-ttu-id="f8572-120">Der Unterschied wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f8572-120">The following example illustrates the difference.</span></span>

```vb
' Await used with a method that returns a Task(Of TResult).
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()

' Await used with a method that returns a Task.
Await AsyncMethodThatReturnsTask()
```

<span data-ttu-id="f8572-121">Ein `Await`-Ausdruck oder eine Await-Anweisung blockiert nicht den Thread, auf dem sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f8572-121">An `Await` expression or statement does not block the thread on which it is executing.</span></span> <span data-ttu-id="f8572-122">Stattdessen wird damit verursacht, dass der Compiler den Rest der asynchronen Methode nach dem `Await`-Ausdruck als Fortsetzung der erwarteten Aufgabe registriert.</span><span class="sxs-lookup"><span data-stu-id="f8572-122">Instead, it causes the compiler to sign up the rest of the async method, after the `Await` expression, as a continuation on the awaited task.</span></span> <span data-ttu-id="f8572-123">Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="f8572-123">Control then returns to the caller of the async method.</span></span> <span data-ttu-id="f8572-124">Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="f8572-124">When the task completes, it invokes its continuation, and execution of the async method resumes where it left off.</span></span>

<span data-ttu-id="f8572-125">Ein `Await`-Ausdruck kann nur im Text einer unmittelbar einschließenden Methode oder eines Lambda-Ausdrucks auftreten, die oder der durch einen `Async`-Modifizierer gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="f8572-125">An `Await` expression can occur only in the body of an immediately enclosing method or lambda expression that is marked by an `Async` modifier.</span></span> <span data-ttu-id="f8572-126">Der Begriff " *warten* " dient nur in diesem Kontext als Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f8572-126">The term *Await* serves as a keyword only in that context.</span></span> <span data-ttu-id="f8572-127">In anderen Kontexten wird er als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f8572-127">Elsewhere, it is interpreted as an identifier.</span></span> <span data-ttu-id="f8572-128">Innerhalb der `Async` Methode oder des Lambda-Ausdrucks kann ein `Await` Ausdruck nicht in einem Abfrage Ausdruck, im `Catch` oder `Finally` Block eines [try... Catch... Schließlich Anweisung](../statements/try-catch-finally-statement.md)im Schleifen Steuerungsvariablen Ausdruck einer `For`-oder `For Each` Schleife oder im Text einer [SyncLock](../statements/synclock-statement.md) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f8572-128">Within the `Async` method or lambda expression, an `Await` expression cannot occur in a query expression, in the `Catch` or `Finally` block of a [Try…Catch…Finally statement](../statements/try-catch-finally-statement.md), in the loop control variable expression of a `For` or `For Each` loop, or in the body of a [SyncLock](../statements/synclock-statement.md) statement.</span></span>

## <a name="exceptions"></a><span data-ttu-id="f8572-129">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f8572-129">Exceptions</span></span>

<span data-ttu-id="f8572-130">Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück.</span><span class="sxs-lookup"><span data-stu-id="f8572-130">Most async methods return a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f8572-131">Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="f8572-131">The properties of the returned task carry information about its status and history, such as whether the task is complete, whether the async method caused an exception or was canceled, and what the final result is.</span></span> <span data-ttu-id="f8572-132">Der Operator `Await` greift auf diese Eigenschaften zu.</span><span class="sxs-lookup"><span data-stu-id="f8572-132">The `Await` operator accesses those properties.</span></span>

<span data-ttu-id="f8572-133">Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `Await` die Ausnahme erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f8572-133">If you await a task-returning async method that causes an exception, the  `Await` operator rethrows the exception.</span></span>

<span data-ttu-id="f8572-134">Wenn Sie eine asynchrone Methode erwarten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `Await` erneut eine <xref:System.OperationCanceledException> aus.</span><span class="sxs-lookup"><span data-stu-id="f8572-134">If you await a task-returning async method that is canceled, the `Await` operator rethrows an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="f8572-135">Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="f8572-135">A single task that is in a faulted state can reflect multiple exceptions.</span></span>  <span data-ttu-id="f8572-136">Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein.</span><span class="sxs-lookup"><span data-stu-id="f8572-136">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f8572-137">Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus.</span><span class="sxs-lookup"><span data-stu-id="f8572-137">When you await such a task, the await operation rethrows only one of the exceptions.</span></span> <span data-ttu-id="f8572-138">Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f8572-138">However, you can't predict which of the exceptions is rethrown.</span></span>

<span data-ttu-id="f8572-139">Beispiele für die Fehlerbehandlung in Async-Methoden finden [Sie unter try... Catch... Abschließend-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f8572-139">For examples of error handling in async methods, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="f8572-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8572-140">Example</span></span>

<span data-ttu-id="f8572-141">Im folgenden Windows Forms-Beispielen wird die Verwendung von `Await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f8572-141">The following Windows Forms example illustrates the use of `Await` in an async method, `WaitAsynchronouslyAsync`.</span></span> <span data-ttu-id="f8572-142">Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="f8572-142">Contrast the behavior of that method with the behavior of `WaitSynchronously`.</span></span> <span data-ttu-id="f8572-143">Ohne einen `Await`-Operator wird `WaitSynchronously` trotz der Verwendung des `Async`-Modifizierers in der Definition und in einem Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> im Text synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8572-143">Without an `Await` operator, `WaitSynchronously` runs synchronously despite the use of the `Async` modifier in its definition and a call to <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> in its body.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f8572-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8572-144">See also</span></span>

- [<span data-ttu-id="f8572-145">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="f8572-145">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="f8572-146">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="f8572-146">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="f8572-147">Async</span><span class="sxs-lookup"><span data-stu-id="f8572-147">Async</span></span>](../../../visual-basic/language-reference/modifiers/async.md)
