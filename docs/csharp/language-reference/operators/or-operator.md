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
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028165"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="90747-102">Operator | (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="90747-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="90747-103">Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="90747-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="90747-104">Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="90747-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="90747-105">Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.</span><span class="sxs-lookup"><span data-stu-id="90747-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90747-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90747-106">Remarks</span></span>  
 <span data-ttu-id="90747-107">Im Gegensatz zum [bedingten OR-Operator](conditional-or-operator.md) `||` wertet der binäre `|`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="90747-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="90747-108">Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="90747-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90747-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90747-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="90747-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90747-110">See Also</span></span>

- [<span data-ttu-id="90747-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="90747-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="90747-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="90747-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="90747-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="90747-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
