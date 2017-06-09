---
title: "ManualResetEvent and ManualResetEventSlim | Microsoft Docs"
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
  - "threading [.NET Framework], ManualResetEvent class"
  - "ManualResetEvent class, about ManualResetEvent class"
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# ManualResetEvent and ManualResetEventSlim
Die <xref:System.Threading.ManualResetEvent?displayProperty=fullName>\-Klasse stellt ein lokales WaitHandle\-Ereignis dar, das nach seiner Auslösung manuell zurückgesetzt werden muss.  Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle?displayProperty=fullName> dar.  Weitere Informationen zur Verwendung und den Features manueller Reset\-Ereignisse finden Sie in der konzeptionellen Dokumentation über [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.ManualResetEvent>\-Objekt bleibt bis zum Aufruf der <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=fullName>\-Methode aktiviert.  Während der Zustand des Objekts signalisiert wird, können beliebig viele wartende Threads oder Threads, die nach der Signalisierung auf das Ereignis warten, freigegeben werden.  <xref:System.Threading.ManualResetEvent> entspricht einem Win32\-`CreateEvent`\-Aufruf, bei dem `true` als `bManualReset`\-Argument angegeben wird.  
  
 In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] können Sie die <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> \- Klasse eine bessere Leistung verwenden, wenn die Wartezeiten, sehr kurz eingeschätzt werden und das Ereignis nicht prozessübergreifend ist.  verwendet <xref:System.Threading.ManualResetEventSlim> vorübergehend andauernde Spinvorgänge kurze Zeit, während er auf das Ereignis wartet, die signalisiert werden.  Bei kurzen Wartezeiten können Spinvorgänge sehr viel weniger ressourcenintensiv sein als das Warten mit Wait\-Handles.  Wenn das Ereignis jedoch nicht innerhalb eines bestimmten Zeitraums signalisiert wird, greift <xref:System.Threading.ManualResetEventSlim> auf einen normalen Wartevorgang mit Ereignishandle zurück.  
  
## Siehe auch  
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)