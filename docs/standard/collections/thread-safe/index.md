---
title: Threadsichere Auflistungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, overview
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
ms.openlocfilehash: 790543118b18b0422f41c3249512b62aae0cfb03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75938108"
---
# <a name="thread-safe-collections"></a>Threadsichere Auflistungen
Das .NET Framework 4 führt den <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace ein, der mehrere Auflistungsklassen einschließt, die sowohl threadsicher als auch skalierbar sind. Mehrere Threads können diesen Auflistungen sicher und effizient Elemente hinzufügen bzw. daraus entfernen, ohne dass zusätzliche Synchronisierung in Benutzercode erforderlich ist. Wenn Sie neuen Code schreiben, verwenden Sie immer dann die Klassen für parallele Auflistungsvorgänge, wenn mehrere Threads gleichzeitig Schreibvorgänge in der Auflistung ausführen. Wenn Sie nur von einer freigegebenen Auflistung lesen, können Sie die Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace verwenden. Es wird empfohlen, keine 1.0-Auflistungsklassen zu verwenden, sofern als Zielversion nicht .NET Framework 1.1 oder eine frühere Laufzeit festgelegt wird.  
  
## <a name="thread-synchronization-in-the-net-framework-10-and-20-collections"></a>Threadsynchronisierung in den Auflistungen von .NET Framework 1.0 und 2.0  
 Die in .NET Framework 1.0 eingeführten Auflistungen befinden sich im <xref:System.Collections?displayProperty=nameWithType>-Namespace. Diese Auflistungen, die das häufig verwendete <xref:System.Collections.ArrayList>-Objekt und das <xref:System.Collections.Hashtable>-Objekt einschließen, bieten eine gewisse Threadsicherheit durch die `Synchronized`-Eigenschaft, von der ein threadsicherer Wrapper um die Auflistung zurückgegeben wird. Der Wrapper funktioniert folgendermaßen: Die gesamte Auflistung wird bei jedem Hinzufüge- oder Entfernungsvorgang gesperrt. Daher muss jeder Thread, der versucht, auf die Auflistung zuzugreifen, warten, bis er die jeweilige Sperre übernehmen kann. Dies ist nicht skalierbar und kann beträchtliche Leistungseinbußen für große Auflistungen verursachen. Außerdem wird der Entwurf nicht völlig vor Racebedingungen geschützt. Weitere Informationen finden Sie im Blogbeitrag [Synchronization in Generic Collections (Synchronisierung in generischen Auflistungen)](https://docs.microsoft.com/archive/blogs/bclteam/synchronization-in-generic-collections-brian-grunkemeyer).  
  
 Die in .NET Framework 2.0 eingeführten Auflistungsklassen befinden sich im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace. Dazu gehören <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> usw. Diese Klassen bieten verbesserte Typsicherheit und Leistung im Vergleich zu den .NET Framework 1.0-Klassen. Die .NET Framework 2.0-Auflistungsklassen stellen jedoch keine Threadsynchronisierung bereit; Benutzercode muss die gesamte Synchronisierung bereitstellen, wenn Elemente gleichzeitig in mehreren Threads hinzugefügt oder entfernt werden.  
  
 Es wird empfohlen, die gleichzeitigen Auflistungsklassen im .NET Framework 4 zu verwenden, da sie nicht nur die Typsicherheit der .NET Framework 2.0-Auflistungsklassen, sondern auch eine effizientere und vollständigere Threadsicherheit als die Auflistungen von .NET Framework 1.0 bieten.  
  
## <a name="fine-grained-locking-and-lock-free-mechanisms"></a>Differenzierte Sperre und sperrenfreie Mechanismen  
 Einige der gleichzeitigen Auflistungstypen verwenden einfache Synchronisierungsmechanismen, z. B. <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim>, und <xref:System.Threading.CountdownEvent>, die neu im .NET Framework 4 sind. Diese Synchronisierungstypen verwenden normalerweise *andauernde Spinvorgänge* für die kurzen Zeiträume, bevor der Thread in einen echten Wartezustand versetzt wird. Wenn Wartezeiten als sehr kurz eingeschätzt werden, sind Spinvorgänge weitaus weniger rechenintensiv als Wartezustände, die einen aufwändigen Kernel-Übergang umfassen. Für Auflistungsklassen, für die Spinvorgänge verwendet werden, bedeutet diese Effizienz, dass mehrere Threads Elemente mit einer sehr hohen Rate hinzufügen und entfernen können. Weitere Informationen zu Spinvorgängen im Vergleich zu Blockierungen finden Sie unter [SpinLock](../../../../docs/standard/threading/spinlock.md) und [SpinWait](../../../../docs/standard/threading/spinwait.md).  
  
 Für die <xref:System.Collections.Concurrent.ConcurrentQueue%601>-Klasse und die <xref:System.Collections.Concurrent.ConcurrentStack%601>-Klasse werden gar keine Sperren verwendet. Stattdessen wird die Threadsicherheit durch <xref:System.Threading.Interlocked>-Vorgänge gewährleistet.  
  
> [!NOTE]
> Da die gleichzeitigen Auflistungsklassen <xref:System.Collections.ICollection> unterstützen, stellen sie Implementierungen für die <xref:System.Collections.ICollection.IsSynchronized%2A>-Eigenschaft und die <xref:System.Collections.ICollection.SyncRoot%2A>-Eigenschaft bereit, auch wenn diese Eigenschaften nicht relevant sind. `IsSynchronized` gibt immer `false` zurück, und `SyncRoot` ist immer `null` (`Nothing` in Visual Basic).  
  
 In der folgenden Tabelle sind die Auflistungstypen im <xref:System.Collections.Concurrent?displayProperty=nameWithType>-Namespace aufgeführt.  
  
|Geben Sie Folgendes ein:|Beschreibung|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|Stellt Begrenzungs- und Blockierungsfunktionen für jeden Typ bereit, von dem <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> implementiert wird. Weitere Informationen finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|Threadsichere Implementierung eines Wörterbuchs von Schlüssel-Wert-Paaren.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|Threadsichere Implementierung einer First In, First Out (FIFO)-Warteschlange.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|Threadsichere Implementierung eines Last In, First Out (LIFO)-Stapels.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|Threadsichere Implementierung einer ungeordneten Auflistung von Elementen.|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|Die Schnittstelle, die ein Typ implementieren muss, damit sie in `BlockingCollection` verwendet werden kann.|  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|Beschreibt die vom <xref:System.Collections.Concurrent.BlockingCollection%601>-Typ bereitgestellte Funktion.|  
|[Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einem ConcurrentDictionary](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|Beschreibt, wie Elemente aus einem <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekt hinzugefügt und entfernt werden.|  
|[Vorgehensweise: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|Beschreibt, wie Elemente einer Blockierungsauflistung hinzugefügt und daraus abgerufen werden, ohne dass der schreibgeschützte Enumerator verwendet wird.|  
|[Vorgehensweise: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Auflistung](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|Beschreibt, wie jede Auflistungsklasse als zugrunde liegender Speichermechanismus für eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>-Auflistung verwendet wird.|  
|[Vorgehensweise: Entfernen von Elementen in einer BlockingCollection mit ForEach](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|Beschreibt, wie mit einer `foreach`-Anweisung (`For Each` in Visual Basic) alle Elemente in einer Blockierungsauflistung entfernt werden.|  
|[Vorgehensweise: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|Beschreibt, wie mit mehreren Blockierungsauflistungen gleichzeitig eine Pipeline implementiert wird.|  
|[Vorgehensweise: Erstellen eines Objektpools mittels ConcurrentBag](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|Zeigt die Verwendung einer parallelen Sammlung zur Verbesserung der Leistung in Szenarien, in denen Sie Objekte nicht fortlaufend neu erstellen müssen, sondern diese wiederverwenden können.|  
  
## <a name="reference"></a>Verweis  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>
