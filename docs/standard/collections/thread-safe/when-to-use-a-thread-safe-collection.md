---
title: "Verwendung einer threadsicheren Auflistung | Microsoft Docs"
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
  - "Threadsichere Auflistungen, Zeitpunkt des Upgrades"
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Verwendung einer threadsicheren Auflistung
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] beinhaltet fünf neue Auflistungstypen, die speziell für die Unterstützung von multithreadbezogenen Hinzufüge\- und Entfernungsvorgängen konzipiert wurden.  Zur Gewährleistung von Threadsicherheit verwenden diese neuen Typen unterschiedliche Arten effizienter sperrender und sperrfreier Synchronisierungsmechanismen.  Ein Vorgang wird durch Synchronisierung aufwändiger.  Das Ausmaß des Aufwands hängt von der Art der verwendeten Synchronisierung, der Art der ausgeführten Vorgänge und von anderen Faktoren ab, z. B. der Anzahl der Threads, die versuchen, gleichzeitig auf die Auflistung zuzugreifen.  
  
 In einigen Szenarien ist der Synchronisierungsaufwand unwesentlich und ermöglicht eine deutlich schnellere Ausführung und bessere Skalierbarkeit des Multithreadtyps als beim nicht sicheren Äquivalent, wenn ein Schutz durch eine externe Sperre besteht.  In anderen Szenarien kann der Aufwand dazu führen, dass der threadsichere Typ in etwa mit der gleichen oder sogar einer geringeren Leistung und Skalierbarkeit ausgeführt wird wie die extern gesperrte, nicht threadsichere Version des Typs.  
  
 Die folgenden Abschnitte enthalten allgemeine Hinweise dazu, wann eine threadsichere Auflistung anstelle ihres nicht threadsicheren Äquivalents verwendet wird, das eine vom Benutzer bereitgestellte Sperre um die Lese\- und Schreibvorgänge besitzt.  Da die Leistung von vielen Faktoren abhängig sein kann, handelt es sich nicht um eine spezielle Anleitung, die daher nicht unter allen Umständen gültig ist.  Wenn die Leistung sehr wichtig ist, ist die am besten geeignete Methode zur Bestimmung des zu verwendenden Auflistungstyps die Messung der Leistung auf Basis von repräsentativen Computerkonfigurationen und Lasten.  In diesem Dokument werden die folgenden Begriffe verwendet:  
  
 *Reines Producer\-Consumer\-Szenario*  
 In jedem angegebenen Thread werden Elemente entweder hinzugefügt oder entfernt, es finden jedoch nicht beide Vorgänge statt.  
  
 *Gemischtes Producer\-Consumer\-Szenario*  
 In jedem angegebenen Thread werden Elemente sowohl hinzugefügt als auch entfernt.  
  
 *Beschleunigung*  
 Schnellere algorithmische Leistung relativ zu einem anderen Typ im gleichen Szenario.  
  
 *Skalierbarkeit*  
 Die Zunahme der Leistung, die proportional zur Anzahl der Kerne auf dem Computer ist.  Mit einem Algorithmus, der skaliert wird, werden bei acht Kernen schnellere Leistungen erzielt als bei zwei Kernen.  
  
## ConcurrentQueue \(T\) im Warteschlange \(T\)  
 In reinen Producer\-Consumer\-Szenarien, in denen die Verarbeitungszeit für jedes Element sehr klein ist \(einige Anweisungen\), kann ein <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>\-Objekt geringfügige Leistungsvorteile gegenüber einem <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>\-Objekt mit einer externen Sperre erreichen.  In diesem Szenario erzielt <xref:System.Collections.Concurrent.ConcurrentQueue%601> die beste Leistung, wenn sich ein dedizierter Thread in der Warteschlange befindet und ein dedizierter Thread die Warteschlange verlässt.  Wenn Sie diese Regel nicht erzwingen, kann <xref:System.Collections.Generic.Queue%601> sogar ein wenig schneller als <xref:System.Collections.Concurrent.ConcurrentQueue%601> auf Computern mit mehreren Kernen ausgeführt werden.  
  
 Wenn die Verarbeitungszeit bei etwa 500 FLOPS \(Gleitkommavorgänge\) oder höher liegt, gilt die Zwei\-Thread\-Regel nicht für das <xref:System.Collections.Concurrent.ConcurrentQueue%601>\-Objekt, das dann über eine sehr gute Skalierbarkeit verfügt.  <xref:System.Collections.Generic.Queue%601> lässt sich in diesem Szenario nicht vorteilhaft skalieren.  
  
 Bei sehr geringer Verarbeitungszeit zeichnet sich ein <xref:System.Collections.Generic.Queue%601>\-Objekt mit einer externen Sperre in gemischten Producer\-Consumer\-Szenarien durch eine bessere Skalierbarkeit als ein <xref:System.Collections.Concurrent.ConcurrentQueue%601>\-Objekt aus.  Wenn die Verarbeitungszeit jedoch bei etwa 500 FLOPS oder darüber liegt, kann das <xref:System.Collections.Concurrent.ConcurrentQueue%601>\-Objekt besser skaliert werden.  
  
## ConcurrentStack für Stapel  
 In reinen Producer\-Consumer\-Szenarien erzielen das <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>\-Objekt und das <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>\-Objekt, das eine externe Sperre besitzt, bei sehr geringer Verarbeitungszeit wahrscheinlich annähernd die gleiche Leistung mit einem dedizierten Thread für Ablegevorgänge und einem dedizierten Thread für Abholvorgänge.  Bei zunehmender Anzahl der Threads werden jedoch beide Typen aufgrund des stärkeren Konflikts langsamer, und mit <xref:System.Collections.Generic.Stack%601> werden unter Umständen bessere Leistungen als mit <xref:System.Collections.Concurrent.ConcurrentStack%601> erzielt.  Wenn die Verarbeitungszeit bei rund 500 FLOPS oder darüber liegt, werden beide Typen mit der etwa gleichen Rate skaliert.  
  
 In gemischten Producer\-Consumer\-Szenarien ist <xref:System.Collections.Concurrent.ConcurrentStack%601> sowohl für kleine als auch für große Arbeitslasten schneller.  
  
 Die Verwendung von <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> und <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> kann die Zugriffszeiten unter Umständen erheblich beschleunigen.  
  
## ConcurrentDictionary anhand Wörterbuch  
 Verwenden Sie im Allgemeinen in jedem Szenario, in dem Sie Schlüssel oder Werte gleichzeitig von mehreren Threads hinzufügen und aktualisieren, ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\-Objekt.  In Szenarien, die häufige Updates und relativ wenige Lesevorgänge umfassen, bietet das <xref:System.Collections.Concurrent.ConcurrentDictionary%602>\-Objekt in der Regel geringfügige Vorteile.  In Szenarien, die zahlreiche Lesevorgänge und Updates umfassen, wird das <xref:System.Collections.Concurrent.ConcurrentDictionary%602>\-Objekt im Allgemeinen auf Computern bedeutend schneller, die über eine beliebige Anzahl von Kernen verfügen.  
  
 In Szenarien, die häufige Updates umfassen, können Sie den Grad der Parallelität im <xref:System.Collections.Concurrent.ConcurrentDictionary%602>\-Objekt erhöhen und anschließend ermitteln, ob sich die Leistung auf Computern mit einer größeren Anzahl von Kernen verbessert.  Wenn Sie die Parallelitätsebene ändern, vermeiden Sie so weit wie möglich globale Vorgänge.  
  
 Wenn Sie nur Schlüssel oder Werte lesen, ist das <xref:System.Collections.Generic.Dictionary%602>\-Objekt schneller, da keine Synchronisierung erforderlich ist, wenn das Wörterbuch nicht von Threads geändert wird.  
  
## ConcurrentBag  
 In reinen Producer\-Consumer\-Szenarien ist das <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>\-Objekt wahrscheinlich langsamer als die anderen gleichzeitigen Auflistungstypen.  
  
 In gemischten Producer\-Consumer\-Szenarien ist das <xref:System.Collections.Concurrent.ConcurrentBag%601>\-Objekt sowohl bei großen als auch bei kleinen Arbeitslasten im Allgemeinen viel schneller und besser skalierbar als ein beliebiger anderer gleichzeitiger Auflistungstyp.  
  
## BlockingCollection  
 Wenn Begrenzungs\- und Blockierungssemantiken erforderlich sind, wird das <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>\-Objekt wahrscheinlich schneller als jede beliebige benutzerdefinierte Implementierung ausgeführt.  Zudem werden umfassende Abbruchmöglichkeiten, Enumeration und Ausnahmebehandlung unterstützt.  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)