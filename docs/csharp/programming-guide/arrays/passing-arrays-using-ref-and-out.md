---
title: "Übergeben von Arrays mithilfe von \"ref\" und \"out\" (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2d4e613491b26e82523d230398af3ec34b4d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="9f5e0-102">Übergeben von Arrays mithilfe von "ref" und "out" (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9f5e0-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="9f5e0-103">Wie alle [out](../../../csharp/language-reference/keywords/out.md)-Parameter muss auch ein `out`-Parameter eines Arraytyps vor der Verwendung zugewiesen werden, d.h., er muss vom Aufgerufenen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="9f5e0-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f5e0-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="9f5e0-105">Wie alle [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter muss auch ein `ref`-Parameter eines Arraytyps vom Aufrufer definitiv zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="9f5e0-106">Daher besteht keine Notwendigkeit, dass die definitive Zuweisung vom Aufgerufenen vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="9f5e0-107">Ein `ref`-Parameter eines Arraytyps kann als Ergebnis des Aufrufs geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="9f5e0-108">Beispielsweise kann dem Array der Wert [NULL](../../../csharp/language-reference/keywords/null.md) zugewiesen werden, oder es kann mit einem anderen Array initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="9f5e0-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f5e0-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="9f5e0-110">In den beiden folgenden Beispielen wird der Unterschied zwischen `out` und `ref` bei der Übergabe von Arrays an Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f5e0-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f5e0-111">Example</span></span>  
 <span data-ttu-id="9f5e0-112">In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) deklariert und in der `FillArray`-Methode initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="9f5e0-113">Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="9f5e0-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f5e0-114">Example</span></span>  
 <span data-ttu-id="9f5e0-115">In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) initialisiert und mithilfe des `FillArray`-Parameters an die `ref`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="9f5e0-116">Einige Arrayelemente werden in der `FillArray`-Methode aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="9f5e0-117">Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f5e0-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9f5e0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f5e0-118">See Also</span></span>  
 [<span data-ttu-id="9f5e0-119">ref</span><span class="sxs-lookup"><span data-stu-id="9f5e0-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="9f5e0-120">Modifizierer für out-Parameter</span><span class="sxs-lookup"><span data-stu-id="9f5e0-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="9f5e0-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9f5e0-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9f5e0-122">Arrays</span><span class="sxs-lookup"><span data-stu-id="9f5e0-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="9f5e0-123">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="9f5e0-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="9f5e0-124">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="9f5e0-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="9f5e0-125">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="9f5e0-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
