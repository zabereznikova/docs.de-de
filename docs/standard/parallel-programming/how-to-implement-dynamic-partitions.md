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
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b08c387c9b10a9d6fa8728a7fce87a7894a37fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-implement-dynamic-partitions"></a>Gewusst wie: Implementieren von dynamischen Partitionen
Im folgenden Beispiel wird das Implementieren eines benutzerdefinierten <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> gezeigt, der dynamische Partitionierung implementiert und von bestimmten <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Überladungen und PLINQ verwendet werden kann.  
  
## <a name="example"></a>Beispiel  
 Jedes Mal, wenn eine Partition <xref:System.Collections.IEnumerator.MoveNext%2A> auf dem Enumerator aufruft, stellt der Enumerator die Partition mit einem Listenelement bereit. Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> ist die Partition eine <xref:System.Threading.Tasks.Task>-Instanz. Da Anforderungen gleichzeitig in mehreren Threads auftreten, wird der Zugriff auf den aktuellen Index synchronisiert.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Dies ist ein Beispiel der Blockpartitionierung, wobei jeder Block aus einem Element besteht. Durch gleichzeitige Bereitstellung weiterer Elemente könnten Sie den Konflikt über die Sperre minimieren und theoretisch eine schnellere Leistung erzielen. Allerdings könnten größere Blöcke ab einem gewissen Punkt zusätzliche Lastenausgleichslogik benötigen, um alle Threads in Betrieb zu halten, bis die gesamte Arbeit abgeschlossen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Partitionierer für PLINQ und TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
