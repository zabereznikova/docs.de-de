---
title: Verwenden von „foreach“ mit Arrays – C#-Programmierhandbuch
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: bb121b0f5d990ef6e596b34a45606e2abde6811a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705677"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="56fef-102">Verwenden von foreach mit Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="56fef-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="56fef-103">Die Anweisung [foreach](../../language-reference/keywords/foreach-in.md) stellt eine einfache, klare Methode bereit, um die Elemente eines Arrays zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="56fef-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="56fef-104">Bei eindimensionalen Arrays verarbeitet die Anweisung `foreach` Elemente in aufsteigender Indexreihenfolge, beginnend bei Index 0 und endend bei Index `Length - 1`:</span><span class="sxs-lookup"><span data-stu-id="56fef-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="56fef-105">Bei mehrdimensionalen Arrays werden Elemente so durchlaufen, dass die Indizes der äußersten rechten Dimension zuerst erhöht werden, dann die der links daneben liegenden Dimension und so weiter, bis die linke Seite erreicht ist:</span><span class="sxs-lookup"><span data-stu-id="56fef-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="56fef-106">Bei mehrdimensionalen Arrays haben Sie jedoch eine größere Kontrolle über die Reihenfolge bei der Verarbeitung von Arrayelementen, wenn Sie eine geschachtelte [for](../../language-reference/keywords/for.md)-Schleife verwenden.</span><span class="sxs-lookup"><span data-stu-id="56fef-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="56fef-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56fef-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="56fef-108">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="56fef-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="56fef-109">Arrays</span><span class="sxs-lookup"><span data-stu-id="56fef-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="56fef-110">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="56fef-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="56fef-111">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="56fef-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="56fef-112">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="56fef-112">Jagged Arrays</span></span>](jagged-arrays.md)
