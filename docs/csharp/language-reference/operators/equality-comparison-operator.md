---
title: ==-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655958"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d433f-102">Operator == (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d433f-102">== Operator (C# Reference)</span></span>

<span data-ttu-id="d433f-103">Der Gleichheitsoperator `==` gibt `true` zurück, wenn die Operanden gleich sind; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d433f-103">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

## <a name="value-types-equality"></a><span data-ttu-id="d433f-104">Gleichheit von Werttypen</span><span class="sxs-lookup"><span data-stu-id="d433f-104">Value types equality</span></span>

<span data-ttu-id="d433f-105">Operanden der [integrierten Werttypen](../keywords/value-types-table.md) sind gleich, wenn ihre Werte gleich sind:</span><span class="sxs-lookup"><span data-stu-id="d433f-105">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="d433f-106">Für die relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="d433f-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="d433f-107">Dies bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist.</span><span class="sxs-lookup"><span data-stu-id="d433f-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="d433f-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="d433f-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="d433f-109">Zwei Operanden desselben [enum](../keywords/enum.md)-Typs sind gleich, wenn die entsprechenden Werte des zugrunde liegenden integralen Typs gleich sind.</span><span class="sxs-lookup"><span data-stu-id="d433f-109">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="d433f-110">Standardmäßig ist der `==`-Operator nicht für einen benutzerdefinierten [struct](../keywords/struct.md)-Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="d433f-110">By default, the `==` operator is not defined for a user-defined [struct](../keywords/struct.md) type.</span></span> <span data-ttu-id="d433f-111">Ein benutzerdefinierter Typ kann den Operator `==` [überladen](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="d433f-111">A user-defined type can [overload](#operator-overloadability) the `==` operator.</span></span>

<span data-ttu-id="d433f-112">Ab C# 7.3 werden die Operatoren `==` und [`!=`](not-equal-operator.md) für C#-[Tupel](../../tuples.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d433f-112">Beginning with C# 7.3, the `==` and [`!=`](not-equal-operator.md) operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="d433f-113">Weitere Informationen finden Sie im Abschnitt [Gleichheit und Tupel](../../tuples.md#equality-and-tuples) im Artikel [C#-Tupeltypen](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-113">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

## <a name="string-equality"></a><span data-ttu-id="d433f-114">Zeichenfolgengleichheit</span><span class="sxs-lookup"><span data-stu-id="d433f-114">String equality</span></span>

<span data-ttu-id="d433f-115">Zwei [Zeichenfolge](../keywords/string.md)-Operanden gleich sind, wenn beide gleich `null` sind oder wenn beide Zeichenfolgeninstanzen dieselbe Länge und identische Zeichen in jeder Zeichenposition haben:</span><span class="sxs-lookup"><span data-stu-id="d433f-115">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="d433f-116">Dies ist ein Ordinalvergleich mit Berücksichtigung der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="d433f-116">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="d433f-117">Weitere Informationen dazu, wie Zeichenfolgen verglichen werden, finden Sie unter [Vergleichen von Zeichenfolgen in C#](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-117">For more information about how to compare strings, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

## <a name="reference-types-equality"></a><span data-ttu-id="d433f-118">Gleichheit von Verweistypen</span><span class="sxs-lookup"><span data-stu-id="d433f-118">Reference types equality</span></span>

<span data-ttu-id="d433f-119">Zwei Verweistypoperanden ungleich `string` sind gleich, wenn sie auf dasselbe Objekt verweisen:</span><span class="sxs-lookup"><span data-stu-id="d433f-119">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="d433f-120">Das Beispiel zeigt, dass der `==`-Operator für benutzerdefinierte Verweistypen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d433f-120">The example shows that the `==` operator is supported by user-defined reference types.</span></span> <span data-ttu-id="d433f-121">Ein benutzerdefinierter Verweistyp kann den `==`-Operator aber überladen.</span><span class="sxs-lookup"><span data-stu-id="d433f-121">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="d433f-122">Wenn ein Verweistyp den `==`-Operator überlädt, verwenden Sie die <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>-Methode, um zu überprüfen, ob zwei Verweise dieses Typs auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="d433f-122">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="d433f-123">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="d433f-123">Operator overloadability</span></span>

<span data-ttu-id="d433f-124">Benutzerdefinierte Typen können den Operator `==` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-124">User-defined types can [overload](../keywords/operator.md) the `==` operator.</span></span> <span data-ttu-id="d433f-125">Wenn ein Typ den Gleichheitsoperator `==` überlädt, muss er auch den [Ungleichheitsoperator](not-equal-operator.md) `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="d433f-125">If a type overloads the equality operator `==`, it must also overload the [inequality operator](not-equal-operator.md) `!=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d433f-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="d433f-126">C# language specification</span></span>

<span data-ttu-id="d433f-127">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d433f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d433f-128">See also</span></span>

- [<span data-ttu-id="d433f-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d433f-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d433f-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d433f-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d433f-131">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="d433f-131">C# Operators</span></span>](index.md)
- [<span data-ttu-id="d433f-132">Übereinstimmungsvergleiche</span><span class="sxs-lookup"><span data-stu-id="d433f-132">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
