---
title: Threadingobjekte und -funktionen
ms.date: 08/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d56d962279120a03a6e4b89154ac1429ea5479e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44039328"
---
# <a name="threading-objects-and-features"></a>Threadingobjekte und -funktionen

Zusammen mit der <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse stellt .NET eine Reihe von Klassen bereit, mit denen Sie Multithread-Anwendungen entwickeln können. In den folgenden Artikeln finden Sie eine Übersicht über diese Klassen:

|Titel|Beschreibung |  
|-----------|-----------------|  
|[Der verwaltete Threadpool](the-managed-thread-pool.md)|Beschreibt die <xref:System.Threading.ThreadPool?displayProperty=nameWithType>-Klasse, die einen Pool von Arbeitsthreads bereitstellt, die von .NET verwaltet werden.|  
|[Timer](timers.md)|Beschreibt Zeitgeber, die in einer Multithreadumgebung verwendet werden können.|
|[Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)|Beschreibt Klassen, die zum Synchronisieren des Zugriffs auf Daten oder zum Steuern von Threadinteraktionen verwendet werden können.|
|[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|Beschreibt verwaltete Event-Wait-Handles, die signalisieren und auf Signale warten und zum Synchronisieren von Threadaktivitäten verwendet werden.|
|[Mutexe](mutexes.md)|Erläutert, wie ein <xref:System.Threading.Mutex?displayProperty=nameWithType> zum Synchronisieren des Zugriffs auf ein Objekt oder zum Erstellen eigener Synchronisierungsmechanismen verwendet wird.|
|[Interlocked-Vorgänge](interlocked-operations.md)|Beschreibt die <xref:System.Threading.Interlocked?displayProperty=nameWithType>-Klasse, die atomare Operationen für Variablen bereitstellt, die von mehreren Threads gemeinsam genutzt werden.|
|[Lese-/Schreibsperren](reader-writer-locks.md)|Beschreibt die <xref:System.Threading.ReaderWriterLockSlim?displayProperty=nameWithType>-Klasse, die Semantik für einzelne Verfasser/mehrere Leser bereitstellt.|
|[Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](semaphore-and-semaphoreslim.md)|Beschreibt <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Klasse und erläutert, wie diese zum Steuern des Zugriffs auf begrenzte Ressourcen verwendet wird.|
|[Barrier](barrier.md)|Beschreibt <xref:System.Threading.Barrier?displayProperty=nameWithType>-Klasse, die das Barrieremuster für die Koordination von Threads in stufenweise durchgeführten Vorgängen implementiert.|
|[SpinLock](spinlock.md)|Beschreibt die <xref:System.Threading.SpinLock?displayProperty=nameWithType>-Klasse, die für bestimmte Low-Level-Szenarios eine einfache Alternative zur <xref:System.Threading.Monitor?displayProperty=nameWithType>-Klasse darstellt.|
|[SpinWait](spinwait.md)|Beschreibt die <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Klasse, einen Low-Level-Synchronisierungsprimitiven, der vor dem Initiieren eines kernelbasierten Wartevorgangs Spinvorgänge ausführt.|

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Verwenden von Threads und Threading](using-threads-and-threading.md)
- [Asynchrone Datei-E/A](../io/asynchronous-file-i-o.md)
- [Parallele Programmierung](../parallel-programming/index.md)
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
