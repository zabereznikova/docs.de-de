---
title: try-catch – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
ms.openlocfilehash: 4715a27a94ac86c5e4955c0e8be95c6ee4a28507
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619701"
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="d738d-102">try-catch (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d738d-102">try-catch (C# Reference)</span></span>

<span data-ttu-id="d738d-103">Die try-catch-Anweisung besteht aus einem `try`-Block gefolgt von einer oder mehreren `catch`-Klauseln, die Handler für verschiedene Ausnahmen angeben.</span><span class="sxs-lookup"><span data-stu-id="d738d-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>

<span data-ttu-id="d738d-104">Wenn eine Ausnahme ausgelöst wird, sucht die Common Language Runtime (CLR) nach der `catch`-Anweisung, die diese Ausnahme behandelt.</span><span class="sxs-lookup"><span data-stu-id="d738d-104">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="d738d-105">Wenn die derzeit ausgeführte Methode keinen solchen `catch`-Block enthält, betrachtet die CLR die Methode, die die aktuelle Methode aufgerufen hat, dann die vorhergehende in der Aufrufliste usw.</span><span class="sxs-lookup"><span data-stu-id="d738d-105">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="d738d-106">Wenn kein `catch`-Block gefunden wird, zeigt die CLR dem Benutzer eine Meldung über eine nicht behandelte Ausnahme an und beendet die Ausführung des Programms.</span><span class="sxs-lookup"><span data-stu-id="d738d-106">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>

<span data-ttu-id="d738d-107">Der `try` -Block enthält den überwachten Code, der möglicherweise die Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="d738d-107">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="d738d-108">Der Block wird ausgeführt, bis eine Ausnahme ausgelöst wird, oder bis er erfolgreich abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-108">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="d738d-109">Beispielsweise löst der folgende Versuch, ein `null`-Objekt umzuwandeln, die <xref:System.NullReferenceException>-Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="d738d-109">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>

```csharp
object o2 = null;
try
{
    int i2 = (int)o2;   // Error
}
```

<span data-ttu-id="d738d-110">Zwar kann die `catch`-Klausel ohne Argumente verwendet werden, um jeden beliebigen Ausnahmetyp abfangen, dies wird jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d738d-110">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="d738d-111">Im Allgemeinen sollten Sie nur solche Ausnahmen abfangen, bei denen Sie wissen, wie die Wiederherstellung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-111">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="d738d-112">Daher sollten Sie immer ein von <xref:System.Exception?displayProperty=nameWithType> abgeleitetes Objektargument angeben, zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d738d-112">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>

```csharp
catch (InvalidCastException e)
{
}
```

<span data-ttu-id="d738d-113">Es ist möglich, mehrere spezifische `catch`-Klauseln in derselben try-catch-Anweisung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d738d-113">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="d738d-114">In diesem Fall ist die Reihenfolge der `catch`-Klauseln wichtig, da die `catch`-Klauseln nacheinander überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="d738d-114">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="d738d-115">Fangen Sie spezifischere Ausnahmen vor den weniger spezifischen ab.</span><span class="sxs-lookup"><span data-stu-id="d738d-115">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="d738d-116">Der Compiler erzeugt einen Fehler, wenn Sie Ihre catch-Blöcke so anordnen, dass ein neuerer Block nie erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="d738d-116">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>

<span data-ttu-id="d738d-117">Die Verwendung von `catch`-Argumenten ist eine Möglichkeit zum Filtern der Ausnahmen, die Sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="d738d-117">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="d738d-118">Sie können auch einen Ausnahmefilter verwenden, der die Ausnahme weiter untersucht, um zu entscheiden, ob Sie sie behandeln möchten.</span><span class="sxs-lookup"><span data-stu-id="d738d-118">You can also use an exception filter that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="d738d-119">Wenn der Ausnahmefilter „FALSE“ zurückgibt, wird die Suche nach einem Ausnahmehandler fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d738d-119">If the exception filter returns false, then the search for a handler continues.</span></span>

```csharp
catch (ArgumentException e) when (e.ParamName == "…")
{
}
```

<span data-ttu-id="d738d-120">Ausnahmefilter sind dem Abfangen und erneuten Auslösen vorzuziehen (siehe nachfolgende Erläuterung), da der Filter den Stapel nicht beschädigt.</span><span class="sxs-lookup"><span data-stu-id="d738d-120">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="d738d-121">Wenn ein späterer Handler den Stapel löscht, können Sie feststellen, wo die Ausnahme ursprünglich herkam, und nicht nur die letzte Stelle, an der sie erneut ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d738d-121">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="d738d-122">Filterausdrücke für Ausnahmen werden häufig zu Protokollierungszwecken eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="d738d-122">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="d738d-123">Sie können einen Filter erstellen, der immer FALSE zurückgibt und außerdem Ausgaben in ein Protokoll schreibt, und Sie können Ausnahmen protokollieren, wenn sie auftreten, ohne sie zu behandeln und erneut auszulösen.</span><span class="sxs-lookup"><span data-stu-id="d738d-123">You can create a filter that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>

<span data-ttu-id="d738d-124">Eine [throw`catch`-Anweisung kann in einem ](throw.md)-Block verwendet werden, um die von der `catch`-Anweisung abgefangene Ausnahme erneut auszulösen.</span><span class="sxs-lookup"><span data-stu-id="d738d-124">A [throw](throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="d738d-125">Im folgenden Beispiel werden Quellinformationen aus einer <xref:System.IO.IOException>-Ausnahme extrahiert, anschließend wird die Ausnahme in der übergeordneten Methode ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d738d-125">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>

```csharp
catch (FileNotFoundException e)
{
    // FileNotFoundExceptions are handled here.
}
catch (IOException e)
{
    // Extract some information from this exception, and then
    // throw it to the parent method.
    if (e.Source != null)
        Console.WriteLine("IOException source: {0}", e.Source);
    throw;
}
```

<span data-ttu-id="d738d-126">Sie können eine Ausnahme abfangen und eine andere Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="d738d-126">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="d738d-127">Wenn Sie dies tun, geben Sie die abgefangene Ausnahme als innere Ausnahme an, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d738d-127">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    // Perform some action here, and then throw a new exception.
    throw new YourCustomException("Put your error message here.", e);
}
```

<span data-ttu-id="d738d-128">Sie können eine Ausnahme auch erneut auslösen, wenn eine angegebene Bedingung erfüllt ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d738d-128">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>

```csharp
catch (InvalidCastException e)
{
    if (e.Data == null)
    {
        throw;
    }
    else
    {
        // Take some action.
    }
}
```

> [!NOTE]
> <span data-ttu-id="d738d-129">Es ist auch möglich, einen Ausnahmefilter zu verwenden, um ein ähnliches Ergebnis auf eine meist übersichtlichere Weise zu erhalten (sowie ohne den Stapel zu bearbeiten, wie weiter oben in diesem Artikel erläutert wurde).</span><span class="sxs-lookup"><span data-stu-id="d738d-129">It is also possible to use an exception filter to get a similar result in an often cleaner fashion (as well as not modifying the stack, as explained earlier in this document).</span></span> <span data-ttu-id="d738d-130">Das folgende Beispiel verfügt über das gleiche Verhalten für Aufrufer wie das vorherige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d738d-130">The following example has a similar behavior for callers as the previous example.</span></span> <span data-ttu-id="d738d-131">Die Funktion gibt `InvalidCastException` an den Aufrufer zurück, wenn `e.Data``null` ist.</span><span class="sxs-lookup"><span data-stu-id="d738d-131">The function throws the `InvalidCastException` back to the caller when `e.Data` is `null`.</span></span>
>
> ```csharp
> catch (InvalidCastException e) when (e.Data != null)
> {
>     // Take some action.
> }
> ```

<span data-ttu-id="d738d-132">Initialisieren Sie innerhalb eines `try`-Blocks nur Variablen, die auch in diesem deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="d738d-132">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="d738d-133">Andernfalls kann eine Ausnahme auftreten, bevor die Ausführung des Blocks abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d738d-133">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="d738d-134">Beispiel: Im folgenden Codebeispiel wird die `n`-Variable innerhalb des `try`-Blocks initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d738d-134">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="d738d-135">Beim Versuch, diese Variable außerhalb des `try`-Blocks in der `Write(n)`-Anweisung zu verwenden, wird ein Compilerfehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d738d-135">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>

```csharp
static void Main()
{
    int n;
    try
    {
        // Do not initialize this variable here.
        n = 123;
    }
    catch
    {
    }
    // Error: Use of unassigned local variable 'n'.
    Console.Write(n);
}
```

<span data-ttu-id="d738d-136">Weitere Informationen zu „catch“ finden Sie unter [try-catch-finally](try-catch-finally.md).</span><span class="sxs-lookup"><span data-stu-id="d738d-136">For more information about catch, see [try-catch-finally](try-catch-finally.md).</span></span>

## <a name="exceptions-in-async-methods"></a><span data-ttu-id="d738d-137">Ausnahmen in Async-Methoden</span><span class="sxs-lookup"><span data-stu-id="d738d-137">Exceptions in async methods</span></span>

<span data-ttu-id="d738d-138">Eine asynchrone Methode wird mit einem [async](async.md)-Modifizierer gekennzeichnet und enthält in der Regel eine oder mehrere await-Ausdrücke oder -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d738d-138">An async method is marked  by an  [async](async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="d738d-139">Ein „await“-Ausdruck wendet den [await](../operators/await.md)-Operator auf ein <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> an.</span><span class="sxs-lookup"><span data-stu-id="d738d-139">An await expression applies the [await](../operators/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="d738d-140">Wenn ein `await`-Ausdruck in der asynchchronen Methode erreicht wird, wird die Ausführung der Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d738d-140">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="d738d-141">Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Methode fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d738d-141">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="d738d-142">Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await](../../programming-guide/concepts/async/index.md) und [Ablaufsteuerung in asynchronen Programmen](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span><span class="sxs-lookup"><span data-stu-id="d738d-142">For more information, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>

<span data-ttu-id="d738d-143">Die abgeschlossene Aufgabe, auf die `await` angewendet wird, kann sich aufgrund einer unbehandelten Ausnahme in der Methode, die die Aufgabe zurückgibt, in einem fehlerhaften Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="d738d-143">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="d738d-144">Das Warten auf die Aufgabe löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d738d-144">Awaiting the task throws an exception.</span></span> <span data-ttu-id="d738d-145">Eine Aufgabe kann auch in einem abgebrochenen Zustand enden, wenn der asynchrone Prozess, der sie zurückgibt, abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-145">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="d738d-146">Das Warten auf eine abgebrochene Aufgabe löst eine `OperationCanceledException` aus.</span><span class="sxs-lookup"><span data-stu-id="d738d-146">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="d738d-147">Weitere Informationen zum Abbrechen eines asynchronen Prozesses finden Sie unter [Feinabstimmung der Async-Anwendung](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span><span class="sxs-lookup"><span data-stu-id="d738d-147">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>

<span data-ttu-id="d738d-148">Um die Ausnahme abzufangen, warten Sie in einem `try`-Block auf die Aufgabe, und fangen Sie die Ausnahme im zugehörigen `catch`-Block ab.</span><span class="sxs-lookup"><span data-stu-id="d738d-148">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="d738d-149">Ein Beispiel hierfür finden Sie im Abschnitt [Beispiel zu einer Async-Methode](#async-method-example).</span><span class="sxs-lookup"><span data-stu-id="d738d-149">For an example, see the [Async method example](#async-method-example) section.</span></span>

<span data-ttu-id="d738d-150">Eine Aufgabe kann sich in einem fehlerhaften Zustand befinden, da mehrere Ausnahmen in der erwarteten asynchronen Methode aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="d738d-150">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="d738d-151">Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein.</span><span class="sxs-lookup"><span data-stu-id="d738d-151">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d738d-152">Wenn Sie auf eine solche Aufgabe warten, wird nur eine der Ausnahmen abgefangen, und Sie können nicht vorhersagen, welche Ausnahme abgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-152">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="d738d-153">Ein Beispiel hierfür finden Sie im Abschnitt [Task.WhenAll-Beispiel](#taskwhenall-example).</span><span class="sxs-lookup"><span data-stu-id="d738d-153">For an example, see the [Task.WhenAll example](#taskwhenall-example) section.</span></span>

## <a name="example"></a><span data-ttu-id="d738d-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d738d-154">Example</span></span>

<span data-ttu-id="d738d-155">Im folgenden Beispiel enthält der `try`-Block einen Aufruf der `ProcessString`-Methode, die eine Ausnahme verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="d738d-155">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="d738d-156">Die `catch`-Klausel enthält den Ausnahmehandler, der lediglich eine Meldung auf dem Bildschirm anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d738d-156">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="d738d-157">Wenn die `throw`-Anweisung aus `ProcessString` heraus aufgerufen wird, sucht das System nach der `catch`-Anweisung und zeigt die Meldung `Exception caught` an.</span><span class="sxs-lookup"><span data-stu-id="d738d-157">When the `throw` statement is called from inside `ProcessString`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>

[!code-csharp[csrefKeywordsExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#2)]

## <a name="two-catch-blocks-example"></a><span data-ttu-id="d738d-158">Beispiel für zwei Catch-Blöcke</span><span class="sxs-lookup"><span data-stu-id="d738d-158">Two catch blocks example</span></span>

<span data-ttu-id="d738d-159">Im folgenden Beispiel werden zwei catch-Blöcke verwendet, und die spezifischste Ausnahme, die an erster Stelle steht, wird abgefangen.</span><span class="sxs-lookup"><span data-stu-id="d738d-159">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>

<span data-ttu-id="d738d-160">Um die allgemeinste Ausnahme abzufangen, können Sie die throw-Anweisung in `ProcessString` durch die folgende Anweisung ersetzen: `throw new Exception()`.</span><span class="sxs-lookup"><span data-stu-id="d738d-160">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>

<span data-ttu-id="d738d-161">Wenn Sie den allgemeinsten catch-Block im Beispiel an erster Stelle platzieren, wird die folgende Fehlermeldung angezeigt: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span><span class="sxs-lookup"><span data-stu-id="d738d-161">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>

[!code-csharp[csrefKeywordsExceptions#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#3)]

## <a name="async-method-example"></a><span data-ttu-id="d738d-162">Beispiel für eine Async-Methode</span><span class="sxs-lookup"><span data-stu-id="d738d-162">Async method example</span></span>

<span data-ttu-id="d738d-163">Im folgenden Beispiel wird die Ausnahmebehandlung für asynchrone Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d738d-163">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="d738d-164">Um eine von einer asynchronen Aufgabe ausgelöste Ausnahme abzufangen, platzieren Sie den `await`-Ausdruck in einem `try`-Block, und fangen Sie die Ausnahme in einem `catch`-Block ab.</span><span class="sxs-lookup"><span data-stu-id="d738d-164">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>

<span data-ttu-id="d738d-165">Heben Sie die Auskommentierung der Zeile `throw new Exception` im Beispiel auf, um die Ausnahmebehandlung zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="d738d-165">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="d738d-166">Die `IsFaulted`-Eigenschaft der Aufgabe wird auf `True` festgelegt, die `Exception.InnerException`-Eigenschaft der Aufgabe auf die Ausnahme, und die Ausnahme wird im `catch`-Block abgefangen.</span><span class="sxs-lookup"><span data-stu-id="d738d-166">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>

<span data-ttu-id="d738d-167">Heben Sie die Auskommentierung der Zeile `throw new OperationCanceledException` auf, um zu veranschaulichen, was beim Abbrechen eines asynchronen Prozesses passiert.</span><span class="sxs-lookup"><span data-stu-id="d738d-167">Uncomment the `throw new OperationCanceledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="d738d-168">Die `IsCanceled`-Eigenschaft der Aufgabe wird auf `true` festgelegt, und die Ausnahme wird im `catch`-Block abgefangen.</span><span class="sxs-lookup"><span data-stu-id="d738d-168">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="d738d-169">Unter bestimmten Bedingungen, die für dieses Beispiel nicht gelten, wird die `IsFaulted`-Eigenschaft der Aufgabe auf `true` und `IsCanceled` auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d738d-169">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>

[!code-csharp[csAsyncExceptions#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#2)]  

## <a name="taskwhenall-example"></a><span data-ttu-id="d738d-170">Task.WhenAll-Beispiel</span><span class="sxs-lookup"><span data-stu-id="d738d-170">Task.WhenAll example</span></span>

<span data-ttu-id="d738d-171">Das folgende Beispiel veranschaulicht die Behandlung von Ausnahmen in Fällen, in denen mehrere Aufgaben zu mehreren Ausnahmen führen können.</span><span class="sxs-lookup"><span data-stu-id="d738d-171">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="d738d-172">Der `try`-Block wartet auf die Aufgabe, die von einem Aufruf von <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-172">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d738d-173">Die Aufgabe ist abgeschlossen, wenn die drei Aufgaben abgeschlossen sind, auf die WhenAll angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d738d-173">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>

<span data-ttu-id="d738d-174">Jede der drei Aufgaben löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d738d-174">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="d738d-175">Der `catch`-Block iteriert durch die Ausnahmen, die in der `Exception.InnerExceptions`-Eigenschaft der Aufgabe stehen, die von <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d738d-175">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>

[!code-csharp[csAsyncExceptions#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csasyncexceptions/cs/class1.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="d738d-176">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d738d-176">C# language specification</span></span>

<span data-ttu-id="d738d-177">Weitere Informationen finden Sie im Abschnitt [Die Try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="d738d-177">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d738d-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d738d-178">See also</span></span>

- [<span data-ttu-id="d738d-179">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d738d-179">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d738d-180">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d738d-180">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d738d-181">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d738d-181">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d738d-182">try, throw, and catch Statements (C++) (try-, throw- und catch-Anweisungen (C++))</span><span class="sxs-lookup"><span data-stu-id="d738d-182">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="d738d-183">throw</span><span class="sxs-lookup"><span data-stu-id="d738d-183">throw</span></span>](throw.md)
- [<span data-ttu-id="d738d-184">try-finally</span><span class="sxs-lookup"><span data-stu-id="d738d-184">try-finally</span></span>](try-finally.md)
- [<span data-ttu-id="d738d-185">Vorgehensweise: Explizites Auslösen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d738d-185">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
