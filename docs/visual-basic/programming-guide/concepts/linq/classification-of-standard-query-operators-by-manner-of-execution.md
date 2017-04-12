---
title: "Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a13f2fcf33c2faacd5b2662cd96d0f962b54322f
ms.lasthandoff: 03/13/2017

---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Klassifizierung von Standardabfrageoperatoren nach Ausführungsarten (Visual Basic)
LINQ to Objects Implementierungen der Standardabfrageoperator-Methoden führen auf zweierlei Weise: sofortige oder zurückgestellt. Abfrageoperatoren, die verzögerte Ausführung verwenden können darüber hinaus in zwei Kategorien unterteilt werden: streaming und nicht-streaming. Wenn Sie wissen, wie die einzelnen Operatoren ausgeführt werden, erleichtert dies das Verständnis der Ergebnisse, die Sie einer Abfrage zu erhalten. Dies ist insbesondere dann der Fall, wenn die Datenquelle geändert wird oder wenn Sie eine Abfrage auf Grundlage einer anderen Abfrage erstellen. In diesem Thema werden die Standardabfrageoperatoren gemäß ihren Ausführungsarten klassifiziert.  
  
## <a name="manners-of-execution"></a>Art der Ausführung  
  
### <a name="immediate"></a>Direkt  
 Unmittelbare Ausführung bedeutet, dass die Datenquelle gelesen und der Vorgang an dem Punkt im Code ausgeführt wird, in dem die Abfrage deklariert ist. Alle Standardabfrageoperatoren, die ein einzelnes, nicht aufzählbares Ergebnis zurückgeben, werden sofort ausgeführt.  
  
### <a name="deferred"></a>Zurückgestellt  
 Verzögerte Ausführung bedeutet, dass der Vorgang nicht ausgeführt wird, an dem Punkt im Code und, in dem die Abfrage deklariert ist. Der Vorgang erfolgt nur, wenn die Abfragevariable aufgezählt wird, z. B. durch Verwendung einer `For Each` Anweisung. Dies bedeutet, dass die Ergebnisse der Ausführung der Abfrage hängt vom Inhalt der Datenquelle aus, wenn die Abfrage ausgeführt wird, statt, wenn die Abfrage definiert ist. Wenn die Abfragevariable mehrfach aufgezählt wird, können die Ergebnisse jedes Mal abweichen. Nahezu alle Standardabfrageoperatoren, dessen Rückgabetyp <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IOrderedEnumerable%601>verzögert ausgeführt.</xref:System.Linq.IOrderedEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Abfrageoperatoren, die verzögerte Ausführung verwenden können außerdem als streaming oder nicht-streaming klassifiziert werden.  
  
#### <a name="streaming"></a>Streaming  
 Streaming-Operatoren müssen nicht alle Quelldaten zu lesen, bevor sie Elemente ergeben. Zum Zeitpunkt der Ausführung führt streaming-Operatoren der Operation auf jedes Quellelement gelesen werden können, und gibt das Element bei Bedarf. Streaming-Operatoren weiterhin Quellelemente zu lesen, bis ein Ergebniselement erzeugt werden kann. Dies bedeutet, dass mehr als ein Quellelement gelesen werden kann, um ein Ergebniselement zu erzeugen.  
  
#### <a name="non-streaming"></a>Nicht-Streaming  
 Nicht-streaming-Operatoren müssen alle Quelldaten lesen, bevor sie ein Ergebniselement ergeben können. Vorgänge wie das Sortieren oder gruppieren, fallen in diese Kategorie. Zum Zeitpunkt der Ausführung nicht-streaming-Operatoren Lesen alle Quelldaten, einer Datenstruktur abgelegt, führen Sie den Vorgang und die resultierenden Elemente ergibt.  
  
## <a name="classification-table"></a>Klassifizierung-Tabelle  
 In der folgenden Tabelle wird jede Standardabfrageoperator-Operator-Methode nach Ausführungsmethoden klassifiziert.  
  
> [!NOTE]
>  Wenn ein Operator in zwei Spalten gekennzeichnet ist, zwei Eingabesequenzen in den Vorgang einbezogen sind, und jeder Sequenz unterschiedlich ausgewertet. In diesen Fällen wird immer die erste Sequenz in der Parameterliste, der ausgewertet wird verzögert, streaming Weise.  
  
|Standardabfrageoperator|Rückgabetyp|Sofortige Ausführung|Verzögerte Streaming-Ausführung|Verzögerte nicht-Streaming-Ausführung|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A></xref:System.Linq.Enumerable.Aggregate%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.All%2A></xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Any%2A></xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A></xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A></xref:System.Linq.Enumerable.Average%2A>|Einzelnen numerischen Wert|X|||  
|<xref:System.Linq.Enumerable.Cast%2A></xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Concat%2A></xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Contains%2A></xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Count%2A></xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32></xref:System.Int32>|X|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A></xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Distinct%2A></xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A></xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A></xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Empty%2A></xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|X|||  
|<xref:System.Linq.Enumerable.Except%2A></xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.First%2A></xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.GroupBy%2A></xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.GroupJoin%2A></xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
<xref:System.Linq.Enumerable.Intersect%2A></xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Join%2A></xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X|X|  
|<xref:System.Linq.Enumerable.Last%2A></xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A></xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LongCount%2A></xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64></xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A></xref:System.Linq.Enumerable.Max%2A>|Einzelnen numerischen Wert, TSource oder TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A></xref:System.Linq.Enumerable.Min%2A>|Einzelnen numerischen Wert, TSource oder TResult|X|||  
|<xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.OrderBy%2A></xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A></xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Range%2A></xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Repeat%2A></xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Reverse%2A></xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.Select%2A></xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SelectMany%2A></xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A></xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean></xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A></xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A></xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.Skip%2A></xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.SkipWhile%2A></xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A></xref:System.Linq.Enumerable.Sum%2A>|Einzelnen numerischen Wert|X|||  
|<xref:System.Linq.Enumerable.Take%2A></xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
<xref:System.Linq.Enumerable.TakeWhile%2A></xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ThenBy%2A></xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A></xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A></xref:System.Linq.Enumerable.ToArray%2A>|TSource array|X|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A></xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602>|X|||  
|<xref:System.Linq.Enumerable.ToList%2A></xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601></xref:System.Collections.Generic.IList%601>|X|||  
|<xref:System.Linq.Enumerable.ToLookup%2A></xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602></xref:System.Linq.ILookup%602>|X|||  
|<xref:System.Linq.Enumerable.Union%2A></xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Where%2A></xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Abfrageausdruckssyntax für Standardabfrageoperatoren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
