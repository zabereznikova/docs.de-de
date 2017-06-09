---
title: "How to: Cancel a Parallel.For or ForEach Loop | Microsoft Docs"
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
  - "parallel foreach loop, how to cancel"
  - "parallel for loops, how to cancel"
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Cancel a Parallel.For or ForEach Loop
Die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Methode und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Methode unterstützen einen Abbruch durch die Verwendung von Abbruchtoken.  Weitere allgemeine Informationen zum Abbruch finden Sie unter [Abbruch](../../../docs/standard/threading/cancellation-in-managed-threads.md).  In einer parallelen Schleife geben Sie das <xref:System.Threading.CancellationToken> für die Methode im <xref:System.Threading.Tasks.ParallelOptions>\-Parameter an und schließen dann den parallelen Aufruf in einen try\/catch\-Block ein.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie einen Aufruf von <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> abbrechen.  Sie können den gleichen Ansatz auch auf einen <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Aufruf anwenden.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Wenn das Token, das den Abbruch signalisiert, das gleiche Token wie in der <xref:System.Threading.Tasks.ParallelOptions>\-Instanz ist, löst die parallele Schleife beim Abbruch eine einzelne <xref:System.OperationCanceledException> aus.  Wenn ein anderes Token einen Abbruch verursacht, löst die Schleife eine <xref:System.AggregateException> mit einer <xref:System.OperationCanceledException> als InnerException aus.  
  
## Siehe auch  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)