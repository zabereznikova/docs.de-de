---
title: Mergeoptionen in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
ms.openlocfilehash: 623466e0e960ea991ae92e5de432171b70bad1d2
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588622"
---
# <a name="merge-options-in-plinq"></a>Mergeoptionen in PLINQ
Wenn eine Abfrage als parallel ausgeführt wird, partitioniert PLINQ die Quellsequenz, sodass mehrere Threads gleichzeitig an verschiedenen Teilen arbeiten können, in der Regel an separaten Threads. Wenn die Ergebnisse in einem einzelnen Thread verarbeitet werden sollen, z.B. in einer `foreach`-Schleife (`For Each` in Visual Basic), müssen die Ergebnisse der einzelnen Threads wieder zu einer einzigen Sequenz zusammengeführt werden. Welche Art der Zusammenführung PLINQ ausführt, hängt von den Operatoren ab, die in der Abfrage vorhanden sind. Beispielsweise müssen Operatoren, die die Ergebnisse in eine neue Reihenfolge stellen, alle Elemente aus allen Threads puffern. Aus der Perspektive des nutzenden Threads (die mit der des Anwendungsbenutzers identisch ist) könnte eine vollständig gepufferte Abfrage für einen beachtlichen Zeitraum ausgeführt werden, bevor sie das erste Ergebnis liefert. Andere Operatoren sind standardmäßig teilweise gepuffert. Sie stellen ihre Ergebnisse batchweise bereit. Ein Operator, <xref:System.Linq.ParallelEnumerable.ForAll%2A>, wird nicht standardmäßig gepuffert. Er stellt alle Elemente aus allen Threads sofort bereit.  
  
 Wie im folgenden Beispiel gezeigt, können Sie mithilfe der <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>-Methode einen Hinweis für PLINQ bereitstellen, der die Art der Zusammenführung angibt.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Das vollständige Beispiel finden Sie unter [Gewusst wie: Angeben von Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Wenn die betreffende Abfrage die angeforderte Option nicht unterstützen kann, wird die Option einfach ignoriert. In den meisten Fällen müssen Sie keine Mergeoption für eine PLINQ-Abfrage angeben. In einigen Fällen stellen Sie jedoch möglicherweise durch Testen und Messen fest, dass eine Abfrage am besten in einem nicht standardmäßigen Modus ausgeführt wird. Eine übliche Verwendung dieser Option ist, zu erzwingen, dass ein Blockzusammenführungs-Operator seine Ergebnisse streamt, um eine reaktionsfreudigere Benutzeroberfläche bereitzustellen.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 Die <xref:System.Linq.ParallelMergeOptions>-Enumeration enthält die folgenden Optionen, die für unterstützte Abfrageformen angeben, wie die endgültige Ausgabe der Abfrage bereitgestellt wird, wenn die Ergebnisse in einem einzelnen Thread verarbeitet werden:  
  
- `Not Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.NotBuffered>-Option bewirkt, dass jedes verarbeitete Element aus jedem Thread zurückgegeben wird, sobald seine Verarbeitung abgeschlossen ist. Dieses Verhalten ist analog zum „Streamen“ der Ausgabe. Wenn der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Operator in der Abfrage vorhanden ist, behält `NotBuffered` die Reihenfolge der Quellelemente bei. Obwohl `NotBuffered` beginnt, Ergebnisse bereitzustellen, sobald sie verfügbar sind, kann die Gesamtzeit zum Erzeugen aller Ergebnisse dennoch länger sein als mit einer der anderen Mergeoptionen.  
  
- `Auto Buffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.AutoBuffered>-Option bewirkt, dass die Abfrage Elemente in einem Puffer sammelt und dann in regelmäßigen Abständen den gesamten Pufferinhalt für den verarbeitenden Thread bereitstellt. Dies ist analog zum Bereitstellen der Quelldaten in „Blöcken“ statt Verwendung des „Streamverhaltens“ von `NotBuffered`. `AutoBuffered` benötigt möglicherweise mehr Zeit als `NotBuffered`, um das erste Element für den verarbeitenden Thread verfügbar zu machen. Die Größe des Puffers und das genaue Ausgabeverhalten sind nicht konfigurierbar und variieren abhängig von verschiedenen, von der Abfrage abhängigen Faktoren.  
  
- `FullyBuffered`  
  
     Die <xref:System.Linq.ParallelMergeOptions.FullyBuffered>-Option bewirkt, dass die Ausgabe der gesamten Abfrage gepuffert wird, bevor eines der Elemente bereitgestellt wird. Wenn Sie diese Option verwenden, kann es länger dauern, bis das erste Element für den verarbeitenden Thread verfügbar ist, aber die vollständigen Ergebnisse könnten dennoch schneller erzeugt werden als mit den anderen Optionen.  
  
## <a name="query-operators-that-support-merge-options"></a>Abfrageoperatoren, die Mergeoptionen unterstützen  
 Die folgende Tabelle enthält die Operatoren, die alle Mergeoptionen unterstützen, und etwaige Einschränkungen.  
  
|Operator|Beschränkungen|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Nicht geordnete Abfragen, die nur über eine Array- oder Listenquelle verfügen.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Nicht geordnete Abfragen, die nur über eine Array- oder Listenquelle verfügen.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Keiner|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Keiner|  
  
 Alle anderen PLINQ-Abfrageoperatoren werden möglicherweise von durch den Benutzer bereitgestellten Mergeoptionen ignoriert. Einige Abfrageoperatoren, z.B. <xref:System.Linq.ParallelEnumerable.Reverse%2A> und <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, können erst dann Elemente bereitstellen, wenn alle erzeugt und neu angeordnet wurden. Wenn <xref:System.Linq.ParallelMergeOptions> in einer Abfrage verwendet wird, die auch einen Operator wie z.B. <xref:System.Linq.ParallelEnumerable.Reverse%2A> enthält, wird darum das Zusammenführungsverhalten erst dann in der Abfrage angewendet, nachdem dieser Operator seine Ergebnisse erzeugt hat.  
  
 Die Fähigkeit einiger Operatoren, Mergeoptionen zu behandeln, hängt vom Typ der Quellsequenz ab, und ob der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Operator früher in der Abfrage verwendet wurde. <xref:System.Linq.ParallelEnumerable.ForAll%2A> ist immer <xref:System.Linq.ParallelMergeOptions.NotBuffered>; er stellt seine Elemente sofort bereit. <xref:System.Linq.ParallelEnumerable.OrderBy%2A> ist immer <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; er muss die gesamte Liste vor der Bereitstellung sortieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [Gewusst wie: Angeben von Mergeoptionen in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
