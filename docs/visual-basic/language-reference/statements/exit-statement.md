---
title: Exit-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832631"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="a04a1-102">Exit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a04a1-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="a04a1-103">Beendet eine Prozedur oder der Block und überträgt die Steuerung sofort an die Anweisung nach dem Prozeduraufruf oder der Blockdefinition.</span><span class="sxs-lookup"><span data-stu-id="a04a1-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a04a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a04a1-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="a04a1-105">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a04a1-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="a04a1-106">Beendet sofort die `Do` wurde eine Schleife in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="a04a1-107">Ausführung wird fortgeführt, mit der Anweisung nach der `Loop` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="a04a1-108">`Exit Do` kann verwendet werden, nur innerhalb einer `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="a04a1-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="a04a1-109">Bei der Verwendung in geschachtelten `Do` Schleifen `Exit Do` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene Schachtelungsebenen.</span><span class="sxs-lookup"><span data-stu-id="a04a1-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="a04a1-110">Beendet sofort die `For` wurde eine Schleife in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="a04a1-111">Ausführung wird fortgeführt, mit der Anweisung nach der `Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="a04a1-112">`Exit For` kann verwendet werden, nur innerhalb einer `For`... `Next` oder `For Each`... `Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="a04a1-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="a04a1-113">Bei der Verwendung in geschachtelten `For` Schleifen `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene Schachtelungsebenen.</span><span class="sxs-lookup"><span data-stu-id="a04a1-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="a04a1-114">Sofort beendet die `Function` Prozedur, die in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="a04a1-115">Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die Namen der `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a04a1-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="a04a1-116">`Exit Function` kann verwendet werden, nur innerhalb einer `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a04a1-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="a04a1-117">Um einen Rückgabewert anzugeben, können Sie den Wert zuweisen, auf den Funktionsnamen in einer Zeile vor der `Exit Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="a04a1-118">Weisen Sie den Rückgabewert und die Funktion in einer Anweisung beenden, können Sie stattdessen die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a04a1-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="a04a1-119">Sofort beendet die `Property` Prozedur, die in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="a04a1-120">Ausführung wird fortgeführt, mit der Anweisung, die Namen der `Property` Prozedur, d. h. mit der Anweisung angefordert oder den Wert der Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a04a1-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="a04a1-121">`Exit Property` kann verwendet werden, nur innerhalb einer Eigenschaft `Get` oder `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a04a1-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="a04a1-122">An einen Rückgabewert in einer `Get` Verfahren können Sie den Wert auf den Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="a04a1-123">Zuweisen von den Rückgabewert und Beenden der `Get` Prozedur in einer Anweisung können Sie stattdessen verwenden die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="a04a1-124">In einem `Set` Verfahren der `Exit Property` Anweisung entspricht der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="a04a1-125">Beendet sofort die `Select Case` -block in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="a04a1-126">Ausführung wird fortgeführt, mit der Anweisung nach der `End Select` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="a04a1-127">`Exit Select` kann verwendet werden, nur innerhalb einer `Select Case` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="a04a1-128">Sofort beendet die `Sub` Prozedur, die in der sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="a04a1-129">Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die Namen der `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a04a1-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="a04a1-130">`Exit Sub` kann verwendet werden, nur innerhalb einer `Sub` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="a04a1-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="a04a1-131">In einem `Sub` Verfahren der `Exit Sub` Anweisung entspricht der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="a04a1-132">Beendet sofort die `Try` oder `Catch` -block in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="a04a1-133">Ausführung wird fortgeführt, mit der `Finally` blockieren, sofern vorhanden, oder mit der Anweisung nach der `End Try` Anweisung andernfalls.</span><span class="sxs-lookup"><span data-stu-id="a04a1-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="a04a1-134">`Exit Try` kann verwendet werden, nur innerhalb einer `Try` oder `Catch` Block und nicht in eine `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="a04a1-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="a04a1-135">Beendet sofort die `While` wurde eine Schleife in der es angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a04a1-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="a04a1-136">Ausführung wird fortgeführt, mit der Anweisung nach der `End While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a04a1-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="a04a1-137">`Exit While` kann verwendet werden, nur innerhalb einer `While` Schleife.</span><span class="sxs-lookup"><span data-stu-id="a04a1-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="a04a1-138">Bei der Verwendung in geschachtelten `While` Schleifen, `Exit While` überträgt die Steuerung an die Schleife, die eine geschachtelte Ebene über der Schleife befindet, in denen `Exit While` auftritt.</span><span class="sxs-lookup"><span data-stu-id="a04a1-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a04a1-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a04a1-139">Remarks</span></span>  
 <span data-ttu-id="a04a1-140">Verwechseln Sie nicht `Exit` -Anweisungen mit `End` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a04a1-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="a04a1-141">`Exit` das Ende einer Anweisung werden keine definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a04a1-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a04a1-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a04a1-142">Example</span></span>  
 <span data-ttu-id="a04a1-143">Im folgenden Beispiel wird die schleifenbedingung die Schleife beendet, mit denen bei der `index` Variable ist größer als 100.</span><span class="sxs-lookup"><span data-stu-id="a04a1-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="a04a1-144">Die `If` Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="a04a1-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="a04a1-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a04a1-145">Example</span></span>  
 <span data-ttu-id="a04a1-146">Im folgende Beispiel weist den zurückgegeben Wert den Namen der Funktion `myFunction`, und verwendet dann `Exit Function` von der Funktion zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a04a1-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="a04a1-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a04a1-147">Example</span></span>  
 <span data-ttu-id="a04a1-148">Im folgenden Beispiel wird die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) weisen den Rückgabewert und die Funktion beenden.</span><span class="sxs-lookup"><span data-stu-id="a04a1-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="a04a1-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a04a1-149">See also</span></span>

- [<span data-ttu-id="a04a1-150">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="a04a1-151">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="a04a1-152">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="a04a1-153">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="a04a1-154">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="a04a1-155">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a04a1-156">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="a04a1-157">Stop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="a04a1-158">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a04a1-159">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a04a1-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
