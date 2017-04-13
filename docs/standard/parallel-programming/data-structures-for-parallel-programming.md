---
title: "Data Structures for Parallel Programming | Microsoft Docs"
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
  - "data structures, multi-threading"
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Data Structures for Parallel Programming
Mit .NET Framework 4 wurden verschiedene neue Typen eingeführt, die in der parallelen Programmierung hilfreich sind, einschließlich einer Gruppe gleichzeitiger Auflistungsklassen, einfache Synchronisierungsprimitiven und Typen für eine verzögerte Initialisierung.  Sie können diese Typen mit jedem Multithreadanwendungscode verwenden, einschließlich der Task Parallel Library und PLINQ.  
  
## Gleichzeitige Auflistungsklassen  
 Die Auflistungsklassen im <xref:System.Collections.Concurrent?displayProperty=fullName>\-Namespace ermöglichen ein threadsicheres Hinzufügen und Entfernen, bei dem Sperren nach Möglichkeit vermieden und, falls erforderlich, differenzierte Sperren verwendet werden.  Im Gegensatz zu Auflistungen, die in .NET Framework 1.0 und 2.0 eingeführt wurden, ist es bei einer gleichzeitigen Auflistungsklasse nicht erforderlich, dass der Benutzercode beim Zugriff auf Elemente Sperren vornimmt.  Gleichzeitige Auflistungsklassen führen im Vergleich zu Typen wie <xref:System.Collections.ArrayList?displayProperty=fullName> und <xref:System.Collections.Generic.List%601?displayProperty=fullName> \(mit vom Benutzer implementierten Sperren\) zu einer deutlichen Leistungssteigerung in Szenarien, in denen mehrere Threads Elemente zu einer Auflistung hinzufügen bzw. Elemente daraus entfernen.  
  
 In der folgenden Tabelle sind die neuen gleichzeitigen Auflistungsklassen aufgeführt:  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>|Stellt Sperr\- und Begrenzungsfunktionen für threadsichere Auflistungen bereit, die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> implementieren.  Producerthreads werden gesperrt, wenn keine Slots verfügbar sind oder die Auflistung voll ist.  Consumerthreads werden gesperrt, wenn die Auflistung leer ist.  Dieser Typ unterstützt auch einen ungesperrten Zugriff durch Consumer und Producer.  <xref:System.Collections.Concurrent.BlockingCollection%601> kann als Basisklasse oder Sicherungsspeicher verwendet werden, um Sperren und Begrenzungen für eine beliebige Auflistungsklasse bereitzustellen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützt.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>|Eine threadsichere Sammlungsimplementierung, die skalierbare Hinzufügungs\- und Abrufvorgänge bereitstellt.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>|Ein gleichzeitiger und skalierbarer Wörterbuchtyp.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>|Eine gleichzeitige und skalierbare FIFO\-Warteschlange.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>|Ein gleichzeitiger und skalierbarer LIFO\-Stapel.|  
  
 Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
## Synchronisierungsprimitiven  
 Die neuen Synchronisierungsprimitiven im <xref:System.Threading?displayProperty=fullName>\-Namespace ermöglichen eine differenzierte Parallelität und höhere Leistung, indem ressourcenintensive Sperrmechanismen vermieden werden, die in veraltetem Multithreadingcode häufig vorkommen.  Für einige neue Typen, wie z. B. <xref:System.Threading.Barrier?displayProperty=fullName> und <xref:System.Threading.CountdownEvent?displayProperty=fullName>, gibt es in früheren Versionen von .NET Framework keine Entsprechung.  
  
 In der folgenden Tabelle werden die neuen Synchronisierungstypen aufgeführt:  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|<xref:System.Threading.Barrier?displayProperty=fullName>|Ermöglicht, dass mehrere Threads einen Algorithmus parallel verarbeiten. Hierzu wird ein Punkt definiert, an dem jede Aufgabe ihre Ankunft signalisieren kann und dann gesperrt wird, bis einige oder alle Aufgaben an diesem Punkt angelegt sind.  Weitere Informationen finden Sie unter [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=fullName>|Vereinfacht Gabelungs\- und Verknüpfungsszenarios \(Fork & Join\), indem ein einfacher Rendezvousmechanismus bereitgestellt wird.  Weitere Informationen finden Sie unter [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>|Eine Synchronisierungsprimitive ähnlich <xref:System.Threading.ManualResetEvent?displayProperty=fullName>.  <xref:System.Threading.ManualResetEventSlim> ist einfacher aufgebaut, kann jedoch nur für die prozessinterne Kommunikation verwendet werden.  Weitere Informationen finden Sie unter [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=fullName>|Eine Synchronisierungsprimitive, die die Anzahl der Threads beschränkt, die gleichzeitig auf eine Ressource oder einen Ressourcenpool zugreifen können.  Weitere Informationen finden Sie unter [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=fullName>|Ein Primitive für eine gegenseitige Ausschlusssperre, durch die der Thread, der die Sperre erhalten möchte, für einen bestimmten Zeitraum in einer Schleife wartet oder *rotiert*, bevor er seinen Anteil erhält.  In Szenarios, in denen voraussichtlich nur kurz auf eine Sperre gewartet werden muss, bietet <xref:System.Threading.SpinLock> eine bessere Leistung als andere Arten von Sperren.  Weitere Informationen finden Sie unter [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=fullName>|Ein kleiner, einfacher Typ, der für einen bestimmten Zeitraum rotiert und den Thread ggf. in einen Wartezustand versetzt, wenn die Anzahl der Rotationen überschritten wurde.  Weitere Informationen finden Sie unter [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Weitere Informationen finden Sie unter:  
  
-   [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## Verzögerte Initialisierungsklassen  
 Bei einer verzögerten Initialisierung wird der Speicher für ein Objekt erst zugeordnet, wenn er benötigt wird.  Die verzögerte Initialisierung kann die Leistung erhöhen, indem Objektzuordnungen gleichmäßig über der Lebensdauer eines Programms verteilt werden.  Sie können die verzögerte Initialisierung für einen beliebigen benutzerdefinierten Typ aktivieren, indem Sie den <xref:System.Lazy%601>\-Typ einschließen.  
  
 In der folgenden Tabelle werden die Typen der verzögerten Initialisierung aufgeführt:  
  
|Typ|**Beschreibung**|  
|---------|----------------------|  
|<xref:System.Lazy%601?displayProperty=fullName>|Stellt eine einfache, threadsichere verzögerte\-Initialisierung bereit.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=fullName>|Stellt pro Thread einen verzögert initialisierten Wert bereit, wobei jeder Thread die Initialisierungsfunktion verzögert aufruft.|  
|<xref:System.Threading.LazyInitializer?displayProperty=fullName>|Stellt statische Methoden bereit, durch die keine dedizierte Instanz mit verzögerter Initialisierung zugeordnet werden muss.  Stattdessen werden Verweise verwendet, um beim Zugriff auf Ziele sicherzustellen, dass diese initialisiert wurden.|  
  
 Weitere Informationen finden Sie unter [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Aggregieren von Ausnahmen  
 Mit dem <xref:System.AggregateException?displayProperty=fullName>\-Typ können mehrere Ausnahmen, die gleichzeitig in separaten Threads ausgelöst werden, erfasst und als eine Ausnahme an den Verbindungsthread zurückgegeben werden.  Die <xref:System.Threading.Tasks.Task?displayProperty=fullName>\- und <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>\-Typen und PLINQ setzen <xref:System.AggregateException> zu diesem Zweck umfassend ein.  Weitere Informationen finden Sie unter [NIB: How to: Handle Exceptions Thrown by Tasks](http://msdn.microsoft.com/de-de/d6c47ec8-9de9-4880-beb3-ff19ae51565d) und [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 <xref:System.Threading?displayProperty=fullName>   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)