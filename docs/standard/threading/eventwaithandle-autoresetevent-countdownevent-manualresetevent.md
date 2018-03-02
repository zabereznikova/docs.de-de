---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6c545f9ebc924c0a12ee2e76fdb6c725c25e2353
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten. Diese Synchronisierungsereignisse beruhen auf Win32-Wait-Handles und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.  
  
 Wait-Handles für ein Ereignis sind in vielen Synchronisierungsszenarien nützlich, in denen auch die <xref:System.Threading.Monitor>-Klasse eingesetzt wird. Wait-Handles für ein Ereignis sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>- und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>-Methode, und sie bieten stärkere Kontrolle über die Signalisierung. Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 Die <xref:System.Threading.EventWaitHandle>-Klasse kann entweder automatische oder manuelle Zurücksetzungsereignisse sowie entweder lokale Ereignisse oder benannte Systemereignisse darstellen.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Die <xref:System.Threading.AutoResetEvent>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das automatisch zurückgesetzt wird.  
  
 [ManualResetEvent und ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Die <xref:System.Threading.ManualResetEvent>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das manuell zurückgesetzt werden muss. Die <xref:System.Threading.ManualResetEventSlim>-Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 Die <xref:System.Threading.CountdownEvent>-Klasse bietet eine vereinfachte Möglichkeit zum Implementieren von Fork/Join-Parallelismusmustern in Code, in dem Wait-Handle verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Wait-Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Die <xref:System.Threading.WaitHandle>-Klasse ist die Basisklasse für die <xref:System.Threading.EventWaitHandle>-, <xref:System.Threading.Semaphore>- und <xref:System.Threading.Mutex>-Klasse. Sie enthält statische Methoden wie <xref:System.Threading.WaitHandle.SignalAndWait%2A> und <xref:System.Threading.WaitHandle.WaitAll%2A>, die bei der Arbeit mit allen Typen von Wait-Handles hilfreich sind.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Grundlagen des verwalteten Threadings](../../../docs/standard/threading/managed-threading-basics.md)
