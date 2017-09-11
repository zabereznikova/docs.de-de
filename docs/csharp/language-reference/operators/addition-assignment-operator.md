---
title: "Operator += (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
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
ms.openlocfilehash: 42567b2d8e7d9b694ce64ccb88e0fd4bfe05b020
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="870e4-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="870e4-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="870e4-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="870e4-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="870e4-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="870e4-104">Remarks</span></span>  
 <span data-ttu-id="870e4-105">Ein Ausdruck mit dem Zuweisungsoperator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="870e4-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="870e4-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="870e4-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="870e4-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="870e4-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="870e4-108">Die Bedeutung des [+-Operators](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab (Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden usw.).</span><span class="sxs-lookup"><span data-stu-id="870e4-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="870e4-109">Der Operator `+=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [+-Operator](../../../csharp/language-reference/operators/addition-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="870e4-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="870e4-110">Der `+=`-Operator wird auch verwendet, um eine Methode zu bestimmen, die als Antwort auf ein Ereignis aufgerufen wird. Solche Methoden werden als Ereignishandler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="870e4-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="870e4-111">Die Verwendung des `+=`-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="870e4-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="870e4-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="870e4-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="870e4-113">und [Delegaten](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="870e4-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="870e4-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="870e4-114">Example</span></span>  
 <span data-ttu-id="870e4-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="870e4-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870e4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="870e4-116">See Also</span></span>  
 <span data-ttu-id="870e4-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="870e4-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="870e4-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="870e4-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="870e4-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="870e4-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

