---
title: Delegaten mit benannten im Vergleich zu Anonyme Methoden – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 586ad5a59eebb03ed9ed6bea68d232a6b249c3c9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241487"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="48e2b-102">Delegaten mit benannten im Vergleich zu Anonyme Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="48e2b-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="48e2b-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) kann einer benannten Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="48e2b-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="48e2b-104">Wenn Sie einen Delegaten mit einer benannten Methode instanziieren, wird die Methode als Parameter übergeben:</span><span class="sxs-lookup"><span data-stu-id="48e2b-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 <span data-ttu-id="48e2b-105">Dies wird mit einer benannten Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="48e2b-105">This is called using a named method.</span></span> <span data-ttu-id="48e2b-106">Mit einer benannten Methode erstellte Delegaten können entweder eine [statische](../../../csharp/language-reference/keywords/static.md) Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="48e2b-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="48e2b-107">Benannte Methoden sind die einzige Möglichkeit, einen Delegaten in früheren Versionen von C# zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="48e2b-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="48e2b-108">Wenn das Erstellen einer neuen Methode jedoch einen unerwünschten Aufwand für Sie darstellt, können Sie in C# einen Delegaten instanziieren und sofort einen Codeblock bestimmen, den der Delegat bei seinem Aufruf verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="48e2b-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="48e2b-109">Der Block kann entweder einen Lambdaausdruck oder eine anonyme Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="48e2b-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="48e2b-110">Weitere Informationen finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="48e2b-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48e2b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48e2b-111">Remarks</span></span>  
 <span data-ttu-id="48e2b-112">Die Methode, die Sie als Delegatparameter übergeben, muss die gleiche Signatur wie die Delegatdeklaration aufweisen.</span><span class="sxs-lookup"><span data-stu-id="48e2b-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="48e2b-113">Eine Delegatinstanz kann entweder eine statische Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="48e2b-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="48e2b-114">Obwohl der Delegat einen [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter verwenden kann, wird empfohlen, ihn nicht mit Multicast-Ereignisdelegaten zu verwenden, da Sie nicht wissen können, welcher Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="48e2b-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="48e2b-115">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="48e2b-115">Example 1</span></span>  
 <span data-ttu-id="48e2b-116">In diesem einfachen Beispiel wird ein Delegat deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="48e2b-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="48e2b-117">Beachten Sie, dass der Delegat `Del` und die zugeordnete Methode `MultiplyNumbers` dieselbe Signatur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="48e2b-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="48e2b-118">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="48e2b-118">Example 2</span></span>  
 <span data-ttu-id="48e2b-119">Im folgenden Beispiel wird ein Delegat sowohl einer statischen Methode als auch einer Instanzmethode zugeordnet und gibt von jeder spezifische Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="48e2b-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="48e2b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48e2b-120">See Also</span></span>

- [<span data-ttu-id="48e2b-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="48e2b-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="48e2b-122">Delegaten</span><span class="sxs-lookup"><span data-stu-id="48e2b-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="48e2b-123">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="48e2b-123">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [<span data-ttu-id="48e2b-124">Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten)</span><span class="sxs-lookup"><span data-stu-id="48e2b-124">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
- [<span data-ttu-id="48e2b-125">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="48e2b-125">Events</span></span>](../../../csharp/programming-guide/events/index.md)
