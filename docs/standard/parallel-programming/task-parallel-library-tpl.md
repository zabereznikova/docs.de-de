---
title: Task Parallel Library (TPL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
caps.latest.revision: 37
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8f63237e139e4be1d8cbb13e1534c894626fd72d
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="task-parallel-library-tpl"></a>Task Parallel Library (TPL)
Die Task Parallel Library (TPL) ist ein Satz von öffentlichen Typen und APIs im <xref:System.Threading?displayProperty=nameWithType>- und <xref:System.Threading.Tasks?displayProperty=nameWithType>-Namespace. Der Zweck der TPL ist es, die Produktivität der Entwickler zu erhöhen, indem das Hinzufügen von Parallelität und Nebenläufigkeit zu Anwendungen vereinfacht wird. Die TPL skaliert den Grad der Nebenläufigkeit dynamisch, um alle verfügbaren Prozessoren möglichst effizient zu nutzen. Außerdem behandelt die TPL die Partitionierung der Arbeit, die Planung von Threads im <xref:System.Threading.ThreadPool>, die Abbruchunterstützung, die Zustandsverwaltung und andere Details auf niedriger Ebene. Mithilfe der TPL können Sie die Leistung des Codes optimieren und sich auf die Arbeit konzentrieren, für die das Programm konzipiert wurde.  
  
 Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ist die TPL die bevorzugte Methode zum Schreiben von Multithreadcode und parallelem Code. Es eignet sich jedoch nicht jeder Code für die Parallelisierung. Wenn eine Schleife z. B. nur einen kleinen Teil der Arbeit in jeder Iteration ausführt oder für viele Iterationen nicht ausgeführt wird, kann der durch die Parallelisierung verursachte Mehraufwand die Ausführung des Codes verlangsamen. Zudem erhöht die Parallelisierung wie anderer Multithreadcode die Komplexität der Programmausführung. Die TPL vereinfacht zwar Multithreadszenarien, Sie sollten jedoch Grundkenntnisse über Threadingkonzepte haben, z. B. Sperren, Deadlocks und Racebedingungen, damit Sie die TPL effektiv verwenden können.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|description|  
|-|-|  
|[Datenparallelität](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|Beschreibt die Erstellung paralleler `for`- und `foreach`-Schleifen (`For` und `For Each` in Visual Basic).|  
|[Aufgabenbasierte asynchrone Programmierung](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|Beschreibt, wie Sie Aufgaben implizit mit <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> oder explizit mit <xref:System.Threading.Tasks.Task>-Objekten erstellen und ausführen.|  
|[Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|Beschreibt, wie die Datenflusskomponenten in der TPL-Datenflussbibliothek zu verwenden sind, um mehrere Vorgänge zu behandeln, die miteinander kommunizieren müssen, oder um Daten zu verarbeiten, sobald sie verfügbar sind.|  
|[Verwenden von TPL mit anderen asynchronen Mustern](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|Beschreibt die Verwendung der TPL mit anderen asynchronen Mustern in .NET.|  
|[Potenzielle Fehler bei Daten- und Aufgabenparallelität](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|Beschreibt einige allgemeine Fehler und Umgehungsstrategien.|  
|[Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Beschreibt das Herstellen von Datenparallelität mit LINQ-Abfragen.|  
|[Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)|Der Knoten auf oberster Ebene für die parallele .NET-Programmierung.|  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele für die parallele Programmierung mit .NET Framework](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
