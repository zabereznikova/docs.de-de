---
title: SELECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
ms.openlocfilehash: 860e2a9a3e484e8d09cad282be8c0126c8235b46
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202213"
---
# <a name="select-entity-sql"></a><span data-ttu-id="dd34c-102">SELECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dd34c-102">SELECT (Entity SQL)</span></span>

<span data-ttu-id="dd34c-103">Gibt die von einer Abfrage zurückgegebenen Elemente an.</span><span class="sxs-lookup"><span data-stu-id="dd34c-103">Specifies the elements returned by a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd34c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd34c-104">Syntax</span></span>  
  
```sql  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
-- or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a><span data-ttu-id="dd34c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="dd34c-105">Arguments</span></span>  

 <span data-ttu-id="dd34c-106">ALL</span><span class="sxs-lookup"><span data-stu-id="dd34c-106">ALL</span></span>  
 <span data-ttu-id="dd34c-107">Gibt an, dass im Resultset Duplikate zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dd34c-107">Specifies that duplicates can appear in the result set.</span></span> <span data-ttu-id="dd34c-108">ALL ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="dd34c-108">ALL is the default.</span></span>  
  
 <span data-ttu-id="dd34c-109">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="dd34c-109">DISTINCT</span></span>  
 <span data-ttu-id="dd34c-110">Gibt an, dass im Resultset nur eindeutige Ergebnisse zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dd34c-110">Specifies that only unique results can appear in the result set.</span></span>  
  
 <span data-ttu-id="dd34c-111">VALUE</span><span class="sxs-lookup"><span data-stu-id="dd34c-111">VALUE</span></span>  
 <span data-ttu-id="dd34c-112">Ermöglicht die Angabe nur eines Elements, und fügt keinen Zeilen-Wrapper hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd34c-112">Allows only one item to be specified, and does not add on a row wrapper.</span></span>  
  
 `topSubclause`  
 <span data-ttu-id="dd34c-113">Jeder gültige Ausdruck von der Form `top(expr)`, der die Anzahl der von der Abfrage zurückzugebenden Ergebnisse angibt.</span><span class="sxs-lookup"><span data-stu-id="dd34c-113">Any valid expression that indicates the number of first results to return from the query, of the form `top(expr)`.</span></span>  
  
 <span data-ttu-id="dd34c-114">Mit dem Limit-Parameter des [Order by](order-by-entity-sql.md) -Operators können Sie auch die ersten n Elemente des Resultsets auswählen.</span><span class="sxs-lookup"><span data-stu-id="dd34c-114">The LIMIT parameter of the [ORDER BY](order-by-entity-sql.md) operator also lets you select the first n items in the result set.</span></span>  
  
 `aliasedExpr`  
 <span data-ttu-id="dd34c-115">Ein Ausdruck der Form:</span><span class="sxs-lookup"><span data-stu-id="dd34c-115">An expression of the form:</span></span>  
  
 <span data-ttu-id="dd34c-116">`expr` wie `identifier` &#124; `expr`</span><span class="sxs-lookup"><span data-stu-id="dd34c-116">`expr` as `identifier` &#124; `expr`</span></span>  
  
 `expr`  
 <span data-ttu-id="dd34c-117">Ein Literal oder ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="dd34c-117">A literal or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd34c-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dd34c-118">Remarks</span></span>  

 <span data-ttu-id="dd34c-119">Die [SELECT-Klausel](having-entity-sql.md) wird ausgewertet, nachdem die [from](from-entity-sql.md)-, [Group by](group-by-entity-sql.md)-und have-Klauseln ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="dd34c-119">The SELECT clause is evaluated after the [FROM](from-entity-sql.md), [GROUP BY](group-by-entity-sql.md), and [HAVING](having-entity-sql.md) clauses have been evaluated.</span></span> <span data-ttu-id="dd34c-120">Die SELECT-Klausel kann sich nur auf aktuell im Bereich (der FROM-Klausel oder äußerer Bereiche) befindliche Elemente beziehen.</span><span class="sxs-lookup"><span data-stu-id="dd34c-120">The SELECT clause can only refer to items currently in-scope (from the FROM clause, or from outer scopes).</span></span> <span data-ttu-id="dd34c-121">Wenn eine GROUP BY-Klausel angegeben wurde, darf die SELECT-Klausel nur auf die Aliase der GROUP BY-Schlüssel verweisen.</span><span class="sxs-lookup"><span data-stu-id="dd34c-121">If a GROUP BY clause has been specified, the SELECT clause is only allowed to reference the aliases for the GROUP BY keys.</span></span> <span data-ttu-id="dd34c-122">Verweise auf Elemente der FROM-Klausel sind nur in Aggregatfunktionen zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd34c-122">Referring to the FROM clause items is only permitted in aggregate functions.</span></span>  
  
 <span data-ttu-id="dd34c-123">Die Liste von einem oder mehreren auf das SELECT-Schlüsselwort folgenden Abfrageausdrücken wird als Auswahlliste oder Projektion bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dd34c-123">The list of one or more query expressions following the SELECT keyword is known as the select list, or more formally as the projection.</span></span> <span data-ttu-id="dd34c-124">Die allgemeinste Form der Projektion ist ein einzelner Abfrageausdruck.</span><span class="sxs-lookup"><span data-stu-id="dd34c-124">The most general form of projection is a single query expression.</span></span> <span data-ttu-id="dd34c-125">Durch Auswahl eines Members `member1` aus einer Auflistung `collection1`wird eine neue Auflistung aller Werte `member1` für jedes Objekt in `collection1`erstellt. Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dd34c-125">If you select a member `member1` from a collection `collection1`, you will produce a new collection of all the `member1` values for each object in `collection1`, as illustrated in the following example.</span></span>  
  
```sql  
SELECT collection1.member1 FROM collection1  
```  
  
 <span data-ttu-id="dd34c-126">Wenn z. B. `customers` eine Auflistung vom Typ `Customer` ist, der über die Eigenschaft `Name` vom Typ `string`verfügt, wird durch die Auswahl von `Name` aus `customers` eine Auflistung von Zeichenfolgen erstellt. Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="dd34c-126">For example, if `customers` is a collection of type `Customer` that has a property `Name` that is of type `string`, selecting `Name` from `customers` will yield a collection of strings, as illustrated in the following example.</span></span>  
  
```sql  
SELECT customers.Name FROM customers AS c  
```  
  
 <span data-ttu-id="dd34c-127">Es kann auch JOIN-Syntax (FULL, INNER, LEFT, OUTER, ON und RIGHT) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd34c-127">It is also possible to use JOIN syntax (FULL, INNER, LEFT, OUTER, ON, and RIGHT).</span></span> <span data-ttu-id="dd34c-128">ON ist für innere Verknüpfungen erforderlich und bei Cross Joins nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dd34c-128">ON is required for inner joins and is nto allowed for cross joins.</span></span>  
  
## <a name="row-and-value-select-clauses"></a><span data-ttu-id="dd34c-129">Zeilen- und Wertauswahlklauseln</span><span class="sxs-lookup"><span data-stu-id="dd34c-129">Row and Value Select Clauses</span></span>  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="dd34c-130">unterstützt zwei Varianten der SELECT-Klausel.</span><span class="sxs-lookup"><span data-stu-id="dd34c-130">supports two variants of the SELECT clause.</span></span> <span data-ttu-id="dd34c-131">Die erste Variante, Zeilenauswahl, wird durch das SELECT-Schlüsselwort identifiziert und kann verwendet werden, um einen oder mehrere Werte anzugeben, die projiziert werden sollen. Da ein Zeilen Wrapper implizit um die zurückgegebenen Werte erweitert wird, ist das Ergebnis des Abfrage Ausdrucks immer eine Multimenge von Zeilen.</span><span class="sxs-lookup"><span data-stu-id="dd34c-131">The first variant, row select, is identified by the SELECT keyword, and can be used to specify one or more values that should be projected out. Because a row wrapper is implicitly added around the values returned, the result of the query expression is always a multiset of rows.</span></span>  
  
 <span data-ttu-id="dd34c-132">In jedem Abfrageausdruck in einer Zeilenauswahl muss ein Alias angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd34c-132">Each query expression in a row select must specify an alias.</span></span> <span data-ttu-id="dd34c-133">Wenn kein Alias angegeben wird, generiert[!INCLUDE[esql](../../../../../../includes/esql-md.md)] mithilfe der Aliasgenerierungsregeln einen Alias.</span><span class="sxs-lookup"><span data-stu-id="dd34c-133">If no alias is specified,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias by using the alias generation rules.</span></span>  
  
 <span data-ttu-id="dd34c-134">Die andere Variante der SELECT-Klausel, Wertauswahl, wird durch das SELECT VALUE-Schlüsselwort angegeben.</span><span class="sxs-lookup"><span data-stu-id="dd34c-134">The other variant of the SELECT clause, value select, is identified by the SELECT VALUE keyword.</span></span> <span data-ttu-id="dd34c-135">Es ermöglicht die Angabe nur eines Werts, und fügt keinen Zeilen-Wrapper hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd34c-135">It allows only one value to be specified, and does not add a row wrapper.</span></span>  
  
 <span data-ttu-id="dd34c-136">Eine Zeilenauswahl ist stets mithilfe von VALUE SELECT ausdrückbar. Dies wird im folgenden Beispiel illustriert.</span><span class="sxs-lookup"><span data-stu-id="dd34c-136">A row select is always expressible in terms of VALUE SELECT, as illustrated in the following example.</span></span>  
  
```sql  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C
```  
  
## <a name="all-and-distinct-modifiers"></a><span data-ttu-id="dd34c-137">Die Modifizierer ALL und DISTINCT</span><span class="sxs-lookup"><span data-stu-id="dd34c-137">All and Distinct Modifiers</span></span>  

 <span data-ttu-id="dd34c-138">Beide Varianten von SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ermöglichen die Angabe eines ALL-Modifizierers oder eines DISTINCT-Modifizierers.</span><span class="sxs-lookup"><span data-stu-id="dd34c-138">Both variants of SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allow the specification of an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="dd34c-139">Wenn der DISTINCT-Modifizierer angegeben wird, werden Duplikate aus der vom Abfrageausdruck erstellten Auflistung entfernt (bis zur und einschließlich der SELECT-Klausel).</span><span class="sxs-lookup"><span data-stu-id="dd34c-139">If the DISTINCT modifier is specified, duplicates are eliminated from the collection produced by the query expression (up to and including the SELECT clause).</span></span> <span data-ttu-id="dd34c-140">Wenn der ALL-Modifizierer angegeben ist, werden Duplikate nicht entfernt. Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="dd34c-140">If the ALL modifier is specified, no duplicate elimination is performed; ALL is the default.</span></span>  
  
## <a name="differences-from-transact-sql"></a><span data-ttu-id="dd34c-141">Unterschiede zu Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dd34c-141">Differences from Transact-SQL</span></span>  

 <span data-ttu-id="dd34c-142">Im Gegensatz zu Transact-SQL unterstützt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nicht die Verwendung des „\*“-Arguments in der SELECT-Klausel.</span><span class="sxs-lookup"><span data-stu-id="dd34c-142">Unlike Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support use of the \* argument in the SELECT clause.</span></span>  <span data-ttu-id="dd34c-143">Stattdessen ermöglicht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in Abfragen das Herausprojizieren ganzer Datensätze durch Verweise auf die Auflistungsaliase der FROM-Klausel. Dies wird im folgenden Beispiel illustriert.</span><span class="sxs-lookup"><span data-stu-id="dd34c-143">Instead, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows queries to project out entire records by referencing the collection aliases from the FROM clause, as illustrated in the following example.</span></span>  
  
```sql  
SELECT * FROM T1, T2  
```  
  
 <span data-ttu-id="dd34c-144">Der vorherige Transact-SQL-Abfrage Ausdruck wird in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wie folgt ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="dd34c-144">The previous Transact-SQL query expression is expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in the following way.</span></span>  
  
```sql  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a><span data-ttu-id="dd34c-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd34c-145">Example</span></span>  

 <span data-ttu-id="dd34c-146">In der folgenden Entity SQL-Abfrage wird der SELECT-Operator verwendet, um die von einer Abfrage zurückzugebenden Elemente anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd34c-146">The following Entity SQL query uses the SELECT operator to specify the elements to be returned by a query.</span></span> <span data-ttu-id="dd34c-147">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="dd34c-147">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dd34c-148">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="dd34c-148">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dd34c-149">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dd34c-149">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dd34c-150">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="dd34c-150">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="dd34c-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd34c-151">See also</span></span>

- [<span data-ttu-id="dd34c-152">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="dd34c-152">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="dd34c-153">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="dd34c-153">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="dd34c-154">TOP</span><span class="sxs-lookup"><span data-stu-id="dd34c-154">TOP</span></span>](top-entity-sql.md)
