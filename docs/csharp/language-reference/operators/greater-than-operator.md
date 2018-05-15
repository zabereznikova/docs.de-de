---
title: '&gt;-Operator (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="bab81-102">Operator &gt; (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bab81-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="bab81-103">Alle numerischen und Emumerationstypen definieren einen relationalen „größer als“-Operator (`>`), der `true` zurückgibt, wenn der erste Operand größer dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="bab81-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bab81-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bab81-104">Remarks</span></span>  
 <span data-ttu-id="bab81-105">Benutzerdefinierte Typen können den Operator `>` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="bab81-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="bab81-106">Wenn `>` überladen ist, muss [<](../../../csharp/language-reference/operators/less-than-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="bab81-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="bab81-107">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="bab81-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab81-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bab81-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bab81-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bab81-109">See Also</span></span>  
 [<span data-ttu-id="bab81-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bab81-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bab81-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bab81-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bab81-112">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="bab81-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="bab81-113">explicit</span><span class="sxs-lookup"><span data-stu-id="bab81-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
