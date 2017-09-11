---
title: Delegaten mit benannten im Vergleich zu Anonyme Methoden (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
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
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="8714b-102">Delegaten mit benannten im Vergleich zu Anonyme Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8714b-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="8714b-103">Ein [Delegat](../../../csharp/language-reference/keywords/delegate.md) kann einer benannten Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8714b-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="8714b-104">Wenn Sie einen Delegaten mit einer benannten Methode instanziieren, wird die Methode als Parameter übergeben:</span><span class="sxs-lookup"><span data-stu-id="8714b-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 <span data-ttu-id="8714b-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8714b-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="8714b-106">Dies wird mit einer benannten Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8714b-106">This is called using a named method.</span></span> <span data-ttu-id="8714b-107">Mit einer benannten Methode erstellte Delegaten können entweder eine [statische](../../../csharp/language-reference/keywords/static.md) Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="8714b-107">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="8714b-108">Benannte Methoden sind die einzige Möglichkeit, einen Delegaten in früheren Versionen von C# zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="8714b-108">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="8714b-109">Wenn das Erstellen einer neuen Methode jedoch einen unerwünschten Aufwand für Sie darstellt, können Sie in C# einen Delegaten instanziieren und sofort einen Codeblock bestimmen, den der Delegat bei seinem Aufruf verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8714b-109">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="8714b-110">Der Block kann entweder einen Lambdaausdruck oder eine anonyme Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="8714b-110">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="8714b-111">Weitere Informationen finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="8714b-111">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8714b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8714b-112">Remarks</span></span>  
 <span data-ttu-id="8714b-113">Die Methode, die Sie als Delegatparameter übergeben, muss die gleiche Signatur wie die Delegatdeklaration aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8714b-113">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="8714b-114">Eine Delegatinstanz kann entweder eine statische Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="8714b-114">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="8714b-115">Obwohl der Delegat einen [out](../../../csharp/language-reference/keywords/out.md)-Parameter verwenden kann, wird empfohlen, ihn nicht mit Multicast-Ereignisdelegaten zu verwenden, da Sie nicht wissen können, welcher Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8714b-115">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="8714b-116">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="8714b-116">Example 1</span></span>  
 <span data-ttu-id="8714b-117">In diesem einfachen Beispiel wird ein Delegat deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="8714b-117">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="8714b-118">Beachten Sie, dass der Delegat `Del` und die zugeordnete Methode `MultiplyNumbers` dieselbe Signatur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8714b-118">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 <span data-ttu-id="8714b-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8714b-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="8714b-120">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="8714b-120">Example 2</span></span>  
 <span data-ttu-id="8714b-121">Im folgenden Beispiel wird ein Delegat sowohl einer statischen Methode als auch einer Instanzmethode zugeordnet und gibt von jeder spezifische Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="8714b-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 <span data-ttu-id="8714b-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8714b-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8714b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8714b-123">See Also</span></span>  
 <span data-ttu-id="8714b-124">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8714b-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8714b-125">[Delegaten](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="8714b-125">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="8714b-126">[Anonyme Methoden](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="8714b-126">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="8714b-127">[Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="8714b-127">[How to: Combine Delegates (Multicast Delegates)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span></span>  
 [<span data-ttu-id="8714b-128">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8714b-128">Events</span></span>](../../../csharp/programming-guide/events/index.md)

