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
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="fa042-102">Zusammenstellen verschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="fa042-102">Composing Nested Entity SQL Queries</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="fa042-103">ist eine umfangreiche funktionale Sprache.</span><span class="sxs-lookup"><span data-stu-id="fa042-103">is a rich functional language.</span></span> <span data-ttu-id="fa042-104">Der Baustein [!INCLUDE[esql](../../../../../../includes/esql-md.md)] von ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fa042-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="fa042-105">Im Gegensatz [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zu herkömmlichem SQL ist es [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht auf ein tabellarisches Resultset beschränkt: unterstützt das Komponieren komplexer Ausdrücke, die Literale, Parameter oder geschachtelte Ausdrücke enthalten können.</span><span class="sxs-lookup"><span data-stu-id="fa042-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="fa042-106">Ein Wert im Ausdruck kann parametrisiert sein oder aus einem anderen Ausdruck bestehen.</span><span class="sxs-lookup"><span data-stu-id="fa042-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="fa042-107">Geschachtelte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="fa042-107">Nested Expressions</span></span>  
 <span data-ttu-id="fa042-108">Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="fa042-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="fa042-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa042-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="fa042-110">Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="fa042-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="fa042-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa042-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="fa042-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen geschachtelte Abfragen stets in Klammern eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="fa042-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="fa042-113">Im folgenden Beispiel wird veranschaulicht, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]wie Ausdrücke ordnungsgemäß verschachtelt werden: [Gewusst wie: Bestellen der Union mit zwei Abfragen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fa042-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="fa042-114">Geschachtelte Abfragen in Projektion</span><span class="sxs-lookup"><span data-stu-id="fa042-114">Nested Queries in Projection</span></span>  
 <span data-ttu-id="fa042-115">Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="fa042-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="fa042-116">Bei einigen Back-End-Servern, einschließlich SQL Server, kann dies dazu führen, dass die TempDB-Tabelle sehr groß wird, was sich negativ auf die Serverleistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="fa042-116">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="fa042-117">Das folgende Beispiel zeigt eine Abfrage dieser Art:</span><span class="sxs-lookup"><span data-stu-id="fa042-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="fa042-118">Reihenfolge geschachtelter Abfragen</span><span class="sxs-lookup"><span data-stu-id="fa042-118">Ordering Nested Queries</span></span>  
 <span data-ttu-id="fa042-119">In Entity Framework kann ein geschachtelter Ausdruck an einer beliebigen Stelle in die Abfrage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fa042-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="fa042-120">Da Entity SQL große Flexibilität beim Schreiben von Abfragen zulässt, kann eine Abfrage mit einer Reihe von geschachtelten Abfragen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fa042-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="fa042-121">Die Reihenfolge einer geschachtelten Abfrage wird jedoch nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="fa042-121">However, the order of a nested query is not preserved.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa042-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa042-122">See also</span></span>

- [<span data-ttu-id="fa042-123">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fa042-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
