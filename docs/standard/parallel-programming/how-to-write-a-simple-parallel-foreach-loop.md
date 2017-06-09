---
title: "How to: Write a Simple Parallel.ForEach Loop | Microsoft Docs"
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
  - "foreach, parallel version"
  - "parallel programming, foreach"
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Write a Simple Parallel.ForEach Loop
In diesem Beispiel wird gezeigt, wie Sie mithilfe einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Schleife Datenparallelität für jede <xref:System.Collections.IEnumerable?displayProperty=fullName>\- oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>\-Datenquelle ermöglichen.  
  
> [!NOTE]
>  In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambda\-Ausdrücken definiert.  Falls Sie nicht mit der Verwendung von Lambda\-Ausdrücken in C\# oder Visual Basic vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Beispiel  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife hat die gleiche Funktion wie eine <xref:System.Threading.Tasks.Parallel.For%2A>\-Schleife.  Die Quellauflistung wird partitioniert, und die Arbeit wird basierend auf der Systemumgebung in mehreren Threads geplant.  Je mehr Prozessoren im System vorhanden sind, umso schneller wird die parallele Methode ausgeführt.  In einigen Quellauflistungen ist eine sequenzielle Schleife möglicherweise schneller. Dies ist abhängig von der Größe der Quelle und der Art von Arbeit, die ausgeführt wird.  Weitere Informationen zur Leistung finden Sie unter [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).  
  
 Weitere Informationen zu parallelen Schleifen finden Sie unter [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)  
  
 Um <xref:System.Threading.Tasks.Parallel.ForEach%2A> für eine nicht generische Auflistung zu verwenden, können Sie die Auflistung mit der <xref:System.Linq.Enumerable.Cast%2A>\-Erweiterungsmethode in eine generische Auflistung umwandeln, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Sie können auch Parallel LINQ \(PLINQ\) verwenden, um die Verarbeitung von <xref:System.Collections.Generic.IEnumerable%601>\-Datenquellen zu parallelisieren.  PLINQ ermöglicht Ihnen, mithilfe von deklarativer Abfragesyntax das Schleifenverhalten anzugeben.  Weitere Informationen finden Sie unter [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## Kompilieren des Codes  
  
-   Kopieren Sie diesen Code, und fügen Sie ihn in ein [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010\-Konsolenanwendungsprojekt ein.  
  
-   Fügen Sie einen Verweis auf "System.Design.dll" hinzu.  
  
-   Drücken von F5  
  
## Siehe auch  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)