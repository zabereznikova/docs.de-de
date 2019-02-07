---
title: <-Operator - C#-Referenz
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: ab21e32b7609bc0c8753b42ccf8b6091bf3ad57b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286636"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a353b-102">\<-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a353b-102">\< Operator (C# Reference)</span></span>

<span data-ttu-id="a353b-103">Der relationale Operator „kleiner als“ `<` gibt `true` zurück, wenn sein erster Operand kleiner ist als sein zweiter Operand; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="a353b-103">The "less than" relational operator `<` returns `true` if its first operand is less than its second operand, `false` otherwise.</span></span> <span data-ttu-id="a353b-104">Alle numerischen Typen und Enumerationstypen unterstützen den `<`-Operator.</span><span class="sxs-lookup"><span data-stu-id="a353b-104">All numeric and enumeration types support the `<` operator.</span></span> <span data-ttu-id="a353b-105">Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.</span><span class="sxs-lookup"><span data-stu-id="a353b-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="a353b-106">Für die relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a353b-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="a353b-107">Dies bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist.</span><span class="sxs-lookup"><span data-stu-id="a353b-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="a353b-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="a353b-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="a353b-109">Im folgenden Beispiel wird die Verwendung des `<`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a353b-109">The following example demonstrates the usage of the `<` operator:</span></span>

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="operator-overloadability"></a><span data-ttu-id="a353b-110">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="a353b-110">Operator overloadability</span></span>

<span data-ttu-id="a353b-111">Benutzerdefinierte Typen können den Operator `<` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="a353b-111">User-defined types can [overload](../keywords/operator.md) the `<` operator.</span></span> <span data-ttu-id="a353b-112">Wenn ein Typ den „kleiner als“-Operator `<` überlädt, muss er auch den [„größer als“-Operator](greater-than-operator.md) `>` überladen.</span><span class="sxs-lookup"><span data-stu-id="a353b-112">If a type overloads the "less than" operator `<`, it must also overload the ["greater than" operator](greater-than-operator.md) `>`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a353b-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a353b-113">C# language specification</span></span>

<span data-ttu-id="a353b-114">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a353b-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a353b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a353b-115">See also</span></span>

- [<span data-ttu-id="a353b-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a353b-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a353b-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a353b-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a353b-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a353b-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="a353b-119"><=-Operator</span><span class="sxs-lookup"><span data-stu-id="a353b-119"><= Operator</span></span>](less-than-equal-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
