---
title: Operator -= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 443f0d717288a491838d23eaa63218150bd346d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-c-reference"></a><span data-ttu-id="420d1-102">Operator -= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="420d1-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="420d1-103">Der Subtraktionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="420d1-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="420d1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="420d1-104">Remarks</span></span>  
 <span data-ttu-id="420d1-105">Ein Ausdruck mit dem Zuweisungsoperator `-=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="420d1-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```  
x -= y  
```  
  
 <span data-ttu-id="420d1-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="420d1-106">is equivalent to</span></span>  
  
```  
x = x - y  
```  
  
 <span data-ttu-id="420d1-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="420d1-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="420d1-108">Die Bedeutung des [Operators -](../../../csharp/language-reference/operators/subtraction-operator.md) hängt von den Typen `x` und `y` (Subtraktion für nummerische Operanden, Delegatentfernung für Delegatoperatoren usw.) ab.</span><span class="sxs-lookup"><span data-stu-id="420d1-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="420d1-109">Der Operator `-=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[- Operator](../../../csharp/language-reference/operators/subtraction-operator.md) überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="420d1-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="420d1-110">Der Operator -= wird auch in C# verwendet, um ein Ereignisabonnement zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="420d1-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="420d1-111">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="420d1-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="420d1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="420d1-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="420d1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="420d1-113">See Also</span></span>  
 [<span data-ttu-id="420d1-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="420d1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="420d1-115">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="420d1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="420d1-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="420d1-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
