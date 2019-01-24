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
ms.openlocfilehash: 185ea3aabff4794ec08cca541773dbec3574ab4b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333511"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="eefb6-102">|-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eefb6-102">| operator (C# Reference)</span></span>

<span data-ttu-id="eefb6-103">Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="eefb6-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="eefb6-104">Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="eefb6-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="eefb6-105">Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.</span><span class="sxs-lookup"><span data-stu-id="eefb6-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eefb6-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eefb6-106">Remarks</span></span>

<span data-ttu-id="eefb6-107">Im Gegensatz zum [bedingten OR-Operator](conditional-or-operator.md) `||` wertet der binäre `|`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="eefb6-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>

<span data-ttu-id="eefb6-108">Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="eefb6-108">User-defined types can overload the `|` operator (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="eefb6-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefb6-109">Example</span></span>

 [!code-csharp[csRefOperators#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#31)]

## <a name="see-also"></a><span data-ttu-id="eefb6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eefb6-110">See also</span></span>

- [<span data-ttu-id="eefb6-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eefb6-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="eefb6-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="eefb6-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="eefb6-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="eefb6-113">C# operators</span></span>](index.md)