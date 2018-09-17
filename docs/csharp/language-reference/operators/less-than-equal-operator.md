---
title: Operator &lt;= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: afbb932c1be010790236bec73a36acf0f01b97f4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45595056"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="7b57b-102">Operator &lt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7b57b-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="7b57b-103">Alle numerischen und Emumerationstypen definieren einen relationalen „weniger oder gleich“-Operator (`<=`), der `true` zurückgibt, wenn der erste Operand weniger oder gleich dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7b57b-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b57b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b57b-104">Remarks</span></span>  
 <span data-ttu-id="7b57b-105">Benutzerdefinierte Typen können den Operator `<=` überladen.</span><span class="sxs-lookup"><span data-stu-id="7b57b-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="7b57b-106">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="7b57b-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="7b57b-107">Wenn `<=` überladen ist, muss [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="7b57b-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="7b57b-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="7b57b-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b57b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b57b-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7b57b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b57b-110">See Also</span></span>

- [<span data-ttu-id="7b57b-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7b57b-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7b57b-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7b57b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7b57b-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7b57b-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="7b57b-114">explicit</span><span class="sxs-lookup"><span data-stu-id="7b57b-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
