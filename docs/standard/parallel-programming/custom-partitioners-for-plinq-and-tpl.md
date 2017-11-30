---
title: "Benutzerdefinierte Partitionierer für PLINQ und TPL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12d234b86b0067178d54d2fdcb5d37ceaee6109d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Benutzerdefinierte Partitionierer für PLINQ und TPL
Um einen Vorgang für eine Datenquelle zu parallelisieren, besteht eine der wesentlichen Schritte darin *Partition* der Quelle in mehrere Abschnitte, die gleichzeitig durch mehrere Threads zugegriffen werden kann. PLINQ und der Task Parallel Library (TPL) bieten standardmäßige Partitionierer, die transparent arbeiten, wenn Sie eine parallele Abfrage schreiben oder <xref:System.Threading.Tasks.Parallel.ForEach%2A> Schleife. Für erweiterte Szenarien können Sie Ihren eigenen Partitionierer anschließen.  
  
## <a name="kinds-of-partitioning"></a>Art der Partitionierung  
 Es gibt viele Möglichkeiten, eine Datenquelle zu partitionieren. Ermöglichen in das effizientesten Verfahren mehrere Threads zum Prozess der ursprünglichen Quellsequenz, anstatt die Quelle in mehrere Untersequenzen physisch zu trennen. Für Arrays und andere Datenquellen wie z. B. indiziert werden <xref:System.Collections.IList> Sammlungen, bei die Länge im Voraus bekannt ist *Bereichspartitionierung* ist die einfachste Art der Partitionierung. Jeder Thread empfängt eindeutig ist, werden öffnend und schließend Indizes, damit dessen Bereich der Quelle ohne überschreiben oder überschrieben wird, indem ein anderer Thread verarbeitet werden können. Der einzige Aufwand Bereichspartitionierung ist die ursprüngliche Erstellung von Bereichen; Danach ist keine zusätzliche Synchronisierung erforderlich. Aus diesem Grund können sie gute Leistung bereitstellen, solange die arbeitsauslastung gleichmäßig verteilt wird. Ein Nachteil der Bereichspartitionierung ist, wenn ein Thread frühzeitig beendet wird, die andere Threads ihre Arbeit abgeschlossen helfen kann nicht an.  
  
 Für verknüpfte Listen oder anderen Auflistungen, dessen Länge nicht bekannt ist, können Sie *Blockpartitionierung*. Segment zu partitionieren, jeder Thread oder eine Aufgabe in einer parallelen Schleife oder einer Abfrage nutzt eine Anzahl von Quellelementen in einem Block, verarbeitet sie und dann zurückkehrt, zusätzliche Elemente abzurufen. Mit dem Partitionierer wird sichergestellt, dass alle Elemente verteilt werden und keine Duplikate vorhanden sind. Ein Block kann eine beliebige Größe sein. Z. B. mit dem Partitionierer, der in gezeigt [Vorgehensweise: Implementieren dynamische Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) erstellt Segmente, die nur ein Element enthalten. Solange die Blöcke nicht zu groß sind, ist diese Art der Partitionierung auch grundsätzlich auf den Lastenausgleich, da die Zuweisung von Elementen, die Threads nicht vorgegeben ist. Allerdings mit dem Partitionierer den Synchronisierung jedes Mal Mehraufwand der Thread einen anderen Block abrufen muss. Die Menge der Synchronisierungsaufwand in diesen Fällen ist umgekehrt proportional zur Größe der Segmente.  
  
 Im Allgemeinen ist die Range-Partitionierung nur schneller, wenn die Ausführungszeit des Delegaten klein ist, Mittel, die Quelle verfügt über eine große Anzahl von Elementen und die gesamte Arbeit in jeder Partition ungefähr entspricht. Blockpartitionierung ist daher im Allgemeinen schneller in den meisten Fällen. Auf Datenquellen mit einer kleinen Anzahl von Elementen oder längere Ausführungszeiten für den Delegaten ist die Leistung des Blocks und Bereichspartitionierung ungefähr gleich.  
  
 Die TPL-Partitionierer unterstützen auch eine dynamische Anzahl von Partitionen. Dies bedeutet, sie können Partitionen auf dynamische, z. B. erstellen, wenn die <xref:System.Threading.Tasks.Parallel.ForEach%2A> Schleife erzeugt eine neue Aufgabe. Dieses Feature ermöglicht den Partitionierer zusammen mit der Schleife selbst zu skalieren. Dynamische Partitionierer sind auch die grundsätzlich auf den Lastenausgleich. Wenn Sie einen benutzerdefinierten Partitionierer erstellen, müssen Sie unterstützen, dynamische Partitionierung, um in werden eine <xref:System.Threading.Tasks.Parallel.ForEach%2A> Schleife.  
  
### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Konfigurieren von Lastenausgleich Partitionierer für PLINQ  
 Einige Überladungen der <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> Methode können Sie die eines Partitionierers für ein Array oder <xref:System.Collections.IList> Datenquelle aus, und gibt an, ob die arbeitsauslastung zwischen den Threads verteilen versucht werden soll. Wenn mit dem Partitionierer für den Lastenausgleich konfiguriert ist, Segment Partitionierung wird verwendet, und die Elemente werden aus auf jede Partition in kleinen Blöcken übergeben, bei deren Anforderung. Dieser Ansatz wird sichergestellt, dass alle Partitionen Elemente haben, bis die gesamte Schleife verarbeitet oder die Abfrage abgeschlossen ist. Eine weitere Überladung kann verwendet werden, um den Lastenausgleich Partitionierung eines beliebigen <xref:System.Collections.IEnumerable> Quelle.  
  
 Lastenausgleich erfordert im Allgemeinen die Partitionen auf Elemente relativ häufig von der Partitionierer anfordern. Dagegen kann ein Partitionierer, der statische Partitionierung ist die Elemente jeder Partitionierer gleichzeitig zuweisen mithilfe von Bereich oder Blockpartitionierung. Dies erfordert weniger Aufwand als Lastenausgleich, aber es möglicherweise länger ausgeführt werden, wenn ein Thread deutlich mehr Arbeit als die anderen endet. Wenn sie IList oder ein Array übergeben wird verwendet standardmäßig PLINQ immer Bereichspartitionierung ohne Lastenausgleich. Um einen Lastenausgleich für PLINQ zu aktivieren, verwenden die `Partitioner.Create` Methode, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 Die beste Möglichkeit zu bestimmen, ob Laden mit Lastenausgleich in einem gegebenen Szenario experimentieren und messen, wie lange dauert Vorgänge unter repräsentative Lade- und Computerkonfigurationen abgeschlossen. Z. B. statische Partitionierung möglicherweise erhebliche Beschleunigung auf einem Multikern-Computer, der nur wenige Kernen bereit, aber es unter Umständen in verlangsamungen auf Computern, die relativ viele Kerne verfügen.  
  
 Die folgende Tabelle listet die verfügbaren Überladungen der <xref:System.Collections.Concurrent.Partitioner.Create%2A> Methode. Diese Partitionierer gilt keine Einschränkung für die Verwendung nur mit PLINQ oder <xref:System.Threading.Tasks.Task>. Sie können auch mit jedem benutzerdefinierten parallelen Konstrukt verwendet werden.  
  
|überladen|Mithilfe des Lastenausgleichs|  
|--------------|-------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Immer|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Wenn das boolesche Argument als "true" angegeben wird|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Wenn das boolesche Argument als "true" angegeben wird|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nie|  
  
### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Bereich für statische Partitionierer für Parallel.ForEach konfigurieren  
 In einem <xref:System.Threading.Tasks.Parallel.For%2A> Schleife, den Text der Schleife wird bereitgestellt, um die Methode als Delegaten vor. Die Kosten für diesen Delegaten aufrufen geht es um den Aufruf einer virtuellen Methode identisch. In einigen Szenarien ist der Text einer parallelen Schleife klein genug möglicherweise, dass die Kosten der Delegataufruf in jeder Schleifeniteration erhebliche wird. In solchen Situationen können Sie mithilfe eines der <xref:System.Collections.Concurrent.Partitioner.Create%2A> Überladungen zum Erstellen einer <xref:System.Collections.Generic.IEnumerable%601> von Bereichspartitionen über die Quellelemente. Übergeben Sie Sie dann diese Auflistung von Bereichen an, um eine <xref:System.Threading.Tasks.Parallel.ForEach%2A> Methode, deren Text eine reguläre besteht `for` Schleife. Der Vorteil dieses Ansatzes ist, dass die Kosten für Delegaten Aufruf nur einmal pro Bereich und nicht einmal pro Element entstanden ist. Das folgende Beispiel zeigt das grundlegende Muster.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Jeder Thread in der Schleife empfängt ein eigenes <xref:System.Tuple%602> , enthält das Start- und Enddatum Indexwerte in der angegebenen untergeordneten Bereich. Die innere `for` -Schleife verwendet die `fromInclusive` und `toExclusive` Werte in einer Schleife über das Array oder die <xref:System.Collections.IList> direkt.  
  
 Eines der <xref:System.Collections.Concurrent.Partitioner.Create%2A> Überladungen können Sie angeben, die Größe der Partitionen und die Anzahl der Partitionen. Diese Überladung kann in Szenarien verwendet, wird die Arbeit pro Element so niedrig ist, dass auch eine virtuelle Methodenaufruf pro Element eine merkliche Auswirkungen auf die Leistung hat.  
  
## <a name="custom-partitioners"></a>Benutzerdefinierte Partitionierer  
 In einigen Szenarien kann es empfehlenswert oder sogar erforderlich, Ihren eigenen Partitionierer zu implementieren sein. Beispielsweise müssen Sie eine benutzerdefinierte Auflistungsklasse möglicherweise, die Sie partitionieren, können effizienter als die Standardzeit Partitionierer können basierend auf Ihrer Kenntnisse der internen Struktur der-Klasse. Oder Sie Bereichspartitionen mit unterschiedlichen Größen basierend auf Ihrer Kenntnisse darüber, wie lange Prozess Elementen an verschiedenen Standorten in der quellauflistung dafür erstellen möchten.  
  
 Zum Erstellen eines einfachen benutzerdefinierten Partitionierers leiten Sie eine Klasse von <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> und die virtuellen Methoden überschreiben, wie in der folgenden Tabelle beschrieben.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt die IList(IEnumerator(TSource)) zurück. Jeder Arbeitsthread in der Schleife oder einer Abfrage aufrufen kann `GetEnumerator` in der Liste zum Abrufen einer <xref:System.Collections.Generic.IEnumerator%601> über eine unterschiedliche Partition.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Zurückgeben `true` bei Implementierung <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, und andernfalls `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> ist `true`, diese Methode kann optional aufgerufen werden, anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Wenn die Ergebnisse sortierbar sein müssen, oder Sie indizierten Zugriff auf die Elemente benötigen, klicken Sie dann eine Ableitung von <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> und ihre virtuellen Methoden überschreiben, wie in der folgenden Tabelle beschrieben.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt eine `IList(IEnumerator(TSource))`. Jeder Arbeitsthread in der Schleife oder einer Abfrage aufrufen kann `GetEnumerator` in der Liste zum Abrufen einer <xref:System.Collections.Generic.IEnumerator%601> über eine unterschiedliche Partition.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Zurückgeben `true` bei Implementierung <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>, andernfalls "false".|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|In der Regel wird dies ruft nur <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> ist `true`, diese Methode kann optional aufgerufen werden, anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>.|  
  
 Die folgende Tabelle enthält weitere Details dazu, wie die drei Arten von Lastenausgleich Partitionierer implementieren die <xref:System.Collections.Concurrent.OrderablePartitioner%601> Klasse.  
  
|Methode/Eigenschaft|IList / Array ohne Lastenausgleich|IList / Array mit Lastenausgleich|IEnumerable|  
|----------------------|-------------------------------------------|----------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Verwendet die Range-Partitionierung|Verwendet die Chunk Partitionierung für Listen für die angegebene PartitionCount optimiert|Verwendet Blockpartitionierung, indem Sie eine statische Anzahl von Partitionen erstellen.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Löst das nicht unterstützte-Ausnahme|Verwendet in Blöcken Partitionierung, optimiert für Listen und dynamische Partitionen|Verwendet Blockpartitionierung, durch das Erstellen einer dynamischen Anzahl von Partitionen.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Gibt `true` zurück.|Gibt `false` zurück.|Gibt `false` zurück.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Gibt `false` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
  
### <a name="dynamic-partitions"></a>Dynamische Partitionen  
 Wenn Sie, mit dem Partitionierer beabsichtigen zu verwendende eine <xref:System.Threading.Tasks.Parallel.ForEach%2A> -Methode, Sie müssen möglicherweise eine dynamische Anzahl von Partitionen zurückgibt. Dies bedeutet, dass mit dem Partitionierer einen Enumerator für eine neue Partition bei Bedarf zu einem beliebigen Zeitpunkt während der schleifenausführung bereitstellen kann. Wenn die Schleife eine neue parallele Aufgabe hinzufügt, fordert er im Grunde eine neue Partition für diese Aufgabe. Wenn Sie die Daten bestellt werden müssen, klicken Sie dann Ableiten aus <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> so, dass jedes Element in jeder Partition einen eindeutigen Index zugewiesen ist.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Vorgehensweise: Implementieren dynamische Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### <a name="contract-for-partitioners"></a>Vertrag für Partitionierer  
 Wenn Sie einen benutzerdefinierten Partitionierer implementieren, befolgen Sie diese Richtlinien, um sicherzustellen, dass ordnungsgemäße Interaktion mit PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> in der TPL:  
  
-   Wenn <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> ist mit einem Argument von 0 (null) oder weniger für `partitionsCount`, lösen <xref:System.ArgumentOutOfRangeException>. Obwohl PLINQ und TPL niemals übergeben wird eine `partitionCount` gleich 0, dennoch sollten Sie davor zu schützen.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> sollte stets `partitionsCount` Anzahl von Partitionen. Wenn der Partitionierer aus Daten, die ausgeführt wird und so viele Partitionen wie angefordert wird, kann nicht erstellt werden, und klicken Sie dann die Methode einen leeren Enumerator für jede der verbleibenden Partitionen zurückgeben soll. Andernfalls löst PLINQ und TPL ein <xref:System.InvalidOperationException>.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>, und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> sollte nie zurückgeben `null` (`Nothing` in Visual Basic). Wenn dies der Fall, PLINQ / TPL löst eine <xref:System.InvalidOperationException>.  
  
-   Methoden, die Partitionen zurückgeben sollte immer Partitionen zurückgegeben, die vollständig und eindeutig die Datenquelle aufgelistet werden können. Es darf keine Duplikate in der Datenquelle oder übersprungene Elemente, sofern nicht ausdrücklich vom Entwurf der mit dem Partitionierer erforderlich. Wenn diese Regel nicht befolgt werden, kann die Ausgabe Reihenfolge Datenschutzaspekten.  
  
-   Die folgenden booleschen Getter müssen immer genau die folgenden Werte zurückgeben, damit, dass die Reihenfolge der Ausgabe nicht verschlüsselt wurde:  
  
    -   `KeysOrderedInEachPartition`: Jede Partition gibt Elemente mit zunehmenden Key Indizes zurück.  
  
    -   `KeysOrderedAcrossPartitions`: Für alle Partitionen, die die Schlüssel Indizes in der Partition zurückgegeben werden *ich* höher sind als die wichtigsten Indizes in der Partition *ich*-1 zurück.  
  
    -   `KeysNormalized`: Der gesamte Schlüssel Indizes sind monoton ohne Lücken, beginnend mit 0 (null).  
  
-   Alle Indizes müssen eindeutig sein. Es kann nicht doppelten Indizes vorhanden sein. Wenn diese Regel nicht befolgt werden, kann die Ausgabe Reihenfolge Datenschutzaspekten.  
  
-   Alle Indizes darf nicht negativ sein. Wenn diese Regel nicht befolgt werden, kann PLINQ/TPL Ausnahmen auslösen.  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Programmierung](../../../docs/standard/parallel-programming/index.md)  
 [Gewusst wie: Implementieren von dynamischen Partitionen](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)  
 [Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
