---
title: 'Arithmetische Operatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, die Multiplikations-, Divisions-, Rest-, Additions- und Subtraktionsoperationen mit numerischen Typen ausführen.
ms.date: 03/27/2019
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
helpviewer_keywords:
- arithmetic operators [C#]
- increment operator [C#]
- ++ operator [C#]
- decrement operator [C#]
- -- operator [C#]
- multiplication operator [C#]
- '* operator [C#]'
- division operator [C#]
- / operator [C#]
- remainder operator [C#]
- '% operator [C#]'
- addition operator [C#]
- + operator [C#]
- subtraction operator [C#]
- '- operator [C#]'
ms.openlocfilehash: f03084fa611c35c5504190b28fab79563d560d03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398064"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="a3630-103">Arithmetische Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a3630-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="a3630-104">Die folgenden Operatoren führen arithmetische Operationen mit Operanden des numerischen Typs aus:</span><span class="sxs-lookup"><span data-stu-id="a3630-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="a3630-105">Unäre Operatoren: [`++` (inkrementell)](#increment-operator-), [`--` (dekrementell)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators) und [`-` (minus)](#unary-plus-and-minus-operators)</span><span class="sxs-lookup"><span data-stu-id="a3630-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="a3630-106">Binäre Operatoren: [`*` (Multiplikation)](#multiplication-operator-), [`/` (Division)](#division-operator-), [`%` (Rest)](#remainder-operator-), [`+` (Addition)](#addition-operator-) und [`-` (Subtraktion)](#subtraction-operator--)</span><span class="sxs-lookup"><span data-stu-id="a3630-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="a3630-107">Diese Operatoren werden alle von numerischen [Ganzzahl](../builtin-types/integral-numeric-types.md)- und [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a3630-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="a3630-108">Inkrementoperator ++</span><span class="sxs-lookup"><span data-stu-id="a3630-108">Increment operator ++</span></span>

<span data-ttu-id="a3630-109">Der unäre Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="a3630-109">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="a3630-110">Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="a3630-110">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="a3630-111">Der Inkrementoperator wird in zwei Formen unterstützt: als Postfix-Inkrementoperator `x++` und als Präfix-Inkrementoperator `++x`.</span><span class="sxs-lookup"><span data-stu-id="a3630-111">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="a3630-112">Postfix-Operator für Inkrement</span><span class="sxs-lookup"><span data-stu-id="a3630-112">Postfix increment operator</span></span>

<span data-ttu-id="a3630-113">Das Ergebnis von `x++` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a3630-113">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="a3630-114">Präfixinkrement-Operator</span><span class="sxs-lookup"><span data-stu-id="a3630-114">Prefix increment operator</span></span>

<span data-ttu-id="a3630-115">Das Ergebnis von `++x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a3630-115">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="a3630-116">Dekrementoperator --</span><span class="sxs-lookup"><span data-stu-id="a3630-116">Decrement operator --</span></span>

<span data-ttu-id="a3630-117">Der unäre Dekrementoperator `--` verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="a3630-117">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="a3630-118">Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="a3630-118">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="a3630-119">Der Dekrementoperator wird in zwei Formen unterstützt: als Postfix-Dekrementoperator `x--` und als Präfix-Dekrementoperator `--x`.</span><span class="sxs-lookup"><span data-stu-id="a3630-119">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="a3630-120">Postfix-Operator für Dekrement</span><span class="sxs-lookup"><span data-stu-id="a3630-120">Postfix decrement operator</span></span>

<span data-ttu-id="a3630-121">Das Ergebnis von `x--` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a3630-121">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="a3630-122">Präfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-122">Prefix decrement operator</span></span>

<span data-ttu-id="a3630-123">Das Ergebnis von `--x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="a3630-123">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="a3630-124">Unäre Plus- und Minusoperatoren</span><span class="sxs-lookup"><span data-stu-id="a3630-124">Unary plus and minus operators</span></span>

<span data-ttu-id="a3630-125">Der unäre `+`-Operator gibt den Wert seines Operanden zurück.</span><span class="sxs-lookup"><span data-stu-id="a3630-125">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="a3630-126">Der unäre `-`-Operator berechnet die numerische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="a3630-126">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="a3630-127">Der [ulong](../builtin-types/integral-numeric-types.md)-Typ unterstützt den unären `-`-Operator nicht.</span><span class="sxs-lookup"><span data-stu-id="a3630-127">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="a3630-128">Multiplikationsoperator \*</span><span class="sxs-lookup"><span data-stu-id="a3630-128">Multiplication operator \*</span></span>

<span data-ttu-id="a3630-129">Der Multiplikationsoperator `*` berechnet das Produkt seiner Operanden:</span><span class="sxs-lookup"><span data-stu-id="a3630-129">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="a3630-130">Der unäre `*`-Operator ist der [Zeigerdereferenzierungsoperator](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="a3630-130">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="a3630-131">Divisionsoperator /</span><span class="sxs-lookup"><span data-stu-id="a3630-131">Division operator /</span></span>

<span data-ttu-id="a3630-132">Der Divisionsoperator `/` dividiert den linken Operanden durch den rechten Operanden.</span><span class="sxs-lookup"><span data-stu-id="a3630-132">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="a3630-133">Ganzzahldivision</span><span class="sxs-lookup"><span data-stu-id="a3630-133">Integer division</span></span>

<span data-ttu-id="a3630-134">Für die Operanden von Ganzzahltypen weist das Ergebnis des `/`-Operators einen Ganzzahltyp auf und ist gleich dem Quotienten der beiden Operanden, gerundet auf Null:</span><span class="sxs-lookup"><span data-stu-id="a3630-134">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="a3630-135">Um den Quotienten der beiden Operanden als Gleitkommazahl abzurufen, verwenden Sie den Typ `float`, `double` oder `decimal`:</span><span class="sxs-lookup"><span data-stu-id="a3630-135">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="a3630-136">Gleitkommadivision</span><span class="sxs-lookup"><span data-stu-id="a3630-136">Floating-point division</span></span>

<span data-ttu-id="a3630-137">Für die Typen `float`, `double` oder `decimal` ist das Ergebnis des `/`-Operators der Quotient der beiden Operanden:</span><span class="sxs-lookup"><span data-stu-id="a3630-137">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="a3630-138">Wenn einer der Operanden `decimal` lautet, kann ein anderer Operand weder `float` noch `double` sein, weil weder `float` noch `double` implizit zu `decimal` konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="a3630-138">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="a3630-139">Sie müssen den Operanden `float` oder `double` explizit zum Typ `decimal` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a3630-139">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="a3630-140">Weitere Informationen zu Konvertierungen zwischen numerischen Typen finden Sie unter [Built-in numeric conversions](../builtin-types/numeric-conversions.md) (Integrierte numerischer Konvertierungen).</span><span class="sxs-lookup"><span data-stu-id="a3630-140">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="a3630-141">Restoperator %</span><span class="sxs-lookup"><span data-stu-id="a3630-141">Remainder operator %</span></span>

<span data-ttu-id="a3630-142">Der Restoperator `%` berechnet den Rest nach der Division seines linken Operanden durch den rechten Operanden.</span><span class="sxs-lookup"><span data-stu-id="a3630-142">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="a3630-143">Ganzzahliger Rest</span><span class="sxs-lookup"><span data-stu-id="a3630-143">Integer remainder</span></span>

<span data-ttu-id="a3630-144">Für Operanden von Ganzzahltypen entspricht das Ergebnis von `a % b` dem von `a - (a / b) * b` erzeugten Wert.</span><span class="sxs-lookup"><span data-stu-id="a3630-144">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="a3630-145">Das Vorzeichen des Rests, der ungleich 0 (null) ist, ist wie im folgenden Beispiel gezeigt identisch mit dem des linken Operanden:</span><span class="sxs-lookup"><span data-stu-id="a3630-145">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="a3630-146">Verwenden Sie die <xref:System.Math.DivRem%2A?displayProperty=nameWithType>-Methode, wenn Sie sowohl Ganzzahldivision als auch Restergebnisse berechnen möchten.</span><span class="sxs-lookup"><span data-stu-id="a3630-146">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="a3630-147">Gleitkommarest</span><span class="sxs-lookup"><span data-stu-id="a3630-147">Floating-point remainder</span></span>

<span data-ttu-id="a3630-148">Für die Operanden `float` und `double` entspricht das Ergebnis von `x % y` für die endlichen Werte `x` und `y` dem Wert `z`, sodass:</span><span class="sxs-lookup"><span data-stu-id="a3630-148">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="a3630-149">das Vorzeichen von `z` dem Vorzeichen von `x` entspricht, sofern der Wert nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="a3630-149">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="a3630-150">der absolute Wert von `z` dem von `|x| - n * |y|` erzeugten Wert entspricht, wobei `n` der größtmöglichen Ganzzahl entspricht, die kleiner oder gleich `|x| / |y|` ist. Hierbei sind `|x|` und `|y|` jeweils die absoluten Werte von `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="a3630-150">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="a3630-151">Diese Methode zum Berechnen des Rests ist analog zu der Methode, die für ganzzahlige Operanden verwendet wird, unterscheidet sich jedoch von der IEEE 754-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="a3630-151">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="a3630-152">Wenn Sie den Restvorgang benötigen, der der IEEE 754-Spezifikation entspricht, verwenden Sie die Methode <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3630-152">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a3630-153">Weitere Informationen zum Verhalten des `%`-Operators bei nicht begrenzten Operanden finden Sie im Abschnitt [Restoperator](~/_csharplang/spec/expressions.md#remainder-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a3630-153">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a3630-154">Der Restoperator `decimal` entspricht für die `%`-Operanden dem [Restoperator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) vom Typ <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a3630-154">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="a3630-155">Im folgenden Beispiel wird das Verhalten des Restoperators mit Gleitkommaoperanden veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a3630-155">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="a3630-156">Additionsoperator +</span><span class="sxs-lookup"><span data-stu-id="a3630-156">Addition operator +</span></span>

<span data-ttu-id="a3630-157">Der Additionsoperator `+` berechnet die Summe der Operanden:</span><span class="sxs-lookup"><span data-stu-id="a3630-157">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="a3630-158">Der `+`-Operator kann auch für die Zeichenfolgenverkettung und Delegatkombination verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3630-158">You also can use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="a3630-159">Weitere Informationen finden Sie im [Artikel zu den Operatoren `+` und `+=`](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a3630-159">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="a3630-160">Subtraktionsoperator -</span><span class="sxs-lookup"><span data-stu-id="a3630-160">Subtraction operator -</span></span>

<span data-ttu-id="a3630-161">Der Subtraktionsoperator `-` subtrahiert den rechten Operanden vom linken:</span><span class="sxs-lookup"><span data-stu-id="a3630-161">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="a3630-162">Der `-`-Operator kann auch für die Delegatentfernung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3630-162">You also can use the `-` operator for delegate removal.</span></span> <span data-ttu-id="a3630-163">Weitere Informationen finden Sie im [Artikel zu den Operatoren `-` und `-=`](subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a3630-163">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="a3630-164">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="a3630-164">Compound assignment</span></span>

<span data-ttu-id="a3630-165">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="a3630-165">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="a3630-166">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="a3630-166">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="a3630-167">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="a3630-167">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="a3630-168">Im folgenden Beispiel wird die Verwendung von Verbundzuweisungen mit arithmetischen Operatoren veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a3630-168">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="a3630-169">Aufgrund von [numerischen Höherstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) kann das Ergebnis der Operation `op` ggf. nicht implizit in den Typ `T` von `x` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3630-169">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="a3630-170">In diesem Fall gilt Folgendes: Wenn `op` ein vordefinierter Operator ist und das Ergebnis der Operation explizit in den Typ `T` von `x` konvertiert werden kann, entspricht ein Verbundzuweisungsausdruck der Form `x op= y` dem Ausdruck `x = (T)(x op y)`. Der einzige Unterschied ist, dass `x` nur einmal ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="a3630-170">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="a3630-171">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="a3630-171">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="a3630-172">Die Operatoren `+=` und `-=` können auch zum Abonnieren von Ereignissen und zum Kündigen eines [Ereignisabonnements](../keywords/event.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3630-172">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="a3630-173">Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="a3630-173">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="a3630-174">Operatorrangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="a3630-174">Operator precedence and associativity</span></span>

<span data-ttu-id="a3630-175">In der folgenden Liste sind die arithmetischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="a3630-175">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="a3630-176">Postfixinkrementoperator `x++` und Postfixdekrementoperator `x--`</span><span class="sxs-lookup"><span data-stu-id="a3630-176">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="a3630-177">Präfixinkrementoperator `++x` und Präfixdekrementoperator `--x` sowie unäre `+`- und `-`-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a3630-177">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="a3630-178">Multiplikative Operatoren `*`, `/` und `%`</span><span class="sxs-lookup"><span data-stu-id="a3630-178">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="a3630-179">Additive Operatoren `+` und `-`</span><span class="sxs-lookup"><span data-stu-id="a3630-179">Additive `+` and `-` operators</span></span>

<span data-ttu-id="a3630-180">Binäre arithmetische Operatoren sind linksassoziativ.</span><span class="sxs-lookup"><span data-stu-id="a3630-180">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="a3630-181">Das bedeutet, dass Operatoren mit der gleichen Rangfolgenebene von links nach rechts ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a3630-181">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="a3630-182">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge und Assoziativität festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a3630-182">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="a3630-183">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="a3630-183">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="a3630-184">Arithmetischer Überlauf und Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="a3630-184">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="a3630-185">Liegt das Ergebnis einer arithmetischen Operation außerhalb des Bereichs möglicher endlicher Werte des betreffenden numerischen Typs, hängt das Verhalten eines arithmetischen Operators vom Typ der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="a3630-185">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="a3630-186">Arithmetischer Überlauf bei ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="a3630-186">Integer arithmetic overflow</span></span>

<span data-ttu-id="a3630-187">Division ganzer Zahlen durch Null löst immer eine <xref:System.DivideByZeroException> aus.</span><span class="sxs-lookup"><span data-stu-id="a3630-187">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="a3630-188">Im Fall eines arithmetischen Überlaufs bei ganzen Zahlen steuert ein Kontext für Überlaufprüfungen, der [aktiviert oder deaktiviert (Checked oder Unchecked)](../keywords/checked-and-unchecked.md) sein kann, das resultierende Verhalten:</span><span class="sxs-lookup"><span data-stu-id="a3630-188">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="a3630-189">In einem aktivierten Kontext tritt bei einem Überlauf in einem konstanten Ausdruck ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a3630-189">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="a3630-190">Andernfalls wird, wenn die Operation zur Laufzeit ausgeführt wird, eine <xref:System.OverflowException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a3630-190">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="a3630-191">In einem deaktivierten Kontext wird das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.</span><span class="sxs-lookup"><span data-stu-id="a3630-191">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="a3630-192">Neben den Anweisungen [Checked und Unchecked](../keywords/checked-and-unchecked.md) können Sie mithilfe der `checked`- und `unchecked`-Operatoren den Kontext für Überlaufprüfungen steuern, in dem ein Ausdruck ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="a3630-192">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="a3630-193">Standardmäßig erscheinen arithmetische Operationen in einem *unchecked*-Kontext.</span><span class="sxs-lookup"><span data-stu-id="a3630-193">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="a3630-194">Arithmetischer Überlauf bei Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="a3630-194">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="a3630-195">Bei arithmetischen Operationen mit den Typen `float` und `double` wird nie eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a3630-195">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="a3630-196">Das Ergebnis von arithmetischen Operationen mit diesen Typen können spezielle Werte sein, die unendliche und nicht numerische Zahlen darstellen:</span><span class="sxs-lookup"><span data-stu-id="a3630-196">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="a3630-197">Für Operanden vom Typ `decimal` löst ein arithmetischer Überlauf immer eine <xref:System.OverflowException>-Ausnahme und die Division durch 0 (null) immer eine <xref:System.DivideByZeroException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a3630-197">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="a3630-198">Rundungsfehler</span><span class="sxs-lookup"><span data-stu-id="a3630-198">Round-off errors</span></span>

<span data-ttu-id="a3630-199">Aufgrund allgemeiner Einschränkungen der Gleitkommadarstellung von reellen Zahlen und arithmetischer Gleitkommaoperatoren können in Berechnungen mit Gleitkommatypen Rundungsfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="a3630-199">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="a3630-200">Das bedeutet, dass das generierte Ergebnis eines Ausdrucks vom erwarteten mathematischen Ergebnis abweichen kann.</span><span class="sxs-lookup"><span data-stu-id="a3630-200">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="a3630-201">Im folgenden Beispiel werden einige solcher Fälle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a3630-201">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="a3630-202">Weitere Informationen finden Sie in den Hinweisen auf den Referenzseiten zu [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) oder [System.Decimal](/dotnet/api/system.decimal#remarks).</span><span class="sxs-lookup"><span data-stu-id="a3630-202">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a3630-203">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="a3630-203">Operator overloadability</span></span>

<span data-ttu-id="a3630-204">Ein benutzerdefinierter Typ kann die unären ([, ](operator-overloading.md), `++` und `--`) und binären (`+`, `-`, `*`, `/` und `%`) arithmetischen Operatoren `+`überladen`-`.</span><span class="sxs-lookup"><span data-stu-id="a3630-204">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="a3630-205">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="a3630-205">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="a3630-206">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="a3630-206">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a3630-207">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a3630-207">C# language specification</span></span>

<span data-ttu-id="a3630-208">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="a3630-208">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="a3630-209">Postfix-Inkrementoperator und Postfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-209">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="a3630-210">Präfix-Inkrementoperator und Präfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-210">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="a3630-211">Unärer Plusoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-211">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="a3630-212">Unärer Minusoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-212">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="a3630-213">Multiplikationsoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-213">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="a3630-214">Divisionsoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-214">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="a3630-215">Restoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-215">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="a3630-216">Additionsoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-216">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="a3630-217">Subtraktionsoperator</span><span class="sxs-lookup"><span data-stu-id="a3630-217">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="a3630-218">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="a3630-218">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="a3630-219">The checked and unchecked operators (Checked- und Unchecked-Operatoren)</span><span class="sxs-lookup"><span data-stu-id="a3630-219">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="a3630-220">Numerische Heraufstufungen</span><span class="sxs-lookup"><span data-stu-id="a3630-220">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="a3630-221">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3630-221">See also</span></span>

- [<span data-ttu-id="a3630-222">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a3630-222">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a3630-223">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a3630-223">C# operators</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="a3630-224">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="a3630-224">Numerics in .NET</span></span>](../../../standard/numerics.md)
