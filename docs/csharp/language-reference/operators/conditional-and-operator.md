---
title: '&amp;&amp;-Operator (C#-Referenz)'
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529234"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="808b6-102">&amp;&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="808b6-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="808b6-103">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der [bool](../keywords/bool.md)-Operanden.</span><span class="sxs-lookup"><span data-stu-id="808b6-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="808b6-104">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="808b6-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="808b6-105">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="808b6-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="808b6-106">Wenn der erste Operand als `false` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `false`.</span><span class="sxs-lookup"><span data-stu-id="808b6-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="808b6-107">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="808b6-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="808b6-108">Der [logische AND-Operator](and-operator.md) `&` berechnet auch die logische AND-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="808b6-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="808b6-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="808b6-109">Operator overloadability</span></span>

<span data-ttu-id="808b6-110">Ein benutzerdefinierter Typ kann den bedingten logischen AND-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="808b6-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="808b6-111">Wenn ein benutzerdefinierter Typ die [logischen AND](and-operator.md)-, [true](../keywords/true-operator.md)- und [false](../keywords/false-operator.md)-Operatoren jedoch in einer bestimmten Weise überlädt, kann die `&&`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="808b6-111">However, if a user-defined type overloads the [logical AND](and-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="808b6-112">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="808b6-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="808b6-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="808b6-113">C# language specification</span></span>

<span data-ttu-id="808b6-114">Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="808b6-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="808b6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="808b6-115">See also</span></span>

- [<span data-ttu-id="808b6-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="808b6-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="808b6-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="808b6-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="808b6-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="808b6-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="808b6-119">||-Operator</span><span class="sxs-lookup"><span data-stu-id="808b6-119">|| operator</span></span>](conditional-or-operator.md)
- [!-Operator]<span data-ttu-id="808b6-120">(logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="808b6-120">(logical-negation-operator.md)</span></span>
- [<span data-ttu-id="808b6-121">&-Operator</span><span class="sxs-lookup"><span data-stu-id="808b6-121">& operator</span></span>](and-operator.md)
