---
title: Operator ++ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: a52f614ce1bbfb8e9d9be686b277c1e69f6f9d35
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44274595"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c7fef-102">Operator ++ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c7fef-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="c7fef-103">Der Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="c7fef-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="c7fef-104">Der Inkrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `++variable` und `variable++`.</span><span class="sxs-lookup"><span data-stu-id="c7fef-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7fef-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7fef-105">Remarks</span></span>  
 <span data-ttu-id="c7fef-106">Die erste Form stellt eine Präfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="c7fef-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="c7fef-107">Das Ergebnis der Operation ist der Wert des Operanden, nachdem er erhöht worden ist.</span><span class="sxs-lookup"><span data-stu-id="c7fef-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="c7fef-108">Die zweite Form stellt eine Postfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="c7fef-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="c7fef-109">Das Ergebnis der Operation ist der Wert des Operanden, bevor er erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="c7fef-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="c7fef-110">Für alle numerischen Typen und Enumerationstypen sind Inkrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="c7fef-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="c7fef-111">Benutzerdefinierte Typen können den Operator `++` überladen.</span><span class="sxs-lookup"><span data-stu-id="c7fef-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="c7fef-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="c7fef-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7fef-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7fef-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c7fef-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7fef-114">See Also</span></span>

- [<span data-ttu-id="c7fef-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c7fef-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c7fef-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7fef-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c7fef-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fef-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
