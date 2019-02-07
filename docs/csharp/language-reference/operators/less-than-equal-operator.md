---
title: <=-Operator - C#-Referenz
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: cb11a746d36cc22ab2341e28a7efba3c0b3510eb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257004"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2a1b6-102">Operator \<= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2a1b6-102">\<= Operator (C# Reference)</span></span>

<span data-ttu-id="2a1b6-103">Der relationale Operator „kleiner als oder gleich“ `<=` gibt `true` zurück, wenn sein erster Operand kleiner gleich seinem zweiten Operanden ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-103">The "less than or equal" relational operator `<=` returns `true` if its first operand is less than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="2a1b6-104">Alle numerischen Typen und Enumerationstypen unterstützen den `<=`-Operator.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-104">All numeric and enumeration types support the `<=` operator.</span></span> <span data-ttu-id="2a1b6-105">Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="2a1b6-106">Für die relationalen Operatoren `==`, `>`, `<`, `>=` und `<=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="2a1b6-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="2a1b6-107">Dies bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="2a1b6-108">Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="2a1b6-109">Im folgenden Beispiel wird die Verwendung des `<=`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2a1b6-109">The following example demonstrates the usage of the `<=` operator:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="2a1b6-110">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="2a1b6-110">Operator overloadability</span></span>

<span data-ttu-id="2a1b6-111">Benutzerdefinierte Typen können den Operator `<=` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="2a1b6-111">User-defined types can [overload](../keywords/operator.md) the `<=` operator.</span></span> <span data-ttu-id="2a1b6-112">Wenn ein Typ den „kleiner als oder gleich“-Operator `<=` überlädt, muss er auch den [„größer als oder gleich“-Operator](greater-than-equal-operator.md) `>=` überladen.</span><span class="sxs-lookup"><span data-stu-id="2a1b6-112">If a type overloads the "less than or equal" operator `<=`, it must also overload the ["greater than or equal" operator](greater-than-equal-operator.md) `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2a1b6-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2a1b6-113">C# language specification</span></span>

<span data-ttu-id="2a1b6-114">Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2a1b6-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a1b6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a1b6-115">See also</span></span>

- [<span data-ttu-id="2a1b6-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2a1b6-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2a1b6-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2a1b6-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2a1b6-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2a1b6-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2a1b6-119"><-Operator</span><span class="sxs-lookup"><span data-stu-id="2a1b6-119">< Operator</span></span>](less-than-operator.md)
- [<span data-ttu-id="2a1b6-120">==-Operator</span><span class="sxs-lookup"><span data-stu-id="2a1b6-120">== Operator</span></span>](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
