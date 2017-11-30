---
title: "Datenstrukturen für die parallele Programmierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>Datenstrukturen für die parallele Programmierung
.NET Framework, Version 4 verschiedene neue Typen eingeführt werden, die in der parallelen Programmierung, darunter eine Gruppe von gleichzeitigen Auflistungsklassen, einfache Synchronisierungsprimitiven und Typen für verzögerte Initialisierung nützlich sind. Sie können diese Typen mit einer Multithreadanwendungscode, einschließlich der Task Parallel Library und PLINQ verwenden.  
  
## <a name="concurrent-collection-classes"></a>Gleichzeitigen Auflistungsklassen  
 Die Auflistungsklassen den <xref:System.Collections.Concurrent?displayProperty=nameWithType> Namespace bereit, Thread-sichere hinzufügen und Entfernen von Vorgängen, die Sperren möglichst zu vermeiden aus, und verwenden Sie die differenzierte Sperre, in denen Sperren erforderlich sind. Im Gegensatz zu Sammlungen, die in .NET Framework-Versionen 1.0 und 2.0 eingeführt wurden, erfordert gleichzeitigen Auflistungsklassen keine Benutzercode zu sperren, wenn sie Elemente zugreift. Die gleichzeitigen Auflistungsklassen können die Leistung erheblich verbessern über Typen wie z. B. <xref:System.Collections.ArrayList?displayProperty=nameWithType> und <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (mit Sperren Benutzer implementiert) in Szenarien, in denen mehrere Threads hinzufügen und Entfernen von Elementen aus einer Auflistung.  
  
 In der folgenden Tabelle sind die neuen gleichzeitigen Auflistungsklassen aufgeführt:  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Stellt Sperr- und Begrenzungsfunktionen für threadsichere Auflistungen bereit, die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> implementieren. Producerthreads blockiert, wenn keine Slots verfügbar sind oder wenn die Auflistung voll ist. Consumer Threads blockiert, wenn die Auflistung leer ist. Dieser Typ unterstützt auch nicht blockierend Zugriff durch Verbraucher und Hersteller. <xref:System.Collections.Concurrent.BlockingCollection%601>kann als Basisklasse verwendet werden oder Sicherungsspeicher bieten blockieren und für jede Auflistungsklasse, die unterstützt umgebende <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Eine Thread-sichere Behälter-Implementierung, die skalierbare bietet hinzufügen und get-Operationen.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Ein für parallele und skalierbare-Wörterbuchtyp.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Eine gleichzeitige und skalierbare FIFO-Warteschlange.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Ein gleichzeitiger und skalierbarer LIFO-Stapel.|  
  
 Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Synchronisierungsprimitiven  
 Die neue Synchronisierungsprimitiven in die <xref:System.Threading?displayProperty=nameWithType> Namespace ermöglichen eine differenzierte Parallelität und schnellere Leistung durch das Vermeiden der ressourcenintensive Sperrmechanismen in Legacycode multithreading. Einige neuen Typen, wie z. B. <xref:System.Threading.Barrier?displayProperty=nameWithType> und <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> gibt es keine Entsprechung in früheren Versionen von .NET Framework.  
  
 Die folgende Tabelle enthält die neue Synchronisierungstypen:  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Ermöglicht mehrere Threads arbeiten an einem Algorithmus parallel durch einen Punkt, an dem jeder Task signalisieren der Eingang und dann blockieren, bis einige oder alle Aufgaben angekommen sind kann, bereitstellen. Weitere Informationen finden Sie unter [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Vereinfacht die Zweig- und Joinknoten Szenarien durch eine einfache Rendezvous-Mechanismus. Weitere Informationen finden Sie unter [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Ein Synchronisierungsprimitiver, der ähnlich wie <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim>ist jedoch nur für die prozessinterne Kommunikation verwendet werden können. Weitere Informationen finden Sie unter [ManualResetEvent und ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Ein Synchronisierungsprimitiver, der die Anzahl der Threads, die gleichzeitig auf eine Ressource zugreifen können oder einen Pool von Ressourcen beschränkt. Weitere Informationen finden Sie unter [Semaphore und SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Ein gegenseitige Sperrprimitiven, die dem Thread, wodurch der versucht, der eine Sperre in einer Schleife wartet oder *Drehfeld*, für einen Zeitraum vor der Rückgabe sein Quantum. In Szenarien, in denen die Latenzzeit für die Sperre wird erwartet kurz <xref:System.Threading.SpinLock> bietet eine bessere Leistung als andere Arten von Sperren. Weitere Informationen finden Sie unter [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Ein kleiner, einfacher Typ, der rotiert wird innerhalb eines angegebenen Zeitraums und versetzt den Thread in einen Wartezustand versetzt, falls die Spinninganzahl überschritten wird.  Weitere Informationen finden Sie unter [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Weitere Informationen finden Sie unter:  
  
-   [Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [Vorgehensweise: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Verzögerte Initialisierung-Klassen  
 Bei einer verzögerten Initialisierung wird der Speicher für ein Objekt nicht zugeordnet, bis diese benötigt wird. Verzögerter Initialisierung kann die Leistung verbessern, indem gleichmäßig objektzuweisungen über die Lebensdauer eines Programms. Sie können die verzögerte Initialisierung für jeden benutzerdefinierten Typ aktivieren, indem Sie umschließt den Typ <xref:System.Lazy%601>.  
  
 Die folgende Tabelle enthält die Typen für verzögerte Initialisierung:  
  
|Typ|Beschreibung|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Stellt einfachen, Thread-sichere verzögerte Initialisierung bereit.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Jeder Thread verzögert-Aufrufen die Initialisierungsfunktion bietet einen verzögert initialisierten Wert auf der Grundlage einer pro Thread.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Stellt statische Methoden, die die Notwendigkeit, eine dedizierte Instanz verzögerte Initialisierung zuordnen zu vermeiden. Verwenden sie stattdessen Verweise, um sicherzustellen, dass Ziele initialisiert wurden, wie darauf zugegriffen wird.|  
  
 Weitere Informationen finden Sie unter [Verzögerte Initialisierung](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Aggregieren von Ausnahmen  
 Die <xref:System.AggregateException?displayProperty=nameWithType> -Typ kann verwendet werden, um mehrere Ausnahmen zu erfassen, die in separaten Threads gleichzeitig ausgelöst werden und an den Verbindungsthread als eine einzelne Ausnahme zurückzugeben. Die <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> verwenden Sie Typen und PLINQ <xref:System.AggregateException> sehr häufig zu diesem Zweck. Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Behandeln Ausnahmen, die von Aufgaben ausgelöste](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d) und [wie: Behandeln von Ausnahmen in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
