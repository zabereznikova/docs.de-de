---
title: "Operator += (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: de83f48fc644d8b232d9ef9e1698272f20a27d65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="27f7f-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="27f7f-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="27f7f-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="27f7f-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27f7f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27f7f-104">Remarks</span></span>  
 <span data-ttu-id="27f7f-105">Ein Ausdruck mit dem Zuweisungsoperator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="27f7f-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="27f7f-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="27f7f-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="27f7f-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="27f7f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="27f7f-108">Die Bedeutung des [+-Operators](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab (Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden usw.).</span><span class="sxs-lookup"><span data-stu-id="27f7f-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="27f7f-109">Der Operator `+=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [+-Operator](../../../csharp/language-reference/operators/addition-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="27f7f-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="27f7f-110">Der `+=`-Operator wird auch verwendet, um eine Methode zu bestimmen, die als Antwort auf ein Ereignis aufgerufen wird. Solche Methoden werden als Ereignishandler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="27f7f-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="27f7f-111">Die Verwendung des `+=`-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="27f7f-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="27f7f-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="27f7f-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27f7f-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27f7f-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="27f7f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27f7f-114">See Also</span></span>  
 [<span data-ttu-id="27f7f-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="27f7f-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="27f7f-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="27f7f-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="27f7f-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="27f7f-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
