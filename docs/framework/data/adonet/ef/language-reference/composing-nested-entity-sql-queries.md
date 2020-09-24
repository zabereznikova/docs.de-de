---
title: Zusammenstellen verschachtelter Entity SQL-Abfragen
ms.date: 03/30/2017
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
ms.openlocfilehash: 0c9a6a99ff49cfa847f4c1e7ea693fbb2611debd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153065"
---
# <a name="composing-nested-entity-sql-queries"></a><span data-ttu-id="e0b49-102">Zusammenstellen verschachtelter Entity SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e0b49-102">Composing Nested Entity SQL Queries</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="e0b49-103">ist eine umfangreiche funktionale Sprache.</span><span class="sxs-lookup"><span data-stu-id="e0b49-103">is a rich functional language.</span></span> <span data-ttu-id="e0b49-104">Der Baustein von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e0b49-104">The building block of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is an expression.</span></span> <span data-ttu-id="e0b49-105">Im Gegensatz zu herkömmlichem SQL [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist nicht auf ein tabellarisches Resultset beschränkt: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt das Verfassen komplexer Ausdrücke, die Literale, Parameter oder unterstützte Ausdrücke aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="e0b49-105">Unlike conventional SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is not limited to a tabular result set: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] supports composing complex expressions that can have literals, parameters, or nested expressions.</span></span> <span data-ttu-id="e0b49-106">Ein Wert im Ausdruck kann parametrisiert sein oder aus einem anderen Ausdruck bestehen.</span><span class="sxs-lookup"><span data-stu-id="e0b49-106">A value in the expression can be parameterized or composed of some other expression.</span></span>  
  
## <a name="nested-expressions"></a><span data-ttu-id="e0b49-107">Geschachtelte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="e0b49-107">Nested Expressions</span></span>  

 <span data-ttu-id="e0b49-108">Ein geschachtelter Ausdruck kann an jeder Stelle verwendet werden, an der der Wert des Rückgabetyps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e0b49-108">A nested expression can be placed anywhere a value of the type it returns is accepted.</span></span> <span data-ttu-id="e0b49-109">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e0b49-109">For example:</span></span>  
  
```sql  
-- Returns a hierarchical collection of three elements at top-level.
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 <span data-ttu-id="e0b49-110">Eine geschachtelte Abfrage kann in einer Projektionsklausel enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="e0b49-110">A nested query can be placed in a projection clause.</span></span> <span data-ttu-id="e0b49-111">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e0b49-111">For example:</span></span>  
  
```sql  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 <span data-ttu-id="e0b49-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] müssen geschachtelte Abfragen stets in Klammern eingeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="e0b49-112">In [!INCLUDE[esql](../../../../../../includes/esql-md.md)], nested queries must always be enclosed in parentheses:</span></span>  
  
```sql  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 <span data-ttu-id="e0b49-113">Im folgenden Beispiel wird veranschaulicht, wie Ausdrücke ordnungsgemäß geschachtelt werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] : Gewusst [wie: Sortieren der Union von zwei Abfragen](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e0b49-113">The following example demonstrates how to properly nest expressions in [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [How to: Order the Union of Two Queries](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100)).</span></span>  
  
## <a name="nested-queries-in-projection"></a><span data-ttu-id="e0b49-114">Geschachtelte Abfragen in Projektion</span><span class="sxs-lookup"><span data-stu-id="e0b49-114">Nested Queries in Projection</span></span>  

 <span data-ttu-id="e0b49-115">Geschachtelte Abfragen in der Projektklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e0b49-115">Nested queries in the project clause might get translated into Cartesian product queries on the server.</span></span> <span data-ttu-id="e0b49-116">Bei einigen Back-End-Servern, einschließlich SQL Server, kann dies dazu führen, dass die tempdb-Tabelle sehr groß wird, was sich negativ auf die Server Leistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="e0b49-116">In some backend servers, including SQL Server, this can cause the TempDB table to get very large, which can adversely affect server performance.</span></span>  
  
 <span data-ttu-id="e0b49-117">Das folgende Beispiel zeigt eine Abfrage dieser Art:</span><span class="sxs-lookup"><span data-stu-id="e0b49-117">The following is an example of such a query:</span></span>  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="e0b49-118">Reihenfolge geschachtelter Abfragen</span><span class="sxs-lookup"><span data-stu-id="e0b49-118">Ordering Nested Queries</span></span>  

 <span data-ttu-id="e0b49-119">In Entity Framework kann ein geschachtelter Ausdruck an einer beliebigen Stelle in die Abfrage eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e0b49-119">In the Entity Framework, a nested expression can be placed anywhere in the query.</span></span> <span data-ttu-id="e0b49-120">Da Entity SQL große Flexibilität beim Schreiben von Abfragen zulässt, kann eine Abfrage mit einer Reihe von geschachtelten Abfragen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e0b49-120">Because Entity SQL allows great flexibility in writing queries, it is possible to write a query that contains an ordering of nested queries.</span></span> <span data-ttu-id="e0b49-121">Die Reihenfolge einer geschachtelten Abfrage wird jedoch nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e0b49-121">However, the order of a nested query is not preserved.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0b49-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0b49-122">See also</span></span>

- [<span data-ttu-id="e0b49-123">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e0b49-123">Entity SQL Overview</span></span>](entity-sql-overview.md)
