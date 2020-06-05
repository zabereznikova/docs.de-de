---
title: If...Then...Else-Anweisung
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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404588"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="7f710-102">If...Then...Else-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f710-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="7f710-103">Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="7f710-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f710-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-104">Syntax</span></span>

```vb
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="7f710-105">Quick Links zum Beispielcode</span><span class="sxs-lookup"><span data-stu-id="7f710-105">Quick links to example code</span></span>

<span data-ttu-id="7f710-106">Dieser Artikel enthält einige Beispiele, in denen die Verwendung von veranschaulicht wird `If` .. `Then` . ...`Else` an</span><span class="sxs-lookup"><span data-stu-id="7f710-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="7f710-107">Beispiel für mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="7f710-108">Beispiel für eine Beispiel Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="7f710-109">Beispiel für einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="7f710-110">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7f710-110">Parts</span></span>

`condition` \
<span data-ttu-id="7f710-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f710-111">Required.</span></span> <span data-ttu-id="7f710-112">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="7f710-112">Expression.</span></span> <span data-ttu-id="7f710-113">Muss zu `True` oder `False` oder zu einem Datentyp ausgewertet werden, der implizit in konvertierbar ist `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7f710-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="7f710-114">Wenn der Ausdruck eine Variable ist, die [NULL-Werte](../../programming-guide/language-features/data-types/nullable-value-types.md) zulässt, die als "Nothing" ausgewertet wird `Boolean` , wird die Bedingung so behandelt, als wäre der Ausdruck [Nothing](../nothing.md) `False` , und die `ElseIf` Blöcke werden ausgewertet, wenn Sie vorhanden sind, oder der `Else` Block wird ausgeführt, wenn er vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7f710-114">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="7f710-115">Erforderlich in der einzeiligen Syntax; optional in der mehrzeiligen Syntax.</span><span class="sxs-lookup"><span data-stu-id="7f710-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="7f710-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="7f710-116">Optional.</span></span> <span data-ttu-id="7f710-117">Eine oder mehrere-Anweisungen `If` `Then` , die ausgeführt werden, wenn `condition` zu ausgewertet wird `True` .</span><span class="sxs-lookup"><span data-stu-id="7f710-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="7f710-118">Erforderlich, wenn `ElseIf` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7f710-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="7f710-119">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="7f710-119">Expression.</span></span> <span data-ttu-id="7f710-120">Muss zu `True` oder `False` oder zu einem Datentyp ausgewertet werden, der implizit in konvertierbar ist `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7f710-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="7f710-121">Optional.</span><span class="sxs-lookup"><span data-stu-id="7f710-121">Optional.</span></span> <span data-ttu-id="7f710-122">Eine oder mehrere-Anweisungen `ElseIf` `Then` , die ausgeführt werden, wenn `elseifcondition` zu ausgewertet wird `True` .</span><span class="sxs-lookup"><span data-stu-id="7f710-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="7f710-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="7f710-123">Optional.</span></span> <span data-ttu-id="7f710-124">Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn kein vorheriger- `condition` oder- `elseifcondition` Ausdruck als ausgewertet wird `True` .</span><span class="sxs-lookup"><span data-stu-id="7f710-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="7f710-125">Beendet die mehrzeilige Version von `If` ... `Then` ...`Else` Baustein.</span><span class="sxs-lookup"><span data-stu-id="7f710-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f710-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7f710-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="7f710-127">Mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-127">Multiline syntax</span></span>

<span data-ttu-id="7f710-128">Wenn ein `If` ... `Then` ...`Else` -Anweisung gefunden wurde, `condition` wird getestet.</span><span class="sxs-lookup"><span data-stu-id="7f710-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="7f710-129">Wenn `condition` `True` den Wert hat, werden die folgenden Anweisungen `Then` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="7f710-130">Wenn den Wert `condition` `False` hat, wird jede- `ElseIf` Anweisung (sofern vorhanden) in der richtigen Reihenfolge ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7f710-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="7f710-131">Wenn eine `True` `elseifcondition` gefunden wird, werden die Anweisungen, die unmittelbar auf die zugeordneten folgen, `ElseIf` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="7f710-132">Wenn keine `elseifcondition` ausgewertet `True` wird oder wenn keine-Anweisungen vorhanden sind `ElseIf` , werden die folgenden Anweisungen `Else` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7f710-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="7f710-133">Nach dem Ausführen der Anweisungen `Then` , die nach, `ElseIf` oder ausgeführt `Else` werden, wird die Ausführung mit der folgenden Anweisung fortgesetzt `End If` .</span><span class="sxs-lookup"><span data-stu-id="7f710-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="7f710-134">Die `ElseIf` `Else` Klauseln und sind optional.</span><span class="sxs-lookup"><span data-stu-id="7f710-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="7f710-135">Sie können beliebig viele `ElseIf` Klauseln in einem `If` ... `Then` ...`Else` -Anweisung, aber keine- `ElseIf` Klausel kann nach einer-Klausel angezeigt werden `Else` .</span><span class="sxs-lookup"><span data-stu-id="7f710-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="7f710-136">`If`...`Then` ...`Else` -Anweisungen können ineinander geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="7f710-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="7f710-137">In der mehrzeiligen Syntax muss die- `If` Anweisung die einzige Anweisung in der ersten Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="7f710-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="7f710-138">Der `ElseIf` `Else` -,-und- `End If` Anweisung kann nur eine Zeilen Bezeichnung vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7f710-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="7f710-139">Die `If` ... `Then` ...`Else` Block muss mit einer- `End If` Anweisung enden.</span><span class="sxs-lookup"><span data-stu-id="7f710-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="7f710-140">Die [SELECT... Die Case-Anweisung](select-case-statement.md) ist möglicherweise nützlicher, wenn Sie einen einzelnen Ausdruck mit mehreren möglichen Werten auswerten.</span><span class="sxs-lookup"><span data-stu-id="7f710-140">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="7f710-141">Einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-141">Single-Line syntax</span></span>

<span data-ttu-id="7f710-142">Sie können die einzeilige Syntax für eine einzelne Bedingung mit Code verwenden, der ausgeführt wird, wenn der Wert true ist.</span><span class="sxs-lookup"><span data-stu-id="7f710-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="7f710-143">Die mehrzeilige Syntax bietet jedoch mehr Struktur und Flexibilität und ist leichter zu lesen, zu warten und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="7f710-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="7f710-144">Wie das- `Then` Schlüsselwort folgt, wird überprüft, um zu bestimmen, ob eine-Anweisung eine einzeilige ist `If` .</span><span class="sxs-lookup"><span data-stu-id="7f710-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="7f710-145">Wenn etwas anderes als ein Kommentar nach `Then` in derselben Zeile angezeigt wird, wird die-Anweisung als einzeilige `If` Anweisung behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f710-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="7f710-146">Wenn nicht `Then` vorhanden ist, muss es sich um den Anfang eines mehrzeiligen `If` ... `Then` ...`Else`.</span><span class="sxs-lookup"><span data-stu-id="7f710-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="7f710-147">In der einzeiligen Syntax können mehrere-Anweisungen als Ergebnis einer `If` ...-Entscheidung ausgeführt werden `Then` .</span><span class="sxs-lookup"><span data-stu-id="7f710-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="7f710-148">Alle-Anweisungen müssen sich in derselben Zeile befinden und durch Doppelpunkte getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="7f710-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="7f710-149">Beispiel für mehrzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="7f710-150">Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax von `If` ... `Then` ...`Else` an.</span><span class="sxs-lookup"><span data-stu-id="7f710-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="7f710-151">Beispiel für eine Beispiel Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="7f710-152">Das folgende Beispiel enthält die-Tabelle `If` ... `Then` ...`Else` Äußerungen.</span><span class="sxs-lookup"><span data-stu-id="7f710-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="7f710-153">Beispiel für einzeilige Syntax</span><span class="sxs-lookup"><span data-stu-id="7f710-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="7f710-154">Im folgenden Beispiel wird die Verwendung der einzeiligen Syntax veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7f710-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="7f710-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f710-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="7f710-156">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7f710-156">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="7f710-157">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7f710-157">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="7f710-158">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="7f710-158">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="7f710-159">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="7f710-159">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="7f710-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f710-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="7f710-161">If-Operator</span><span class="sxs-lookup"><span data-stu-id="7f710-161">If Operator</span></span>](../operators/if-operator.md)
