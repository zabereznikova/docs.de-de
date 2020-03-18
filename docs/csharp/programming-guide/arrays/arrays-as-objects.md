---
title: Arrays als Objekte – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: d8b929eccf9be259874d03dd93f49a49798bb349
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715094"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="d7692-102">Arrays als Objekte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d7692-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="d7692-103">In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++.</span><span class="sxs-lookup"><span data-stu-id="d7692-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="d7692-104"><xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="d7692-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="d7692-105">Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt.</span><span class="sxs-lookup"><span data-stu-id="d7692-105">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="d7692-106">Ein Beispiel dafür ist die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d7692-106">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="d7692-107">Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:</span><span class="sxs-lookup"><span data-stu-id="d7692-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="d7692-108">Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.</span><span class="sxs-lookup"><span data-stu-id="d7692-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>

## <a name="example"></a><span data-ttu-id="d7692-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7692-109">Example</span></span>

<span data-ttu-id="d7692-110">In diesem Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7692-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="d7692-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7692-111">See also</span></span>

- [<span data-ttu-id="d7692-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d7692-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d7692-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="d7692-113">Arrays</span></span>](./index.md)
- [<span data-ttu-id="d7692-114">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="d7692-114">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="d7692-115">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="d7692-115">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="d7692-116">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="d7692-116">Jagged Arrays</span></span>](./jagged-arrays.md)
