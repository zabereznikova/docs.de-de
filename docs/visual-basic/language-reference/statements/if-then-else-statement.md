---
title: If...Then...Else-Anweisung (Visual Basic)
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
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
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="4b2bb-102">If...Then...Else-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b2bb-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="4b2bb-103">Führt bedingt eine Gruppe von Anweisungen aus, abhängig vom Wert eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b2bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b2bb-104">Syntax</span></span>  
  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="4b2bb-105">Links zu Beispielcode</span><span class="sxs-lookup"><span data-stu-id="4b2bb-105">Quick links to example code</span></span>

<span data-ttu-id="4b2bb-106">Dieser Artikel enthält mehrere Beispiele, die Verwendungen der veranschaulichen die `If`... `Then`... `Else` Anweisung:</span><span class="sxs-lookup"><span data-stu-id="4b2bb-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="4b2bb-107">Mehrzeilige Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="4b2bb-108">Geschachtelte Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="4b2bb-109">Einzeilige Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="4b2bb-110">Teile</span><span class="sxs-lookup"><span data-stu-id="4b2bb-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="4b2bb-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-111">Required.</span></span> <span data-ttu-id="4b2bb-112">Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-112">Expression.</span></span> <span data-ttu-id="4b2bb-113">Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="4b2bb-114">Wenn der Ausdruck ist ein [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` Variable, der ergibt [nichts](../../../visual-basic/language-reference/nothing.md), die Bedingung wird behandelt, als ob der Ausdruck ist `False` und die `Else` Block ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="4b2bb-115">In der Syntax für einzeilige erforderlich; in mehrzeiligen Syntax optional.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="4b2bb-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-116">Optional.</span></span> <span data-ttu-id="4b2bb-117">Eine oder mehrere Anweisungen nach `If`... `Then` , die ausgeführt werden, wenn `condition` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="4b2bb-118">Erforderlich, wenn `ElseIf` vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="4b2bb-119">Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-119">Expression.</span></span> <span data-ttu-id="4b2bb-120">Muss ergeben `True` oder `False`, oder in einen Datentyp, der implizit in `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="4b2bb-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-121">Optional.</span></span> <span data-ttu-id="4b2bb-122">Eine oder mehrere Anweisungen nach `ElseIf`... `Then` , die ausgeführt werden, wenn `elseifcondition` ergibt `True`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="4b2bb-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-123">Optional.</span></span> <span data-ttu-id="4b2bb-124">Eine oder mehrere Anweisungen, die ausgeführt werden, wenn kein vorheriges `condition` oder `elseifcondition` Ausdruck wird zu `True`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="4b2bb-125">Beendet die mehrzeilige Version des `If`... `Then`... `Else` Block.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b2bb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b2bb-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="4b2bb-127">Multiline-syntax</span><span class="sxs-lookup"><span data-stu-id="4b2bb-127">Multiline syntax</span></span>  
 <span data-ttu-id="4b2bb-128">Wenn ein `If`... `Then`... `Else` Anweisung festgestellt wird, `condition` getestet wird.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="4b2bb-129">Wenn `condition` ist `True`, die nachfolgenden Anweisungen `Then` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="4b2bb-130">Wenn `condition` ist `False`, die jeweils `ElseIf` Anweisung (sofern vorhanden) wird in der Reihenfolge ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="4b2bb-131">Wenn eine `True` `elseifcondition` gefunden wird, werden die Anweisungen, die direkt nach der zugeordneten `ElseIf` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="4b2bb-132">Wenn kein `elseifcondition` ergibt `True`, oder es sind keine `ElseIf` -Anweisungen, die nachfolgenden Anweisungen `Else` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="4b2bb-133">Nach dem Ausführen der folgenden Anweisungen `Then`, `ElseIf`, oder `Else`, die Ausführung wird fortgeführt, mit der folgenden Anweisung `End If`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="4b2bb-134">Die `ElseIf` und `Else` Klauseln sind optional.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="4b2bb-135">Sie können beliebig viele `ElseIf` Klauseln, wie Sie möchten, dass in einer `If`... `Then`... `Else` -Anweisung, jedoch keine `ElseIf` -Klausel kann angezeigt werden, nachdem ein `Else` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="4b2bb-136">`If`... `Then`... `Else` -Anweisungen können ineinander geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="4b2bb-137">In der Syntax von mehrzeiligen der `If` Anweisung muss die einzige Anweisung in der ersten Zeile sein.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="4b2bb-138">Die `ElseIf`, `Else`, und `End If` Anweisungen können nur von einer zeilenbezeichnung vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="4b2bb-139">Die `If`... `Then`... `Else` Block mit Enden einer `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4b2bb-140">Die [auswählen... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) kann nützlicher sein, wenn Sie einen einzelnen Ausdruck auswerten, die mehrere mögliche Werte hat.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="4b2bb-141">Einzeilige-syntax</span><span class="sxs-lookup"><span data-stu-id="4b2bb-141">Single-Line syntax</span></span>  
 <span data-ttu-id="4b2bb-142">Können die einzeilige Syntax für eine einzelne Bedingung mit dem Code ausgeführt werden, wenn dieser Wert true ist.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="4b2bb-143">Allerdings wird die Syntax mehrere Zeilen Struktur und flexibler und ist einfacher zu lesen, verwalten und Debuggen.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="4b2bb-144">Welche folgt die `Then` Schlüsselwort wird untersucht, um zu bestimmen, ob eine Anweisung eine einzeilige `If`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="4b2bb-145">Wenn etwas anderes als ein Kommentar, nach dem angezeigt `Then` in der gleichen Zeile wird die Anweisung als eine einzeilige behandelt `If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="4b2bb-146">Wenn `Then` nicht vorhanden ist, muss er den Anfang einer mehrzeiligen `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="4b2bb-147">In der Syntax einzeilige können mehrere Anweisungen, die als Ergebnis der Ausführung einer `If`... `Then` Entscheidung.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="4b2bb-148">Alle Anweisungen müssen in der gleichen Zeile und durch Doppelpunkte getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="4b2bb-149">Mehrzeilige Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="4b2bb-150">Das folgende Beispiel veranschaulicht die Verwendung der mehrzeiligen Syntax für die `If`... `Then`... `Else` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a><span data-ttu-id="4b2bb-151">Geschachtelte Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="4b2bb-152">Das folgende Beispiel enthält geschachtelte `If`... `Then`... `Else` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="4b2bb-153">Einzeilige Syntaxbeispiel</span><span class="sxs-lookup"><span data-stu-id="4b2bb-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="4b2bb-154">Das folgende Beispiel veranschaulicht die Verwendung der Syntax einzeilige.</span><span class="sxs-lookup"><span data-stu-id="4b2bb-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a><span data-ttu-id="4b2bb-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b2bb-155">See also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="4b2bb-156">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="4b2bb-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="4b2bb-157">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4b2bb-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="4b2bb-158">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4b2bb-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="4b2bb-159">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4b2bb-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="4b2bb-160">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b2bb-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="4b2bb-161">If-Operator</span><span class="sxs-lookup"><span data-stu-id="4b2bb-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
