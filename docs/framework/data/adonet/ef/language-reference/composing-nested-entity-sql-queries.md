---
title: Zusammenstellen verschachtelter Entity SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 0ab92c1e41c89f141c3cbd37be3e1e18e64d9666
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833912"
---
# <a name="composing-nested-entity-sql-queries"></a>Zusammenstellen verschachtelter Entity SQL-Abfragen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine umfangreiche funktionale Sprache. Der Baustein von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist ein Ausdruck. Im Gegensatz zu herkömmlichem SQL ist [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht auf ein tabellarisches Resultset beschränkt: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt das Verfassen komplexer Ausdrücke, die Literale, Parameter oder erbt Ausdrücke enthalten können. Ein Wert im Ausdruck kann parametrisiert oder aus einem anderen Ausdruck zusammengesetzt werden.  
  
## <a name="nested-expressions"></a>Geschachtelte Ausdrücke  
 Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist. Zum Beispiel:  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein. Zum Beispiel:  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen geschachtelte Abfragen stets in Klammern eingeschlossen werden:  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 Im folgenden Beispiel wird veranschaulicht, wie Ausdrücke in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ordnungsgemäß geschachtelt werden: [Vorgehensweise: Ordnen Sie die Union von zwei Abfragen @ no__t-0 zu.  
  
## <a name="nested-queries-in-projection"></a>Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden. Bei einigen Backendservern, einschließlich SLQ Server, kann hierdurch die TempDB-Tabelle sehr groß werden, was die Serverleistung beeinträchtigen kann.  
  
 Das folgende Beispiel zeigt eine Abfrage dieser Art:  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>Reihenfolge geschachtelter Abfragen  
 In Entity Framework kann ein geschachtelter Ausdruck an einer beliebigen Stelle in die Abfrage eingefügt werden. Da Entity SQL große Flexibilität beim Schreiben von Abfragen zulässt, kann eine Abfrage mit einer Reihe von geschachtelten Abfragen geschrieben werden. Die Reihenfolge einer geschachtelten Abfrage wird jedoch nicht beibehalten.  
  
```sql  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
