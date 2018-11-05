---
title: + Operator (C#-Referenz)
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: ae2774d96bc50afa271fffdea445e640e68c3647
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192297"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1bb17-102">Operator + (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1bb17-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="1bb17-103">Der Operator `+` wird in zwei Formen unterstützt: als unärer Plusoperator oder als binärer Additionsoperator.</span><span class="sxs-lookup"><span data-stu-id="1bb17-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

<span data-ttu-id="1bb17-104">Benutzerdefinierte Typen können die unären und binären `+`-Operatoren [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="1bb17-104">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="1bb17-105">Wenn ein binärer `+`-Operator überladen ist, wird der [Additionszuweisungsoperator](addition-assignment-operator.md) `+=`auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="1bb17-105">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="1bb17-106">Unärer Plus-Operator</span><span class="sxs-lookup"><span data-stu-id="1bb17-106">Unary plus operator</span></span>

<span data-ttu-id="1bb17-107">Der unäre `+`-Operator gibt den Wert seines Operanden zurück.</span><span class="sxs-lookup"><span data-stu-id="1bb17-107">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="1bb17-108">Er wird von allen numerischen Typen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1bb17-108">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="1bb17-109">Numerische Addition</span><span class="sxs-lookup"><span data-stu-id="1bb17-109">Numeric addition</span></span>

<span data-ttu-id="1bb17-110">Für numerische Typen berechnet der `+`-Operator die Summe der Operanden:</span><span class="sxs-lookup"><span data-stu-id="1bb17-110">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="1bb17-111">Zeichenfolgenverkettung</span><span class="sxs-lookup"><span data-stu-id="1bb17-111">String concatenation</span></span>

<span data-ttu-id="1bb17-112">Wenn ein Operand oder beide Operanden vom Typ [String](../keywords/string.md) sind, verkettet der `+`-Operator die Zeichenfolgendarstellungen der Operanden:</span><span class="sxs-lookup"><span data-stu-id="1bb17-112">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="1bb17-113">Ab C# 6 bietet die [Zeichenfolgeninterpolation](../tokens/interpolated.md) eine benutzerfreundliche Option zum Formatieren von Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="1bb17-113">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="1bb17-114">Kombinieren von Delegaten</span><span class="sxs-lookup"><span data-stu-id="1bb17-114">Delegate combination</span></span>

<span data-ttu-id="1bb17-115">Für [Delegattypen](../keywords/delegate.md) gibt der Operator `+` eine neue Delegatinstanz zurück, die beim Aufruf den ersten Operanden und dann den zweiten Operanden aufruft.</span><span class="sxs-lookup"><span data-stu-id="1bb17-115">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="1bb17-116">Wenn einer der Operanden `null` lautet, gibt der `+`-Operator den Wert eines anderen Operanden zurück (der ggf. ebenfalls `null` ist).</span><span class="sxs-lookup"><span data-stu-id="1bb17-116">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="1bb17-117">Das folgende Beispiel zeigt, wie Delegaten mit dem `+`-Operator kombiniert werden können:</span><span class="sxs-lookup"><span data-stu-id="1bb17-117">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="1bb17-118">Weitere Informationen zu Delegattypen finden Sie unter [Delegaten](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="1bb17-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1bb17-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1bb17-119">C# language specification</span></span>

<span data-ttu-id="1bb17-120">Weitere Informationen finden Sie unter [C#-Sprachspezifikation](../language-specification/index.md) in den Abschnitten [Unärer Plusoperator](~/_csharplang/spec/expressions.md#unary-plus-operator) und [Additionsoperator](~/_csharplang/spec/expressions.md#addition-operator).</span><span class="sxs-lookup"><span data-stu-id="1bb17-120">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1bb17-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bb17-121">See also</span></span>

- [<span data-ttu-id="1bb17-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1bb17-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1bb17-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1bb17-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1bb17-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1bb17-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="1bb17-125">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="1bb17-125">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="1bb17-126">Gewusst wie: Verketten von mehreren Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1bb17-126">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="1bb17-127">Delegaten</span><span class="sxs-lookup"><span data-stu-id="1bb17-127">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="1bb17-128">Checked und unchecked</span><span class="sxs-lookup"><span data-stu-id="1bb17-128">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
