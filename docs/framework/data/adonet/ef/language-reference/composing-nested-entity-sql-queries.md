---
title: Zusammenstellen verschachtelter Entity SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 6b2fc9a32fc30d205b9c33257bf98781cfa07499
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150388"
---
# <a name="composing-nested-entity-sql-queries"></a>Zusammenstellen verschachtelter Entity SQL-Abfragen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine umfangreiche funktionale Sprache. Der Baustein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] von ist ein Ausdruck. Im Gegensatz [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zu herkömmlichem SQL ist es [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht auf ein tabellarisches Resultset beschränkt: unterstützt das Komponieren komplexer Ausdrücke, die Literale, Parameter oder geschachtelte Ausdrücke enthalten können. Ein Wert im Ausdruck kann parametrisiert sein oder aus einem anderen Ausdruck bestehen.  
  
## <a name="nested-expressions"></a>Geschachtelte Ausdrücke  
 Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist. Beispiel:  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein. Beispiel:  
  
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
  
 Im folgenden Beispiel wird veranschaulicht, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]wie Ausdrücke ordnungsgemäß verschachtelt werden: [Gewusst wie: Bestellen der Union mit zwei Abfragen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).  
  
## <a name="nested-queries-in-projection"></a>Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden. Bei einigen Back-End-Servern, einschließlich SQL Server, kann dies dazu führen, dass die TempDB-Tabelle sehr groß wird, was sich negativ auf die Serverleistung auswirken kann.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Entity SQL](entity-sql-overview.md)
