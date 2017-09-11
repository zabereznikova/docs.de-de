---
title: "Ausführen einer Unterabfrage für eine Gruppierungsoperation"
description: "So führen Sie eine Unterabfrage für eine Gruppierungsoperation aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68acc07e0c33d042123d3cd403a73d58a7c3d245
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="ba309-104">Ausführen einer Unterabfrage für eine Gruppierungsoperation</span><span class="sxs-lookup"><span data-stu-id="ba309-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="ba309-105">In diesem Thema werden zwei verschiedene Möglichkeiten gezeigt, um eine Abfrage zu erstellen, die Quelldaten in Gruppen sortiert und anschließend eine Unterabfrage für jede einzelne Gruppe ausführt.</span><span class="sxs-lookup"><span data-stu-id="ba309-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="ba309-106">Die grundlegende Technik in jedem Beispiel besteht darin, die Quellelemente mithilfe einer *Fortsetzung* namens `newGroup` zu gruppieren und anschließend eine neue Unterabfrage für `newGroup` zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="ba309-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="ba309-107">Diese Unterabfrage wird für jede neue Gruppe ausgeführt, die von der äußeren Abfrage erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba309-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="ba309-108">Beachten Sie, dass in diesem speziellen Beispiel die endgültige Ausgabe keine Gruppe ist, sondern eine flache Sequenz von anonymen Typen.</span><span class="sxs-lookup"><span data-stu-id="ba309-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="ba309-109">Weitere Informationen zum Gruppieren finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ba309-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="ba309-110">Weitere Informationen zu Fortsetzungen finden Sie unter [into](../language-reference/keywords/into.md).</span><span class="sxs-lookup"><span data-stu-id="ba309-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="ba309-111">Im folgenden Beispiel wird eine Datenstruktur im Arbeitsspeicher als Datenquelle verwendet, jedoch gelten für jede Art von LINQ-Datenquelle die gleichen Prinzipien.</span><span class="sxs-lookup"><span data-stu-id="ba309-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba309-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba309-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="ba309-113">In diesem Beispiel sind Verweise auf Objekte enthalten, die im Beispielcode in [Abfragen einer Auflistung von Objekten](query-a-collection-of-objects.md) definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba309-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 <span data-ttu-id="ba309-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ba309-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span></span>  
   
## <a name="see-also"></a><span data-ttu-id="ba309-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba309-115">See also</span></span>  
 [<span data-ttu-id="ba309-116">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="ba309-116">LINQ Query Expressions</span></span>](index.md)

