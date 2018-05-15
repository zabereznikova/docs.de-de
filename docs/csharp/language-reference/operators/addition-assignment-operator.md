---
title: Operator += (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 90967dcdccfb71995ac83e0dd52ea7bd86f136be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="be736-102">Operator += (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="be736-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="be736-103">Der Additionszuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="be736-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be736-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be736-104">Remarks</span></span>  
 <span data-ttu-id="be736-105">Ein Ausdruck mit dem Zuweisungsoperator `+=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="be736-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="be736-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="be736-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="be736-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="be736-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="be736-108">Die Bedeutung des [+-Operators](../../../csharp/language-reference/operators/addition-operator.md) hängt von den Typen von `x` und `y` ab (Addition für numerische Operanden, Verkettung für Zeichenfolgenoperanden usw.).</span><span class="sxs-lookup"><span data-stu-id="be736-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="be736-109">Der Operator `+=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [+-Operator](../../../csharp/language-reference/operators/addition-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="be736-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="be736-110">Der `+=`-Operator wird auch verwendet, um eine Methode zu bestimmen, die als Antwort auf ein Ereignis aufgerufen wird. Solche Methoden werden als Ereignishandler bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="be736-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="be736-111">Die Verwendung des `+=`-Operators in diesem Kontext wird als *Abonnieren eines Ereignisses* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="be736-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="be736-112">Weitere Informationen finden Sie unter [Vorgehensweise: Abonnieren von Ereignissen und Kündigen von Ereignisabonnements](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="be736-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be736-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be736-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="be736-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be736-114">See Also</span></span>  
 [<span data-ttu-id="be736-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="be736-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="be736-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="be736-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be736-117">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="be736-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
