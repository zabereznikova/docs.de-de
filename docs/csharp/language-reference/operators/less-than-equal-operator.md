---
title: Operator &lt;= (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 931843783888a844d9f90f273b2362d327e8ccbc
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="d71c3-102">Operator &lt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d71c3-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="d71c3-103">Alle numerischen und Emumerationstypen definieren einen relationalen „weniger oder gleich“-Operator (`<=`), der `true` zurückgibt, wenn der erste Operand weniger oder gleich dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d71c3-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d71c3-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d71c3-104">Remarks</span></span>  
 <span data-ttu-id="d71c3-105">Benutzerdefinierte Typen können den Operator `<=` überladen.</span><span class="sxs-lookup"><span data-stu-id="d71c3-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="d71c3-106">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="d71c3-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="d71c3-107">Wenn `<=` überladen ist, muss [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="d71c3-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="d71c3-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="d71c3-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d71c3-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d71c3-109">Example</span></span>  
 <span data-ttu-id="d71c3-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d71c3-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d71c3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d71c3-111">See Also</span></span>  
 <span data-ttu-id="d71c3-112">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d71c3-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d71c3-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d71c3-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d71c3-114">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="d71c3-114">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="d71c3-115">explicit</span><span class="sxs-lookup"><span data-stu-id="d71c3-115">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

