---
title: Operatoren und Ausdrücke
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: fa410a739be2da8802e76a35068448263ddec1fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343612"
---
# <a name="operators-and-expressions-in-visual-basic"></a><span data-ttu-id="2ca86-102">Operatoren und Ausdrücke in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ca86-102">Operators and Expressions in Visual Basic</span></span>
<span data-ttu-id="2ca86-103">Ein *Operator* ist ein Codeelement, das einen Vorgang auf einem oder mehreren Codeelementen ausführt, die Werte halten.</span><span class="sxs-lookup"><span data-stu-id="2ca86-103">An *operator* is a code element that performs an operation on one or more code elements that hold values.</span></span> <span data-ttu-id="2ca86-104">Wertelemente sind unter anderem Variablen, Konstanten, Literale, Eigenschaften, Rückgaben von `Function`- und `Operator`-Prozeduren sowie Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2ca86-104">Value elements include variables, constants, literals, properties, returns from `Function` and `Operator` procedures, and expressions.</span></span>  
  
 <span data-ttu-id="2ca86-105">Ein *Ausdruck* ist eine Serie von Wertelementen, die mit Operatoren kombiniert sind, was einen neuen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="2ca86-105">An *expression* is a series of value elements combined with operators, which yields a new value.</span></span> <span data-ttu-id="2ca86-106">Die Operatoren werden auf den Wertelementen ausgeführt, indem Berechnungen, Vergleiche oder andere Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca86-106">The operators act on the value elements by performing calculations, comparisons, or other operations.</span></span>  
  
## <a name="types-of-operators"></a><span data-ttu-id="2ca86-107">Operatortypen</span><span class="sxs-lookup"><span data-stu-id="2ca86-107">Types of Operators</span></span>  
 <span data-ttu-id="2ca86-108">Visual Basic stellt die folgenden Typen von Operatoren bereit:</span><span class="sxs-lookup"><span data-stu-id="2ca86-108">Visual Basic provides the following types of operators:</span></span>  
  
- <span data-ttu-id="2ca86-109">[Arithmetische Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) führen bekannte Berechnungen auf numerischen Werten aus, einschließlich Verschieben der Bitmuster.</span><span class="sxs-lookup"><span data-stu-id="2ca86-109">[Arithmetic Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) perform familiar calculations on numeric values, including shifting their bit patterns.</span></span>  
  
- <span data-ttu-id="2ca86-110">[Vergleichsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) vergleichen zwei Ausdrücke und geben einen `Boolean`-Wert zurück, der das Ergebnis des Vergleichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ca86-110">[Comparison Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) compare two expressions and return a `Boolean` value representing the result of the comparison.</span></span>  
  
- <span data-ttu-id="2ca86-111">[Verkettungsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) verbinden mehrere Zeichenfolgen zu einer einzelnen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2ca86-111">[Concatenation Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) join multiple strings into a single string.</span></span>  
  
- <span data-ttu-id="2ca86-112">[Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) kombinieren `Boolean` oder numerische Werte und geben ein Ergebnis desselben Datentyps wie die Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="2ca86-112">[Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) combine `Boolean` or numeric values and return a result of the same data type as the values.</span></span>  
  
 <span data-ttu-id="2ca86-113">Die Wertelemente, die mit einem Operator kombiniert sind, werden *Operanden* dieses Operators genannt.</span><span class="sxs-lookup"><span data-stu-id="2ca86-113">The value elements that are combined with an operator are called *operands* of that operator.</span></span> <span data-ttu-id="2ca86-114">Operatoren, die mit Wertelementen kombiniert sind, bilden Ausdrücke. Eine Ausnahme ist der Zuweisungsoperator, der eine *Anweisung* bildet.</span><span class="sxs-lookup"><span data-stu-id="2ca86-114">Operators combined with value elements form expressions, except for the assignment operator, which forms a *statement*.</span></span> <span data-ttu-id="2ca86-115">Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca86-115">For more information, see [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
## <a name="evaluation-of-expressions"></a><span data-ttu-id="2ca86-116">Auswertung von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="2ca86-116">Evaluation of Expressions</span></span>  
 <span data-ttu-id="2ca86-117">Das Endergebnis eines Ausdrucks stellt einen Wert dar, der normalerweise ein bekannter Datentyp ist, z.B. `Boolean`, `String` oder ein numerischer Typ.</span><span class="sxs-lookup"><span data-stu-id="2ca86-117">The end result of an expression represents a value, which is typically of a familiar data type such as `Boolean`, `String`, or a numeric type.</span></span>  
  
 <span data-ttu-id="2ca86-118">Nachstehend sind Beispiele für Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="2ca86-118">The following are examples of expressions.</span></span>  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 <span data-ttu-id="2ca86-119">Einige Operatoren können Aktionen in einzelnen Ausdrücken oder einer Anweisung ausführen, wie das folgende Beispiel darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ca86-119">Several operators can perform actions in a single expression or statement, as the following example illustrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 <span data-ttu-id="2ca86-120">Im vorangehenden Beispiel führt Visual Basic die Vorgänge im Ausdruck auf der rechten Seite des Zuweisungs Operators (`=`) aus und weist dann den resultierenden Wert der Variablen `x` auf der linken Seite zu.</span><span class="sxs-lookup"><span data-stu-id="2ca86-120">In the preceding example, Visual Basic performs the operations in the expression on the right side of the assignment operator (`=`), then assigns the resulting value to the variable `x` on the left.</span></span> <span data-ttu-id="2ca86-121">Es gibt keine festgelegte Einschränkung für die Anzahl der Operatoren, die in einem Ausdruck kombiniert werden können. Jedoch ist es notwendig, die [Operatorrangfolge in Visual Studio](../../../../visual-basic/language-reference/operators/operator-precedence.md) zu verstehen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ca86-121">There is no practical limit to the number of operators that can be combined into an expression, but an understanding of [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) is necessary to ensure that you get the results you expect.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2ca86-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca86-122">See also</span></span>

- [<span data-ttu-id="2ca86-123">Operatoren</span><span class="sxs-lookup"><span data-stu-id="2ca86-123">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="2ca86-124">Effiziente Kombination von Operatoren</span><span class="sxs-lookup"><span data-stu-id="2ca86-124">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="2ca86-125">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="2ca86-125">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
