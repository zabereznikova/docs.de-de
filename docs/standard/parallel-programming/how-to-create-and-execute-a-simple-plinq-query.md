---
title: 'Gewusst wie: Erstellen und Ausführen einer einfachen PLINQ-Abfrage'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 349cc8d78e9a080d720e09a7e3e5e314752605c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106959"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="23ddb-102">Gewusst wie: Erstellen und Ausführen einer einfachen PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="23ddb-102">How to: Create and Execute a Simple PLINQ Query</span></span>
<span data-ttu-id="23ddb-103">Das folgende Beispiel zeigt, wie Sie eine einfache Parallel LINQ-Abfrage erstellen, indem Sie die <xref:System.Linq.ParallelEnumerable.AsParallel%2A>-Erweiterungsmethode in der Quellsequenz verwenden und die Abfrage mit der <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="23ddb-103">The following example shows how to create a simple Parallel LINQ query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A> extension method on the source sequence, and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23ddb-104">In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert.</span><span class="sxs-lookup"><span data-stu-id="23ddb-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="23ddb-105">Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="23ddb-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23ddb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23ddb-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="23ddb-107">Dieses Beispiel zeigt das grundlegende Muster zum Erstellen und Ausführen einer beliebigen Parallel LINQ-Abfrage, wenn die Sortierung der Ergebnissequenz nicht wichtig ist. Unsortierte Abfragen sind im Allgemeinen schneller als sortierte Abfragen.</span><span class="sxs-lookup"><span data-stu-id="23ddb-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important; unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="23ddb-108">Die Abfrage partitioniert die Quelle in Aufgaben, die asynchron in mehreren Threads ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23ddb-108">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="23ddb-109">Die Reihenfolge, in der jede Aufgabe abgeschlossen wird, hängt nicht nur von der Menge der mit der Verarbeitung der Elemente in der Partition verbundenen Arbeit, sondern auch von externen Faktoren ab, beispielsweise wie das Betriebssystem jeden Thread plant.</span><span class="sxs-lookup"><span data-stu-id="23ddb-109">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="23ddb-110">Dieses Beispiel soll die Nutzung darstellen und wird möglicherweise nicht schneller ausgeführt als die entsprechende sequenzielle LINQ to Objects-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="23ddb-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="23ddb-111">Weitere Informationen finden Sie unter [Grundlagen zur Beschleunigung in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="23ddb-111">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="23ddb-112">Weitere Informationen zur Beibehaltung der Sortierung von Elementen in einer Abfrage finden Sie unter [Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span><span class="sxs-lookup"><span data-stu-id="23ddb-112">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ddb-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23ddb-113">See also</span></span>

- [<span data-ttu-id="23ddb-114">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="23ddb-114">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
