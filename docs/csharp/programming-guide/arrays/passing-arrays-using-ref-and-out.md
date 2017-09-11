---
title: "Übergeben von Arrays mithilfe von \"ref\" und \"out\" (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="cd7c4-102">Übergeben von Arrays mithilfe von "ref" und "out" (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cd7c4-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="cd7c4-103">Wie alle [out](../../../csharp/language-reference/keywords/out.md)-Parameter muss auch ein `out`-Parameter eines Arraytyps vor der Verwendung zugewiesen werden, d.h., er muss vom Aufgerufenen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="cd7c4-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cd7c4-104">For example:</span></span>  
  
 <span data-ttu-id="cd7c4-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd7c4-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="cd7c4-106">Wie alle [ref](../../../csharp/language-reference/keywords/ref.md)-Parameter muss auch ein `ref`-Parameter eines Arraytyps vom Aufrufer definitiv zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="cd7c4-107">Daher besteht keine Notwendigkeit, dass die definitive Zuweisung vom Aufgerufenen vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="cd7c4-108">Ein `ref`-Parameter eines Arraytyps kann als Ergebnis des Aufrufs geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="cd7c4-109">Beispielsweise kann dem Array der Wert [NULL](../../../csharp/language-reference/keywords/null.md) zugewiesen werden, oder es kann mit einem anderen Array initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="cd7c4-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cd7c4-110">For example:</span></span>  
  
 <span data-ttu-id="cd7c4-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd7c4-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="cd7c4-112">In den beiden folgenden Beispielen wird der Unterschied zwischen `out` und `ref` bei der Übergabe von Arrays an Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd7c4-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd7c4-113">Example</span></span>  
 <span data-ttu-id="cd7c4-114">In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) deklariert und in der `FillArray`-Methode initialisiert.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="cd7c4-115">Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="cd7c4-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd7c4-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd7c4-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd7c4-117">Example</span></span>  
 <span data-ttu-id="cd7c4-118">In diesem Beispiel wird das Array `theArray` im Aufrufer (der `Main`-Methode) initialisiert und mithilfe des `FillArray`-Parameters an die `ref`-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="cd7c4-119">Einige Arrayelemente werden in der `FillArray`-Methode aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="cd7c4-120">Anschließend werden die Elemente des Arrays an den Aufrufer zurückgegeben und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="cd7c4-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="cd7c4-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7c4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd7c4-122">See Also</span></span>  
 <span data-ttu-id="cd7c4-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="cd7c4-124">[Modifizierer für out-Parameter](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="cd7c4-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cd7c4-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="cd7c4-127">[Eindimensionale Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="cd7c4-128">[Mehrdimensionale Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="cd7c4-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="cd7c4-129">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="cd7c4-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

