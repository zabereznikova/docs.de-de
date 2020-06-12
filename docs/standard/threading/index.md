---
title: Verwaltetes Threading
description: Hier finden Sie Links zu Artikeln über verwaltetes Threading in .NET, die sich mit den Grundlagen, den bewährten Methoden, den Threadingobjekten und -features, Referenzseiten und mehr befassen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: 570db45138c85c4252967404da4404d434660d69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599749"
---
# <a name="managed-threading"></a>Verwaltetes Threading
Unabhängig davon, ob eine Anwendung für einen Computer mit einem oder mehreren Prozessoren entwickelt wurde, sollte sie optimal auf die Interaktion mit einem Benutzer reagieren, auch wenn sie gerade mit anderen Aufgaben befasst ist. Die Verwendung verschiedener Ausführungsthreads stellt eine der effektivsten Möglichkeiten dar, eine Anwendung entsprechend reaktionsschnell zu gestalten und gleichzeitig den Prozessor zwischen Benutzerereignissen oder sogar währenddessen zu nutzen. In diesem Abschnitt werden die grundlegenden Threadingkonzepte eingeführt und insbesondere verwaltete Threadingkonzepte und die Verwendung von verwaltetem Threading ausführlich behandelt.  
  
> [!NOTE]
> Ab .NET Framework 4 wird die Multithreadprogrammierung durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Tasks anstatt von Threads basiert, erheblich vereinfacht. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Grundlagen des verwalteten Threadings](managed-threading-basics.md)  
 Enthält eine Übersicht über das verwaltete Threading und erläutert, in welchen Fällen mehrere Threads verwendet werden.  
  
 [Verwenden von Threads und Threading](using-threads-and-threading.md)  
 Erklärt das Erstellen, Starten, Anhalten, Fortsetzen und Abbrechen von Threads.  
  
 [Empfohlene Vorgehensweise für das verwaltete Threading](managed-threading-best-practices.md)  
 Behandelt Synchronisierungsstufen, die Vermeidung von Deadlock- und Racebedingungen und weitere Threadingprobleme.  
  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)  
 Beschreibt die verwalteten Klassen, mit denen Sie Threadingaktivitäten sowie die Daten von Objekten, auf die in verschiedenen Threads zugegriffen wird, synchronisieren können, und bietet eine Übersicht über Threadpoolthreads.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Threading>  
 Enthält Klassen zum Verwenden und Synchronisieren von verwalteten Threads.  
  
 <xref:System.Collections.Concurrent>  
 Enthält Auflistungsklassen, die sicher mit mehreren Threads verwendet werden können.  
  
 <xref:System.Threading.Tasks>  
 Enthält Klassen zum Erstellen und Planen von parallelen Verarbeitungsaufgaben.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Anwendungsdomänen](../../framework/app-domains/application-domains.md)  
 Übersicht über Anwendungsdomänen und deren Verwendung durch die Common Language-Infrastruktur.  
  
 [Asynchrone Datei-E/A](../io/asynchronous-file-i-o.md)  
 Beschreibt die Leistungsvorteile und den grundlegenden Ablauf der asynchronen E/A.  
  
 [Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](../asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 Bietet eine Übersicht über das empfohlene Muster für asynchrone Programmierung in .NET.  
  
 [Asynchrones Aufrufen von synchronen Methoden](../asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Erläutert das Aufrufen von Methoden für Threadpoolthreads mithilfe der integrierten Features von Delegaten.  
  
 [Parallele Programmierung](../parallel-programming/index.md)  
 Beschreibt die parallelen Programmierbibliotheken, die die Verwendung mehrerer Threads in Anwendungen vereinfachen.  
  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../parallel-programming/introduction-to-plinq.md)  
 Beschreibt ein System zum parallelen Ausführen von Abfragen, um die Vorteile mehrerer Prozessoren zu nutzen.
