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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581815"
---
# <a name="goto-statement"></a><span data-ttu-id="aec33-102">GoTo-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-102">GoTo Statement</span></span>
<span data-ttu-id="aec33-103">Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="aec33-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aec33-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="aec33-105">Segment</span><span class="sxs-lookup"><span data-stu-id="aec33-105">Part</span></span>  
 `line`  
 <span data-ttu-id="aec33-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aec33-106">Required.</span></span> <span data-ttu-id="aec33-107">Eine beliebige Zeilen Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="aec33-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec33-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aec33-108">Remarks</span></span>  
 <span data-ttu-id="aec33-109">Die `GoTo`-Anweisung kann nur bis Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aec33-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="aec33-110">Die Linie muss über eine Zeilen Bezeichnung verfügen, auf die `GoTo` verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="aec33-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="aec33-111">Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="aec33-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aec33-112">mit `GoTo`-Anweisungen kann der Code schwierig zu lesen und zu warten.</span><span class="sxs-lookup"><span data-stu-id="aec33-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="aec33-113">Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur.</span><span class="sxs-lookup"><span data-stu-id="aec33-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="aec33-114">Weitere Informationen finden Sie unter [Ablauf Steuerung](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="aec33-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="aec33-115">Eine `GoTo`-Anweisung kann nicht verwendet werden, um außerhalb eines `For` zu verzweigen... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, 0... 1 oder 2... 3 Konstruktion in eine Bezeichnung in.</span><span class="sxs-lookup"><span data-stu-id="aec33-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="aec33-116">Verzweigungen und Versuchs Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="aec33-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="aec33-117">Innerhalb einer `Try`... `Catch`... `Finally` Konstruktion gelten die folgenden Regeln für die Verzweigung mit der `GoTo`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="aec33-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="aec33-118">Block oder Region</span><span class="sxs-lookup"><span data-stu-id="aec33-118">Block or region</span></span>|<span data-ttu-id="aec33-119">Verzweigungen von außerhalb</span><span class="sxs-lookup"><span data-stu-id="aec33-119">Branching in from outside</span></span>|<span data-ttu-id="aec33-120">Verzweigungen aus innerhalb</span><span class="sxs-lookup"><span data-stu-id="aec33-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="aec33-121">`Try`-Block</span><span class="sxs-lookup"><span data-stu-id="aec33-121">`Try` block</span></span>|<span data-ttu-id="aec33-122">Nur aus einem `Catch` Block desselben Baus <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="aec33-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="aec33-123">Nur für die gesamte Konstruktion</span><span class="sxs-lookup"><span data-stu-id="aec33-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="aec33-124">`Catch`-Block</span><span class="sxs-lookup"><span data-stu-id="aec33-124">`Catch` block</span></span>|<span data-ttu-id="aec33-125">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="aec33-125">Never allowed</span></span>|<span data-ttu-id="aec33-126">Nur für die gesamte Konstruktion oder den `Try` Block desselben Aufbaus <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="aec33-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="aec33-127">`Finally`-Block</span><span class="sxs-lookup"><span data-stu-id="aec33-127">`Finally` block</span></span>|<span data-ttu-id="aec33-128">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="aec33-128">Never allowed</span></span>|<span data-ttu-id="aec33-129">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="aec33-129">Never allowed</span></span>|  
  
 <span data-ttu-id="aec33-130"><sup>1</sup> , wenn ein `Try`... `Catch`... `Finally` Konstruktion in einer anderen geschachtelt ist, kann ein `Catch` Block in den `Try` Block auf der eigenen Schachtelungs Ebene, aber nicht in einen anderen `Try` Block verzweigen.</span><span class="sxs-lookup"><span data-stu-id="aec33-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="aec33-131">Ein-`Try`... `Catch`... `Finally` Konstruktion muss vollständig in einem `Try` oder `Catch` Block der Konstruktion enthalten sein, in der Sie geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="aec33-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="aec33-132">Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="aec33-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="aec33-133">Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.</span><span class="sxs-lookup"><span data-stu-id="aec33-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Grafisches Diagramm der Verzweigung in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="aec33-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aec33-135">Example</span></span>  
 <span data-ttu-id="aec33-136">Im folgenden Beispiel wird die `GoTo`-Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.</span><span class="sxs-lookup"><span data-stu-id="aec33-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="aec33-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aec33-137">See also</span></span>

- [<span data-ttu-id="aec33-138">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="aec33-139">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="aec33-140">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="aec33-141">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="aec33-142">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="aec33-143">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="aec33-144">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="aec33-145">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aec33-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
