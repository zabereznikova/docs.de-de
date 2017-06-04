---
title: "How to: Write a Custom PLINQ Aggregate Function | Microsoft Docs"
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
  - "PLINQ queries, how to create aggregate function"
ms.assetid: 5a70dd49-ab2a-4798-b551-196ee7042b1a
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Write a Custom PLINQ Aggregate Function
In diesem Beispiel wird gezeigt, wie Sie mit der <xref:System.Linq.ParallelEnumerable.Aggregate%2A>\-Methode eine benutzerdefinierte Aggregatfunktion auf eine Quellsequenz anwenden.  
  
> [!WARNING]
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 Im folgenden Beispiel wird die Standardabweichung einer Sequenz von Ganzzahlen berechnet.  
  
 [!code-csharp[PLINQ#31](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#31)]
 [!code-vb[PLINQ#31](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#31)]  
  
 Dieses Beispiel verwendet eine Überladung des standardmäßigen Aggregatabfrageoperators, die für PLINQ eindeutig ist.  Diese Überladung unterstützt eine zusätzliche <xref:System.Func%603?displayProperty=fullName> als dritten Eingabeparameter.  Der Delegat kombiniert die Ergebnisse aus allen Threads, bevor die abschließende Berechnung der aggregierten Ergebnissen durchgeführt wird.  In diesem Beispiel werden die Summen aus allen Threads addiert.  
  
 Wenn der Textkörper eines Lambda\-Ausdrucks aus einem einzelnen Ausdruck besteht, entspricht der Rückgabewert des <xref:System.Func%602?displayProperty=fullName>\-Delegaten dem Wert des Ausdrucks.  
  
## Siehe auch  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)