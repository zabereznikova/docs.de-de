---
title: "Threading Objects and Features | Microsoft Docs"
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
  - "threading [.NET Framework], features"
  - "managed threading"
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Threading Objects and Features
.NET Framework stellt eine Reihe von Objekten bereit, mit denen Sie Multithreadanwendungen erstellen und verwalten können.  Verwaltete Threads werden durch die <xref:System.Threading.Thread>\-Klasse repräsentiert.  Die <xref:System.Threading.ThreadPool>\-Klasse ermöglicht eine einfache Erstellung und Verwaltung von Multithreaded\-Hintergrundaufgaben.  Die <xref:System.ComponentModel.BackgroundWorker>\-Klasse erfüllt den gleichen Zweck für Aufgaben, die mit der Benutzeroberfläche interagieren.  Die <xref:System.Threading.Timer> \-Klasse führt Hintergrundaufgaben in festgelegten Intervallen aus.  
  
 Darüber hinaus gibt es eine Reihe von Klassen, die Aktivitäten von Threads synchronisieren. Dazu zählen auch die <xref:System.Threading.Semaphore>\- und <xref:System.Threading.EventWaitHandle>\-Klasse, die in .NET Framework 2.0 eingeführt wurden.  Die Funktionen dieser Klassen werden im Artikel [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md) miteinander verglichen.  
  
## In diesem Abschnitt  
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Erläutert die **ThreadPool** \-Klasse, mit der Sie einen Thread zum Ausführen einer Aufgabe anfordern können, ohne den Thread in irgendeiner Form selbst verwalten zu müssen.  
  
 [Timers](../../../docs/standard/threading/timers.md)  
 Hier wird erläutert, wie Sie mit einem **Timer** einen Delegaten angeben, der zu einer bestimmten Zeit aufgerufen werden soll.  
  
 [Monitore](../Topic/Monitors.md)  
 Erläutert, wie die **Monitor**\-Klasse zum Synchronisieren des Zugriffs auf ein Member oder zum Erstellen eigener Threadverwaltungsarten verwendet wird.  
  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 Beschreibt die <xref:System.Threading.WaitHandle>\-Klasse, die abstrakte Basisklasse für Event\-Wait\-Handles, Mutexe und Semaphoren, welche die Wartefunktion für mehrere Synchronisierungsereignisse ermöglicht.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 Beschreibt verwaltete Event\-Wait\-Handles, die signalisieren und auf Signale warten und zum Synchronisieren von Threadaktivitäten verwendet werden.  
  
 [Mutexes](../../../docs/standard/threading/mutexes.md)  
 Erläutert, wie ein <xref:System.Threading.Mutex>zum Synchronisieren des Zugriffs auf ein Objekt oder zum Erstellen eigener Synchronisierungsmechanismen verwendet wird.  
  
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)  
 Erläutert, wie mit der <xref:System.Threading.Interlocked>\-Klasse ein Wert in einem einzigen Vorgang erhöht oder verringert und gleichzeitig gespeichert wird.  
  
 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)  
 Definiert eine Sperre, die eine Semantik implementiert, die nur einen Schreibvorgang, aber mehrere Lesevorgänge gleichzeitig zulässt.  
  
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 Beschreibt <xref:System.Threading.Semaphore>\-Objekte und erläutert, wie diese zum Steuern des Zugriffs auf begrenzte Ressourcen verwendet werden.  
  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Vergleicht die Funktionen von .NET Framework\-Klassen, die zum Sperren und Synchronisieren verwalteter Threads zur Verfügung stehen.  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 Beschreibt <xref:System.Threading.Barrier>\-Objekte, die das Barrieremuster für die Koordination von Threads in stufenweise durchgeführten Vorgängen implementieren.  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 Beschreibt <xref:System.Threading.SpinLock>, eine einfache Alternative zur Monitor\-Klasse für bestimmte Low\-Level\-Szenarien.  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 Beschreibt <xref:System.Threading.SpinWait>, einen Low\-Level\-Synchronisierungsprimitiven, der vor dem Initiieren eines kernelbasierten Wartevorgangs Spinvorgänge ausführt.  
  
## Referenz  
 <xref:System.Threading.Thread>  
 Stellt die Referenzdokumentation für die **Thread**\-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Aktiviert Hintergrundaufgaben, die mit der Benutzeroberfläche interagieren und über Ereignisse kommunizieren, die auf dem Benutzeroberflächenthread ausgelöst wurden.  
  
## Verwandte Abschnitte  
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)  
 Beschreibt, wie asynchrone E\/A\-Abschlussports den Threadpool verwenden, um die Verarbeitung nur bei Abschluss eines E\/A\-Vorgangs anzufordern.  
  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Beschreibt die empfohlene Vorgehensweise bei der Multithreadprogrammierung in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und höher.