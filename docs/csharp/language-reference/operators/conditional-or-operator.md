---
title: Operator || (C#-Referenz)
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: a391078372e4ec0a3882bed4515733adedffb547
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "42925539"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="809a2-102">Operator || (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="809a2-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="809a2-103">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der [bool](../keywords/bool.md)-Operanden.</span><span class="sxs-lookup"><span data-stu-id="809a2-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="809a2-104">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="809a2-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="809a2-105">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="809a2-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="809a2-106">Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `true`.</span><span class="sxs-lookup"><span data-stu-id="809a2-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="809a2-107">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="809a2-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="809a2-108">Der [logische OR-Operator](or-operator.md) `|` berechnet auch die logische OR-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="809a2-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="809a2-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="809a2-109">Operator overloadability</span></span>

<span data-ttu-id="809a2-110">Ein benutzerdefinierter Typ kann den bedingten logischen OR-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="809a2-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="809a2-111">Wenn ein benutzerdefinierter Typ die [logischen OR](or-operator.md)-, [true](../keywords/true-operator.md)- und [false](../keywords/false-operator.md)-Operatoren jedoch in einer bestimmten Weise überlädt, kann die `||`-Operation für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="809a2-111">However, if a user-defined type overloads the [logical OR](or-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="809a2-112">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="809a2-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="809a2-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="809a2-113">C# language specification</span></span>

<span data-ttu-id="809a2-114">Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="809a2-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="809a2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="809a2-115">See also</span></span>

- [<span data-ttu-id="809a2-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="809a2-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="809a2-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="809a2-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="809a2-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="809a2-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="809a2-119">&&-Operator </span><span class="sxs-lookup"><span data-stu-id="809a2-119">&& operator</span></span>](conditional-and-operator.md)
- [!-Operator]<span data-ttu-id="809a2-120">(logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="809a2-120">(logical-negation-operator.md)</span></span>
- [<span data-ttu-id="809a2-121">|-Operator</span><span class="sxs-lookup"><span data-stu-id="809a2-121">| operator</span></span>](or-operator.md)
