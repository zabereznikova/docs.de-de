---
title: If...Then...Else-Anweisung (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: d91a913d515f36a6b974850bc30079b000a919b4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842693"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="de022-102">If...Then...Else-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de022-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="de022-103">Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="de022-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de022-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de022-104">Syntax</span></span>  
  
```  
' Multiline syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  

## <a name="quick-links-to-example-code"></a><span data-ttu-id="de022-105">Quicklinks zum Beispielcode</span><span class="sxs-lookup"><span data-stu-id="de022-105">Quick links to example code</span></span>

<span data-ttu-id="de022-106">Dieser Artikel enthält mehrere Beispiele, wird von zeigen der `If`... `Then`... `Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="de022-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="de022-107">Mehrzeilige Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="de022-108">Geschachtelte Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="de022-109">Einzeilige Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="de022-110">Teile</span><span class="sxs-lookup"><span data-stu-id="de022-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="de022-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="de022-111">Required.</span></span> <span data-ttu-id="de022-112">-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de022-112">Expression.</span></span> <span data-ttu-id="de022-113">Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="de022-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="de022-114">Wenn der Ausdruck ist eine [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, die sich ergibt [nichts](../../../visual-basic/language-reference/nothing.md), die Bedingung wird behandelt, als ob der Ausdruck ist `False` und `Else` Block wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="de022-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="de022-115">In der Syntax einzeilige erforderlich. in der mehrzeiligen Syntax optional.</span><span class="sxs-lookup"><span data-stu-id="de022-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="de022-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="de022-116">Optional.</span></span> <span data-ttu-id="de022-117">Eine oder mehrere Anweisungen nach `If`... `Then` ausgeführt werden, wenn `condition` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="de022-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="de022-118">Erforderlich, wenn `ElseIf` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="de022-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="de022-119">-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de022-119">Expression.</span></span> <span data-ttu-id="de022-120">Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="de022-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="de022-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="de022-121">Optional.</span></span> <span data-ttu-id="de022-122">Eine oder mehrere Anweisungen nach `ElseIf`... `Then` ausgeführt werden, wenn `elseifcondition` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="de022-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="de022-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="de022-123">Optional.</span></span> <span data-ttu-id="de022-124">Eine oder mehrere Anweisungen, die ausgeführt werden, wenn kein vorheriges `condition` oder `elseifcondition` Ausdruck wird zu `True`.</span><span class="sxs-lookup"><span data-stu-id="de022-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="de022-125">Beendet die mehrzeilige Version des `If`... `Then`... `Else` Block.</span><span class="sxs-lookup"><span data-stu-id="de022-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de022-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de022-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="de022-127">Multiline-syntax</span><span class="sxs-lookup"><span data-stu-id="de022-127">Multiline syntax</span></span>  
 <span data-ttu-id="de022-128">Wenn ein `If`... `Then`... `Else` -Anweisung gefunden, `condition` getestet wird.</span><span class="sxs-lookup"><span data-stu-id="de022-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="de022-129">Wenn `condition` ist `True`, die nachfolgenden Anweisungen `Then` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de022-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="de022-130">Wenn `condition` ist `False`, die jeweils `ElseIf` Anweisung (sofern vorhanden) wird in der Reihenfolge ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="de022-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="de022-131">Wenn eine `True` `elseifcondition` gefunden wird, wird die Anweisungen, die direkt nach der zugeordneten `ElseIf` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de022-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="de022-132">Wenn kein `elseifcondition` ergibt `True`, oder es sind keine `ElseIf` Anweisungen, die nachfolgenden Anweisungen `Else` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="de022-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="de022-133">Nach dem Ausführen der folgenden Anweisungen `Then`, `ElseIf`, oder `Else`, Ausführung wird fortgeführt, mit der Anweisung nach `End If`.</span><span class="sxs-lookup"><span data-stu-id="de022-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="de022-134">Die `ElseIf` und `Else` Klauseln sind optional.</span><span class="sxs-lookup"><span data-stu-id="de022-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="de022-135">Sie haben so viele `ElseIf` Klauseln, wie Sie möchten in einer `If`... `Then`... `Else` -Anweisung, jedoch keine `ElseIf` -Klausel kann nach dem erscheinen einer `Else` Klausel.</span><span class="sxs-lookup"><span data-stu-id="de022-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="de022-136">`If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="de022-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="de022-137">In der mehrzeiligen Syntax der `If` Anweisung muss die einzige Anweisung in der ersten Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="de022-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="de022-138">Die `ElseIf`, `Else`, und `End If` Anweisungen können nur von der Bezeichnung einer Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="de022-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="de022-139">Die `If`... `Then`... `Else` Block mit Enden einer `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="de022-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="de022-140">Die [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) kann mehr hilfreich sein, wenn Sie einen einzelnen Ausdruck auswerten, die mehrere mögliche Werte hat.</span><span class="sxs-lookup"><span data-stu-id="de022-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="de022-141">Einzeilige syntax</span><span class="sxs-lookup"><span data-stu-id="de022-141">Single-Line syntax</span></span>  
 <span data-ttu-id="de022-142">Sie können die Syntax für einzeilige für eine einzelne Bedingung mit Code ausgeführt werden, wenn es "true" ist.</span><span class="sxs-lookup"><span data-stu-id="de022-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="de022-143">Allerdings wird die Syntax mehrere Zeilen Struktur und Flexibilität bietet und ist einfacher zu lesen, verwalten und Debuggen.</span><span class="sxs-lookup"><span data-stu-id="de022-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="de022-144">Nachfolgend die `Then` Schlüsselwort wird untersucht, um zu bestimmen, ob eine Anweisung mit einem einzeiligen ist `If`.</span><span class="sxs-lookup"><span data-stu-id="de022-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="de022-145">Wenn etwas anderes als ein Kommentar angezeigt, nach dem wird `Then` in der gleichen Zeile wird die Anweisung als einem einzeiligen behandelt `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="de022-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="de022-146">Wenn `Then` nicht vorhanden ist, muss er den Anfang einer Zeile `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="de022-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="de022-147">In der Syntax einzeilige haben Sie mehrere Anweisungen, die als Ergebnis der Ausführung einer `If`... `Then` Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="de022-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="de022-148">Alle Anweisungen in der gleichen Zeile befinden müssen, und durch Doppelpunkte getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="de022-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="de022-149">Mehrzeilige Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="de022-150">Das folgende Beispiel veranschaulicht die Verwendung der Syntax für den mehrzeiligen der `If`... `Then`... `Else` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="de022-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="de022-151">Geschachtelte Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="de022-152">Das folgende Beispiel enthält geschachtelte `If`... `Then`... `Else` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="de022-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="de022-153">Einzeilige Attributsyntax-Beispiel</span><span class="sxs-lookup"><span data-stu-id="de022-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="de022-154">Das folgende Beispiel veranschaulicht die Verwendung der Syntax einzeilige.</span><span class="sxs-lookup"><span data-stu-id="de022-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]
  
## <a name="see-also"></a><span data-ttu-id="de022-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de022-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="de022-156">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="de022-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="de022-157">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="de022-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="de022-158">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="de022-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="de022-159">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="de022-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="de022-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de022-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="de022-161">If-Operator</span><span class="sxs-lookup"><span data-stu-id="de022-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
