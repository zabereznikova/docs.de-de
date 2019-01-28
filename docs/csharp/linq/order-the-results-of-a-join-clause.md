---
title: Sortieren der Ergebnisse einer Join-Klausel (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie die Ergebnisse einer Join-Klausel in C# sortieren.
ms.date: 12/01/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f60000b83bf378dd8740b7255d421dd4335614c4
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857887"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="b969b-103">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="b969b-103">Order the results of a join clause</span></span>

<span data-ttu-id="b969b-104">Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren.</span><span class="sxs-lookup"><span data-stu-id="b969b-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="b969b-105">Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b969b-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="b969b-106">Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b969b-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="b969b-107">Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b969b-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="b969b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b969b-108">Example</span></span>

<span data-ttu-id="b969b-109">Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="b969b-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="b969b-110">Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.</span><span class="sxs-lookup"><span data-stu-id="b969b-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="b969b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b969b-111">See also</span></span>

- [<span data-ttu-id="b969b-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b969b-112">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="b969b-113">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="b969b-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="b969b-114">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="b969b-114">join clause</span></span>](../language-reference/keywords/join-clause.md)
