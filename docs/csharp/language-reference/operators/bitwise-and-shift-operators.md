---
title: 'Bitweise und Schiebeoperatoren: C#-Referenz'
description: Enthält Informationen zu C#-Operatoren, die bitweise bzw. Schiebeoperationen mit Operanden mit integralen Typen durchführen.
ms.date: 04/18/2019
author: pkulikov
f1_keywords:
- ~_CSharpKeyword
- <<_CSharpKeyword
- '>>_CSharpKeyword'
- '&_CSharpKeyword'
- ^_CSharpKeyword
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise logical operators [C#]
- shift operators [C#]
- tilde operator [C#]
- one's complement operator [C#]
- bitwise complement operator [C#]
- ~ operator [C#]
- left shift operator [C#]
- << operator [C#]
- right shift operator [C#]
- '>> operator [C#]'
- bitwise logical AND operator [C#]
- ampersand operator [C#]
- '& operator [C#]'
- bitwise logical exclusive OR operator [C#]
- bitwise logical XOR operator [C#]
- ^ operator [C#]
- bitwise logical OR operator [C#]
- '| operator [C#]'
ms.openlocfilehash: f14b92aba270eab845ca50e5407da3502b5c4087
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345340"
---
# <a name="bitwise-and-shift-operators-c-reference"></a><span data-ttu-id="1667a-103">Bitweise und Schiebeoperatoren: C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1667a-103">Bitwise and shift operators (C# reference)</span></span>

<span data-ttu-id="1667a-104">Mit den folgenden Operatoren werden bitweise oder Verschiebevorgänge mit Operanden durchgeführt, die [integrale numerische Typen](../builtin-types/integral-numeric-types.md) oder den [char](../builtin-types/char.md)-Typ aufweisen:</span><span class="sxs-lookup"><span data-stu-id="1667a-104">The following operators perform bitwise or shift operations with operands of the [integral numeric types](../builtin-types/integral-numeric-types.md) or the [char](../builtin-types/char.md) type:</span></span>

- <span data-ttu-id="1667a-105">Unärer Operator [`~` (bitweises Komplement)](#bitwise-complement-operator-)</span><span class="sxs-lookup"><span data-stu-id="1667a-105">Unary [`~` (bitwise complement)](#bitwise-complement-operator-) operator</span></span>
- <span data-ttu-id="1667a-106">Binäre Schiebeoperatoren [`<<` (Linksverschiebung)](#left-shift-operator-) und [`>>` (Rechtsverschiebung)](#right-shift-operator-)</span><span class="sxs-lookup"><span data-stu-id="1667a-106">Binary [`<<` (left shift)](#left-shift-operator-) and [`>>` (right shift)](#right-shift-operator-) shift operators</span></span>
- <span data-ttu-id="1667a-107">Binäre Operatoren [`&` (logisches UND)](#logical-and-operator-), [`|` (logisches ODER)](#logical-or-operator-) und [`^` (logisches exklusives ODER)](#logical-exclusive-or-operator-)</span><span class="sxs-lookup"><span data-stu-id="1667a-107">Binary [`&` (logical AND)](#logical-and-operator-), [`|` (logical OR)](#logical-or-operator-), and [`^` (logical exclusive OR)](#logical-exclusive-or-operator-) operators</span></span>

<span data-ttu-id="1667a-108">Diese Operatoren werden für die Typen `int`, `uint`, `long` und `ulong` definiert.</span><span class="sxs-lookup"><span data-stu-id="1667a-108">Those operators are defined for the `int`, `uint`, `long`, and `ulong` types.</span></span> <span data-ttu-id="1667a-109">Wenn beide Operanden andere integrale Typen aufweisen (`sbyte`, `byte`, `short`, `ushort` oder `char`), werden ihre Werte in den Typ `int` konvertiert. Hierbei handelt es sich auch um den Ergebnistyp einer Operation.</span><span class="sxs-lookup"><span data-stu-id="1667a-109">When both operands are of other integral types (`sbyte`, `byte`, `short`, `ushort`, or `char`), their values are converted to the `int` type, which is also the result type of an operation.</span></span> <span data-ttu-id="1667a-110">Wenn die Operanden abweichende integrale Typen aufweisen, werden ihre Werte in den enthaltenden integralen Typ konvertiert, der am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="1667a-110">When operands are of different integral types, their values are converted to the closest containing integral type.</span></span> <span data-ttu-id="1667a-111">Weitere Informationen finden Sie im Abschnitt [Numerische Heraufstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-111">For more information, see the [Numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="1667a-112">Die Operatoren `&`, `|` und `^` werden auch für Operanden des `bool`-Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="1667a-112">The `&`, `|`, and `^` operators are also defined for operands of the `bool` type.</span></span> <span data-ttu-id="1667a-113">Weitere Informationen finden Sie unter [Logische boolesche Operatoren](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-113">For more information, see [Boolean logical operators](boolean-logical-operators.md).</span></span>

<span data-ttu-id="1667a-114">Bitweise und Schiebeoperationen verursachen niemals Überläufe und führen sowohl in [geprüften als auch in ungeprüften](../keywords/checked-and-unchecked.md) Kontexten zu identischen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="1667a-114">Bitwise and shift operations never cause overflow and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="bitwise-complement-operator-"></a><span data-ttu-id="1667a-115">Bitweiser Komplementoperator ~</span><span class="sxs-lookup"><span data-stu-id="1667a-115">Bitwise complement operator ~</span></span>

<span data-ttu-id="1667a-116">Mit dem Operator `~` wird ein bitweises Komplement seines Operanden erzeugt, indem jedes Bit umgekehrt wird:</span><span class="sxs-lookup"><span data-stu-id="1667a-116">The `~` operator produces a bitwise complement of its operand by reversing each bit:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseComplement)]

<span data-ttu-id="1667a-117">Sie können das Symbol `~` auch verwenden, um Finalizers zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="1667a-117">You can also use the `~` symbol to declare finalizers.</span></span> <span data-ttu-id="1667a-118">Weitere Informationen finden Sie unter [Finalizer](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-118">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

## <a name="left-shift-operator-"></a><span data-ttu-id="1667a-119">Operator für Linksverschiebung \<\<</span><span class="sxs-lookup"><span data-stu-id="1667a-119">Left-shift operator \<\<</span></span>

<span data-ttu-id="1667a-120">Mit dem Operator `<<` wird der linke Operand um die Anzahl von Bits nach links verschoben, die durch den rechten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1667a-120">The `<<` operator shifts its left-hand operand left by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="1667a-121">Bei der Operation zum Verschieben nach links werden die hohen Bits, die außerhalb des Bereichs des Ergebnistyps liegen, verworfen, und die niedrigen leeren Bitpositionen werden auf null festgelegt. Dies ist im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1667a-121">The left-shift operation discards the high-order bits that are outside the range of the result type and sets the low-order empty bit positions to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShift)]

<span data-ttu-id="1667a-122">Da die Verschiebeoperatoren nur für die Typen `int`, `uint`, `long` und `ulong` definiert werden, enthält das Ergebnis einer Operation immer mindestens 32 Bit.</span><span class="sxs-lookup"><span data-stu-id="1667a-122">Because the shift operators are defined only for the `int`, `uint`, `long`, and `ulong` types, the result of an operation always contains at least 32 bits.</span></span> <span data-ttu-id="1667a-123">Wenn der linke Operand einen abweichenden integralen Typ aufweist (`sbyte`, `byte`, `short`, `ushort` oder `char`), wird sein Wert in den Typ `int` konvertiert. Dies ist im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1667a-123">If the left-hand operand is of another integral type (`sbyte`, `byte`, `short`, `ushort`, or `char`), its value is converted to the `int` type, as the following example shows:</span></span>

[!code-csharp-interactive[left shift with promotion](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LeftShiftPromoted)]

<span data-ttu-id="1667a-124">Informationen dazu, wie der rechte Operand des Operators `<<` die Anzahl für die Verschiebung definiert, finden Sie im Abschnitt [Anzahl für die Verschiebung durch Schiebeoperatoren](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="1667a-124">For information about how the right-hand operand of the `<<` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="right-shift-operator-"></a><span data-ttu-id="1667a-125">Operator für Rechtsverschiebung >></span><span class="sxs-lookup"><span data-stu-id="1667a-125">Right-shift operator >></span></span>

<span data-ttu-id="1667a-126">Mit dem Operator `>>` wird der linke Operand um die Anzahl von Bits nach rechts verschoben, die durch den rechten Operanden angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1667a-126">The `>>` operator shifts its left-hand operand right by the number of bits defined by its right-hand operand.</span></span>

<span data-ttu-id="1667a-127">Bei der Operation zum Verschieben nach rechts werden die niedrigen Bits verworfen. Dies ist im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1667a-127">The right-shift operation discards the low-order bits, as the following example shows:</span></span>

[!code-csharp-interactive[right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#RightShift)]

<span data-ttu-id="1667a-128">Die höheren leeren Bitpositionen werden basierend auf dem Typ des linken Operanden wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="1667a-128">The high-order empty bit positions are set based on the type of the left-hand operand as follows:</span></span>

- <span data-ttu-id="1667a-129">Wenn der linke Operand vom Typ `int` oder `long` ist, führt der Operator zur Rechtsverschiebung eine *arithmetische* Verschiebung durch: Der Wert des Bits mit dem höchsten Stellenwert (MSB, „most significant bit“) des linken Operanden wird auf die hohen leeren Bitpositionen übertragen.</span><span class="sxs-lookup"><span data-stu-id="1667a-129">If the left-hand operand is of type `int` or `long`, the right-shift operator performs an *arithmetic* shift: the value of the most significant bit (the sign bit) of the left-hand operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="1667a-130">Die hohen leeren Bitpositionen werden daher auf 0 festgelegt, wenn der linke Operand nicht negativ ist, bzw. auf 1, wenn der linke Operand negativ ist.</span><span class="sxs-lookup"><span data-stu-id="1667a-130">That is, the high-order empty bit positions are set to zero if the left-hand operand is non-negative and set to one if it's negative.</span></span>

  [!code-csharp-interactive[arithmetic right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ArithmeticRightShift)]

- <span data-ttu-id="1667a-131">Wenn der linke Operand vom Typ `uint` oder `ulong` ist, führt der Operator zur Rechtsverschiebung eine *logische* Verschiebung durch: Die hohen leeren Bitpositionen werden immer auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1667a-131">If the left-hand operand is of type `uint` or `ulong`, the right-shift operator performs a *logical* shift: the high-order empty bit positions are always set to zero.</span></span>

  [!code-csharp-interactive[logical right shift](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#LogicalRightShift)]

<span data-ttu-id="1667a-132">Informationen dazu, wie der rechte Operand des Operators `>>` die Anzahl für die Verschiebung definiert, finden Sie im Abschnitt [Anzahl für die Verschiebung durch Schiebeoperatoren](#shift-count-of-the-shift-operators).</span><span class="sxs-lookup"><span data-stu-id="1667a-132">For information about how the right-hand operand of the `>>` operator defines the shift count, see the [Shift count of the shift operators](#shift-count-of-the-shift-operators) section.</span></span>

## <a name="logical-and-operator-"></a> <span data-ttu-id="1667a-133">Logischer AND-Operator &amp;</span><span class="sxs-lookup"><span data-stu-id="1667a-133">Logical AND operator &amp;</span></span>

<span data-ttu-id="1667a-134">Mit dem Operator `&` wird „bitweises logisches UND“ für die Operanden berechnet:</span><span class="sxs-lookup"><span data-stu-id="1667a-134">The `&` operator computes the bitwise logical AND of its operands:</span></span>

[!code-csharp-interactive[bitwise AND](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseAnd)]

<span data-ttu-id="1667a-135">Für `bool`-Operanden berechnet der `&`-Operator das [logische UND](boolean-logical-operators.md#logical-and-operator-) für die Operanden.</span><span class="sxs-lookup"><span data-stu-id="1667a-135">For `bool` operands, the `&` operator computes the [logical AND](boolean-logical-operators.md#logical-and-operator-) of its operands.</span></span> <span data-ttu-id="1667a-136">Der unäre `&`-Operator ist der [address-of-Operator](pointer-related-operators.md#address-of-operator-).</span><span class="sxs-lookup"><span data-stu-id="1667a-136">The unary `&` operator is the [address-of operator](pointer-related-operators.md#address-of-operator-).</span></span>

## <a name="logical-exclusive-or-operator-"></a><span data-ttu-id="1667a-137">Logischer exklusiver OR-Operator: ^</span><span class="sxs-lookup"><span data-stu-id="1667a-137">Logical exclusive OR operator ^</span></span>

<span data-ttu-id="1667a-138">Mit dem Operator `^` wird „bitweises logisches exklusives ODER“, auch als „bitweises logisches XOR“ bezeichnet, seiner Operanden berechnet:</span><span class="sxs-lookup"><span data-stu-id="1667a-138">The `^` operator computes the bitwise logical exclusive OR, also known as the bitwise logical XOR, of its operands:</span></span>

[!code-csharp-interactive[bitwise XOR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseXor)]

<span data-ttu-id="1667a-139">Für `bool`-Operanden berechnet der `^`-Operator das [logische exklusive ODER](boolean-logical-operators.md#logical-exclusive-or-operator-) für die Operanden.</span><span class="sxs-lookup"><span data-stu-id="1667a-139">For `bool` operands, the `^` operator computes the [logical exclusive OR](boolean-logical-operators.md#logical-exclusive-or-operator-) of its operands.</span></span>

## <a name="logical-or-operator-"></a><span data-ttu-id="1667a-140">Logischer OR-Operator: |</span><span class="sxs-lookup"><span data-stu-id="1667a-140">Logical OR operator |</span></span>

<span data-ttu-id="1667a-141">Mit dem Operator `|` wird „bitweises logisches ODER“ der Operanden berechnet:</span><span class="sxs-lookup"><span data-stu-id="1667a-141">The `|` operator computes the bitwise logical OR of its operands:</span></span>

[!code-csharp-interactive[bitwise OR](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#BitwiseOr)]

<span data-ttu-id="1667a-142">Für `bool`-Operanden berechnet der `|`-Operator das [logische ODER](boolean-logical-operators.md#logical-or-operator-) für die Operanden.</span><span class="sxs-lookup"><span data-stu-id="1667a-142">For `bool` operands, the `|` operator computes the [logical OR](boolean-logical-operators.md#logical-or-operator-) of its operands.</span></span>

## <a name="compound-assignment"></a><span data-ttu-id="1667a-143">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="1667a-143">Compound assignment</span></span>

<span data-ttu-id="1667a-144">Bei einem binären Operator `op` entspricht ein Verbundzuweisungsausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="1667a-144">For a binary operator `op`, a compound assignment expression of the form</span></span>

```csharp
x op= y
```

<span data-ttu-id="1667a-145">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1667a-145">is equivalent to</span></span>

```csharp
x = x op y
```

<span data-ttu-id="1667a-146">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1667a-146">except that `x` is only evaluated once.</span></span>

<span data-ttu-id="1667a-147">Im folgenden Beispiel wird die Verwendung von Verbundzuweisungen mit bitweisen und Schiebeoperatoren veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1667a-147">The following example demonstrates the usage of compound assignment with bitwise and shift operators:</span></span>

[!code-csharp-interactive[compound assignment](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignment)]

<span data-ttu-id="1667a-148">Aufgrund von [numerischen Höherstufungen](~/_csharplang/spec/expressions.md#numeric-promotions) kann das Ergebnis der Operation `op` ggf. nicht implizit in den Typ `T` von `x` konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1667a-148">Because of [numeric promotions](~/_csharplang/spec/expressions.md#numeric-promotions), the result of the `op` operation might be not implicitly convertible to the type `T` of `x`.</span></span> <span data-ttu-id="1667a-149">In diesem Fall gilt Folgendes: Wenn `op` ein vordefinierter Operator ist und das Ergebnis der Operation explizit in den Typ `T` von `x` konvertiert werden kann, entspricht ein Verbundzuweisungsausdruck der Form `x op= y` dem Ausdruck `x = (T)(x op y)`. Der einzige Unterschied ist, dass `x` nur einmal ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1667a-149">In such a case, if `op` is a predefined operator and the result of the operation is explicitly convertible to the type `T` of `x`, a compound assignment expression of the form `x op= y` is equivalent to `x = (T)(x op y)`, except that `x` is only evaluated once.</span></span> <span data-ttu-id="1667a-150">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="1667a-150">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[compound assignment with cast](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#CompoundAssignmentWithCast)]

## <a name="operator-precedence"></a><span data-ttu-id="1667a-151">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="1667a-151">Operator precedence</span></span>

<span data-ttu-id="1667a-152">In der folgenden Liste sind die bitweisen und Schiebeoperatoren absteigend nach Rangfolge sortiert:</span><span class="sxs-lookup"><span data-stu-id="1667a-152">The following list orders bitwise and shift operators starting from the highest precedence to the lowest:</span></span>

- <span data-ttu-id="1667a-153">Bitweiser Komplementoperator `~`</span><span class="sxs-lookup"><span data-stu-id="1667a-153">Bitwise complement operator `~`</span></span>
- <span data-ttu-id="1667a-154">Schiebeoperatoren `<<` und `>>`</span><span class="sxs-lookup"><span data-stu-id="1667a-154">Shift operators `<<` and `>>`</span></span>
- <span data-ttu-id="1667a-155">Logischer AND-Operator `&`</span><span class="sxs-lookup"><span data-stu-id="1667a-155">Logical AND operator `&`</span></span>
- <span data-ttu-id="1667a-156">Logischer exklusiver OR-Operator `^`</span><span class="sxs-lookup"><span data-stu-id="1667a-156">Logical exclusive OR operator `^`</span></span>
- <span data-ttu-id="1667a-157">Logischer OR-Operator `|`</span><span class="sxs-lookup"><span data-stu-id="1667a-157">Logical OR operator `|`</span></span>

<span data-ttu-id="1667a-158">Verwenden Sie Klammern `()`, wenn Sie die Reihenfolge der Auswertung ändern möchten, die durch Operatorrangfolge festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="1667a-158">Use parentheses, `()`, to change the order of evaluation imposed by operator precedence:</span></span>

[!code-csharp-interactive[operator precedence](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#Precedence)]

<span data-ttu-id="1667a-159">Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie im Abschnitt [Operatorrangfolge](index.md#operator-precedence) im Artikel [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-159">For the complete list of C# operators ordered by precedence level, see the [Operator precedence](index.md#operator-precedence) section of the [C# operators](index.md) article.</span></span>

## <a name="shift-count-of-the-shift-operators"></a><span data-ttu-id="1667a-160">Anzahl für die Verschiebung durch Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="1667a-160">Shift count of the shift operators</span></span>

<span data-ttu-id="1667a-161">Für die Schiebeoperatoren `<<` und `>>` muss der Typ des rechten Operanden `int` lauten oder ein Typ sein, der eine [vordefinierte, implizite numerische Konvertierung](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) in `int` aufweist.</span><span class="sxs-lookup"><span data-stu-id="1667a-161">For the shift operators `<<` and `>>`, the type of the right-hand operand must be `int` or a type that has a [predefined implicit numeric conversion](../builtin-types/numeric-conversions.md#implicit-numeric-conversions) to `int`.</span></span>

<span data-ttu-id="1667a-162">Für die Ausdrücke `x << count` und `x >> count` hängt die tatsächliche Verschiebungsanzahl wie folgt vom Typ von `x` ab:</span><span class="sxs-lookup"><span data-stu-id="1667a-162">For the `x << count` and `x >> count` expressions, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="1667a-163">Lautet der Typ von `x``int` oder `uint`, wird die Verschiebungsanzahl durch die niedrigen *fünf* Bits des rechten Operanden definiert.</span><span class="sxs-lookup"><span data-stu-id="1667a-163">If the type of `x` is `int` or `uint`, the shift count is defined by the low-order *five* bits of the right-hand operand.</span></span> <span data-ttu-id="1667a-164">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x1F` (oder `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="1667a-164">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="1667a-165">Lautet der Typ von `x``long` oder `ulong`, wird die Verschiebungsanzahl durch die niedrigen *sechs* Bits des rechten Operanden definiert.</span><span class="sxs-lookup"><span data-stu-id="1667a-165">If the type of `x` is `long` or `ulong`, the shift count is defined by the low-order *six* bits of the right-hand operand.</span></span> <span data-ttu-id="1667a-166">Die Verschiebungsanzahl errechnet sich daher aus `count & 0x3F` (oder `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="1667a-166">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="1667a-167">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="1667a-167">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/csharp/language-reference/operators/BitwiseAndShiftOperators.cs#ShiftCount)]

## <a name="enumeration-logical-operators"></a><span data-ttu-id="1667a-168">Logische Enumerationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="1667a-168">Enumeration logical operators</span></span>

<span data-ttu-id="1667a-169">Die Operatoren `~`, `&`, `|` und `^` werden auch von jedem [Enumerationstyp](../builtin-types/enum.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1667a-169">The `~`, `&`, `|`, and `^` operators are also supported by any [enumeration](../builtin-types/enum.md) type.</span></span> <span data-ttu-id="1667a-170">Für Operanden mit dem gleichen Enumerationstyp wird ein logischer Vorgang für die entsprechenden Werte des zugrunde liegenden integralen Typs durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1667a-170">For operands of the same enumeration type, a logical operation is performed on the corresponding values of the underlying integral type.</span></span> <span data-ttu-id="1667a-171">Für alle `x`- und `y`-Elemente des Enumerationstyps `T` mit dem zugrunde liegenden Typ `U` führt der Ausdruck `x & y` zum gleichen Ergebnis wie der Ausdruck `(T)((U)x & (U)y)`.</span><span class="sxs-lookup"><span data-stu-id="1667a-171">For example, for any `x` and `y` of an enumeration type `T` with an underlying type `U`, the `x & y` expression produces the same result as the `(T)((U)x & (U)y)` expression.</span></span>

<span data-ttu-id="1667a-172">Normalerweise verwenden Sie bitweise logische Operatoren mit einem Enumerationstyp, der mit dem [Flags](xref:System.FlagsAttribute)-Attribut definiert wird.</span><span class="sxs-lookup"><span data-stu-id="1667a-172">You typically use bitwise logical operators with an enumeration type which is defined with the [Flags](xref:System.FlagsAttribute) attribute.</span></span> <span data-ttu-id="1667a-173">Weitere Informationen finden Sie im Abschnitt [Enumerationstypen als Bitflags](../builtin-types/enum.md#enumeration-types-as-bit-flags) des Artikels [Enumerationstypen](../builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-173">For more information, see the [Enumeration types as bit flags](../builtin-types/enum.md#enumeration-types-as-bit-flags) section of the [Enumeration types](../builtin-types/enum.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="1667a-174">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="1667a-174">Operator overloadability</span></span>

<span data-ttu-id="1667a-175">Ein benutzerdefinierter Typ kann die Operatoren `~`, `<<`, `>>`, `&`, `|` und `^`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="1667a-175">A user-defined type can [overload](operator-overloading.md) the `~`, `<<`, `>>`, `&`, `|`, and `^` operators.</span></span> <span data-ttu-id="1667a-176">Wenn ein binärer Operator überladen ist, wird der zugehörige Verbundzuweisungsoperator implizit auch überladen.</span><span class="sxs-lookup"><span data-stu-id="1667a-176">When a binary operator is overloaded, the corresponding compound assignment operator is also implicitly overloaded.</span></span> <span data-ttu-id="1667a-177">Ein benutzerdefinierter Typ kann einen Verbundzuweisungsoperator nicht explizit überladen.</span><span class="sxs-lookup"><span data-stu-id="1667a-177">A user-defined type cannot explicitly overload a compound assignment operator.</span></span>

<span data-ttu-id="1667a-178">Wenn ein benutzerdefinierter Typ `T` den Operator `<<` oder `>>` überlädt, muss der Typ des linken Operanden `T` und der Typ des rechten Operanden `int` lauten.</span><span class="sxs-lookup"><span data-stu-id="1667a-178">If a user-defined type `T` overloads the `<<` or `>>` operator, the type of the left-hand operand must be `T` and the type of the right-hand operand must be `int`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1667a-179">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1667a-179">C# language specification</span></span>

<span data-ttu-id="1667a-180">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="1667a-180">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="1667a-181">Bitweiser Komplementoperator</span><span class="sxs-lookup"><span data-stu-id="1667a-181">Bitwise complement operator</span></span>](~/_csharplang/spec/expressions.md#bitwise-complement-operator)
- [<span data-ttu-id="1667a-182">Shift operators (Schiebeoperatoren)</span><span class="sxs-lookup"><span data-stu-id="1667a-182">Shift operators</span></span>](~/_csharplang/spec/expressions.md#shift-operators)
- [<span data-ttu-id="1667a-183">Logical operators (Logische Operatoren)</span><span class="sxs-lookup"><span data-stu-id="1667a-183">Logical operators</span></span>](~/_csharplang/spec/expressions.md#logical-operators)
- [<span data-ttu-id="1667a-184">Verbundzuweisung</span><span class="sxs-lookup"><span data-stu-id="1667a-184">Compound assignment</span></span>](~/_csharplang/spec/expressions.md#compound-assignment)
- [<span data-ttu-id="1667a-185">Numerische Heraufstufungen</span><span class="sxs-lookup"><span data-stu-id="1667a-185">Numeric promotions</span></span>](~/_csharplang/spec/expressions.md#numeric-promotions)

## <a name="see-also"></a><span data-ttu-id="1667a-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1667a-186">See also</span></span>

- [<span data-ttu-id="1667a-187">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1667a-187">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1667a-188">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1667a-188">C# operators</span></span>](index.md)
- [<span data-ttu-id="1667a-189">Logische boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="1667a-189">Boolean logical operators</span></span>](boolean-logical-operators.md)
