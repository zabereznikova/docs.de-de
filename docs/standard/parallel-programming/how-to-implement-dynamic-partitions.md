---
title: 'Gewusst wie: Implementieren von dynamischen Partitionen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="0b732-102">Gewusst wie: Implementieren von dynamischen Partitionen</span><span class="sxs-lookup"><span data-stu-id="0b732-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="0b732-103">Im folgende Beispiel wird gezeigt, wie implementieren eine benutzerdefinierten <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , dynamische Partitionierung implementiert und können verwendet werden, von bestimmten Überladungen <xref:System.Threading.Tasks.Parallel.ForEach%2A> und PLINQ.</span><span class="sxs-lookup"><span data-stu-id="0b732-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b732-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b732-104">Example</span></span>  
 <span data-ttu-id="0b732-105">Jedes Mal eine Partition ruft <xref:System.Collections.IEnumerator.MoveNext%2A> für den Enumerator stellt der Enumerator die Partition mit einem Listenelement bereit.</span><span class="sxs-lookup"><span data-stu-id="0b732-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="0b732-106">Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A>, die Partition ist ein <xref:System.Threading.Tasks.Task> Instanz.</span><span class="sxs-lookup"><span data-stu-id="0b732-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="0b732-107">Da Anforderungen gleichzeitig in mehreren Threads auftreten, wird der Zugriff auf den aktuellen Index synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0b732-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="0b732-108">Dies ist ein Beispiel eines Blocks Partitionierung, wobei jeder Block mit einem Element.</span><span class="sxs-lookup"><span data-stu-id="0b732-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="0b732-109">Sie könnten durch weitere Elemente bereitstellt, die zu einem Zeitpunkt, die Konflikte minimieren, über die Sperre und theoretisch eine schnellere Leistung erzielen.</span><span class="sxs-lookup"><span data-stu-id="0b732-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="0b732-110">Allerdings möglicherweise zu einem späteren Zeitpunkt größere Blöcken zusätzliche Logik mit Lastenausgleich benötigen, um alle Threads beschäftigt halten, bis die gesamte Arbeit abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="0b732-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b732-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b732-111">See Also</span></span>  
 [<span data-ttu-id="0b732-112">Benutzerdefinierte Partitionierer für PLINQ und TPL</span><span class="sxs-lookup"><span data-stu-id="0b732-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="0b732-113">Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren</span><span class="sxs-lookup"><span data-stu-id="0b732-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
