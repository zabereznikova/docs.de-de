---
title: Verwenden von Threads und Threading
ms.date: 08/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
ms.openlocfilehash: 863fa565f7c107214273912a6d110b7664bffe6b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131495"
---
# <a name="using-threads-and-threading"></a>Verwenden von Threads und Threading

Sie können mit .NET Anwendungen schreiben, die mehrere Vorgänge zur gleichen Zeit ausführen. Vorgänge, die möglicherweise andere Vorgänge aufhalten, können in separaten Threads ausgeführt werden. Dieser Prozess ist als *Multithreading* oder *Freies Threading* bekannt.  
  
Clientanwendungen, die Multithreading verwenden, reagieren besser auf Benutzereingaben, weil die Benutzeroberfläche aktiv bleibt, da prozessorintensive Aufgaben in separaten Threads ausgeführt werden. Multithreading ist auch nützlich, wenn Sie skalierbare Aufgaben erstellen, da Sie Threads bei steigender Arbeitsauslastung hinzufügen können.

> [!NOTE]
> Wenn Sie mehr Kontrolle über das Verhalten von Threads der Anwendung benötigen, können Sie die Threads selbst verwalten. Ab .NET Framework 4 wird die Multithreadprogrammierung durch die Klassen <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/parallel-linq-plinq.md), neue parallele Sammlungsklassen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace und ein neues Programmiermodell, das auf dem Konzept von Tasks anstatt von Threads basiert, erheblich vereinfacht. Weitere Informationen finden Sie in den Artikeln zur [parallelen Programmierung](../parallel-programming/index.md) und zu [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md).

## <a name="how-to-create-and-start-a-new-thread"></a>Vorgehensweise: Erstellen und Starten eines neuen Threads

Sie können einen neuen Thread erstellen, indem Sie eine neue Instanz der <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse erstellen und den Namen der Methode angeben, die Sie in einem neuen Thread an den Konstruktor ausführen möchten. Rufen Sie die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methode auf, um einen erstellten Thread auszuführen. Weitere Informationen und Beispiele finden Sie unter [Erstellen von Threads und Übergeben von Daten zur Startzeit](creating-threads-and-passing-data-at-start-time.md) und in der <xref:System.Threading.Thread>-API-Referenz.

## <a name="how-to-stop-a-thread"></a>Vorgehensweise: Anhalten eines Threads

Verwenden Sie die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode, um die Ausführung eines Threads zu beenden. Diese Methode löst eine <xref:System.Threading.ThreadAbortException> im Thread aus, in dem sie aufgerufen wird. Weitere Informationen finden Sie unter [Zerstören von Threads](destroying-threads.md).

Ab .NET Framework 4 können Sie die <xref:System.Threading.CancellationToken?displayProperty=nameWithType> verwenden, um einen Thread kooperativ abzubrechen. Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](cancellation-in-managed-threads.md).

Verwenden Sie die <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>-Methode, damit der aufrufende Thread auf das Beenden des Threads wartet, in dem die Methode aufgerufen wurde.

## <a name="how-to-pause-or-interrupt-a-thread"></a>Vorgehensweise: Anhalten oder Unterbrechen eines Threads

Mit der <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>-Methode können Sie den aktuellen Thread für bestimmte Zeit pausieren. Sie können einen blockierten Thread unterbrechen, indem Sie die <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>-Methode aufrufen. Weitere Informationen finden Sie unter [Pausing and interrupting threads (Anhalten und Unterbrechen von Threads)](pausing-and-resuming-threads.md).

## <a name="thread-properties"></a>Threadeigenschaften

In der folgenden Tabelle werden einige <xref:System.Threading.Thread>-Eigenschaften aufgeführt:  
  
|Eigenschaft|BESCHREIBUNG|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Gibt `true` zurück, wenn dieser Thread gestartet und ordnungsgemäß beendet bzw. abgebrochen wurde.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Es wird ein boolescher Wert abgerufen oder festgelegt, der angibt, ob ein Thread ein Hintergrundthread ist. Hintergrundthreads sind wie Vordergrundthreads, aber ein Hintergrundthread verhindert nicht, dass ein Prozess beendet wird. Sobald alle zu einem Prozess gehörenden Vordergrundthreads beendet wurden, beendet die Common Language Runtime den Prozess, indem die Methode <xref:System.Threading.Thread.Abort%2A> in Hintergrundthreads aufgerufen wird, die noch aktiv sind. Weitere Informationen finden Sie im Artikel zu [Vordergrund- und Hintergrundthreads](foreground-and-background-threads.md).|  
|<xref:System.Threading.Thread.Name%2A>|Ruft den Namen eines Threads ab oder legt diesen fest. Wird am häufigsten beim Debuggen verwendet, um einzelne Threads zu erkennen.|  
|<xref:System.Threading.Thread.Priority%2A>|Es wird ein <xref:System.Threading.ThreadPriority>-Wert abgerufen oder festgelegt, der vom Betriebssystem zum Priorisieren der Threadplanung verwendet wird. Weitere Informationen finden Sie unter [Scheduling Threads (Planen von Threads)](scheduling-threads.md) und in der <xref:System.Threading.ThreadPriority>-Referenz.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Ruft einen <xref:System.Threading.ThreadState>-Wert ab, der die aktuellen Zustände des Threads enthält.|  

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Thread?displayProperty=nameWithType>
- [Threads and Threading (Threads und Threading)](threads-and-threading.md)
- [Parallele Programmierung](../parallel-programming/index.md)
