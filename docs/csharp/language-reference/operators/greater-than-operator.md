---
title: '&gt;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 0c9d414d159b5e2f1faa24e9bd5f073d1ca874a4
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655971"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="09650-102">&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="09650-102">&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="09650-103">Der relationale Operator „größer als“ `>` gibt `true` zurück, wenn sein erster Operand größer ist als sein zweiter Operand; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="09650-103">The "greater than" relational operator `>` returns `true` if its first operand is greater than its second operand, `false` otherwise.</span></span> <span data-ttu-id="09650-104">Alle numerischen Typen und Enumerationstypen unterstützen den `>`-Operator.</span><span class="sxs-lookup"><span data-stu-id="09650-104">All numeric and enumeration types support the `>` operator.</span></span> <span data-ttu-id="09650-105">Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.</span><span class="sxs-lookup"><span data-stu-id="09650-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="09650-106">Für die relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="09650-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="09650-107">Dies bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist.</span><span class="sxs-lookup"><span data-stu-id="09650-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="09650-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="09650-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="09650-109">Im folgenden Beispiel wird die Verwendung des `>`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="09650-109">The following example demonstrates the usage of the `>` operator:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="operator-overloadability"></a><span data-ttu-id="09650-110">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="09650-110">Operator overloadability</span></span>

<span data-ttu-id="09650-111">Benutzerdefinierte Typen können den Operator `>` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="09650-111">User-defined types can [overload](../keywords/operator.md) the `>` operator.</span></span> <span data-ttu-id="09650-112">Wenn ein Typ den „größer als“-Operator `>` überlädt, muss er auch den [„kleiner als“-Operator](less-than-operator.md) `<` überladen.</span><span class="sxs-lookup"><span data-stu-id="09650-112">If a type overloads the "greater than" operator `>`, it must also overload the ["less than" operator](less-than-operator.md) `<`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="09650-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="09650-113">C# language specification</span></span>

<span data-ttu-id="09650-114">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="09650-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09650-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09650-115">See also</span></span>

- [<span data-ttu-id="09650-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="09650-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="09650-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="09650-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="09650-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="09650-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="09650-119">>=-Operator</span><span class="sxs-lookup"><span data-stu-id="09650-119">>= Operator</span></span>](greater-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
