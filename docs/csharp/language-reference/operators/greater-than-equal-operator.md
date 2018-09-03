---
title: Operator &gt;= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 8749d1dc0670a5a76bda5ee0d69a4a142671c1e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481761"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="5ba45-102">Operator &gt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5ba45-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="5ba45-103">Alle numerischen und Emumerationstypen definieren einen relationalen „größer oder gleich“-Operator (`>=`), der `true` zurückgibt, wenn der erste Operand größer oder gleich dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5ba45-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ba45-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ba45-104">Remarks</span></span>  
 <span data-ttu-id="5ba45-105">Benutzerdefinierte Typen können den Operator `>=` überladen.</span><span class="sxs-lookup"><span data-stu-id="5ba45-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="5ba45-106">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="5ba45-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="5ba45-107">Wenn `>=` überladen ist, muss [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="5ba45-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="5ba45-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="5ba45-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ba45-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ba45-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5ba45-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ba45-110">See Also</span></span>

- [<span data-ttu-id="5ba45-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5ba45-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="5ba45-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5ba45-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5ba45-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5ba45-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
