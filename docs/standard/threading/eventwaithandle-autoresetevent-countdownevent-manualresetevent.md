---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47205918"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent

Threads können mithilfe von Wait-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten. Diese Synchronisierungsereignisse beruhen auf Wait-Handles des Betriebssystems und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen, und Ereignisse, die manuell zurückgesetzt werden müssen.  
  
Wait-Handles für ein Ereignis sind in vielen Synchronisierungsszenarien nützlich, in denen auch die <xref:System.Threading.Monitor>-Klasse eingesetzt wird. Wait-Handles für ein Ereignis sind häufig einfacher zu verwenden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType>- und <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>-Methode, und sie bieten stärkere Kontrolle über die Signalisierung. Mit benannten Wait-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt

 [EventWaitHandle](eventwaithandle.md)  
 Die <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>-Klasse kann entweder automatische oder manuelle Zurücksetzungsereignisse sowie entweder lokale Ereignisse oder benannte Systemereignisse darstellen.  
  
 [AutoResetEvent](autoresetevent.md)  
 Die <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das automatisch zurückgesetzt wird.  
  
 [ManualResetEvent und ManualResetEventSlim](manualresetevent-and-manualreseteventslim.md)  
 Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das manuell zurückgesetzt werden muss. Die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.  
  
 [CountdownEvent](countdownevent.md)  
 Die <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>-Klasse bietet eine vereinfachte Möglichkeit zum Implementieren von Fork/Join-Parallelismusmustern in Code, in dem Wait-Handle verwendet werden.  

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
- [Managed Threading Basics](managed-threading-basics.md) (Grundlagen des verwalteten Threadings)
