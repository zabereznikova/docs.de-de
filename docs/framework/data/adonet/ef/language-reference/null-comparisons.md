---
title: "NULL-Vergleiche | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# NULL-Vergleiche
Ein `null`\-Wert in der Datenquelle gibt an, dass der Wert unbekannt ist.  Sie können in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]\-Abfragen auf NULL\-Werte überprüfen, damit bestimmte Berechnungen oder Vergleiche nur für Zeilen mit gültigen Daten bzw. Daten, die nicht den Wert NULL haben, ausgeführt werden.  Die NULL\-Semantik der CLR unterscheidet sich jedoch möglicherweise von der NULL\-Semantik der Datenquelle.  Die meisten Datenbanken verwenden eine Logikversion mit einer dritten Möglichkeit der Auswertung, um NULL\-Vergleiche zu behandeln.  Dabei wird jeder Vergleich mit einem NULL\-Wert nicht als `true` oder `false`, sondern als `unknown` ausgewertet.  Oft ist dies eine Implementierung von ANSI\-Nullen, das ist jedoch nicht immer der Fall.  
  
 Standardmäßig gibt der NULL\-gleich\-NULL\-Vergleich in SQL Server einen NULL\-Wert zurück.  Im folgenden Beispiel werden die Zeilen, in denen `ShipDate` gleich NULL ist, vom Resultset ausgeschlossen, sodass die [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]\-Anweisung keine Zeilen zurückgeben würde.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Dies unterscheidet sich sehr von der NULL\-Semantik der CLR, bei der der NULL\-gleich\-NULL\-Vergleich **true** zurückgibt.  
  
 Die folgende LINQ\-Abfrage wird in der Semantik der CLR ausgedrückt, wird jedoch in der Datenquelle ausgeführt.  Da nicht gewährleistet ist, dass die CLR\-Semantik von der Datenquelle verarbeitet wird, ist unklar, ob sie sich wie erwartet verhält.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## Schlüsselauswahlfunktionen  
 Eine *Schlüsselauswahl* ist eine in den Standardabfrageoperatoren verwendete Funktion zur Extrahierung eines Schlüssels aus einem Element.  In der Schlüsselauswahlfunktion kann ein Ausdruck mit einer Konstante verglichen werden.  Die NULL\-Semantik der CLR wird angewendet, wenn ein Ausdruck mit einer NULL\-Konstante oder zwei NULL\-Konstanten miteinander verglichen werden.  Die NULL\-Semantik des Speichers gilt, wenn zwei Spalten mit NULL\-Werten in der Datenquelle verglichen werden.  Schlüsselauswahlfunktionen sind in vielen der Standardabfrageoperatoren zum Gruppieren und Sortieren zu finden, wie beispielsweise in <xref:System.Linq.Queryable.GroupBy%2A>. Sie werden verwendet, um Schlüssel auszuwählen, nach denen die Abfrageergebnisse sortiert oder gruppiert werden sollen.  
  
## NULL\-Eigenschaft eines NULL\-Objekts  
 In [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind die Eigenschaften eines NULL\-Objekts gleich NULL.  Wenn Sie versuchen, in der CLR auf eine Eigenschaft eines NULL\-Objekts zu verweisen, erhalten Sie eine <xref:System.NullReferenceException>.  Wenn eine LINQ\-Abfrage eine Eigenschaft eines NULL\-Objekts einschließt, kann dies zu inkonsistentem Verhalten führen.  
  
 In der folgenden Abfrage wird die Umwandlung in `NewProduct` auf der Ebene der Befehlsstruktur durchgeführt. Das kann dazu führen, dass die `Introduced`\-Eigenschaft NULL sein kann.  Wenn NULL\-Vergleiche in der Datenbank in der Weise definiert wurden, dass der <xref:System.DateTime>\-Vergleich zu **true** ausgewertet wird, wird die Zeile eingeschlossen.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## Übergeben von NULL\-Auflistungen an Aggregatfunktionen  
 In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] werden beim Übergeben einer Auflistung, die `IQueryable` für eine Aggregatfunktion unterstützt, aggregierte Operationen in der Datenbank ausgeführt.  Zwischen den Ergebnissen einer Abfrage, die im Arbeitsspeicher ausgeführt wurde, und einer Abfrage, die in der Datenbank ausgeführt wurde, können Unterschiede bestehen.  Bei einer Abfrage im Arbeitsspeicher gibt die Abfrage 0 \(null\) zurück, wenn keine Übereinstimmungen gefunden werden kann.  Bei der Datenbankabfrage gibt die gleiche Abfrage `null` zurück.  Wird ein `null`\-Wert an eine LINQ\-Aggregatfunktion übergeben, wird eine Ausnahme ausgelöst.  Wandeln Sie die Typen und die Eigenschaften der Typen, die Abfrageergebnisse empfangen, in NULL\-Werte um, um mögliche `null`\-Werte zu akzeptieren.  
  
## Siehe auch  
 [Ausdrücke in LINQ to Entities\-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)