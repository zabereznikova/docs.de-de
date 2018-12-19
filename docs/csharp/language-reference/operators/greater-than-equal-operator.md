---
title: '&gt;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 9bea9034d2998a589fefca19f41444c9aced6e13
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237713"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="f800d-102">&gt;=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f800d-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="f800d-103">Alle numerischen und Emumerationstypen definieren einen relationalen „größer oder gleich“-Operator (`>=`), der `true` zurückgibt, wenn der erste Operand größer oder gleich dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f800d-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f800d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f800d-104">Remarks</span></span>  
 <span data-ttu-id="f800d-105">Benutzerdefinierte Typen können den Operator `>=` überladen.</span><span class="sxs-lookup"><span data-stu-id="f800d-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="f800d-106">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="f800d-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="f800d-107">Wenn `>=` überladen ist, muss [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="f800d-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="f800d-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="f800d-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f800d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f800d-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f800d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f800d-110">See Also</span></span>

- [<span data-ttu-id="f800d-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f800d-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f800d-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f800d-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f800d-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="f800d-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
