---
title: Threading (c#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e3f213b43c2f05a5afef1db7aec8b9c2695df989
ms.contentlocale: de-de
ms.lasthandoff: 06/15/2017

---
# <a name="threading-c"></a>Threading (C#)
Threading ermöglicht das C#-Programm ausführen, gleichzeitige Verarbeitung, damit Sie mehrere Vorgänge gleichzeitig ausführen können. Beispielsweise können Sie threading überwachen Eingaben des Benutzers, Ausführen von Hintergrundaufgaben und gleichzeitige Eingabestreams zu behandeln.  
  
 Threads haben die folgenden Eigenschaften:  
  
-   Threads ermöglichen das Programm zum Ausführen von parallelen Verarbeitung.  
  
-   .NET Framework <xref:System.Threading> Namespace nutzt, die Verwendung von Threads.  
  
-   Threads gemeinsam nutzen, die Ressourcen der Anwendung. Weitere Informationen finden Sie unter [mithilfe von Threads und Threading](https://msdn.microsoft.com/library/e1dx6b2h).  
  
 Standardmäßig besitzt ein C#-Programm einen Thread. Allerdings können Hilfsthreads erstellt und zum Ausführen von Code mit dem primären Thread parallel verwendet werden. Diese Threads sind häufig bezeichnet *Arbeitsthreads*.  
  
 Arbeitsthreads können zeitaufwändig oder zeitkritische Aufgaben ohne Binden des primären Threads verwendet werden. Arbeitsthreads werden beispielsweise häufig in Server-Anwendungen verwendet, um eingehende Anforderungen zu erfüllen, ohne zu warten, für die vorherige Anforderung abgeschlossen werden. Arbeitsthreads werden auch "Hintergrund" Aufgaben in desktop-Anwendungen verwendet, damit der Hauptthread--die Elemente der Benutzeroberfläche--bleibt, die auf Benutzeraktionen reagieren, steuert.  
  
 Threading löst Probleme mit dem Durchsatz und Reaktionsfähigkeit, aber sie können auch gemeinsame Nutzung von Ressourcen zu Problemen führen, z. B. Deadlocks und Racebedingungen. Mehrere Threads sind besonders für Aufgaben, die verschiedene Ressourcen wie Dateihandles und Netzwerkverbindungen benötigt. Mehrere Threads einer einzelnen Ressource zuzuweisen, wird wahrscheinlich Synchronisierungsproblemen zu verursachen, und Threads häufig blockiert beim Warten auf andere Threads zunichte von mehreren Threads.  
  
 Eine allgemeine Strategie ist die Verwendung von Arbeitsthreads zeitaufwändig ausführen oder zeitkritische Aufgaben, die viele der Ressourcen von anderen Threads nicht benötigen. Natürlich müssen einige Ressourcen in Ihrem Programm durch mehrere Threads zugegriffen werden. In diesen Fällen die <xref:System.Threading> -Namespace stellt Klassen zum Synchronisieren von Threads bereit. Diese Klassen umfassen <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, und <xref:System.Threading.ManualResetEvent>.  
  
 Können Sie einige oder alle diese Klassen zum Synchronisieren der Aktivitäten mehrerer Threads, aber einige Unterstützung für threading wird von der C#-Sprache unterstützt. Z. B. die [Ausnahmebehandlungsanweisung](../../../../csharp/language-reference/keywords/lock-statement.md) bietet Synchronisierungsfeatures für die über impliziten Verwendung der <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  Ab der [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], Multithreading-Programmierung erheblich vereinfacht die <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> und <xref:System.Threading.Tasks.Task?displayProperty=fullName> Klassen, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), neue gleichzeitigen Auflistungsklassen der <xref:System.Collections.Concurrent?displayProperty=fullName> -Namespace und eine neue Programmiermodell, das auf dem Konzept von Aufgaben anstatt von Threads basiert. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](https://msdn.microsoft.com/library/dd460693).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Multithreaded Applications (C#) (Multithreadanwendungen (C#))](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|Beschreibt das Erstellen und Verwenden von Threads.|  
|[Parameter und Rückgabewerte für Multithreadprozeduren (c#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Beschreibt, wie übergeben und Rückgabeparameter mit Multithreadanwendungen verwendet werden können.|  
|[Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (c#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Veranschaulicht das Erstellen einer einfachen Multithreadanwendung.|  
|[Threadsynchronisierung (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|Beschreibt, wie die Interaktionen von Threads steuern.|  
|[Threadzeitgeber (c#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)|Beschreibt die Prozeduren in separaten Threads in festen Intervallen ausgeführt.|  
|[Threadpooling (c#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|Beschreibt, wie einen Pool von Arbeitsthreads, die vom System verwaltet werden.|  
|[Vorgehensweise: Verwenden eines Threadpools (c#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Veranschaulicht die synchronisierte Verwendung mehrerer Threads im Threadpool.|  
|[Threading](https://msdn.microsoft.com/library/3e8s7xdd)|Beschreibt, wie threading in .NET Framework implementiert.|
