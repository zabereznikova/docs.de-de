---
title: Arrays als Objekte (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 07e824d21ffc02ba7a3c33507d22d1dc7a1ac638
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="fce23-102">Arrays als Objekte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="fce23-102">Arrays as Objects (C# Programming Guide)</span></span>
<span data-ttu-id="fce23-103">In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++.</span><span class="sxs-lookup"><span data-stu-id="fce23-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="fce23-104"><xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="fce23-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="fce23-105">Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt.</span><span class="sxs-lookup"><span data-stu-id="fce23-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="fce23-106">Ein Beispiel dafür wäre die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fce23-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="fce23-107">Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:</span><span class="sxs-lookup"><span data-stu-id="fce23-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <span data-ttu-id="fce23-108">Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.</span><span class="sxs-lookup"><span data-stu-id="fce23-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fce23-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fce23-109">Example</span></span>  
 <span data-ttu-id="fce23-110">In diesem Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fce23-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fce23-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fce23-111">See Also</span></span>  
 [<span data-ttu-id="fce23-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fce23-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fce23-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="fce23-113">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="fce23-114">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="fce23-114">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="fce23-115">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="fce23-115">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="fce23-116">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="fce23-116">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
