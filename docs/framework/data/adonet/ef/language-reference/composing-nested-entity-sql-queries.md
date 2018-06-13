---
title: Zusammenstellen verschachtelter Entity SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 92e3153350787ef75c48ee52f1b6c68e09e15b4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760855"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="0500e-102">Zusammenstellen verschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="0500e-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="0500e-103"> ist eine umfangreiche funktionale Sprache.</span><span class="sxs-lookup"><span data-stu-id="0500e-103"> is a rich functional language.</span></span> <span data-ttu-id="0500e-104">Der Baustein von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0500e-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="0500e-105">Im Gegensatz zu herkömmlichen SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist nicht auf tabellarische Resultsets beschränkt: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt komplexe Ausdrücke, die Literale, Parameter oder geschachtelte Ausdrücke aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="0500e-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="0500e-106">Ein Wert im Ausdruck kann parametrisiert oder einem anderen Ausdruck bestehen.</span><span class="sxs-lookup"><span data-stu-id="0500e-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="0500e-107">Geschachtelte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0500e-107">Nested Expressions</span></span>  
 <span data-ttu-id="0500e-108">Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0500e-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="0500e-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0500e-109">For example:</span></span>  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="0500e-110">Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="0500e-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="0500e-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0500e-111">For example:</span></span>  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="0500e-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen geschachtelte Abfragen stets in Klammern eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="0500e-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="0500e-113">Im folgende Beispiel wird veranschaulicht, wie Ausdrücke in ordnungsgemäß geschachtelt [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [wie: Sortieren Sie die Union der beiden Abfragen](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).</span><span class="sxs-lookup"><span data-stu-id="0500e-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](http://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="0500e-114">Geschachtelte Abfragen in Projektion</span><span class="sxs-lookup"><span data-stu-id="0500e-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="0500e-115">Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0500e-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="0500e-116">Bei einigen Backendservern, einschließlich SLQ Server, kann hierdurch die TempDB-Tabelle sehr groß werden, was die Serverleistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="0500e-116">In some backend servers, including SLQ Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="0500e-117">Das folgende Beispiel zeigt eine Abfrage dieser Art:</span><span class="sxs-lookup"><span data-stu-id="0500e-117">The following is an example of such a query:</span></span>  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="0500e-118">Reihenfolge geschachtelter Abfragen</span><span class="sxs-lookup"><span data-stu-id="0500e-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="0500e-119">In Entity Framework kann ein geschachtelter Ausdruck an einer beliebigen Stelle in die Abfrage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0500e-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="0500e-120">Da Entity SQL große Flexibilität beim Schreiben von Abfragen zulässt, kann eine Abfrage mit einer Reihe von geschachtelten Abfragen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0500e-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="0500e-121">Die Reihenfolge einer geschachtelten Abfrage wird jedoch nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0500e-121">However, the order of a nested query is not preserved.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0500e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0500e-122">See Also</span></span>  
 [<span data-ttu-id="0500e-123">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="0500e-123">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
