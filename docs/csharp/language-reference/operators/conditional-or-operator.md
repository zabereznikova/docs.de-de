---
title: '||-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: f4bb7ada12fbcebcb90fb7cd22d6e6bccad5fb57
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244569"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="212ca-102">Operator || (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="212ca-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="212ca-103">Der bedingte logische OR-Operator `||`, auch bekannt als der "kurzschließender" logischer OR-Operator bezeichnet, berechnet die logische OR-Operation der [bool](../keywords/bool.md)-Operanden.</span><span class="sxs-lookup"><span data-stu-id="212ca-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="212ca-104">Das Ergebnis von `x || y` ist `true`, wenn entweder `x` oder `y` `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="212ca-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="212ca-105">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="212ca-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="212ca-106">Wenn der erste Operand als `true` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `true`.</span><span class="sxs-lookup"><span data-stu-id="212ca-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="212ca-107">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="212ca-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="212ca-108">Der [logische OR-Operator](or-operator.md) `|` berechnet auch die logische OR-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="212ca-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="212ca-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="212ca-109">Operator overloadability</span></span>

<span data-ttu-id="212ca-110">Ein benutzerdefinierter Typ kann den bedingten logischen OR-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="212ca-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="212ca-111">Wenn ein benutzerdefinierter Typ die Operatoren [logisches OR](or-operator.md) sowie [true und false](../keywords/true-false-operators.md) jedoch in einer bestimmten Weise überlädt, kann der `||`-Vorgang für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="212ca-111">However, if a user-defined type overloads the [logical OR](or-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="212ca-112">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="212ca-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="212ca-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="212ca-113">C# language specification</span></span>

<span data-ttu-id="212ca-114">Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="212ca-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="212ca-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="212ca-115">See also</span></span>

- [<span data-ttu-id="212ca-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="212ca-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="212ca-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="212ca-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="212ca-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="212ca-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="212ca-119">&&-Operator </span><span class="sxs-lookup"><span data-stu-id="212ca-119">&& operator</span></span>](conditional-and-operator.md)
- [!-Operator]<span data-ttu-id="212ca-120">(logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="212ca-120">(logical-negation-operator.md)</span></span>
- [<span data-ttu-id="212ca-121">|-Operator</span><span class="sxs-lookup"><span data-stu-id="212ca-121">| operator</span></span>](or-operator.md)
