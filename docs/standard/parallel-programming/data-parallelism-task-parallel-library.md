---
title: "Data Parallelism (Task Parallel Library) | Microsoft Docs"
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
  - "parallelism, data"
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
caps.latest.revision: 25
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 25
---
# Data Parallelism (Task Parallel Library)
*Datenparallelismus* verweist auf Szenarien, in denen der gleiche Vorgang gleichzeitig \(d. h. parallel\) für Elemente in einer Quellauflistung oder einem Array ausgeführt wird.  In parallelen Datenvorgängen wird die Quellauflistung partitioniert, sodass mehrere Threads gleichzeitig auf verschiedene Segmente angewendet werden können.  
  
 Die Task Parallel Library \(TPL\) unterstützt Datenparallelität durch die <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>\-Klasse.  Diese Klasse stellt methodenbasierte parallele Implementierungen von [for](../Topic/for%20\(C%23%20Reference\).md)\-Schleifen und [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md)\-Schleifen bereit \(`For`  und `For Each` in Visual Basic\).  Sie schreiben die Schleifenlogik für eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Schleife oder <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Schleife weitgehend auf die gleiche Weise wie eine sequenzielle Schleife.  Sie müssen keine Threads erstellen oder Arbeitsaufgaben in die Warteschlange einreihen.  In grundlegenden Schleifen sind keine Sperren erforderlich.  Die TPL übernimmt alle Arbeiten auf niedriger Ebene für Sie.  Um ausführliche Informationen zu der Verwendung von <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> zu erhalten, laden Sie das Dokument [Muster für parallele Programmierung: Verstehen und Anwenden paralleler Muster mit .NET Framework 4](http://www.microsoft.com/download/details.aspx?id=19222) herunter.  Im folgenden Codebeispiel werden eine einfache `foreach`\-Schleife und deren parallele Entsprechung dargestellt.  
  
> [!NOTE]
>  Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambda\-Ausdrücken.  Falls Sie mit der Verwendung von Lambda\-Ausdrücken in C\# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 Wenn eine parallele Schleife ausgeführt wird, partitioniert die TPL die Datenquelle, sodass die Schleife mehrere Teile gleichzeitig bearbeiten kann.  Im Hintergrund partitioniert der Taskplaner die Aufgabe basierend auf den Systemressourcen und der Arbeitsauslastung.  Nach Möglichkeit verteilt der Planer die Arbeit auf mehrere Threads und Prozessoren, wenn die Arbeitsauslastung unausgewogen ist.  
  
> [!NOTE]
>  Sie können auch einen eigenen, benutzerdefinierten Partitionierer oder Planer angeben.  Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) sowie unter [Task Schedulers](../Topic/Task%20Schedulers.md).  
  
 Sowohl die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Methode als auch die <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Methode verfügen über mehrere Überladungen, die es Ihnen ermöglichen, die Schleifenausführung anzuhalten bzw. zu unterbrechen, den Zustand der Schleife in anderen Threads zu überwachen, den lokalen Threadzustand beizubehalten, lokale Threadobjekte abzuschließen, den Grad der Parallelität zu steuern usw.  Zu den Hilfstypen, die diese Funktionalität ermöglichen, zählen <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions> und <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> und <xref:System.Threading.CancellationTokenSource>.  
  
 Weitere Informationen finden Sie unter [Muster für parallele Programmierung](http://go.microsoft.com/fwlink/p/?LinkId=265491).  
  
 Datenparallelismus mit deklarativer oder abfrageähnlicher Syntax wird von PLINQ unterstützt.  Weitere Informationen finden Sie unter [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.For%2A>\-Schleife über jedes Array oder indizierbare <xref:System.Collections.Generic.IEnumerable%601>\-Quellauflistung geschrieben wird.|  
|[How to: Write a Simple Parallel.ForEach Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife über jede <xref:System.Collections.Generic.IEnumerable%601>\-Quellauflistung geschrieben wird.|  
|[How to: Stop or Break from a Parallel.For Loop](http://msdn.microsoft.com/de-de/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)|Beschreibt, wie eine parallele Schleife beendet oder unterbrochen wird, damit alle Threads von der Aktion informiert werden.|  
|[How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.For%2A>\-Schleife geschrieben wird, in der jeder Thread eine private Variable beibehält, die für alle anderen Threads nicht sichtbar ist, und wie die Ergebnisse von allen Threads synchronisiert werden, wenn die Schleife abgeschlossen wird.|  
|[How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife geschrieben wird, in der jeder Thread eine private Variable beibehält, die für alle anderen Threads nicht sichtbar ist, und wie die Ergebnisse von allen Threads synchronisiert werden, wenn die Schleife abgeschlossen wird.|  
|[How to: Cancel a Parallel.For or ForEach Loop](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|Beschreibt, wie eine parallele Schleife mit einem <xref:System.Threading.CancellationToken?displayProperty=fullName>\-Objekt abgebrochen wird|  
|[How to: Speed Up Small Loop Bodies](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|Beschreibt eine Möglichkeit zur Beschleunigung der Ausführung, wenn ein Schleifenkörper sehr klein ist.|  
|[Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Übersicht über die Task Parallel Library.|  
|[Parallel Programming](../../../docs/standard/parallel-programming/index.md)|Einführung in parallele Programmierung in .NET Framework|  
  
## Siehe auch  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)