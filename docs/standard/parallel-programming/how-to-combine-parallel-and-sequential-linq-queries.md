---
title: "How to: Combine Parallel and Sequential LINQ Queries | Microsoft Docs"
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
  - "parallel queries, combine parallel and sequential"
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Combine Parallel and Sequential LINQ Queries
In diesem Beispiel wird gezeigt, wie Sie mithilfe der <xref:System.Linq.ParallelEnumerable.AsSequential%2A>\-Methode PLINQ anweisen, alle nachfolgenden Operatoren in der Abfrage sequenziell zu verarbeiten.  Die sequenzielle Verarbeitung ist im Allgemeinen zwar langsamer als die parallele Verarbeitung, manchmal ist dies jedoch notwendig, um korrekte Ergebnisse zu erhalten.  
  
> [!WARNING]
>  Dieses Beispiel soll die Verwendung veranschaulichen, und es wird möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein Szenario gezeigt, in dem <xref:System.Linq.ParallelEnumerable.AsSequential%2A> erforderlich ist, um die Reihenfolge beizubehalten, die in einer vorherigen Klausel der Abfrage festgelegt wurde.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## Kompilieren des Codes  
 Um diesen Code zu kompilieren und auszuführen, fügen Sie ihn in das [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md)\-Projekt ein, fügen Sie eine Zeile zum Aufrufen der Methode in `Main` hinzu, und drücken Sie F5.  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)