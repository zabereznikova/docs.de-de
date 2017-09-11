---
title: 'Gewusst wie: Berechnen von numerischen Werten (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe781cca8f716c792d3af153b2004c716bc87f90
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="f9032-102">Gewusst wie: Berechnen von numerischen Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9032-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="f9032-103">Sie können numerische Werte mithilfe von numerischen Ausdrücken berechnen.</span><span class="sxs-lookup"><span data-stu-id="f9032-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="f9032-104">Ein *numerischen Ausdruck* ist ein Ausdruck, der literalen, Konstanten und Variablen, die numerische Werte enthält und Operatoren, die für diese Werte fungieren.</span><span class="sxs-lookup"><span data-stu-id="f9032-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="f9032-105">Berechnen von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="f9032-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="f9032-106">Um einen numerischen Wert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="f9032-106">To calculate a numeric value</span></span>  
  
-   <span data-ttu-id="f9032-107">Kombinieren Sie einen oder mehrere numerischen Literalen, Konstanten und Variablen in einem numerischen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f9032-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="f9032-108">Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="f9032-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="f9032-109">Die ersten drei Zeilen enthalten ein Literal, eine Konstante und einer Variable.</span><span class="sxs-lookup"><span data-stu-id="f9032-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="f9032-110">Jede bildet einen gültigen numerischen Ausdruck selbst.</span><span class="sxs-lookup"><span data-stu-id="f9032-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="f9032-111">Die letzte Zeile zeigt eine Kombination einer Variablen mit zwei Literalen.</span><span class="sxs-lookup"><span data-stu-id="f9032-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="f9032-112">Beachten Sie, dass ein numerisches Ausdrucks keine vollständige bilden [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisung selbst.</span><span class="sxs-lookup"><span data-stu-id="f9032-112">Note that a numeric expression does not form a complete [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statement by itself.</span></span> <span data-ttu-id="f9032-113">Sie müssen den Ausdruck als Teil einer vollständigen Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f9032-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="f9032-114">Um einen numerischen Wert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f9032-114">To store a numeric value</span></span>  
  
-   <span data-ttu-id="f9032-115">Eine Zuweisung können durch einen numerischen Ausdruck einer Variablen dargestellten Wert zuweisen, wie im folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f9032-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     <span data-ttu-id="f9032-116">[!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f9032-116">[!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]</span></span>  
  
     <span data-ttu-id="f9032-117">Im vorherigen Beispiel den Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators (`=`) der Variablen zugewiesen `j` auf der linken Seite des Operators, damit `j` 276 ergibt.</span><span class="sxs-lookup"><span data-stu-id="f9032-117">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="f9032-118">Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="f9032-118">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="f9032-119">Mehrere Operatoren</span><span class="sxs-lookup"><span data-stu-id="f9032-119">Multiple Operators</span></span>  
 <span data-ttu-id="f9032-120">Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge, die Auswertung, durch die Regeln der Operatorrangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f9032-120">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="f9032-121">Um die Regeln der Operatorrangfolge überschreiben möchten, müssen Sie Ausdrücke in Klammern, wie im obigen Beispiel; die Ausdrücke ein Klammern werden zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f9032-121">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="f9032-122">Normale Operatorrangfolge überschreiben</span><span class="sxs-lookup"><span data-stu-id="f9032-122">To override normal operator precedence</span></span>  
  
-   <span data-ttu-id="f9032-123">Verwenden Sie Klammern, die Vorgänge einschließen, zuerst ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9032-123">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="f9032-124">Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit den gleichen Operanden und Operatoren.</span><span class="sxs-lookup"><span data-stu-id="f9032-124">The following example shows two different results with the same operands and operators.</span></span>  
  
     <span data-ttu-id="f9032-125">[!code-vb[VbVbalrOperators&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f9032-125">[!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]</span></span>  
  
     <span data-ttu-id="f9032-126">Im vorhergehenden Beispiel die Berechnung für `j` der Additionsoperator (`+`) erste da Klammern `(67 + i)` überschreiben normale Rangfolge und den zugewiesenen Wert `j` ist 276 (4 Mal 69).</span><span class="sxs-lookup"><span data-stu-id="f9032-126">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="f9032-127">Die Berechnung für `k` führt die Operatoren in der normalen Rangfolge (`*` vor `+`), und den zugewiesenen Wert `k` ist 270 (268 plus 2).</span><span class="sxs-lookup"><span data-stu-id="f9032-127">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="f9032-128">Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="f9032-128">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9032-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9032-129">See Also</span></span>  
 <span data-ttu-id="f9032-130">[Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9032-130">[Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="f9032-131"> [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="f9032-131"> [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="f9032-132"> [Anweisungen](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="f9032-132"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="f9032-133"> [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="f9032-133"> [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="f9032-134"> [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="f9032-134"> [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="f9032-135"> [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="f9032-135"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
