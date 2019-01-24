---
title: '\-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: ac306038aefba4ca0e0f13fa2945d01c27c0804d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654684"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="00abc-102">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00abc-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="00abc-103">Dividiert zwei Zahlen und gibt ein ganzzahliges Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="00abc-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00abc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00abc-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="00abc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="00abc-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="00abc-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00abc-106">Required.</span></span> <span data-ttu-id="00abc-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="00abc-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="00abc-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00abc-108">Required.</span></span> <span data-ttu-id="00abc-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="00abc-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="00abc-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="00abc-110">Supported Types</span></span>  
 <span data-ttu-id="00abc-111">Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="00abc-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="00abc-112">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="00abc-112">Result</span></span>  
 <span data-ttu-id="00abc-113">Das Ergebnis ist der ganzzahlige Quotient aus `expression1` geteilt durch `expression2`, der Rest wird verworfen, und nur den ganzzahlige Teil beibehalten.</span><span class="sxs-lookup"><span data-stu-id="00abc-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="00abc-114">Dies bezeichnet man als *Abschneiden*.</span><span class="sxs-lookup"><span data-stu-id="00abc-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="00abc-115">Der Ergebniswert vom Datentyp eines numerischen Typs, die für die Datentypen der entsprechenden `expression1` und `expression2`.</span><span class="sxs-lookup"><span data-stu-id="00abc-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="00abc-116">Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="00abc-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="00abc-117">Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt zurück, der volle Quotient, der den Rest in der Bruchteil den Teil enthält.</span><span class="sxs-lookup"><span data-stu-id="00abc-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00abc-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00abc-118">Remarks</span></span>  
 <span data-ttu-id="00abc-119">Ausführen der Division Visual Basic-Versuche vor dem Konvertieren Sie einen numerischen Gleitkommaausdruck, `Long`.</span><span class="sxs-lookup"><span data-stu-id="00abc-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="00abc-120">Wenn `Option Strict` ist `On`, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="00abc-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="00abc-121">Wenn `Option Strict` ist `Off`, <xref:System.OverflowException> ist möglich, wenn der Wert außerhalb des Bereichs von ist das [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="00abc-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="00abc-122">Die Konvertierung in `Long` kann auch *Banker rounding*.</span><span class="sxs-lookup"><span data-stu-id="00abc-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="00abc-123">Weitere Informationen finden Sie unter "Nachkommastellen" in [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="00abc-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="00abc-124">Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="00abc-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="00abc-125">Versuchte Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="00abc-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="00abc-126">Wenn `expression2` ergibt 0 (null), die `\` löst der Operator ein <xref:System.DivideByZeroException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="00abc-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="00abc-127">Dies gilt auch für alle numerischen Datentypen der Operanden.</span><span class="sxs-lookup"><span data-stu-id="00abc-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00abc-128">Die `\` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="00abc-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="00abc-129">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="00abc-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="00abc-130">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="00abc-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00abc-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00abc-131">Example</span></span>  
 <span data-ttu-id="00abc-132">Im folgenden Beispiel wird die `\` Operator, um eine Ganzzahldivision ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="00abc-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="00abc-133">Das Ergebnis ist eine ganze Zahl, die den Quotienten ganze Zahl, der zwei Operanden, mit der Rest verworfen darstellt.</span><span class="sxs-lookup"><span data-stu-id="00abc-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 <span data-ttu-id="00abc-134">Die Ausdrücke im vorhergehenden Beispiel geben die Werte von 2, 3, 33 und-22, bzw. zurück.</span><span class="sxs-lookup"><span data-stu-id="00abc-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00abc-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00abc-135">See also</span></span>
- [<span data-ttu-id="00abc-136">\\= Operator</span><span class="sxs-lookup"><span data-stu-id="00abc-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="00abc-137">/-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00abc-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="00abc-138">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="00abc-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="00abc-139">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="00abc-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="00abc-140">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00abc-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="00abc-141">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="00abc-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="00abc-142">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00abc-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
