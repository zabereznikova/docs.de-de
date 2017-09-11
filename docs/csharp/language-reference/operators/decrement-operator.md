---
title: "Operator -- (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="eb715-102">Operator -- (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eb715-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="eb715-103">Der Dekrementoperator (`--`) verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="eb715-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="eb715-104">Der Dekrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `--variable` und `variable--`.</span><span class="sxs-lookup"><span data-stu-id="eb715-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="eb715-105">Die erste Form stellt eine Präfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="eb715-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="eb715-106">Das Ergebnis der Operation ist der Wert des Operanden, „nachdem“ er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="eb715-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="eb715-107">Die zweite Form stellt eine Postfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="eb715-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="eb715-108">Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="eb715-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb715-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb715-109">Remarks</span></span>  
 <span data-ttu-id="eb715-110">Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="eb715-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="eb715-111">Benutzerdefinierte Typen können den Operator `--` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="eb715-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="eb715-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb715-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb715-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb715-113">Example</span></span>  
 <span data-ttu-id="eb715-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eb715-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb715-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb715-115">See Also</span></span>  
 <span data-ttu-id="eb715-116">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb715-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="eb715-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb715-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="eb715-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="eb715-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

