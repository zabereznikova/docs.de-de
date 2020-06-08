---
title: Benutzerdefinierte Partitionierer für PLINQ und TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, partitioners
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
ms.openlocfilehash: 50553aab30d5a1bc5880ae0fe39c34508e57d0e5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276724"
---
# <a name="custom-partitioners-for-plinq-and-tpl"></a>Benutzerdefinierte Partitionierer für PLINQ und TPL

Einer der wesentlichen Schritte, um einen Vorgang für eine Datenquelle zu parallelisieren, ist das *Partitionieren* der Quelle in mehrere Abschnitte, auf die mehrere Threads gleichzeitig zugreifen können. PLINQ und die Task Parallel Library (TPL) stellen standardmäßige Partitionierer bereit, die transparent arbeiten, wenn Sie eine parallele Abfrage oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife schreiben. Für erweiterte Szenarien können Sie Ihren eigenen Partitionierer einbeziehen.

## <a name="kinds-of-partitioning"></a>Arten der Partitionierung

Es gibt viele Möglichkeiten, eine Datenquelle zu partitionieren. Bei den effizientesten Ansätzen wird die Quelle nicht physisch in mehrere Untersequenzen unterteilt, sondern mehrere Threads kooperieren beim Verarbeiten der ursprünglichen Quellsequenz. Für Arrays und andere indizierte Quellen wie <xref:System.Collections.IList>-Sammlungen, bei denen die Länge im Voraus bekannt ist, ist die *Bereichspartitionierung* die einfachste Art der Partitionierung. Jeder Thread empfängt eindeutige Indizes für Anfang und Ende, sodass er seinen Bereich der Quelle verarbeiten kann, ohne einen anderen Thread zu überschreiben oder selbst überschrieben zu werden. Der einzige Mehraufwand bei der Bereichspartitionierung ist die ursprüngliche Erstellung von Bereichen; danach ist keine zusätzliche Synchronisierung erforderlich. Aus diesem Grund liefert sie gute Leistung, solange die Arbeitsauslastung gleichmäßig verteilt wird. Ein Nachteil der Bereichspartitionierung ist, dass ein Thread, der seine Arbeit frühzeitig beendet, den anderen Threads keine Arbeit abnehmen kann.

Für verknüpfte Listen oder andere Sammlungen, deren Länge nicht bekannt ist, können Sie die *Blockpartitionierung* verwenden. Bei der Blockpartitionierung nutzt jeder Thread oder jede Aufgabe in einer parallelen Schleife oder Abfrage eine Anzahl von Quellelementen in einem Block, verarbeitet sie und kehrt dann zurück, um zusätzliche Elemente abzurufen. Mit dem Partitionierer wird sichergestellt, dass alle Elemente verteilt werden und keine Duplikate vorhanden sind. Ein Block kann eine beliebige Größe haben. Der in [Gewusst wie: Implementieren von dynamischen Partitionen](how-to-implement-dynamic-partitions.md) gezeigte Partitionierer erstellt z.B. Blöcke, die nur ein Element enthalten. Solange die Blöcke nicht zu groß sind, bewirkt diese Art der Partitionierung auch grundsätzlich einen Lastenausgleich, da die Zuweisung von Elementen zu Threads nicht vorgegeben ist. Allerdings macht sich der Synchronisierungsmehraufwand für den Partitionierer immer dann bemerkbar, wenn der Thread einen anderen Block abrufen muss. Das Ausmaß der Synchronisierung ist in diesen Fällen umgekehrt proportional zur Größe der Blöcke.

Im Allgemeinen ist die Bereichspartitionierung nur schneller, wenn die Ausführungszeit des Delegaten kurz bis mäßig ist, die Quelle über eine große Anzahl von Elementen verfügt und die gesamte Arbeit in jeder Partition ungefähr gleich ist. Die Blockpartitionierung ist daher im Allgemeinen in den meisten Fällen schneller. Bei Datenquellen mit einer kleinen Anzahl von Elementen oder längeren Ausführungszeiten für den Delegaten sind Leistung des Blocks und Bereichspartitionierung ungefähr gleich.

Die TPL-Partitionierer unterstützen auch eine dynamische Anzahl von Partitionen. Dies bedeutet, dass sie Partitionen während des Betriebs erstellen können, z.B. wenn die <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife eine neue Aufgabe erzeugt. Dieses Feature ermöglicht dem Partitionierer, zusammen mit der Schleife selbst zu skalieren. Dynamische Partitionierer bewirken auch grundsätzlich einen Lastenausgleich. Wenn Sie einen benutzerdefinierten Partitionierer erstellen, müssen Sie die Nutzung der dynamischen Partitionierung von einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Schleife aus unterstützen.

### <a name="configuring-load-balancing-partitioners-for-plinq"></a>Konfigurieren von Lastenausgleichspartitionierern für PLINQ

Mit einigen Überladungen der <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>-Methode können Sie einen Partitionierer für ein Array oder eine <xref:System.Collections.IList>-Datenquelle erstellen und festlegen, ob er versuchen soll, die Arbeitsauslastung zwischen den Threads auszugleichen. Wenn der Partitionierer für den Lastenausgleich konfiguriert ist, wird die Blockpartitionierung verwendet, und die Elemente werden bei Anforderung jeder Partition in kleinen Blöcken übergeben. Dieser Ansatz stellt sicher, dass alle Partitionen über zu verarbeitende Elemente verfügen, bis die gesamte Schleife oder Abfrage abgeschlossen ist. Eine weitere Überladung kann zur Lastenausgleichspartitionierung einer beliebigen <xref:System.Collections.IEnumerable>-Quelle dienen.

Lastenausgleich erfordert im Allgemeinen, dass die Partitionen relativ häufig Elemente vom Partitionierer anfordern. Dagegen kann ein Partitionierer, der statische Partitionierung durchführt, mithilfe der Bereichs- oder Blockpartitionierung alle Elemente jedem Partitionierer gleichzeitig zuweisen. Dies erfordert weniger Mehraufwand als der Lastenausgleich, aber die Ausführung dauert möglicherweise länger, wenn ein Thread am Ende deutlich mehr Arbeit bewältigen muss als die anderen. Wenn PLINQ eine IList oder ein Array übergeben wird, verwendet PLINQ standardmäßig immer die Bereichspartitionierung ohne Lastenausgleich. Um den Lastenausgleich für PLINQ zu aktivieren, verwenden Sie die `Partitioner.Create`-Methode, wie im folgenden Beispiel gezeigt.

[!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
[!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]

Ob in einem gegebenen Szenario der Lastenausgleich verwendet werden sollte, bestimmen Sie am besten, indem Sie durch Experimentieren und Messen feststellen, wie lange die Ausführung von Vorgängen unter repräsentativen Lasten und Computerkonfigurationen dauert. Die statische Partitionierung könnte z.B. möglicherweise auf einem Mehrkerncomputer mit nur wenigen Kernen für erhebliche Beschleunigung sorgen, doch bei Computern mit relativ vielen Kernen zu Verlangsamungen führen.

In der folgenden Tabelle sind die verfügbaren Optionen der <xref:System.Collections.Concurrent.Partitioner.Create%2A>-Methode aufgelistet. Diese Partitionierer sind nicht auf die Verwendung mit PLINQ oder <xref:System.Threading.Tasks.Task> beschränkt. Sie können auch mit jedem benutzerdefinierten parallelen Konstrukt verwendet werden.

|Überladung|Verwendet Lastenausgleich|
|--------------|-------------------------|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Always|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Wenn das boolesche Argument als „true“ angegeben wird|
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Wenn das boolesche Argument als „true“ angegeben wird|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nie|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nie|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nie|
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nie|

### <a name="configuring-static-range-partitioners-for-parallelforeach"></a>Konfigurieren von statischen Bereichspartitionierern für Parallel.ForEach

In einer <xref:System.Threading.Tasks.Parallel.For%2A>-Schleife wird der Inhalt der Schleife der Methode als Delegat bereitgestellt. Der Aufwand für den Aufruf dieses Delegaten ist mit dem des Aufrufs einer virtuellen Methode identisch. In einigen Szenarien könnte der Inhalt einer parallelen Schleife so klein sein, dass der Aufwand des Delegatenaufrufs in jeder Schleifeniteration signifikant wird. In solchen Situationen können Sie mithilfe einer der <xref:System.Collections.Concurrent.Partitioner.Create%2A>-Überladungen eine <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle von Bereichspartitionen über die Quellelemente erstellen. Dann übergeben Sie diese Sammlung von Bereichen an eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Methode, deren Inhalt aus einer regulären `for`-Schleife besteht. Dieser Ansatz hat den Vorteil, dass der Aufwand für den Delegatenaufruf nur einmal pro Bereich und nicht einmal pro Element anfällt. Das Grundmuster wird im folgenden Beispiel veranschaulicht.

[!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
[!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]

Jeder Thread in der Schleife empfängt ein eigenes <xref:System.Tuple%602>, das Start- und Endindexwerte im angegebenen untergeordneten Bereich enthält. Die innere `for`-Schleife verwendet die `fromInclusive`- und `toExclusive`-Werte für einen direkten Schleifendurchlauf über das Array oder <xref:System.Collections.IList>.

Mit einer der <xref:System.Collections.Concurrent.Partitioner.Create%2A>-Überladungen können Sie Größe und Anzahl der Partitionen angeben. Diese Überladung kann in Szenarien verwendet, wo die Arbeit pro Element so gering ist, dass auch ein einziger Aufruf einer virtuellen Methode pro Element eine merkliche Auswirkung auf die Leistung hat.

## <a name="custom-partitioners"></a>Benutzerdefinierte Partitionierer

In einigen Szenarien kann es empfehlenswert oder sogar erforderlich sein, dass Sie Ihren eigenen Partitionierer implementieren. Beispielsweise könnten Sie über eine benutzerdefinierte Auflistungsklasse verfügen, die Sie basierend auf Ihren Kenntnissen der internen Struktur der Klasse effizienter partitionieren können als der Standardpartitionierer. Vielleicht möchten Sie auch Bereichspartitionen mit unterschiedlichen Größen basierend auf Ihrer Kenntnis der Dauer der Verarbeitung von Elementen an verschiedenen Positionen in der Quellsammlung erstellen.

Leiten Sie zum Erstellen eines einfachen benutzerdefinierten Partitionierers eine Klasse von <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=nameWithType> ab, und überschreiben Sie die virtuellen Methoden, wie in der folgenden Tabelle beschrieben.

|||
|-|-|
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt eine IList(IEnumerator(TSource)) zurück. Jeder Arbeitsthread in der Schleife oder Abfrage kann `GetEnumerator` in der Liste zum Abrufen eines <xref:System.Collections.Generic.IEnumerator%601> über eine unterschiedliche Partition aufrufen.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Geben Sie `true` zurück, wenn Sie <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> implementieren, andernfalls `false`.|
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>`true` ist, kann diese Methode optional anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> aufgerufen werden.|

Wenn die Ergebnisse sortierbar sein müssen, oder Sie indizierten Zugriff auf die Elemente benötigen, leiten Sie von <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> ab, und überschreiben Sie dessen virtuelle Methoden wie in der folgenden Tabelle beschrieben.

|||
|-|-|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt eine `IList(IEnumerator(TSource))` zurück. Jeder Arbeitsthread in der Schleife oder Abfrage kann `GetEnumerator` in der Liste zum Abrufen eines <xref:System.Collections.Generic.IEnumerator%601> über eine unterschiedliche Partition aufrufen.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Geben Sie `true` zurück, wenn Sie <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A> implementieren; andernfalls „false“.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|In der Regel wird hiermit <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> aufgerufen.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>`true` ist, kann diese Methode optional anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> aufgerufen werden.|

Die folgende Tabelle enthält weitere Details zur Implementierung der <xref:System.Collections.Concurrent.OrderablePartitioner%601>-Klasse durch die drei Arten von Lastenausgleichspartitionierern.

|Methode/Eigenschaft|IList/Array ohne Lastenausgleich|IList/Array mit Lastenausgleich|IEnumerable|
|----------------------|-------------------------------------------|----------------------------------------|-----------------|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Verwendet Bereichspartitionierung|Verwendet optimierte Blockpartitionierung für Listen für die angegebene partitionCount|Verwendet Blockpartitionierung durch Erstellen einer statischen Anzahl von Partitionen|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=nameWithType>|Löst nicht unterstützte Ausnahme aus|Verwendet optimierte Blockpartitionierung für Listen und dynamische Partitionen|Verwendet Blockpartitionierung durch Erstellen einer dynamischen Anzahl von Partitionen.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Gibt `true` zurück.|Gibt `false` zurück.|Gibt `false` zurück.|
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Gibt `false` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|

### <a name="dynamic-partitions"></a>Dynamische Partitionen

Wenn Sie beabsichtigen, den Partitionierer in einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>-Methode zu verwenden, müssen Sie eine dynamische Anzahl von Partitionen zurückgeben können. Dies bedeutet, dass der Partitionierer bei Bedarf jederzeit während der Schleifenausführung einen Enumerator für eine neue Partition bereitstellen kann. Im Wesentlichen wird immer dann, wenn die Schleife eine neue parallele Aufgabe hinzufügt, eine neue Partition für diese Aufgabe angefordert. Wenn die Daten sortierbar sein müssen, leiten Sie von <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> ab, sodass jedem Element in jeder Partition ein eindeutiger Index zugewiesen wird.

Weitere Informationen und ein Beispiel finden Sie unter [Gewusst wie: Implementieren von dynamischen Partitionen](how-to-implement-dynamic-partitions.md).

### <a name="contract-for-partitioners"></a>Vertrag für Partitionierer

Wenn Sie einen benutzerdefinierten Partitionierer implementieren, befolgen Sie diese Richtlinien, um ordnungsgemäße Interaktion mit PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> in der TPL sicherzustellen:

- Wenn <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> mit einem Argument von 0 (null) oder weniger für `partitionsCount` aufgerufen wird, soll <xref:System.ArgumentOutOfRangeException> ausgelöst werden. Obwohl PLINQ und TPL niemals eine `partitionCount` gleich 0 übergeben werden, sollten Sie dennoch einen Schutz vor dieser Möglichkeit einbauen.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> sollten stets eine `partitionsCount` Anzahl von Partitionen zurückgeben. Wenn dem Partitionierer keine Daten mehr zur Verfügung stehen, sodass er nicht mehr so viele Partitionen wie angefordert erstellen kann, sollte die Methode für jede der verbleibenden Partitionen einen leeren Enumerator zurückgeben. Andernfalls löst sowohl PLINQ als auch TPL eine <xref:System.InvalidOperationException> aus.

- <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> sollten niemals `null` (`Nothing` in Visual Basic) zurückgeben. Wenn dies doch der Fall ist, lösen PLINQ/TPL eine <xref:System.InvalidOperationException> aus.

- Partitionen zurückgebende Methoden sollten immer Partitionen zurückgeben, die die Datenquelle vollständig und eindeutig aufzählen können. Sofern nicht ausdrücklich vom Entwurf des Partitionierers gefordert, dürfen in der Datenquelle keine Duplikate oder übersprungenen Elemente enthalten sein. Wenn diese Regel nicht befolgt wird, kann die Ausgabereihenfolge durcheinander geraten.

- Die folgenden booleschen Getter müssen immer genau die folgenden Werte zurückgeben, damit die Reihenfolge der Ausgabe nicht durcheinander gerät:

  - `KeysOrderedInEachPartition`: Jede Partition gibt Elemente mit zunehmenden Schlüsselindizes zurück.

  - `KeysOrderedAcrossPartitions`: Für alle zurückgegebenen Partitionen sind die Schlüsselindizes in Partition *i* höher als diejenigen in Partition *i*-1.

  - `KeysNormalized`: Alle Schlüsselindizes nehmen beginnend mit 0 (null) ohne Lücken monoton zu.

- Alle Indizes müssen eindeutig sein. Es darf keine doppelten Indizes geben. Wenn diese Regel nicht befolgt wird, kann die Ausgabereihenfolge durcheinander geraten.

- Alle Indizes dürfen nicht negativ sein. Wenn diese Regel nicht befolgt wird, kann PLINQ/TPL Ausnahmen auslösen.

## <a name="see-also"></a>Weitere Informationen

- [Parallele Programmierung](index.md)
- [Gewusst wie: Implementieren von dynamischen Partitionen](how-to-implement-dynamic-partitions.md)
- [Gewusst wie: Implementieren eines Partitionierers für statisches Partitionieren](how-to-implement-a-partitioner-for-static-partitioning.md)
