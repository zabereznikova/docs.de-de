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
ms.openlocfilehash: 864c39aa6673537d66d8402896bce5b4fa92e5ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602442"
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent und ManualResetEventSlim
Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse stellt ein lokales Wait-Handleereignis dar, das manuell zurückgesetzt werden muss, nachdem es signalisiert worden ist. Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> dar. Weitere Informationen zur Verwendung und zu den Features manueller Reset-Ereignisse finden Sie in der Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.ManualResetEvent>-Objekt bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden.
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie für eine bessere Leistung die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>-Klasse verwenden, wenn die Wartezeiten als sehr kurz eingeschätzt werden und das Ereignis nicht prozessübergreifend ist. <xref:System.Threading.ManualResetEventSlim> verwendet während des Wartens auf die Signalisierung des Ereignisses für kurze Zeit ausgelastete Spinvorgänge. Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait-Handles. Wenn das Ereignis jedoch nicht innerhalb eines bestimmten Zeitraums signalisiert wird, greift <xref:System.Threading.ManualResetEventSlim> auf einen normalen Wartevorgang mit Ereignishandle zurück.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [AutoResetEvent](autoresetevent.md)
- [SpinWait](spinwait.md)
- [Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](semaphore-and-semaphoreslim.md)
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
- [Threading](index.md)
