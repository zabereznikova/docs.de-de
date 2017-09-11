---
title: Yield-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="691d9-102">Yield-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="691d9-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="691d9-103">Sendet das nächste Element einer Auflistung in eine `For Each...Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="691d9-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="691d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="691d9-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="691d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="691d9-105">Parameters</span></span>  
  
|<span data-ttu-id="691d9-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="691d9-106">Term</span></span>|<span data-ttu-id="691d9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="691d9-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="691d9-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="691d9-108">Required.</span></span> <span data-ttu-id="691d9-109">Ein Ausdruck, der implizit in den Typ der Iteratorfunktion ist oder `Get` -Accessor, der enthält die `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="691d9-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="691d9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="691d9-110">Remarks</span></span>  
 <span data-ttu-id="691d9-111">Die `Yield` -Anweisung gibt ein Element einer Auflistung zu einem Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="691d9-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="691d9-112">Die `Yield` -Anweisung wird in einer Iteratorfunktion eingefügt oder `Get` -Accessor, der über eine Auflistung benutzerdefinierte Iterationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="691d9-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="691d9-113">Sie erzeugen eine Iteratorfunktion, indem eine [für jeden... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="691d9-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="691d9-114">Jede Iteration der `For Each` -Schleife Ruft den Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="691d9-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="691d9-115">Wenn ein `Yield` -Anweisung erreicht wird, in der Iteratorfunktion `expression` zurückgegeben wird, und die aktuelle Position im Code beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="691d9-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="691d9-116">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="691d9-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="691d9-117">Eine implizite Konvertierung muss vorhanden sein, von dem Typ des `expression` in der `Yield` Anweisung in den Rückgabetyp des Iterators.</span><span class="sxs-lookup"><span data-stu-id="691d9-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="691d9-118">Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="691d9-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="691d9-119">"" Ist ein reserviertes Wort und hat eine besondere Bedeutung nur bei Verwendung in einem `Iterator` Funktion oder `Get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="691d9-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="691d9-120">Weitere Informationen zu iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="691d9-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="691d9-121">Iteratorfunktionen und Get-Accessoren</span><span class="sxs-lookup"><span data-stu-id="691d9-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="691d9-122">Die Deklaration einer Funktion Iterator oder `Get` Accessor muss die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="691d9-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="691d9-123">Muss ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="691d9-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="691d9-124">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="691d9-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="691d9-125">Keine `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="691d9-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="691d9-126">Eine Iteratorfunktion kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.</span><span class="sxs-lookup"><span data-stu-id="691d9-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="691d9-127">Eine Iteratorfunktion kann eine anonyme Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="691d9-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="691d9-128">Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="691d9-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="691d9-129">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="691d9-129">Exception Handling</span></span>  
 <span data-ttu-id="691d9-130">Ein `Yield` Anweisung kann innerhalb einer `Try` -Block eine [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="691d9-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="691d9-131">Ein `Try` blockieren, die eine `Yield` -Anweisung kann verfügen `Catch` blockiert, und kann einen `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="691d9-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="691d9-132">Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="691d9-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="691d9-133">Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, ein `Catch` -Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="691d9-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="691d9-134">Ein `Catch` Block innerhalb einer Iteratorfunktion nur Ausnahmen abzufangen, die innerhalb der Iteratorfunktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="691d9-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="691d9-135">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="691d9-135">Technical Implementation</span></span>  
 <span data-ttu-id="691d9-136">Der folgende code gibt ein `IEnumerable (Of String)` aus einer Iteratorfunktion und iteriert dann durch die Elemente der `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="691d9-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="691d9-137">Der Aufruf von `MyIteratorFunction` führt nicht den Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="691d9-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="691d9-138">Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="691d9-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="691d9-139">Bei einer Iteration der der `For Each` -Schleife, die <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A></span><span class="sxs-lookup"><span data-stu-id="691d9-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="691d9-140">Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="691d9-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="691d9-141">Die `Yield` Anweisung gibt einen Ausdruck, der nicht nur der Wert bestimmt die `element` -Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>-Eigenschaft der Elemente, die eine `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A></span><span class="sxs-lookup"><span data-stu-id="691d9-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="691d9-142">Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="691d9-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="691d9-143">Die `For Each` Schleife wird beendet, wenn das Ende der Iteratorfunktion oder ein `Return` oder `Exit Function` -Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="691d9-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="691d9-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="691d9-144">Example</span></span>  
 <span data-ttu-id="691d9-145">Im folgenden Beispiel ist ein `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="691d9-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="691d9-146">Jeder Iteration der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) Anweisungstext in `Main` erstellt einen Aufruf an die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="691d9-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="691d9-147">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="691d9-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="691d9-148">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, ein Iteratorschnittstellentyp.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="691d9-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="691d9-149">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="691d9-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="691d9-150">[!code-vb[VbVbalrStatements&#98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="691d9-150">[!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="691d9-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="691d9-151">Example</span></span>  
 <span data-ttu-id="691d9-152">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="691d9-152">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="691d9-153">Die Eigenschaftendeklaration enthält eine `Iterator` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="691d9-153">The property declaration includes an `Iterator` modifier.</span></span>  
  
 <span data-ttu-id="691d9-154">[!code-vb[VbVbalrStatements&#99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="691d9-154">[!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="691d9-155">Weitere Beispiele finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="691d9-155">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="691d9-156">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="691d9-156">Requirements</span></span>  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="691d9-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="691d9-157">See Also</span></span>  
 <span data-ttu-id="691d9-158">[Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span><span class="sxs-lookup"><span data-stu-id="691d9-158">[Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span></span>  
<span data-ttu-id="691d9-159"> [Anweisungen](../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="691d9-159"> [Statements](../../../visual-basic/language-reference/statements/index.md)</span></span>
