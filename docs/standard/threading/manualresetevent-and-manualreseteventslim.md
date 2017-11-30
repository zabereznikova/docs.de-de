---
title: ManualResetEvent und ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent und ManualResetEventSlim
Die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Klasse stellt ein lokales Wait-Handle-Ereignis, das manuell zurückgesetzt werden muss, nachdem es signalisiert wird. Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Weitere Informationen zur Verwendung und zu den Features manueller Reset-Ereignisse finden Sie in der Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.ManualResetEvent> Objekt bleibt signalisiert, bis seine <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> -Methode aufgerufen wird. Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden. <xref:System.Threading.ManualResetEvent>entspricht einem Win32- `CreateEvent` aufzurufen, Angeben von `true` für die `bManualReset` Argument.  
  
 In der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], können Sie die <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> Klasse für eine bessere Leistung, wenn die Wartezeiten voraussichtlich sehr kurz sind und das Ereignis nicht prozessübergreifend ist. <xref:System.Threading.ManualResetEventSlim>verwendet andauernde Spinvorgänge für kurze Zeit, während er darauf wartet, dass das Ereignis signalisiert wird. Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait-Handles. Jedoch, wenn das Ereignis nicht innerhalb eines bestimmten Zeitraums Zeit Signalisierung ist <xref:System.Threading.ManualResetEventSlim> Wait-Handle regulären Ereignisse neu sortiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait-Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore and SemaphoreSlim (Semaphore und SemaphoreSlim)](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
