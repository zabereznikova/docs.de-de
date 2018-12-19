---
title: '&lt;=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 950ba3fc02e015f2574d123d1fd9adc116aae045
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243451"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="4c002-102">&lt;=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4c002-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="4c002-103">Alle numerischen und Emumerationstypen definieren einen relationalen „weniger oder gleich“-Operator (`<=`), der `true` zurückgibt, wenn der erste Operand weniger oder gleich dem zweiten ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="4c002-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c002-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c002-104">Remarks</span></span>  
 <span data-ttu-id="4c002-105">Benutzerdefinierte Typen können den Operator `<=` überladen.</span><span class="sxs-lookup"><span data-stu-id="4c002-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="4c002-106">Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="4c002-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="4c002-107">Wenn `<=` überladen ist, muss [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="4c002-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="4c002-108">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="4c002-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c002-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c002-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4c002-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c002-110">See Also</span></span>

- [<span data-ttu-id="4c002-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4c002-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4c002-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4c002-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4c002-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="4c002-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="4c002-114">explicit</span><span class="sxs-lookup"><span data-stu-id="4c002-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
