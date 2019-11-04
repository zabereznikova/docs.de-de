---
title: Threadingobjekte und -funktionen
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: dd9b7b8cb194353d0a1c285af10d54dc7366896e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128962"
---
# <a name="threading-objects-and-features"></a>Threadingobjekte und -funktionen

Zusammen mit der <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse stellt .NET eine Reihe von Klassen bereit, mit denen Sie Multithread-Anwendungen entwickeln können. In den folgenden Artikeln finden Sie eine Übersicht über diese Klassen:

|Titel|Beschreibung|  
|-----------|-----------------|  
|[Der verwaltete Threadpool](the-managed-thread-pool.md)|Beschreibt die <xref:System.Threading.ThreadPool?displayProperty=nameWithType>-Klasse, die einen Pool von Arbeitsthreads bereitstellt, die von .NET verwaltet werden.|  
|[Timer](timers.md)|Beschreibt .NET-Timer, die in einer Multithreadumgebung verwendet werden können.|
|[Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md)|Beschreibt Typen, die zum Synchronisieren des Zugriffs auf eine freigegebene Ressource oder zum Steuern von Threadinteraktionen verwendet werden können.|
|[EventWaitHandle](eventwaithandle.md)|Beschreibt die <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>-Klasse, die ein Threadsynchronisierungsereignis darstellt.|
|[CountdownEvent](countdownevent.md)|Beschreibt die <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>-Klasse, die ein Threadsynchronisierungsereignis darstellt, das eingestellt wird, wenn sein Zähler gleich Null ist.|
|[Mutexe](mutexes.md)|Beschreibt die <xref:System.Threading.Mutex?displayProperty=nameWithType>-Klasse, die exklusiven Zugriff auf eine freigegebene Ressource gewährt.|
|[Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](semaphore-and-semaphoreslim.md)|Beschreibt die <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Klasse, die die Anzahl von Threads einschränkt, die gleichzeitig auf eine freigegebene Ressource oder einen Pool von Ressourcen zugreifen können.|
|[Barrier](barrier.md)|Beschreibt die <xref:System.Threading.Barrier?displayProperty=nameWithType>-Klasse, die das Barrieremuster für die Koordination von Threads in stufenweise durchgeführten Vorgängen implementiert.|
|[SpinLock](spinlock.md)|Beschreibt die <xref:System.Threading.SpinLock?displayProperty=nameWithType>-Struktur, die für bestimmte Low-Level-Sperrszenarios eine einfache Alternative zur <xref:System.Threading.Monitor?displayProperty=nameWithType>-Klasse darstellt.|
|[SpinWait](spinwait.md)|Beschreibt die <xref:System.Threading.SpinWait?displayProperty=nameWithType>-Struktur, die Unterstützung für Spin-basierte Wartevorgänge bereitstellt.|

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [Verwenden von Threads und Threading](using-threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Parallele Programmierung](../parallel-programming/index.md)
- [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)
