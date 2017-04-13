---
title: "Zust&#228;nde von verwalteten Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Threading [.NET Framework], Zustände"
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Zust&#228;nde von verwalteten Threads
Die Eigenschaft <xref:System.Threading.Thread.ThreadState%2A?displayProperty=fullName> stellt eine Bitmaske zur Verfügung, die den aktuellen Zustand des Threads angibt. Ein Thread ist immer in mindestens einem der möglichen Zustände in der <xref:System.Threading.ThreadState>\-Enumeration und kann mehrere Zustände zugleich aufweisen.  
  
> [!IMPORTANT]
>  Der Threadzustand ist nur in einigen Debugszenarien von Interesse. Sie sollten den Threadzustand niemals verwenden, um die Aktivitäten von Threads zu synchronisieren.  
  
 Wenn Sie einen verwalteten Thread erstellen, befindet er sich im <xref:System.Threading.ThreadState>\-Zustand. Der Thread verbleibt im Zustand <xref:System.Threading.ThreadState>, bis er vom Betriebssystem in den gestarteten Zustand versetzt wird. Durch Aufrufen von <xref:System.Threading.Thread.Start%2A> wird das Betriebssystem darüber informiert, dass der Thread gestartet werden kann; es ändert jedoch nicht den Zustand des Threads.  
  
 Nicht verwaltete Threads, die in die verwaltete Umgebung gelangen, befinden sich bereits im gestarteten Zustand. Sobald sich ein Thread im gestarteten Zustand befindet, kann eine Reihe von Aktionen eine Änderung seines Zustands bewirken. In der folgenden Tabelle sind die Aktionen aufgelistet, die zu einer Zustandsänderung führen, zusammen mit dem entsprechenden neuen Zustand.  
  
|Aktion|Resultierender neuer Zustand|  
|------------|----------------------------------|  
|Der Konstruktor für die <xref:System.Threading.Thread>\-Klasse wird aufgerufen.|<xref:System.Threading.ThreadState>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> auf.|<xref:System.Threading.ThreadState>|  
|Der Thread reagiert auf <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> und wird gestartet.|<xref:System.Threading.ThreadState>|  
|Der Thread ruft <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> auf.|<xref:System.Threading.ThreadState>|  
|Der Thread ruft <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> auf einem anderen Objekt auf.|<xref:System.Threading.ThreadState>|  
|Der Thread ruft <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> auf einem anderen Thread auf.|<xref:System.Threading.ThreadState>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> auf.|<xref:System.Threading.ThreadState>|  
|Der Thread reagiert auf eine <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>\-Anforderung.|<xref:System.Threading.ThreadState>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> auf.|<xref:System.Threading.ThreadState>|  
|Ein anderer Thread ruft <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> auf.|<xref:System.Threading.ThreadState>|  
|Der Thread reagiert auf eine <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>\-Anforderung.|<xref:System.Threading.ThreadState>, dann <xref:System.Threading.ThreadState>|  
  
 Da der <xref:System.Threading.ThreadState>\-Zustand den Wert „0“ hat, kann kein Bittest zur Erkennung dieses Zustands ausgeführt werden. Stattdessen kann der folgende Test \(in Pseudocode\) verwendet werden:  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 Threads sind häufig in mehreren Zuständen gleichzeitig. Wenn beispielsweise ein Thread durch einen <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName>\-Aufruf blockiert ist und ein anderer Thread <xref:System.Threading.Thread.Abort%2A> für den gleichen Thread aufruft, befindet sich der Thread gleichzeitig im Zustand <xref:System.Threading.ThreadState> und im Zustand <xref:System.Threading.ThreadState>. Sobald der Thread in diesem Fall von dem Aufruf an <xref:System.Threading.Monitor.Wait%2A> zurückkehrt oder unterbrochen wird, empfängt er die <xref:System.Threading.ThreadAbortException>.  
  
 Sobald ein Thread den Zustand <xref:System.Threading.ThreadState> als Folge eines Aufrufs von <xref:System.Threading.Thread.Start%2A> verlässt, kann er nicht mehr in den Zustand <xref:System.Threading.ThreadState> zurückkehren. Ein Thread kann den Zustand <xref:System.Threading.ThreadState> nie verlassen.  
  
## Siehe auch  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadState>   
 [Threading](../../../docs/standard/threading/index.md)