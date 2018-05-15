---
title: Operator ++ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="517b2-102">Operator ++ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="517b2-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="517b2-103">Der Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="517b2-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="517b2-104">Der Inkrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `++variable` und `variable++`.</span><span class="sxs-lookup"><span data-stu-id="517b2-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="517b2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="517b2-105">Remarks</span></span>  
 <span data-ttu-id="517b2-106">Die erste Form stellt eine Präfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="517b2-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="517b2-107">Das Ergebnis der Operation ist der Wert des Operanden, nachdem er erhöht worden ist.</span><span class="sxs-lookup"><span data-stu-id="517b2-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="517b2-108">Die zweite Form stellt eine Postfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="517b2-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="517b2-109">Das Ergebnis der Operation ist der Wert des Operanden, bevor er erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="517b2-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="517b2-110">Für alle numerischen Typen und Enumerationstypen sind Inkrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="517b2-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="517b2-111">Benutzerdefinierte Typen können den Operator `++` überladen.</span><span class="sxs-lookup"><span data-stu-id="517b2-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="517b2-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="517b2-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="517b2-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="517b2-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="517b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="517b2-114">See Also</span></span>  
 [<span data-ttu-id="517b2-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="517b2-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="517b2-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="517b2-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="517b2-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="517b2-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
