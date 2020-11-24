---
title: 'Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 67863346046b0c400529b87355c11f97d0c3f01f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827086"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="f66b2-102">Vorgehensweise: Erstellen und Ausführen einer einfachen PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="f66b2-102">How to: Create and Execute a Simple PLINQ Query</span></span>

<span data-ttu-id="f66b2-103">Das Beispiel in diesem Artikel zeigt, wie Sie eine einfache Parallel LINQ-Abfrage (Language Integrated Query) erstellen, indem Sie die <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType>-Erweiterungsmethode in der Quellsequenz verwenden und die Abfrage mit der <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType>-Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="f66b2-103">The example in this article shows how to create a simple Parallel Language Integrated Query (LINQ) query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> extension method on the source sequence and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f66b2-104">In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert.</span><span class="sxs-lookup"><span data-stu-id="f66b2-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="f66b2-105">Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="f66b2-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f66b2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f66b2-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="f66b2-107">Dieses Beispiel zeigt das grundlegende Muster zum Erstellen und Ausführen einer beliebigen Parallel LINQ-Abfrage, wenn die Sortierung der Ergebnissequenz nicht wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="f66b2-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important.</span></span> <span data-ttu-id="f66b2-108">Unsortierte Abfragen sind im Allgemeinen schneller als sortierte Abfragen.</span><span class="sxs-lookup"><span data-stu-id="f66b2-108">Unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="f66b2-109">Die Abfrage partitioniert die Quelle in Aufgaben, die asynchron in mehreren Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f66b2-109">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="f66b2-110">Die Reihenfolge, in der jede Aufgabe abgeschlossen wird, hängt nicht nur von der Menge der mit der Verarbeitung der Elemente in der Partition verbundenen Arbeit, sondern auch von externen Faktoren ab, beispielsweise wie das Betriebssystem jeden Thread plant.</span><span class="sxs-lookup"><span data-stu-id="f66b2-110">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="f66b2-111">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="f66b2-111">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="f66b2-112">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="f66b2-112">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="f66b2-113">Weitere Informationen zur Beibehaltung der Sortierung von Elementen in einer Abfrage finden Sie unter [Vorgehensweise: Steuern der Reihenfolge in einer PLINQ-Abfrage](how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="f66b2-113">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f66b2-114">See also</span></span>

- [<span data-ttu-id="f66b2-115">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="f66b2-115">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
