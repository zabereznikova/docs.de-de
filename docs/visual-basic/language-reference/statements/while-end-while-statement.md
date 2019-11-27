---
title: While...End While-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352748"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="16c71-102">While...End While-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16c71-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="16c71-103">Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung `True`ist.</span><span class="sxs-lookup"><span data-stu-id="16c71-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c71-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16c71-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="16c71-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="16c71-105">Parts</span></span>  
  
|<span data-ttu-id="16c71-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="16c71-106">Term</span></span>|<span data-ttu-id="16c71-107">Definition</span><span class="sxs-lookup"><span data-stu-id="16c71-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="16c71-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="16c71-108">Required.</span></span> <span data-ttu-id="16c71-109">`Boolean` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="16c71-109">`Boolean` expression.</span></span> <span data-ttu-id="16c71-110">Wenn `condition` `Nothing`ist, wird es von Visual Basic als `False`behandelt.</span><span class="sxs-lookup"><span data-stu-id="16c71-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="16c71-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="16c71-111">Optional.</span></span> <span data-ttu-id="16c71-112">Eine oder mehrere Anweisungen nach `While`, die jedes Mal ausgeführt werden, wenn `condition` `True`wird.</span><span class="sxs-lookup"><span data-stu-id="16c71-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="16c71-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="16c71-113">Optional.</span></span> <span data-ttu-id="16c71-114">Überträgt die Steuerung an die nächste Iterations `While` Blocks.</span><span class="sxs-lookup"><span data-stu-id="16c71-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="16c71-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="16c71-115">Optional.</span></span> <span data-ttu-id="16c71-116">Überträgt die Steuerung aus dem `While`-Block.</span><span class="sxs-lookup"><span data-stu-id="16c71-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="16c71-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="16c71-117">Required.</span></span> <span data-ttu-id="16c71-118">Beendet die Definition des `While`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="16c71-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16c71-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16c71-119">Remarks</span></span>  
 <span data-ttu-id="16c71-120">Verwenden Sie eine `While...End While` Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung `True`bleibt.</span><span class="sxs-lookup"><span data-stu-id="16c71-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="16c71-121">Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="16c71-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="16c71-122">Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="16c71-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16c71-123">Das `While`-Schlüsselwort wird auch in der [Do... Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), die [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und die [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="16c71-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="16c71-124">Wenn `condition` `True`ist, werden alle `statements` ausgeführt, bis die `End While`-Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="16c71-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="16c71-125">Die Steuerung kehrt dann zur `While`-Anweisung zurück, und `condition` wird erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="16c71-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="16c71-126">Wenn `condition` weiterhin `True`ist, wird der Prozess wiederholt.</span><span class="sxs-lookup"><span data-stu-id="16c71-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="16c71-127">Wenn `False`, wird die Steuerung an die Anweisung weitergeleitet, die auf die `End While` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="16c71-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="16c71-128">Die `While`-Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="16c71-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="16c71-129">Die Schleife wird fortgesetzt, während die Bedingung `True`bleibt.</span><span class="sxs-lookup"><span data-stu-id="16c71-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="16c71-130">Wenn `condition` bei der ersten Eingabe der Schleife `False` wird, wird Sie auch nicht einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="16c71-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="16c71-131">Die `condition` ergibt in der Regel einen Vergleich zweier Werte, es kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`) ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="16c71-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="16c71-132">Dieser Ausdruck kann einen Wert eines anderen Datentyps (z. b. einen numerischen Typ) enthalten, der in `Boolean`konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="16c71-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="16c71-133">Sie können `While` Schleifen schachteln, indem Sie eine Schleife in einer anderen platzieren.</span><span class="sxs-lookup"><span data-stu-id="16c71-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="16c71-134">Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln.</span><span class="sxs-lookup"><span data-stu-id="16c71-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="16c71-135">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="16c71-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="16c71-136">Beenden während</span><span class="sxs-lookup"><span data-stu-id="16c71-136">Exit While</span></span>  
 <span data-ttu-id="16c71-137">Die [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, eine `While` Schleife zu beenden.</span><span class="sxs-lookup"><span data-stu-id="16c71-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="16c71-138">`Exit While` überträgt die Steuerung sofort an die Anweisung, die auf die `End While` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="16c71-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="16c71-139">In der Regel verwenden Sie `Exit While`, nachdem eine bestimmte Bedingung ausgewertet wurde (z. b. in einer `If...Then...Else` Struktur).</span><span class="sxs-lookup"><span data-stu-id="16c71-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="16c71-140">Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung.</span><span class="sxs-lookup"><span data-stu-id="16c71-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="16c71-141">Sie können `Exit While` verwenden, wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="16c71-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="16c71-142">Anschließend können Sie mit `Exit While` die Schleife mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="16c71-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="16c71-143">Sie können beliebig viele `Exit While` Anweisungen in der `While`-Schleife platzieren.</span><span class="sxs-lookup"><span data-stu-id="16c71-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="16c71-144">Wenn Sie in geschachtelten `While` Schleifen verwendet wird, überträgt `Exit While` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="16c71-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="16c71-145">Die `Continue While`-Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="16c71-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="16c71-146">Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="16c71-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16c71-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16c71-147">Example</span></span>  
 <span data-ttu-id="16c71-148">Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index`-Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="16c71-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="16c71-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16c71-149">Example</span></span>  
 <span data-ttu-id="16c71-150">Das folgende Beispiel veranschaulicht die Verwendung der Anweisungen `Continue While` und `Exit While`.</span><span class="sxs-lookup"><span data-stu-id="16c71-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="16c71-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16c71-151">Example</span></span>  
 <span data-ttu-id="16c71-152">Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="16c71-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="16c71-153">Die <xref:System.IO.File.OpenText%2A>-Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> zurück, die die Zeichen liest.</span><span class="sxs-lookup"><span data-stu-id="16c71-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="16c71-154">In der `While` Bedingung bestimmt die <xref:System.IO.StreamReader.Peek%2A>-Methode des `StreamReader`, ob die Datei zusätzliche Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="16c71-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="16c71-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c71-155">See also</span></span>

- [<span data-ttu-id="16c71-156">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="16c71-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="16c71-157">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16c71-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="16c71-158">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16c71-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="16c71-159">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="16c71-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="16c71-160">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="16c71-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="16c71-161">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16c71-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="16c71-162">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="16c71-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
