---
title: Yield-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: f938ad29df54ade6722f3de33e931c851ade8c21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604866"
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="89354-102">Yield-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89354-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="89354-103">Sendet das nächste Element einer Auflistung in ein `For Each...Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="89354-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89354-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89354-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89354-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89354-105">Parameters</span></span>  
  
|<span data-ttu-id="89354-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="89354-106">Term</span></span>|<span data-ttu-id="89354-107">Definition</span><span class="sxs-lookup"><span data-stu-id="89354-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="89354-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89354-108">Required.</span></span> <span data-ttu-id="89354-109">Ein Ausdruck, der implizit in den Typ der Iteratorfunktion ist oder `Get` Accessor, der enthält die `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="89354-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89354-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89354-110">Remarks</span></span>  
 <span data-ttu-id="89354-111">Die `Yield` -Anweisung gibt ein Element einer Auflistung zu einem Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="89354-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="89354-112">Die `Yield` -Anweisung wird in einer Iteratorfunktion eingefügt oder `Get` Accessor, der benutzerdefinierte Iterationen durch eine Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="89354-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="89354-113">Sie nutzen eine Iteratorfunktion mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="89354-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="89354-114">Jede Iteration der `For Each` Schleife aufgerufen, wenn die Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="89354-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="89354-115">Wenn eine `Yield` -Anweisung erreicht wird, in der Iteratorfunktion `expression` zurückgegeben wird, und die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="89354-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="89354-116">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="89354-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="89354-117">Eine implizite Konvertierung muss vorhanden sein, von dem Typ des `expression` in der `Yield` Anweisung in den Rückgabetyp des Iterators.</span><span class="sxs-lookup"><span data-stu-id="89354-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="89354-118">Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="89354-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="89354-119">Ist ein reserviertes Wort und hat eine besondere Bedeutung, wenn sie im verwendet wird "Yield" ein `Iterator` Funktion oder `Get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="89354-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="89354-120">Weitere Informationen zu iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="89354-120">For more information about iterator functions and `Get` accessors, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="89354-121">Iteratorfunktionen und Get-Accessoren</span><span class="sxs-lookup"><span data-stu-id="89354-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="89354-122">Die Deklaration einer Funktion Iterator oder `Get` Accessor muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="89354-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="89354-123">Muss ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="89354-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="89354-124">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="89354-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="89354-125">Es sind keine `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="89354-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="89354-126">Eine Iteratorfunktion kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.</span><span class="sxs-lookup"><span data-stu-id="89354-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="89354-127">Eine Iteratorfunktion kann mit einer anonymen Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="89354-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="89354-128">Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="89354-128">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="89354-129">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="89354-129">Exception Handling</span></span>  
 <span data-ttu-id="89354-130">Ein `Yield` Anweisung kann innerhalb einer `Try` -Block ein [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="89354-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="89354-131">Ein `Try` Block, der verfügt über eine `Yield` -Anweisung kann verfügen `Catch` blockiert und können eine `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="89354-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="89354-132">Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="89354-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="89354-133">Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, eine `Catch` Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="89354-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="89354-134">Ein `Catch` Block innerhalb einer Iteratorfunktion fängt nur Ausnahmen, die innerhalb der Iteratorfunktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="89354-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="89354-135">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="89354-135">Technical Implementation</span></span>  
 <span data-ttu-id="89354-136">Der folgende code gibt ein `IEnumerable (Of String)` aus einer Iteratorfunktion und iteriert dann durch die Elemente der `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="89354-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="89354-137">Der Aufruf von `MyIteratorFunction` führt nicht den Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="89354-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="89354-138">Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="89354-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="89354-139">Bei einer Iteration der `For Each`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="89354-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="89354-140">Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="89354-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="89354-141">Die `Yield` Anweisung gibt einen Ausdruck, der nicht nur der Wert bestimmt die `element` -Variable für die Verwendung vom Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Eigenschaft von Elementen, die eine `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="89354-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="89354-142">Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="89354-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="89354-143">Die `For Each` Schleife abgeschlossen wird, wenn das Ende der Iteratorfunktion oder ein `Return` oder `Exit Function` -Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="89354-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89354-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89354-144">Example</span></span>  
 <span data-ttu-id="89354-145">Im folgenden Beispiel ist ein `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="89354-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="89354-146">Jede Iteration der der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erzeugt einen Aufruf an die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="89354-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="89354-147">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="89354-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="89354-148">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, Iteratorschnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="89354-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="89354-149">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="89354-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="89354-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89354-150">Example</span></span>  
 <span data-ttu-id="89354-151">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="89354-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="89354-152">Die Eigenschaftendeklaration enthält eine `Iterator` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="89354-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="89354-153">Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="89354-153">For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89354-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89354-154">See Also</span></span>  
 [<span data-ttu-id="89354-155">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="89354-155">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
