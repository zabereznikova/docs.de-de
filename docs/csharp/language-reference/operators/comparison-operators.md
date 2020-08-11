---
title: 'Vergleichsoperatoren: C#-Referenz'
description: Erfahren Sie mehr über C#-Vergleichsoperatoren, mit denen Sie die Reihenfolge numerischer Werte überprüfen können.
ms.date: 05/11/2020
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
ms.openlocfilehash: 9fa739d8b5461d4043f3ae51f5d14949a95c68e5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916884"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="c6d9a-103">Vergleichsoperatoren (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c6d9a-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="c6d9a-104">Die Vergleichsoperatoren [`<` (kleiner als)](#less-than-operator-), [`>` (größer als)](#greater-than-operator-), [`<=` (kleiner als oder gleich)](#less-than-or-equal-operator-) und [`>=` (größer als oder gleich)](#greater-than-or-equal-operator-) – auch bekannt als relationale Operatoren – vergleichen ihre Operanden.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="c6d9a-105">Diese Operatoren werden alle von numerischen [Ganzzahl](../builtin-types/integral-numeric-types.md)- und [Gleitkommatypen](../builtin-types/floating-point-numeric-types.md) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-105">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="c6d9a-106">Bei den Operatoren `==`, `<`, `>`, `<=` und `>=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="c6d9a-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="c6d9a-107">Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="c6d9a-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="c6d9a-109">Der [char](../builtin-types/char.md)-Typ unterstützt auch Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-109">The [char](../builtin-types/char.md) type also supports comparison operators.</span></span> <span data-ttu-id="c6d9a-110">Im Fall von `char`-Operanden werden die entsprechenden Zeichencodes verglichen.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-110">In the case of `char` operands, the corresponding character codes are compared.</span></span>

<span data-ttu-id="c6d9a-111">Enumerationstypen unterstützen auch Vergleichsoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-111">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="c6d9a-112">Für Operanden desselben [enum](../builtin-types/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-112">For operands of the same [enum](../builtin-types/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="c6d9a-113">Die Operatoren [`==` und `!=`](equality-operators.md) überprüfen, ob die Operanden gleich sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-113">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="c6d9a-114">„Kleiner als“-Operator \<</span><span class="sxs-lookup"><span data-stu-id="c6d9a-114">Less than operator \<</span></span>

<span data-ttu-id="c6d9a-115">Der `<`-Operator gibt `true` zurück, wenn sein linker Operand kleiner ist als sein rechter Operand, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c6d9a-115">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](snippets/shared/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="c6d9a-116">„Größer als“-Operator ></span><span class="sxs-lookup"><span data-stu-id="c6d9a-116">Greater than operator ></span></span>

<span data-ttu-id="c6d9a-117">Der `>`-Operator gibt `true` zurück, wenn sein linker Operand größer ist als sein rechter Operand, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c6d9a-117">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](snippets/shared/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="c6d9a-118">„Kleiner oder gleich“-Operator \<=</span><span class="sxs-lookup"><span data-stu-id="c6d9a-118">Less than or equal operator \<=</span></span>

<span data-ttu-id="c6d9a-119">Der `<=`-Operator gibt `true` zurück, wenn sein linker Operand kleiner ist als der rechte Operand oder diesem entspricht, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c6d9a-119">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](snippets/shared/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="c6d9a-120">„Größer oder gleich“-Operator >=</span><span class="sxs-lookup"><span data-stu-id="c6d9a-120">Greater than or equal operator >=</span></span>

<span data-ttu-id="c6d9a-121">Der `>=`-Operator gibt `true` zurück, wenn sein linker Operand größer ist als der rechte Operand oder diesem entspricht, andernfalls `false`:</span><span class="sxs-lookup"><span data-stu-id="c6d9a-121">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](snippets/shared/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="c6d9a-122">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="c6d9a-122">Operator overloadability</span></span>

<span data-ttu-id="c6d9a-123">Ein benutzerdefinierter Typ kann die Operatoren `<`, `>`, `<=` und `>=`[überladen](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="c6d9a-123">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="c6d9a-124">Wenn ein Typ einen der `<`- oder `>`-Operatoren überlädt, muss er sowohl `<` als auch `>` überladen.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-124">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="c6d9a-125">Wenn ein Typ einen der `<=`- oder `>=`-Operatoren überlädt, muss er sowohl `<=` als auch `>=` überladen.</span><span class="sxs-lookup"><span data-stu-id="c6d9a-125">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c6d9a-126">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c6d9a-126">C# language specification</span></span>

<span data-ttu-id="c6d9a-127">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c6d9a-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6d9a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6d9a-128">See also</span></span>

- [<span data-ttu-id="c6d9a-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c6d9a-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c6d9a-130">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c6d9a-130">C# operators and expressions</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="c6d9a-131">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c6d9a-131">Equality operators</span></span>](equality-operators.md)
