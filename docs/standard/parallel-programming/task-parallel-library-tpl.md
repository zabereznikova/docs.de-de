---
title: "Task Parallel Library (TPL) | Microsoft Docs"
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
  - ".NET, concurrency in"
  - ".NET, parallel programming in"
  - "Parallel Programming"
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
caps.latest.revision: 37
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 37
---
# Task Parallel Library (TPL)
Die Task Parallel Library \(TPL\) ist ein Satz von öffentlichen Typen und APIs im <xref:System.Threading?displayProperty=fullName>\- und <xref:System.Threading.Tasks?displayProperty=fullName>\-Namespace.  Der Zweck der TPL ist es, die Produktivität der Entwickler zu erhöhen, indem das Hinzufügen von Parallelität und Nebenläufigkeit zu Anwendungen vereinfacht wird.  Die TPL skaliert den Grad der Nebenläufigkeit dynamisch, um alle verfügbaren Prozessoren möglichst effizient zu nutzen.  Außerdem behandelt die TPL die Partitionierung der Arbeit, die Planung von Threads im <xref:System.Threading.ThreadPool>, die Abbruchunterstützung, die Zustandsverwaltung und andere Details auf niedriger Ebene.  Mithilfe der TPL können Sie die Leistung des Codes optimieren und sich auf die Arbeit konzentrieren, für die das Programm konzipiert wurde.  
  
 Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ist die TPL die bevorzugte Methode zum Schreiben von Multithreadcode und parallelem Code.  Es eignet sich jedoch nicht jeder Code für die Parallelisierung. Wenn eine Schleife z. B. nur einen kleinen Teil der Arbeit in jeder Iteration ausführt oder für viele Iterationen nicht ausgeführt wird, kann der durch die Parallelisierung verursachte Mehraufwand die Ausführung des Codes verlangsamen.  Zudem erhöht die Parallelisierung wie anderer Multithreadcode die Komplexität der Programmausführung.  Die TPL vereinfacht zwar Multithreadszenarien, Sie sollten jedoch Grundkenntnisse über Threadingkonzepte haben, z. B. Sperren, Deadlocks und Racebedingungen, damit Sie die TPL effektiv verwenden können.  
  
## Verwandte Themen  
  
|||  
|-|-|  
|Titel|Beschreibung|  
|[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|Beschreibt die Erstellung paralleler `for`\- und `foreach`\-Schleifen \(`For` und `For Each` in Visual Basic\).|  
|[Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|Beschreibt, wie Sie Aufgaben implizit mit <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=fullName> oder explizit mit <xref:System.Threading.Tasks.Task>\-Objekten erstellen und ausführen.|  
|[Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|Beschreibt, wie die Datenflusskomponenten in der TPL\-Datenflussbibliothek zu verwenden sind, um mehrere Vorgänge zu behandeln, die miteinander kommunizieren müssen, oder um Daten zu verarbeiten, sobald sie verfügbar sind.|  
|[Using TPL with Other Asynchronous Patterns](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|Beschreibt die Verwendung der TPL mit anderen asynchronen Mustern in .NET.|  
|[Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|Beschreibt einige allgemeine Fehler und Umgehungsstrategien.|  
|[Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Beschreibt das Herstellen von Datenparallelität mit LINQ\-Abfragen.|  
|[Parallel Programming](../../../docs/standard/parallel-programming/index.md)|Der Knoten auf oberster Ebene für die parallele .NET\-Programmierung.|  
  
## Siehe auch  
 [Samples for Parallel Programming with the .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)