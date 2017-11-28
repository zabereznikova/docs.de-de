---
title: Operator Mod(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="6c90e-102">Operator Mod(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c90e-102">Mod Operator (Visual Basic)</span></span>
<span data-ttu-id="6c90e-103">Dividiert zwei Zahlen und gibt nur den Restwert zurück.</span><span class="sxs-lookup"><span data-stu-id="6c90e-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c90e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c90e-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="6c90e-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6c90e-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="6c90e-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6c90e-106">Required.</span></span> <span data-ttu-id="6c90e-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6c90e-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="6c90e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6c90e-108">Required.</span></span> <span data-ttu-id="6c90e-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6c90e-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="6c90e-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="6c90e-110">Supported Types</span></span>  
 <span data-ttu-id="6c90e-111">Alle numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="6c90e-111">All numeric types.</span></span> <span data-ttu-id="6c90e-112">Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="6c90e-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="6c90e-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="6c90e-113">Result</span></span>  
 <span data-ttu-id="6c90e-114">Das Ergebnis wird im weiteren Verlauf nach `number1` wird geteilt durch `number2`.</span><span class="sxs-lookup"><span data-stu-id="6c90e-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="6c90e-115">Z. B. der Ausdruck `14 Mod 4` 2 ergibt.</span><span class="sxs-lookup"><span data-stu-id="6c90e-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c90e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c90e-116">Remarks</span></span>  
 <span data-ttu-id="6c90e-117">Wenn entweder `number1` oder `number2` ist der Wert ein Gleitkommazahl der Gleitkommarest der Division wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c90e-117">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="6c90e-118">Der Datentyp des Ergebnisses ist der kleinste Datentyp, die alle möglichen Werte enthalten kann, die aus der Division mit den Datentypen der resultieren `number1` und `number2`.</span><span class="sxs-lookup"><span data-stu-id="6c90e-118">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="6c90e-119">Wenn `number1` oder `number2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird dies als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="6c90e-119">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="6c90e-120">Verwandte Operatoren umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6c90e-120">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="6c90e-121">Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück.</span><span class="sxs-lookup"><span data-stu-id="6c90e-121">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="6c90e-122">Z. B. der Ausdruck `14 \ 4` 3 ergibt.</span><span class="sxs-lookup"><span data-stu-id="6c90e-122">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="6c90e-123">Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten, einschließlich des Restes, als Gleitkommazahl zurück.</span><span class="sxs-lookup"><span data-stu-id="6c90e-123">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="6c90e-124">Z. B. der Ausdruck `14 / 4` 3.5 ergibt.</span><span class="sxs-lookup"><span data-stu-id="6c90e-124">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="6c90e-125">Versuchte Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="6c90e-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="6c90e-126">Wenn `number2` ergibt 0 (null), das Verhalten der `Mod` Operator hängt von den Datentyp des Operanden.</span><span class="sxs-lookup"><span data-stu-id="6c90e-126">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="6c90e-127">Ganzzahldivision wird eine <xref:System.DivideByZeroException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6c90e-127">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="6c90e-128">Gibt eine Gleitkommadivision <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="6c90e-128">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="6c90e-129">Entsprechende Formel</span><span class="sxs-lookup"><span data-stu-id="6c90e-129">Equivalent Formula</span></span>  
 <span data-ttu-id="6c90e-130">Der Ausdruck `a Mod b` ist gleichbedeutend mit beiden der folgenden Formeln:</span><span class="sxs-lookup"><span data-stu-id="6c90e-130">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="6c90e-131">Gleitkomma Ungenauigkeit</span><span class="sxs-lookup"><span data-stu-id="6c90e-131">Floating-Point Imprecision</span></span>  
 <span data-ttu-id="6c90e-132">Wenn Sie mit Gleitkommazahlen arbeiten, denken Sie daran, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c90e-132">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="6c90e-133">Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und `Mod` Operator.</span><span class="sxs-lookup"><span data-stu-id="6c90e-133">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="6c90e-134">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="6c90e-134">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6c90e-135">Überladen</span><span class="sxs-lookup"><span data-stu-id="6c90e-135">Overloading</span></span>  
 <span data-ttu-id="6c90e-136">Die `Mod` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann.</span><span class="sxs-lookup"><span data-stu-id="6c90e-136">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="6c90e-137">Wenn Ihr Code wendet `Mod` mit einer Instanz einer Klasse oder Struktur, die eine Überladung verwendet wird, werden Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="6c90e-137">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6c90e-138">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6c90e-138">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c90e-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c90e-139">Example</span></span>  
 <span data-ttu-id="6c90e-140">Im folgenden Beispiel wird die `Mod` Operator, um zwei Zahlen dividiert, und geben Sie nur den Restwert zurück.</span><span class="sxs-lookup"><span data-stu-id="6c90e-140">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="6c90e-141">Wenn entweder eine Gleitkommazahl ist, ist das Ergebnis eine Gleitkommazahl, die den Rest darstellt.</span><span class="sxs-lookup"><span data-stu-id="6c90e-141">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="6c90e-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6c90e-142">Example</span></span>  
 <span data-ttu-id="6c90e-143">Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden.</span><span class="sxs-lookup"><span data-stu-id="6c90e-143">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="6c90e-144">In der ersten Anweisung den Operanden sind `Double`, und 0,2 ist ein unendlicher Binärbruch mit dem gespeicherten Wert 0,20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="6c90e-144">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="6c90e-145">In der zweiten Anweisung wird das Literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung.</span><span class="sxs-lookup"><span data-stu-id="6c90e-145">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6c90e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c90e-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="6c90e-147">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="6c90e-147">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="6c90e-148">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c90e-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="6c90e-149">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="6c90e-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="6c90e-150">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="6c90e-150">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="6c90e-151">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6c90e-151">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="6c90e-152">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c90e-152">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
