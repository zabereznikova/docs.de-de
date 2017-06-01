---
title: "How to: Measure PLINQ Query Performance | Microsoft Docs"
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
  - "PLINQ queries, how to measure performance"
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Measure PLINQ Query Performance
Dieses Beispiel zeigt, wie Sie mithilfe der <xref:System.Diagnostics.Stopwatch>\-Klasse messen, wie viel Zeit für die Ausführung einer PLINQ\-Abfrage benötigt wird.  
  
## Beispiel  
 In diesem Beispiel wird eine leere `foreach`\-Schleife \(`For Each` in Visual Basic\) verwendet, um die für die Ausführung der Abfrage erforderliche Zeit zu messen.  In realem Code enthält die Schleife normalerweise weitere Verarbeitungsschritte, die die insgesamt für die Abfrageausführung benötigte Zeit erhöhen.  Beachten Sie, dass die Stoppuhr erst kurz vor der Schleife gestartet wird, wenn die Abfrageausführung beginnt.  Wenn Sie eine differenziertere Messung benötigen, können Sie die `ElapsedTicks`\-Eigenschaft anstelle von `ElapsedMilliseconds` verwenden.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 Die Gesamtausführungszeit ist eine wichtige Messgröße beim Test von Abfrageimplementierungen, sie vermittelt doch nicht immer ein Gesamtbild.  Verwenden Sie die Parallelitätsschnellansicht, um eine genauere und umfangreichere Darstellung von der Interaktion der Abfragethreads untereinander und mit anderen laufenden Prozessen zu erhalten.  Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](../Topic/Concurrency%20Visualizer.md).  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)