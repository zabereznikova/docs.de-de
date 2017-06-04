---
title: "CountdownEvent | Microsoft Docs"
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
  - "synchronization primitives, CountdownEvent"
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# CountdownEvent
<xref:System.Threading.CountdownEvent?displayProperty=fullName> ist ein Synchronisierungsgrundelement, für das die Blockierung der wartenden Threads aufgehoben wird, nachdem dies mehrfach signalisiert wurde.  <xref:System.Threading.CountdownEvent> wurde für Szenarios entworfen, in denen sonst ein <xref:System.Threading.ManualResetEvent> oder <xref:System.Threading.ManualResetEventSlim> verwendet und vor dem Signalisieren des Ereignisses manuell eine Variable dekrementiert werden müsste.  Zum Beispiel kann in einem Verzweigungs\-\/Verknüpfungsszenario nur ein <xref:System.Threading.CountdownEvent>\-Element mit einer Signalanzahl von 5 erstellt werden. Anschließend können fünf Arbeitsaufgaben im Threadpool gestartet werden, wobei für jede Arbeitsaufgabe bei deren Abschluss <xref:System.Threading.CountdownEvent.Signal%2A> aufgerufen werden kann.  Durch jeden Aufruf von <xref:System.Threading.CountdownEvent.Signal%2A> wird die Signalanzahl um 1 verringert.  Auf dem Hauptthread wird der Aufruf von <xref:System.Threading.CountdownEvent.Wait%2A> solange blockiert, bis die Signalanzahl 0 \(null\) beträgt.  
  
> [!NOTE]
>  Erwägen Sie für Code, der nicht mit älteren .NET Framework\-Synchronisierungs\-APIs interagieren muss, die Verwendung von <xref:System.Threading.Tasks.Task?displayProperty=fullName>\-Objekten oder der <xref:System.Threading.Tasks.Parallel.Invoke%2A>\-Methode, um Verzweigungs\-Verknüpfungs\-Parallelismus leichter ausdrücken zu können.  
  
 <xref:System.Threading.CountdownEvent> verfügt über diese zusätzlichen Funktionen:  
  
-   Der Wartevorgang kann mit Abbruchtokens abgebrochen werden.  
  
-   Seine Signalanzahl kann nach der Erstellung der Instanz erhöht werden.  
  
-   Instanzen können nach der Rückgabe von <xref:System.Threading.CountdownEvent.Wait%2A> durch den Aufruf der <xref:System.Threading.CountdownEvent.Reset%2A>\-Methode wiederverwendet werden.  
  
-   Instanzen stellen ein <xref:System.Threading.WaitHandle> für die Integration in andere .NET Framework\-Synchronisierungs\-APIs, wie z. B. <xref:System.Threading.WaitHandle.WaitAll%2A>, bereit.  
  
## Grundlegende Verwendung  
 Das folgende Beispiel veranschaulicht die Verwendung eines <xref:System.Threading.CountdownEvent>\-Elements mit <xref:System.Threading.ThreadPool>\-Arbeitsaufgaben.  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## CountdownEvent mit Abbruch  
 Das folgende Beispiel veranschaulicht, wie der Wartevorgang für <xref:System.Threading.CountdownEvent> mit einem Abbruchtoken abgebrochen wird.  Das grundlegende Muster folgt dem Modell für einheitlichen Abbruch, der in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] eingeführt wird.  Weitere Informationen finden Sie unter [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 Beachten Sie, dass vom Wartevorgang nicht die Threads abgebrochen werden, die den Wartevorgang signalisieren.  In der Regel wird eine logische Operation abgebrochen. Hierzu zählen das Warten auf das Ereignis sowie alle Arbeitsaufgaben, die vom Wartevorgang synchronisiert werden.  In diesem Beispiel wird jeder Arbeitsaufgabe eine Kopie des gleichen Abbruchtokens übergeben, damit auf die Abbruchanforderung reagiert werden kann.  
  
## Siehe auch  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)