---
title: Verwenden von „foreach“ mit Arrays – C#-Programmierhandbuch
description: Die foreach-Anweisung in C# durchläuft die Elemente eines Arrays. Bei eindimensionalen Arrays verarbeitet die foreach-Anweisung Prozesselemente in zunehmender Indexreihenfolge.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474539"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="a67e8-104">Verwenden von foreach mit Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a67e8-104">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="a67e8-105">Die Anweisung [foreach](../../language-reference/keywords/foreach-in.md) stellt eine einfache, klare Methode bereit, um die Elemente eines Arrays zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a67e8-105">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="a67e8-106">Bei eindimensionalen Arrays verarbeitet die Anweisung `foreach` Elemente in aufsteigender Indexreihenfolge, beginnend bei Index 0 und endend bei Index `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="a67e8-106">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="a67e8-107">Bei mehrdimensionalen Arrays werden Elemente so durchlaufen, dass die Indizes der äußersten rechten Dimension zuerst erhöht werden, dann die der links daneben liegenden Dimension und so weiter, bis die linke Seite erreicht ist:</span><span class="sxs-lookup"><span data-stu-id="a67e8-107">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="a67e8-108">Bei mehrdimensionalen Arrays haben Sie jedoch eine größere Kontrolle über die Reihenfolge bei der Verarbeitung von Arrayelementen, wenn Sie eine geschachtelte [for](../../language-reference/keywords/for.md)-Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="a67e8-108">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="a67e8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a67e8-109">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="a67e8-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a67e8-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a67e8-111">Arrays</span><span class="sxs-lookup"><span data-stu-id="a67e8-111">Arrays</span></span>](index.md)
- [<span data-ttu-id="a67e8-112">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="a67e8-112">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="a67e8-113">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="a67e8-113">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="a67e8-114">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="a67e8-114">Jagged Arrays</span></span>](jagged-arrays.md)
