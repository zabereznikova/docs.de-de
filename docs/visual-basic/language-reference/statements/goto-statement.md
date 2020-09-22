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
ms.openlocfilehash: 000f6754575bcce6b2d79d85541e755219aca956
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866624"
---
# <a name="goto-statement"></a><span data-ttu-id="b9927-102">GoTo-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-102">GoTo Statement</span></span>

<span data-ttu-id="b9927-103">Verzweigt bedingungslos in eine angegebene Zeile in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b9927-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9927-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9927-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="b9927-105">Teil</span><span class="sxs-lookup"><span data-stu-id="b9927-105">Part</span></span>  

 `line`  
 <span data-ttu-id="b9927-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b9927-106">Required.</span></span> <span data-ttu-id="b9927-107">Eine beliebige Zeilen Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="b9927-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9927-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b9927-108">Remarks</span></span>  

 <span data-ttu-id="b9927-109">Die- `GoTo` Anweisung kann nur an Zeilen in der Prozedur verzweigt werden, in der Sie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b9927-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="b9927-110">Die Linie muss über eine Zeilen Bezeichnung verfügen, `GoTo` auf die verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9927-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="b9927-111">Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="b9927-111">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9927-112">`GoTo` -Anweisungen können das Lesen und Verwalten des Codes erschweren.</span><span class="sxs-lookup"><span data-stu-id="b9927-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="b9927-113">Verwenden Sie, wenn möglich, stattdessen eine Steuerelement Struktur.</span><span class="sxs-lookup"><span data-stu-id="b9927-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="b9927-114">Weitere Informationen finden Sie unter [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9927-114">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="b9927-115">Sie können keine- `GoTo` Anweisung verwenden, um eine Verzweigung außerhalb eines...,. `For` `Next` `For Each` .. `Next` , `SyncLock` `End SyncLock` `Try` `Catch` ...,... ... `Finally` , `With` ... `End With` oder `Using` ... `End Using` in eine Bezeichnung in.</span><span class="sxs-lookup"><span data-stu-id="b9927-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="b9927-116">Verzweigungen und Versuchs Konstruktionen</span><span class="sxs-lookup"><span data-stu-id="b9927-116">Branching and Try Constructions</span></span>  

 <span data-ttu-id="b9927-117">In einer `Try` ... `Catch` ...`Finally` die folgenden Regeln gelten für die Verzweigung mit der- `GoTo` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b9927-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="b9927-118">Block oder Region</span><span class="sxs-lookup"><span data-stu-id="b9927-118">Block or region</span></span>|<span data-ttu-id="b9927-119">Verzweigungen von außerhalb</span><span class="sxs-lookup"><span data-stu-id="b9927-119">Branching in from outside</span></span>|<span data-ttu-id="b9927-120">Verzweigungen aus innerhalb</span><span class="sxs-lookup"><span data-stu-id="b9927-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="b9927-121">`Try`-Block</span><span class="sxs-lookup"><span data-stu-id="b9927-121">`Try` block</span></span>|<span data-ttu-id="b9927-122">Nur aus einem `Catch` Block desselben Baus <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9927-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="b9927-123">Nur für die gesamte Konstruktion</span><span class="sxs-lookup"><span data-stu-id="b9927-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="b9927-124">`Catch`-Block</span><span class="sxs-lookup"><span data-stu-id="b9927-124">`Catch` block</span></span>|<span data-ttu-id="b9927-125">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="b9927-125">Never allowed</span></span>|<span data-ttu-id="b9927-126">Nur für die gesamte Konstruktion oder den `Try` Block der gleichen Konstruktion <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9927-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="b9927-127">`Finally`-Block</span><span class="sxs-lookup"><span data-stu-id="b9927-127">`Finally` block</span></span>|<span data-ttu-id="b9927-128">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="b9927-128">Never allowed</span></span>|<span data-ttu-id="b9927-129">Nie zulässig</span><span class="sxs-lookup"><span data-stu-id="b9927-129">Never allowed</span></span>|  
  
 <span data-ttu-id="b9927-130"><sup>1</sup> `Try` .. `Catch` . ...`Finally` die Konstruktion ist in einer anderen geschachtelt, ein `Catch` Block kann in den `Try` Block auf der eigenen Schachtelungs Ebene, aber nicht in einen anderen Block verzweigen `Try` .</span><span class="sxs-lookup"><span data-stu-id="b9927-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="b9927-131">Ein `Try` ... `Catch` ...`Finally` die Konstruktion muss vollständig in einem- `Try` oder- `Catch` Block der Konstruktion enthalten sein, in der Sie geschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="b9927-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="b9927-132">Die folgende Abbildung zeigt eine `Try` in einer anderen geschachtelte Konstruktion.</span><span class="sxs-lookup"><span data-stu-id="b9927-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="b9927-133">Verschiedene Verzweigungen zwischen den Blöcken der beiden Konstruktionen werden als gültig oder ungültig angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9927-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Grafisches Diagramm zum Branchen in Try-Konstrukten](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="b9927-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9927-135">Example</span></span>  

 <span data-ttu-id="b9927-136">Im folgenden Beispiel wird die- `GoTo` Anweisung verwendet, um Zeilen Bezeichnungen in einer-Prozedur zu verzweigen.</span><span class="sxs-lookup"><span data-stu-id="b9927-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="b9927-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9927-137">See also</span></span>

- [<span data-ttu-id="b9927-138">Do...Loop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-138">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="b9927-139">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-139">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="b9927-140">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-140">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="b9927-141">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-141">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="b9927-142">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-142">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="b9927-143">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-143">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="b9927-144">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-144">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="b9927-145">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b9927-145">With...End With Statement</span></span>](with-end-with-statement.md)
