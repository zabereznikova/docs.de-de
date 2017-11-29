---
title: Threading (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb942047278fec7c6446190a98666532c2769c17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="threading-visual-basic"></a>Threading (Visual Basic)
Mit Threading kann Ihr Visual Basic-Programm parallele Verarbeitungsaufgaben durchführen, damit Sie mehr als einen Vorgang gleichzeitig durchführen können. Sie können z.B. Threading verwenden, um Benutzereingaben zu überwachen, Aufgaben im Hintergrund auszuführen und parallele Eingabestreams zu behandeln.  
  
 Threads weisen folgende Eigenschaften auf:  
  
-   Mit Threads kann Ihr Programm parallele Verarbeitungsaufgaben durchführen.  
  
-   Der <xref:System.Threading>-Namespace von .NET Framework erleichtert das Verwenden von Threads.  
  
-   Threads verwenden die gleichen Ressourcen wie die Anwendung. Weitere Informationen finden Sie unter [Using Threads and Threading (Verwenden von Threads und Threading)](https://msdn.microsoft.com/library/e1dx6b2h).  
  
 Standardmäßig verfügt ein Visual Basic-Programm über einen Thread. Sie können aber Hilfsthreads erstellen und diese parallel zum primären Thread zur Ausführung von Code verwenden. Diese Threads werden auch als *Arbeitsthreads* bezeichnet.  
  
 Arbeitsthreads können zum durchführen von zeitaufwändigen oder zeitkritischen Aufgaben verwendet werden, ohne dass dadurch der primäre Thread gebunden wird. Arbeitsthreads werden z.B. oft in Serveranwendungen verwendet, um eingehende Anforderungen zu erfüllen, ohne dass auf den Abschluss der vorherigen Anforderung gewartet werden muss. Arbeitsthreads werden auch verwendet, um Aufgaben im Hintergrund in der Desktopanwendung auszuführen, damit der Hauptthread – der Elemente der Benutzeroberfläche antreibt – weiterhin auf Benutzeraktionen reagieren kann.  
  
 Threading löst Probleme beim Durchsatz und der Reaktionsfähigkeit. Es kann allerdings zu Problemen bei der Ressourcenfreigabe führen, wie z.B. zu Deadlocks oder zu Racebedingungen. Mehrere Threads eignen sich am besten für Aufgaben, die verschiedenen Ressourcen erfordern, wie etwa Dateihandles und Netzwerkverbindungen. Wenn Sie einer Ressource mehrere Threads zuweisen, kann es zu Synchronisierungsproblemen kommen. Wenn Threads oft beim Warten auf andere Threads blockiert sind, verfehlt dies den Zweck mehrerer Threads.  
  
 Eine gängige Herangehensweise ist hier das Verwenden von Arbeitsthreads, die zeitaufwändige oder zeitkritische Aufgaben durchführen, die nicht viele der Ressourcen erfordern, die von anderen Threads verwendet werden. Auf einige der Ressourcen in Ihrem Programm muss aber selbstverständlich von mehreren Threads zugegriffen werden. Für diese Fälle stellt der <xref:System.Threading>-Namespace Klassen für das Synchronisieren von Threads bereit. Diese Klassen umfassen <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor> <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent>.  
  
 Sie können einige oder alle diese Klassen zum Synchronisieren der Aktivitäten mehrerer Threads verwenden. Allerdings wird der Support für das Threading teilweise von Visual Basic unterstützt. Die [SyncLock-Anweisung](../../../../visual-basic/language-reference/statements/synclock-statement.md) stellt z.B. Synchronisierungsfunktionen durch das implizit Verwenden von <xref:System.Threading.Monitor> bereit.  
  
> [!NOTE]
>  Ab [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)] wurde die Multithreadprogrammierung erheblich vereinfacht, und zwar durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Aufgaben anstatt von Threads basiert. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](https://msdn.microsoft.com/library/dd460693).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)|Beschreibt das Erstellen und Verwenden von Threads|  
|[Parameter und Rückgabewerte für Multithreadprozeduren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Beschreibt, wie Sie Parameter mit Multithreadanwendungen übergeben und zurückgeben können|  
|[Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Veranschaulicht, wie Sie eine einfache Multithreadanwendung erstellen können|  
|[Threadsynchronisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)|Beschreibt, wie Sie die Interaktionen von Threads steuern können|  
|[Threadtimer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md)|Beschreibt, wie die Prozeduren auf separaten Threads in regelmäßigen Abständen ausführen können|  
|[Threadpooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)|Beschreibt, wie Sie einen Pool von Arbeitsthreads verwenden können, die vom System verwaltet werden|  
|[Vorgehensweise: Verwenden eines Threadpools (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Veranschaulicht das synchronisierte Verwenden von mehreren Threads im Threadpool|  
|[Threading](https://msdn.microsoft.com/library/3e8s7xdd)|Beschreibt, wie Sie Threading in .NET Framework implementieren|
