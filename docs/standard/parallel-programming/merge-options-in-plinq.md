---
title: "Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, merge options"
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Merge Options in PLINQ
Wenn eine Abfrage parallel ausgeführt wird, partitioniert PLINQ die Quellsequenz, damit mehrere Threads verschiedene Teile gleichzeitig, zumeist in separaten Threads bearbeiten können.  Wenn die Ergebnisse in einem Thread genutzt werden sollen, z. B. in einer `foreach`\-Schleife \(`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), müssen die Ergebnisse von jedem Thread wieder in einer Sequenz zusammengeführt werden.  Die Art der von PLINQ ausgeführten Zusammenführung hängt von den Operatoren in der Abfrage ab.  Bei Operatoren, die eine neue Reihenfolge der Ergebnissen erzeugen, müssen beispielsweise alle Elemente aus allen Threads gepuffert werden.  Aus Sicht des Consumerthreads \(der Thread des Anwendungsbenutzers\) kann die Ausführung einer vollständig gepufferten Abfrage relativ lange dauern, bevor erste Ergebnisse erzielt werden.  Andere Operatoren werden standardmäßig teilweise gepuffert, d. h. sie geben Ergebnisse in Batches aus.  Ein Operator, <xref:System.Linq.ParallelEnumerable.ForAll%2A>, wird standardmäßig nicht gepuffert.  Er gibt alle Elemente aus allen Thread unmittelbar aus.  
  
 Mit der <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>\-Methode können Sie einen Hinweis in PLINQ angeben, der die durchzuführende Art der Zusammenführung kennzeichnet, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Das vollständige Beispiel finden Sie unter [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Wenn die konkrete Abfrage die angeforderte Option nicht unterstützt, wird die Option ignoriert.  In den meisten Fällen müssen Sie keine Zusammenführungsoption für eine PLINQ\-Abfrage angeben.  In einigen Fällen finden Sie mittels Tests und Messung jedoch ggf. heraus, dass eine Abfrage am besten in einem nicht standardmäßigen Modus ausgeführt wird.  Diese Option wird häufig verwendet, wenn die Ergebnisse eines blockzusammenführenden Operators per Streaming übertragen werden sollen, um eine Benutzeroberfläche mit kürzeren Reaktionszeiten bereitzustellen.  
  
## ParallelMergeOptions  
 Die <xref:System.Linq.ParallelMergeOptions>\-Enumeration schließt die folgenden Optionen ein, die für unterstützte Abfrageformen angeben, wie die abschließende Ausgabe der Abfrage ausgegeben wird, wenn die Ergebnisse in einem Thread genutzt werden:  
  
-   `Not Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions>\-Option bewirkt, dass jedes verarbeitete Element von jedem Thread zurückgegeben wird, sobald es erzeugt wurde.  Dieses Verhalten entspricht somit einem "Streaming" der Ausgabe.  Wenn der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>\-Operator in der Abfrage vorhanden ist, behält `NotBuffered` die Reihenfolge der Quellelemente bei.  Obwohl `NotBuffered` Ergebnisse ausgibt, sobald diese verfügbar sind, kann die insgesamt zum Erzeugen der Ergebnisse benötigte Zeit länger sein als mit einer der anderen Zusammenführungsoptionen.  
  
-   `Auto Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions> \- Option bewirkt, dass die Abfrage Elemente in einem Puffer sammelt und den Pufferinhalt zum Consumerthread dann in regelmäßigen Abständen als Ganzes zu führen.  Dies entspricht einer Ausgabe der Quelldaten in "Blöcken" anstelle des bei `NotBuffered` verwendeten "Streamings".  `AutoBuffered` benötigt zum Bereitstellen des ersten Elements im Consumerthread möglicherweise länger als `NotBuffered`.  Die Größe des Puffers und das genaue Ausgabeverhalten können nicht konfiguriert werden und variieren abhängig von verschiedenen, die Abfrage betreffenden Faktoren.  
  
-   `FullyBuffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions>\-Option bewirkt, dass die Ausgabe der gesamten Abfrage gepuffert wird, bevor eines der Elemente ausgegeben wird.  Wenn Sie diese Option verwenden, dauert es ggf. länger, bis das erste Element im Consumerthread bereitgestellt wird, das Gesamtergebnis wird allerdings meist schneller erzeugt als bei den anderen Optionen.  
  
## Abfrageoperatoren mit Unterstützung von Zusammenführungsoptionen  
 In der folgenden Tabelle sind die Operatoren, die, abhängig von den angegebenen Beschränkungen, alle Zusammenführungsoptionsmodi unterstützen.  
  
|Operator|Beschränkungen|  
|--------------|--------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Nicht geordnete Abfragen, die nur über eine Array\- oder Listenquelle verfügen|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Nicht geordnete Abfragen, die nur über eine Array\- oder Listenquelle verfügen|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Kein|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Kein|  
  
 Alle anderen PLINQ\-Abfrageoperatoren ignorieren ggf. vom Benutzer bereitgestellte Zusammenführungsoptionen.  Einige Abfrageoperatoren, z. B. <xref:System.Linq.ParallelEnumerable.Reverse%2A> und <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, können Elemente erst ausgeben, wenn alle Elemente erzeugt und neu sortiert wurden.  Wenn <xref:System.Linq.ParallelMergeOptions> in einer Abfrage verwendet wird, die zudem einen Operator wie <xref:System.Linq.ParallelEnumerable.Reverse%2A> enthält, wird das Zusammenführungsverhalten in der Abfrage erst angewendet, nachdem dieser Operator Ergebnisse erzeugt hat.  
  
 Die Fähigkeit einiger Operatoren, Zusammenführungsoptionen zu verarbeiten, hängt vom Typ der Quellsequenz und von der vorherigen Verwendung des <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>\-Operators in der Abfrage ab.  <xref:System.Linq.ParallelEnumerable.ForAll%2A> lautet immer <xref:System.Linq.ParallelMergeOptions>, d. h., die Elemente werden unmittelbar ausgegeben.  <xref:System.Linq.ParallelEnumerable.OrderBy%2A> lautet immer <xref:System.Linq.ParallelMergeOptions>, d. h., die Elemente werden erst ausgegeben, nachdem die gesamte Liste sortiert wurde.  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)