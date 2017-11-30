---
title: Grundlagen des verwalteten Threadings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62c207f6074e33813887c6903f5285ee72d14e85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="managed-threading-basics"></a>Grundlagen des verwalteten Threadings
Die ersten fünf Themen in diesem Abschnitt sollen Sie bestimmen, wann die verwaltetes threading verwenden, und Erläutern Sie einige grundlegende Funktionen unterstützen. Informationen zu den Klassen, die zusätzliche Funktionen bereitstellen, finden Sie unter [Threading und-Features](../../../docs/standard/threading/threading-objects-and-features.md) und [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Der Rest der Themen in diesem Abschnitt behandeln die erweiterte Themen, einschließlich der Interaktion mit dem Windows-Betriebssystem verwaltetes threading.  
  
> [!NOTE]
>  In der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], geben Sie die Task Parallel Library und PLINQ APIs für Aufgabe und der Parallelität in Multithreaded-Programmen. Weitere Informationen finden Sie unter [Parallel Programming in the .NET Framework (Parallele Programmierung in .NET Framework)](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Threads and Threading (Threads und Threading)](../../../docs/standard/threading/threads-and-threading.md)  
 Erläutert die vor- und Nachteile von mehreren Threads und beschreibt die Szenarien, in denen Sie Threads erstellen oder Verwenden von Threads im Threadpool.  
  
 [Ausnahmen in verwalteten Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 Beschreibt das Verhalten der nicht behandelten Ausnahmen in Threads für verschiedene Versionen von .NET Framework, insbesondere bei die Situationen in die sie bei Beendigung der Anwendung führen.  
  
 [Datensynchronisierung für Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 Beschreibt Strategien zum Synchronisieren von Daten in Klassen, die mit mehreren Threads verwendet werden.  
  
 [Zustände von verwalteten Threads](../../../docs/standard/threading/managed-thread-states.md)  
 Beschreibt die grundlegenden Threadzustände und erklärt, wie zu ermitteln, ob ein Thread ausgeführt wird.  
  
 [Vordergrund- und Hintergrundthreads](../../../docs/standard/threading/foreground-and-background-threads.md)  
 Erläutert die Unterschiede zwischen Vordergrund-und Hintergrundthreads.  
  
 [Verwaltetes und nicht verwaltetes Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 Beschreibt die Beziehung zwischen verwalteten und nicht verwaltetes threading, verwaltete Entsprechungen für Windows-threading-APIs aufgelistet und die Interaktion von COM-Apartments und verwaltete Threads erläutert.  
  
 [Thread.Suspend, Garbage Collection und Sicherungspunkte](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 Beschreibt Thread anhalten und die Garbage Collection.  
  
 [Threadlokaler Speicher: Threadbezogene statische Felder und Datenslots](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 Beschreibt threadbezogene Speichermechanismen.  
  
 [Abbruch in verwalteten Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 Beschreibt die Funktionsweise der asynchronen oder lang andauernden synchrone Vorgängen kann durch Verwenden eines Abbruchtokens abgebrochen werden.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Threading.Thread>  
 Stellt die Referenzdokumentation für die **Thread**-Klasse bereit, die einen verwalteten Thread repräsentiert, und zwar unabhängig davon, ob er von nicht verwaltetem Code stammt oder in einer verwalteten Anwendung erstellt wurde.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Bietet eine sichere Möglichkeit zum Implementieren multithreading in Verbindung mit Benutzeroberflächenobjekten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Übersicht über Synchronisierungsprimitiven](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Beschreibt die verwalteten Klassen verwendet, um die Aktivitäten mehrerer Threads zu synchronisieren.  
  
 [Empfohlene Vorgehensweise für das verwaltete Threading](../../../docs/standard/threading/managed-threading-best-practices.md)  
 Beschreibt allgemeine Probleme mit multithreading und Strategien zur Vermeidung von Problemen.  
  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)  
 Beschreibt die Task Parallel Library und PLINQ, die asynchrone und mit mehreren Threads .NET Framework-Anwendungen erstellen erheblich vereinfachen.
