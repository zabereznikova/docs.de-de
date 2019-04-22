---
title: GoTo-Anweisung (Visual Basic)
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
ms.openlocfilehash: c4dd249620ba1bf445642ce4600498f6beb30461
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827769"
---
# <a name="goto-statement"></a><span data-ttu-id="75cc1-102">GoTo-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-102">GoTo Statement</span></span>
<span data-ttu-id="75cc1-103">Brancht ohne Bedingungen in eine angegebene Zeile in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="75cc1-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75cc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75cc1-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="75cc1-105">Segment</span><span class="sxs-lookup"><span data-stu-id="75cc1-105">Part</span></span>  
 `line`  
 <span data-ttu-id="75cc1-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75cc1-106">Required.</span></span> <span data-ttu-id="75cc1-107">Alle zeilenbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="75cc1-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75cc1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75cc1-108">Remarks</span></span>  
 <span data-ttu-id="75cc1-109">Die `GoTo` -Anweisung kann nur für Zeilen in der Prozedur, die in der es auftritt verzweigen.</span><span class="sxs-lookup"><span data-stu-id="75cc1-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="75cc1-110">Die Zeile benötigen eine Zeile, die Bezeichnung `GoTo` können zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="75cc1-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="75cc1-111">Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="75cc1-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75cc1-112">`GoTo` -Anweisungen können, dass Code schwierig zu lesen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="75cc1-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="75cc1-113">Wann immer möglich, verwenden Sie stattdessen eine Steuerelement-Struktur.</span><span class="sxs-lookup"><span data-stu-id="75cc1-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="75cc1-114">Weitere Informationen finden Sie unter [Ablaufsteuerung](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="75cc1-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="75cc1-115">Sie können keine `GoTo` Anweisung außerhalb von einer `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, oder `Using`... `End Using` Erstellung zu einer Bezeichnung in.</span><span class="sxs-lookup"><span data-stu-id="75cc1-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="75cc1-116">Verzweigen und versuchen Sie es Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="75cc1-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="75cc1-117">Innerhalb einer `Try`... `Catch`... `Finally` Konstruktion die folgenden Regeln gelten zur Verzweigung mit dem `GoTo` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75cc1-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="75cc1-118">Block oder eine region</span><span class="sxs-lookup"><span data-stu-id="75cc1-118">Block or region</span></span>|<span data-ttu-id="75cc1-119">Verzweigung von außerhalb</span><span class="sxs-lookup"><span data-stu-id="75cc1-119">Branching in from outside</span></span>|<span data-ttu-id="75cc1-120">Verzweigen Sie von innerhalb</span><span class="sxs-lookup"><span data-stu-id="75cc1-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="75cc1-121">`Try` Block</span><span class="sxs-lookup"><span data-stu-id="75cc1-121">`Try` block</span></span>|<span data-ttu-id="75cc1-122">Nur von einem `Catch` Block, der die gleiche Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="75cc1-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="75cc1-123">Nur für außerhalb der gesamten Konstruktion</span><span class="sxs-lookup"><span data-stu-id="75cc1-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="75cc1-124">`Catch` Block</span><span class="sxs-lookup"><span data-stu-id="75cc1-124">`Catch` block</span></span>|<span data-ttu-id="75cc1-125">Nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="75cc1-125">Never allowed</span></span>|<span data-ttu-id="75cc1-126">Nur für außerhalb der gesamten Konstruktion oder auf die `Try` Block, der die gleiche Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="75cc1-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="75cc1-127">`Finally` Block</span><span class="sxs-lookup"><span data-stu-id="75cc1-127">`Finally` block</span></span>|<span data-ttu-id="75cc1-128">Nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="75cc1-128">Never allowed</span></span>|<span data-ttu-id="75cc1-129">Nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="75cc1-129">Never allowed</span></span>|  
  
 <span data-ttu-id="75cc1-130"><sup>1</sup> sofern `Try`... `Catch`... `Finally` -Konstruktion innerhalb einer anderen geschachtelt ist eine `Catch` -Block verzweigen kann, in der `Try` Block, eine eigene Schachtelungsebene, aber nicht in einen anderen `Try` Block.</span><span class="sxs-lookup"><span data-stu-id="75cc1-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="75cc1-131">Eine geschachtelte `Try`... `Catch`... `Finally` Konstruktion muss vollständig im enthalten sein, eine `Try` oder `Catch` Block von der Konstruktion, in dem sie geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="75cc1-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="75cc1-132">Die folgende Abbildung zeigt eine `Try` Konstruktion in einer anderen geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="75cc1-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="75cc1-133">Verschiedene getestete Branches zwischen die beiden Konstruktionen Datenblöcke werden als gültig oder ungültig angegeben.</span><span class="sxs-lookup"><span data-stu-id="75cc1-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="75cc1-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75cc1-135">Example</span></span>  
 <span data-ttu-id="75cc1-136">Im folgenden Beispiel wird die `GoTo` Branch in Zeile Bezeichnungen in einer Prozedur-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="75cc1-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="75cc1-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75cc1-137">See also</span></span>

- [<span data-ttu-id="75cc1-138">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="75cc1-139">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="75cc1-140">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="75cc1-141">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="75cc1-142">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="75cc1-143">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="75cc1-144">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="75cc1-145">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="75cc1-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
