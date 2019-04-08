---
title: Gleichheitsoperatoren – C#-Referenz
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 98b96f5b4c6d6ea70687a97c849e89573c67c37e
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545891"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="db4cf-102">Gleichheitsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="db4cf-102">Equality operators (C# Reference)</span></span>

<span data-ttu-id="db4cf-103">Die Operatoren [`==` (Gleichheit)](#equality-operator-) und [`!=` (Ungleichheit)](#inequality-operator-) überprüfen, ob die Operanden gleich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="db4cf-103">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="db4cf-104">Gleichheitsoperator ==</span><span class="sxs-lookup"><span data-stu-id="db4cf-104">Equality operator ==</span></span>

<span data-ttu-id="db4cf-105">Der Gleichheitsoperator `==` gibt `true` zurück, wenn die Operanden gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="db4cf-105">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="db4cf-106">Gleichheit von Werttypen</span><span class="sxs-lookup"><span data-stu-id="db4cf-106">Value types equality</span></span>

<span data-ttu-id="db4cf-107">Operanden der [integrierten Werttypen](../keywords/value-types-table.md) sind gleich, wenn ihre Werte gleich sind:</span><span class="sxs-lookup"><span data-stu-id="db4cf-107">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="db4cf-108">Für die Gleichheits- und relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="db4cf-108">For equality and relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="db4cf-109">Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`.</span><span class="sxs-lookup"><span data-stu-id="db4cf-109">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="db4cf-110">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="db4cf-110">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="db4cf-111">Zwei Operanden desselben [enum](../keywords/enum.md)-Typs sind gleich, wenn die entsprechenden Werte des zugrunde liegenden integralen Typs gleich sind.</span><span class="sxs-lookup"><span data-stu-id="db4cf-111">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="db4cf-112">Benutzerdefinierte [Strukturtypen](../keywords/struct.md) unterstützen den `==`-Operator nicht standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="db4cf-112">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="db4cf-113">Eine benutzerdefinierte Struktur muss den `==`-Operator [überladen](#operator-overloadability), damit er unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="db4cf-113">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="db4cf-114">Ab C# 7.3 werden die Operatoren `==` und `!=` für [C#-Tupel](../../tuples.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="db4cf-114">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="db4cf-115">Weitere Informationen finden Sie im Abschnitt [Gleichheit und Tupel](../../tuples.md#equality-and-tuples) im Artikel [C#-Tupeltypen](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-115">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="db4cf-116">Zeichenfolgengleichheit</span><span class="sxs-lookup"><span data-stu-id="db4cf-116">String equality</span></span>

<span data-ttu-id="db4cf-117">Zwei [Zeichenfolge](../keywords/string.md)-Operanden gleich sind, wenn beide gleich `null` sind oder wenn beide Zeichenfolgeninstanzen dieselbe Länge und identische Zeichen in jeder Zeichenposition haben:</span><span class="sxs-lookup"><span data-stu-id="db4cf-117">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="db4cf-118">Dies ist ein Ordinalvergleich mit Berücksichtigung der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="db4cf-118">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="db4cf-119">Weitere Informationen zum Zeichenfolgenvergleich finden Sie unter [Vergleichen von Zeichenfolgen in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-119">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="db4cf-120">Gleichheit von Verweistypen</span><span class="sxs-lookup"><span data-stu-id="db4cf-120">Reference types equality</span></span>

<span data-ttu-id="db4cf-121">Zwei Verweistypoperanden ungleich `string` sind gleich, wenn sie auf dasselbe Objekt verweisen:</span><span class="sxs-lookup"><span data-stu-id="db4cf-121">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="db4cf-122">Das Beispiel zeigt, dass benutzerdefinierte Verweistypen den `==`-Operator standardmäßig unterstützen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-122">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="db4cf-123">Ein benutzerdefinierter Verweistyp kann den `==`-Operator aber überladen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-123">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="db4cf-124">Wenn ein Verweistyp den `==`-Operator überlädt, verwenden Sie die <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode, um zu überprüfen, ob zwei Verweise dieses Typs auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-124">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="db4cf-125">Ungleichheitsoperator !=</span><span class="sxs-lookup"><span data-stu-id="db4cf-125">Inequality operator !=</span></span>

<span data-ttu-id="db4cf-126">Der Ungleichheitsoperator `!=` gibt `true` zurück, wenn die Operanden nicht gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="db4cf-126">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="db4cf-127">Für die Operanden der [integrierten Typen](../keywords/built-in-types-table.md) führt der Ausdruck `x != y` zum selben Ergebnis wie der Ausdruck `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="db4cf-127">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="db4cf-128">Weitere Informationen zur Typengleichheit finden Sie im Abschnitt [Gleichheitsoperator](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="db4cf-128">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="db4cf-129">Im folgenden Beispiel wird die Verwendung des `!=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="db4cf-129">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="db4cf-130">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="db4cf-130">Operator overloadability</span></span>

<span data-ttu-id="db4cf-131">Benutzerdefinierte Typen können die Operatoren `==` und `!=` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-131">User-defined types can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="db4cf-132">Wenn ein Typ einen der beiden Operatoren überlädt, muss er auch den anderen Operator überladen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-132">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="db4cf-133">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="db4cf-133">C# language specification</span></span>

<span data-ttu-id="db4cf-134">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-134">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db4cf-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db4cf-135">See also</span></span>

- [<span data-ttu-id="db4cf-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="db4cf-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db4cf-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="db4cf-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="db4cf-138">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="db4cf-138">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="db4cf-139">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="db4cf-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
