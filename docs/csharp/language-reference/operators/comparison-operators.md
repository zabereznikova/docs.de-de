---
title: Vergleichsoperatoren – C#-Referenz
description: Erfahren Sie mehr über C#-Vergleichsoperatoren, mit denen Sie die Reihenfolge numerischer Werte überprüfen können.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 6d3751ff1ee2c6ee2f058eeda4ffd5db188a988e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633758"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="c3217-103">Vergleichsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c3217-103">Comparison operators (C# Reference)</span></span>

<span data-ttu-id="c3217-104">Die Vergleichsoperatoren [`<` (kleiner als)](#less-than-operator-), [`>` (größer als)](#greater-than-operator-), [`<=` (kleiner als oder gleich)](#less-than-or-equal-operator-) und [`>=` (größer als oder gleich)](#greater-than-or-equal-operator-) – auch bekannt als relationale Operatoren – vergleichen ihre Operanden.</span><span class="sxs-lookup"><span data-stu-id="c3217-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="c3217-105">Diese Operatoren unterstützen alle numerischen [Ganzzahl](../keywords/integral-types-table.md)- und [Gleitkomma](../keywords/floating-point-types-table.md)-Typen.</span><span class="sxs-lookup"><span data-stu-id="c3217-105">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="c3217-106">Bei den Operatoren `==`, `<`, `>`, `<=` und `>=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="c3217-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="c3217-107">Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`.</span><span class="sxs-lookup"><span data-stu-id="c3217-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="c3217-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="c3217-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="c3217-109">Enumerationstypen unterstützen auch Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c3217-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="c3217-110">Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.</span><span class="sxs-lookup"><span data-stu-id="c3217-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="c3217-111">Die Operatoren [`==` und `!=`](equality-operators.md) überprüfen, ob die Operanden gleich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c3217-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="c3217-112">„Kleiner als“-Operator \<</span><span class="sxs-lookup"><span data-stu-id="c3217-112">Less than operator \<</span></span>

<span data-ttu-id="c3217-113">Der `<`-Operator gibt `true` zurück, wenn sein erster Operand kleiner ist als sein zweiter Operand, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c3217-113">The `<` operator returns `true` if its first operand is less than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="c3217-114">„Größer als“-Operator ></span><span class="sxs-lookup"><span data-stu-id="c3217-114">Greater than operator ></span></span>

<span data-ttu-id="c3217-115">Der `>`-Operator gibt `true` zurück, wenn sein erster Operand größer ist als sein zweiter Operand, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c3217-115">The `>` operator returns `true` if its first operand is greater than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="c3217-116">„Kleiner oder gleich“-Operator \<=</span><span class="sxs-lookup"><span data-stu-id="c3217-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="c3217-117">Der `<=`-Operator gibt `true` zurück, wenn sein erster Operand kleiner als sein zweiter Operand oder gleich ist, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c3217-117">The `<=` operator returns `true` if its first operand is less than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="c3217-118">„Größer oder gleich“-Operator >=</span><span class="sxs-lookup"><span data-stu-id="c3217-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="c3217-119">Der `>=`-Operator gibt `true` zurück, wenn sein erster Operand größer als sein zweiter Operand oder gleich ist, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c3217-119">The `>=` operator returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="c3217-120">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="c3217-120">Operator overloadability</span></span>

<span data-ttu-id="c3217-121">Ein benutzerdefinierter Typ kann die Operatoren `<`, `>`, `<=` und `>=` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="c3217-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="c3217-122">Wenn ein Typ einen der `<`- oder `>`-Operatoren überlädt, muss er sowohl `<` als auch `>` überladen.</span><span class="sxs-lookup"><span data-stu-id="c3217-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="c3217-123">Wenn ein Typ einen der `<=`- oder `>=`-Operatoren überlädt, muss er sowohl `<=` als auch `>=` überladen.</span><span class="sxs-lookup"><span data-stu-id="c3217-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c3217-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c3217-124">C# language specification</span></span>

<span data-ttu-id="c3217-125">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c3217-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3217-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3217-126">See also</span></span>

- [<span data-ttu-id="c3217-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c3217-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c3217-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c3217-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c3217-129">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c3217-129">C# Operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="c3217-130">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c3217-130">Equality operators</span></span>](equality-operators.md)
