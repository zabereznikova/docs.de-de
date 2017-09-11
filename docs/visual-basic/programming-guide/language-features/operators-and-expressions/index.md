---
title: "Operatoren und Ausdrücke in Visual Basic"
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
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands, definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3675af3ac8a0a80b5fb5f208c1679dc28ab77acf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="c46ca-102">Operatoren und Ausdrücke in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c46ca-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="c46ca-103">Ein *Operator* ist ein Codeelement, das einen Vorgang auf einem oder mehreren Codeelementen ausführt, die Werte halten.</span><span class="sxs-lookup"><span data-stu-id="c46ca-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="c46ca-104">Wertelemente sind unter anderem Variablen, Konstanten, Literale, Eigenschaften, Rückgaben von `Function`- und `Operator`-Prozeduren sowie Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c46ca-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="c46ca-105">Ein *Ausdruck* ist eine Serie von Wertelementen, die mit Operatoren kombiniert sind, was einen neuen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="c46ca-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="c46ca-106">Die Operatoren werden auf den Wertelementen ausgeführt, indem Berechnungen, Vergleiche oder andere Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c46ca-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="c46ca-107">Arten von Operatoren</span><span class="sxs-lookup"><span data-stu-id="c46ca-107">Types of Operators</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="c46ca-108"> stellt folgende Arten von Operatoren bereit:</span><span class="sxs-lookup"><span data-stu-id="c46ca-108"> provides the following types of operators:</span></span>  
  
-   <span data-ttu-id="c46ca-109">[Arithmetische Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) führen bekannte Berechnungen auf numerischen Werten aus, einschließlich Verschieben der Bitmuster.</span><span class="sxs-lookup"><span data-stu-id="c46ca-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
-   <span data-ttu-id="c46ca-110">[Vergleichsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) vergleichen zwei Ausdrücke und geben einen `Boolean`-Wert zurück, der das Ergebnis des Vergleichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="c46ca-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
-   <span data-ttu-id="c46ca-111">[Verkettungsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c46ca-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
-   <span data-ttu-id="c46ca-112">[Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) kombinieren `Boolean` oder numerische Werte und geben ein Ergebnis desselben Datentyps wie die Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="c46ca-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="c46ca-113">Die Wertelemente, die mit einem Operator kombiniert sind, werden *Operanden* dieses Operators genannt.</span><span class="sxs-lookup"><span data-stu-id="c46ca-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="c46ca-114">Operatoren, die mit Wertelementen kombiniert sind, bilden Ausdrücke. Eine Ausnahme ist der Zuweisungsoperator, der eine *Anweisung* bildet.</span><span class="sxs-lookup"><span data-stu-id="c46ca-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="c46ca-115">Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="c46ca-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="c46ca-116">Auswertung von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="c46ca-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="c46ca-117">Das Endergebnis eines Ausdrucks stellt einen Wert dar, der normalerweise ein bekannter Datentyp ist, z.B. `Boolean`, `String` oder ein numerischer Typ.</span><span class="sxs-lookup"><span data-stu-id="c46ca-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="c46ca-118">Nachstehend sind Beispiele für Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c46ca-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="c46ca-119">Einige Operatoren können Aktionen in einzelnen Ausdrücken oder einer Anweisung ausführen, wie das folgende Beispiel darstellt.</span><span class="sxs-lookup"><span data-stu-id="c46ca-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 <span data-ttu-id="c46ca-120">[!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c46ca-120">[!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
 <span data-ttu-id="c46ca-121">Im vorhergehenden Beispiel führt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die Vorgänge im Ausdruck auf der rechten Seite des Zuweisungsoperators (`=`) aus und weist den ergebenden Wert dann der Variable `x` auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="c46ca-121">In the preceding example, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="c46ca-122">Es gibt keine festgelegte Einschränkung für die Anzahl der Operatoren, die in einem Ausdruck kombiniert werden können. Jedoch ist es notwendig, die [Operatorrangfolge in Visual Studio](../../../../visual-basic/language-reference/operators/operator-precedence.md) zu verstehen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="c46ca-122">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  
  
 <span data-ttu-id="c46ca-123">Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005 (Operatorüberladung in Visual Basic 2005)](http://go.microsoft.com/fwlink/?LinkId=101703).</span><span class="sxs-lookup"><span data-stu-id="c46ca-123">For more information and examples, see [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46ca-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c46ca-124">See Also</span></span>  
 <span data-ttu-id="c46ca-125">[Operatoren](../../../../visual-basic/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c46ca-125">[Operators](../../../../visual-basic/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="c46ca-126">[Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md) </span><span class="sxs-lookup"><span data-stu-id="c46ca-126">[Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md) </span></span>  
 [<span data-ttu-id="c46ca-127">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="c46ca-127">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)

