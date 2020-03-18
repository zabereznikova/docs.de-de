---
title: Datenstrukturen für die parallele Programmierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
ms.openlocfilehash: a2271feae78100940b4ecac3c42c9bfefa7e1769
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123149"
---
# <a name="data-structures-for-parallel-programming"></a>Datenstrukturen für die parallele Programmierung
.NET Framework Version 4 führt mehrere neue Typen ein, die für die parallele Programmierung nützlich sind. Darunter eine Reihe von parallelen Auflistungsklassen, einfache Synchronisierungsprimitiven und Typen für die verzögerte Initialisierung. Sie können diese Typen mit jedem Multithreadanwendungscode verwenden, einschließlich der Task Parallel Library und PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Parallele Auflistungsklassen  
 Die Auflistungsklassen im Namespace <xref:System.Collections.Concurrent?displayProperty=nameWithType> bieten threadsichere Vorgänge für das Hinzufügen und Entfernen. Diese vermeiden Sperren, wo immer dies möglich ist, und setzen differenzierte Sperren ein, wenn Sperren erforderlich sind. Im Gegensatz zu Auflistungen, die in den .NET Framework-Versionen 1.0 und 2.0 eingeführt wurden, benötigt die parallele Auflistungsklasse keinen Benutzercode, um beim Zugriff auf Elemente Sperren zu akzeptieren. Die parallelen Auflistungsklassen können die Leistung gegenüber Typen wie <xref:System.Collections.ArrayList?displayProperty=nameWithType> und <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (mit benutzerimplementierter Sperre) in Szenarien, in denen mehrere Threads Elemente aus einer Auflistung hinzufügen und entfernen, erheblich verbessern.  
  
 In der folgenden Tabelle sind die neuen parallelen Auflistungsklassen aufgeführt:  
  
|Geben Sie Folgendes ein:|Beschreibung|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Stellt Sperr- und Begrenzungsfunktionen für threadsichere Auflistungen bereit, die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> implementieren. Producerthreads werden blockiert, wenn keine Zeitfenster verfügbar sind oder wenn die Auflistung voll ist. Consumerthreads werden blockiert, wenn die Auflistung leer ist. Dieser Typ unterstützt auch nicht blockierenden Zugriff durch Consumer und Producer. <xref:System.Collections.Concurrent.BlockingCollection%601> kann als Basisklasse oder Sicherungsspeicher verwendet werden, um das Blockieren und Binden für jede Auflistungsklasse zu ermöglichen, die <xref:System.Collections.Generic.IEnumerable%601> unterstützt.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Eine threadsichere Behälterimplementierung, die skalierbare Vorgänge zum Hinzufügen und Abrufen bietet.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Ein paralleler und skalierbarer Wörterbuchtyp|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Eine parallele und skalierbare FIFO-Warteschlange|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Ein paralleler und skalierbarer LIFO-Stapel|  
  
 Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Synchronisierungsprimitiven  
 Die neuen Synchronisierungsprimitiven im <xref:System.Threading?displayProperty=nameWithType>-Namespace ermöglichen eine differenzierte Parallelität und schnellere Leistung durch das Vermeiden ressourcenintensiver Sperrmechanismen in Legacy-Multithreadingcode. Für einige neuen Typen, wie z.B. <xref:System.Threading.Barrier?displayProperty=nameWithType> und <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> gibt es in früheren Versionen von .NET Framework keine Entsprechung.  
  
 Die folgende Tabelle enthält die neuen Synchronisierungstypen:  
  
|Geben Sie Folgendes ein:|Beschreibung|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Ermöglicht mehreren Threads, parallel an einem Algorithmus zu arbeiten, indem ein Punkt bereitgestellt wird, an dem jeder Task seine Ankunft signalisieren und dann blockieren kann, bis einige oder alle Tasks angekommen sind. Weitere Informationen finden Sie unter [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Vereinfacht Fork- und Join-Szenarien durch einen einfachen Rendezvousmechanismus. Weitere Informationen finden Sie unter [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Eine Synchronisierungsprimitive, ähnlich wie <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim> ist einfacher, kann aber nur für prozessinterne Kommunikation verwendet werden.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Eine Synchronisierungsprimitive, die die Anzahl von Threads beschränkt, die parallel auf eine Ressource oder einen Ressourcenpool zugreifen können. Weitere Informationen finden Sie unter [Semaphore und SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Eine gegenseitige Ausschlusssperrprimitive, durch die der Thread, der die Sperre zu erlangen versucht, für eine gewisse Zeit in einer Schleife warten (oder *rotieren*) muss, bevor er sein Quantum liefert. In Szenarien, in denen die Wartezeit für die Sperre nur kurz ist, bietet <xref:System.Threading.SpinLock> eine bessere Leistung als andere Arten von Sperren. Weitere Informationen finden Sie unter [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Ein kleiner, einfacher Typ, der für eine bestimmte Zeit rotiert und schließlich den Thread in einen Wartezustand versetzt, wenn die Schleifenzahl überschritten wird.  Weitere Informationen finden Sie unter [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Weitere Informationen finden Sie unter:  
  
- [Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
- [Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)  
  
## <a name="lazy-initialization-classes"></a>Klassen mit verzögerter Initialisierung  
 Bei einer verzögerten Initialisierung wird der Speicher für ein Objekt nicht zugewiesen, bis dieser benötigt wird. Eine verzögerte Initialisierung kann zur Verbesserung der Leistung beitragen, indem Objektzuweisungen über die Lebensdauer eines Programms hinweg verteilt werden. Sie können die verzögerte Initialisierung für jeden benutzerdefinierten Typ verwenden, indem Sie damit den Typ <xref:System.Lazy%601> umschließen.  
  
 Die folgende Tabelle enthält eine Auflistung der Typen für eine verzögerte Initialisierung:  
  
|Geben Sie Folgendes ein:|Beschreibung|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Stellt einfache, threadsichere verzögerte Initialisierung bereit.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Stellt einen Wert durch eine verzögerte Initialisierung auf Threadbasis bereit, wobei jeder Thread die Initialisierungsfunktion verzögert aufruft.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Stellt statische Methoden bereit, durch die das Zuweisen einer dedizierten Instanz für die verzögerte Initialisierung nicht mehr erforderlich ist. Stattdessen werden Verweise eingesetzt, um sicherzustellen, dass Ziele initialisiert werden, sobald darauf zugegriffen wird.|  
  
 Weitere Informationen finden Sie unter [Verzögerte Initialisierung](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Aggregieren von Ausnahmen  
 Die <xref:System.AggregateException?displayProperty=nameWithType>-Typ kann verwendet werden, um mehrere Ausnahmen zu erfassen, die in separaten Threads parallel ausgelöst und an den Verbindungsthread als eine einzelne Ausnahme zurückgegeben werden. Die Typen <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> sowie PLINQ verwenden hierzu sehr häufig <xref:System.AggregateException>. Weitere Informationen finden Sie unter [Ausnahmebehandlung](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md) und unter [Vorgehensweise: Behandeln von Ausnahmen in einer PLINQ-Abfrage](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- <xref:System.Threading?displayProperty=nameWithType>
- [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)
