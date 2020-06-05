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
ms.openlocfilehash: d9eb8cb95d46e860aa127954d7b44e37991d4a13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391585"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="0c70c-102">While...End While-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c70c-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="0c70c-103">Führt eine Reihe von-Anweisungen aus, solange eine bestimmte Bedingung ist `True` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c70c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c70c-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="0c70c-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0c70c-105">Parts</span></span>  
  
|<span data-ttu-id="0c70c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0c70c-106">Term</span></span>|<span data-ttu-id="0c70c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0c70c-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="0c70c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c70c-108">Required.</span></span> <span data-ttu-id="0c70c-109">`Boolean`-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0c70c-109">`Boolean` expression.</span></span> <span data-ttu-id="0c70c-110">Wenn den Wert `condition` `Nothing` hat, wird er von Visual Basic behandelt `False` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="0c70c-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="0c70c-111">Optional.</span></span> <span data-ttu-id="0c70c-112">Eine oder mehrere der folgenden Anweisungen `While` , die jedes Mal ausgeführt werden, `condition` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="0c70c-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="0c70c-113">Optional.</span></span> <span data-ttu-id="0c70c-114">Überträgt die Steuerung an die nächste Iterationen des- `While` Blocks.</span><span class="sxs-lookup"><span data-stu-id="0c70c-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="0c70c-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="0c70c-115">Optional.</span></span> <span data-ttu-id="0c70c-116">Überträgt die Steuerung aus dem- `While` Block.</span><span class="sxs-lookup"><span data-stu-id="0c70c-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="0c70c-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0c70c-117">Required.</span></span> <span data-ttu-id="0c70c-118">Beendet die Definition des `While`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="0c70c-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c70c-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0c70c-119">Remarks</span></span>  
 <span data-ttu-id="0c70c-120">Verwenden `While...End While` Sie eine Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, solange eine Bedingung verbleibt `True` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="0c70c-121">Wenn Sie mehr Flexibilität benötigen, um die Bedingung zu testen, oder das Ergebnis, das Sie testen, bevorzugen Sie ggf. den Vorgang [... Loop-Anweisung](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0c70c-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](do-loop-statement.md).</span></span> <span data-ttu-id="0c70c-122">Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="0c70c-122">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c70c-123">Das `While` Schlüsselwort wird auch im [Do... Schleifen Anweisung](do-loop-statement.md), die [Skip While-Klausel](../queries/skip-while-clause.md) und die [Take While-Klausel](../queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0c70c-123">The `While` keyword is also used in the [Do...Loop Statement](do-loop-statement.md), the [Skip While Clause](../queries/skip-while-clause.md) and the [Take While Clause](../queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="0c70c-124">Wenn `condition` `True` den Wert hat, `statements` wird alle ausgeführt, bis die-Anweisung gefunden wurde `End While` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="0c70c-125">Dann kehrt die Steuerung zur `While` -Anweisung zurück und `condition` wird erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0c70c-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="0c70c-126">Wenn `condition` weiterhin ist `True` , wird der Prozess wiederholt.</span><span class="sxs-lookup"><span data-stu-id="0c70c-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="0c70c-127">Wenn dies der Fall ist `False` , wird die Steuerung an die Anweisung weitergeleitet, die der `End While` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="0c70c-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="0c70c-128">Die- `While` Anweisung überprüft die Bedingung immer, bevor die Schleife gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0c70c-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="0c70c-129">Die Schleife wird fortgesetzt, während die Bedingung verbleibt `True` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="0c70c-130">Wenn `condition` der Wert ist `False` , wenn Sie die Schleife zum ersten Mal eingeben, wird Sie auch nicht einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0c70c-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="0c70c-131">Das `condition` Ergebnis ergibt sich in der Regel aus einem Vergleich von zwei Werten, aber es kann sich um einen beliebigen Ausdruck handeln, der zu einem [booleschen Datentyp](../data-types/boolean-data-type.md) Wert ( `True` oder) ausgewertet wird `False` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="0c70c-132">Dieser Ausdruck kann einen Wert eines anderen Datentyps enthalten, z. b. einen numerischen Typ, der in konvertiert wurde `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="0c70c-133">Sie können Schleifen schachteln, `While` indem Sie eine Schleife in einer anderen platzieren.</span><span class="sxs-lookup"><span data-stu-id="0c70c-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="0c70c-134">Sie können auch verschiedene Arten von Steuerungsstrukturen innerhalb eines anderen schachteln.</span><span class="sxs-lookup"><span data-stu-id="0c70c-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="0c70c-135">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="0c70c-135">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="0c70c-136">Beenden während</span><span class="sxs-lookup"><span data-stu-id="0c70c-136">Exit While</span></span>  
 <span data-ttu-id="0c70c-137">Die [Exit While](exit-statement.md) -Anweisung kann eine andere Möglichkeit bieten, eine Schleife zu beenden `While` .</span><span class="sxs-lookup"><span data-stu-id="0c70c-137">The [Exit While](exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="0c70c-138">`Exit While`überträgt die Steuerung sofort an die-Anweisung, die auf die- `End While` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="0c70c-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="0c70c-139">Normalerweise verwenden Sie `Exit While` , nachdem eine bestimmte Bedingung ausgewertet wurde (z. b. in einer- `If...Then...Else` Struktur).</span><span class="sxs-lookup"><span data-stu-id="0c70c-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="0c70c-140">Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung.</span><span class="sxs-lookup"><span data-stu-id="0c70c-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="0c70c-141">Sie können verwenden, `Exit While` Wenn Sie eine Bedingung testen, die zu einer *Endlosschleife*führen könnte. Dies ist eine Schleife, die eine extrem große oder sogar unendliche Anzahl von Zeiten ausführen könnte.</span><span class="sxs-lookup"><span data-stu-id="0c70c-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="0c70c-142">Anschließend können Sie verwenden `Exit While` , um die Schleife zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c70c-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="0c70c-143">Sie können beliebig viele `Exit While` Anweisungen in der `While` Schleife platzieren.</span><span class="sxs-lookup"><span data-stu-id="0c70c-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="0c70c-144">Überträgt bei Verwendung in geschachtelten `While` Schleifen `Exit While` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="0c70c-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="0c70c-145">Die- `Continue While` Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife.</span><span class="sxs-lookup"><span data-stu-id="0c70c-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="0c70c-146">Weitere Informationen finden Sie unter [Continue-Anweisung](continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0c70c-146">For more information, see [Continue Statement](continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c70c-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c70c-147">Example</span></span>  
 <span data-ttu-id="0c70c-148">Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die- `index` Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="0c70c-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="0c70c-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c70c-149">Example</span></span>  
 <span data-ttu-id="0c70c-150">Im folgenden Beispiel wird die Verwendung der `Continue While` -Anweisung und der- `Exit While` Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0c70c-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="0c70c-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c70c-151">Example</span></span>  
 <span data-ttu-id="0c70c-152">Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="0c70c-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="0c70c-153">Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt einen zurück <xref:System.IO.StreamReader> , der die Zeichen liest.</span><span class="sxs-lookup"><span data-stu-id="0c70c-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="0c70c-154">In der `While` Bedingung bestimmt die- <xref:System.IO.StreamReader.Peek%2A> Methode von, `StreamReader` ob die Datei zusätzliche Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="0c70c-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="0c70c-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c70c-155">See also</span></span>

- [<span data-ttu-id="0c70c-156">Schleifenstrukturen</span><span class="sxs-lookup"><span data-stu-id="0c70c-156">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="0c70c-157">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c70c-157">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="0c70c-158">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c70c-158">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="0c70c-159">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0c70c-159">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="0c70c-160">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0c70c-160">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="0c70c-161">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c70c-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="0c70c-162">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0c70c-162">Continue Statement</span></span>](continue-statement.md)
