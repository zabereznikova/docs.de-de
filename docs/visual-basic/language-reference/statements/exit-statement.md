---
title: Exit-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df63ecbf0605d07296e1692f18b1b015e27cd03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="2417f-102">Exit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2417f-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="2417f-103">Eine Prozedur oder den Block beendet, und überträgt die Steuerung sofort an die Anweisung nach dem Prozeduraufruf oder der Blockdefinition.</span><span class="sxs-lookup"><span data-stu-id="2417f-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2417f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2417f-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="2417f-105">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="2417f-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="2417f-106">Beendet sofort die `Do` wurde eine Schleife in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="2417f-107">Die Ausführung wird fortgeführt, mit der Anweisung nach der `Loop` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="2417f-108">`Exit Do`kann verwendet werden, nur innerhalb einer `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="2417f-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="2417f-109">Bei Verwendung in geschachtelten `Do` Schleifen `Exit Do` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene der Schachtelung.</span><span class="sxs-lookup"><span data-stu-id="2417f-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="2417f-110">Beendet sofort die `For` wurde eine Schleife in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="2417f-111">Die Ausführung wird fortgeführt, mit der Anweisung nach der `Next` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="2417f-112">`Exit For`kann verwendet werden, nur innerhalb einer `For`... `Next` oder `For Each`... `Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="2417f-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="2417f-113">Bei Verwendung in geschachtelten `For` Schleifen `Exit For` verlässt die innerste Schleife und überträgt die Steuerung an der nächsthöheren Ebene der Schachtelung.</span><span class="sxs-lookup"><span data-stu-id="2417f-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="2417f-114">Beendet sofort die `Function` Prozedur, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="2417f-115">Die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die aufgerufen der `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2417f-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="2417f-116">`Exit Function`kann verwendet werden, nur innerhalb einer `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2417f-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="2417f-117">Um einen Rückgabewert anzugeben, können Sie den Wert dem Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="2417f-118">Um weisen den Rückgabewert, und die Funktion in einer Anweisung zu beenden, können Sie stattdessen die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2417f-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="2417f-119">Beendet sofort die `Property` Prozedur, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="2417f-120">Die Ausführung wird fortgeführt, mit der Anweisung, die aufgerufen der `Property` Prozedur, d. h. mit der Anweisung angefordert oder den Wert der Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2417f-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="2417f-121">`Exit Property`kann verwendet werden, nur in einer Eigenschaft `Get` oder `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2417f-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="2417f-122">An einen Rückgabewert in einer `Get` Verfahren können Sie den Wert dem Funktionsnamen in einer Zeile vor dem Zuweisen der `Exit Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="2417f-123">Zuweisen von den Rückgabewert und Beenden der `Get` Prozedur in einer Anweisung, stattdessen können Sie die `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="2417f-124">In einem `Set` Prozedur, die `Exit Property` Anweisung entspricht der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="2417f-125">Beendet sofort die `Select Case` -block in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="2417f-126">Die Ausführung wird fortgeführt, mit der Anweisung nach der `End Select` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="2417f-127">`Exit Select`kann verwendet werden, nur innerhalb einer `Select Case` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="2417f-128">Beendet sofort die `Sub` Prozedur, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="2417f-129">Die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die aufgerufen der `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2417f-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="2417f-130">`Exit Sub`kann verwendet werden, nur innerhalb einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2417f-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="2417f-131">In einem `Sub` Prozedur, die `Exit Sub` Anweisung entspricht der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="2417f-132">Beendet sofort die `Try` oder `Catch` -block in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="2417f-133">Die Ausführung wird fortgeführt, mit der `Finally` blockieren, sofern vorhanden, oder mit der Anweisung nach der `End Try` Anweisung andernfalls.</span><span class="sxs-lookup"><span data-stu-id="2417f-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="2417f-134">`Exit Try`kann verwendet werden, nur innerhalb einer `Try` oder `Catch` Block, und nicht in eine `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="2417f-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="2417f-135">Beendet sofort die `While` wurde eine Schleife in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2417f-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="2417f-136">Die Ausführung wird fortgeführt, mit der Anweisung nach der `End While` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2417f-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="2417f-137">`Exit While`kann verwendet werden, nur innerhalb einer `While` Schleife.</span><span class="sxs-lookup"><span data-stu-id="2417f-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="2417f-138">Bei Verwendung in geschachtelten `While` Schleifen, `Exit While` überträgt die Steuerung an die Schleife, die eine geschachtelte Ebene über die Schleife ist, in dem `Exit While` auftritt.</span><span class="sxs-lookup"><span data-stu-id="2417f-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2417f-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2417f-139">Remarks</span></span>  
 <span data-ttu-id="2417f-140">Verwechseln Sie nicht `Exit` -Anweisungen mit `End` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="2417f-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="2417f-141">`Exit`das Ende einer Anweisung werden keine definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2417f-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2417f-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2417f-142">Example</span></span>  
 <span data-ttu-id="2417f-143">Im folgenden Beispiel wird die schleifenbedingung die Schleife beendet bei der `index` Variable größer als 100 ist.</span><span class="sxs-lookup"><span data-stu-id="2417f-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="2417f-144">Die `If` -Anweisung in der Schleife, bewirkt jedoch, dass die `Exit Do` Anweisung zum Beenden der Schleife, wenn die Indexvariable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="2417f-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="2417f-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2417f-145">Example</span></span>  
 <span data-ttu-id="2417f-146">Im folgende Beispiel weist den Rückgabewert den Namen der Funktion `myFunction`, und verwendet dann `Exit Function` , von der Funktion zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="2417f-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="2417f-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2417f-147">Example</span></span>  
 <span data-ttu-id="2417f-148">Im folgenden Beispiel wird die [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) weisen den Rückgabewert und die Funktion beenden.</span><span class="sxs-lookup"><span data-stu-id="2417f-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2417f-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2417f-149">See Also</span></span>  
 [<span data-ttu-id="2417f-150">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [<span data-ttu-id="2417f-151">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="2417f-152">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="2417f-153">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="2417f-154">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="2417f-155">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="2417f-156">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="2417f-157">Stop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="2417f-158">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="2417f-159">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2417f-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
