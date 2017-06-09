---
title: "How to: Implement Dynamic Partitions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, how to create a dynamic partitioner"
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Implement Dynamic Partitions
Im folgenden Beispiel wird gezeigt, wie ein benutzerdefiniertes <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>\-Objekt, das dynamische Partitionierung implementiert und von bestimmten Überladungen \(<xref:System.Threading.Tasks.Parallel.ForEach%2A>\) und von PLINQ verwendet werden kann, implementiert wird.  
  
## Beispiel  
 Bei jedem Aufruf von <xref:System.Collections.IEnumerator.MoveNext%2A> auf dem Enumerator stellt der Enumerator die Partition mit einem Listenelement bereit.  Im Fall von PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> ist die Partition eine <xref:System.Threading.Tasks.Task>\-Instanz.  Da Anforderungen gleichzeitig auf mehreren Threads gestellt werden, wird der Zugriff auf den aktuellen Index synchronisiert.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Dies ist ein Beispiel für Blockpartitionierung, wobei jeder Block aus einem Element besteht.  Sie können den Konflikt hinsichtlich der Sperre verringern und theoretisch eine Leistungsverbesserung erzielen, indem Sie jeweils mehr Elemente bereitstellen.  An einem bestimmten Punkt erfordern größere Blöcke jedoch möglicherweise zusätzliche Lastenausgleichslogik, um alle Threads bis zum Abschluss der gesamten Arbeit auszulasten.  
  
## Siehe auch  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)