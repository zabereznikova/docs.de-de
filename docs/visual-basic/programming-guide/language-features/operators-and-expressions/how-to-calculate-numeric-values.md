---
title: 'Vorgehensweise: Berechnen von numerischen Werten'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 452a8392b46f0c25b6ad2a8a30c51071f2ae1d93
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071715"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="f5ef9-102">Gewusst wie: Berechnen von numerischen Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5ef9-102">How to: Calculate Numeric Values (Visual Basic)</span></span>

<span data-ttu-id="f5ef9-103">Numerische Werte können mithilfe numerischer Ausdrücke berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="f5ef9-104">Ein *numerischer Ausdruck* ist ein Ausdruck, der Literale, Konstanten und Variablen, die numerische Werte darstellen, sowie Operatoren enthält, die auf diese Werte reagieren.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="f5ef9-105">Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="f5ef9-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="f5ef9-106">So berechnen Sie einen numerischen Wert</span><span class="sxs-lookup"><span data-stu-id="f5ef9-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="f5ef9-107">Kombinieren Sie eine oder mehrere numerische Literale, Konstanten und Variablen in einem numerischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="f5ef9-108">Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="f5ef9-109">In den ersten drei Zeilen wird ein Literalwert, eine Konstante und eine Variable angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="f5ef9-110">Jede ist ein gültiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="f5ef9-111">In der letzten Zeile wird eine Kombination aus einer Variablen mit zwei literalen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="f5ef9-112">Beachten Sie, dass ein numerischer Ausdruck nicht über eine komplette Visual Basic-Anweisung verfügt.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="f5ef9-113">Sie müssen den Ausdruck als Teil einer Complete-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="f5ef9-114">So speichern Sie einen numerischen Wert</span><span class="sxs-lookup"><span data-stu-id="f5ef9-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="f5ef9-115">Sie können eine Zuweisungsanweisung verwenden, um den von einem numerischen Ausdruck dargestellten Wert einer Variablen zuzuweisen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="f5ef9-116">Im vorangehenden Beispiel wird der Wert des Ausdrucks auf der rechten Seite des Gleichheits Operators ( `=` ) der Variablen `j` auf der linken Seite des Operators zugewiesen, daher ergibt den Wert `j` 276.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="f5ef9-117">Weitere Informationen finden Sie unter [Transact-SQL-Anweisungen](../../../language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f5ef9-117">For more information, see [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="f5ef9-118">Mehrere Operatoren</span><span class="sxs-lookup"><span data-stu-id="f5ef9-118">Multiple Operators</span></span>  

 <span data-ttu-id="f5ef9-119">Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge, in der Sie ausgewertet werden, durch die Regeln der Operator Rangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="f5ef9-120">Um die Regeln der Operator Rangfolge zu überschreiben, schließen Sie Ausdrücke in Klammern ein, wie im obigen Beispiel gezeigt. die eingeschlossenen Ausdrücke werden zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="f5ef9-121">So überschreiben Sie normale Operator Rangfolge</span><span class="sxs-lookup"><span data-stu-id="f5ef9-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="f5ef9-122">Verwenden Sie Klammern, um die Vorgänge, die zuerst ausgeführt werden sollen, einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="f5ef9-123">Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit denselben Operanden und Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f5ef9-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="f5ef9-124">Im vorherigen Beispiel führt die Berechnung für `j` den Additions Operator ( `+` ) zuerst aus, da die Klammern um die `(67 + i)` normale Rangfolge überschreiben, und der zugewiesene Wert `j` ist 276 (4 mal 69).</span><span class="sxs-lookup"><span data-stu-id="f5ef9-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="f5ef9-125">Die Berechnung für `k` führt die Operatoren in ihrer normalen Rangfolge ( `*` vor `+` ) aus, und der zugewiesene Wert `k` ist 270 (268 plus 2).</span><span class="sxs-lookup"><span data-stu-id="f5ef9-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="f5ef9-126">Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f5ef9-126">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ef9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5ef9-127">See also</span></span>

- [<span data-ttu-id="f5ef9-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f5ef9-128">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="f5ef9-129">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="f5ef9-129">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="f5ef9-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="f5ef9-130">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="f5ef9-131">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5ef9-131">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f5ef9-132">Arithmetic Operators (Arithmetische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="f5ef9-132">Arithmetic Operators</span></span>](../../../language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f5ef9-133">Effiziente Kombination von Operatoren</span><span class="sxs-lookup"><span data-stu-id="f5ef9-133">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
