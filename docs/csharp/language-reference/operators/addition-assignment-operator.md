---
title: Operator += (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bcd56acad8e2b08585e5ae60f1c3cf8183b5664a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="444b1-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="444b1-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="444b1-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="444b1-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="444b1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="444b1-104">Remarks</span></span>  
 <span data-ttu-id="444b1-105">Ein Ausdruck mit dem Zuweisungsoperator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="444b1-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```csharp  
x += y  
```  
  
 <span data-ttu-id="444b1-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="444b1-106">is equivalent to</span></span>  
  
```csharp  
x = x + y  
```  
  
 <span data-ttu-id="444b1-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="444b1-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="444b1-108">Die Bedeutung des [+-Operators](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab (Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden usw.).</span><span class="sxs-lookup"><span data-stu-id="444b1-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="444b1-109">Der Operator `+=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [+-Operator](../../../csharp/language-reference/operators/addition-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="444b1-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="444b1-110">Der `+=`-Operator wird auch verwendet, um eine Methode zu bestimmen, die als Antwort auf ein Ereignis aufgerufen wird. Solche Methoden werden als Ereignishandler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="444b1-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="444b1-111">Die Verwendung des `+=`-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="444b1-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="444b1-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="444b1-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="444b1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="444b1-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="444b1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="444b1-114">See Also</span></span>  
 [<span data-ttu-id="444b1-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="444b1-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="444b1-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="444b1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="444b1-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="444b1-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
