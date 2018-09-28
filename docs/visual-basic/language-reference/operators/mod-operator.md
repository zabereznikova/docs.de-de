---
title: Operator Mod(Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 456c19fc8e28517a0662b58e338028e1c75cd8c8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424401"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="5f71d-102">MOD-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f71d-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="5f71d-103">Dividiert zwei Zahlen und gibt nur den Restwert zurück.</span><span class="sxs-lookup"><span data-stu-id="5f71d-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f71d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f71d-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="5f71d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="5f71d-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="5f71d-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f71d-106">Required.</span></span> <span data-ttu-id="5f71d-107">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5f71d-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="5f71d-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f71d-108">Required.</span></span> <span data-ttu-id="5f71d-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="5f71d-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="5f71d-110">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="5f71d-110">Supported types</span></span>  
 <span data-ttu-id="5f71d-111">Alle numerischen Typen.</span><span class="sxs-lookup"><span data-stu-id="5f71d-111">All numeric types.</span></span> <span data-ttu-id="5f71d-112">Dazu gehören auch die Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5f71d-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="5f71d-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="5f71d-113">Result</span></span>

<span data-ttu-id="5f71d-114">Das Ergebnis ist der Rest nach der `number1` wird geteilt durch `number2`.</span><span class="sxs-lookup"><span data-stu-id="5f71d-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="5f71d-115">Beispiel: der Ausdruck `14 Mod 4` 2 ergibt.</span><span class="sxs-lookup"><span data-stu-id="5f71d-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="5f71d-116">Es gibt einen Unterschied zwischen *Rest* und *Modulo* in der Mathematik mit unterschiedlichen Ergebnissen für negative Zahlen.</span><span class="sxs-lookup"><span data-stu-id="5f71d-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="5f71d-117">Die `Mod` -Operator in Visual Basic .NET Framework `op_Modulus` Operator und den zugrunde liegenden [Rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL-Anweisung, die alle einen Remainder-Vorgang ausführen.</span><span class="sxs-lookup"><span data-stu-id="5f71d-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="5f71d-118">Das Ergebnis einer `Mod` Vorgang behält die Vorzeichen des Divisors, `number1`, und daher positiv oder negativ sein.</span><span class="sxs-lookup"><span data-stu-id="5f71d-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="5f71d-119">Das Ergebnis ist immer im Bereich (-`number2`, `number2`), exklusive.</span><span class="sxs-lookup"><span data-stu-id="5f71d-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="5f71d-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5f71d-120">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="5f71d-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f71d-121">Remarks</span></span>  
 <span data-ttu-id="5f71d-122">Wenn entweder `number1` oder `number2` ist ein Gleitkommawert, der Gleitkommarest von der Abteilung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f71d-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="5f71d-123">Der Datentyp des Ergebnisses ist den kleinsten Datentyp, die alle möglichen Werte enthalten kann, die aus der Division mit den Datentypen der führen `number1` und `number2`.</span><span class="sxs-lookup"><span data-stu-id="5f71d-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="5f71d-124">Wenn `number1` oder `number2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="5f71d-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="5f71d-125">Die folgenden: zugehörige Operatoren</span><span class="sxs-lookup"><span data-stu-id="5f71d-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="5f71d-126">Die [\-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück.</span><span class="sxs-lookup"><span data-stu-id="5f71d-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="5f71d-127">Beispiel: der Ausdruck `14 \ 4` 3 ergibt.</span><span class="sxs-lookup"><span data-stu-id="5f71d-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="5f71d-128">Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt zurück, der volle Quotient, einschließlich den Rest als Gleitkommazahl.</span><span class="sxs-lookup"><span data-stu-id="5f71d-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="5f71d-129">Beispiel: der Ausdruck `14 / 4` 3.5 ergibt.</span><span class="sxs-lookup"><span data-stu-id="5f71d-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="5f71d-130">Versuchte Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="5f71d-130">Attempted division by zero</span></span>  
 <span data-ttu-id="5f71d-131">Wenn `number2` ergibt NULL, das Verhalten der `Mod` Operator hängt von den Datentyp des Operanden.</span><span class="sxs-lookup"><span data-stu-id="5f71d-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="5f71d-132">Ganzzahldivision wird eine <xref:System.DivideByZeroException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="5f71d-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="5f71d-133">Gibt eine Gleitkommadivision <xref:System.Double.NaN>.</span><span class="sxs-lookup"><span data-stu-id="5f71d-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="5f71d-134">Gleichwertigen Formel</span><span class="sxs-lookup"><span data-stu-id="5f71d-134">Equivalent formula</span></span>  
 <span data-ttu-id="5f71d-135">Der Ausdruck `a Mod b` ist gleichbedeutend mit einer der folgenden Formeln:</span><span class="sxs-lookup"><span data-stu-id="5f71d-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="5f71d-136">Gleitkomma Ungenauigkeit</span><span class="sxs-lookup"><span data-stu-id="5f71d-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="5f71d-137">Beim Arbeiten mit Gleitkommazahlen, denken Sie daran, dass sie nicht immer eine genaue dezimale Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="5f71d-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="5f71d-138">Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator.</span><span class="sxs-lookup"><span data-stu-id="5f71d-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="5f71d-139">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5f71d-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5f71d-140">Überladen</span><span class="sxs-lookup"><span data-stu-id="5f71d-140">Overloading</span></span>  
 <span data-ttu-id="5f71d-141">Die `Mod` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann.</span><span class="sxs-lookup"><span data-stu-id="5f71d-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="5f71d-142">Wenn Ihr Code gilt `Mod` mit einer Instanz einer Klasse oder Struktur, die solche eine Überladung umfasst, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="5f71d-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5f71d-143">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5f71d-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f71d-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f71d-144">Example</span></span>  
 <span data-ttu-id="5f71d-145">Im folgenden Beispiel wird die `Mod` Operator, um zwei Zahlen dividiert, und nur den Rest zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5f71d-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="5f71d-146">Wenn entweder Anzahl eine Gleitkommazahl ist, ist das Ergebnis eine Gleitkommazahl, die den Rest darstellt.</span><span class="sxs-lookup"><span data-stu-id="5f71d-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5f71d-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f71d-147">Example</span></span>  
 <span data-ttu-id="5f71d-148">Das folgende Beispiel zeigt die potenzielle Ungenauigkeit der Gleitkomma-Operanden.</span><span class="sxs-lookup"><span data-stu-id="5f71d-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="5f71d-149">In der ersten Anweisung, die Operanden sind `Double`, 0,2 ist ein unendlich Binärbruch mit dem gespeicherten Wert 0,20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="5f71d-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="5f71d-150">In der zweiten Anweisung, das Literal-Typzeichen `D` erzwingt, dass beide Operanden `Decimal`, und 0,2 verfügt über eine genaue Darstellung.</span><span class="sxs-lookup"><span data-stu-id="5f71d-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5f71d-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f71d-151">See also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="5f71d-152">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="5f71d-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="5f71d-153">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f71d-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5f71d-154">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="5f71d-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5f71d-155">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="5f71d-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="5f71d-156">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f71d-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="5f71d-157">\-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f71d-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
