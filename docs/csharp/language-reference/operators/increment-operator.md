---
title: "Operator ++ (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="b45b5-102">Operator ++ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b45b5-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="b45b5-103">Der Inkrementoperator (`++`) erhöht seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="b45b5-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="b45b5-104">Der Inkrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `++variable` und `variable++`.</span><span class="sxs-lookup"><span data-stu-id="b45b5-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b45b5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b45b5-105">Remarks</span></span>  
 <span data-ttu-id="b45b5-106">Die erste Form stellt eine Präfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="b45b5-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="b45b5-107">Das Ergebnis der Operation ist der Wert des Operanden, nachdem er erhöht worden ist.</span><span class="sxs-lookup"><span data-stu-id="b45b5-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="b45b5-108">Die zweite Form stellt eine Postfixinkrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="b45b5-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="b45b5-109">Das Ergebnis der Operation ist der Wert des Operanden, bevor er erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="b45b5-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="b45b5-110">Für alle numerischen Typen und Enumerationstypen sind Inkrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="b45b5-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="b45b5-111">Benutzerdefinierte Typen können den Operator `++` überladen.</span><span class="sxs-lookup"><span data-stu-id="b45b5-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="b45b5-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="b45b5-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b45b5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b45b5-113">Example</span></span>  
 <span data-ttu-id="b45b5-114">[!code-cs[csRefOperatoren#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b45b5-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b45b5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b45b5-115">See Also</span></span>  
 <span data-ttu-id="b45b5-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b45b5-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b45b5-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b45b5-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b45b5-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b45b5-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

