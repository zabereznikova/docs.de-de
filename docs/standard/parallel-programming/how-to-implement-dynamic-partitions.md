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
# <a name="how-to-implement-dynamic-partitions"></a>Gewusst wie: Implementieren von dynamischen Partitionen
Im folgende Beispiel wird gezeigt, wie implementieren eine benutzerdefinierten <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , dynamische Partitionierung implementiert und können verwendet werden, von bestimmten Überladungen <xref:System.Threading.Tasks.Parallel.ForEach%2A> und PLINQ.  
  
## <a name="example"></a>Beispiel  
 Jedes Mal eine Partition ruft <xref:System.Collections.IEnumerator.MoveNext%2A> für den Enumerator stellt der Enumerator die Partition mit einem Listenelement bereit. Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A>, die Partition ist ein <xref:System.Threading.Tasks.Task> Instanz. Da Anforderungen gleichzeitig in mehreren Threads auftreten, wird der Zugriff auf den aktuellen Index synchronisiert.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Dies ist ein Beispiel eines Blocks Partitionierung, wobei jeder Block mit einem Element. Sie könnten durch weitere Elemente bereitstellt, die zu einem Zeitpunkt, die Konflikte minimieren, über die Sperre und theoretisch eine schnellere Leistung erzielen. Allerdings möglicherweise zu einem späteren Zeitpunkt größere Blöcken zusätzliche Logik mit Lastenausgleich benötigen, um alle Threads beschäftigt halten, bis die gesamte Arbeit abgeschlossen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
