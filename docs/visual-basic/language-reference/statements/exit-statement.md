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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956937"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="e73ed-102">Exit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e73ed-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="e73ed-103">Beendet eine Prozedur oder einen Block und überträgt die Steuerung sofort an die Anweisung nach dem Prozedur-oder der Block Definition.</span><span class="sxs-lookup"><span data-stu-id="e73ed-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="e73ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e73ed-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="e73ed-105">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="e73ed-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="e73ed-106">Beendet sofort die `Do`-Schleife, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="e73ed-107">Die Ausführung wird mit der Anweisung nach der `Loop`-Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="e73ed-108">`Exit Do` kann nur innerhalb einer `Do`-Schleife verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="e73ed-109">Bei der Verwendung in geschachtelten `Do`-Schleifen beendet `Exit Do` die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="e73ed-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="e73ed-110">Beendet sofort die `For`-Schleife, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="e73ed-111">Die Ausführung wird mit der Anweisung nach der `Next`-Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="e73ed-112">`Exit For` kann nur innerhalb einer `For`... `Next`-oder `For Each`... `Next`-Schleife verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="e73ed-113">Bei der Verwendung in geschachtelten `For`-Schleifen beendet `Exit For` die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="e73ed-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="e73ed-114">Beendet sofort die Prozedur "`Function`", in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="e73ed-115">Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die Prozedur "`Function`" aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="e73ed-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="e73ed-116">`Exit Function` kann nur innerhalb einer `Function`-Prozedur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="e73ed-117">Zum Angeben eines Rückgabewerts können Sie den Wert dem Funktionsnamen in einer Zeile vor der `Exit Function`-Anweisung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e73ed-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="e73ed-118">Wenn Sie den Rückgabewert zuweisen und die Funktion in einer Anweisung beenden möchten, können Sie stattdessen die [Return-Anweisung](return-statement.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="e73ed-119">Beendet sofort die Prozedur "`Property`", in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="e73ed-120">Die Ausführung wird mit der Anweisung fortgesetzt, die die Prozedur `Property` aufgerufen hat, d. h. mit der Anweisung, die den Wert der Eigenschaft anfordert oder festlegt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="e73ed-121">`Exit Property` kann nur innerhalb der `Get`-oder `Set`-Prozedur einer Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="e73ed-122">Um einen Rückgabewert in einer `Get`-Prozedur anzugeben, können Sie den Wert dem Funktionsnamen in einer Zeile vor der `Exit Property`-Anweisung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e73ed-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="e73ed-123">Um den Rückgabewert zuzuweisen und die `Get`-Prozedur in einer Anweisung zu beenden, können Sie stattdessen die `Return`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="e73ed-124">In einer `Set`-Prozedur entspricht die `Exit Property`-Anweisung der Anweisung `Return`.</span><span class="sxs-lookup"><span data-stu-id="e73ed-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="e73ed-125">Beendet sofort den Block "`Select Case`", in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="e73ed-126">Die Ausführung wird mit der Anweisung nach der `End Select`-Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="e73ed-127">`Exit Select` kann nur innerhalb einer `Select Case`-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="e73ed-128">Beendet sofort die Prozedur "`Sub`", in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="e73ed-129">Die Ausführung wird mit der Anweisung nach der Anweisung fortgesetzt, die die Prozedur "`Sub`" aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="e73ed-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="e73ed-130">`Exit Sub` kann nur innerhalb einer `Sub`-Prozedur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="e73ed-131">In einer `Sub`-Prozedur entspricht die `Exit Sub`-Anweisung der Anweisung `Return`.</span><span class="sxs-lookup"><span data-stu-id="e73ed-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="e73ed-132">Beendet sofort den Block "`Try`" oder "`Catch`", in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="e73ed-133">Die Ausführung wird mit dem Block "`Finally`" fortgesetzt, sofern vorhanden, oder mit der Anweisung, die der `End Try`-Anweisung folgt, andernfalls.</span><span class="sxs-lookup"><span data-stu-id="e73ed-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="e73ed-134">`Exit Try` kann nur innerhalb eines `Try`-oder `Catch`-Blocks und nicht innerhalb eines `Finally`-Blocks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="e73ed-135">Beendet sofort die `While`-Schleife, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e73ed-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="e73ed-136">Die Ausführung wird mit der Anweisung nach der `End While`-Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="e73ed-137">`Exit While` kann nur innerhalb einer `While`-Schleife verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e73ed-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="e73ed-138">Bei der Verwendung in geschachtelten `While`-Schleifen überträgt `Exit While` die Steuerung an die Schleife, die eine geschachtelte Ebene oberhalb der Schleife ist, in der `Exit While` auftritt.</span><span class="sxs-lookup"><span data-stu-id="e73ed-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="e73ed-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e73ed-139">Remarks</span></span>

<span data-ttu-id="e73ed-140">Verwechseln Sie `Exit`-Anweisungen nicht mit `End`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e73ed-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="e73ed-141">`Exit` definiert nicht das Ende einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e73ed-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="e73ed-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e73ed-142">Example</span></span>

<span data-ttu-id="e73ed-143">Im folgenden Beispiel stoppt die Schleifen Bedingung die Schleife, wenn die `index`-Variable größer als 100 ist.</span><span class="sxs-lookup"><span data-stu-id="e73ed-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="e73ed-144">Die Anweisung "`If`" in der Schleife bewirkt jedoch, dass die `Exit Do`-Anweisung die Schleife beendet, wenn die Index Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="e73ed-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="e73ed-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e73ed-145">Example</span></span>

<span data-ttu-id="e73ed-146">Im folgenden Beispiel wird der Rückgabewert dem Funktionsnamen `myFunction` zugewiesen, und anschließend wird `Exit Function` verwendet, um von der-Funktion zurückzugeben:</span><span class="sxs-lookup"><span data-stu-id="e73ed-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="e73ed-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e73ed-147">Example</span></span>

<span data-ttu-id="e73ed-148">Im folgenden Beispiel wird die [Return-Anweisung](return-statement.md) verwendet, um den Rückgabewert zuzuweisen und die-Funktion zu beenden:</span><span class="sxs-lookup"><span data-stu-id="e73ed-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="e73ed-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e73ed-149">See also</span></span>

- [<span data-ttu-id="e73ed-150">Continue-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="e73ed-151">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="e73ed-152">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="e73ed-153">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="e73ed-154">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="e73ed-155">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="e73ed-156">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="e73ed-157">Stop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="e73ed-158">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="e73ed-159">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e73ed-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
