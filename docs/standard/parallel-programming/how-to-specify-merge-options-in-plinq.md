---
title: "How to: Specify Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use merge options"
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Specify Merge Options in PLINQ
In diesem Beispiel wird gezeigt, wie Sie Zusammenführungsoptionen für alle nachfolgenden Operatoren in einer PLINQ\-Abfrage angeben.  Sie müssen Zusammenführungsoptionen nicht explizit festlegen, dies kann jedoch zu einer Leistungsverbesserung beitragen.  Weitere Informationen zu Zusammenführungsoptionen finden Sie unter [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 Im folgenden Beispiel wird das Verhalten von Zusammenführungsoptionen in einem grundlegenden Szenario gezeigt, das eine ungeordnete Quelle aufweist und eine rechenintensive Funktion auf jedes Element anwendet.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 Wenn die <xref:System.Linq.ParallelMergeOptions>\-Option unerwünschte Wartezeit verursacht, bevor das erste Element ausgegeben wird, können Sie versuchen, mit der <xref:System.Linq.ParallelMergeOptions>\-Option Ergebniselemente schneller und reibungsloser auszugeben.  
  
## Siehe auch  
 <xref:System.Linq.ParallelMergeOptions>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)