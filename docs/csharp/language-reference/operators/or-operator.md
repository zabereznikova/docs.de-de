---
title: Operator | (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 374adc30e6937a68d67bfae152f2546c854b829b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fc7d2-102">Operator | (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fc7d2-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="fc7d2-103">Binäre `|`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="fc7d2-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="fc7d2-104">Für integrale Typen berechnet `|` die bitweise OR-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="fc7d2-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="fc7d2-105">Für `bool` Operanden berechnet `|` die logische OR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `false` ist, wenn beide Operanden `false` sind.</span><span class="sxs-lookup"><span data-stu-id="fc7d2-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc7d2-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc7d2-106">Remarks</span></span>  
 <span data-ttu-id="fc7d2-107">Benutzerdefinierte Typen können den Operator `|` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="fc7d2-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc7d2-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc7d2-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fc7d2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc7d2-109">See Also</span></span>  
 [<span data-ttu-id="fc7d2-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fc7d2-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fc7d2-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fc7d2-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fc7d2-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="fc7d2-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
