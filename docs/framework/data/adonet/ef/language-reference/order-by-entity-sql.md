---
title: ORDER BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: f3310274766ff3619604e30bfb5f5ca437cb1acd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249753"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="1c066-102">ORDER BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1c066-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="1c066-103">Legt die Sortierreihenfolge für Objekte fest, die von einer SELECT-Anweisung zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c066-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c066-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c066-104">Syntax</span></span>  
  
```  
[ ORDER BY   
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]   
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c066-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="1c066-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="1c066-106">Ein gültiger Abfrageausdruck, der eine Eigenschaft angibt, nach der sortiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c066-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="1c066-107">Es können mehrere Sortierausdrücke angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c066-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="1c066-108">Die Reihenfolge der Sortierausdrücke in der ORDER BY-Klausel definiert den Aufbau des sortierten Resultsets.</span><span class="sxs-lookup"><span data-stu-id="1c066-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="1c066-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="1c066-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="1c066-110">Gibt an, dass die ORDER BY-Operation nach der in `collation_name`angegebenen Sortierreihenfolge ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c066-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="1c066-111">COLLATE ist nur für Zeichenfolgenausdrücke anwendbar.</span><span class="sxs-lookup"><span data-stu-id="1c066-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="1c066-112">ASC</span><span class="sxs-lookup"><span data-stu-id="1c066-112">ASC</span></span>  
 <span data-ttu-id="1c066-113">Gibt an, dass die Werte der angegebenen Eigenschaft in aufsteigender Reihenfolge (vom kleinsten zum größten Wert) sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1c066-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="1c066-114">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="1c066-114">This is the default.</span></span>  
  
 <span data-ttu-id="1c066-115">DESC</span><span class="sxs-lookup"><span data-stu-id="1c066-115">DESC</span></span>  
 <span data-ttu-id="1c066-116">Gibt an, dass die Werte der angegebenen Eigenschaft in absteigender Reihenfolge (vom größten zum kleinsten Wert) sortiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1c066-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="1c066-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="1c066-117">LIMIT `n`</span></span>  
 <span data-ttu-id="1c066-118">Nur die ersten `n` -Elemente werden ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1c066-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="1c066-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="1c066-119">SKIP `n`</span></span>  
 <span data-ttu-id="1c066-120">Überspringt die ersten `n` -Elemente.</span><span class="sxs-lookup"><span data-stu-id="1c066-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c066-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c066-121">Remarks</span></span>  
 <span data-ttu-id="1c066-122">Die ORDER BY-Klausel wird logisch auf das Ergebnis der SELECT-Klausel angewendet.</span><span class="sxs-lookup"><span data-stu-id="1c066-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="1c066-123">In der ORDER BY-Klausel kann auf Elemente in der Auswahlliste verwiesen werden, indem deren Aliase verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c066-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="1c066-124">Die ORDER BY-Klausel kann auch auf andere Variablen verweisen, die sich aktuell im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="1c066-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="1c066-125">Wenn die SELECT-Klausel jedoch mit einem DISTINCT-Modifizierer angegeben wurde, kann von der ORDER BY-Klausel nur auf Aliase der SELECT-Klausel verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1c066-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="1c066-126">Jeder Ausdruck in der ORDER BY-Klausel muss zu einem Typ ausgewertet werden, der bzgl. geordneter Ungleichheit ("kleiner als", "größer als" usw.) verglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1c066-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="1c066-127">Bei diesen Typen handelt es sich im Allgemeinen um skalare primitive Typen wie Zahlen, Zeichenfolgen und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="1c066-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="1c066-128">"RowTypes" vergleichbarer Typen sind ebenfalls in der Reihenfolge vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="1c066-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="1c066-129">Wenn Code eine geordnete Menge durchläuft, wird, anders als bei einer Projektion in der obersten Ebene, die Reihenfolge bei der Ausgabe möglicherweise nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c066-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  
  
```  
-- In the following sample, order is guaranteed to be preserved:  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="1c066-130">Verwenden Sie folgendes Muster, um eine geordnete UNION, UNION ALL, EXCEPT oder INTERSECT-Operation durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="1c066-130">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="1c066-131">Eingeschränkte Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="1c066-131">Restricted keywords</span></span>  
 <span data-ttu-id="1c066-132">Die folgenden Schlüsselwörter müssen bei der Verwendung in einer `ORDER BY` -Klausel in Anführungszeichen gesetzt werden:</span><span class="sxs-lookup"><span data-stu-id="1c066-132">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="1c066-133">CROSS</span><span class="sxs-lookup"><span data-stu-id="1c066-133">CROSS</span></span>  
  
- <span data-ttu-id="1c066-134">FULL</span><span class="sxs-lookup"><span data-stu-id="1c066-134">FULL</span></span>  
  
- <span data-ttu-id="1c066-135">KEY</span><span class="sxs-lookup"><span data-stu-id="1c066-135">KEY</span></span>  
  
- <span data-ttu-id="1c066-136">NACH-LINKS</span><span class="sxs-lookup"><span data-stu-id="1c066-136">LEFT</span></span>  
  
- <span data-ttu-id="1c066-137">ORDER</span><span class="sxs-lookup"><span data-stu-id="1c066-137">ORDER</span></span>  
  
- <span data-ttu-id="1c066-138">OUTER</span><span class="sxs-lookup"><span data-stu-id="1c066-138">OUTER</span></span>  
  
- <span data-ttu-id="1c066-139">NACH-RECHTS</span><span class="sxs-lookup"><span data-stu-id="1c066-139">RIGHT</span></span>  
  
- <span data-ttu-id="1c066-140">ROW</span><span class="sxs-lookup"><span data-stu-id="1c066-140">ROW</span></span>  
  
- <span data-ttu-id="1c066-141">VALUE</span><span class="sxs-lookup"><span data-stu-id="1c066-141">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="1c066-142">Reihenfolge geschachtelter Abfragen</span><span class="sxs-lookup"><span data-stu-id="1c066-142">Ordering Nested Queries</span></span>  
 <span data-ttu-id="1c066-143">In Entity Framework kann ein geschachtelter Ausdruck an jeder Stelle in der Abfrage verwendet werden. Die Reihenfolge einer geschachtelten Abfrage wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1c066-143">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  
  
```  
-- The following query will order the results by the last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="1c066-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c066-144">Example</span></span>  
 <span data-ttu-id="1c066-145">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der ORDER BY-Operator verwendet, um die für von der SELECT-Anweisung zurückgegebene Objekte zu verwendende Sortierreihenfolge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c066-145">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="1c066-146">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="1c066-146">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1c066-147">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="1c066-147">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1c066-148">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="1c066-148">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1c066-149">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="1c066-149">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ORDERBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="1c066-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c066-150">See also</span></span>

- [<span data-ttu-id="1c066-151">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="1c066-151">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="1c066-152">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="1c066-152">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="1c066-153">SKIP</span><span class="sxs-lookup"><span data-stu-id="1c066-153">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="1c066-154">LIMIT</span><span class="sxs-lookup"><span data-stu-id="1c066-154">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="1c066-155">TOP</span><span class="sxs-lookup"><span data-stu-id="1c066-155">TOP</span></span>](top-entity-sql.md)
