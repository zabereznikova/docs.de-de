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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten. Diese Synchronisierungsereignisse beruhen auf Win32-Wait-Handles und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.  
  
 Ereignis-Wait-Handles eignen sich in viele der gleichen Synchronisierungsszenarien als die <xref:System.Threading.Monitor> Klasse. Ereignis-Wait-Handles sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> Methoden, und sie bieten mehr Kontrolle über signalisieren. Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 Die <xref:System.Threading.EventWaitHandle> Klasse kann entweder automatisch oder manuell zurückgesetzt wird, sowie entweder lokale Ereignisse oder benannte darstellen Systemereignisse.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Die <xref:System.Threading.AutoResetEvent> Klasse leitet sich von <xref:System.Threading.EventWaitHandle> und stellt ein lokales Ereignis, das automatisch zurückgesetzt.  
  
 [ManualResetEvent und ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Die <xref:System.Threading.ManualResetEvent> Klasse leitet sich von <xref:System.Threading.EventWaitHandle> und stellt ein lokales Ereignis, das manuell zurückgesetzt werden muss. Die <xref:System.Threading.ManualResetEventSlim> -Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 Die <xref:System.Threading.CountdownEvent> -Klasse bietet eine vereinfachte Möglichkeit, Fork-Join Parallelität Muster im Code zu implementieren, dass-Handle verwendet Wait.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Wait-Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Die <xref:System.Threading.WaitHandle> Klasse ist die Basisklasse für die <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, und <xref:System.Threading.Mutex> Klassen. Enthält statische Methoden wie z. B. <xref:System.Threading.WaitHandle.SignalAndWait%2A> und <xref:System.Threading.WaitHandle.WaitAll%2A> , sind hilfreich bei der Arbeit mit allen Arten von Wait-Handles.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Grundlagen des verwalteten Threadings](../../../docs/standard/threading/managed-threading-basics.md)
