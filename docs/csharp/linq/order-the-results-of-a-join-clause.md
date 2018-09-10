---
title: Sortieren der Ergebnisse einer Join-Klausel (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie die Ergebnisse einer Join-Klausel in C# sortieren.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: 13cd6cb202cf67def17310db6d98e368ce837646
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516985"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="a967b-103">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="a967b-103">Order the results of a join clause</span></span>

<span data-ttu-id="a967b-104">Dieses Beispiel zeigt, wie Sie die Ergebnisse einer Verknüpfungsoperation sortieren.</span><span class="sxs-lookup"><span data-stu-id="a967b-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="a967b-105">Beachten Sie, dass die Sortierung nach der Verknüpfung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a967b-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="a967b-106">Obwohl Sie eine `orderby`-Klausel mit einer oder mehreren Quellsequenzen verwenden können, wird dies normalerweise nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a967b-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="a967b-107">Einige LINQ-Anbieter könnten diese Sortierung nach der Verknüpfung vielleicht nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a967b-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="a967b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a967b-108">Example</span></span>

<span data-ttu-id="a967b-109">Diese Abfrage erstellt eine Gruppenverknüpfung und sortiert die Gruppen anschließend anhand des Elements der Kategorie, das sich noch im Geltungsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="a967b-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="a967b-110">Innerhalb des anonymen Typinitialisierers ordnet eine Unterabfrage alle übereinstimmende Elemente aus der Produktsequenz.</span><span class="sxs-lookup"><span data-stu-id="a967b-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="a967b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a967b-111">See also</span></span>

- [<span data-ttu-id="a967b-112">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a967b-112">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="a967b-113">orderby-Klausel</span><span class="sxs-lookup"><span data-stu-id="a967b-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
- [<span data-ttu-id="a967b-114">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="a967b-114">join clause</span></span>](../language-reference/keywords/join-clause.md)  