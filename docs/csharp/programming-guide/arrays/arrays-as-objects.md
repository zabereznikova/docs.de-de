---
title: Arrays als Objekte – C#-Programmierhandbuch
description: Arrays in C# sind Objekte des abstrakten Basistyparrays. Sie können die Eigenschaften und andere Klassenmember des Arrays verwenden, z. B. die Length-Eigenschaft.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: 984def3ef74b07d7099fae6cae6d6f8ce7e03e12
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474721"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="b832b-104">Arrays als Objekte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b832b-104">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="b832b-105">In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++.</span><span class="sxs-lookup"><span data-stu-id="b832b-105">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="b832b-106"><xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="b832b-106"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="b832b-107">Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt.</span><span class="sxs-lookup"><span data-stu-id="b832b-107">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="b832b-108">Ein Beispiel dafür ist die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b832b-108">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="b832b-109">Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:</span><span class="sxs-lookup"><span data-stu-id="b832b-109">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="b832b-110">Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.</span><span class="sxs-lookup"><span data-stu-id="b832b-110">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="b832b-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b832b-111">Example</span></span>

<span data-ttu-id="b832b-112">In diesem Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b832b-112">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="b832b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b832b-113">See also</span></span>

- [<span data-ttu-id="b832b-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b832b-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b832b-115">Arrays</span><span class="sxs-lookup"><span data-stu-id="b832b-115">Arrays</span></span>](./index.md)
- [<span data-ttu-id="b832b-116">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="b832b-116">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="b832b-117">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="b832b-117">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="b832b-118">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="b832b-118">Jagged Arrays</span></span>](./jagged-arrays.md)
