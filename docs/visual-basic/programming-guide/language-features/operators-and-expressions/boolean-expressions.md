---
title: Boolesche Ausdrücke
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 51340bf95795d837c055df796424f3cad912adc7
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085749"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="7ef2d-102">Boolesche Ausdrücke (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ef2d-102">Boolean Expressions (Visual Basic)</span></span>

<span data-ttu-id="7ef2d-103">Ein *boolescher Ausdruck* ist ein Ausdruck, der zu einem Wert des [booleschen Datentyps](../../../language-reference/data-types/boolean-data-type.md)ausgewertet wird: `True` oder `False` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="7ef2d-104">`Boolean` Ausdrücke können mehrere Formen annehmen.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="7ef2d-105">Am einfachsten ist der direkte Vergleich des Werts einer `Boolean` Variablen mit einem `Boolean` Literalwert, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="7ef2d-106">Zwei Bedeutungen des =-Operators</span><span class="sxs-lookup"><span data-stu-id="7ef2d-106">Two Meanings of the = Operator</span></span>  

 <span data-ttu-id="7ef2d-107">Beachten Sie, dass die Zuweisungsanweisung `newCustomer = True` wie der Ausdruck im vorherigen Beispiel aussieht, aber eine andere Funktion ausführt und anders verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="7ef2d-108">Im vorherigen Beispiel stellt der Ausdruck `newCustomer = True` einen booleschen Wert dar, und das `=` Vorzeichen wird als Vergleichs Operator interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="7ef2d-109">In einer eigenständigen-Anweisung wird das `=` Vorzeichen als Zuweisungs Operator interpretiert und weist der Variablen auf der linken Seite den Wert auf der rechten Seite zu.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="7ef2d-110">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="7ef2d-111">Weitere Informationen finden Sie unter [Wert Vergleiche](value-comparisons.md) und- [Anweisungen](../../../language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2d-111">For further information, see [Value Comparisons](value-comparisons.md) and [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="7ef2d-112">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="7ef2d-112">Comparison Operators</span></span>  

 <span data-ttu-id="7ef2d-113">Vergleichs Operatoren wie `=` , `<` , `>` , `<>` , `<=` und werden `>=` boolesche Ausdrücke erzeugt, indem der Ausdruck auf der linken Seite des Operators mit dem Ausdruck auf der rechten Seite des Operators verglichen und das Ergebnis als oder ausgewertet `True` wird `False` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="7ef2d-114">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="7ef2d-115">Da 42 kleiner als 81 ist, wird der boolesche Ausdruck im vorherigen Beispiel zu ausgewertet `True` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="7ef2d-116">Weitere Informationen zu dieser Art von Ausdruck finden Sie unter [Wert Vergleiche](value-comparisons.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2d-116">For more information on this kind of expression, see [Value Comparisons](value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="7ef2d-117">Vergleichs Operatoren in Kombination mit logischen Operatoren</span><span class="sxs-lookup"><span data-stu-id="7ef2d-117">Comparison Operators Combined with Logical Operators</span></span>  

 <span data-ttu-id="7ef2d-118">Vergleichsausdrücke können mit logischen Operatoren kombiniert werden, um komplexere boolesche Ausdrücke zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="7ef2d-119">Das folgende Beispiel veranschaulicht die Verwendung von Vergleichs Operatoren in Verbindung mit einem logischen Operator.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="7ef2d-120">Im vorherigen Beispiel hängt der Wert des allgemeinen Ausdrucks von den Werten der Ausdrücke auf den einzelnen Seiten des `And` Operators ab.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="7ef2d-121">Wenn beide Ausdrücke sind `True` , wird der allgemeine Ausdruck als ausgewertet `True` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="7ef2d-122">Wenn einer der Ausdrücke ist `False` , wird der gesamte Ausdruck als ausgewertet `False` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="7ef2d-123">Kurzschluss Operatoren</span><span class="sxs-lookup"><span data-stu-id="7ef2d-123">Short-Circuiting Operators</span></span>  

 <span data-ttu-id="7ef2d-124">Die logischen Operatoren und weisen das Verhalten auf, das `AndAlso` `OrElse` als *Kurzschluss*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="7ef2d-125">Ein Kurzschluss Operator wertet den linken Operanden zuerst aus.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="7ef2d-126">Wenn der linke Operand den Wert des gesamten Ausdrucks bestimmt, wird die Programmausführung fortgesetzt, ohne den rechten Ausdruck auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="7ef2d-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="7ef2d-128">Im vorherigen Beispiel wertet der Operator den linken Ausdruck aus `45 < 12` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="7ef2d-129">Da der linke Ausdruck als ausgewertet `False` wird, muss der gesamte logische Ausdruck zu ausgewertet werden `False` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="7ef2d-130">Die Programmausführung überspringt somit die Ausführung des Codes innerhalb des `If` Blocks, ohne den rechten Ausdruck auszuwerten `testFunction(3)` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="7ef2d-131">In diesem Beispiel wird nicht aufgerufen, `testFunction()` da der linke Ausdruck den gesamten Ausdruck fälert.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="7ef2d-132">Entsprechend geht die Ausführung, wenn der linke Ausdruck in einem logischen Ausdruck mit `OrElse` ausgewertet `True` wird, mit der nächsten Codezeile fort, ohne den rechten Ausdruck auszuwerten, da der linke Ausdruck bereits den gesamten Ausdruck überprüft hat.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="7ef2d-133">Vergleich mit nicht Kurzschluss Operatoren</span><span class="sxs-lookup"><span data-stu-id="7ef2d-133">Comparison with Non-Short-Circuiting Operators</span></span>  

 <span data-ttu-id="7ef2d-134">Im Gegensatz dazu werden beide Seiten des logischen Operators ausgewertet, wenn die logischen Operatoren `And` und `Or` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="7ef2d-135">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="7ef2d-136">Im vorangehenden Beispiel wird aufgerufen `testFunction()` , auch wenn der linke Ausdruck als ausgewertet wird `False` .</span><span class="sxs-lookup"><span data-stu-id="7ef2d-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="7ef2d-137">Klammer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7ef2d-137">Parenthetical Expressions</span></span>  

 <span data-ttu-id="7ef2d-138">Sie können Klammern verwenden, um die Reihenfolge der Auswertung von booleschen Ausdrücken zu steuern.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="7ef2d-139">Ausdrücke, die in Klammern eingeschlossen sind, werden zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="7ef2d-140">Bei mehreren Schachtelungs Ebenen wird den untersten geschachtelten Ausdrücken Vorrang eingeräumt.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="7ef2d-141">Innerhalb von Klammern verläuft die Auswertung gemäß den Regeln der Operator Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="7ef2d-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="7ef2d-142">Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="7ef2d-142">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef2d-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ef2d-143">See also</span></span>

- [<span data-ttu-id="7ef2d-144">Logische und bitweise Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef2d-144">Logical and Bitwise Operators in Visual Basic</span></span>](logical-and-bitwise-operators.md)
- [<span data-ttu-id="7ef2d-145">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="7ef2d-145">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="7ef2d-146">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7ef2d-146">Statements</span></span>](../statements.md)
- [<span data-ttu-id="7ef2d-147">Comparison Operators (Vergleichsoperatoren)</span><span class="sxs-lookup"><span data-stu-id="7ef2d-147">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="7ef2d-148">Effiziente Kombination von Operatoren</span><span class="sxs-lookup"><span data-stu-id="7ef2d-148">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
- [<span data-ttu-id="7ef2d-149">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ef2d-149">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7ef2d-150">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7ef2d-150">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)
