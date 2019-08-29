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
ms.openlocfilehash: e0b365afaa8cf7dff130cf01d2937be629e5f7a8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106520"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="33d80-102">If...Then...Else-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33d80-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="33d80-103">Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="33d80-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="33d80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="33d80-105">Quick Links zum Beispielcode</span><span class="sxs-lookup"><span data-stu-id="33d80-105">Quick links to example code</span></span>

<span data-ttu-id="33d80-106">Dieser Artikel enthält einige Beispiele, in denen die `If`Verwendung von veranschaulicht wird... `Then`... `Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="33d80-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="33d80-107">Beispiel für mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="33d80-108">Beispiel für eine Beispiel Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="33d80-109">Beispiel für einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="33d80-110">Teile</span><span class="sxs-lookup"><span data-stu-id="33d80-110">Parts</span></span>

`condition` \
<span data-ttu-id="33d80-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="33d80-111">Required.</span></span> <span data-ttu-id="33d80-112">Begriff.</span><span class="sxs-lookup"><span data-stu-id="33d80-112">Expression.</span></span> <span data-ttu-id="33d80-113">Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertierbar ist.</span><span class="sxs-lookup"><span data-stu-id="33d80-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="33d80-114">Wenn der Ausdruck eine Variable ist, die [null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` `False` -Werte zulässt, die als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird die Bedingung so behandelt, als ob der Ausdruck und der `Else` -Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="33d80-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>

`Then` \
<span data-ttu-id="33d80-115">Erforderlich in der einzeiligen Syntax; optional in der mehrzeiligen Syntax.</span><span class="sxs-lookup"><span data-stu-id="33d80-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="33d80-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="33d80-116">Optional.</span></span> <span data-ttu-id="33d80-117">Mindestens eine-Anweisung folgt `If`... , die ausgeführt wird, wenn `True`zu ausgewertet wird `condition`. `Then`</span><span class="sxs-lookup"><span data-stu-id="33d80-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="33d80-118">Erforderlich, `ElseIf` wenn vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="33d80-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="33d80-119">Begriff.</span><span class="sxs-lookup"><span data-stu-id="33d80-119">Expression.</span></span> <span data-ttu-id="33d80-120">Muss zu `True` oder `False`oder zu einem Datentyp ausgewertet werden, der implizit in `Boolean`konvertierbar ist.</span><span class="sxs-lookup"><span data-stu-id="33d80-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="33d80-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="33d80-121">Optional.</span></span> <span data-ttu-id="33d80-122">Mindestens eine-Anweisung folgt `ElseIf`... , die ausgeführt wird, wenn `True`zu ausgewertet wird `elseifcondition`. `Then`</span><span class="sxs-lookup"><span data-stu-id="33d80-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="33d80-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="33d80-123">Optional.</span></span> <span data-ttu-id="33d80-124">Eine oder mehrere-Anweisungen, die ausgeführt werden, `condition` Wenn `elseifcondition` kein vorheriger- `True`oder-Ausdruck als ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="33d80-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="33d80-125">Beendet die mehrzeilige Version `If`von... `Then`... `Else` blockieren.</span><span class="sxs-lookup"><span data-stu-id="33d80-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="33d80-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33d80-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="33d80-127">Mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-127">Multiline syntax</span></span>

<span data-ttu-id="33d80-128">Wenn ein `If`... `Then`... -Anweisung gefunden wurde `condition` , wird getestet. `Else`</span><span class="sxs-lookup"><span data-stu-id="33d80-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="33d80-129">Wenn `condition`den Wert `Then` hat, werden die folgenden Anweisungen ausgeführt. `True`</span><span class="sxs-lookup"><span data-stu-id="33d80-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="33d80-130">Wenn `condition`den Wert `ElseIf` hat, wird jede-Anweisung (sofern vorhanden) in der richtigen Reihenfolge ausgewertet. `False`</span><span class="sxs-lookup"><span data-stu-id="33d80-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="33d80-131">Wenn eine `True` `elseifcondition` gefunden wird, werden die Anweisungen, die unmittelbar `ElseIf` auf die zugeordneten folgen, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="33d80-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="33d80-132">Wenn keine `elseifcondition` `ElseIf` ausgewertet wird oder wenn keine-Anweisungen vorhanden sind, werden die folgenden `Else` Anweisungen ausgeführt. `True`</span><span class="sxs-lookup"><span data-stu-id="33d80-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="33d80-133">Nach dem Ausführen der Anweisungen `Then`, `ElseIf`die nach `Else`, oder ausgeführt werden, wird die `End If`Ausführung mit der folgenden Anweisung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="33d80-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="33d80-134">Die `ElseIf` Klauseln `Else` und sind optional.</span><span class="sxs-lookup"><span data-stu-id="33d80-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="33d80-135">Sie können beliebig viele `ElseIf` Klauseln in einem `If`... `Then`... -Anweisung, aber `ElseIf` keine-Klausel kann nach `Else` einer-Klausel angezeigt werden. `Else`</span><span class="sxs-lookup"><span data-stu-id="33d80-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="33d80-136">`If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="33d80-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="33d80-137">In der mehrzeiligen Syntax muss `If` die-Anweisung die einzige Anweisung in der ersten Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="33d80-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="33d80-138">Der `ElseIf`- `Else`,- `End If` und-Anweisung kann nur eine Zeilen Bezeichnung vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="33d80-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="33d80-139">Die `If`... `Then`... Block muss mit einer `End If` -Anweisung enden. `Else`</span><span class="sxs-lookup"><span data-stu-id="33d80-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="33d80-140">Die [SELECT... Die Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) ist möglicherweise nützlicher, wenn Sie einen einzelnen Ausdruck mit mehreren möglichen Werten auswerten.</span><span class="sxs-lookup"><span data-stu-id="33d80-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="33d80-141">Einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-141">Single-Line syntax</span></span>

<span data-ttu-id="33d80-142">Sie können die einzeilige Syntax für eine einzelne Bedingung mit Code verwenden, der ausgeführt wird, wenn der Wert true ist.</span><span class="sxs-lookup"><span data-stu-id="33d80-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="33d80-143">Die mehrzeilige Syntax bietet jedoch mehr Struktur und Flexibilität und ist leichter zu lesen, zu warten und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="33d80-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="33d80-144">Wie das `Then` -Schlüsselwort folgt, wird überprüft, um zu bestimmen, ob eine `If`-Anweisung eine einzeilige ist.</span><span class="sxs-lookup"><span data-stu-id="33d80-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="33d80-145">Wenn etwas anderes als ein Kommentar nach `Then` in derselben Zeile angezeigt wird, wird die-Anweisung als einzeilige `If` Anweisung behandelt.</span><span class="sxs-lookup"><span data-stu-id="33d80-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="33d80-146">Wenn `Then` nicht vorhanden ist, muss es sich um den Anfang eines mehrzeiligen `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="33d80-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="33d80-147">In der einzeiligen Syntax können mehrere-Anweisungen als Ergebnis eines `If`... `Then` Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="33d80-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="33d80-148">Alle-Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkte getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="33d80-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="33d80-149">Beispiel für mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="33d80-150">Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax von `If`... `Then`... `Else` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="33d80-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="33d80-151">Beispiel für eine Beispiel Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="33d80-152">Das folgende Beispiel enthält `If`die-Tabelle... `Then`... `Else` -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="33d80-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="33d80-153">Beispiel für einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="33d80-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="33d80-154">Im folgenden Beispiel wird die Verwendung der einzeiligen Syntax veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="33d80-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="33d80-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33d80-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="33d80-156">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="33d80-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="33d80-157">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="33d80-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="33d80-158">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="33d80-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="33d80-159">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="33d80-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="33d80-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33d80-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="33d80-161">If-Operator</span><span class="sxs-lookup"><span data-stu-id="33d80-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
