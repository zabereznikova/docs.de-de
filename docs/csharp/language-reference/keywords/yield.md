---
description: 'Kontextabhängiges yield-Schlüsselwort: C#-Referenz'
title: 'Kontextabhängiges yield-Schlüsselwort: C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: c8caf7e34397faf9f7085d6634287cffcb37eb08
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141880"
---
# <a name="yield-c-reference"></a><span data-ttu-id="2c63a-103">yield (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2c63a-103">yield (C# Reference)</span></span>

<span data-ttu-id="2c63a-104">Wenn Sie das [kontextabhängige Schlüsselwort](index.md#contextual-keywords) `yield` in einer Anweisung verwenden, geben Sie damit an, dass die Methode, der Operator oder der `get`-Accessor, in der bzw. dem es vorkommt, ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="2c63a-104">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="2c63a-105">Wird ein Iterator mithilfe von `yield` definiert, ist eine explizite zusätzliche Klasse (die Klasse, die den Zustand für eine Enumeration enthält, siehe beispielsweise <xref:System.Collections.Generic.IEnumerator%601>) nicht erforderlich, wenn Sie das <xref:System.Collections.IEnumerable>-Muster und das <xref:System.Collections.IEnumerator>-Muster für einen benutzerdefinierten Auflistungstyp implementieren.</span><span class="sxs-lookup"><span data-stu-id="2c63a-105">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="2c63a-106">Im folgenden Beispiel werden zwei Formen der `yield`-Anweisung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c63a-106">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="2c63a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c63a-107">Remarks</span></span>

<span data-ttu-id="2c63a-108">Sie verwenden eine `yield return`-Anweisung, um jedes Element einzeln zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2c63a-108">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="2c63a-109">Die von einer Iteratormethode zurückgegebene Sequenz kann durch eine [foreach](foreach-in.md)-Anweisung oder eine LINQ-Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c63a-109">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="2c63a-110">Jede Iteration der `foreach`-Schleife ruft die Iteratormethode auf.</span><span class="sxs-lookup"><span data-stu-id="2c63a-110">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="2c63a-111">Wenn eine `yield return`-Anweisung im Iterator erreicht wird, wird ein `expression`-Ausdruck zurückgegeben, und die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2c63a-111">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="2c63a-112">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="2c63a-112">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="2c63a-113">Sie verwenden eine `yield break`-Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2c63a-113">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="2c63a-114">Weitere Informationen zu Iteratoren finden Sie unter [Iterators (Iteratoren)](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="2c63a-114">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="2c63a-115">Iteratormethoden und Get-Zugriffsmethoden</span><span class="sxs-lookup"><span data-stu-id="2c63a-115">Iterator methods and get accessors</span></span>

<span data-ttu-id="2c63a-116">Die Deklaration eines Iterators muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2c63a-116">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="2c63a-117">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="2c63a-117">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="2c63a-118">Die Deklaration darf nicht über [in](in-parameter-modifier.md)-, [ref](ref.md)- oder [out](out-parameter-modifier.md)-Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="2c63a-118">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="2c63a-119">Der `yield`-Typ eines Iterators, der <xref:System.Collections.IEnumerable> oder <xref:System.Collections.IEnumerator> zurückgibt, ist `object`.</span><span class="sxs-lookup"><span data-stu-id="2c63a-119">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="2c63a-120">Wenn der Iterator <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Collections.Generic.IEnumerator%601> zurückgibt, ist eine implizite Konvertierung vom Typ des Ausdrucks in der `yield return`-Anweisung in den generischen Typparameter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2c63a-120">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="2c63a-121">Folgendes darf keine `yield return`- oder `yield break`-Anweisung enthalten:</span><span class="sxs-lookup"><span data-stu-id="2c63a-121">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="2c63a-122">[Lambdaausdrücke](../operators/lambda-expressions.md) und [anonyme Methoden](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2c63a-122">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="2c63a-123">Methoden, die unsichere Blöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c63a-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="2c63a-124">Weitere Informationen finden Sie unter [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="2c63a-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="2c63a-125">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="2c63a-125">Exception handling</span></span>

<span data-ttu-id="2c63a-126">Eine `yield return`-Anweisung kann sich nicht in einem try-catch-Block befinden.</span><span class="sxs-lookup"><span data-stu-id="2c63a-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="2c63a-127">Eine `yield return`-Anweisung kann sich im try-Block einer try-finally-Anweisung befinden.</span><span class="sxs-lookup"><span data-stu-id="2c63a-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="2c63a-128">Eine `yield break`-Anweisung kann sich in einem try- oder catch-Block befinden, nicht jedoch in einem finally-Block.</span><span class="sxs-lookup"><span data-stu-id="2c63a-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="2c63a-129">Wenn der `foreach`-Text (außerhalb der Iteratormethode) eine Ausnahme auslöst, wird ein `finally`-Block in der Iteratormethode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2c63a-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="2c63a-130">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="2c63a-130">Technical implementation</span></span>

<span data-ttu-id="2c63a-131">Der folgende Code gibt einen `IEnumerable<string>` aus einer Iteratormethode zurück und durchläuft dann die Elemente.</span><span class="sxs-lookup"><span data-stu-id="2c63a-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="2c63a-132">Der Aufruf von `MyIteratorMethod` führt nicht den Text der Methode aus.</span><span class="sxs-lookup"><span data-stu-id="2c63a-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="2c63a-133">Stattdessen gibt der Aufruf einen `IEnumerable<string>` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="2c63a-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="2c63a-134">Bei einer Iteration der `foreach`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2c63a-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="2c63a-135">Dieser Aufruf führt `MyIteratorMethod` aus, bis die nächste `yield return`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="2c63a-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="2c63a-136">Der Ausdruck, der durch die `yield return`-Anweisung zurückgegeben wird, ermittelt nicht nur den Wert der `element`-Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>-Eigenschaft von `elements` (ein `IEnumerable<string>`).</span><span class="sxs-lookup"><span data-stu-id="2c63a-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="2c63a-137">Bei jeder nachfolgenden Iteration der `foreach`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `yield return`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2c63a-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="2c63a-138">Die `foreach`-Schleife wird beendet, wenn das Ende der Iteratormethode oder eine `yield break`-Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="2c63a-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="2c63a-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c63a-139">Example</span></span>

<span data-ttu-id="2c63a-140">Das folgende Beispiel weist eine `yield return`-Anweisung auf, die sich innerhalb einer `for`-Schleife befindet.</span><span class="sxs-lookup"><span data-stu-id="2c63a-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="2c63a-141">Jede Iteration des `foreach`-Anweisungstexts in der Methode `Main` erzeugt einen Aufruf an die Iteratorfunktion `Power`.</span><span class="sxs-lookup"><span data-stu-id="2c63a-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="2c63a-142">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `yield return`-Schleife zur nächsten Ausführung der `for`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2c63a-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="2c63a-143">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.IEnumerable>, was ein Iteratorschnittstellentyp ist.</span><span class="sxs-lookup"><span data-stu-id="2c63a-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="2c63a-144">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="2c63a-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="2c63a-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c63a-145">Example</span></span>

<span data-ttu-id="2c63a-146">Das folgende Beispiel zeigt einen `get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="2c63a-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="2c63a-147">Im Beispiel gibt jede `yield return`-Anweisung eine Instanz einer benutzerdefinierten Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="2c63a-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="2c63a-148">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2c63a-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2c63a-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c63a-149">See also</span></span>

- [<span data-ttu-id="2c63a-150">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2c63a-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c63a-151">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2c63a-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2c63a-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="2c63a-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="2c63a-153">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="2c63a-153">Iterators</span></span>](../../iterators.md)
