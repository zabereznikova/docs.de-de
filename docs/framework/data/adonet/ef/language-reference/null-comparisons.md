---
title: NULL-Vergleiche
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 71b7c4d86debe8cf267b1b65e3d176cbc4704e6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185105"
---
# <a name="null-comparisons"></a>NULL-Vergleiche

Ein `null`-Wert in der Datenquelle gibt an, dass der Wert unbekannt ist. In LINQ to Entities-Abfragen können Sie nach NULL-Werten suchen, damit bestimmte Berechnungen oder Vergleiche nur für Zeilen mit gültigen Daten oder nicht-NULL-Daten ausgeführt werden. Die NULL-Semantik der CLR unterscheidet sich jedoch möglicherweise von der NULL-Semantik der Datenquelle. Die meisten Datenbanken verwenden eine Logikversion mit einer dritten Möglichkeit der Auswertung, um NULL-Vergleiche zu behandeln. Dies bedeutet, dass ein Vergleich mit einem NULL-Wert nicht zu `true` oder ausgewertet `false` wird, sondern als ausgewertet wird `unknown` . Oft ist dies eine Implementierung von ANSI-Nullen, das ist jedoch nicht immer der Fall.  
  
 Standardmäßig gibt der NULL-gleich-NULL-Vergleich in SQL Server einen NULL-Wert zurück. Im folgenden Beispiel werden die Zeilen, in denen `ShipDate` NULL ist, aus dem Resultset ausgeschlossen, und die Transact-SQL-Anweisung würde 0 Zeilen zurückgeben.  
  
```sql  
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

 Ein *Schlüsselselektor* ist eine Funktion, die in den Standard Abfrage Operatoren zum Extrahieren eines Schlüssels aus einem Element verwendet wird. In der Schlüsselauswahlfunktion kann ein Ausdruck mit einer Konstante verglichen werden. Die NULL-Semantik der CLR wird angewendet, wenn ein Ausdruck mit einer NULL-Konstante oder zwei NULL-Konstanten miteinander verglichen werden. Die NULL-Semantik des Speichers gilt, wenn zwei Spalten mit NULL-Werten in der Datenquelle verglichen werden. Schlüsselauswahlfunktionen sind in vielen der Standardabfrageoperatoren zum Gruppieren und Sortieren zu finden, wie beispielsweise in <xref:System.Linq.Queryable.GroupBy%2A>. Sie werden verwendet, um Schlüssel auszuwählen, nach denen die Abfrageergebnisse sortiert oder gruppiert werden sollen.  
  
## <a name="null-property-on-a-null-object"></a>NULL-Eigenschaft eines NULL-Objekts  

 In der Entity Framework sind die Eigenschaften eines NULL-Objekts NULL. Wenn Sie versuchen, in der CLR auf eine Eigenschaft eines NULL-Objekts zu verweisen, erhalten Sie eine <xref:System.NullReferenceException>. Wenn eine LINQ-Abfrage eine Eigenschaft eines NULL-Objekts einschließt, kann dies zu inkonsistentem Verhalten führen.  
  
 In der folgenden Abfrage wird die Umwandlung in `NewProduct` auf der Ebene der Befehlsstruktur durchgeführt. Das kann dazu führen, dass die `Introduced`-Eigenschaft NULL sein kann. Wenn NULL-Vergleiche in der Datenbank in der Weise definiert wurden, dass der -Vergleich zu true ausgewertet wird, wird die Zeile eingeschlossen.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Übergeben von NULL-Auflistungen an Aggregatfunktionen  

 Wenn Sie in LINQ to Entities eine Auflistung, die von unterstützt `IQueryable` wird, an eine Aggregatfunktion übergeben, werden Aggregat Vorgänge in der Datenbank ausgeführt. Zwischen den Ergebnissen einer Abfrage, die im Arbeitsspeicher ausgeführt wurde, und einer Abfrage, die in der Datenbank ausgeführt wurde, können Unterschiede bestehen. Bei einer Abfrage im Arbeitsspeicher gibt die Abfrage 0 (null) zurück, wenn keine Übereinstimmungen gefunden werden kann. Bei der Datenbankabfrage gibt die gleiche Abfrage `null` zurück. Wenn ein `null` Wert an eine LINQ-Aggregatfunktion übermittelt wird, wird eine Ausnahme ausgelöst. Um mögliche Werte zu akzeptieren, wandeln Sie `null` die Typen und die Eigenschaften der Typen, die Abfrageergebnisse empfangen, in Werttypen um, die NULL-Werte zulassen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ausdrücke in LINQ to Entities-Abfragen](expressions-in-linq-to-entities-queries.md)
