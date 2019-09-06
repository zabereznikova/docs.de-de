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
ms.openlocfilehash: dc1e866836bb7420ffe17210b5be7a5e1d4048d0
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374493"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="11754-102">Mod-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11754-102">Mod operator (Visual Basic)</span></span>

<span data-ttu-id="11754-103">Dividiert zwei Zahlen und gibt nur den Rest zurück.</span><span class="sxs-lookup"><span data-stu-id="11754-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="11754-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11754-104">Syntax</span></span>

```vb
result = number1 Mod number2
```

## <a name="parts"></a><span data-ttu-id="11754-105">Teile</span><span class="sxs-lookup"><span data-stu-id="11754-105">Parts</span></span>

`result` \
<span data-ttu-id="11754-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11754-106">Required.</span></span> <span data-ttu-id="11754-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11754-107">Any numeric variable or property.</span></span>

`number1` \
<span data-ttu-id="11754-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11754-108">Required.</span></span> <span data-ttu-id="11754-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="11754-109">Any numeric expression.</span></span>

`number2` \
<span data-ttu-id="11754-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11754-110">Required.</span></span> <span data-ttu-id="11754-111">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="11754-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="11754-112">Unterstützte Typen</span><span class="sxs-lookup"><span data-stu-id="11754-112">Supported types</span></span>

<span data-ttu-id="11754-113">allen numerischen Typen</span><span class="sxs-lookup"><span data-stu-id="11754-113">All numeric types.</span></span> <span data-ttu-id="11754-114">Dies schließt die unsignierten-und Gleit Komma Typen `Decimal`und ein.</span><span class="sxs-lookup"><span data-stu-id="11754-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="11754-115">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="11754-115">Result</span></span>

<span data-ttu-id="11754-116">Das Ergebnis ist der Rest, `number1` nachdem durch dividiert wurde. `number2`</span><span class="sxs-lookup"><span data-stu-id="11754-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="11754-117">Beispielsweise wird der Ausdruck `14 Mod 4` zu 2 ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="11754-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="11754-118">Es gibt einen Unterschied zwischen *Rest* und *Modulo* in der Mathematik mit unterschiedlichen Ergebnissen für negative Zahlen.</span><span class="sxs-lookup"><span data-stu-id="11754-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="11754-119">Der `Mod` Operator in Visual Basic, der .NET Framework `op_Modulus` -Operator und die zugrunde liegende [REM](<xref:System.Reflection.Emit.OpCodes.Rem>) Il-Anweisung führen einen Rest-Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="11754-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="11754-120">Das Ergebnis eines `Mod` -Vorgangs behält das Vorzeichen der `number1`Dividende bei, und es kann positiv oder negativ sein.</span><span class="sxs-lookup"><span data-stu-id="11754-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="11754-121">Das Ergebnis liegt immer im Bereich (-`number2`, `number2`), exklusiv.</span><span class="sxs-lookup"><span data-stu-id="11754-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="11754-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="11754-122">For example:</span></span>

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

## <a name="remarks"></a><span data-ttu-id="11754-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11754-123">Remarks</span></span>

<span data-ttu-id="11754-124">Wenn entweder `number1` oder `number2` ein Gleit Komma Wert ist, wird der Rest der Division zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="11754-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="11754-125">Der Datentyp des Ergebnisses ist der kleinste Datentyp, der alle möglichen Werte enthalten kann, die sich aus der Division mit den Daten `number1` Typen `number2`und ergeben.</span><span class="sxs-lookup"><span data-stu-id="11754-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

<span data-ttu-id="11754-126">Wenn `number1` oder`number2` als " [Nothing](../../../visual-basic/language-reference/nothing.md)" ausgewertet wird, wird es als 0 (null) behandelt.</span><span class="sxs-lookup"><span data-stu-id="11754-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

<span data-ttu-id="11754-127">Verwandte Operatoren umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="11754-127">Related operators include the following:</span></span>

- <span data-ttu-id="11754-128">Der [Operator \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück.</span><span class="sxs-lookup"><span data-stu-id="11754-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="11754-129">Der Ausdruck `14 \ 4` wird z. b. zu 3 ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="11754-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="11754-130">Der [Operator/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten, einschließlich des Restwerts, als Gleit Komma Zahl zurück.</span><span class="sxs-lookup"><span data-stu-id="11754-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="11754-131">Der Ausdruck `14 / 4` wird z. b. zu 3,5 ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="11754-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="11754-132">Versuchte Division durch Null</span><span class="sxs-lookup"><span data-stu-id="11754-132">Attempted division by zero</span></span>

<span data-ttu-id="11754-133">Wenn `number2` der Wert 0 (null) ergibt, `Mod` hängt das Verhalten des-Operators vom Datentyp der Operanden ab:</span><span class="sxs-lookup"><span data-stu-id="11754-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>
- <span data-ttu-id="11754-134">Eine ganzzahlige Division <xref:System.DivideByZeroException> löst eine `number2` -Ausnahme aus, wenn nicht in der Kompilierzeit bestimmt werden kann `BC30542 Division by zero occurred while evaluating this expression` , `number2` und generiert einen Kompilierzeitfehler, wenn zur Kompilierzeit NULL ergibt.</span><span class="sxs-lookup"><span data-stu-id="11754-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542 Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
- <span data-ttu-id="11754-135">Eine Gleit Komma Division gibt zurück <xref:System.Double.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="11754-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="11754-136">Äquivalente Formel</span><span class="sxs-lookup"><span data-stu-id="11754-136">Equivalent formula</span></span>

<span data-ttu-id="11754-137">Der Ausdruck `a Mod b` entspricht einer der folgenden Formeln:</span><span class="sxs-lookup"><span data-stu-id="11754-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="11754-138">Ungenauigkeit von Gleit Komma Werten</span><span class="sxs-lookup"><span data-stu-id="11754-138">Floating-point imprecision</span></span>

<span data-ttu-id="11754-139">Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Dezimal Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="11754-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="11754-140">Dies kann zu unerwarteten Ergebnissen von bestimmten Vorgängen führen, wie z. b. `Mod` Wert Vergleiche und Operator.</span><span class="sxs-lookup"><span data-stu-id="11754-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="11754-141">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="11754-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="11754-142">Überladen</span><span class="sxs-lookup"><span data-stu-id="11754-142">Overloading</span></span>

<span data-ttu-id="11754-143">Der `Mod` Operator kann *überladen*werden, was bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann.</span><span class="sxs-lookup"><span data-stu-id="11754-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="11754-144">Wenn Ihr Code auf `Mod` eine Instanz einer Klasse oder Struktur angewendet wird, die eine solche Überlastung einschließt, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="11754-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="11754-145">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="11754-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="11754-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11754-146">Example</span></span>

<span data-ttu-id="11754-147">Im folgenden Beispiel wird der `Mod` -Operator verwendet, um zwei Zahlen aufzuteilen und nur den Rest zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="11754-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="11754-148">Wenn eine der Zahlen eine Gleit Komma Zahl ist, ist das Ergebnis eine Gleit Komma Zahl, die den Restwert darstellt.</span><span class="sxs-lookup"><span data-stu-id="11754-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="11754-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11754-149">Example</span></span>

<span data-ttu-id="11754-150">Im folgenden Beispiel wird die mögliche Ungenauigkeit von Gleit Komma Operanden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="11754-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="11754-151">In der ersten Anweisung sind `Double`die Operanden, und 0,2 ist ein unendlich wiederholter binärer Bruchteil mit einem gespeicherten Wert von 0.20000000000000001.</span><span class="sxs-lookup"><span data-stu-id="11754-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="11754-152">In der zweiten Anweisung erzwingt das Literaltypzeichen `D` beide Operanden zu `Decimal`, und 0,2 hat eine genaue Darstellung.</span><span class="sxs-lookup"><span data-stu-id="11754-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="11754-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11754-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="11754-154">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="11754-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="11754-155">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11754-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="11754-156">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="11754-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="11754-157">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="11754-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="11754-158">Arithmetische Operatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11754-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="11754-159">Operator \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11754-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
