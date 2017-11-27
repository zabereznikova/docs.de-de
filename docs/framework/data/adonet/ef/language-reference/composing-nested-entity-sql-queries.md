---
title: Zusammenstellen verschachtelter Entity SQL-Abfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 175affdd8e9763f6cc7d0c48c38498af6e8ffabb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="composing-nested-entity-sql-queries"></a>Zusammenstellen verschachtelter Entity SQL-Abfragen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine umfangreiche funktionale Sprache. Der Baustein von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist ein Ausdruck. Im Gegensatz zu herkömmlichen SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist nicht auf tabellarische Resultsets beschränkt: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt komplexe Ausdrücke, die Literale, Parameter oder geschachtelte Ausdrücke aufweisen können. Ein Wert im Ausdruck kann parametrisiert oder einem anderen Ausdruck bestehen.  
  
## <a name="nested-expressions"></a>Geschachtelte Ausdrücke  
 Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist. Beispiel:  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein. Beispiel:  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen geschachtelte Abfragen stets in Klammern eingeschlossen werden:  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 Im folgende Beispiel wird veranschaulicht, wie Ausdrücke in ordnungsgemäß geschachtelt [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [wie: Sortieren Sie die Union der beiden Abfragen](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313).  
  
## <a name="nested-queries-in-projection"></a>Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden. Bei einigen Backendservern, einschließlich SLQ Server, kann hierdurch die TempDB-Tabelle sehr groß werden, was die Serverleistung beeinträchtigen kann.  
  
 Das folgende Beispiel zeigt eine Abfrage dieser Art:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>Reihenfolge geschachtelter Abfragen  
 In Entity Framework kann ein geschachtelter Ausdruck an einer beliebigen Stelle in die Abfrage eingefügt werden. Da Entity SQL große Flexibilität beim Schreiben von Abfragen zulässt, kann eine Abfrage mit einer Reihe von geschachtelten Abfragen geschrieben werden. Die Reihenfolge einer geschachtelten Abfrage wird jedoch nicht beibehalten.  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
