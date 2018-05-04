---
title: NULL-Vergleiche
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: f4d4f6cdbb5ac6bae3af66d46599ec65aaae22f4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="null-comparisons"></a>NULL-Vergleiche
Ein `null`-Wert in der Datenquelle gibt an, dass der Wert unbekannt ist. Sie können in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen auf NULL-Werte überprüfen, damit bestimmte Berechnungen oder Vergleiche nur für Zeilen mit gültigen Daten bzw. Daten, die nicht den Wert NULL haben, ausgeführt werden. Die NULL-Semantik der CLR unterscheidet sich jedoch möglicherweise von der NULL-Semantik der Datenquelle. Die meisten Datenbanken verwenden eine Logikversion mit einer dritten Möglichkeit der Auswertung, um NULL-Vergleiche zu behandeln. D. h., dass jeder Vergleich mit einem null-Wert wird nicht ausgewertet `true` oder `false`, ergibt es `unknown`. Oft ist dies eine Implementierung von ANSI-Nullen, das ist jedoch nicht immer der Fall.  
  
 Standardmäßig gibt der NULL-gleich-NULL-Vergleich in SQL Server einen NULL-Wert zurück. Im folgenden Beispiel werden die Zeilen, in denen `ShipDate` gleich NULL ist, vom Resultset ausgeschlossen, sodass die [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-Anweisung keine Zeilen zurückgeben würde.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Dies unterscheidet sich sehr von der NULL-Semantik der CLR, bei der der NULL-gleich-NULL-Vergleich true zurückgibt.  
  
 Die folgende LINQ-Abfrage wird in der Semantik der CLR ausgedrückt, wird jedoch in der Datenquelle ausgeführt. Da nicht gewährleistet ist, dass die CLR-Semantik von der Datenquelle verarbeitet wird, ist unklar, ob sie sich wie erwartet verhält.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>Schlüsselauswahlfunktionen  
 Ein *Schlüsselauswahlfunktion* ist eine Funktion, die in den Standardabfrageoperatoren zum Extrahieren eines Schlüssels aus einem Element verwendet. In der Schlüsselauswahlfunktion kann ein Ausdruck mit einer Konstante verglichen werden. Die NULL-Semantik der CLR wird angewendet, wenn ein Ausdruck mit einer NULL-Konstante oder zwei NULL-Konstanten miteinander verglichen werden. Die NULL-Semantik des Speichers gilt, wenn zwei Spalten mit NULL-Werten in der Datenquelle verglichen werden. Schlüsselauswahlfunktionen sind in vielen der Standardabfrageoperatoren zum Gruppieren und Sortieren zu finden, wie beispielsweise in <xref:System.Linq.Queryable.GroupBy%2A>. Sie werden verwendet, um Schlüssel auszuwählen, nach denen die Abfrageergebnisse sortiert oder gruppiert werden sollen.  
  
## <a name="null-property-on-a-null-object"></a>NULL-Eigenschaft eines NULL-Objekts  
 In [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind die Eigenschaften eines NULL-Objekts gleich NULL. Wenn Sie versuchen, in der CLR auf eine Eigenschaft eines NULL-Objekts zu verweisen, erhalten Sie eine <xref:System.NullReferenceException>. Wenn eine LINQ-Abfrage eine Eigenschaft eines NULL-Objekts einschließt, kann dies zu inkonsistentem Verhalten führen.  
  
 In der folgenden Abfrage wird die Umwandlung in `NewProduct` auf der Ebene der Befehlsstruktur durchgeführt. Das kann dazu führen, dass die `Introduced`-Eigenschaft NULL sein kann. Wenn NULL-Vergleiche in der Datenbank in der Weise definiert wurden, dass der <xref:System.DateTime>-Vergleich zu true ausgewertet wird, wird die Zeile eingeschlossen.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Übergeben von NULL-Auflistungen an Aggregatfunktionen  
 In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], wenn Sie eine Auflistung übergeben, die unterstützt `IQueryable` für eine Aggregatfunktion zusammengesetzte Operationen in der Datenbank ausgeführt werden. Es gibt möglicherweise Unterschiede in den Ergebnissen einer Abfrage, die im Arbeitsspeicher ausgeführt wurde und eine Abfrage, die in der Datenbank ausgeführt wurde. Wenn keine Übereinstimmungen vorhanden sind, gibt die Abfrage in einer in-Memory-Abfrage 0 (null) zurück. Bei der Datenbankabfrage gibt die gleiche Abfrage `null` zurück. Wenn ein `null` Wert an eine LINQ-Aggregatfunktion übergeben wird, wird eine Ausnahme ausgelöst werden. Um mögliche akzeptieren `null` Werte umgewandelt, die Typen und die Eigenschaften der Typen, die Abfrageergebnisse in auf NULL festlegbare Typen zu empfangen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke in LINQ to Entities-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
