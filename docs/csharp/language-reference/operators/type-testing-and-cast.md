---
title: 'Typtest- und Umwandlungsoperatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Operatoren, mit denen Sie den Typ eines Ausdrucksergebnisses überprüfen und bei Bedarf in einen anderen Typ konvertieren können.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: c3550a593eafb9b50fa7e419e2f747c3e7a0e2ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972651"
---
# <a name="type-testing-and-cast-operators-c-reference"></a><span data-ttu-id="0b8b9-103">Typtest- und Umwandlungsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0b8b9-103">Type-testing and cast operators (C# reference)</span></span>

<span data-ttu-id="0b8b9-104">Sie können die folgenden Operatoren zur Überprüfung oder Konvertierung von Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-104">You can use the following operators to perform type checking or type conversion:</span></span>

- <span data-ttu-id="0b8b9-105">[is-Operator](#is-operator): Prüft, ob der Laufzeittyp eines Ausdrucks mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-105">[is operator](#is-operator): to check if the runtime type of an expression is compatible with a given type</span></span>
- <span data-ttu-id="0b8b9-106">[as-Operator](#as-operator): Konvertiert einen Ausdruck explizit in einen angegebenen Typ, wenn der Laufzeittyp mit diesem Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-106">[as operator](#as-operator): to explicitly convert an expression to a given type if its runtime type is compatible with that type</span></span>
- <span data-ttu-id="0b8b9-107">[cast-Operator ()](#cast-operator-): Führt eine explizite Konvertierung durch.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-107">[cast operator ()](#cast-operator-): to perform an explicit conversion</span></span>
- <span data-ttu-id="0b8b9-108">[typeof-Operator](#typeof-operator): Ruft die <xref:System.Type?displayProperty=nameWithType>-Instanz für einen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-108">[typeof operator](#typeof-operator): to obtain the <xref:System.Type?displayProperty=nameWithType> instance for a type</span></span>

## <a name="is-operator"></a><span data-ttu-id="0b8b9-109">is-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-109">is operator</span></span>

<span data-ttu-id="0b8b9-110">Der `is`-Operator prüft, ob der Laufzeittyp eines Ausdrucksergebnisses mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-110">The `is` operator checks if the runtime type of an expression result is compatible with a given type.</span></span> <span data-ttu-id="0b8b9-111">Ab C# 7.0 überprüft der `is`-Operator ein Ausdrucksergebnis auch anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-111">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span>

<span data-ttu-id="0b8b9-112">Der Ausdruck mit dem `is`-Operator für die Typüberprüfung weist folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-112">The expression with the type-testing `is` operator has the following form</span></span>

```csharp
E is T
```

<span data-ttu-id="0b8b9-113">Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, und `T` ist der Name eines Typs oder Typparameters.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-113">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter.</span></span> <span data-ttu-id="0b8b9-114">`E` kann weder eine anonyme Methode noch ein Lambdaausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-114">`E` cannot be an anonymous method or a lambda expression.</span></span>

<span data-ttu-id="0b8b9-115">Der `E is T`-Ausdruck gibt `true` zurück, wenn das Ergebnis von `E` nicht NULL ist und durch eine Verweis-, eine Boxing- oder eine Unboxingkonvertierung in den Typ `T` konvertiert werden kann. Andernfalls gibt der Ausdruck `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-115">The `E is T` expression returns `true` if the result of `E` is non-null and can be converted to type `T` by a reference conversion, a boxing conversion, or an unboxing conversion; otherwise, it returns `false`.</span></span> <span data-ttu-id="0b8b9-116">Der `is`-Operator berücksichtigt keine benutzerdefinierten Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-116">The `is` operator doesn't consider user-defined conversions.</span></span>

<span data-ttu-id="0b8b9-117">Das folgende Beispiel zeigt, dass der `is`-Operator `true` zurückgibt, wenn der Laufzeittyp eines Ausdrucksergebnisses von einem angegebenen Typ abgeleitet ist, wenn also eine Verweiskonvertierung zwischen Typen besteht:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-117">The following example demonstrates that the `is` operator returns `true` if the runtime type of an expression result derives from a given type, that is, there exists a reference conversion between types:</span></span>

[!code-csharp[is with reference conversion](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

<span data-ttu-id="0b8b9-118">Das nächste Beispiel zeigt, dass der `is`-Operator Boxing- und Unboxingkonvertierungen berücksichtigt, [numerische Konvertierungen](../builtin-types/numeric-conversions.md) aber nicht:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-118">The next example shows that the `is` operator takes into account boxing and unboxing conversions but doesn't consider [numeric conversions](../builtin-types/numeric-conversions.md):</span></span>

[!code-csharp-interactive[is with int](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithInt)]

<span data-ttu-id="0b8b9-119">Informationen zu C#-Konvertierungen finden Sie im Kapitel [Konvertierungen](~/_csharplang/spec/conversions.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-119">For information about C# conversions, see the [Conversions](~/_csharplang/spec/conversions.md) chapter of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

### <a name="type-testing-with-pattern-matching"></a><span data-ttu-id="0b8b9-120">Typüberprüfung mit Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="0b8b9-120">Type testing with pattern matching</span></span>

<span data-ttu-id="0b8b9-121">Ab C# 7.0 überprüft der `is`-Operator ein Ausdrucksergebnis auch anhand eines Musters.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-121">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span> <span data-ttu-id="0b8b9-122">Insbesondere wird das Typmuster in der folgenden Form unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-122">In particular, it supports the type pattern in the following form:</span></span>

```csharp
E is T v
```

<span data-ttu-id="0b8b9-123">Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, `T` ist der Name eines Typs oder Typparameters, und `v` ist eine neue lokale Variable des Typs `T`.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-123">where `E` is an expression that returns a value, `T` is the name of a type or a type parameter, and `v` is a new local variable of type `T`.</span></span> <span data-ttu-id="0b8b9-124">Wenn das Ergebnis von `E` ungleich NULL ist und durch eine Verweis-, eine Boxing- oder eine Unboxingkonvertierung in `T` konvertiert werden kann, gibt der `E is T v`-Ausdruck `true` zurück, und der konvertierte Wert des Ergebnisses von `E` wird der Variable `v` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-124">If the result of `E` is non-null and can be converted to `T` by a reference, boxing, or unboxing conversion, the `E is T v` expression returns `true` and the converted value of the result of `E` is assigned to variable `v`.</span></span>

<span data-ttu-id="0b8b9-125">Das folgende Beispiel veranschaulicht die Verwendung des `is`-Operators mit dem Typmuster:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-125">The following example demonstrates the usage of the `is` operator with the type pattern:</span></span>

[!code-csharp-interactive[is with type pattern](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsTypePattern)]

<span data-ttu-id="0b8b9-126">Weitere Informationen zum Typmuster und weiteren unterstützten Mustern finden Sie unter [Musterabgleich mit „is“](../keywords/is.md#pattern-matching-with-is).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-126">For more information about the type pattern and other supported patterns, see [Pattern matching with is](../keywords/is.md#pattern-matching-with-is).</span></span>

## <a name="as-operator"></a><span data-ttu-id="0b8b9-127">as-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-127">as operator</span></span>

<span data-ttu-id="0b8b9-128">Der `as`-Operator konvertiert das Ergebnis eines Ausdrucks explizit in einen angegebenen Verweis- oder Nullable-Typ.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-128">The `as` operator explicitly converts the result of an expression to a given reference or nullable value type.</span></span> <span data-ttu-id="0b8b9-129">Wenn die Konvertierung nicht möglich ist, gibt der `as`-Operator `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-129">If the conversion is not possible, the `as` operator returns `null`.</span></span> <span data-ttu-id="0b8b9-130">Im Gegensatz zum [cast-Operator ()](#cast-operator-) löst der `as`-Operator nie eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-130">Unlike the [cast operator ()](#cast-operator-), the `as` operator never throws an exception.</span></span>

<span data-ttu-id="0b8b9-131">Sehen Sie sich diesen Ausdruck an:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-131">The expression of the form</span></span>

```csharp
E as T
```

<span data-ttu-id="0b8b9-132">Hierbei ist `E` ein Ausdruck, der einen Wert zurückgibt, und `T` ist der Name eines Typs oder Typparameters. Das führt zum gleichen Ergebnis wie dies:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-132">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter, produces the same result as</span></span>

```csharp
E is T ? (T)(E) : (T)null
```

<span data-ttu-id="0b8b9-133">außer dass `E` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-133">except that `E` is only evaluated once.</span></span>

<span data-ttu-id="0b8b9-134">Der `as`-Operator berücksichtigt nur Verweis-, Nullable-, Boxing- und Unboxingkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-134">The `as` operator considers only reference, nullable, boxing, and unboxing conversions.</span></span> <span data-ttu-id="0b8b9-135">Sie können den `as`-Operator nicht verwenden, um eine benutzerdefinierte Konvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-135">You cannot use the `as` operator to perform a user-defined conversion.</span></span> <span data-ttu-id="0b8b9-136">Verwenden Sie zu diesem Zweck den [cast-Operator ()](#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-136">To do that, use the [cast operator ()](#cast-operator-).</span></span>

<span data-ttu-id="0b8b9-137">Im folgenden Beispiel wird die Verwendung des `as`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-137">The following example demonstrates the usage of the `as` operator:</span></span>

[!code-csharp-interactive[as operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> <span data-ttu-id="0b8b9-138">Wie das vorherige Beispiel zeigt, müssen Sie das Ergebnis des `as`-Ausdrucks mit `null` vergleichen, um zu überprüfen, ob die Konvertierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-138">As the preceding example shows, you need to compare the result of the `as` expression with `null` to check if the conversion is successful.</span></span> <span data-ttu-id="0b8b9-139">Ab C# 7.0 können Sie den [is-Operator](#type-testing-with-pattern-matching) verwenden, um sowohl die erfolgreiche Durchführung der Konvertierung zu überprüfen als auch bei Erfolg das Ergebnis einer neuen Variable zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-139">Beginning with C# 7.0, you can use the [is operator](#type-testing-with-pattern-matching) both to test if the conversion succeeds and, if it succeeds, assign its result to a new variable.</span></span>

## <a name="cast-operator-"></a><span data-ttu-id="0b8b9-140">Umwandlungsoperator ()</span><span class="sxs-lookup"><span data-stu-id="0b8b9-140">Cast operator ()</span></span>

<span data-ttu-id="0b8b9-141">Ein cast-Ausdruck der Form `(T)E` führt eine explizite Konvertierung des Ergebnisses des Ausdrucks `E` in den Typ `T` durch.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-141">A cast expression of the form `(T)E` performs an explicit conversion of the result of expression `E` to type `T`.</span></span> <span data-ttu-id="0b8b9-142">Wenn keine explizite Konvertierung von Typ `E` in Typ `T` möglich ist, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-142">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="0b8b9-143">Möglicherweise ist eine explizite Konvertierung zur Laufzeit nicht erfolgreich, und ein cast-Ausdruck löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-143">At run time, an explicit conversion might not succeed and a cast expression might throw an exception.</span></span>

<span data-ttu-id="0b8b9-144">Das folgende Beispiel zeigt explizite numerische und Verweiskonvertierungen:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-144">The following example demonstrates explicit numeric and reference conversions:</span></span>

[!code-csharp-interactive[cast expression](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#Cast)]

<span data-ttu-id="0b8b9-145">Informationen zu expliziten Konvertierungen finden Sie im Abschnitt [Explizite Konvertierungen](~/_csharplang/spec/conversions.md#explicit-conversions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-145">For information about supported explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="0b8b9-146">Informationen zum Definieren einer benutzerdefinierten expliziten oder impliziten Typkonvertierung finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-146">For information about how to define a custom explicit or implicit type conversion, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="0b8b9-147">Andere Verwendungen von „()“</span><span class="sxs-lookup"><span data-stu-id="0b8b9-147">Other usages of ()</span></span>

<span data-ttu-id="0b8b9-148">Sie verwenden Klammern auch zum [Aufrufen einer Methode oder eines Delegaten](member-access-operators.md#invocation-operator-).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-148">You also use parentheses to [call a method or invoke a delegate](member-access-operators.md#invocation-operator-).</span></span>

<span data-ttu-id="0b8b9-149">Mit Klammern können Sie auch die Reihenfolge anpassen, in der Vorgänge in einem Ausdruck ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-149">Other use of parentheses is to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="0b8b9-150">Weitere Informationen finden Sie unter [C#-Operatoren](index.md).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-150">For more information, see [C# operators](index.md).</span></span>

## <a name="typeof-operator"></a><span data-ttu-id="0b8b9-151">typeof-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-151">typeof operator</span></span>

<span data-ttu-id="0b8b9-152">Der `typeof`-Operator ruft die <xref:System.Type?displayProperty=nameWithType>-Instanz für einen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-152">The `typeof` operator obtains the <xref:System.Type?displayProperty=nameWithType> instance for a type.</span></span> <span data-ttu-id="0b8b9-153">Das Argument für den `typeof`-Operator muss der Name eines Typs oder Typparameters sein, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-153">The argument to the `typeof` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[typeof operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOf)]

<span data-ttu-id="0b8b9-154">Sie können den `typeof`-Operator auch mit ungebundenen generischen Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-154">You also can use the `typeof` operator with unbound generic types.</span></span> <span data-ttu-id="0b8b9-155">Der Name eines ungebundenen generischen Typs muss die entsprechende Anzahl von Kommas enthalten: eines weniger als die Anzahl von Typparametern.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-155">The name of an unbound generic type must contain the appropriate number of commas, which is one less than the number of type parameters.</span></span> <span data-ttu-id="0b8b9-156">Das folgende Beispiel zeigt die Verwendung des `typeof`-Operators mit einem ungebundenen generischen Typ:</span><span class="sxs-lookup"><span data-stu-id="0b8b9-156">The following example shows the usage of the `typeof` operator with an unbound generic type:</span></span>

[!code-csharp-interactive[typeof unbound generic](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

<span data-ttu-id="0b8b9-157">Ein Ausdruck kann kein Argument des `typeof`-Operators sein.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-157">An expression cannot be an argument of the `typeof` operator.</span></span> <span data-ttu-id="0b8b9-158">Verwenden Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um die <xref:System.Type?displayProperty=nameWithType>-Instanz für den Laufzeittyp eines Ausdrucksergebnisses abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-158">To get the <xref:System.Type?displayProperty=nameWithType> instance for the runtime type of an expression result, use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method.</span></span>

### <a name="type-testing-with-the-typeof-operator"></a><span data-ttu-id="0b8b9-159">Typüberprüfung mit dem `typeof`-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-159">Type testing with the `typeof` operator</span></span>

<span data-ttu-id="0b8b9-160">Verwenden Sie den `typeof`-Operator, um zu überprüfen, ob der Laufzeittyp des Ausdrucksergebnisses exakt mit einem angegebenen Typ übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-160">Use the `typeof` operator to check if the runtime type of the expression result exactly matches a given type.</span></span> <span data-ttu-id="0b8b9-161">Das folgende Beispiel zeigt den Unterschied zwischen der Typüberprüfung mit dem `typeof`-Operator und mit dem [is-Operator](#is-operator):</span><span class="sxs-lookup"><span data-stu-id="0b8b9-161">The following example demonstrates the difference between type checking performed with the `typeof` operator and the [is operator](#is-operator):</span></span>

[!code-csharp[typeof vs is](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a><span data-ttu-id="0b8b9-162">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="0b8b9-162">Operator overloadability</span></span>

<span data-ttu-id="0b8b9-163">Die Operatoren `is`, `as` und `typeof` können nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-163">The `is`, `as`, and `typeof` operators cannot be overloaded.</span></span>

<span data-ttu-id="0b8b9-164">Ein benutzerdefinierter Typ kann den `()`-Operator nicht überladen, kann aber benutzerdefinierte Typkonvertierungen definieren, die durch einen cast-Ausdruck ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="0b8b9-164">A user-defined type cannot overload the `()` operator, but can define custom type conversions that can be performed by a cast expression.</span></span> <span data-ttu-id="0b8b9-165">Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0b8b9-165">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0b8b9-166">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="0b8b9-166">C# language specification</span></span>

<span data-ttu-id="0b8b9-167">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0b8b9-167">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0b8b9-168">Der is-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-168">The is operator</span></span>](~/_csharplang/spec/expressions.md#the-is-operator)
- [<span data-ttu-id="0b8b9-169">Der as-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-169">The as operator</span></span>](~/_csharplang/spec/expressions.md#the-as-operator)
- [<span data-ttu-id="0b8b9-170">cast-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0b8b9-170">Cast expressions</span></span>](~/_csharplang/spec/expressions.md#cast-expressions)
- [<span data-ttu-id="0b8b9-171">Der typeof-Operator</span><span class="sxs-lookup"><span data-stu-id="0b8b9-171">The typeof operator</span></span>](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a><span data-ttu-id="0b8b9-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b8b9-172">See also</span></span>

- [<span data-ttu-id="0b8b9-173">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0b8b9-173">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0b8b9-174">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0b8b9-174">C# operators</span></span>](index.md)
- [<span data-ttu-id="0b8b9-175">Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „is“ und „as“</span><span class="sxs-lookup"><span data-stu-id="0b8b9-175">How to safely cast by using pattern matching and the is and as operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="0b8b9-176">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="0b8b9-176">Generics in .NET</span></span>](../../../standard/generics/index.md)
