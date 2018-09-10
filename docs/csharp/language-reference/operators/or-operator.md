---
title: Operator | (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085704"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ad763-102">Operator | (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ad763-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="ad763-103">Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="ad763-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="ad763-104">Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="ad763-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="ad763-105">Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.</span><span class="sxs-lookup"><span data-stu-id="ad763-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad763-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad763-106">Remarks</span></span>  
 <span data-ttu-id="ad763-107">Im Gegensatz zum [bedingten OR-Operator] (conditional-or-operator.md) `||` wertet der binäre `|`-Operator beide Operatoren unabhängig vom Wert des ersten Operators aus.</span><span class="sxs-lookup"><span data-stu-id="ad763-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator]     (conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="ad763-108">Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="ad763-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad763-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad763-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ad763-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad763-110">See Also</span></span>

- [<span data-ttu-id="ad763-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ad763-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ad763-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad763-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ad763-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="ad763-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
