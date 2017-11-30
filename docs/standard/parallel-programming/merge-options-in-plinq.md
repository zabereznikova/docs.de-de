---
title: Mergeoptionen in PLINQ
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>Mergeoptionen in PLINQ
Wenn eine Abfrage als parallele, PLINQ Partitionen die Quellsequenz ausgeführt wird, damit mehrere Threads auf verschiedene Teile gleichzeitig, in der Regel in separaten Threads arbeiten können. Wenn die Ergebnisse in einem Thread genutzt werden z. B. in einem `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])-Schleife befindet, und klicken Sie dann die Ergebnisse von jedem Thread wieder zu einer einzigen Sequenz zusammengeführt werden müssen. Die Art der Mergereplikation, die PLINQ führt hängt die Operatoren, die in der Abfrage vorhanden sind. Operatoren, die vorgeben eine neue Bestellung auf die Ergebnisse müssen z. B. alle Elemente aus allen Threads gepuffert. Aus der Perspektive eines im Consumerthread (also auch die des Anwendungsbenutzers) kann eine vollständig gepufferte Abfrage ausführen, für einen deutlichen Zeitraum, bevor sie das erste Ergebnis erzeugt. Andere Operatoren sind teilweise standardmäßig gepuffert. Sie führen ihre Ergebnisse batchweise. Ein Operator, <xref:System.Linq.ParallelEnumerable.ForAll%2A> wird nicht standardmäßig gepuffert. Er gibt alle Elemente aus allen Threads sofort.  
  
 Mithilfe der <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> -Methode, wie im folgenden Beispiel gezeigt Sie bieten einen Hinweis für PLINQ, die die Art der Zusammenführung angibt.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Das vollständige Beispiel finden Sie unter [Vorgehensweise: Angeben von Zusammenführungsoptionen in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Wenn die betreffende Abfrage die angeforderte Option nicht unterstützt, wird die Option einfach ignoriert. In den meisten Fällen müssen Sie keinen Zusammenführungsoption für eine PLINQ-Abfrage angeben. Jedoch in einigen Fällen möglicherweise durch Testen und Messung, die am besten eine Abfrage in einem nicht standardmäßigen Modus ausgeführt wird. Eine übliche Verwendung dieser Option wird einen Block Zusammenführen-Operator, um seine Ergebnisse zu streamen, um eine Reaktionsgeschwindigkeit Benutzeroberfläche bereitstellen erzwungen.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 Die <xref:System.Linq.ParallelMergeOptions> Enumeration enthält die folgenden Optionen, die für unterstützte Abfrageformen angeben, wie die endgültige Ausgabe der Abfrage ausgegeben wird, wenn die Ergebnisse in einem Thread verarbeitet werden:  
  
-   `Not Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.NotBuffered> Option bewirkt, dass jedes verarbeitete Element aus jeder Thread zurückgegeben werden, sobald es erstellt wird. Dieses Verhalten ist analog zu "streaming" die Ausgabe. Wenn die <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> Operator fehlt in der Abfrage `NotBuffered` behält die Reihenfolge der Elemente der Quelle. Obwohl `NotBuffered` beginnt, die keine Ergebnisse aus, sobald sie verfügbar sind, die die Gesamtzeit für alle zu erzeugen, die Ergebnisse möglicherweise dennoch, nicht länger als mit einer der anderen Zusammenführungsoptionen.  
  
-   `Auto Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.AutoBuffered> Option bewirkt, dass die Abfrage zum Sammeln von Elementen in einen Puffer und klicken Sie dann in regelmäßigen Abständen den Pufferinhalt alle auf einmal auf dem Consumerthread. Dies ist analog zu und gibt die Quelldaten in "datenrationen" anstelle der "streamingverhalten" des `NotBuffered`. `AutoBuffered`dauert möglicherweise länger als `NotBuffered` um das erste Element im Consumerthread verfügbar zu machen. Die Größe des Puffers und das genaue Ausgabeverhalten sind nicht konfigurierbar und variieren abhängig von verschiedenen Faktoren ab, die für die Abfrage sind.  
  
-   `FullyBuffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.FullyBuffered> Option bewirkt, dass die Ausgabe der gesamten Abfrage gepuffert werden, bevor Sie eines der Elemente zurückgegeben werden. Wenn Sie diese Option verwenden, dauert länger vor das erste Element im Consumerthread verfügbar ist, jedoch möglicherweise dennoch die vollständigen Ergebnisse erzeugt werden schneller als mit den anderen Optionen.  
  
## <a name="query-operators-that-support-merge-options"></a>Abfrageoperatoren, die Unterstützung von Zusammenführungsoptionen  
 Die folgende Tabelle enthält die Operatoren, die alle Merge-Option-Modi, unterliegen den angegebenen zu unterstützen.  
  
|Operator|Beschränkungen|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Nicht geordnete Abfragen, die nur eine Array- oder Listenelemente Datenquelle verfügen.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Nicht geordnete Abfragen, die nur eine Array- oder Listenelemente Datenquelle verfügen.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Keine|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Keine|  
  
 Alle anderen PLINQ-Abfrageoperatoren möglicherweise vom Benutzer bereitgestellte Zusammenführungsoptionen ignorieren. Einige Abfrageoperatoren, z. B. <xref:System.Linq.ParallelEnumerable.Reverse%2A> und <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, alle Elemente können nicht ausgegeben werden, bis erzeugt und neu angeordnet wurden. Aus diesem Grund, dass bei <xref:System.Linq.ParallelMergeOptions> wird verwendet, in einer Abfrage, die einen Operator wie z. B. auch enthält <xref:System.Linq.ParallelEnumerable.Reverse%2A>, das Verhalten der Merge werden nicht in der Abfrage erst angewendet, nachdem dieser Operator Ergebnisse erzeugt hat.  
  
 Die Fähigkeit einiger Operatoren, Zusammenführungsoptionen verarbeiten hängt vom Typ der Quellsequenz, und gibt an, ob die <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> Operator weiter oben in der Abfrage verwendet wurde. <xref:System.Linq.ParallelEnumerable.ForAll%2A>ist immer <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; er seine Elemente sofort ergibt. <xref:System.Linq.ParallelEnumerable.OrderBy%2A>ist immer <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; es muss die gesamte Liste sortieren, bevor es ergibt.  
  
## <a name="see-also"></a>Siehe auch  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Gewusst wie: Angeben von Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
