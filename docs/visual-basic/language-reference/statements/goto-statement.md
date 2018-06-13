---
title: GoTo-Anweisung
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
ms.openlocfilehash: 27ebc677bab8b7f61a02408fddb30a6ec21c43cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604743"
---
# <a name="goto-statement"></a><span data-ttu-id="ddbca-102">GoTo-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-102">GoTo Statement</span></span>
<span data-ttu-id="ddbca-103">Verzweigungen bedingungslos an eine angegebene Zeile in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ddbca-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddbca-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="ddbca-105">Segment</span><span class="sxs-lookup"><span data-stu-id="ddbca-105">Part</span></span>  
 `line`  
 <span data-ttu-id="ddbca-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ddbca-106">Required.</span></span> <span data-ttu-id="ddbca-107">Alle zeilenbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="ddbca-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddbca-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddbca-108">Remarks</span></span>  
 <span data-ttu-id="ddbca-109">Die `GoTo` -Anweisung verzweigen kann, nur für Zeilen in der Prozedur, in dem er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ddbca-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="ddbca-110">Die Zeile benötigen eine Linie, die Bezeichnung `GoTo` finden können.</span><span class="sxs-lookup"><span data-stu-id="ddbca-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="ddbca-111">Weitere Informationen finden Sie unter [wie: Label-Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="ddbca-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddbca-112">`GoTo` Anweisungen können, dass Code schwierig zu lesen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ddbca-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="ddbca-113">Wann immer möglich, verwenden Sie stattdessen eine Steuerelement-Struktur.</span><span class="sxs-lookup"><span data-stu-id="ddbca-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="ddbca-114">Weitere Informationen finden Sie unter [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddbca-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="ddbca-115">Sie können keine `GoTo` Anweisung außerhalb von einer `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, oder `Using`... `End Using` Konstruktion zu einer Bezeichnung in.</span><span class="sxs-lookup"><span data-stu-id="ddbca-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="ddbca-116">Verzweigung und Try-Konstrukten</span><span class="sxs-lookup"><span data-stu-id="ddbca-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="ddbca-117">Innerhalb einer `Try`... `Catch`... `Finally` Konstruktion, die folgenden Regeln gelten, für die Verzweigung mit der `GoTo` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ddbca-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="ddbca-118">Blockieren oder region</span><span class="sxs-lookup"><span data-stu-id="ddbca-118">Block or region</span></span>|<span data-ttu-id="ddbca-119">Verzweigung von außerhalb</span><span class="sxs-lookup"><span data-stu-id="ddbca-119">Branching in from outside</span></span>|<span data-ttu-id="ddbca-120">Verzweigen Sie von innerhalb</span><span class="sxs-lookup"><span data-stu-id="ddbca-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="ddbca-121">`Try` Blockieren</span><span class="sxs-lookup"><span data-stu-id="ddbca-121">`Try` block</span></span>|<span data-ttu-id="ddbca-122">Nur von einem `Catch` Block mit der gleichen Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ddbca-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="ddbca-123">Nur für außerhalb der gesamten Konstruktion</span><span class="sxs-lookup"><span data-stu-id="ddbca-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="ddbca-124">`Catch` Blockieren</span><span class="sxs-lookup"><span data-stu-id="ddbca-124">`Catch` block</span></span>|<span data-ttu-id="ddbca-125">Nie zulässig.</span><span class="sxs-lookup"><span data-stu-id="ddbca-125">Never allowed</span></span>|<span data-ttu-id="ddbca-126">Nur für außerhalb der gesamten Konstruktion oder auf die `Try` Block mit der gleichen Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ddbca-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="ddbca-127">`Finally` Blockieren</span><span class="sxs-lookup"><span data-stu-id="ddbca-127">`Finally` block</span></span>|<span data-ttu-id="ddbca-128">Nie zulässig.</span><span class="sxs-lookup"><span data-stu-id="ddbca-128">Never allowed</span></span>|<span data-ttu-id="ddbca-129">Nie zulässig.</span><span class="sxs-lookup"><span data-stu-id="ddbca-129">Never allowed</span></span>|  
  
 <span data-ttu-id="ddbca-130"><sup>1</sup> sofern `Try`... `Catch`... `Finally` Konstruktion in einer anderen geschachtelt ist ein `Catch` Block kann keine Verzweigung in die `Try` Block auf einem eigenen Schachtelungsebene, jedoch nicht in einen anderen `Try` Block.</span><span class="sxs-lookup"><span data-stu-id="ddbca-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="ddbca-131">Eine geschachtelte `Try`... `Catch`... `Finally` -Konstruktion muss vollständig in enthalten eine `Try` oder `Catch` Block der Konstruktion, in dem sie geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="ddbca-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="ddbca-132">Die folgende Abbildung zeigt eine `Try` Konstruktion in einer anderen geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="ddbca-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="ddbca-133">Verschiedene Verzweigungen zwischen den Blöcken des zwei Konstruktionen werden als gültig oder ungültig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ddbca-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="ddbca-134">![Grafisches Diagramm der Verzweigung in Try-Konstrukten](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="ddbca-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="ddbca-135">Gültigen und ungültigen Verzweigungen in Try-Konstrukten</span><span class="sxs-lookup"><span data-stu-id="ddbca-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddbca-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ddbca-136">Example</span></span>  
 <span data-ttu-id="ddbca-137">Im folgenden Beispiel wird die `GoTo` Anweisung zum Verzweigen zeilenbezeichnungen in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="ddbca-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ddbca-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddbca-138">See Also</span></span>  
 [<span data-ttu-id="ddbca-139">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="ddbca-140">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="ddbca-141">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="ddbca-142">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="ddbca-143">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="ddbca-144">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="ddbca-145">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="ddbca-146">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ddbca-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
