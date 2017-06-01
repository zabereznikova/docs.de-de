---
title: "How to: Speed Up Small Loop Bodies | Microsoft Docs"
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
  - "parallel loops, how to speed up"
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# How to: Speed Up Small Loop Bodies
Wenn eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Schleife nur wenig Text enthält, wird sie möglicherweise langsamer ausgeführt als die entsprechende sequenzielle Schleife, wie die [For](../Topic/for%20\(C%23%20Reference\).md)\-Schleife in C\# und die [For](http://msdn.microsoft.com/de-de/c470a263-9b49-4308-8fd6-8592b84a7980)\-Schleife in Visual Basic.  Der Leistungsverlust wird von dem Aufwand verursacht, der mit dem Partitionieren der Daten einhergeht, und von den Kosten des Aufrufs eines Delegaten bei jeder Schleifeniteration.  Für solche Szenarien stellt die <xref:System.Collections.Concurrent.Partitioner>\-Klasse die <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName>\-Methode bereit, die es Ihnen ermöglicht, eine sequenzielle Schleife für den Delegattext einzurichten, damit der Delegat nur einmal pro Partition und nicht einmal bei jeder Iteration aufgerufen wird.  Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Beispiel  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Der in diesem Beispiel gezeigte Ansatz ist hilfreich, wenn die Schleife nur eine minimale Menge an Arbeit ausführt.  Wenn die Arbeit berechnungsintensiver wird, erhalten Sie wahrscheinlich die gleiche oder eine bessere Leistung, wenn Sie eine <xref:System.Threading.Tasks.Parallel.For%2A>\- oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife in Verbindung mit dem Standardpartitionierer verwenden.  
  
## Siehe auch  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [Iteratoren](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)