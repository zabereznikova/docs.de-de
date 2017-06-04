---
title: "Managed Threading Basics | Microsoft Docs"
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
  - "multiple threads"
  - "threading [.NET Framework], multiple threads"
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Managed Threading Basics
In den ersten fünf Themen dieses Abschnitts wird erläutert, in welchen Situationen Sie verwaltetes Threading verwenden können. Außerdem werden einige grundlegende Features erklärt.  Informationen zu Klassen, die zusätzliche Features bereitstellen, finden Sie unter [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) und unter [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Die übrigen Themen in diesem Abschnitt behandeln weiterführende Themen wie die Interaktion von verwaltetem Threading mit dem Windows\-Betriebssystem.  
  
> [!NOTE]
>  Im [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellen die Task Parallel Library und PLINQ APIs für Aufgaben und Datenparallelismus in Multithreadprogrammen bereit.  Weitere Informationen finden Sie unter [Parallel Programming](../../../docs/standard/parallel-programming/index.md).  
  
## In diesem Abschnitt  
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)  
 Erläutert die Vor\- und Nachteile von mehrfachen Threads und skizziert die Szenarien, in denen Sie Threads erstellen oder Threadpoolthreads verwenden können.  
  
 [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Beschreibt für verschiedene Versionen von .NET Framework das Verhalten von unbehandelten Ausnahmen in Threads, insbesondere in den Situationen, in denen sie zum Beenden der Anwendung führen.  
  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.  
  
 [Zustände von verwalteten Threads](../../../docs/standard/threading/managed-thread-states.md)  
 Beschreibt die grundlegenden Threadzustände und erklärt, wie sich ermitteln lässt, ob ein Thread ausgeführt wird.  
  
 [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Beschreibt die Unterschiede zwischen Vordergrund\- und Hintergrundthreads.  
  
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Erläutert die Beziehung zwischen verwaltetem und nicht verwaltetem Threading, führt verwaltete Entsprechungen für Windows\-Threading\-APIs auf und behandelt die Interaktion von COM\-Apartments und verwalteten Threads.  
  
 [Thread.Suspend, Garbage Collection, and Safe Points](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Beschreibt die Unterbrechung von Threads und die Garbage Collection.  
  
 [Thread Local Storage: Thread\-Relative Static Fields and Data Slots](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Beschreibt threadbezogene Speichermechanismen.  
  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Beschreibt, wie asynchrone Vorgänge oder synchrone Vorgänge mit langer Laufzeit mithilfe eines Abbruchtokens abgebrochen werden können.  
  
## Referenz  
 <xref:System.Threading.Thread>  
 Referenzdokumentation für die **Thread**\-Klasse, die einen verwalteten Thread unabhängig davon repräsentiert, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Bietet ein sicheres Verfahren zum Implementieren von Multithreading in Verbindung mit Benutzeroberflächenobjekten.  
  
## Verwandte Abschnitte  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Beschreibt die verwalteten Klassen, mit denen die Aktivitäten mehrerer Threads synchronisiert werden.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Beschreibt allgemeine Probleme mit Multithreading und Vermeidungsstrategien.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 Beschreibt die Task Parallel Library und PLINQ, mit denen die Arbeit für das Erstellen von asynchronen und Multithread\-.NET Framework\-Anwendungen erheblich vereinfacht wird.