---
title: Wertvergleiche
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
ms.openlocfilehash: 01816b5730cf4fda61f1737ce3ce00ab82f57da8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403394"
---
# <a name="value-comparisons-visual-basic"></a><span data-ttu-id="cb6da-102">Wertevergleich (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb6da-102">Value Comparisons (Visual Basic)</span></span>
<span data-ttu-id="cb6da-103">Vergleichs Operatoren können verwendet werden, um Ausdrücke zu erstellen, die die Werte numerischer Variablen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cb6da-103">Comparison operators can be used to construct expressions that compare the values of numeric variables.</span></span> <span data-ttu-id="cb6da-104">Diese Ausdrücke geben einen `Boolean` Wert zurück, der darauf basiert, ob der Vergleich true oder false ist.</span><span class="sxs-lookup"><span data-stu-id="cb6da-104">These expressions return a `Boolean` value based on whether the comparison is true or false.</span></span> <span data-ttu-id="cb6da-105">Beispiele für einen solchen Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="cb6da-105">Examples of such an expression are as follows.</span></span>  
  
 `45 > 26`  
  
 `26 > 45`  
  
 <span data-ttu-id="cb6da-106">Der erste Ausdruck wird zu ausgewertet `True` , da 45 größer als 26 ist.</span><span class="sxs-lookup"><span data-stu-id="cb6da-106">The first expression evaluates to `True`, because 45 is greater than 26.</span></span> <span data-ttu-id="cb6da-107">Im zweiten Beispiel `False` wird als ausgewertet, da 26 nicht größer als 45 ist.</span><span class="sxs-lookup"><span data-stu-id="cb6da-107">The second example evaluates to `False`, because 26 is not greater than 45.</span></span>  
  
 <span data-ttu-id="cb6da-108">Sie können numerische Ausdrücke auch auf diese Weise vergleichen.</span><span class="sxs-lookup"><span data-stu-id="cb6da-108">You can also compare numeric expressions in this fashion.</span></span> <span data-ttu-id="cb6da-109">Die Ausdrücke, die Sie vergleichen, können selbst komplexe Ausdrücke sein, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb6da-109">The expressions you compare can themselves be complex expressions, as in the following example.</span></span>  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 <span data-ttu-id="cb6da-110">Der vorangehende komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="cb6da-110">The preceding complex expression includes literals, variables, and function calls.</span></span> <span data-ttu-id="cb6da-111">Die Ausdrücke auf beiden Seiten des Vergleichs Operators werden ausgewertet, und die resultierenden Werte werden dann mithilfe des `>=` Vergleichs Operators verglichen.</span><span class="sxs-lookup"><span data-stu-id="cb6da-111">The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the `>=` comparison operator.</span></span> <span data-ttu-id="cb6da-112">Wenn der Wert des Ausdrucks auf der linken Seite größer oder gleich dem Wert des Ausdrucks auf der rechten Seite ist, wird der gesamte Ausdruck zu ausgewertet `True` ; andernfalls wird zu ausgewertet `False` .</span><span class="sxs-lookup"><span data-stu-id="cb6da-112">If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to `True`; otherwise, it evaluates to `False`.</span></span>  
  
 <span data-ttu-id="cb6da-113">Ausdrücke, die Werte vergleichen, werden am häufigsten in- `If...Then` Konstruktionen verwendet, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb6da-113">Expressions that compare values are most commonly used in `If...Then` constructions, as in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 <span data-ttu-id="cb6da-114">Das `=` Vorzeichen ist ein Vergleichs Operator und ein Zuweisungs Operator.</span><span class="sxs-lookup"><span data-stu-id="cb6da-114">The `=` sign is a comparison operator as well as an assignment operator.</span></span> <span data-ttu-id="cb6da-115">Wenn es als Vergleichs Operator verwendet wird, wird ausgewertet, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite ist, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb6da-115">When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 <span data-ttu-id="cb6da-116">Sie können auch einen Vergleichs Ausdruck überall dort verwenden `Boolean` , wo ein Wert benötigt wird, z. b. in einer- `If` ,-,-oder- `While` `Loop` `ElseIf` Anweisung, oder wenn Sie einer Variablen einen Wert zuweisen oder einen Wert übergeben `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="cb6da-116">You can also use a comparison expression anywhere a `Boolean` value is needed, such as in an `If`, `While`, `Loop`, or `ElseIf` statement, or when assigning to or passing a value to a `Boolean` variable.</span></span> <span data-ttu-id="cb6da-117">Im folgenden Beispiel wird der vom Vergleichs Ausdruck zurückgegebene Wert einer `Boolean` Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cb6da-117">In the following example, the value returned by the comparison expression is assigned to a `Boolean` variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a><span data-ttu-id="cb6da-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb6da-118">See also</span></span>

- [<span data-ttu-id="cb6da-119">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="cb6da-119">Boolean Expressions</span></span>](boolean-expressions.md)
- [<span data-ttu-id="cb6da-120">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="cb6da-120">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="cb6da-121">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb6da-121">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
- [<span data-ttu-id="cb6da-122">Vorgehensweise: Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="cb6da-122">How to: Calculate Numeric Values</span></span>](how-to-calculate-numeric-values.md)
- [<span data-ttu-id="cb6da-123">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb6da-123">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
