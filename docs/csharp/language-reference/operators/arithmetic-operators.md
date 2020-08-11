---
title: 'Arithmetische Operatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, die Multiplikations-, Divisions-, Rest-, Additions- und Subtraktionsoperationen mit numerischen Typen ausführen.
ms.date: 05/11/2020
author: pkulikov
f1_keywords:
- ++_CSharpKeyword
- --_CSharpKeyword
- '*_CSharpKeyword'
- /_CSharpKeyword
- '%_CSharpKeyword'
- +_CSharpKeyword
- -_CSharpKeyword
- '%=_CSharpKeyword'
- '*=_CSharpKeyword'
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
ms.openlocfilehash: f5da9c4433ffcf3e6a110bbb1543343289240778
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916955"
---
# <a name="arithmetic-operators-c-reference"></a><span data-ttu-id="1973d-103">Arithmetische Operatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1973d-103">Arithmetic operators (C# reference)</span></span>

<span data-ttu-id="1973d-104">Die folgenden Operatoren führen arithmetische Operationen mit Operanden des numerischen Typs aus:</span><span class="sxs-lookup"><span data-stu-id="1973d-104">The following operators perform arithmetic operations with operands of numeric types:</span></span>

- <span data-ttu-id="1973d-105">Unäre Operatoren: [`++` (inkrementell)](#increment-operator-), [`--` (dekrementell)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators) und [`-` (minus)](#unary-plus-and-minus-operators)</span><span class="sxs-lookup"><span data-stu-id="1973d-105">Unary [`++` (increment)](#increment-operator-), [`--` (decrement)](#decrement-operator---), [`+` (plus)](#unary-plus-and-minus-operators), and [`-` (minus)](#unary-plus-and-minus-operators) operators</span></span>
- <span data-ttu-id="1973d-106">Binäre Operatoren: [`*` (Multiplikation)](#multiplication-operator-), [`/` (Division)](#division-operator-), [`%` (Rest)](#remainder-operator-), [`+` (Addition)](#addition-operator-) und [`-` (Subtraktion)](#subtraction-operator--)</span><span class="sxs-lookup"><span data-stu-id="1973d-106">Binary [`*` (multiplication)](#multiplication-operator-), [`/` (division)](#division-operator-), [`%` (remainder)](#remainder-operator-), [`+` (addition)](#addition-operator-), and [`-` (subtraction)](#subtraction-operator--) operators</span></span>

<span data-ttu-id="1973d-107">Diese Operatoren werden alle von numerischen [Ganzzahl](../builtin-types/integral-numeric-types.md)- und [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1973d-107">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

<span data-ttu-id="1973d-108">Bei integralen Typen werden diese Operatoren (außer den Operatoren `++` und `--`) für die Typen `int`, `uint`, `long` und `ulong` definiert.</span><span class="sxs-lookup"><span data-stu-id="1973d-108">In the case of integral types, those operators (except the `++` and `--` operators) are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="1973d-109">Wenn Operanden andere integrale Typen aufweisen (`sbyte`, `byte`, `short`, `ushort` oder `char`), werden ihre Werte in den Typ `int` konvertiert. Hierbei handelt es sich auch um den Ergebnistyp einer Operation.</span><span class="sxs-lookup"><span data-stu-id="1973d-109">When operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="1973d-110">Wenn Operanden abweichende integrale Typen oder Gleitkommatypen aufweisen, werden ihre Werte in den am besten geeigneten enthaltenden Typ konvertiert, falls solch ein Typ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1973d-110">When operands are of different integral or floating-point types, their values are converted to the closest containing type, if such a type exists.</span></span> <span data-ttu-id="1973d-111">Weitere Informationen finden Sie im Abschnitt [Numerische Heraufstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="1973d-112">Die `++`- und `--`-Operatoren werden für alle numerischen integralen und Gleitkommatypen sowie den [char](../builtin-types/char.md)-Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="1973d-112">The `++` and `--` operators are defined for all integral and floating-point numeric types and the [char](../builtin-types/char.md) type.</span></span>

## <a name="increment-operator-"></a><span data-ttu-id="1973d-113">Inkrementoperator ++</span><span class="sxs-lookup"><span data-stu-id="1973d-113">Increment operator ++</span></span>

<span data-ttu-id="1973d-114">Der unäre Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="1973d-114">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="1973d-115">Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="1973d-115">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="1973d-116">Der Inkrementoperator wird in zwei Formen unterstützt: als Postfix-Inkrementoperator `x++` und als Präfix-Inkrementoperator `++x`.</span><span class="sxs-lookup"><span data-stu-id="1973d-116">The increment operator is supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

### <a name="postfix-increment-operator"></a><span data-ttu-id="1973d-117">Postfix-Operator für Inkrement</span><span class="sxs-lookup"><span data-stu-id="1973d-117">Postfix increment operator</span></span>

<span data-ttu-id="1973d-118">Das Ergebnis von `x++` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1973d-118">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](snippets/shared/ArithmeticOperators.cs#PostfixIncrement)]

### <a name="prefix-increment-operator"></a><span data-ttu-id="1973d-119">Präfixinkrement-Operator</span><span class="sxs-lookup"><span data-stu-id="1973d-119">Prefix increment operator</span></span>

<span data-ttu-id="1973d-120">Das Ergebnis von `++x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1973d-120">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](snippets/shared/ArithmeticOperators.cs#PrefixIncrement)]

## <a name="decrement-operator---"></a><span data-ttu-id="1973d-121">Dekrementoperator --</span><span class="sxs-lookup"><span data-stu-id="1973d-121">Decrement operator --</span></span>

<span data-ttu-id="1973d-122">Der unäre Dekrementoperator `--` verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="1973d-122">The unary decrement operator `--` decrements its operand by 1.</span></span> <span data-ttu-id="1973d-123">Der Operand muss eine Variable, ein [Eigenschaftenzugriff](../../programming-guide/classes-and-structs/properties.md) oder ein [Indexerzugriff](../../programming-guide/indexers/index.md) sein.</span><span class="sxs-lookup"><span data-stu-id="1973d-123">The operand must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../programming-guide/indexers/index.md) access.</span></span>

<span data-ttu-id="1973d-124">Der Dekrementoperator wird in zwei Formen unterstützt: als Postfix-Dekrementoperator `x--` und als Präfix-Dekrementoperator `--x`.</span><span class="sxs-lookup"><span data-stu-id="1973d-124">The decrement operator is supported in two forms: the postfix decrement operator, `x--`, and the prefix decrement operator, `--x`.</span></span>

### <a name="postfix-decrement-operator"></a><span data-ttu-id="1973d-125">Postfix-Operator für Dekrement</span><span class="sxs-lookup"><span data-stu-id="1973d-125">Postfix decrement operator</span></span>

<span data-ttu-id="1973d-126">Das Ergebnis von `x--` ist der Wert von `x` *vor* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1973d-126">The result of `x--` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix decrement](snippets/shared/ArithmeticOperators.cs#PostfixDecrement)]

### <a name="prefix-decrement-operator"></a><span data-ttu-id="1973d-127">Präfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-127">Prefix decrement operator</span></span>

<span data-ttu-id="1973d-128">Das Ergebnis von `--x` ist der Wert von `x` *nach* dem Vorgang, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1973d-128">The result of `--x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix decrement](snippets/shared/ArithmeticOperators.cs#PrefixDecrement)]

## <a name="unary-plus-and-minus-operators"></a><span data-ttu-id="1973d-129">Unäre Plus- und Minusoperatoren</span><span class="sxs-lookup"><span data-stu-id="1973d-129">Unary plus and minus operators</span></span>

<span data-ttu-id="1973d-130">Der unäre `+`-Operator gibt den Wert seines Operanden zurück.</span><span class="sxs-lookup"><span data-stu-id="1973d-130">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="1973d-131">Der unäre `-`-Operator berechnet die numerische Negation des Operanden.</span><span class="sxs-lookup"><span data-stu-id="1973d-131">The unary `-` operator computes the numeric negation of its operand.</span></span>

[!code-csharp-interactive[unary plus and minus](snippets/shared/ArithmeticOperators.cs#UnaryPlusAndMinus)]

<span data-ttu-id="1973d-132">Der [ulong](../builtin-types/integral-numeric-types.md)-Typ unterstützt den unären `-`-Operator nicht.</span><span class="sxs-lookup"><span data-stu-id="1973d-132">The [ulong](../builtin-types/integral-numeric-types.md) type doesn't support the unary `-` operator.</span></span>

## <a name="multiplication-operator-"></a><span data-ttu-id="1973d-133">Multiplikationsoperator \*</span><span class="sxs-lookup"><span data-stu-id="1973d-133">Multiplication operator \*</span></span>

<span data-ttu-id="1973d-134">Der Multiplikationsoperator `*` berechnet das Produkt seiner Operanden:</span><span class="sxs-lookup"><span data-stu-id="1973d-134">The multiplication operator `*` computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication operator](snippets/shared/ArithmeticOperators.cs#Multiplication)]

<span data-ttu-id="1973d-135">Der unäre `*`-Operator ist der [Zeigerdereferenzierungsoperator](pointer-related-operators.md#pointer-indirection-operator-).</span><span class="sxs-lookup"><span data-stu-id="1973d-135">The unary `*` operator is the [pointer indirection operator](pointer-related-operators.md#pointer-indirection-operator-).</span></span>

## <a name="division-operator-"></a><span data-ttu-id="1973d-136">Divisionsoperator /</span><span class="sxs-lookup"><span data-stu-id="1973d-136">Division operator /</span></span>

<span data-ttu-id="1973d-137">Der Divisionsoperator `/` dividiert den linken Operanden durch den rechten Operanden.</span><span class="sxs-lookup"><span data-stu-id="1973d-137">The division operator `/` divides its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-division"></a><span data-ttu-id="1973d-138">Ganzzahldivision</span><span class="sxs-lookup"><span data-stu-id="1973d-138">Integer division</span></span>

<span data-ttu-id="1973d-139">Für die Operanden von Ganzzahltypen weist das Ergebnis des `/`-Operators einen Ganzzahltyp auf und ist gleich dem Quotienten der beiden Operanden, gerundet auf Null:</span><span class="sxs-lookup"><span data-stu-id="1973d-139">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](snippets/shared/ArithmeticOperators.cs#IntegerDivision)]

<span data-ttu-id="1973d-140">Um den Quotienten der beiden Operanden als Gleitkommazahl abzurufen, verwenden Sie den Typ `float`, `double` oder `decimal`:</span><span class="sxs-lookup"><span data-stu-id="1973d-140">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](snippets/shared/ArithmeticOperators.cs#IntegerAsFloatingPointDivision)]

### <a name="floating-point-division"></a><span data-ttu-id="1973d-141">Gleitkommadivision</span><span class="sxs-lookup"><span data-stu-id="1973d-141">Floating-point division</span></span>

<span data-ttu-id="1973d-142">Für die Typen `float`, `double` oder `decimal` ist das Ergebnis des `/`-Operators der Quotient der beiden Operanden:</span><span class="sxs-lookup"><span data-stu-id="1973d-142">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](snippets/shared/ArithmeticOperators.cs#FloatingPointDivision)]

<span data-ttu-id="1973d-143">Wenn einer der Operanden `decimal` lautet, kann ein anderer Operand weder `float` noch `double` sein, weil weder `float` noch `double` implizit zu `decimal` konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="1973d-143">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="1973d-144">Sie müssen den Operanden `float` oder `double` explizit zum Typ `decimal` konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1973d-144">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="1973d-145">Weitere Informationen zu Konvertierungen zwischen numerischen Typen finden Sie unter [Built-in numeric conversions](../builtin-types/numeric-conversions.md) (Integrierte numerischer Konvertierungen).</span><span class="sxs-lookup"><span data-stu-id="1973d-145">For more information about conversions between numeric types, see [Built-in numeric conversions](../builtin-types/numeric-conversions.md).</span></span>

## <a name="remainder-operator-"></a><span data-ttu-id="1973d-146">Restoperator %</span><span class="sxs-lookup"><span data-stu-id="1973d-146">Remainder operator %</span></span>

<span data-ttu-id="1973d-147">Der Restoperator `%` berechnet den Rest nach der Division seines linken Operanden durch den rechten Operanden.</span><span class="sxs-lookup"><span data-stu-id="1973d-147">The remainder operator `%` computes the remainder after dividing its left-hand operand by its right-hand operand.</span></span>

### <a name="integer-remainder"></a><span data-ttu-id="1973d-148">Ganzzahliger Rest</span><span class="sxs-lookup"><span data-stu-id="1973d-148">Integer remainder</span></span>

<span data-ttu-id="1973d-149">Für Operanden von Ganzzahltypen entspricht das Ergebnis von `a % b` dem von `a - (a / b) * b` erzeugten Wert.</span><span class="sxs-lookup"><span data-stu-id="1973d-149">For the operands of integer types, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="1973d-150">Das Vorzeichen des Rests, der ungleich 0 (null) ist, ist wie im folgenden Beispiel gezeigt identisch mit dem des linken Operanden:</span><span class="sxs-lookup"><span data-stu-id="1973d-150">The sign of the non-zero remainder is the same as that of the left-hand operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](snippets/shared/ArithmeticOperators.cs#IntegerRemainder)]

<span data-ttu-id="1973d-151">Verwenden Sie die <xref:System.Math.DivRem%2A?displayProperty=nameWithType>-Methode, wenn Sie sowohl Ganzzahldivision als auch Restergebnisse berechnen möchten.</span><span class="sxs-lookup"><span data-stu-id="1973d-151">Use the <xref:System.Math.DivRem%2A?displayProperty=nameWithType> method to compute both integer division and remainder results.</span></span>

### <a name="floating-point-remainder"></a><span data-ttu-id="1973d-152">Gleitkommarest</span><span class="sxs-lookup"><span data-stu-id="1973d-152">Floating-point remainder</span></span>

<span data-ttu-id="1973d-153">Für die Operanden `float` und `double` entspricht das Ergebnis von `x % y` für die endlichen Werte `x` und `y` dem Wert `z`, sodass:</span><span class="sxs-lookup"><span data-stu-id="1973d-153">For the `float` and `double` operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="1973d-154">das Vorzeichen von `z` dem Vorzeichen von `x` entspricht, sofern der Wert nicht 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="1973d-154">The sign of `z`, if non-zero, is the same as the sign of `x`.</span></span>
- <span data-ttu-id="1973d-155">der absolute Wert von `z` dem von `|x| - n * |y|` erzeugten Wert entspricht, wobei `n` der größtmöglichen Ganzzahl entspricht, die kleiner oder gleich `|x| / |y|` ist. Hierbei sind `|x|` und `|y|` jeweils die absoluten Werte von `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="1973d-155">The absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="1973d-156">Diese Methode zum Berechnen des Rests ist analog zu der Methode, die für ganzzahlige Operanden verwendet wird, unterscheidet sich jedoch von der IEEE 754-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="1973d-156">This method of computing the remainder is analogous to that used for integer operands, but different from the IEEE 754 specification.</span></span> <span data-ttu-id="1973d-157">Wenn Sie den Restvorgang benötigen, der der IEEE 754-Spezifikation entspricht, verwenden Sie die Methode <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1973d-157">If you need the remainder operation that complies with the IEEE 754 specification, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1973d-158">Weitere Informationen zum Verhalten des `%`-Operators bei nicht begrenzten Operanden finden Sie im Abschnitt [Restoperator](~/_csharplang/spec/expressions.md#remainder-operator) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-158">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="1973d-159">Der Restoperator `%` entspricht für die `decimal`-Operanden dem [Restoperator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) vom Typ <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1973d-159">For the `decimal` operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

<span data-ttu-id="1973d-160">Im folgenden Beispiel wird das Verhalten des Restoperators mit Gleitkommaoperanden veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1973d-160">The following example demonstrates the behavior of the remainder operator with floating-point operands:</span></span>

[!code-csharp-interactive[floating-point remainder](snippets/shared/ArithmeticOperators.cs#FloatingPointRemainder)]

## <a name="addition-operator-"></a><span data-ttu-id="1973d-161">Additionsoperator +</span><span class="sxs-lookup"><span data-stu-id="1973d-161">Addition operator +</span></span>

<span data-ttu-id="1973d-162">Der Additionsoperator `+` berechnet die Summe der Operanden:</span><span class="sxs-lookup"><span data-stu-id="1973d-162">The addition operator `+` computes the sum of its operands:</span></span>

[!code-csharp-interactive[addition operator](snippets/shared/ArithmeticOperators.cs#Addition)]

<span data-ttu-id="1973d-163">Der `+`-Operator kann auch für die Zeichenfolgenverkettung und Delegatkombination verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1973d-163">You can also use the `+` operator for string concatenation and delegate combination.</span></span> <span data-ttu-id="1973d-164">Weitere Informationen finden Sie im [Artikel zu den Operatoren `+` und `+=`](addition-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-164">For more information, see the [`+` and `+=` operators](addition-operator.md) article.</span></span>

## <a name="subtraction-operator--"></a><span data-ttu-id="1973d-165">Subtraktionsoperator -</span><span class="sxs-lookup"><span data-stu-id="1973d-165">Subtraction operator -</span></span>

<span data-ttu-id="1973d-166">Der Subtraktionsoperator `-` subtrahiert den rechten Operanden vom linken:</span><span class="sxs-lookup"><span data-stu-id="1973d-166">The subtraction operator `-` subtracts its right-hand operand from its left-hand operand:</span></span>

[!code-csharp-interactive[subtraction operator](snippets/shared/ArithmeticOperators.cs#Subtraction)]

<span data-ttu-id="1973d-167">Der `-`-Operator kann auch für die Delegatentfernung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1973d-167">You can also use the `-` operator for delegate removal.</span></span> <span data-ttu-id="1973d-168">Weitere Informationen finden Sie im [Artikel zu den Operatoren `-` und `-=`](subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-168">For more information, see the [`-` and `-=` operators](subtraction-operator.md) article.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="1973d-169">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="1973d-169">Compound assignment</span></span>

<span data-ttu-id="1973d-170">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="1973d-170">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="1973d-171">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1973d-171">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="1973d-172">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1973d-172">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1973d-173">Im folgenden Beispiel wird die Verwendung von Verbundzuweisungen mit arithmetischen Operatoren veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1973d-173">The following example demonstrates the usage of compound assignment with arithmetic operators:</span></span>

[!code-csharp-interactive[compound assignment](snippets/shared/ArithmeticOperators.cs#CompoundAssignment)]

<span data-ttu-id="1973d-174">Aufgrund von [numerischen Höherstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) kann das Ergebnis der Operation `op` ggf. nicht implizit in den Typ `T` von `x` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1973d-174">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="1973d-175">In diesem Fall gilt Folgendes: Wenn `op` ein vordefinierter Operator ist und das Ergebnis der Operation explizit in den Typ `T` von `x` konvertiert werden kann, entspricht ein Verbundzuweisungsausdruck der Form `x op= y` dem Ausdruck `x = (T)(x op y)`. Der einzige Unterschied ist, dass `x` nur einmal ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1973d-175">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="1973d-176">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="1973d-176">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](snippets/shared/ArithmeticOperators.cs#CompoundAssignmentWithCast)]

<span data-ttu-id="1973d-177">Die Operatoren `+=` und `-=` können auch zum Abonnieren von Ereignissen und zum Kündigen eines [Ereignisabonnements](../keywords/event.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1973d-177">You also use the `+=` and `-=` operators to subscribe to and unsubscribe from an [event](../keywords/event.md), respectively.</span></span> <span data-ttu-id="1973d-178">Weitere Informationen finden Sie unter [Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-178">For more information, see [How to subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-precedence-and-associativity"></a><span data-ttu-id="1973d-179">Operatorrangfolge und Assoziativität</span><span class="sxs-lookup"><span data-stu-id="1973d-179">Operator precedence and associativity</span></span>

<span data-ttu-id="1973d-180">In der folgenden Liste sind die arithmetischen Operatoren beginnend mit dem höchsten Rangfolgenoperator absteigend sortiert:</span><span class="sxs-lookup"><span data-stu-id="1973d-180">The following list orders arithmetic operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="1973d-181">Postfixinkrementoperator `x++` und Postfixdekrementoperator `x--`</span><span class="sxs-lookup"><span data-stu-id="1973d-181">Postfix increment `x++` and decrement `x--` operators</span></span>
- <span data-ttu-id="1973d-182">Präfixinkrementoperator `++x` und Präfixdekrementoperator `--x` sowie unäre `+`- und `-`-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1973d-182">Prefix increment `++x` and decrement `--x` and unary `+` and `-` operators</span></span>
- <span data-ttu-id="1973d-183">Multiplikative Operatoren `*`, `/` und `%`</span><span class="sxs-lookup"><span data-stu-id="1973d-183">Multiplicative `*`, `/`, and `%` operators</span></span>
- <span data-ttu-id="1973d-184">Additive Operatoren `+` und `-`</span><span class="sxs-lookup"><span data-stu-id="1973d-184">Additive `+` and `-` operators</span></span>

<span data-ttu-id="1973d-185">Binäre arithmetische Operatoren sind linksassoziativ.</span><span class="sxs-lookup"><span data-stu-id="1973d-185">Binary arithmetic operators are left-associative.</span></span> <span data-ttu-id="1973d-186">Das bedeutet, dass Operatoren mit der gleichen Rangfolgenebene von links nach rechts ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="1973d-186">That is, operators with the same precedence level are evaluated from left to right.</span></span>

<span data-ttu-id="1973d-187">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge und Assoziativität festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1973d-187">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence and associativity.</span></span>

[!code-csharp-interactive[precedence and associativity](snippets/shared/ArithmeticOperators.cs#PrecedenceAndAssociativity)]

<span data-ttu-id="1973d-188">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-188">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="arithmetic-overflow-and-division-by-zero"></a><span data-ttu-id="1973d-189">Arithmetischer Überlauf und Division durch 0 (null)</span><span class="sxs-lookup"><span data-stu-id="1973d-189">Arithmetic overflow and division by zero</span></span>

<span data-ttu-id="1973d-190">Liegt das Ergebnis einer arithmetischen Operation außerhalb des Bereichs möglicher endlicher Werte des betreffenden numerischen Typs, hängt das Verhalten eines arithmetischen Operators vom Typ der Operanden ab.</span><span class="sxs-lookup"><span data-stu-id="1973d-190">When the result of an arithmetic operation is outside the range of possible finite values of the involved numeric type, the behavior of an arithmetic operator depends on the type of its operands.</span></span>

### <a name="integer-arithmetic-overflow"></a><span data-ttu-id="1973d-191">Arithmetischer Überlauf bei ganzen Zahlen</span><span class="sxs-lookup"><span data-stu-id="1973d-191">Integer arithmetic overflow</span></span>

<span data-ttu-id="1973d-192">Division ganzer Zahlen durch Null löst immer eine <xref:System.DivideByZeroException> aus.</span><span class="sxs-lookup"><span data-stu-id="1973d-192">Integer division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

<span data-ttu-id="1973d-193">Im Fall eines arithmetischen Überlaufs bei ganzen Zahlen steuert ein Kontext für Überlaufprüfungen, der [aktiviert oder deaktiviert (Checked oder Unchecked)](../keywords/checked-and-unchecked.md) sein kann, das resultierende Verhalten:</span><span class="sxs-lookup"><span data-stu-id="1973d-193">In case of integer arithmetic overflow, an overflow checking context, which can be [checked or unchecked](../keywords/checked-and-unchecked.md), controls the resulting behavior:</span></span>

- <span data-ttu-id="1973d-194">In einem aktivierten Kontext tritt bei einem Überlauf in einem konstanten Ausdruck ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="1973d-194">In a checked context, if overflow happens in a constant expression, a compile-time error occurs.</span></span> <span data-ttu-id="1973d-195">Andernfalls wird, wenn die Operation zur Laufzeit ausgeführt wird, eine <xref:System.OverflowException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1973d-195">Otherwise, when the operation is performed at run time, an <xref:System.OverflowException> is thrown.</span></span>
- <span data-ttu-id="1973d-196">In einem deaktivierten Kontext wird das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.</span><span class="sxs-lookup"><span data-stu-id="1973d-196">In an unchecked context, the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>

<span data-ttu-id="1973d-197">Neben den Anweisungen [Checked und Unchecked](../keywords/checked-and-unchecked.md) können Sie mithilfe der `checked`- und `unchecked`-Operatoren den Kontext für Überlaufprüfungen steuern, in dem ein Ausdruck ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="1973d-197">Along with the [checked and unchecked](../keywords/checked-and-unchecked.md) statements, you can use the `checked` and `unchecked` operators to control the overflow checking context, in which an expression is evaluated:</span></span>

[!code-csharp-interactive[checked and unchecked](snippets/shared/ArithmeticOperators.cs#CheckedUnchecked)]

<span data-ttu-id="1973d-198">Standardmäßig erscheinen arithmetische Operationen in einem *unchecked*-Kontext.</span><span class="sxs-lookup"><span data-stu-id="1973d-198">By default, arithmetic operations occur in an *unchecked* context.</span></span>

### <a name="floating-point-arithmetic-overflow"></a><span data-ttu-id="1973d-199">Arithmetischer Überlauf bei Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="1973d-199">Floating-point arithmetic overflow</span></span>

<span data-ttu-id="1973d-200">Bei arithmetischen Operationen mit den Typen `float` und `double` wird nie eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1973d-200">Arithmetic operations with the `float` and `double` types never throw an exception.</span></span> <span data-ttu-id="1973d-201">Das Ergebnis von arithmetischen Operationen mit diesen Typen können spezielle Werte sein, die unendliche und nicht numerische Zahlen darstellen:</span><span class="sxs-lookup"><span data-stu-id="1973d-201">The result of arithmetic operations with those types can be one of special values that represent infinity and not-a-number:</span></span>

[!code-csharp-interactive[double non-finite values](snippets/shared/ArithmeticOperators.cs#FloatingPointOverflow)]

<span data-ttu-id="1973d-202">Für Operanden vom Typ `decimal` löst ein arithmetischer Überlauf immer eine <xref:System.OverflowException>-Ausnahme und die Division durch 0 (null) immer eine <xref:System.DivideByZeroException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="1973d-202">For the operands of the `decimal` type, arithmetic overflow always throws an <xref:System.OverflowException> and division by zero always throws a <xref:System.DivideByZeroException>.</span></span>

## <a name="round-off-errors"></a><span data-ttu-id="1973d-203">Rundungsfehler</span><span class="sxs-lookup"><span data-stu-id="1973d-203">Round-off errors</span></span>

<span data-ttu-id="1973d-204">Aufgrund allgemeiner Einschränkungen der Gleitkommadarstellung von reellen Zahlen und arithmetischer Gleitkommaoperatoren können in Berechnungen mit Gleitkommatypen Rundungsfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="1973d-204">Because of general limitations of the floating-point representation of real numbers and floating-point arithmetic, round-off errors might occur in calculations with floating-point types.</span></span> <span data-ttu-id="1973d-205">Das bedeutet, dass das generierte Ergebnis eines Ausdrucks vom erwarteten mathematischen Ergebnis abweichen kann.</span><span class="sxs-lookup"><span data-stu-id="1973d-205">That is, the produced result of an expression might differ from the expected mathematical result.</span></span> <span data-ttu-id="1973d-206">Im folgenden Beispiel werden einige solcher Fälle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1973d-206">The following example demonstrates several such cases:</span></span>

[!code-csharp-interactive[round-off errors](snippets/shared/ArithmeticOperators.cs#RoundOffErrors)]

<span data-ttu-id="1973d-207">Weitere Informationen finden Sie in den Hinweisen auf den Referenzseiten zu [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks) oder [System.Decimal](/dotnet/api/system.decimal#remarks).</span><span class="sxs-lookup"><span data-stu-id="1973d-207">For more information, see remarks at the [System.Double](/dotnet/api/system.double#remarks), [System.Single](/dotnet/api/system.single#remarks), or [System.Decimal](/dotnet/api/system.decimal#remarks) reference pages.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1973d-208">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="1973d-208">Operator overloadability</span></span>

<span data-ttu-id="1973d-209">Ein benutzerdefinierter Typ kann die unären (`++`, `--`, `+` und `-`) und binären (`*`, `/`, `%`, `+` und `-`) arithmetischen Operatoren [überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="1973d-209">A user-defined type can [overload](operator-overloading.md) the unary (`++`, `--`, `+`, and `-`) and binary (`*`, `/`, `%`, `+`, and `-`) arithmetic operators.</span></span> <span data-ttu-id="1973d-210">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="1973d-210">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="1973d-211">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="1973d-211">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1973d-212">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1973d-212">C# language specification</span></span>

<span data-ttu-id="1973d-213">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1973d-213">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1973d-214">Postfix-Inkrementoperator und Postfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-214">Postfix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)
- [<span data-ttu-id="1973d-215">Präfix-Inkrementoperator und Präfix-Dekrementoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-215">Prefix increment and decrement operators</span></span>](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)
- [<span data-ttu-id="1973d-216">Unärer Plusoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-216">Unary plus operator</span></span>](~/_csharplang/spec/expressions.md#unary-plus-operator)
- [<span data-ttu-id="1973d-217">Unärer Minusoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-217">Unary minus operator</span></span>](~/_csharplang/spec/expressions.md#unary-minus-operator)
- [<span data-ttu-id="1973d-218">Multiplikationsoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-218">Multiplication operator</span></span>](~/_csharplang/spec/expressions.md#multiplication-operator)
- [<span data-ttu-id="1973d-219">Divisionsoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-219">Division operator</span></span>](~/_csharplang/spec/expressions.md#division-operator)
- [<span data-ttu-id="1973d-220">Restoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-220">Remainder operator</span></span>](~/_csharplang/spec/expressions.md#remainder-operator)
- [<span data-ttu-id="1973d-221">Additionsoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-221">Addition operator</span></span>](~/_csharplang/spec/expressions.md#addition-operator)
- [<span data-ttu-id="1973d-222">Subtraktionsoperator</span><span class="sxs-lookup"><span data-stu-id="1973d-222">Subtraction operator</span></span>](~/_csharplang/spec/expressions.md#subtraction-operator)
- [<span data-ttu-id="1973d-223">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="1973d-223">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="1973d-224">The checked and unchecked operators (Checked- und Unchecked-Operatoren)</span><span class="sxs-lookup"><span data-stu-id="1973d-224">The checked and unchecked operators</span></span>](~/_csharplang/spec/expressions.md#the-checked-and-unchecked-operators)
- [<span data-ttu-id="1973d-225">Numerische Heraufstufungen</span><span class="sxs-lookup"><span data-stu-id="1973d-225">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="1973d-226">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1973d-226">See also</span></span>

- [<span data-ttu-id="1973d-227">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1973d-227">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1973d-228">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1973d-228">C# operators and expressions</span></span>](index.md)
- <xref:System.Math?displayProperty=nameWithType>
- <xref:System.MathF?displayProperty=nameWithType>
- [<span data-ttu-id="1973d-229">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="1973d-229">Numerics in .NET</span></span>](../../../standard/numerics.md)
