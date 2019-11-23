---
title: GROUP BY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 711fbdc2d51177037cf349150c3431de14b11974
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833778"
---
# <a name="group-by-entity-sql"></a><span data-ttu-id="eca89-102">GROUP BY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="eca89-102">GROUP BY (Entity SQL)</span></span>
<span data-ttu-id="eca89-103">Gibt Gruppen an, in denen von einem Abfrageausdruck ([SELECT](select-entity-sql.md)) zurückgegebene Objekte platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eca89-103">Specifies groups into which objects returned by a query ([SELECT](select-entity-sql.md)) expression are to be placed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eca89-104">Syntax</span></span>  
  
```sql  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="eca89-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="eca89-105">Arguments</span></span>  
 `aliasedExpression`  
 <span data-ttu-id="eca89-106">Jeder gültige Abfrageausdruck, der gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="eca89-106">Any valid query expression on which grouping is performed.</span></span> <span data-ttu-id="eca89-107">`expression` kann eine Eigenschaft oder ein nicht aggregierter Ausdruck sein, der auf eine von der FROM-Klausel zurückgegebene Eigenschaft verweist.</span><span class="sxs-lookup"><span data-stu-id="eca89-107">`expression` can be a property or a non-aggregate expression that references a property returned by the FROM clause.</span></span> <span data-ttu-id="eca89-108">Die Auswertung jedes Ausdrucks in einer GROUP BY-Klausel muss einen Typ ergeben, der auf Gleichheit überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="eca89-108">Each expression in a GROUP BY clause must evaluate to a type that can be compared for equality.</span></span> <span data-ttu-id="eca89-109">Bei diesen Typen handelt es sich im Allgemeinen um skalare primitive Typen wie Zahlen, Zeichenfolgen und Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="eca89-109">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="eca89-110">Nach einer Auflistung kann nicht gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="eca89-110">You cannot group by a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eca89-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eca89-111">Remarks</span></span>  
 <span data-ttu-id="eca89-112">Wenn Aggregatfunktionen in der SELECT-Klausel enthalten sind \<Select List >, Group by berechnet einen Zusammenfassungs Wert für jede Gruppe.</span><span class="sxs-lookup"><span data-stu-id="eca89-112">If aggregate functions are included in the SELECT clause \<select list>, GROUP BY calculates a summary value for each group.</span></span> <span data-ttu-id="eca89-113">Wenn GROUP BY angegeben wird, muss jeder Eigenschaftsname jedes Nichtaggregatausdrucks in der Auswahlliste in der GROUP BY-Liste eingeschlossen sein, oder der GROUP BY-Ausdruck muss dem Auswahllistenausdruck genau entsprechen.</span><span class="sxs-lookup"><span data-stu-id="eca89-113">When GROUP BY is specified, either each property name in any nonaggregate expression in the select list should be included in the GROUP BY list, or the GROUP BY expression must exactly match the select list expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eca89-114">Falls die ORDER BY-Klausel nicht angegeben wird, haben die von der GROUP BY-Klausel zurückgegebenen Gruppen keine feste Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="eca89-114">If the ORDER BY clause is not specified, groups returned by the GROUP BY clause are not in any particular order.</span></span> <span data-ttu-id="eca89-115">Es wird empfohlen, dass Sie die ORDER BY-Klausel zum Angeben einer bestimmten Reihenfolge von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="eca89-115">To specify a particular ordering of the data, we recommend that you always use the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="eca89-116">Wenn eine GROUP BY-Klausel angegeben wird, ob explizit oder implizit (beispielsweise aufgrund einer HAVING-Klausel in der Abfrage), wird der aktuelle Bereich versteckt und ein neuer Bereich eingeführt.</span><span class="sxs-lookup"><span data-stu-id="eca89-116">When a GROUP BY clause is specified, either explicitly or implicitly (for example, by a HAVING clause in the query), the current scope is hidden, and a new scope is introduced.</span></span>  
  
 <span data-ttu-id="eca89-117">Die Klauseln SELECT, HAVING und ORDER BY können nicht mehr auf in der FROM-Klausel angegebene Elementnamen verweisen.</span><span class="sxs-lookup"><span data-stu-id="eca89-117">The SELECT clause, the HAVING clause, and the ORDER BY clause will no longer be able to refer to element names specified in the FROM clause.</span></span> <span data-ttu-id="eca89-118">Es kann nur auf die Gruppierungsausdrücke selbst verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="eca89-118">You can only refer to the grouping expressions themselves.</span></span> <span data-ttu-id="eca89-119">Zu diesem Zweck können den Gruppierungsausdrücken neue Namen (Aliase) zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="eca89-119">To do this, you can assign new names (aliases) to each grouping expression.</span></span> <span data-ttu-id="eca89-120">Wenn für einen Gruppierungsausdruck kein Alias angegeben wird, versucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen solchen mithilfe der Regeln zur Aliaserstellung zu generieren. Das ist im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eca89-120">If no alias is specified for a grouping expression, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate one by using the alias generation rules, as illustrated in the following example.</span></span>  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 <span data-ttu-id="eca89-121">Ausdrücke in der GROUP BY-Klausel können nicht auf vorher in derselben GROUP BY-Klausel definierte Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="eca89-121">Expressions in the GROUP BY clause cannot refer to names defined earlier in the same GROUP BY clause.</span></span>  
  
 <span data-ttu-id="eca89-122">Zusätzlich zu Gruppierungsnamen können in den Klauseln SELECT, HAVING und ORDER BY auch Aggregate angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eca89-122">In addition to grouping names, you can also specify aggregates in the SELECT clause, HAVING clause, and the ORDER BY clause.</span></span> <span data-ttu-id="eca89-123">Ein Aggregat enthält einen Ausdruck, der für jedes Element der Gruppe ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="eca89-123">An aggregate contains an expression that is evaluated for each element of the group.</span></span> <span data-ttu-id="eca89-124">Der Aggregatoperator führt die Werte aller dieser Ausdrücke zusammen (meist, aber nicht immer, in einen einzelnen Wert).</span><span class="sxs-lookup"><span data-stu-id="eca89-124">The aggregate operator reduces the values of all these expressions (usually, but not always, into a single value).</span></span> <span data-ttu-id="eca89-125">Der Aggregatausdruck kann auf die im übergeordneten Bereich sichtbaren ursprünglichen Elementnamen oder auf die neuen, in der GROUP BY-Klausel selbst eingeführten Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="eca89-125">The aggregate expression can make references to the original element names visible in the parent scope, or to any of the new names introduced by the GROUP BY clause itself.</span></span> <span data-ttu-id="eca89-126">Obwohl die Aggregate in den Klauseln SELECT, HAVING oder ORDER BY stehen, werden sie im selben Bereich wie die Gruppierungsausdrücke ausgewertet. Dies wird im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="eca89-126">Although the aggregates appear in the SELECT clause, HAVING clause, and ORDER BY clause, they are actually evaluated under the same scope as the grouping expressions, as illustrated in the following example.</span></span>  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 <span data-ttu-id="eca89-127">In dieser Abfrage wird die GROUP BY-Klausel verwendet, um einen nach Produkten aufgeschlüsselten Bericht der Kosten aller bestellten Produkte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eca89-127">This query uses the GROUP BY clause to produce a report of the cost of all products ordered, broken down by product.</span></span> <span data-ttu-id="eca89-128">Der Name `name` des Produkts wird als Teil des Gruppierungsausdrucks angegeben, und auf diesen Namen wird daraufhin in der SELECT-Liste verwiesen.</span><span class="sxs-lookup"><span data-stu-id="eca89-128">It gives the name `name` to the product as part of the grouping expression, and then references that name in the SELECT list.</span></span> <span data-ttu-id="eca89-129">Weiterhin wird das Aggregat `sum` in der SELECT-Liste angegeben, das intern auf den Preis und die Menge der Auftragsposition verweist.</span><span class="sxs-lookup"><span data-stu-id="eca89-129">It also specifies the aggregate `sum` in the SELECT list that internally references the price and quantity of the order line.</span></span>  
  
 <span data-ttu-id="eca89-130">Jeder GROUP BY-Schlüsselausdruck muss über mindestens einen Verweis auf den Eingabebereich verfügen:</span><span class="sxs-lookup"><span data-stu-id="eca89-130">Each GROUP By key expression must have at least one reference to the input scope:</span></span>  
  
```sql  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 <span data-ttu-id="eca89-131">Ein Beispiel für die Verwendung von GROUP BY finden Sie unter [HAVING](having-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="eca89-131">For an example of using GROUP BY, see [HAVING](having-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eca89-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eca89-132">Example</span></span>  
 <span data-ttu-id="eca89-133">In der folgenden Entity SQL-Abfrage wird der GROUP BY-Operator verwendet, um Gruppen anzugeben, in die Objekte von einer Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eca89-133">The following Entity SQL query uses the GROUP BY operator to specify groups into which objects are returned by a query.</span></span> <span data-ttu-id="eca89-134">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="eca89-134">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="eca89-135">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="eca89-135">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="eca89-136">Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="eca89-136">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="eca89-137">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="eca89-137">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#GROUPBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#groupby)]  
  
## <a name="see-also"></a><span data-ttu-id="eca89-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eca89-138">See also</span></span>

- [<span data-ttu-id="eca89-139">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="eca89-139">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="eca89-140">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="eca89-140">Query Expressions</span></span>](query-expressions-entity-sql.md)
