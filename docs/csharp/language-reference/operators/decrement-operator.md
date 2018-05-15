---
title: Operator -- (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 25f301bc0b2bc9bf51b0a44f26b2efabae00e452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="---operator-c-reference"></a><span data-ttu-id="703b8-102">Operator -- (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="703b8-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="703b8-103">Der Dekrementoperator (`--`) verringert seinen Operanden um 1.</span><span class="sxs-lookup"><span data-stu-id="703b8-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="703b8-104">Der Dekrementoperator kann vor oder hinter seinem Operanden angezeigt werden: `--variable` und `variable--`.</span><span class="sxs-lookup"><span data-stu-id="703b8-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="703b8-105">Die erste Form stellt eine Präfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="703b8-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="703b8-106">Das Ergebnis der Operation ist der Wert des Operanden, „nachdem“ er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="703b8-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="703b8-107">Die zweite Form stellt eine Postfixdekrementoperation dar.</span><span class="sxs-lookup"><span data-stu-id="703b8-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="703b8-108">Das Ergebnis der Operation ist der Wert des Operanden, bevor er vermindert worden ist.</span><span class="sxs-lookup"><span data-stu-id="703b8-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="703b8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="703b8-109">Remarks</span></span>  
 <span data-ttu-id="703b8-110">Für alle numerischen Typen und Enumerationstypen sind Dekrementoperatoren vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="703b8-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="703b8-111">Benutzerdefinierte Typen können den Operator `--` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="703b8-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="703b8-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="703b8-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="703b8-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="703b8-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="703b8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="703b8-114">See Also</span></span>  
 [<span data-ttu-id="703b8-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="703b8-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="703b8-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="703b8-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="703b8-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="703b8-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
