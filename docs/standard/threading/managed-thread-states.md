---
title: Zustände von verwalteten Threads
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4266aea9bf206d127e2837955dcc00cc23f4119b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="managed-thread-states"></a>Zustände von verwalteten Threads
Die Eigenschaft <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> stellt eine Bitmaske zur Verfügung, die den aktuellen Zustand des Threads angibt. Ein Thread ist immer in mindestens einem der möglichen Zustände in der <xref:System.Threading.ThreadState> -Enumeration und kann mehrere Zustände zugleich aufweisen.  
  
> [!IMPORTANT]
>  Der Threadzustand ist nur in einigen Debugszenarien von Interesse. Sie sollten den Threadzustand niemals verwenden, um die Aktivitäten von Threads zu synchronisieren.  
  
 Wenn Sie einen verwalteten Thread erstellen, befindet er sich im <xref:System.Threading.ThreadState.Unstarted> -Zustand. Der Thread verbleibt im Zustand <xref:System.Threading.ThreadState.Unstarted> , bis er vom Betriebssystem in den gestarteten Zustand versetzt wird. Durch Aufrufen von <xref:System.Threading.Thread.Start%2A> wird das Betriebssystem darüber informiert, dass der Thread gestartet werden kann; es ändert jedoch nicht den Zustand des Threads.  
  
 Nicht verwaltete Threads, die in die verwaltete Umgebung gelangen, befinden sich bereits im gestarteten Zustand. Sobald sich ein Thread im gestarteten Zustand befindet, kann eine Reihe von Aktionen eine Änderung seines Zustands bewirken. In der folgenden Tabelle sind die Aktionen aufgelistet, die zu einer Zustandsänderung führen, zusammen mit dem entsprechenden neuen Zustand.  
  
|Aktion|Resultierender neuer Zustand|  
|------------|-------------------------|  
|Der Konstruktor für die <xref:System.Threading.Thread> -Klasse wird aufgerufen.|<xref:System.Threading.ThreadState.Unstarted>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> auf.|<xref:System.Threading.ThreadState.Unstarted>|  
|Der Thread reagiert auf <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> und wird gestartet.|<xref:System.Threading.ThreadState.Running>|  
|Der Thread ruft <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> auf.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Der Thread ruft <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> auf einem anderen Objekt auf.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Der Thread ruft <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> auf einem anderen Thread auf.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> auf.|<xref:System.Threading.ThreadState.SuspendRequested>|  
|Der Thread reagiert auf eine <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>-Anforderung.|<xref:System.Threading.ThreadState.Suspended>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> auf.|<xref:System.Threading.ThreadState.Running>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> auf.|<xref:System.Threading.ThreadState.AbortRequested>|  
|Der Thread reagiert auf eine <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Anforderung.|<xref:System.Threading.ThreadState.Aborted>, dann <xref:System.Threading.ThreadState.Stopped>|  
  
 Da der <xref:System.Threading.ThreadState.Running> -Zustand den Wert „0“ hat, kann kein Bittest zur Erkennung dieses Zustands ausgeführt werden. Stattdessen kann der folgende Test (in Pseudocode) verwendet werden:  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 Threads sind häufig in mehreren Zuständen gleichzeitig. Wenn beispielsweise ein Thread durch einen <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>-Aufruf blockiert ist und ein anderer Thread <xref:System.Threading.Thread.Abort%2A> für den gleichen Thread aufruft, befindet sich der Thread gleichzeitig im Zustand <xref:System.Threading.ThreadState.WaitSleepJoin> und <xref:System.Threading.ThreadState.AbortRequested>. Sobald der Thread in diesem Fall von dem Aufruf an <xref:System.Threading.Monitor.Wait%2A> zurückkehrt oder unterbrochen wird, empfängt er die <xref:System.Threading.ThreadAbortException>.  
  
 Sobald ein Thread den Zustand <xref:System.Threading.ThreadState.Unstarted> als Folge eines Aufrufs von <xref:System.Threading.Thread.Start%2A>verlässt, kann er nicht mehr in den Zustand <xref:System.Threading.ThreadState.Unstarted> zurückkehren. Ein Thread kann den Zustand <xref:System.Threading.ThreadState.Stopped> nie verlassen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadState>  
 [Threading](../../../docs/standard/threading/index.md)
