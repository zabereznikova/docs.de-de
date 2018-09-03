---
title: Datenparallelität (Task Parallel Library)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, data
ms.assetid: 3f05f33f-f1da-4b16-81c2-9ceff1bef449
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f414e5b0463e28427c8c60e2f8b8774ad6973da2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464136"
---
# <a name="data-parallelism-task-parallel-library"></a>Datenparallelität (Task Parallel Library)
*Datenparallelismus* verweist auf Szenarios, in denen der gleiche Vorgang gleichzeitig (d.h. parallel) für Elemente in einer Quellauflistung oder einem Array ausgeführt wird. In parallelen Datenvorgängen wird die Quellauflistung partitioniert, sodass mehrere Threads gleichzeitig auf verschiedene Segmente angewendet werden können.  
  
 Die Task Parallel Library (TPL) unterstützt Datenparallelität durch die <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>-Klasse. Diese Klasse stellt methodenbasierte parallele Implementierungen von [for](~/docs/csharp/language-reference/keywords/for.md)-Schleifen und [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md)-Schleifen bereit (`For` und `For Each` in Visual Basic). Sie schreiben die Schleifenlogik für eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife oder <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife weitgehend auf die gleiche Weise wie eine sequenzielle Schleife. Sie müssen keine Threads erstellen oder Arbeitselemente in die Warteschlange einreihen. In grundlegenden Schleifen sind keine Sperren erforderlich. Die TPL übernimmt alle Arbeiten auf niedriger Ebene für Sie. Um ausführliche Informationen über die Verwendung von <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> zu erhalten, laden Sie das Dokument zum Thema [Muster für parallele Programmierung: Verstehen und Anwenden paralleler Muster mit .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=19222) herunter. Im folgenden Codebeispiel werden eine einfache `foreach`-Schleife und deren parallele Entsprechung dargestellt.  
  
> [!NOTE]
>  Diese Dokumentation definiert Delegaten in TPL mithilfe von Lambdaausdrücken. Falls Sie mit der Verwendung von Lambda-Ausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambda Expressions in PLINQ and TPL (Lambda-Ausdrücke in PLINQ und TPL)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 [!code-csharp[TPL#20](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#20)]
 [!code-vb[TPL#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#20)]  
  
 Wenn eine parallele Schleife ausgeführt wird, partitioniert die TPL die Datenquelle, sodass die Schleife mehrere Teile gleichzeitig bearbeiten kann. Im Hintergrund partitioniert der Taskplaner die Aufgabe basierend auf den Systemressourcen und der Arbeitsauslastung. Nach Möglichkeit verteilt der Planer die Arbeit auf mehrere Threads und Prozessoren, wenn die Arbeitsauslastung unausgewogen ist.  
  
> [!NOTE]
>  Sie können auch einen eigenen, benutzerdefinierten Partitionierer oder Planer angeben. Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) sowie unter [TaskScheduler](https://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65).  
  
 Sowohl die <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Methode als auch die <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode verfügen über mehrere Überladungen, die es Ihnen ermöglichen, die Schleifenausführung anzuhalten bzw. zu unterbrechen, den Zustand der Schleife in anderen Threads zu überwachen, den lokalen Threadzustand beizubehalten, lokale Threadobjekte abzuschließen, den Grad der Parallelität zu steuern usw. Zu den Hilfstypen, die diese Funktionalität ermöglichen, zählen <xref:System.Threading.Tasks.ParallelLoopState>, <xref:System.Threading.Tasks.ParallelOptions> und <xref:System.Threading.Tasks.ParallelLoopResult>, <xref:System.Threading.CancellationToken> und <xref:System.Threading.CancellationTokenSource>.  
  
 Weitere Informationen finden Sie unter [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4 (Muster für die parallele Programmierung: Verstehen und Anwenden von parallelen Mustern mit .NET Framework 4)](https://www.microsoft.com/download/details.aspx?id=19222).  
  
 Datenparallelismus mit deklarativer oder abfrageähnlicher Syntax wird von PLINQ unterstützt. Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) Paralleles LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung |  
|-----------|-----------------|  
|[How to: Write a Simple Parallel.For Loop (Vorgehensweise: Schreiben einer einfachen Parallel.For-Schleife)](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife über jedes Array oder indizierbare <xref:System.Collections.Generic.IEnumerable%601>-Quellauflistung geschrieben wird.|  
|[How to: Write a Simple Parallel.ForEach Loop (Vorgehensweise: Schreiben einer einfachen Parallel.ForEach-Schleife)](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-foreach-loop.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife über jede <xref:System.Collections.Generic.IEnumerable%601>-Quellauflistung geschrieben wird.|  
|[Vorgehensweise: Beenden oder Verlassen einer Parallel.For-Schleife](https://msdn.microsoft.com/library/de52e4f1-9346-4ad5-b582-1a4d54dc7f7e)|Beschreibt, wie eine parallele Schleife beendet oder unterbrochen wird, damit alle Threads von der Aktion informiert werden.|  
|[How to: Write a Parallel.For Loop with Thread-Local Variables (Vorgehensweise: Schreiben einer Parallel.For-Schleife mit thread-lokalen Variablen)](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife geschrieben wird, in der jeder Thread eine private Variable beibehält, die für alle anderen Threads nicht sichtbar ist, und wie die Ergebnisse von allen Threads synchronisiert werden, wenn die Schleife abgeschlossen wird.|  
|[Vorgehensweise: Schreiben einer Parallel.ForEach-Schleife mit partitionslokalen Variablen](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md)|Beschreibt, wie eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife geschrieben wird, in der jeder Thread eine private Variable beibehält, die für alle anderen Threads nicht sichtbar ist, und wie die Ergebnisse von allen Threads synchronisiert werden, wenn die Schleife abgeschlossen wird.|  
|[How to: Cancel a Parallel.For or ForEach Loop (Vorgehensweise: Abbrechen einer Parallel.For-Schleife oder einer ForEach-Schleife)](../../../docs/standard/parallel-programming/how-to-cancel-a-parallel-for-or-foreach-loop.md)|Beschreibt, wie eine parallele Schleife mit einem <xref:System.Threading.CancellationToken?displayProperty=nameWithType>-Objekt abgebrochen wird|  
|[How to: Speed Up Small Loop Bodies (Vorgehensweise: Beschleunigen von kurzen Schleifenkörpern)](../../../docs/standard/parallel-programming/how-to-speed-up-small-loop-bodies.md)|Beschreibt eine Möglichkeit zur Beschleunigung der Ausführung, wenn ein Schleifenkörper sehr klein ist.|  
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Übersicht über die Task Parallel Library.|  
|[Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)|Einführung in parallele Programmierung in .NET Framework|  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
