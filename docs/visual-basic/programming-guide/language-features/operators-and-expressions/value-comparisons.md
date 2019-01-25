---
title: Wertevergleich (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: 23733741a79506730187d5735a20f3848e43da1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724813"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="3c57a-102">Wertevergleich (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c57a-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="3c57a-103">Vergleichsoperatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte von numerischen Variablen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3c57a-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="3c57a-104">Diese Ausdrücke geben eine `Boolean` Wert basiert, ob der Vergleich "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="3c57a-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="3c57a-105">Beispiele für ein solcher Ausdruck sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="3c57a-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="3c57a-106">Der erste Ausdruck wird zu `True`, da 45 größer als 26 ist.</span><span class="sxs-lookup"><span data-stu-id="3c57a-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="3c57a-107">Im zweite Beispiel ergibt `False`, da 26 nicht größer als 45 befindet.</span><span class="sxs-lookup"><span data-stu-id="3c57a-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="3c57a-108">Sie können auch die numerische Ausdrücken auf diese Weise vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3c57a-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="3c57a-109">Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke, wie im folgenden Beispiel sein.</span><span class="sxs-lookup"><span data-stu-id="3c57a-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="3c57a-110">Die obige komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="3c57a-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="3c57a-111">Die Ausdrücke auf beiden Seiten des Vergleichsoperators werden ausgewertet, und die resultierenden Werte werden dann verglichen mit der `>=` Vergleichsoperator.</span><span class="sxs-lookup"><span data-stu-id="3c57a-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="3c57a-112">Wenn der Wert des Ausdrucks auf der linken Seite größer als oder gleich dem Wert des Ausdrucks auf der rechten Seite, der gesamte Ausdruck ergibt `True`ist, andernfalls ist er `False`.</span><span class="sxs-lookup"><span data-stu-id="3c57a-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="3c57a-113">Ausdrücke, die Werte zu vergleichen sind am häufigsten in `If...Then` Konstruktionen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c57a-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="3c57a-114">Die `=` Vorzeichen ist, ein Vergleichsoperator als auch ein Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="3c57a-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="3c57a-115">Wenn als Vergleichsoperator verwendet wird, wertet er, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c57a-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="3c57a-116">Sie können auch einen Vergleichsausdruck an einer beliebigen Stelle verwenden eine `Boolean` Wert ist erforderlich, z. B. in einer `If`, `While`, `Loop`, oder `ElseIf` -Anweisung, oder beim Zuweisen oder das Übergeben eines Werts an eine `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="3c57a-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="3c57a-117">Im folgenden Beispiel der von der Vergleichsausdruck zurückgegebene Wert zugewiesen ist eine `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="3c57a-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3c57a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c57a-118">See also</span></span>
- [<span data-ttu-id="3c57a-119">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3c57a-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="3c57a-120">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3c57a-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="3c57a-121">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c57a-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="3c57a-122">Vorgehensweise: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="3c57a-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [<span data-ttu-id="3c57a-123">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c57a-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
