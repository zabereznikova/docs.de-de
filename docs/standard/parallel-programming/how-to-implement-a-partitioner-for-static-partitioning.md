---
title: "How to: Implement a Partitioner for Static Partitioning | Microsoft Docs"
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
  - "tasks, how to create a static partitioner"
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Implement a Partitioner for Static Partitioning
Im folgenden Beispiel wird eine Möglichkeit gezeigt, einen einfachen benutzerdefinierten Partitionierer für PLINQ zu implementieren, der statische Partitionierung ausführt.  Da der Partitionierer keine dynamischen Partitionen unterstützt, kann er von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> nicht verwendet werden.  Mit diesem speziellen Partitionierer können im Vergleich zum standardmäßigen Bereichspartitionierer für Datenquellen, bei dem für jedes Element eine zunehmende Berarbeitungsdauer fällig wird, Geschwindigkeitsvorteile erzielt werden.  
  
## Beispiel  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Die Partitionen in diesem Beispiel basieren auf der Annahme einer linearen Zunahme der Bearbeitungszeit für jedes Element.  In Wirklichkeit ist es möglicherweise schwierig, Bearbeitungszeiten auf diese Weise vorherzusagen.  Wenn Sie einen statischen Partitionierer mit einer bestimmten Datenquelle verwenden, können Sie die Partitionierungsformel für die Quelle optimieren, Lastenausgleichslogik hinzufügen oder eine Blockpartitionierungsmethode verwenden \(siehe [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)\).  
  
## Siehe auch  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)