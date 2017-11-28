---
title: '&gt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc7c173ecc97bd3ca3b76a92ccbabc0f40062ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="6662a-102">Operator &gt; (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6662a-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="6662a-103">Alle numerischen und Emumerationstypen definieren einen relationalen „größer als“-Operator (`>`), der `true` zurückgibt, wenn der erste Operand größer dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="6662a-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6662a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6662a-104">Remarks</span></span>  
 <span data-ttu-id="6662a-105">Benutzerdefinierte Typen können den Operator `>` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="6662a-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6662a-106">Wenn `>` überladen ist, muss [<](../../../csharp/language-reference/operators/less-than-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="6662a-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="6662a-107">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="6662a-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6662a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6662a-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6662a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6662a-109">See Also</span></span>  
 [<span data-ttu-id="6662a-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6662a-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6662a-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6662a-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6662a-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6662a-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="6662a-113">explicit</span><span class="sxs-lookup"><span data-stu-id="6662a-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
