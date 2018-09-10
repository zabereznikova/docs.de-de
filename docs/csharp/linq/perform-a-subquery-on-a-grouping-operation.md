---
title: Ausführen einer Unterabfrage für eine Gruppierungsoperation (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie eine Unterabfrage für eine Gruppierungsoperation mit LINQ in C# ausführen.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 514db81b80557a3026589f00177910cc9446c0f4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213052"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="d2b86-103">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="d2b86-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="d2b86-104">In diesem Artikel werden zwei verschiedene Möglichkeiten gezeigt, um eine Abfrage zu erstellen, die Quelldaten in Gruppen sortiert und anschließend eine Unterabfrage für jede einzelne Gruppe ausführt.</span><span class="sxs-lookup"><span data-stu-id="d2b86-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="d2b86-105">Die grundlegende Technik in jedem Beispiel besteht darin, die Quellelemente mithilfe einer *Fortsetzung* namens `newGroup` zu gruppieren und anschließend eine neue Unterabfrage für `newGroup` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="d2b86-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="d2b86-106">Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d2b86-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="d2b86-107">Beachten Sie, dass in diesem speziellen Beispiel die endgültige Ausgabe keine Gruppe ist, sondern eine flache Sequenz von anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="d2b86-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="d2b86-108">Weitere Informationen zum Gruppieren finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d2b86-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="d2b86-109">Weitere Informationen zu Fortsetzungen finden Sie unter [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="d2b86-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="d2b86-110">Im folgenden Beispiel wird eine Datenstruktur im Arbeitsspeicher als Datenquelle verwendet, jedoch gelten für jede Art von LINQ-Datenquelle die gleichen Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="d2b86-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2b86-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2b86-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="d2b86-112">Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d2b86-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="d2b86-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2b86-113">See also</span></span>

- [<span data-ttu-id="d2b86-114">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="d2b86-114">Language Integrated Query (LINQ)</span></span>](index.md)
