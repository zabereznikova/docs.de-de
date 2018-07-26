---
title: Threading (C#)
ms.date: 07/20/2015
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
ms.openlocfilehash: 8325132a359c8b65572943bb79c9f02a485eb290
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874665"
---
# <a name="threading-c"></a>Threading (C#)
Mit Threading kann Ihr C#-Programm parallele Verarbeitungsaufgaben durchführen, damit Sie mehr als einen Vorgang gleichzeitig durchführen können. Sie können z.B. Threading verwenden, um Benutzereingaben zu überwachen, Aufgaben im Hintergrund auszuführen und parallele Eingabestreams zu behandeln.  
  
 Threads weisen folgende Eigenschaften auf:  
  
-   Mit Threads kann Ihr Programm parallele Verarbeitungsaufgaben durchführen.  
  
-   Der <xref:System.Threading>-Namespace von .NET Framework erleichtert das Verwenden von Threads.  
  
-   Threads verwenden die gleichen Ressourcen wie die Anwendung. Weitere Informationen finden Sie unter [Using Threads and Threading (Verwenden von Threads und Threading)](../../../../../docs/standard/threading/using-threads-and-threading.md).  
  
 Standardmäßig verfügt ein C#-Programm über einen Thread. Sie können aber Hilfsthreads erstellen und diese parallel zum primären Thread zur Ausführung von Code verwenden. Diese Threads werden auch als *Arbeitsthreads* bezeichnet.  
  
 Arbeitsthreads können zum durchführen von zeitaufwändigen oder zeitkritischen Aufgaben verwendet werden, ohne dass dadurch der primäre Thread gebunden wird. Arbeitsthreads werden z.B. oft in Serveranwendungen verwendet, um eingehende Anforderungen zu erfüllen, ohne dass auf den Abschluss der vorherigen Anforderung gewartet werden muss. Arbeitsthreads werden auch verwendet, um Aufgaben im Hintergrund in der Desktopanwendung auszuführen, damit der Hauptthread – der Elemente der Benutzeroberfläche antreibt – weiterhin auf Benutzeraktionen reagieren kann.  
  
 Threading löst Probleme beim Durchsatz und der Reaktionsfähigkeit. Es kann allerdings zu Problemen bei der Ressourcenfreigabe führen, wie z.B. zu Deadlocks oder zu Racebedingungen. Mehrere Threads eignen sich am besten für Aufgaben, die verschiedenen Ressourcen erfordern, wie etwa Dateihandles und Netzwerkverbindungen. Wenn Sie einer Ressource mehrere Threads zuweisen, kann es zu Synchronisierungsproblemen kommen. Wenn Threads oft beim Warten auf andere Threads blockiert sind, verfehlt dies den Zweck mehrerer Threads.  
  
 Eine gängige Herangehensweise ist hier das Verwenden von Arbeitsthreads, die zeitaufwändige oder zeitkritische Aufgaben durchführen, die nicht viele der Ressourcen erfordern, die von anderen Threads verwendet werden. Auf einige der Ressourcen in Ihrem Programm muss aber selbstverständlich von mehreren Threads zugegriffen werden. Für diese Fälle stellt der <xref:System.Threading>-Namespace Klassen für das Synchronisieren von Threads bereit. Diese Klassen umfassen <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor> <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> und <xref:System.Threading.ManualResetEvent>.  
  
 Sie können einige oder alle diese Klassen zum Synchronisieren der Aktivitäten mehrerer Threads verwenden. Allerdings wird der Support für das Threading teilweise von C# unterstützt. Die [Lock-Anweisung](../../../../csharp/language-reference/keywords/lock-statement.md) stellt z.B. Synchronisierungsfunktionen durch das implizit Verwenden von <xref:System.Threading.Monitor> bereit.  
  
> [!NOTE]
>  Ab [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)] wurde die Multithreadprogrammierung erheblich vereinfacht, und zwar durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), neue parallele Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Aufgaben anstatt von Threads basiert. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../../../docs/standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung |  
|-----------|-----------------|  
|[Multithreaded Applications (C#) (Multithreadanwendungen (C#))](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|Beschreibt das Erstellen und Verwenden von Threads|  
|[Parameter und Rückgabewerte für Multithreadprozeduren (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Beschreibt, wie Sie Parameter mit Multithreadanwendungen übergeben und zurückgeben können|  
|[Exemplarische Vorgehensweise: Multithreading mit der BackgroundWorker-Komponente (C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Veranschaulicht, wie Sie eine einfache Multithreadanwendung erstellen können|  
|[Threadsynchronisierung (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|Beschreibt, wie Sie die Interaktionen von Threads steuern können|  
|[Thread Pooling (C#) (Pooling von Threads (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|Beschreibt, wie Sie einen Pool von Arbeitsthreads verwenden können, die vom System verwaltet werden|  
|[Vorgehensweise: Verwenden eines Threadpools (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Veranschaulicht das synchronisierte Verwenden von mehreren Threads im Threadpool|  
|[Threading](../../../../../docs/standard/threading/index.md)|Beschreibt, wie Sie Threading in .NET Framework implementieren|
