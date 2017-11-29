---
title: Wertevergleich (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c11f12bbaf261c0853e96802f03322c5e7fdc706
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="843d5-102">Wertevergleich (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="843d5-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="843d5-103">Vergleichsoperatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte von numerischen Variablen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="843d5-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="843d5-104">Diese Ausdrücke Zurückgeben einer `Boolean` Wert basierend darauf, ob der Vergleich "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="843d5-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="843d5-105">Beispiele für ein solcher Ausdruck sind wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="843d5-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="843d5-106">Der erste Ausdruck wird zu `True`, weil 45 größer als 26 ist.</span><span class="sxs-lookup"><span data-stu-id="843d5-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="843d5-107">Im zweite Beispiel ergibt `False`, da 26 nicht größer als 45 befindet.</span><span class="sxs-lookup"><span data-stu-id="843d5-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="843d5-108">Sie können auch numerische Ausdrücke auf diese Weise vergleichen.</span><span class="sxs-lookup"><span data-stu-id="843d5-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="843d5-109">Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke, wie im folgenden Beispiel werden.</span><span class="sxs-lookup"><span data-stu-id="843d5-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="843d5-110">Die vorangehende komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="843d5-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="843d5-111">Die Ausdrücke auf beiden Seiten des Vergleichsoperators werden ausgewertet, und die erhaltenen Werte werden dann einem Vergleich unter Verwendung der `>=` Vergleichsoperator.</span><span class="sxs-lookup"><span data-stu-id="843d5-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="843d5-112">Wenn der Wert des Ausdrucks auf der linken Seite größer als oder gleich dem Wert des Ausdrucks auf der rechten Seite, der gesamte Ausdruck wird zu `True`ist, andernfalls ist er `False`.</span><span class="sxs-lookup"><span data-stu-id="843d5-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="843d5-113">Ausdrücke, die Werte verglichen werden am häufigsten `If...Then` Konstruktionen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="843d5-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 <span data-ttu-id="843d5-114">Die `=` Anmeldung ist ein Vergleichsoperator sowie ein Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="843d5-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="843d5-115">Wenn als Vergleichsoperator verwendet wird, wertet ihn an, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="843d5-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 <span data-ttu-id="843d5-116">Sie können auch einen Vergleichsausdruck verwenden, an einer beliebigen Stelle ein `Boolean` Wert ist erforderlich, z. B. in einer `If`, `While`, `Loop`, oder `ElseIf` -Anweisung, oder beim Zuweisen oder zum Übergeben eines Werts an eine `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="843d5-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="843d5-117">Im folgenden Beispiel durch den Vergleichsausdruck zurückgegebene Wert zugewiesen wird eine `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="843d5-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="843d5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="843d5-118">See Also</span></span>  
 [<span data-ttu-id="843d5-119">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="843d5-119">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="843d5-120">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="843d5-120">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="843d5-121">Vergleichsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="843d5-121">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="843d5-122">Gewusst wie: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="843d5-122">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="843d5-123">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="843d5-123">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
