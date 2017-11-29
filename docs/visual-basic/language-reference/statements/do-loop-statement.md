---
title: Do...Loop-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- "conditional statements [Visual Basic], Do�Loop"
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- "loop structures [Visual Basic], Do�Loop statements"
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79d25dce963f383a84b56ce2c9b600fc2d5a7937
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="8db0b-102">Do...Loop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8db0b-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="8db0b-103">Wiederholt einen Block von Anweisungen, die während einer `Boolean` Bedingung `True` oder bis die Bedingung wird `True`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8db0b-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="8db0b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8db0b-105">Parts</span></span>  
  
|<span data-ttu-id="8db0b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="8db0b-106">Term</span></span>|<span data-ttu-id="8db0b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="8db0b-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="8db0b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8db0b-108">Required.</span></span> <span data-ttu-id="8db0b-109">Startet die Definition der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="8db0b-110">Erforderlich, außer wenn `Until` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8db0b-110">Required unless `Until` is used.</span></span> <span data-ttu-id="8db0b-111">Wiederholen Sie die Schleife bis `condition` ist `False`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="8db0b-112">Erforderlich, außer wenn `While` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8db0b-112">Required unless `While` is used.</span></span> <span data-ttu-id="8db0b-113">Wiederholen Sie die Schleife bis `condition` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="8db0b-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8db0b-114">Optional.</span></span> <span data-ttu-id="8db0b-115">`Boolean`Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8db0b-115">`Boolean` expression.</span></span> <span data-ttu-id="8db0b-116">Wenn `condition` ist `Nothing`, Visual Basic behandelt sie als `False`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="8db0b-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8db0b-117">Optional.</span></span> <span data-ttu-id="8db0b-118">Eine oder mehrere Anweisungen, die wiederholt werden, während oder bis `condition` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="8db0b-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8db0b-119">Optional.</span></span> <span data-ttu-id="8db0b-120">Überträgt die Steuerung an die nächste Iteration der der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="8db0b-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8db0b-121">Optional.</span></span> <span data-ttu-id="8db0b-122">Überträgt die Steuerung von der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="8db0b-123">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8db0b-123">Required.</span></span> <span data-ttu-id="8db0b-124">Beendet die Definition des der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8db0b-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8db0b-125">Remarks</span></span>  
 <span data-ttu-id="8db0b-126">Verwenden einer `Do...Loop` Struktur, wenn Sie eine Reihe von Anweisungen eine unbestimmte Anzahl, wie oft, bis eine Bedingung erfüllt ist wiederholen möchten.</span><span class="sxs-lookup"><span data-stu-id="8db0b-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="8db0b-127">Wenn Sie den Anweisungen eine festgelegten Anzahl an, wie oft wiederholen möchten die [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="8db0b-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="8db0b-128">Verwenden Sie entweder `While` oder `Until` an `condition`, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="8db0b-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="8db0b-129">Sie können testen, `condition` nur einmal am Anfang oder Ende der Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="8db0b-130">Wenn Sie testen `condition` am Anfang der Schleife (in der `Do` Anweisung), die Schleife möglicherweise nicht noch einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8db0b-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="8db0b-131">Wenn Sie am Ende der Schleife testen (in der `Loop` Anweisung), die Schleife immer mindestens einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8db0b-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="8db0b-132">Die Bedingung ergibt sich normalerweise durch einen Vergleich von zwei Werten, aber es kann ein beliebiger Ausdruck, der ergibt eine [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`).</span><span class="sxs-lookup"><span data-stu-id="8db0b-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="8db0b-133">Hierzu gehören auch Werte anderer Datentypen, z. B. numerische Typen, die in konvertiert wurden `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="8db0b-134">Sie können schachteln `Do` Schleifen, indem Sie eine Schleife in eine andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="8db0b-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="8db0b-135">Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln.</span><span class="sxs-lookup"><span data-stu-id="8db0b-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="8db0b-136">Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="8db0b-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8db0b-137">Die `Do...Loop` Struktur bietet mehr Flexibilität als die [während... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) da Sie entscheiden, ob die Schleife endet können, wenn `condition` beendet, `True` oder wenn es das erste Mal `True`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="8db0b-138">Außerdem können Sie testen `condition` am Anfang oder Ende der Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="8db0b-139">Exit Do</span><span class="sxs-lookup"><span data-stu-id="8db0b-139">Exit Do</span></span>  
 <span data-ttu-id="8db0b-140">Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung kann bieten eine alternative Möglichkeit zum Beenden einer `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="8db0b-141">`Exit Do`überträgt die Steuerung sofort an die Anweisung mit der `Loop` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8db0b-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="8db0b-142">`Exit Do`wird häufig verwendet werden, nachdem eine Bedingung, z. B. in ausgewertet wird einer `If...Then...Else` Struktur.</span><span class="sxs-lookup"><span data-stu-id="8db0b-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="8db0b-143">Möglicherweise möchten eine Schleife zu beenden, wenn Sie eine Bedingung, in dem unnötige oder überhaupt nicht erkennen zu fortfahren, Iteration, z. B. einen fehlerhaften Wert oder eine Anforderung zum Beenden können.</span><span class="sxs-lookup"><span data-stu-id="8db0b-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="8db0b-144">Eine Verwendungsmöglichkeit von `Exit Do` besteht darin, eine Bedingung zu testen, verursachen einen *Endlosschleife*, also in einer Schleife, die eine große oder sogar unendliche Anzahl von Malen ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8db0b-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="8db0b-145">Sie können `Exit Do` für die Schleife Escapezeichen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8db0b-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="8db0b-146">Sie können eine beliebige Anzahl von einschließen `Exit Do` Anweisungen, die an einer beliebigen Stelle in einem `Do…Loop`.</span><span class="sxs-lookup"><span data-stu-id="8db0b-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="8db0b-147">Bei Verwendung in geschachtelten `Do` Schleifen, `Exit Do` überträgt die Steuerung aus der innersten Schleife und in der nächsthöheren Ebene der Schachtelung.</span><span class="sxs-lookup"><span data-stu-id="8db0b-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8db0b-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8db0b-148">Example</span></span>  
 <span data-ttu-id="8db0b-149">Im folgenden Beispiel die Anweisungen in der Schleife weiterhin ausgeführt werden, bis die `index` Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="8db0b-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="8db0b-150">Die `Until` -Klausel ist am Ende der Schleife.</span><span class="sxs-lookup"><span data-stu-id="8db0b-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="8db0b-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8db0b-151">Example</span></span>  
 <span data-ttu-id="8db0b-152">Im folgenden Beispiel wird eine `While` -Klausel anstelle von einer `Until` -Klausel und `condition` am Anfang der Schleife statt am Ende getestet wird.</span><span class="sxs-lookup"><span data-stu-id="8db0b-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="8db0b-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8db0b-153">Example</span></span>  
 <span data-ttu-id="8db0b-154">Im folgenden Beispiel `condition` die Schleife beendet bei der `index` Variable größer als 100 ist.</span><span class="sxs-lookup"><span data-stu-id="8db0b-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="8db0b-155">Die `If` -Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="8db0b-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="8db0b-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8db0b-156">Example</span></span>  
 <span data-ttu-id="8db0b-157">Das folgende Beispiel liest alle Zeilen in einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="8db0b-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="8db0b-158">Die <xref:System.IO.File.OpenText%2A> -Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> , liest die Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8db0b-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="8db0b-159">In der `Do...Loop` Bedingung, die <xref:System.IO.StreamReader.Peek%2A> Methode von der `StreamReader` bestimmt, ob alle zusätzlichen Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8db0b-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8db0b-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8db0b-160">See Also</span></span>  
 [<span data-ttu-id="8db0b-161">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="8db0b-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="8db0b-162">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8db0b-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="8db0b-163">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8db0b-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="8db0b-164">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="8db0b-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="8db0b-165">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8db0b-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="8db0b-166">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8db0b-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
