---
title: GOTO-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912446"
---
# <a name="goto-statement"></a><span data-ttu-id="e644e-102">GoTo-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-102">GoTo Statement</span></span>
<span data-ttu-id="e644e-103">Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e644e-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e644e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e644e-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="e644e-105">Segment</span><span class="sxs-lookup"><span data-stu-id="e644e-105">Part</span></span>  
 `line`  
 <span data-ttu-id="e644e-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e644e-106">Required.</span></span> <span data-ttu-id="e644e-107">Eine beliebige Zeilen Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="e644e-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e644e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e644e-108">Remarks</span></span>  
 <span data-ttu-id="e644e-109">Die `GoTo` -Anweisung kann nur an Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e644e-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="e644e-110">Die Linie muss über eine Zeilen Bezeichnung verfügen `GoTo` , auf die verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e644e-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="e644e-111">Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnungs](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e644e-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e644e-112">`GoTo`-Anweisungen können das Lesen und Verwalten des Codes erschweren.</span><span class="sxs-lookup"><span data-stu-id="e644e-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="e644e-113">Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur.</span><span class="sxs-lookup"><span data-stu-id="e644e-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="e644e-114">Weitere Informationen finden Sie unter [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="e644e-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="e644e-115">Sie können keine- `GoTo` Anweisung verwenden, um eine Verzweigung außerhalb eines `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, oder`Using`... `End Using` Konstruktion in eine Bezeichnung in.</span><span class="sxs-lookup"><span data-stu-id="e644e-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="e644e-116">Verzweigungen und Versuchs Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="e644e-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="e644e-117">In einer `Try`... `Catch`... die folgenden Regeln gelten für die Verzweigung mit der `GoTo` -Anweisung. `Finally`</span><span class="sxs-lookup"><span data-stu-id="e644e-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="e644e-118">Block oder Region</span><span class="sxs-lookup"><span data-stu-id="e644e-118">Block or region</span></span>|<span data-ttu-id="e644e-119">Verzweigungen von außerhalb</span><span class="sxs-lookup"><span data-stu-id="e644e-119">Branching in from outside</span></span>|<span data-ttu-id="e644e-120">Verzweigungen aus innerhalb</span><span class="sxs-lookup"><span data-stu-id="e644e-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="e644e-121">`Try`Baustein</span><span class="sxs-lookup"><span data-stu-id="e644e-121">`Try` block</span></span>|<span data-ttu-id="e644e-122">Nur aus einem `Catch` Block desselben Baus <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e644e-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="e644e-123">Nur für die gesamte Konstruktion</span><span class="sxs-lookup"><span data-stu-id="e644e-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="e644e-124">`Catch`Baustein</span><span class="sxs-lookup"><span data-stu-id="e644e-124">`Catch` block</span></span>|<span data-ttu-id="e644e-125">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="e644e-125">Never allowed</span></span>|<span data-ttu-id="e644e-126">Nur für die gesamte Konstruktion oder den `Try` Block der gleichen Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e644e-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="e644e-127">`Finally`Baustein</span><span class="sxs-lookup"><span data-stu-id="e644e-127">`Finally` block</span></span>|<span data-ttu-id="e644e-128">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="e644e-128">Never allowed</span></span>|<span data-ttu-id="e644e-129">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="e644e-129">Never allowed</span></span>|  
  
 <span data-ttu-id="e644e-130"><sup>1..</sup> `Try`. `Catch`... die Konstruktion ist in einer anderen geschachtelt, ein `Catch` Block kann `Try` in den Block auf der eigenen Schachtelungs Ebene, aber `Try` nicht in einen anderen Block verzweigen. `Finally`</span><span class="sxs-lookup"><span data-stu-id="e644e-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="e644e-131">`Try`Ein... `Catch`... die Konstruktion muss vollständig in einem `Try` - `Catch` oder-Block der Konstruktion enthalten sein, in der Sie geschachtelt ist. `Finally`</span><span class="sxs-lookup"><span data-stu-id="e644e-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="e644e-132">Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="e644e-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="e644e-133">Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.</span><span class="sxs-lookup"><span data-stu-id="e644e-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="e644e-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e644e-135">Example</span></span>  
 <span data-ttu-id="e644e-136">Im folgenden Beispiel wird die `GoTo` -Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.</span><span class="sxs-lookup"><span data-stu-id="e644e-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="e644e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e644e-137">See also</span></span>

- [<span data-ttu-id="e644e-138">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="e644e-139">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="e644e-140">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="e644e-141">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="e644e-142">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="e644e-143">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="e644e-144">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="e644e-145">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e644e-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
