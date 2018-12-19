---
title: '&amp;&amp;-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 82442f50275f21e0a0748951dc50628a8d7e11bb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243586"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="a0dba-102">&amp;&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a0dba-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="a0dba-103">Der bedingte logische AND-Operator `&&`, auch bekannt als der "kurzschließender" logischer AND-Operator bezeichnet, berechnet die logische AND-Operation der [bool](../keywords/bool.md)-Operanden.</span><span class="sxs-lookup"><span data-stu-id="a0dba-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="a0dba-104">Das Ergebnis von `x && y` ist `true`, wenn sowohl `x` als auch `y` zu `true` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a0dba-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="a0dba-105">Andernfalls ist das Ergebnis `false`.</span><span class="sxs-lookup"><span data-stu-id="a0dba-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="a0dba-106">Wenn der erste Operand als `false` ausgewertet wird, wird der zweite Operand nicht ausgewertet, und das Ergebnis der Operation ist `false`.</span><span class="sxs-lookup"><span data-stu-id="a0dba-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="a0dba-107">Das folgende Beispiel veranschaulicht dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="a0dba-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="a0dba-108">Der [logische AND-Operator](and-operator.md) `&` berechnet auch die logische AND-Operation der `bool`-Operanden, es werden jedoch immer beide Operanden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a0dba-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a0dba-109">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="a0dba-109">Operator overloadability</span></span>

<span data-ttu-id="a0dba-110">Ein benutzerdefinierter Typ kann den bedingten logischen AND-Operator nicht überladen.</span><span class="sxs-lookup"><span data-stu-id="a0dba-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="a0dba-111">Wenn ein benutzerdefinierter Typ die Operatoren [logisches AND](and-operator.md) sowie [true und false](../keywords/true-false-operators.md) jedoch in einer bestimmten Weise überlädt, kann der `&&`-Vorgang für die Operanden dieses Typs ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a0dba-111">However, if a user-defined type overloads the [logical AND](and-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="a0dba-112">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte bedingte logische Operatoren](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a0dba-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a0dba-113">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a0dba-113">C# language specification</span></span>

<span data-ttu-id="a0dba-114">Weitere Informationen finden Sie im Abschnitt [Bedingte logische Operatoren](~/_csharplang/spec/expressions.md#conditional-logical-operators) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a0dba-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0dba-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0dba-115">See also</span></span>

- [<span data-ttu-id="a0dba-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a0dba-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a0dba-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a0dba-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a0dba-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a0dba-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="a0dba-119">||-Operator</span><span class="sxs-lookup"><span data-stu-id="a0dba-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="a0dba-120">\!-Operator</span><span class="sxs-lookup"><span data-stu-id="a0dba-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="a0dba-121">&-Operator</span><span class="sxs-lookup"><span data-stu-id="a0dba-121">& operator</span></span>](and-operator.md)
