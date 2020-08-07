---
title: Delegaten mit benannten im Vergleich zu Anonyme Methoden – C#-Programmierhandbuch
description: Lernen Sie Delegaten mit benannten im Vergleich zu anonymen Methoden kennen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 940363b87e17b34feeffaff38ed498d6fcf6850a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302749"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="a560c-104">Delegaten mit benannten im Vergleich zu Anonyme Methoden (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a560c-104">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="a560c-105">Ein [Delegat](../../language-reference/builtin-types/reference-types.md) kann einer benannten Methode zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a560c-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="a560c-106">Wenn Sie einen Delegaten mit einer benannten Methode instanziieren, wird die Methode als Parameter übergeben:</span><span class="sxs-lookup"><span data-stu-id="a560c-106">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="a560c-107">Dies wird mit einer benannten Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a560c-107">This is called using a named method.</span></span> <span data-ttu-id="a560c-108">Mit einer benannten Methode erstellte Delegaten können entweder eine [statische](../../language-reference/keywords/static.md) Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="a560c-108">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="a560c-109">Benannte Methoden sind die einzige Möglichkeit, einen Delegaten in früheren Versionen von C# zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="a560c-109">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="a560c-110">Wenn das Erstellen einer neuen Methode jedoch einen unerwünschten Aufwand für Sie darstellt, können Sie in C# einen Delegaten instanziieren und sofort einen Codeblock bestimmen, den der Delegat bei seinem Aufruf verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a560c-110">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="a560c-111">Der Block kann entweder einen Lambdaausdruck oder eine anonyme Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="a560c-111">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="a560c-112">Weitere Informationen finden Sie unter [Anonyme Funktionen](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="a560c-112">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a560c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a560c-113">Remarks</span></span>  
 <span data-ttu-id="a560c-114">Die Methode, die Sie als Delegatparameter übergeben, muss die gleiche Signatur wie die Delegatdeklaration aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a560c-114">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="a560c-115">Eine Delegatinstanz kann entweder eine statische Methode oder eine Instanzmethode kapseln.</span><span class="sxs-lookup"><span data-stu-id="a560c-115">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="a560c-116">Obwohl der Delegat einen [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter verwenden kann, wird empfohlen, ihn nicht mit Multicast-Ereignisdelegaten zu verwenden, da Sie nicht wissen können, welcher Delegat aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a560c-116">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="a560c-117">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="a560c-117">Example 1</span></span>  
 <span data-ttu-id="a560c-118">In diesem einfachen Beispiel wird ein Delegat deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="a560c-118">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="a560c-119">Beachten Sie, dass der Delegat `Del` und die zugeordnete Methode `MultiplyNumbers` dieselbe Signatur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a560c-119">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="a560c-120">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="a560c-120">Example 2</span></span>  
 <span data-ttu-id="a560c-121">Im folgenden Beispiel wird ein Delegat sowohl einer statischen Methode als auch einer Instanzmethode zugeordnet und gibt von jeder spezifische Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="a560c-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a560c-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a560c-122">See also</span></span>

- [<span data-ttu-id="a560c-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a560c-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a560c-124">Delegaten</span><span class="sxs-lookup"><span data-stu-id="a560c-124">Delegates</span></span>](./index.md)
- [<span data-ttu-id="a560c-125">Kombinieren von Delegaten (Multicastdelegaten)</span><span class="sxs-lookup"><span data-stu-id="a560c-125">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="a560c-126">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a560c-126">Events</span></span>](../events/index.md)
