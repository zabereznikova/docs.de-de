---
title: Verwendung einer threadsicheren Auflistung
description: Verwendung einer threadsicheren Auflistung
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a2a42d44-f6a5-4f16-9000-026221d66349
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 05f692a1a58c0c653e14993cafd61a0711ebf9f8

---

# <a name="when-to-use-a-threadsafe-collection"></a>Verwendung einer threadsicheren Auflistung

Die Sammlungstypen `ConcurrentQueue`, `ConcurrentStack`, `ConcurrentDictionary`, `ConcurrentBag` und `BlockingCollection` sind speziell für die Unterstützung von multithreadbezogenen Hinzufüge- und Entfernungsvorgängen konzipiert. Zur Gewährleistung von Threadsicherheit verwenden diese neuen Typen unterschiedliche Arten effizienter sperrender und sperrfreier Synchronisierungsmechanismen. Ein Vorgang wird durch Synchronisierung aufwändiger. Das Ausmaß des Aufwands hängt von der Art der verwendeten Synchronisierung, der Art der ausgeführten Vorgänge und von anderen Faktoren ab, z.B. der Anzahl der Threads, die versuchen, gleichzeitig auf die Sammlung zuzugreifen.

In einigen Szenarien ist der Synchronisierungsaufwand unwesentlich und ermöglicht eine deutlich schnellere Ausführung und bessere Skalierbarkeit des Multithreadtyps als beim nicht threadsicheren Äquivalent, wenn ein Schutz durch eine externe Sperre besteht. In anderen Szenarien kann der Aufwand dazu führen, dass der threadsichere Typ in etwa mit der gleichen oder sogar einer geringeren Leistung und Skalierbarkeit ausgeführt wird wie die extern gesperrte, nicht threadsichere Version des Typs.

Die folgenden Abschnitte enthalten eine allgemeine Anleitung dazu, wann eine threadsichere Sammlung anstelle ihres nicht threadsicheren Äquivalents verwendet wird, das eine vom Benutzer bereitgestellte Sperre für die Lese- und Schreibvorgänge besitzt. Da die Leistung von vielen Faktoren abhängig sein kann, handelt es sich nicht um eine spezielle Anleitung, die daher nicht unter allen Umständen gültig ist. Wenn die Leistung sehr wichtig ist, ist die am besten geeignete Methode zur Bestimmung des zu verwendenden Sammlungstyps die Messung der Leistung auf Basis von repräsentativen Computerkonfigurationen und Lasten. In diesem Dokument werden die folgenden Begriffe verwendet:

*Reines Producer-Consumer-Szenario:* In jedem angegebenen Thread werden Elemente entweder hinzugefügt oder entfernt, es finden jedoch nicht beide Vorgänge statt.

*Gemischtes Producer-Consumer-Szenario:* In jedem angegebenen Thread werden Elemente sowohl hinzugefügt als auch entfernt.

*Beschleunigung:* Höhere algorithmische Leistung relativ zu einem anderen Typ im gleichen Szenario.

*Skalierbarkeit:* Die Zunahme der Leistung, die proportional zur Anzahl der Kerne des Computers ist. Mit einem Algorithmus, der skaliert wird, werden bei acht Kernen höhere Leistungen erzielt als bei zwei Kernen.

## <a name="concurrentqueuelttgt-vs-queuelttgt"></a>ConcurrentQueue&lt;T&gt; oder Queue&lt;T&gt;

In reinen Producer-Consumer-Szenarien, in denen die Verarbeitungszeit für jedes Element sehr kurz ist (einige Anweisungen), kann [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) geringfügige Leistungsvorteile gegenüber [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) mit einer externen Sperre bieten. In diesem Szenario erzielt `ConcurrentQueue<T>` die beste Leistung, wenn sich ein dedizierter Thread in der Warteschlange befindet und ein dedizierter Thread die Warteschlange verlässt. Wenn Sie diese Regel nicht erzwingen, kann `Queue<T>` sogar etwas schneller als `ConcurrentQueue<T>` auf Computern mit mehreren Kernen ausgeführt werden. 

Wenn die Verarbeitungszeit bei etwa 500 FLOPS (Gleitkommavorgänge) oder höher liegt, gilt die Zwei-Thread-Regel nicht für `ConcurrentQueue<T>`, sodass dann eine sehr gute Skalierbarkeit möglich ist. `Queue<T>` lässt sich in diesem Szenario nicht vorteilhaft skalieren.

Bei sehr geringer Verarbeitungszeit zeichnet sich `Queue<T>` mit einer externen Sperre in gemischten Producer-Consumer-Szenarien durch eine bessere Skalierbarkeit als `ConcurrentQueue<T>` aus. Wenn die Verarbeitungszeit jedoch bei etwa 500 FLOPS oder darüber liegt, kann `ConcurrentQueue<T>` besser skaliert werden.

## <a name="concurrentstack-vs-stack"></a>ConcurrentStack oder Stapel

In reinen Producer-Consumer-Szenarien erzielen [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) und [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) mit einer externen Sperre bei sehr geringer Verarbeitungszeit wahrscheinlich annähernd die gleiche Leistung mit einem dedizierten Thread für Ablegevorgänge und einem dedizierten Thread für Abholvorgänge. Bei zunehmender Anzahl der Threads werden jedoch beide Typen aufgrund des stärkeren Konflikts langsamer, und mit `Stack<T>` werden unter Umständen bessere Leistungen als mit `ConcurrentStack<T>` erzielt. Wenn die Verarbeitungszeit bei rund 500 FLOPS oder darüber liegt, werden beide Typen mit der etwa gleichen Rate skaliert. 

In gemischten Producer-Consumer-Szenarien ist `ConcurrentStack<T>` für kleine und große Arbeitsauslastungen schneller.

Die Verwendung von `PushRange` und `TryPopRange` kann die Zugriffszeiten unter Umständen erheblich beschleunigen.

## <a name="concurrentdictionary-vs-dictionary"></a>ConcurrentDictionary oder Dictionary

Verwenden Sie im Allgemeinen in jedem Szenario, in dem Sie Schlüssel oder Werte gleichzeitig von mehreren Threads hinzufügen und aktualisieren, [System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2). In Szenarien, die häufige Updates und relativ wenige Lesevorgänge umfassen, bietet `ConcurrentDictionary<TKey, TValue>` in der Regel geringfügige Vorteile. In Szenarien, die zahlreiche Lesevorgänge und Updates umfassen, ist `ConcurrentDictionary<TKey, TValue>` im Allgemeinen auf Computern bedeutend schneller, die über eine beliebige Anzahl von Kernen verfügen.

In Szenarien, die häufige Updates umfassen, können Sie den Grad der Parallelität in `ConcurrentDictionary<TKey, TValue>` erhöhen und anschließend ermitteln, ob sich die Leistung auf Computern mit einer größeren Anzahl von Kernen verbessert. Wenn Sie die Parallelitätsebene ändern, vermeiden Sie so weit wie möglich globale Vorgänge.

Wenn Sie nur Schlüssel oder Werte lesen, ist [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) schneller, da keine Synchronisierung erforderlich ist, wenn das Wörterbuch nicht von Threads geändert wird.

## <a name="concurrentbag"></a>ConcurrentBag

In reinen Producer-Consumer-Szenarien ist [System.Collections.Concurrent.ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) wahrscheinlich langsamer als die anderen gleichzeitigen Sammlungstypen.

In gemischten Producer-Consumer-Szenarien ist `ConcurrentBag<T>` sowohl bei großen als auch bei kleinen Arbeitsauslastungen im Allgemeinen viel schneller und besser skalierbar als ein beliebiger anderer gleichzeitiger Sammlungstyp.

## <a name="blockingcollection"></a>BlockingCollection

Wenn Begrenzungs- und Blockierungssemantiken erforderlich sind, wird [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) wahrscheinlich schneller als jede beliebige benutzerdefinierte Implementierung ausgeführt. Zudem werden umfassende Möglichkeiten für die Abbruch-, Enumerations- und Ausnahmebehandlung unterstützt.

## <a name="see-also"></a>Siehe auch

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Threadsichere Sammlungen](index.md)



<!--HONumber=Nov16_HO3-->


