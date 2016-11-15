---
title: Threadsichere Auflistungen
description: Threadsichere Auflistungen
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 92d5515d-f5d6-4a09-8bbb-31865d678643
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 421d46585b5d83f5772fa6596ad581c8c6acbf71

---

# <a name="threadsafe-collections"></a>Threadsichere Auflistungen

Der [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace umfasst mehrere Auflistungsklassen, die sowohl threadsicher als auch skalierbar sind. Mehrere Threads können diesen Auflistungen sicher und effizient Elemente hinzufügen bzw. daraus entfernen, ohne dass zusätzliche Synchronisierung in Benutzercode erforderlich ist. Wenn Sie neuen Code schreiben, verwenden Sie die gleichzeitigen Auflistungsklassen, wenn von der Auflistung gleichzeitig Elemente in mehrere Threads geschrieben werden. Wenn Sie nur aus einer freigegebenen Auflistung lesen, können Sie die Klassen im [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)-Namespace verwenden. Es wird empfohlen, keine [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Auflistungsklassen zu verwenden, sofern als Zielversion nicht die .NET Framework 1.1-Runtime oder früher erforderlich ist.

## <a name="finegrained-locking-and-lockfree-mechanisms"></a>Differenzierte Sperre und sperrenfreie Mechanismen

Einige der gleichzeitigen Auflistungstypen verwenden einfache Synchronisierungsmechanismen z.B. [SpinLock](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinLock), [SpinWait](https://docs.microsoft.com/dotnet/core/api/System.Threading.SpinWait), [SemaphoreSlim](https://docs.microsoft.com/dotnet/core/api/System.Threading.SemaphoreSlim) und [CountdownEvent](https://docs.microsoft.com/dotnet/core/api/System.Threading.CountdownEvent). Diese Synchronisierungstypen verwenden normalerweise für einen kurzen Zeitraum Verzögerungsschleifen, bevor der Thread in einen echten `Wait`-Zustand versetzt wird. Wenn Wartezeiten als sehr kurz eingeschätzt werden, sind Spinvorgänge weitaus weniger rechenintensiv als Wartezustände, die einen aufwändigen Kernel-Übergang umfassen. Für Auflistungsklassen, für die Spinvorgänge verwendet werden, bedeutet diese Effizienz, dass mehrere Threads Elemente mit einer sehr hohen Rate hinzufügen und entfernen können.

Die Klassen [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) und [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) verwenden überhaupt keine Sperren. Stattdessen wird die Threadsicherheit durch Interlocked-Vorgänge gewährleistet.

> [!NOTE]
> Da die gleichzeitigen Auflistungsklassen [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection) unterstützen, stellen sie Implementierungen für die Eigenschaften `IsSynchronized` und `SyncRoot` bereit, auch wenn diese Eigenschaften nicht relevant sind. `IsSynchronized` gibt immer `false` zurück, und `SyncRoot` ist immer Null.

In der folgenden Tabelle sind die Auflistungstypen im [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace aufgeführt.

Typ | Beschreibung
---- | -----------
[BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) | Stellt Begrenzungs- und Blockierungsfunktionen für jeden Typ bereit, der [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) implementiert. Weitere Informationen finden Sie unter [Übersicht über BlockingCollection](blockingcollection-overview.md).
[ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) | Threadsichere Implementierung einer ungeordneten Auflistung von Elementen.
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) | Threadsichere Implementierung eines Wörterbuchs von Schlüssel-Wert-Paaren.
[ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) | Threadsichere Implementierung einer First In, First Out (FIFO)-Warteschlange.
[ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) | Threadsichere Implementierung eines Last In, First Out (LIFO)-Stapels.
[IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1) | Die Schnittstelle, die ein Typ implementieren muss, damit sie in `BlockingCollection` verwendet werden kann.

## <a name="thread-synchronization-in-the-net-framework-version-10-and-20-collections"></a>Threadsynchronisierung in den Auflistungen von .NET Framework Version 1.0 und 2.0

Die Auflistungen, die zum ersten Mal in .NET Framework Version 1.0 eingeführt wurden, befinden sich im [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Namespace. Diese Auflistungen, zu denen die häufig verwendeten Objekte [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) und [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) gehören, bieten eine gewisse Threadsicherheit durch die `Synchronized`-Eigenschaft, die einen threadsicheren Wrapper um die Auflistung zurückgibt. Der Wrapper funktioniert folgendermaßen: Die gesamte Auflistung wird bei jedem Hinzufüge- oder Entfernungsvorgang gesperrt. Daher muss jeder Thread, der versucht, auf die Auflistung zuzugreifen, warten, bis er die jeweilige Sperre übernehmen kann. Dies ist nicht skalierbar und kann beträchtliche Leistungseinbußen für große Auflistungen verursachen. Außerdem wird der Entwurf nicht völlig vor Racebedingungen geschützt. 

Die Auflistungsklassen, die zum ersten Mal in .NET Framework Version 2.0 eingeführt wurden, befinden sich im [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)-Namespace. Sie umfassen [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1), [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) usw. Diese Klassen bieten verbesserte Typsicherheit und Leistung im Vergleich zu den `System.Collections`-Klassen. Die `System.Collections.Generic`-Auflistungsklassen stellen jedoch keine Threadsynchronisierung bereit; der Benutzercode muss die gesamte Synchronisierung bereitstellen, wenn Elemente gleichzeitig in mehreren Threads hinzugefügt oder daraus entfernt werden.

Es wird empfohlen, die gleichzeitigen `System.Collections.Concurrent`-Auflistungsklassen zu verwenden, da sie nicht nur die Typsicherheit der `System.Collections.Generic`-Auflistungsklassen, sondern auch eine effizientere und vollständigere Threadsicherheit als die `System.Collections`-Auflistungen bieten.

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | -----------
[Übersicht über BlockingCollection](blockingcollection-overview.md) | Beschreibt die vom `BlockingCollection<T>`-Typ bereitgestellte Funktion.
[Verwendung einer threadsicheren Auflistung](when-to-use-a-thread-safe-collection.md) | Erläutert, wann es sinnvoll ist, eine threadsichere Auflistung zu verwenden.
[Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einem ConcurrentDictionary](how-to-add-and-remove-items.md) | Beschreibt, wie Elemente zu einem `ConcurrentDictionary<TKey, TValue>`-Objekt hinzugefügt und daraus entfernt werden.
[Vorgehensweise: Hinzufügen und Entfernen von einzelnen Elementen zu bzw. aus einer BlockingCollection](how-to-add-and-take-items.md) | Beschreibt, wie Elemente einer Blockierungsauflistung hinzugefügt und daraus abgerufen werden, ohne dass der schreibgeschützte Enumerator verwendet wird.
[Vorgehensweise: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Auflistung](how-to-add-bounding-and-blocking.md ) | Beschreibt, wie jede Auflistungsklasse als zugrunde liegender Speichermechanismus für eine `IProducerConsumerCollection<T>;`-Auflistung verwendet wird.
[Vorgehensweise: Entfernen von Elementen in einer BlockingCollection mit ForEach](how-to-use-foreach-to-remove.md ) | Beschreibt, wie mit `foreach` alle Elemente aus einer Blockierungsauflistung entfernt werden.
[Vorgehensweise: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline](how-to-use-arrays-of-blockingcollections.md) | Beschreibt, wie mit mehreren Blockierungsauflistungen gleichzeitig eine Pipeline implementiert wird.
[Vorgehensweise: Erstellen eines Objektpools mittels ConcurrentBag](how-to-create-an-object-pool.md) | Zeigt die Verwendung einer parallelen Sammlung zur Verbesserung der Leistung in Szenarien, in denen Sie Objekte nicht fortlaufend neu erstellen müssen, sondern diese wiederverwenden können.

## <a name="reference"></a>Verweis

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)






 





<!--HONumber=Nov16_HO3-->


