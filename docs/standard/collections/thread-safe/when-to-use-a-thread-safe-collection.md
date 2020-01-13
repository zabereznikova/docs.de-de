---
title: Verwendung einer threadsicheren Auflistung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, when to upgrade
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
ms.openlocfilehash: 5a0abef6de9f932f44fc7e3239b98c3a27846580
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711219"
---
# <a name="when-to-use-a-thread-safe-collection"></a>Verwendung einer threadsicheren Auflistung
Mit .NET Framework 4 werden fünf neue Auflistungstypen eingeführt, die speziell für die Unterstützung von Hinzufügungs- und Entfernungsvorgängen in mehreren Threads konzipiert sind. Zur Gewährleistung von Threadsicherheit verwenden diese neuen Typen unterschiedliche Arten effizienter sperrender und sperrfreier Synchronisierungsmechanismen. Ein Vorgang wird durch Synchronisierung aufwändiger. Das Ausmaß des Aufwands hängt von der Art der verwendeten Synchronisierung, der Art der ausgeführten Vorgänge und von anderen Faktoren ab, z.B. der Anzahl der Threads, die versuchen, gleichzeitig auf die Sammlung zuzugreifen.  
  
 In einigen Szenarien ist der Synchronisierungsaufwand unwesentlich und ermöglicht eine deutlich schnellere Ausführung und bessere Skalierbarkeit des Multithreadtyps als beim nicht threadsicheren Äquivalent, wenn ein Schutz durch eine externe Sperre besteht. In anderen Szenarien kann der Aufwand dazu führen, dass der threadsichere Typ in etwa mit der gleichen oder sogar einer geringeren Leistung und Skalierbarkeit ausgeführt wird wie die extern gesperrte, nicht threadsichere Version des Typs.  
  
 Die folgenden Abschnitte enthalten eine allgemeine Anleitung dazu, wann eine threadsichere Sammlung anstelle ihres nicht threadsicheren Äquivalents verwendet wird, das eine vom Benutzer bereitgestellte Sperre für die Lese- und Schreibvorgänge besitzt. Da die Leistung von vielen Faktoren abhängig sein kann, handelt es sich nicht um eine spezielle Anleitung, die daher nicht unter allen Umständen gültig ist. Wenn die Leistung sehr wichtig ist, ist die am besten geeignete Methode zur Bestimmung des zu verwendenden Sammlungstyps die Messung der Leistung auf Basis von repräsentativen Computerkonfigurationen und Lasten. In diesem Dokument werden die folgenden Begriffe verwendet:  
  
 *Reines Producer-Consumer-Szenario*  
 In jedem vorhandenen Thread werden Elemente entweder hinzugefügt oder entfernt, es finden jedoch nicht beide Vorgänge statt.  
  
 *Gemischtes Producer-Consumer-Szenario*  
 In jedem vorhandenen Thread werden Elemente sowohl hinzugefügt als auch entfernt.  
  
 *Geschwindigkeitszuwachs*  
 Höhere algorithmische Leistung relativ zu einem anderen Typ im gleichen Szenario.  
  
 *Skalierbarkeit*  
 Die Zunahme der Leistung, die proportional zur Anzahl der Kerne des Computers ist. Mit einem Algorithmus, der skaliert wird, werden bei acht Kernen höhere Leistungen erzielt als bei zwei Kernen.  
  
## <a name="concurrentqueuet-vs-queuet"></a>ConcurrentQueue(T) oder Queue(T)  
 In reinen Producer-Consumer-Szenarien, in denen die Verarbeitungszeit für jedes Element sehr kurz ist (einige Anweisungen), kann <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> geringfügige Leistungsvorteile gegenüber <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> mit einer externen Sperre bieten. In diesem Szenario erzielt <xref:System.Collections.Concurrent.ConcurrentQueue%601> die beste Leistung, wenn sich ein dedizierter Thread in der Warteschlange befindet und ein dedizierter Thread die Warteschlange verlässt. Wenn Sie diese Regel nicht erzwingen, kann <xref:System.Collections.Generic.Queue%601> sogar etwas schneller als <xref:System.Collections.Concurrent.ConcurrentQueue%601> auf Computern mit mehreren Kernen ausgeführt werden.  
  
 Wenn die Verarbeitungszeit bei etwa 500 FLOPS (Gleitkommavorgänge) oder höher liegt, gilt die Zwei-Thread-Regel nicht für <xref:System.Collections.Concurrent.ConcurrentQueue%601>, sodass dann eine sehr gute Skalierbarkeit möglich ist. <xref:System.Collections.Generic.Queue%601> lässt sich in diesem Szenario nicht vorteilhaft skalieren.  
  
 Bei sehr geringer Verarbeitungszeit zeichnet sich <xref:System.Collections.Generic.Queue%601> mit einer externen Sperre in gemischten Producer-Consumer-Szenarien durch eine bessere Skalierbarkeit als <xref:System.Collections.Concurrent.ConcurrentQueue%601> aus. Wenn die Verarbeitungszeit jedoch bei etwa 500 FLOPS oder darüber liegt, kann <xref:System.Collections.Concurrent.ConcurrentQueue%601> besser skaliert werden.  
  
## <a name="concurrentstack-vs-stack"></a>ConcurrentStack oder Stapel  
 In reinen Producer-Consumer-Szenarien erzielen <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> mit einer externen Sperre bei sehr geringer Verarbeitungszeit wahrscheinlich annähernd die gleiche Leistung mit einem dedizierten Thread für Ablegevorgänge und einem dedizierten Thread für Abholvorgänge. Bei zunehmender Anzahl der Threads werden jedoch beide Typen aufgrund des stärkeren Konflikts langsamer, und mit <xref:System.Collections.Generic.Stack%601> werden unter Umständen bessere Leistungen als mit <xref:System.Collections.Concurrent.ConcurrentStack%601> erzielt. Wenn die Verarbeitungszeit bei rund 500 FLOPS oder darüber liegt, werden beide Typen mit der etwa gleichen Rate skaliert.  
  
 In gemischten Producer-Consumer-Szenarien ist <xref:System.Collections.Concurrent.ConcurrentStack%601> für kleine und große Arbeitsauslastungen schneller.  
  
 Die Verwendung von <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> und <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> kann die Zugriffszeiten unter Umständen erheblich beschleunigen.  
  
## <a name="concurrentdictionary-vs-dictionary"></a>ConcurrentDictionary oder Dictionary  
 Verwenden Sie <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> im Allgemeinen in jedem Szenario, in dem Sie Schlüssel oder Werte gleichzeitig aus mehreren Threads hinzufügen und aktualisieren. In Szenarien, die häufige Updates und relativ wenige Lesevorgänge umfassen, bietet <xref:System.Collections.Concurrent.ConcurrentDictionary%602> in der Regel geringfügige Vorteile. In Szenarien, die zahlreiche Lesevorgänge und Updates umfassen, ist <xref:System.Collections.Concurrent.ConcurrentDictionary%602> im Allgemeinen auf Computern bedeutend schneller, die über eine beliebige Anzahl von Kernen verfügen.  
  
 In Szenarien, die häufige Updates umfassen, können Sie den Grad der Parallelität in <xref:System.Collections.Concurrent.ConcurrentDictionary%602> erhöhen und anschließend ermitteln, ob sich die Leistung auf Computern mit einer größeren Anzahl von Kernen verbessert. Wenn Sie die Parallelitätsebene ändern, vermeiden Sie so weit wie möglich globale Vorgänge.  
  
 Wenn Sie nur Schlüssel oder Werte lesen, ist <xref:System.Collections.Generic.Dictionary%602> schneller, da keine Synchronisierung erforderlich ist, wenn das Wörterbuch nicht von Threads geändert wird.  
  
## <a name="concurrentbag"></a>ConcurrentBag  
 In reinen Producer-Consumer-Szenarien ist <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType> wahrscheinlich langsamer als die anderen gleichzeitigen Sammlungstypen.  
  
 In gemischten Producer-Consumer-Szenarien ist <xref:System.Collections.Concurrent.ConcurrentBag%601> sowohl bei großen als auch bei kleinen Arbeitsauslastungen im Allgemeinen viel schneller und besser skalierbar als ein beliebiger anderer gleichzeitiger Sammlungstyp.  
  
## <a name="blockingcollection"></a>BlockingCollection  
 Wenn Begrenzungs- und Blockierungssemantiken erforderlich sind, wird <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> wahrscheinlich schneller als jede beliebige benutzerdefinierte Implementierung ausgeführt. Zudem werden umfassende Möglichkeiten für die Abbruch-, Enumerations- und Ausnahmebehandlung unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Threadsichere Sammlungen](../../../../docs/standard/collections/thread-safe/index.md)
- [Parallele Programmierung](../../../../docs/standard/parallel-programming/index.md)
