---
title: Task Parallel Library (TPL)
description: Erkunden Sie die Task Parallel Library (TPL), eine Sammlung von öffentlichen Typen und APIs zum Vereinfachen des Hinzufügungsprozesses für Parallelität und Nebenläufigkeit zu Anwendungen in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 596671b267484561a8697546caa5a4764242ebd3
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925232"
---
# <a name="task-parallel-library-tpl"></a>Task Parallel Library (TPL)

Die Task Parallel Library (TPL) ist ein Satz von öffentlichen Typen und APIs im <xref:System.Threading?displayProperty=nameWithType>- und <xref:System.Threading.Tasks?displayProperty=nameWithType>-Namespace. Der Zweck der TPL ist es, die Produktivität der Entwickler zu erhöhen, indem das Hinzufügen von Parallelität und Nebenläufigkeit zu Anwendungen vereinfacht wird. Die TPL skaliert den Grad der Nebenläufigkeit dynamisch, um alle verfügbaren Prozessoren möglichst effizient zu nutzen. Außerdem behandelt die TPL die Partitionierung der Arbeit, die Planung von Threads im <xref:System.Threading.ThreadPool>, die Abbruchunterstützung, die Zustandsverwaltung und andere Details auf niedriger Ebene. Mithilfe der TPL können Sie die Leistung des Codes optimieren und sich auf die Arbeit konzentrieren, für die das Programm konzipiert wurde.  
  
 Ab .NET Framework 4 ist die TPL die bevorzugte Methode zum Schreiben von Multithreadcode und parallelem Code. Allerdings eignet sich nicht jeder Code für die Parallelisierung. Wenn eine Schleife z. B. nur einen kleinen Teil der Arbeit in jeder Iteration ausführt oder für viele Iterationen nicht ausgeführt wird, kann der durch die Parallelisierung verursachte Mehraufwand die Ausführung des Codes verlangsamen. Zudem erhöht die Parallelisierung wie anderer Multithreadcode die Komplexität der Programmausführung. Die TPL vereinfacht zwar Multithreadszenarien, Sie sollten jedoch Grundkenntnisse über Threadingkonzepte haben, z. B. Sperren, Deadlocks und Racebedingungen, damit Sie die TPL effektiv verwenden können.  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|Titel|Beschreibung|  
|-|-|  
|[Datenparallelität](data-parallelism-task-parallel-library.md)|Beschreibt die Erstellung paralleler `for`- und `foreach`-Schleifen (`For` und `For Each` in Visual Basic).|  
|[Aufgabenbasierte asynchrone Programmierung](task-based-asynchronous-programming.md)|Beschreibt, wie Sie Aufgaben implizit mit <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> oder explizit mit <xref:System.Threading.Tasks.Task>-Objekten erstellen und ausführen.|  
|[Dataflow (Datenfluss)](dataflow-task-parallel-library.md)|Beschreibt, wie die Datenflusskomponenten in der TPL-Datenflussbibliothek zu verwenden sind, um mehrere Vorgänge zu behandeln, die miteinander kommunizieren müssen, oder um Daten zu verarbeiten, sobald sie verfügbar sind.|
|[Potenzielle Fehler bei Daten- und Aufgabenparallelität](potential-pitfalls-in-data-and-task-parallelism.md)|Beschreibt einige allgemeine Fehler und Umgehungsstrategien.|  
|[Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)|Beschreibt das Herstellen von Datenparallelität mit LINQ-Abfragen.|  
|[Parallele Programmierung](index.md)|Der Knoten auf oberster Ebene für die parallele .NET-Programmierung.|  
  
## <a name="see-also"></a>Siehe auch

- [Beispiele für die parallele Programmierung mit .NET Core und .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
