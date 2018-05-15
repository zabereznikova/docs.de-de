---
title: Verwenden von foreach mit Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="0e9fb-102">Verwenden von foreach mit Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0e9fb-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="0e9fb-103">C# enthält außerdem die [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0e9fb-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="0e9fb-104">Diese Anweisung stellt eine einfache, klare Methode bereit, um die Elemente eines Arrays oder einer aufzählbaren Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="0e9fb-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="0e9fb-105">Die `foreach`-Anweisung verarbeitet Elemente in der Reihenfolge, die vom Array oder Enumerator des Auflistungstyps zurückgegeben wird, also normalerweise vom nullten bis zum letzten Element.</span><span class="sxs-lookup"><span data-stu-id="0e9fb-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="0e9fb-106">Durch folgenden Code wird beispielsweise ein Array mit dem Namen `numbers` erstellt, das mithilfe der `foreach`-Anweisung durchlaufen wird:</span><span class="sxs-lookup"><span data-stu-id="0e9fb-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 <span data-ttu-id="0e9fb-107">Bei mehrdimensionalen Arrays können Sie dieselbe Methode zum Durchlaufen der Elemente verwenden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0e9fb-107">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 <span data-ttu-id="0e9fb-108">Bei mehrdimensionalen Arrays haben Sie jedoch eine größere Kontrolle über die Arrayelemente, indem Sie eine geschachtelte [for](../../../csharp/language-reference/keywords/for.md)-Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="0e9fb-108">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9fb-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e9fb-109">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="0e9fb-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0e9fb-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0e9fb-111">Arrays</span><span class="sxs-lookup"><span data-stu-id="0e9fb-111">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="0e9fb-112">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="0e9fb-112">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="0e9fb-113">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="0e9fb-113">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="0e9fb-114">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="0e9fb-114">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
