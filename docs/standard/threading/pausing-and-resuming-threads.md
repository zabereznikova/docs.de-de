---
title: "Pausing and Resuming Threads | Microsoft Docs"
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
  - "resuming threads"
  - "threading [.NET Framework], pausing"
  - "pausing threads"
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Pausing and Resuming Threads
Die gängigsten Verfahren zum Synchronisieren der Aktivitäten von Threads bestehen darin, Threads zu blockieren und freizugeben bzw. Objekte oder Codebereiche zu sperren.  Weitere Informationen zu diesen Sperr\- und Blockierungsmechanismen finden Sie unter [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Sie können auch vorsehen, dass Threads sich selbst deaktivieren \(in den Standbymodus versetzen\).  Wenn Threads blockiert oder deaktiviert sind, können Sie sie mit einer <xref:System.Threading.ThreadInterruptedException> wieder aus ihrem Wartezustand holen.  
  
## Die "Thread.Sleep"\-Methode  
 Durch Aufrufen der <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>\-Methode wird der aktuelle Thread sofort für die in Millisekunden angegebene Dauer blockiert, die Sie an <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> übergeben, wobei der restliche Zeitanteil dieses Threads einem anderen Thread zur Verfügung gestellt wird.  Ein Thread kann <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> nicht für einen anderen Thread aufrufen.  
  
 Durch den Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> mit <xref:System.Threading.Timeout.Infinite?displayProperty=fullName> bleibt ein Thread so lange deaktiviert \(im Standbymodus\), bis er von einem anderen Thread unterbrochen wird, der <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> aufruft, oder bis er durch <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> beendet wird.  
  
## Unterbrechen von Threads  
 Sie können einen wartenden Thread unterbrechen, indem Sie <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> für den blockierten Thread aufrufen, um eine <xref:System.Threading.ThreadInterruptedException> auszulösen, durch die der Thread aus dem blockierenden Aufruf gelöst wird.  Der Thread sollte die <xref:System.Threading.ThreadInterruptedException> abfangen und die angemessenen Aktionen zum Fortsetzen der Arbeit ausführen.  Wenn der Thread die Ausnahme ignoriert, wird diese von der Laufzeit abgefangen, und der Thread wird beendet.  
  
> [!NOTE]
>  Wenn der Zielthread beim Aufrufen von <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> nicht blockiert ist, muss er zuerst blockiert werden, bevor er unterbrochen werden kann.  Wenn der Thread nie blockiert wird, kann er ohne jegliche Unterbrechung abgeschlossen werden.  
  
 Wenn sich ein Thread in einem verwalteten Wartezustand befindet, kann er durch <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> und <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> sofort aktiviert werden.  Bei einem nicht verwalteten Wartezustand \(beispielsweise bei einem Plattformaufruf der `WaitForSingleObject`Win32\-Funktion\) können <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> und <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> die Steuerung des Threads erst übernehmen, wenn der Thread zu verwaltetem Code zurückkehrt oder einen Aufruf in verwaltetem Code ausführt.  In verwaltetem Code sieht das Verhalten wie folgt aus:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> aktiviert einen Thread aus jedem Wartezustand heraus und veranlasst, dass eine <xref:System.Threading.ThreadInterruptedException> im Zielthread ausgelöst wird.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> ist mit <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> vergleichbar, außer dass dabei eine <xref:System.Threading.ThreadAbortException> für den Thread ausgelöst wird.  Ausführliche Informationen finden Sie unter [Zerstören von Threads](../../../docs/standard/threading/destroying-threads.md).  
  
## Unterbrechen und Fortsetzen \(veraltet\)  
 Die <xref:System.Threading.Thread>\-Klasse enthält zwei Methoden \(<xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> und <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>\) zum Anhalten und Fortsetzen eines Threads.  Die Verwendung dieser Methoden wird jedoch nicht empfohlen.  
  
> [!IMPORTANT]
>  Ab .NET Framework 2.0 sind die Methoden <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> und <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> als veraltet markiert, und sie werden in einer der nächsten Versionen entfernt.  
>   
>  Die <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>\-Methode und die <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>Methode sind nicht generell für alle Anwendungen sinnvoll und dürfen nicht mit Synchronisierungsmechanismen verwechselt werden.  Da <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> und <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> nicht auf die Kooperation mit dem gesteuerten Thread angewiesen sind, gelten sie als sehr intrusiv. Dadurch können ernsthafte Anwendungsprobleme wie Deadlocks entstehen \(wenn Sie beispielsweise einen Thread anhalten, der eine von einem anderen Thread benötigte Ressource enthält\).  
  
 Bei einigen Anwendungen muss die Priorität von Threads gesteuert werden, um eine bessere Leistung zu ermöglichen.  Verwenden Sie zu diesem Zweck die <xref:System.Threading.Thread.Priority%2A?displayProperty=fullName>\-Eigenschaft anstelle von <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadInterruptedException>   
 <xref:System.Threading.ThreadAbortException>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)