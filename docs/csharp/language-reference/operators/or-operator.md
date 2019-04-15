---
title: '|-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 38f8e21dbd07868441e0c4fbb6074f9897905222
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312877"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ba8e4-102">|-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ba8e4-102">| operator (C# Reference)</span></span>

<span data-ttu-id="ba8e4-103">Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="ba8e4-104">Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="ba8e4-105">Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba8e4-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="ba8e4-106">Remarks</span></span>

<span data-ttu-id="ba8e4-107">Im Gegensatz zum [bedingten OR-Operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||` wertet der binäre `|`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="ba8e4-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](boolean-logical-operators.md#conditional-logical-or-operator-) `||`.</span></span>

<span data-ttu-id="ba8e4-108">Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ba8e4-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="ba8e4-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba8e4-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="ba8e4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba8e4-110">See also</span></span>

- [<span data-ttu-id="ba8e4-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ba8e4-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ba8e4-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ba8e4-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ba8e4-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ba8e4-113">C# operators</span></span>](index.md)