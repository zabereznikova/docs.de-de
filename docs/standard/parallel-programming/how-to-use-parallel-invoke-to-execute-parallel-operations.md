---
title: "How to: Use Parallel.Invoke to Execute Parallel Operations | Microsoft Docs"
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
  - "task parallelism in .NET"
  - "parallel programming, task parallelism"
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# How to: Use Parallel.Invoke to Execute Parallel Operations
In diesem Beispiel wird veranschaulicht, wie Vorgänge parallelisiert werden können, indem <xref:System.Threading.Tasks.Parallel.Invoke%2A> in der Task Parallel Library verwendet wird.  Es werden drei Vorgänge für eine freigegebene Datenquelle ausgeführt.  Da die Quelle durch keinen der Vorgänge geändert wird, können diese auf einfache Weise parallel ausgeführt werden.  
  
> [!NOTE]
>  Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambda\-Ausdrücken.  Falls Sie mit der Verwendung von Lambda\-Ausdrücken in C\# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Beispiel  
 [!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
 [!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]  
  
 Beachten Sie, dass Sie mit <xref:System.Threading.Tasks.Parallel.Invoke%2A> nur angeben, welche Aktionen gleichzeitig ausgeführt werden sollen. Alle Details der Threadplanung, einschließlich automatischem Skalieren entsprechend der Anzahl von Kernen auf dem Hostcomputer, werden von der Common Language Runtime verwaltet.  
  
 In diesem Beispiel werden die Vorgänge, nicht die Daten parallelisiert.  Eine alternative Vorgehensweise besteht darin, die LINQ\-Abfragen mithilfe von PLINQ zu parallelisieren und die Abfragen sequenziell auszuführen.  Sie könnten die Daten aber auch parallelisieren, indem Sie PLINQ verwenden.  Eine weitere Möglichkeit ist, sowohl die Abfragen als auch die Aufgaben zu parallelisieren.  Durch den resultierenden Mehraufwand kann zwar die Leistung auf Hostcomputern mit relativ wenigen Prozessoren beeinträchtigt werden, die Skalierung auf Computern mit vielen Prozessoren ist jedoch deutlich besser.  
  
## Kompilieren des Codes  
  
-   Kopieren Sie das gesamte Beispiel, fügen Sie es in ein Microsoft Visual Studio 2010\-Projekt ein, und drücken Sie F5.  
  
## Siehe auch  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [How to: Wait on One or More Tasks to Complete](../Topic/How%20to:%20Wait%20on%20One%20or%20More%20Tasks%20to%20Complete.md)   
 [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)