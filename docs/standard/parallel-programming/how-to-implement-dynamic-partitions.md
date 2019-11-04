---
title: 'Vorgehensweise: Implementieren von dynamischen Partitionen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 3970566b4e3f51ce538c328d4e69b20ec22ec09b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091419"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="43ca9-102">Vorgehensweise: Implementieren von dynamischen Partitionen</span><span class="sxs-lookup"><span data-stu-id="43ca9-102">How to: Implement Dynamic Partitions</span></span>

<span data-ttu-id="43ca9-103">Im folgenden Beispiel wird das Implementieren eines benutzerdefinierten <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> gezeigt, der dynamische Partitionierung implementiert und von bestimmten <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Überladungen und PLINQ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="43ca9-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43ca9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43ca9-104">Example</span></span>

<span data-ttu-id="43ca9-105">Jedes Mal, wenn eine Partition <xref:System.Collections.IEnumerator.MoveNext%2A> auf dem Enumerator aufruft, stellt der Enumerator die Partition mit einem Listenelement bereit.</span><span class="sxs-lookup"><span data-stu-id="43ca9-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="43ca9-106">Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> ist die Partition eine <xref:System.Threading.Tasks.Task>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="43ca9-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="43ca9-107">Da Anforderungen gleichzeitig in mehreren Threads auftreten, wird der Zugriff auf den aktuellen Index synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="43ca9-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

<span data-ttu-id="43ca9-108">Dies ist ein Beispiel der Blockpartitionierung, wobei jeder Block aus einem Element besteht.</span><span class="sxs-lookup"><span data-stu-id="43ca9-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="43ca9-109">Durch gleichzeitige Bereitstellung weiterer Elemente könnten Sie den Konflikt über die Sperre minimieren und theoretisch eine schnellere Leistung erzielen.</span><span class="sxs-lookup"><span data-stu-id="43ca9-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="43ca9-110">Allerdings könnten größere Blöcke ab einem gewissen Punkt zusätzliche Lastenausgleichslogik benötigen, um alle Threads in Betrieb zu halten, bis die gesamte Arbeit abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="43ca9-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ca9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43ca9-111">See also</span></span>

* [<span data-ttu-id="43ca9-112">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="43ca9-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
* [<span data-ttu-id="43ca9-113">Vorgehensweise: Implementieren eines Partitionierers für statisches Partitionieren</span><span class="sxs-lookup"><span data-stu-id="43ca9-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
