---
title: Yield-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: cc89e6f9bc2ccb4fff9a9fe12cd190a6b2d212dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401367"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="ae83c-102">Yield-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae83c-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="ae83c-103">Sendet das nächste Element einer Auflistung an eine- `For Each...Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ae83c-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae83c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae83c-104">Syntax</span></span>  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae83c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae83c-105">Parameters</span></span>  
  
|<span data-ttu-id="ae83c-106">Benennung</span><span class="sxs-lookup"><span data-stu-id="ae83c-106">Term</span></span>|<span data-ttu-id="ae83c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ae83c-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="ae83c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ae83c-108">Required.</span></span> <span data-ttu-id="ae83c-109">Ein Ausdruck, der implizit in den Typ der Iteratorfunktion oder-Zugriffsmethode konvertiert werden kann `Get` , die die `Yield` Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="ae83c-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae83c-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ae83c-110">Remarks</span></span>  
 <span data-ttu-id="ae83c-111">Die- `Yield` Anweisung gibt jeweils ein Element einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="ae83c-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="ae83c-112">Die- `Yield` Anweisung ist in einer Iteratorfunktion oder einem- `Get` Accessor enthalten, die benutzerdefinierte Iterationen über eine Auflistung ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae83c-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="ae83c-113">Sie nutzen eine Iteratorfunktion mit einem [for each... Next-Anweisung](for-each-next-statement.md) oder eine LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ae83c-113">You consume an iterator function by using a [For Each...Next Statement](for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="ae83c-114">Jede Iterationen der- `For Each` Schleife ruft die Iteratorfunktion auf.</span><span class="sxs-lookup"><span data-stu-id="ae83c-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="ae83c-115">Wenn eine- `Yield` Anweisung in der Iteratorfunktion erreicht wird, `expression` wird zurückgegeben, und die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ae83c-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="ae83c-116">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ae83c-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="ae83c-117">Eine implizite Konvertierung muss vom Typ der `expression` in der- `Yield` Anweisung bis zum Rückgabetyp des Iterators vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ae83c-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="ae83c-118">Sie können eine- `Exit Function` oder- `Return` Anweisung verwenden, um die Iterationen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="ae83c-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="ae83c-119">"Yield" ist kein reserviertes Wort und hat nur dann eine besondere Bedeutung, wenn es in einer `Iterator` Funktion oder einem `Get` Accessor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ae83c-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="ae83c-120">Weitere Informationen zu iteratorfunktionen und `Get` Accessoren finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="ae83c-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="ae83c-121">Iteratorfunktionen und Get-Accessoren</span><span class="sxs-lookup"><span data-stu-id="ae83c-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="ae83c-122">Die Deklaration einer Iteratorfunktion oder- `Get` Zugriffsmethode muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ae83c-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
- <span data-ttu-id="ae83c-123">Er muss einen [iteratormodifizierer](../modifiers/iterator.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="ae83c-123">It must include an [Iterator](../modifiers/iterator.md) modifier.</span></span>  
  
- <span data-ttu-id="ae83c-124">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="ae83c-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
- <span data-ttu-id="ae83c-125">Er darf keine `ByRef` Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ae83c-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="ae83c-126">Eine Iteratorfunktion kann nicht in einem Ereignis, Instanzkonstruktor, statischen Konstruktor oder statischen Dekonstruktor auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae83c-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="ae83c-127">Eine Iteratorfunktion kann eine anonyme Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="ae83c-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="ae83c-128">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="ae83c-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="ae83c-129">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="ae83c-129">Exception Handling</span></span>  
 <span data-ttu-id="ae83c-130">Eine- `Yield` Anweisung kann sich innerhalb eines `Try` Blocks eines [try... Catch... Abschließend-Anweisung](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ae83c-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span> <span data-ttu-id="ae83c-131">Ein `Try` -Block, der über eine `Yield` -Anweisung verfügt `Catch` , kann-Blöcke aufweisen und kann über einen- `Finally` Block verfügen.</span><span class="sxs-lookup"><span data-stu-id="ae83c-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="ae83c-132">Eine- `Yield` Anweisung darf sich nicht in einem- `Catch` Block oder einem- `Finally` Block befinden.</span><span class="sxs-lookup"><span data-stu-id="ae83c-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="ae83c-133">Wenn der `For Each` Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, wird ein- `Catch` Block in der Iteratorfunktion nicht ausgeführt, aber ein- `Finally` Block in der Iteratorfunktion wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ae83c-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="ae83c-134">Ein `Catch` Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die innerhalb der Iteratorfunktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="ae83c-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="ae83c-135">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="ae83c-135">Technical Implementation</span></span>  
 <span data-ttu-id="ae83c-136">Der folgende Code gibt einen `IEnumerable (Of String)` aus einer Iteratorfunktion zurück und durchläuft dann die Elemente der `IEnumerable (Of String)` .</span><span class="sxs-lookup"><span data-stu-id="ae83c-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="ae83c-137">Der-Befehl führt `MyIteratorFunction` nicht den Text der-Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="ae83c-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="ae83c-138">Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="ae83c-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="ae83c-139">Bei einer Iteration der `For Each`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ae83c-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="ae83c-140">Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="ae83c-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="ae83c-141">Die- `Yield` Anweisung gibt einen Ausdruck zurück, der nicht nur den Wert der `element` Variablen für die Verwendung durch den Schleifen Text, sondern auch die- <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Eigenschaft von-Elementen bestimmt, bei der es sich um handelt `IEnumerable (Of String)` .</span><span class="sxs-lookup"><span data-stu-id="ae83c-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="ae83c-142">Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ae83c-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="ae83c-143">Die `For Each` Schleife wird beendet, wenn das Ende der Iteratorfunktion oder einer- `Return` oder- `Exit Function` Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ae83c-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae83c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae83c-144">Example</span></span>  
 <span data-ttu-id="ae83c-145">Das folgende Beispiel enthält eine- `Yield` Anweisung, die sich innerhalb einer [for... Nächste](for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="ae83c-145">The following example has a `Yield` statement that is inside a [For…Next](for-next-statement.md) loop.</span></span> <span data-ttu-id="ae83c-146">Jede Iterationen des [foreach](for-each-next-statement.md) - `Main` Anweisungs Texts in erstellt einen-Rückruf für die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="ae83c-146">Each iteration of the [For Each](for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="ae83c-147">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ae83c-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="ae83c-148">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601> , ein Iteratorschnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="ae83c-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="ae83c-149">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="ae83c-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a><span data-ttu-id="ae83c-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae83c-150">Example</span></span>  
 <span data-ttu-id="ae83c-151">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="ae83c-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="ae83c-152">Die Eigenschaften Deklaration enthält einen `Iterator` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="ae83c-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 <span data-ttu-id="ae83c-153">Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="ae83c-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae83c-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae83c-154">See also</span></span>

- [<span data-ttu-id="ae83c-155">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ae83c-155">Statements</span></span>](index.md)
