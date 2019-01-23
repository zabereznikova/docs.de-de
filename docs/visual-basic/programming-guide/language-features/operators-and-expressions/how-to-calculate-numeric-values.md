---
title: 'Vorgehensweise: Berechnen von numerischen Werten (Visual Basic)'
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
ms.openlocfilehash: 7bbc3bcadb318203688a3b8ecae18e723e82c8ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560736"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="941bc-102">Vorgehensweise: Berechnen von numerischen Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="941bc-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="941bc-103">Sie können numerische Werte durch die Verwendung von numerischen Ausdrücken berechnen.</span><span class="sxs-lookup"><span data-stu-id="941bc-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="941bc-104">Ein *numerischer Ausdruck* ist ein Ausdruck mit Literalen, Konstanten und Variablen, die Darstellung von numerischer Werten und Operatoren, die für diese Werte dienen.</span><span class="sxs-lookup"><span data-stu-id="941bc-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="941bc-105">Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="941bc-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="941bc-106">Um einen numerischen Wert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="941bc-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="941bc-107">Kombinieren Sie mindestens eine numerischen Literalen, Konstanten und Variablen in einen numerischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="941bc-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="941bc-108">Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="941bc-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="941bc-109">Die ersten drei Zeilen zeigen ein Literal, eine Konstante und einer Variablen.</span><span class="sxs-lookup"><span data-stu-id="941bc-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="941bc-110">Jeder bildet einen gültigen numerischen Ausdruck selbst.</span><span class="sxs-lookup"><span data-stu-id="941bc-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="941bc-111">Die letzte Zeile zeigt eine Kombination aus einer Variablen mit zwei Literale.</span><span class="sxs-lookup"><span data-stu-id="941bc-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="941bc-112">Beachten Sie, dass ein numerischer Ausdruck eine vollständige Visual Basic-Anweisung selbst bilden keine ist.</span><span class="sxs-lookup"><span data-stu-id="941bc-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="941bc-113">Sie müssen den Ausdruck als Teil des eine vollständige Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="941bc-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="941bc-114">Um einen numerischen Wert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="941bc-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="941bc-115">Sie können eine zuweisungsanweisung verwenden, den durch einen numerischen Ausdruck auf eine Variable dargestellten Wert zuweisen, wie im folgende Beispiel wird veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="941bc-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     <span data-ttu-id="941bc-116">Im vorherigen Beispiel den Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators (`=`) der Variablen zugewiesen ist `j` auf der linken Seite des Operators, sodass `j` 276 ergibt.</span><span class="sxs-lookup"><span data-stu-id="941bc-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="941bc-117">Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="941bc-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="941bc-118">Mehrere Operatoren</span><span class="sxs-lookup"><span data-stu-id="941bc-118">Multiple Operators</span></span>  
 <span data-ttu-id="941bc-119">Wenn der numerische Ausdruck mehrere Operatoren enthält, wird die Reihenfolge, in der sie ausgewertet werden, durch die Regeln der Operatorrangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="941bc-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="941bc-120">Um die Regeln der Operatorrangfolge zu überschreiben, müssen Sie die Ausdrücke in Klammern ein, wie im obigen Beispiel; die Ausdrücke ein Klammern werden zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="941bc-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="941bc-121">Überschreiben der normalen Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="941bc-121">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="941bc-122">Verwenden Sie Klammern, um die Vorgänge einzuschließen, die zuerst ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="941bc-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="941bc-123">Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit dem gleichen Operanden und Operatoren.</span><span class="sxs-lookup"><span data-stu-id="941bc-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     <span data-ttu-id="941bc-124">Im vorherigen Beispiel, der Berechnung für `j` der Additionsoperator (`+`) ersten da Klammern `(67 + i)` überschreiben normale Rangfolge und den zugewiesenen Wert `j` 276 (4-Mal so 69) ist.</span><span class="sxs-lookup"><span data-stu-id="941bc-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="941bc-125">Die Berechnung für `k` führt die Operatoren in der normalen Rangfolge (`*` vor `+`), und der zugewiesene Wert `k` ist 270 (268 plus 2).</span><span class="sxs-lookup"><span data-stu-id="941bc-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="941bc-126">Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="941bc-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941bc-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="941bc-127">See also</span></span>
- [<span data-ttu-id="941bc-128">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="941bc-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="941bc-129">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="941bc-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="941bc-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="941bc-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="941bc-131">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="941bc-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="941bc-132">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="941bc-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="941bc-133">Effiziente Kombination von Operatoren</span><span class="sxs-lookup"><span data-stu-id="941bc-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
