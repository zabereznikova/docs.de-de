---
title: "EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], EventWaitHandle class"
  - "event wait handles [.NET Framework]"
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
Threads können mithilfe von Wait\-Handles für ein Ereignis Aktivitäten synchronisieren, indem sie einander Signale senden und auf die Signale der anderen Threads warten.  Diese Synchronisierungsereignisse beruhen auf Win32\-Wait\-Handles und untergliedern sich in zwei Typen: Ereignisse, die sich nach der Signalisierung automatisch zurücksetzen und Ereignisse, die manuell zurückgesetzt werden müssen.  
  
 Wait\-Handles für ein Ereignis sind in vielen Synchronisierungsszenarien nützlich, in denen auch die <xref:System.Threading.Monitor>\-Klasse eingesetzt wird.  Wait\-Handles für ein Ereignis können oft einfacher verwendet werden als die <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName>\-Methode und die <xref:System.Threading.Monitor.Pulse%2A?displayProperty=fullName>\-Methode und ermöglichen zudem eine bessere Steuerung der Signalisierungsvorgänge.  Mit benannten Wait\-Handles für ein Ereignis können Aktivitäten auch über Anwendungsdomänen und Prozesse hinweg synchronisiert werden, während Monitore nur lokal innerhalb einer Anwendungsdomäne eingesetzt werden können.  
  
## In diesem Abschnitt  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 Die <xref:System.Threading.EventWaitHandle>\-Klasse kann entweder automatische oder manuelle Zurücksetzungsereignisse sowie entweder lokale Ereignisse oder benannte Systemereignisse darstellen.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 Die <xref:System.Threading.AutoResetEvent>\-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das sich automatisch zurücksetzt.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 Die <xref:System.Threading.ManualResetEvent>\-Klasse ist von <xref:System.Threading.EventWaitHandle> abgeleitet und stellt ein lokales Ereignis dar, das manuell zurückgesetzt werden muss.  Die <xref:System.Threading.ManualResetEventSlim>\-Klasse ist eine einfache, schnellere Version, die für Ereignisse innerhalb des gleichen Prozesses verwendet werden kann.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 Die <xref:System.Threading.CountdownEvent>\-Klasse bietet eine vereinfachte Möglichkeit zum Implementieren von Verzweigung\/Join\-Parallelismusmustern in Code, in dem Wait\-Handle verwendet werden.  
  
## Verwandte Abschnitte  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 Die <xref:System.Threading.WaitHandle>\-Klasse ist die Basisklasse für die Klassen <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> und <xref:System.Threading.Mutex>.  Sie enthält statische Methoden wie <xref:System.Threading.WaitHandle.SignalAndWait%2A> und <xref:System.Threading.WaitHandle.WaitAll%2A>, die für die Verwendung von den verschiedenen Wait\-Handles nützlich sind.  
  
## Siehe auch  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)