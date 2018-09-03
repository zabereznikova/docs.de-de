---
title: ManualResetEvent und ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4a6950d17fef60298a2e47b63bec068554b2b8b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43390500"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent und ManualResetEventSlim
Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse stellt ein lokales Wait-Handleereignis dar, das manuell zurückgesetzt werden muss, nachdem es signalisiert worden ist. Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> dar. Weitere Informationen zur Verwendung und zu den Features manueller Reset-Ereignisse finden Sie in der Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.ManualResetEvent>-Objekt bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden. <xref:System.Threading.ManualResetEvent> entspricht einem Win32-`CreateEvent`-Aufruf, wobei `true` für das `bManualReset`-Argument angegeben wird.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie für eine bessere Leistung die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse verwenden, wenn die Wartezeiten als sehr kurz eingeschätzt werden und das Ereignis nicht prozessübergreifend ist. <xref:System.Threading.ManualResetEventSlim> verwendet während des Wartens auf die Signalisierung des Ereignisses für kurze Zeit ausgelastete Spinvorgänge. Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait-Handles. Wenn das Ereignis jedoch nicht innerhalb eines bestimmten Zeitraums signalisiert wird, greift <xref:System.Threading.ManualResetEventSlim> auf einen normalen Wartevorgang mit Ereignishandle zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait-Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
