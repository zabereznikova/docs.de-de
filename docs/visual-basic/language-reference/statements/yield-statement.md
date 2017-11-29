---
title: Yield-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99f5129d5cb43cddfb17731f337a72fae22d3626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="19866-102">Yield-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19866-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="19866-103">Sendet das nächste Element einer Auflistung in ein `For Each...Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="19866-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19866-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19866-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19866-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19866-105">Parameters</span></span>  
  
|<span data-ttu-id="19866-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="19866-106">Term</span></span>|<span data-ttu-id="19866-107">Definition</span><span class="sxs-lookup"><span data-stu-id="19866-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="19866-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="19866-108">Required.</span></span> <span data-ttu-id="19866-109">Ein Ausdruck, der implizit in den Typ der Iteratorfunktion ist oder `Get` Accessor, der enthält die `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="19866-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19866-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19866-110">Remarks</span></span>  
 <span data-ttu-id="19866-111">Die `Yield` -Anweisung gibt ein Element einer Auflistung zu einem Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="19866-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="19866-112">Die `Yield` -Anweisung wird in einer Iteratorfunktion eingefügt oder `Get` Accessor, der benutzerdefinierte Iterationen durch eine Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="19866-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="19866-113">Sie nutzen eine Iteratorfunktion mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="19866-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="19866-114">Jede Iteration der `For Each` Schleife aufgerufen, wenn die Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="19866-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="19866-115">Wenn eine `Yield` -Anweisung erreicht wird, in der Iteratorfunktion `expression` zurückgegeben wird, und die aktuelle Position im Code wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="19866-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="19866-116">Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="19866-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="19866-117">Eine implizite Konvertierung muss vorhanden sein, von dem Typ des `expression` in der `Yield` Anweisung in den Rückgabetyp des Iterators.</span><span class="sxs-lookup"><span data-stu-id="19866-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="19866-118">Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="19866-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="19866-119">Ist ein reserviertes Wort und hat eine besondere Bedeutung, wenn sie im verwendet wird "Yield" ein `Iterator` Funktion oder `Get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="19866-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="19866-120">Weitere Informationen zu iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="19866-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="19866-121">Iteratorfunktionen und Get-Accessoren</span><span class="sxs-lookup"><span data-stu-id="19866-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="19866-122">Die Deklaration einer Funktion Iterator oder `Get` Accessor muss die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="19866-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="19866-123">Muss ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="19866-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="19866-124">Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.</span><span class="sxs-lookup"><span data-stu-id="19866-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="19866-125">Es sind keine `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="19866-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="19866-126">Eine Iteratorfunktion kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.</span><span class="sxs-lookup"><span data-stu-id="19866-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="19866-127">Eine Iteratorfunktion kann mit einer anonymen Funktion sein.</span><span class="sxs-lookup"><span data-stu-id="19866-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="19866-128">Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="19866-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="19866-129">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="19866-129">Exception Handling</span></span>  
 <span data-ttu-id="19866-130">Ein `Yield` Anweisung kann innerhalb einer `Try` -Block ein [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="19866-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="19866-131">Ein `Try` Block, der verfügt über eine `Yield` -Anweisung kann verfügen `Catch` blockiert und können eine `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="19866-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="19866-132">Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="19866-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="19866-133">Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, eine `Catch` Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19866-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="19866-134">Ein `Catch` Block innerhalb einer Iteratorfunktion fängt nur Ausnahmen, die innerhalb der Iteratorfunktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="19866-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="19866-135">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="19866-135">Technical Implementation</span></span>  
 <span data-ttu-id="19866-136">Der folgende code gibt ein `IEnumerable (Of String)` aus einer Iteratorfunktion und iteriert dann durch die Elemente der `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="19866-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="19866-137">Der Aufruf von `MyIteratorFunction` führt nicht den Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="19866-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="19866-138">Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.</span><span class="sxs-lookup"><span data-stu-id="19866-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="19866-139">Bei einer Iteration der `For Each`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="19866-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="19866-140">Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="19866-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="19866-141">Die `Yield` Anweisung gibt einen Ausdruck, der nicht nur der Wert bestimmt die `element` -Variable für die Verwendung vom Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Eigenschaft von Elementen, die eine `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="19866-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="19866-142">Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="19866-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="19866-143">Die `For Each` Schleife abgeschlossen wird, wenn das Ende der Iteratorfunktion oder ein `Return` oder `Exit Function` -Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="19866-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19866-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19866-144">Example</span></span>  
 <span data-ttu-id="19866-145">Im folgenden Beispiel ist ein `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="19866-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="19866-146">Jede Iteration der der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erzeugt einen Aufruf an die `Power` Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="19866-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="19866-147">Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="19866-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="19866-148">Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, Iteratorschnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="19866-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="19866-149">Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="19866-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="19866-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19866-150">Example</span></span>  
 <span data-ttu-id="19866-151">Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist.</span><span class="sxs-lookup"><span data-stu-id="19866-151">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="19866-152">Die Eigenschaftendeklaration enthält eine `Iterator` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="19866-152">The property declaration includes an `Iterator` modifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 <span data-ttu-id="19866-153">Weitere Beispiele finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="19866-153">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19866-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19866-154">See Also</span></span>  
 [<span data-ttu-id="19866-155">Iteratoren</span><span class="sxs-lookup"><span data-stu-id="19866-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="19866-156">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="19866-156">Statements</span></span>](../../../visual-basic/language-reference/statements/index.md)
