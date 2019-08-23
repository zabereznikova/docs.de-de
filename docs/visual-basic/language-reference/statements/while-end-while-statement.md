---
title: While...End While-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 7ea0814c587f65ddc1f114d2314ac7147143d40d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965811"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="838ca-102">While...End While-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="838ca-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="838ca-103">Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung `True`ist.</span><span class="sxs-lookup"><span data-stu-id="838ca-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="838ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="838ca-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="838ca-105">Teile</span><span class="sxs-lookup"><span data-stu-id="838ca-105">Parts</span></span>  
  
|<span data-ttu-id="838ca-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="838ca-106">Term</span></span>|<span data-ttu-id="838ca-107">Definition</span><span class="sxs-lookup"><span data-stu-id="838ca-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="838ca-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="838ca-108">Required.</span></span> <span data-ttu-id="838ca-109">`Boolean`Begriff.</span><span class="sxs-lookup"><span data-stu-id="838ca-109">`Boolean` expression.</span></span> <span data-ttu-id="838ca-110">Wenn `condition`den Wert `False`hat, wird er von Visual Basic behandelt. `Nothing`</span><span class="sxs-lookup"><span data-stu-id="838ca-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="838ca-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="838ca-111">Optional.</span></span> <span data-ttu-id="838ca-112">Eine oder mehrere der folgenden `While`Anweisungen, die jedes Mal `condition` ausgeführt `True`werden, ist.</span><span class="sxs-lookup"><span data-stu-id="838ca-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="838ca-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="838ca-113">Optional.</span></span> <span data-ttu-id="838ca-114">Überträgt die Steuerung an die nächste Iterationen des `While` -Blocks.</span><span class="sxs-lookup"><span data-stu-id="838ca-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="838ca-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="838ca-115">Optional.</span></span> <span data-ttu-id="838ca-116">Überträgt die Steuerung aus dem `While` -Block.</span><span class="sxs-lookup"><span data-stu-id="838ca-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="838ca-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="838ca-117">Required.</span></span> <span data-ttu-id="838ca-118">Beendet die Definition des `While`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="838ca-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="838ca-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="838ca-119">Remarks</span></span>  
 <span data-ttu-id="838ca-120">Verwenden Sie `While...End While` eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung verbleibt. `True`</span><span class="sxs-lookup"><span data-stu-id="838ca-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="838ca-121">Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="838ca-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="838ca-122">Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="838ca-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="838ca-123">Das `While` Schlüsselwort wird auch im [Do... Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md), die [Skip While-Klausel](../../../visual-basic/language-reference/queries/skip-while-clause.md) und die [Take While-Klausel](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="838ca-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="838ca-124">`condition` `statements` Wenn den Wert `End While` hat, wird alle ausgeführt, bis die-Anweisung gefunden wurde. `True`</span><span class="sxs-lookup"><span data-stu-id="838ca-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="838ca-125">Dann kehrt die `While` Steuerung zur-Anweisung zurück `condition` und wird erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="838ca-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="838ca-126">Wenn `condition` weiterhin`True`ist, wird der Prozess wiederholt.</span><span class="sxs-lookup"><span data-stu-id="838ca-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="838ca-127">Wenn dies der `False`Fall ist, wird die Steuerung an die Anweisung `End While` weitergeleitet, die der Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="838ca-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="838ca-128">Die `While` -Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="838ca-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="838ca-129">Die Schleife wird fortgesetzt, während `True`die Bedingung verbleibt.</span><span class="sxs-lookup"><span data-stu-id="838ca-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="838ca-130">Wenn `condition` der `False` Wert ist, wenn Sie die Schleife zum ersten Mal eingeben, wird Sie auch nicht einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="838ca-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="838ca-131">Das `condition` Ergebnis ergibt sich in der Regel aus einem Vergleich von zwei Werten, aber es kann sich um einen beliebigen Ausdruck handeln, der zu einem`True` [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (oder `False`) ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="838ca-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="838ca-132">Dieser Ausdruck kann einen Wert eines anderen Datentyps enthalten, z. b. einen numerischen Typ, der `Boolean`in konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="838ca-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="838ca-133">Sie können `While` Schleifen schachteln, indem Sie eine Schleife in einer anderen platzieren.</span><span class="sxs-lookup"><span data-stu-id="838ca-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="838ca-134">Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln.</span><span class="sxs-lookup"><span data-stu-id="838ca-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="838ca-135">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="838ca-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="838ca-136">Beenden während</span><span class="sxs-lookup"><span data-stu-id="838ca-136">Exit While</span></span>  
 <span data-ttu-id="838ca-137">Die [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, `While` eine Schleife zu beenden.</span><span class="sxs-lookup"><span data-stu-id="838ca-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="838ca-138">`Exit While`überträgt die Steuerung sofort an die-Anweisung, `End While` die auf die-Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="838ca-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="838ca-139">Normalerweise verwenden `Exit While` Sie, nachdem eine bestimmte Bedingung ausgewertet wurde (z. `If...Then...Else` b. in einer-Struktur).</span><span class="sxs-lookup"><span data-stu-id="838ca-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="838ca-140">Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung.</span><span class="sxs-lookup"><span data-stu-id="838ca-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="838ca-141">Sie können verwenden `Exit While` , wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen könnte.</span><span class="sxs-lookup"><span data-stu-id="838ca-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="838ca-142">Anschließend können Sie verwenden `Exit While` , um die Schleife zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="838ca-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="838ca-143">Sie können beliebig viele `Exit While` Anweisungen in der `While` Schleife platzieren.</span><span class="sxs-lookup"><span data-stu-id="838ca-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="838ca-144">`Exit While` Überträgt bei Verwendung in `While` geschachtelten Schleifen die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="838ca-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="838ca-145">Die `Continue While` -Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="838ca-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="838ca-146">Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="838ca-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="838ca-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="838ca-147">Example</span></span>  
 <span data-ttu-id="838ca-148">Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index` -Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="838ca-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="838ca-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="838ca-149">Example</span></span>  
 <span data-ttu-id="838ca-150">Im folgenden Beispiel wird die Verwendung `Continue While` der-Anweisung und der- `Exit While` Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="838ca-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="838ca-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="838ca-151">Example</span></span>  
 <span data-ttu-id="838ca-152">Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="838ca-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="838ca-153">Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt <xref:System.IO.StreamReader> einen zurück, der die Zeichen liest.</span><span class="sxs-lookup"><span data-stu-id="838ca-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="838ca-154">In der `While` Bedingung `StreamReader` bestimmt die <xref:System.IO.StreamReader.Peek%2A> -Methode von, ob die Datei zusätzliche Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="838ca-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="838ca-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="838ca-155">See also</span></span>

- [<span data-ttu-id="838ca-156">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="838ca-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="838ca-157">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="838ca-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="838ca-158">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="838ca-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="838ca-159">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="838ca-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="838ca-160">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="838ca-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="838ca-161">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="838ca-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="838ca-162">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="838ca-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
