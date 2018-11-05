---
title: Ausführen einer Unterabfrage für eine Gruppierungsoperation (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie eine Unterabfrage für eine Gruppierungsoperation mit LINQ in C# ausführen.
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 19be93fe695982e93abea9a59153a4245dce4a60
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846317"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="ee47e-103">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="ee47e-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="ee47e-104">In diesem Artikel werden zwei verschiedene Möglichkeiten gezeigt, um eine Abfrage zu erstellen, die Quelldaten in Gruppen sortiert und anschließend eine Unterabfrage für jede einzelne Gruppe ausführt.</span><span class="sxs-lookup"><span data-stu-id="ee47e-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="ee47e-105">Die grundlegende Technik in jedem Beispiel besteht darin, die Quellelemente mithilfe einer *Fortsetzung* namens `newGroup` zu gruppieren und anschließend eine neue Unterabfrage für `newGroup` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="ee47e-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="ee47e-106">Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ee47e-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="ee47e-107">Beachten Sie, dass in diesem speziellen Beispiel die endgültige Ausgabe keine Gruppe ist, sondern eine flache Sequenz von anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="ee47e-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="ee47e-108">Weitere Informationen zum Gruppieren finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ee47e-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="ee47e-109">Weitere Informationen zu Fortsetzungen finden Sie unter [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="ee47e-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="ee47e-110">Im folgenden Beispiel wird eine Datenstruktur im Arbeitsspeicher als Datenquelle verwendet, jedoch gelten für jede Art von LINQ-Datenquelle die gleichen Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="ee47e-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee47e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee47e-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="ee47e-112">Dieses Beispiel enthält Verweise auf Objekte, die im Beispielcode in [Abfragen einer Sammlung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ee47e-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)] 

<span data-ttu-id="ee47e-113">Die Abfrage im oben stehenden Codeausschnitt können auch per Methodensyntax geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ee47e-113">The query in the snippet above can also be written using method syntax.</span></span> <span data-ttu-id="ee47e-114">Der folgende Codeausschnitt weist eine semantisch äquivalente Abfrage auf, die per Methodensyntax geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="ee47e-114">The following code snippet has a semantically equivalent query written using method syntax.</span></span>

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a><span data-ttu-id="ee47e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee47e-115">See also</span></span>

- [<span data-ttu-id="ee47e-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ee47e-116">Language Integrated Query (LINQ)</span></span>](index.md)
