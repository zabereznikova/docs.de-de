---
title: "Custom Partitioners for PLINQ and TPL | Microsoft Docs"
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
  - "tasks, partitioners"
ms.assetid: 96153688-9a01-47c4-8430-909cee9a2887
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Custom Partitioners for PLINQ and TPL
Um einen Vorgang in einer Datenquelle zu parallelisieren, ist einer der wesentlichen Schritte das *Partitionieren* der Quelle in mehrere Abschnitte, auf die gleichzeitig von mehreren Threads zugegriffen werden kann.  PLINQ und die Task Parallel Library \(TPL\) bieten standardmäßige Partitionierer, die transparent funktionieren, wenn Sie eine parallele Abfrage oder <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife schreiben.  Für komplexere Szenarien können Sie Ihren eigenen Partitionierer verwenden.  
  
## Arten der Partitionierung  
 Es gibt viele Möglichkeiten, eine Datenquelle zu partitionieren.  Bei den effizientesten Methoden kooperieren mehrere Threads, um die ursprüngliche Quellsequenz zu verarbeiten, anstatt die Quelle physisch in mehrere Untersequenzen zu trennen.  Für Arrays und andere indizierte Quellen wie z. B. <xref:System.Collections.IList>\-Auflistungen, in denen die Länge im Voraus bekannt ist, ist die *Bereichspartitionierung* die einfachste Art der Partitionierung.  Jeder Thread empfängt eindeutige Anfangs\- und Endindizes, damit der Bereich der Quelle verarbeitet werden kann, ohne dass dieser bzw. ein anderer Thread überschrieben wird.  Der einzige durch Bereichspartitionierung entstehende Mehraufwand ist die ursprüngliche Erstellung von Bereichen. Danach ist keine zusätzliche Synchronisierung erforderlich.  Daher kann eine gute Leistung erzielt werden, solange die Arbeitsauslastung gleichmäßig geteilt wird.  Ein Nachteil der Bereichspartitionierung ist, dass bei frühzeitigem Beenden eines Threads für die anderen Threads keine Unterstützung bei deren Arbeit mehr zur Verfügung steht.  
  
 Für verknüpfte Listen oder andere Auflistungen, deren Länge nicht bekannt ist, können Sie *Blockpartitionierung* verwenden.  Bei der Blockpartitionierung verwendet jeder Thread oder jede Aufgabe in einer parallelen Schleife oder Abfrage eine gewisse Anzahl von Quellelementen in einem Block, verarbeitet diese und ruft anschließend zusätzliche Elemente ab.  Der Partitionierer stellt sicher, dass alle Elemente verteilt werden, und dass keine Duplikate vorhanden sind.  Ein Block kann jede beliebige Größe besitzen.  Der Partitionierer, der in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md) veranschaulicht wird, erstellt z. B. Ausschnitte, die nur ein Element enthalten.  Solange die Blöcke nicht zu groß sind, sorgt diese Art von Partitionierung grundsätzlich für Lastenausgleich, da die Zuweisung von Elementen zu Threads nicht vorgegeben ist.  Allerdings tritt beim Partitionierer ein Synchronisierungsmehraufwand auf, wenn der Thread einen weiteren Block abrufen muss.  Der Synchronisierungsaufwand in diesen Fällen ist umgekehrt proportional zur Größe der Blöcke.  
  
 Im Allgemeinen ist die Bereichspartitionierung nur dann schneller, wenn die Ausführungszeit des Delegaten kurz oder von mittlerer Länge ist, die Quelle eine große Anzahl von Elementen enthält und die gesamte Arbeitslast jeder Partition ungefähr gleich ist.  Blockpartitionierung ist daher im Allgemeinen in den meisten Fällen schneller.  In Quellen mit einer geringen Anzahl von Elementen oder längeren Ausführungszeiten für den Delegaten ist die Leistung der Block\- und Bereichspartitionierung ungefähr gleich.  
  
 Die TPL\-Partitionierer unterstützen auch eine dynamische Anzahl von Partitionen.  Dies bedeutet, dass Partitionen direkt erstellt werden können, z. B., wenn die <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife eine neue Aufgabe erzeugt.  Diese Funktion ermöglicht dem Partitionierer eine gemeinsame Skalierung mit der Schleife.  Dynamische Partitionierer sorgen zudem grundsätzlich für Lastenausgleich.  Wenn Sie einen benutzerdefinierten Partitionierer erstellen, müssen Sie dynamische Partitionierung unterstützen, um eine Verwendung von einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Schleife zu gewährleisten.  
  
### Konfigurieren von Lastenausgleichspartitionierern für PLINQ  
 Einige Überladungen der <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName>\-Methode ermöglichen die Erstellung eines Partitioners für ein Array oder eine <xref:System.Collections.IList>\-Quelle und die Angabe, ob die Arbeitslast zwischen den Threads gleichmäßig verteilt werden soll.  Wenn der Partitionierer für Lastenausgleich konfiguriert wird, wird Blockpartitionierung verwendet, und die Elemente werden gemäß Anforderung in kleinen Blöcken an jede Partition übergeben.  Durch diese Methode wird gewährleistet, dass alle Partitionen zu verarbeitende Elemente enthalten, bis die gesamte Schleife oder Abfrage abgeschlossen ist.  Mit einer zusätzlichen Überladung kann Lastenausgleichspartitionierung einer beliebigen <xref:System.Collections.IEnumerable>\-Quelle bereitgestellt werden.  
  
 Im Allgemeinen erfordert Lastenausgleich, dass die Partitionen relativ häufig Elemente vom Partitionierer anfordern.  Im Gegensatz dazu kann ein Partitionierer, der eine statische Partitionierung vornimmt, jedem Partitionierer sofort alle Elemente zuweisen, wenn er entweder Bereichs\- oder Blockpartitionierung verwendet.  Dies erfordert weniger Aufwand als Lastenausgleich, doch die Ausführung kann mehr Zeit in Anspruch nehmen, wenn in einem Thread deutlich mehr Arbeit als in den anderen Threads anfällt.  Wenn eine IList oder ein Array an PLINQ übergeben wird, wird immer Bereichspartitionierung ohne Lastenausgleich verwendet.  Um Lastenausgleich für PLINQ zu aktivieren, verwenden Sie die `Partitioner.Create`\-Methode \(siehe folgendes Beispiel\).  
  
 [!code-csharp[TPL_Partitioners#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#02)]
 [!code-vb[TPL_Partitioners#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionsnippets_vb.vb#02)]  
  
 Die beste Möglichkeit, zu bestimmen, ob in einem gegebenen Szenario Lastenausgleich verwendet werden soll, besteht darin durch Experimentieren zu ermitteln, wie viel Zeit Vorgänge bei repräsentativer Auslastung und mit entsprechenden Computerkonfigurationen in Anspruch nehmen.  Statische Partitionierung kann z. B. für beträchtliche Geschwindigkeitssteigerungen auf einem Multikerncomputer sorgen, der nur einige Kerne besitzt, doch auf Computern mit verhältnismäßig vielen Kernen kann es zu einer Verlangsamung kommen.  
  
 In der folgenden Tabelle sind die verfügbaren Überladungen der <xref:System.Collections.Concurrent.Partitioner.Create%2A>\-Methode aufgelistet.  Für diese Partitionierer gilt keine Einschränkung, dass sie nur mit PLINQ oder <xref:System.Threading.Tasks.Task> verwendet werden dürfen.  Sie können auch mit jedem benutzerdefinierten parallelen Konstrukt verwendet werden.  
  
|Überladung|Verwendet Lastenausgleich|  
|----------------|-------------------------------|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>|Immer|  
|[Create\<TSource\>\(TSource\<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28%60%600%5B%5D%2CSystem.Boolean%29>|Wenn das boolesche Argument als "true" \(wahr\) angegeben wird|  
|<xref:System.Collections.Concurrent.Partitioner.Create%60%601%28System.Collections.Generic.IList%7B%60%600%7D%2CSystem.Boolean%29>|Wenn das boolesche Argument als "true" \(wahr\) angegeben wird|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int32%2CSystem.Int32%2CSystem.Int32%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%29>|Nie|  
|<xref:System.Collections.Concurrent.Partitioner.Create%28System.Int64%2CSystem.Int64%2CSystem.Int64%29>|Nie|  
  
### Konfigurieren von statischen Bereichspartitionierern für "Parallel.ForEach"  
 In einer <xref:System.Threading.Tasks.Parallel.For%2A>\-Schleife wird der Text der Schleife für die Methode als Delegat bereitgestellt.  Der Aufwand für einen Delegatenaufruf entspricht ungefähr dem für einen virtuellen Methodenaufruf.  In einigen Szenarien ist der Text einer parallelen Schleife möglicherweise so klein, dass der Aufwand für einen Delegataufruf in jeder Schleifeniteration ein beträchtliches Ausmaß erreicht.  In solchen Situationen können Sie mit einer der <xref:System.Collections.Concurrent.Partitioner.Create%2A>\-Überladungen ein <xref:System.Collections.Generic.IEnumerable%601>\-Objekt von Bereichspartitionen über den Quellelementen erstellen.  Anschließend können Sie diese Bereichsauflistung an eine <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Methode übergeben, deren Text aus einer regulären `for`\-Schleife besteht.  Der Vorteil dieser Methode liegt darin, dass der Aufwand für einen Delegataufruf nur einmal pro Bereich und nicht einmal pro Element anfällt.  Das grundlegende Muster wird im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Jeder Thread in der Schleife empfängt ein eigenes <xref:System.Tuple%602>\-Objekt, das die Anfangs\- und Endindexwerte im angegebenen Teilbereich enthält.  Die innere `for`\-Schleife verwendet den `fromInclusive`\-Wert und den `toExclusive`\-Wert, um das Array oder das <xref:System.Collections.IList>\-Objekt direkt in einer Schleife zu durchlaufen.  
  
 Eine der <xref:System.Collections.Concurrent.Partitioner.Create%2A>\-Überladungen ermöglicht die Angabe der Größe und der Anzahl der Partitionen.  Diese Überladung kann in Szenarien verwendet werden, in denen die Arbeit pro Element so geringfügig ist, dass sogar ein einzelner virtueller Methodenaufruf pro Element beträchtliche Auswirkungen auf die Leistung hat.  
  
## Benutzerdefinierte Partitionierer  
 In einigen Szenarien kann es empfehlenswert oder sogar erforderlich sein, einen eigenen Partitionierer zu implementieren.  Beispiel: Sie besitzen eine benutzerdefinierte Auflistungsklasse, die Sie aufgrund Ihrer Kenntnisse der internen Struktur der Klasse effizienter als Standardpartitionierer partitionieren können.  Möglicherweise möchten Sie auch unter Berücksichtigung Ihrer Kenntnis der Verarbeitungsdauer von Elementen an verschiedenen Orten in der Quellauflistung unterschiedlich große Bereichspartitionen erstellen.  
  
 Zum Erstellen eines grundlegenden benutzerdefinierten Partitioners muss eine Klasse von <xref:System.Collections.Concurrent.Partitioner%601?displayProperty=fullName> abgeleitet werden, und die virtuellen Methoden müssen überschrieben werden. Eine entsprechende Beschreibung finden Sie in der folgenden Tabelle.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt einen IList\(IEnumerator\(TSource\)\) zurück.  Jeder Arbeitsthread in der Schleife oder Abfrage kann `GetEnumerator` in der Liste aufrufen, um über eine unterschiedliche Partition einen <xref:System.Collections.Generic.IEnumerator%601> abzurufen.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Gibt `true` zurück, wenn Sie <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>implementieren, andernfalls `false`.|  
|<xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> den Wert `true` ergibt, kann optional diese Methode anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> aufgerufen werden.|  
  
 Wenn die Ergebnisse sortierbar sein müssen, oder wenn Sie indizierten Zugriff auf die Elemente benötigen, führen Sie eine Ableitung von <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> aus, und überschreiben Sie die virtuellen Methoden entsprechend der Beschreibung in der folgenden Tabelle.  
  
|||  
|-|-|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetPartitions%2A>|Diese Methode wird einmal vom Hauptthread aufgerufen und gibt einen `IList(IEnumerator(TSource))` zurück.  Jeder Arbeitsthread in der Schleife oder Abfrage kann `GetEnumerator` in der Liste aufrufen, um über eine unterschiedliche Partition einen <xref:System.Collections.Generic.IEnumerator%601> abzurufen.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Gibt `true` zurück, wenn Sie <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>implementieren, andernfalls "false".|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetDynamicPartitions%2A>|In der Regel wird dabei nur <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> aufgerufen.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A>|Wenn <xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A> den Wert `true` ergibt, kann optional diese Methode anstelle von <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> aufgerufen werden.|  
  
 Die folgende Tabelle enthält weitere Details darüber, wie die drei Arten von Lastenausgleichspartitionierern die <xref:System.Collections.Concurrent.OrderablePartitioner%601>\-Klasse implementieren.  
  
|Methode\/Eigenschaft|IList\/Array ohne Lastenausgleich|IList\/Array mit Lastenausgleich|IEnumerable|  
|--------------------------|---------------------------------------|--------------------------------------|-----------------|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>|Verwendet Bereichspartitionierung|Verwendet Blockpartitionierung, die für Listen für die angegebene Partitionsanzahl \(partitionCount\) optimiert ist|Verwendet Blockpartitionierung durch Erstellen einer statischen Anzahl von Partitionen.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A?displayProperty=fullName>|Löst eine nicht unterstützte Ausnahme aus|Verwendet für Listen und dynamische Partitionen optimierte Blockpartitionierung|Verwendet Blockpartitionierung durch Erstellen einer dynamischen Anzahl von Partitionen.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedInEachPartition%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysOrderedAcrossPartitions%2A>|Gibt `true` zurück.|Gibt `false` zurück.|Gibt `false` zurück.|  
|<xref:System.Collections.Concurrent.OrderablePartitioner%601.KeysNormalized%2A>|Gibt `true` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
|<xref:System.Collections.Concurrent.Partitioner%601.SupportsDynamicPartitions%2A>|Gibt `false` zurück.|Gibt `true` zurück.|Gibt `true` zurück.|  
  
### Dynamische Partitionen  
 Wenn Sie den Partitionierer in einer <xref:System.Threading.Tasks.Parallel.ForEach%2A>\-Methode verwenden möchten, muss eine dynamische Anzahl von Partitionen zurückgegeben werden können.  Dies bedeutet, dass der Partitionierer jederzeit während der Schleifenausführung für eine neue Partition bedarfsabhängig einen Enumerator angeben kann.  Grundsätzlich wird beim Hinzufügen einer neuen parallelen Aufgabe durch die Schleife eine neue Partition für diese Aufgabe angefordert.  Wenn die Daten sortierbar sein müssen, nehmen Sie eine Ableitung von <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName> vor, damit jedem Element in jeder Partition ein eindeutiger Index zugewiesen wird.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
### Vertrag für Partitionierer  
 Wenn Sie einen benutzerdefinierten Partitionierer implementieren, gehen Sie folgendermaßen vor, um eine ordnungsgemäße Interaktion mit PLINQ und <xref:System.Threading.Tasks.Parallel.ForEach%2A> in der TPL sicherzustellen:  
  
-   Wenn <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> mit einem Argument kleiner oder gleich 0 \(null\) für `partitionsCount` aufgerufen wird, wird <xref:System.ArgumentOutOfRangeException> ausgelöst.  Obwohl PLINQ und TPL niemals eine `partitionCount` gleich 0 übergeben, empfiehlt es sich trotzdem, sich davor zu schützen.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A> und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A> geben immer die folgende Partitionsanzahl zurück: `partitionsCount` Wenn dem Partitionierer keine Daten mehr zur Verfügung stehen und nicht so viele Partitionen wie gewünscht erstellt werden können, wird von dieser Methode für jede der verbleibenden Partitionen ein leerer Enumerator zurückgegeben.  Andernfalls lösen sowohl PLINQ als auch TPL eine <xref:System.InvalidOperationException> aus.  
  
-   <xref:System.Collections.Concurrent.Partitioner%601.GetPartitions%2A>, <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderablePartitions%2A>, <xref:System.Collections.Concurrent.Partitioner%601.GetDynamicPartitions%2A> und <xref:System.Collections.Concurrent.OrderablePartitioner%601.GetOrderableDynamicPartitions%2A> geben niemals `null` zurück \(`Nothing` in Visual Basic\).  Wenn dies doch der Fall ist, löst PLINQ\/TPL eine <xref:System.InvalidOperationException> aus.  
  
-   Methoden, die Partitionen zurückgeben, geben immer Partitionen zurück, die die Datenquelle vollständig und eindeutig auflisten können.  Es darf keine doppelten Vorkommen in der Datenquelle oder übersprungene Elementen geben, sofern dies die Struktur des Partitionierers nicht ausdrücklich erfordert.  Wenn diese Regel nicht befolgt wird, gerät die Ausgabereihenfolge möglicherweise durcheinander.  
  
-   Die folgenden booleschen Getter müssen immer exakt die folgenden Werte zurückgeben, damit die Ausgabereihenfolge nicht durcheinander gerät:  
  
    -   `KeysOrderedInEachPartition`: Jede Partition gibt Elemente mit zunehmenden Schlüsselindizes zurück.  
  
    -   `KeysOrderedAcrossPartitions`: Für alle Partitionen, die zurückgegeben werden, sind die Schlüsselindizes in Partition *i* höher als die Schlüsselindizes in Partition *i*\-1.  
  
    -   `KeysNormalized`: Alle Schlüsselindizes steigen monoton ohne Lücken an \(ausgehend von 0 \(null\)\).  
  
-   Alle Indizes müssen eindeutig sein.  Es darf keine doppelten Indizes geben.  Wenn diese Regel nicht befolgt wird, gerät die Ausgabereihenfolge möglicherweise durcheinander.  
  
-   Alle Indizes müssen nicht negativ sein.  Wenn diese Regel nicht befolgt wird, löst PLINQ\/TPL möglicherweise Ausnahmen aus.  
  
## Siehe auch  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)