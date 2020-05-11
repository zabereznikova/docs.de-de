---
title: 'Kontextabhängiges yield-Schlüsselwort: C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: d3fe4cf92ca17457bd541f092f5d146ba6c1c095
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794415"
---
# <a name="yield-c-reference"></a><span data-ttu-id="6e731-102">yield (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6e731-102">yield (C# Reference)</span></span>

<span data-ttu-id="6e731-103">Wenn Sie das [kontextabhängige Schlüsselwort](index.md#contextual-keywords) `yield` in einer Anweisung verwenden, geben Sie damit an, dass die Methode, der Operator oder der `get`-Accessor, in der bzw. dem es vorkommt, ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="6e731-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="6e731-104">Wird ein Iterator mithilfe von `yield` definiert, ist eine explizite zusätzliche Klasse (die Klasse, die den Zustand für eine Enumeration enthält, siehe beispielsweise <xref:System.Collections.Generic.IEnumerator%601>) nicht erforderlich, wenn Sie das <xref:System.Collections.IEnumerable>-Muster und das <xref:System.Collections.IEnumerator>-Muster für einen benutzerdefinierten Auflistungstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="6e731-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="6e731-105">Im folgenden Beispiel werden zwei Formen der `yield`-Anweisung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e731-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="6e731-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e731-106">Remarks</span></span>

<span data-ttu-id="6e731-107">Sie verwenden eine `yield return`-Anweisung, um jedes Element einzeln zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6e731-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="6e731-108">Die von einer Iteratormethode zurückgegebene Sequenz kann durch eine [foreach](foreach-in.md)-Anweisung oder eine LINQ-Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e731-108">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="6e731-109">Jede Iteration der `foreach`-Schleife ruft die Iteratormethode auf.</span><span class="sxs-lookup"><span data-stu-id="6e731-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="6e731-110">Wenn eine `yield return`-Anweisung im Iterator erreicht wird, wird ein `expression`-Ausdruck zurückgegeben, und die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6e731-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="6e731-111">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="6e731-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="6e731-112">Sie verwenden eine `yield break`-Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="6e731-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="6e731-113">Weitere Informationen zu Iteratoren finden Sie unter [Iterators (Iteratoren)](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="6e731-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="6e731-114">Iteratormethoden und Get-Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="6e731-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="6e731-115">Die Deklaration eines Iterators muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="6e731-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="6e731-116">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="6e731-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="6e731-117">Die Deklaration darf nicht über [in](in-parameter-modifier.md)-, [ref](ref.md)- oder [out](out-parameter-modifier.md)-Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e731-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="6e731-118">Der `yield`-Typ eines Iterators, der <xref:System.Collections.IEnumerable> oder <xref:System.Collections.IEnumerator> zurückgibt, ist `object`.</span><span class="sxs-lookup"><span data-stu-id="6e731-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="6e731-119">Wenn der Iterator <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Collections.Generic.IEnumerator%601> zurückgibt, ist eine implizite Konvertierung vom Typ des Ausdrucks in der `yield return`-Anweisung in den generischen Typparameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e731-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="6e731-120">Folgendes darf keine `yield return`- oder `yield break`-Anweisung enthalten:</span><span class="sxs-lookup"><span data-stu-id="6e731-120">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="6e731-121">[Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md) und [anonyme Methoden](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6e731-121">[Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="6e731-122">Methoden, die unsichere Blöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e731-122">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="6e731-123">Weitere Informationen finden Sie unter [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6e731-123">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="6e731-124">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="6e731-124">Exception handling</span></span>

<span data-ttu-id="6e731-125">Eine `yield return`-Anweisung kann sich nicht in einem try-catch-Block befinden.</span><span class="sxs-lookup"><span data-stu-id="6e731-125">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="6e731-126">Eine `yield return`-Anweisung kann sich im try-Block einer try-finally-Anweisung befinden.</span><span class="sxs-lookup"><span data-stu-id="6e731-126">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="6e731-127">Eine `yield break`-Anweisung kann sich in einem try- oder catch-Block befinden, nicht jedoch in einem finally-Block.</span><span class="sxs-lookup"><span data-stu-id="6e731-127">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="6e731-128">Wenn der `foreach`-Text (außerhalb der Iteratormethode) eine Ausnahme auslöst, wird ein `finally`-Block in der Iteratormethode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e731-128">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="6e731-129">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="6e731-129">Technical implementation</span></span>

<span data-ttu-id="6e731-130">Der folgende Code gibt einen `IEnumerable<string>` aus einer Iteratormethode zurück und durchläuft dann die Elemente.</span><span class="sxs-lookup"><span data-stu-id="6e731-130">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="6e731-131">Der Aufruf von `MyIteratorMethod` führt nicht den Text der Methode aus.</span><span class="sxs-lookup"><span data-stu-id="6e731-131">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="6e731-132">Stattdessen gibt der Aufruf einen `IEnumerable<string>` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="6e731-132">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="6e731-133">Bei einer Iteration der `foreach`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6e731-133">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="6e731-134">Dieser Aufruf führt `MyIteratorMethod` aus, bis die nächste `yield return`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="6e731-134">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="6e731-135">Der Ausdruck, der durch die `yield return`-Anweisung zurückgegeben wird, ermittelt nicht nur den Wert der `element`-Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>-Eigenschaft von `elements` (ein `IEnumerable<string>`).</span><span class="sxs-lookup"><span data-stu-id="6e731-135">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="6e731-136">Bei jeder nachfolgenden Iteration der `foreach`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `yield return`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6e731-136">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="6e731-137">Die `foreach`-Schleife wird beendet, wenn das Ende der Iteratormethode oder eine `yield break`-Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="6e731-137">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="6e731-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e731-138">Example</span></span>

<span data-ttu-id="6e731-139">Das folgende Beispiel weist eine `yield return`-Anweisung auf, die sich innerhalb einer `for`-Schleife befindet.</span><span class="sxs-lookup"><span data-stu-id="6e731-139">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="6e731-140">Jede Iteration des `foreach`-Anweisungstexts in der Methode `Main` erzeugt einen Aufruf an die Iteratorfunktion `Power`.</span><span class="sxs-lookup"><span data-stu-id="6e731-140">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="6e731-141">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `yield return`-Schleife zur nächsten Ausführung der `for`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6e731-141">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="6e731-142">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.IEnumerable>, was ein Iteratorschnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="6e731-142">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="6e731-143">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="6e731-143">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="6e731-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e731-144">Example</span></span>

<span data-ttu-id="6e731-145">Das folgende Beispiel zeigt einen `get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="6e731-145">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="6e731-146">Im Beispiel gibt jede `yield return`-Anweisung eine Instanz einer benutzerdefinierten Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="6e731-146">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="6e731-147">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="6e731-147">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6e731-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e731-148">See also</span></span>

- [<span data-ttu-id="6e731-149">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6e731-149">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e731-150">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6e731-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6e731-151">foreach, in</span><span class="sxs-lookup"><span data-stu-id="6e731-151">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="6e731-152">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="6e731-152">Iterators</span></span>](../../iterators.md)
