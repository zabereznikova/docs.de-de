---
title: '! -Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303711"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ef4aa-103">!</span><span class="sxs-lookup"><span data-stu-id="ef4aa-103">!</span></span> <span data-ttu-id="ef4aa-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ef4aa-104">operator (C# Reference)</span></span>

<span data-ttu-id="ef4aa-105">Der logische Negationsoperator `!` ist ein unärer Operator, der eine logische Negation des zugehörigen [bool](../keywords/bool.md)-Operanden berechnet.</span><span class="sxs-lookup"><span data-stu-id="ef4aa-105">The logical negation operator `!` is a unary operator that computes logical negation of its [bool](../keywords/bool.md) operand.</span></span> <span data-ttu-id="ef4aa-106">D. h., er ergibt `true`, wenn der Operand `false` ist, und `false`, wenn der Operand `true` ist:</span><span class="sxs-lookup"><span data-stu-id="ef4aa-106">That is, it produces `true`, if the operand is `false`, and `false`, if the operand is `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a><span data-ttu-id="ef4aa-107">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="ef4aa-107">Operator overloadability</span></span>

<span data-ttu-id="ef4aa-108">Benutzerdefinierte Typen können den Operator `!` [überladen](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="ef4aa-108">User-defined types can [overload](../keywords/operator.md) the `!` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ef4aa-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ef4aa-109">C# language specification</span></span>

<span data-ttu-id="ef4aa-110">Weitere Informationen finden Sie im Abschnitt [Logischer Negationsoperator](~/_csharplang/spec/expressions.md#logical-negation-operator) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ef4aa-110">For more information, see the [Logical negation operator](~/_csharplang/spec/expressions.md#logical-negation-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef4aa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef4aa-111">See also</span></span>

- [<span data-ttu-id="ef4aa-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ef4aa-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ef4aa-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ef4aa-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ef4aa-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ef4aa-114">C# Operators</span></span>](index.md)