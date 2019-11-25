---
title: Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten
ms.date: 07/20/2015
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
ms.openlocfilehash: edace870ea684c70bbf2768c44388f2236622c2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345714"
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Classification of Standard Query Operators by Manner of Execution (Visual Basic)
Die LINQ to Objects-Implementierungen des Standardabfrageoperators werden mit einer von zwei möglichen Arten ausgeführt: direkt oder zurückgestellt. Abfrageoperatoren, die die verzögerte Ausführung verwenden, können darüber hinaus in zwei Kategorien unterteilt werden: Streaming und Nicht-Streaming. Wenn Sie wissen, wie die einzelnen Abfrageoperatoren ausgeführt werden, erleichtert dies das Verständnis der Ergebnisse, die Sie von einer Abfrage erhalten. Dies ist insbesondere dann der Fall, wenn die Datenquelle geändert wird oder wenn Sie eine Abfrage auf Grundlage einer anderen Abfrage erstellen. In diesem Thema werden die Standardabfrageoperatoren gemäß ihrer Ausführungsarten klassifiziert.  
  
## <a name="manners-of-execution"></a>Arten der Ausführung  
  
### <a name="immediate"></a>Direkt  
 Direkte Ausführung bedeutet, dass die Datenquelle gelesen wird und die Operation an dem Zeitpunkt im Code ausgeführt wird, an dem die Abfrage deklariert wird. Alle Standardabfrageoperatoren, die ein einzelnes, nicht aufzählbares Ergebnis zurückgeben, werden sofort ausgeführt.  
  
### <a name="deferred"></a>Zurückgestellt  
 Zurückgestellte Ausführung bedeutet, dass der Vorgang nicht zum Zeitpunkt im Code ausgeführt wird, an dem die Abfrage deklariert wird. Der Vorgang erfolgt nur, wenn die Abfragevariable aufgezählt wird, z.B. durch Verwendung einer `For Each`-Anweisung. Dies bedeutet, dass die Ergebnisse der Ausführung der Abfrage vom Inhalt der Datenquelle zum Zeitpunkt der Abfrageausführung, nicht der Abfragedefinition abhängen. Wenn die Abfragevariable mehrfach aufgezählt wird, können die Ergebnisse jedes Mal abweichen. Fast alle Standardabfrageoperatoren, deren Rückgabetyp <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IOrderedEnumerable%601> ist, werden verzögert ausgeführt.  
  
 Abfrageoperatoren, die die verzögerte Ausführung verwenden, können zusätzlich als Streaming und Nicht-Streaming klassifiziert werden.  
  
#### <a name="streaming"></a>Streaming  
 Streaming-Operatoren müssen nicht alle Quelldaten lesen, bevor sie Elemente liefern. Zum Zeitpunkt der Ausführung führt ein Streaming-Operator seine Operation auf jedem Quellelement aus, während es gelesen wird, und liefert ggf. die Elemente. Ein Streaming-Operator liest weiterhin Quellelemente, bis ein Ergebniselement erzeugt werden kann. Dies bedeutet, dass mehr als ein Quellelement womöglich gelesen werden kann, um ein Ergebniselement zu erzeugen.  
  
#### <a name="non-streaming"></a>Nicht-Streaming  
 Nicht-Streaming-Operatoren müssen alle Quelldaten lesen, bevor sie ein Ergebniselement liefern können. Vorgänge wie das Sortieren oder Gruppieren fallen unter diese Kategorie. Zum Zeitpunkt der Ausführung lesen Nicht-Streaming-Operatoren alle Quelldaten, fügen sie in eine Datenstruktur ein, führen den Vorgang aus und liefern die Elemente, die sich ergeben.  
  
## <a name="classification-table"></a>Klassifizierungstabelle  
 In der folgenden Tabelle wird jede Standardabfrageoperator-Methode laut der Ausführungsmethode klassifiziert.  
  
> [!NOTE]
> Wenn ein Operator in zwei Spalten gekennzeichnet ist, werden zwei Eingabesequenzen in den Vorgang einbezogen, und jede Sequenz wird unterschiedlich ausgewertet. In diesen Fällen ist es immer die erste Sequenz in der Parameterliste, die verzögert und mit der Nicht-Straming-Methode ausgewertet wird.  
  
|Standardabfrageoperator|Rückgabetyp|Sofortige Ausführung|Verzögerte Streaming-Ausführung|Verzögerte Nicht-Streaming-Ausführung|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|w|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|w|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Average%2A>|Einzelner numerischer Wert|w|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|w|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|w|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|w|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w|w|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w|w|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w|w|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w|w|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|w|||  
|<xref:System.Linq.Enumerable.Max%2A>|Einzelner numerischer Wert, TSource oder TResult|w|||  
|<xref:System.Linq.Enumerable.Min%2A>|Einzelner numerischer Wert, TSource oder TResult|w|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|w|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|w|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Sum%2A>|Einzelner numerischer Wert|w|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||w|  
|<xref:System.Linq.Enumerable.ToArray%2A>|TSource-Array|w|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|w|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|w|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|w|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||w||  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
