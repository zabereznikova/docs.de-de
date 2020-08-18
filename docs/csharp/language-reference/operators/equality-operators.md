---
title: Gleichheitsoperatoren – C#-Referenz
description: Erfahren Sie mehr über Gleichheitsvergleichsoperatoren und C#-Typengleichheit.
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 33215e2440b14fb888a6f0df5c220c891ebed0e2
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063093"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="92f2e-103">Gleichheitsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="92f2e-103">Equality operators (C# reference)</span></span>

<span data-ttu-id="92f2e-104">Die Operatoren [`==` (Gleichheit)](#equality-operator-) und [`!=` (Ungleichheit)](#inequality-operator-) überprüfen, ob die Operanden gleich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="92f2e-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="92f2e-105">Gleichheitsoperator ==</span><span class="sxs-lookup"><span data-stu-id="92f2e-105">Equality operator ==</span></span>

<span data-ttu-id="92f2e-106">Der Gleichheitsoperator `==` gibt `true` zurück, wenn die Operanden gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="92f2e-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="92f2e-107">Gleichheit von Werttypen</span><span class="sxs-lookup"><span data-stu-id="92f2e-107">Value types equality</span></span>

<span data-ttu-id="92f2e-108">Operanden der [integrierten Werttypen](../builtin-types/value-types.md#built-in-value-types) sind gleich, wenn ihre Werte gleich sind:</span><span class="sxs-lookup"><span data-stu-id="92f2e-108">Operands of the [built-in value types](../builtin-types/value-types.md#built-in-value-types) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](snippets/shared/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="92f2e-109">Bei den Operatoren `==`, [`<`, `>`, `<=` und `>=`](comparison-operators.md) ist das Ergebnis eines Vorgangs `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="92f2e-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="92f2e-110">Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`.</span><span class="sxs-lookup"><span data-stu-id="92f2e-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="92f2e-111">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="92f2e-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="92f2e-112">Zwei Operanden desselben [enum](../builtin-types/enum.md)-Typs sind gleich, wenn die entsprechenden Werte des zugrunde liegenden integralen Typs gleich sind.</span><span class="sxs-lookup"><span data-stu-id="92f2e-112">Two operands of the same [enum](../builtin-types/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="92f2e-113">Benutzerdefinierte [Strukturtypen](../builtin-types/struct.md) unterstützen den `==`-Operator nicht standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="92f2e-113">User-defined [struct](../builtin-types/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="92f2e-114">Eine benutzerdefinierte Struktur muss den `==`-Operator [überladen](operator-overloading.md), damit er unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="92f2e-114">To support the `==` operator, a user-defined struct must [overload](operator-overloading.md) it.</span></span>

<span data-ttu-id="92f2e-115">Ab C# 7.3 werden die Operatoren `==` und `!=` für [C#-Tupel](../builtin-types/value-tuples.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="92f2e-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../builtin-types/value-tuples.md).</span></span> <span data-ttu-id="92f2e-116">Weitere Informationen finden Sie im Abschnitt [Tupelgleichheit](../builtin-types/value-tuples.md#tuple-equality) im Artikel [Tupeltypen](../builtin-types/value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-116">For more information, see the [Tuple equality](../builtin-types/value-tuples.md#tuple-equality) section of the [Tuple types](../builtin-types/value-tuples.md) article.</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="92f2e-117">Gleichheit von Verweistypen</span><span class="sxs-lookup"><span data-stu-id="92f2e-117">Reference types equality</span></span>

<span data-ttu-id="92f2e-118">Standardmäßig sind zwei Verweistypoperanden gleich, wenn sie auf dasselbe Objekt verweisen:</span><span class="sxs-lookup"><span data-stu-id="92f2e-118">By default, two reference-type operands are equal if they refer to the same object:</span></span>

[!code-csharp[reference type equality](snippets/shared/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="92f2e-119">Das Beispiel zeigt, dass benutzerdefinierte Verweistypen den `==`-Operator standardmäßig unterstützen.</span><span class="sxs-lookup"><span data-stu-id="92f2e-119">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="92f2e-120">Ein Verweistyp kann den Operator `==` aber überladen.</span><span class="sxs-lookup"><span data-stu-id="92f2e-120">However, a reference type can overload the `==` operator.</span></span> <span data-ttu-id="92f2e-121">Wenn ein Verweistyp den `==`-Operator überlädt, verwenden Sie die <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode, um zu überprüfen, ob zwei Verweise dieses Typs auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="92f2e-121">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

### <a name="string-equality"></a><span data-ttu-id="92f2e-122">Zeichenfolgengleichheit</span><span class="sxs-lookup"><span data-stu-id="92f2e-122">String equality</span></span>

<span data-ttu-id="92f2e-123">Zwei [Zeichenfolge](../builtin-types/reference-types.md#the-string-type)-Operanden gleich sind, wenn beide gleich `null` sind oder wenn beide Zeichenfolgeninstanzen dieselbe Länge und identische Zeichen in jeder Zeichenposition haben:</span><span class="sxs-lookup"><span data-stu-id="92f2e-123">Two [string](../builtin-types/reference-types.md#the-string-type) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](snippets/shared/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="92f2e-124">Dies ist ein Ordinalvergleich unter Berücksichtigung der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="92f2e-124">That is a case-sensitive ordinal comparison.</span></span> <span data-ttu-id="92f2e-125">Weitere Informationen zum Zeichenfolgenvergleich finden Sie unter [Vergleichen von Zeichenfolgen in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-125">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="delegate-equality"></a><span data-ttu-id="92f2e-126">Delegatengleichheit</span><span class="sxs-lookup"><span data-stu-id="92f2e-126">Delegate equality</span></span>

<span data-ttu-id="92f2e-127">Zwei [delegate](../../programming-guide/delegates/index.md)-Operanden mit demselben Laufzeittyp sind gleich, wenn beide `null` lauten oder ihre Aufruflisten die gleiche Länge aufweisen und an jeder Position gleiche Einträge umfassen:</span><span class="sxs-lookup"><span data-stu-id="92f2e-127">Two [delegate](../../programming-guide/delegates/index.md) operands of the same runtime type are equal when both of them are `null` or their invocation lists are of the same length and have equal entries in each position:</span></span>

[!code-csharp-interactive[delegate equality](snippets/shared/EqualityOperators.cs#DelegateEquality)]

<span data-ttu-id="92f2e-128">Weitere Informationen finden Sie im Abschnitt [Operatoren für Delegatengleichheit](~/_csharplang/spec/expressions.md#delegate-equality-operators) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-128">For more information, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="92f2e-129">Delegaten, die durch die Auswertung semantisch identischer [Lambdaausdrücke](lambda-expressions.md) erzeugt werden, sind beispielsweise nicht gleich. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="92f2e-129">Delegates that are produced from evaluation of semantically identical [lambda expressions](lambda-expressions.md) are not equal, as the following example shows:</span></span>

[!code-csharp-interactive[from identical lambdas](snippets/shared/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a><span data-ttu-id="92f2e-130">Ungleichheitsoperator !=</span><span class="sxs-lookup"><span data-stu-id="92f2e-130">Inequality operator !=</span></span>

<span data-ttu-id="92f2e-131">Der Ungleichheitsoperator `!=` gibt `true` zurück, wenn die Operanden nicht gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="92f2e-131">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="92f2e-132">Für die Operanden der [integrierten Typen](../builtin-types/built-in-types.md) führt der Ausdruck `x != y` zum selben Ergebnis wie der Ausdruck `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="92f2e-132">For the operands of the [built-in types](../builtin-types/built-in-types.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="92f2e-133">Weitere Informationen zur Typengleichheit finden Sie im Abschnitt [Gleichheitsoperator](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="92f2e-133">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="92f2e-134">Im folgenden Beispiel wird die Verwendung des `!=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="92f2e-134">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](snippets/shared/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="92f2e-135">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="92f2e-135">Operator overloadability</span></span>

<span data-ttu-id="92f2e-136">Ein benutzerdefinierter Typ kann die Operatoren `==` und `!=`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-136">A user-defined type can [overload](operator-overloading.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="92f2e-137">Wenn ein Typ einen der zwei Operatoren überlädt, muss er auch den anderen Operator überladen.</span><span class="sxs-lookup"><span data-stu-id="92f2e-137">If a type overloads one of the two operators, it must also overload the other one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="92f2e-138">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="92f2e-138">C# language specification</span></span>

<span data-ttu-id="92f2e-139">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-139">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92f2e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92f2e-140">See also</span></span>

- [<span data-ttu-id="92f2e-141">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="92f2e-141">C# reference</span></span>](../index.md)
- [<span data-ttu-id="92f2e-142">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="92f2e-142">C# operators and expressions</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="92f2e-143">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="92f2e-143">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="92f2e-144">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="92f2e-144">Comparison operators</span></span>](comparison-operators.md)
