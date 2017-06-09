---
title: "How to: Control Ordering in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to control ordering"
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Control Ordering in a PLINQ Query
In diesen Beispielen wird gezeigt, wie Sie die Sortierung in einer PLINQ\-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>\-Erweiterungsmethode steuern.  
  
> [!WARNING]
>  Diese Beispiele sollen in erster Linie die Verwendung veranschaulichen, und sie werden eventuell nicht schneller als die entsprechenden sequenziellen LINQ to Objects\-Abfragen ausgeführt.  
  
## Beispiel  
 Im folgenden Beispiel wird die Reihenfolge der Quellsequenz beibehalten.  Dies ist in bestimmten Fällen notwendig. Einige Abfrageoperatoren erfordern beispielsweise eine geordnete Quellsequenz, um korrekte Ergebnisse zu liefern.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## Beispiel  
 Im folgenden Beispiel werden einige Abfrageoperatoren dargestellt, bei denen mit großer Wahrscheinlichkeit eine geordnete Quellsequenz erwartet wird.  Diese Operatoren können zwar auch für ungeordnete Sequenzen verwendet werden, sie haben dort jedoch ggf. unerwartete Ergebnisse zur Folge.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Fügen Sie diese Methode in die PLINQDataSample\-Klasse des Projekts [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) ein, und drücken Sie F5, um sie auszuführen.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie die Reihenfolge für den ersten Teil einer Abfrage beibehalten, die Sortierung anschließend entfernen, um die Leistung einer Join\-Klausel zu erhöhen, und dann die Endergebnissequenz erneut sortieren.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Fügen Sie diese Methode in die PLINQDataSample\-Klasse des Projekts [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) ein, und drücken Sie F5, um sie auszuführen.  
  
## Siehe auch  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)