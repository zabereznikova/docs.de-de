---
title: "How to: Specify the Execution Mode in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use execution mode"
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Specify the Execution Mode in PLINQ
In diesem Beispiel wird gezeigt, wie Sie PLINQ anweisen, die Standardheuristik zu übergehen und eine Abfrage unabhängig von deren Form zu parallelisieren.  
  
> [!WARNING]
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ wurde speziell auf die Nutzung von Parallelisierungsmöglichkeiten ausgelegt.  Nicht alle Abfragen profitieren jedoch von einer parallelen Ausführung.  Wenn eine Abfrage beispielsweise nur einen Benutzerdelegaten enthält, der relativ wenige Aufgaben ausführt, wird die Abfrage normalerweise im sequenziellen Modus schneller ausgeführt.  Dies ist darauf zurückzuführen, dass der Mehraufwand für die Aktivierung der parallelen Ausführung größer ist als die erzielten Geschwindigkeitsvorteile.  Aus diesem Grund parallelisiert PLINQ nicht automatisch alle Abfragen.  Zunächst werden die Form der Abfrage und die zahlreichen Operatoren, aus denen diese besteht, untersucht.  Anhand dieser Analyse entscheidet sich PLINQ im Standardausführungsmodus möglicherweise, eine Abfrage ganz oder teilweise sequenziell auszuführen.  In bestimmten Fällen kann es vorkommen, dass Ihnen mehr Informationen zu einer Abfrage vorliegen, als PLINQ in der Analyse ermitteln kann.  Sie wissen beispielsweise, dass ein Delegat besonders aufwändig ist und dass die Abfrage definitiv von einer Parallelisierung profitiert wird.  In solchen Fällen können Sie die <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>\-Methode verwenden und den <xref:System.Linq.ParallelExecutionMode>\-Wert angeben, um PLINQ anzuweisen, dass die Abfrage stets parallel ausgeführt werden soll.  
  
## Kompilieren des Codes  
 Schneiden Sie diesen Code aus, fügen Sie ihn in [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) ein, und rufen Sie die Methode von `Main` aus auf.  
  
## Siehe auch  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)