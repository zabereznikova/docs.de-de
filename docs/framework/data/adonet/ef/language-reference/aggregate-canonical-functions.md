---
title: Aggregieren kanonischer Funktionen
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: f5d3584c6e9d35c9eb69b4f54cad45187416ee59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607452"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="d3ee8-102">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="d3ee8-102">Aggregate Canonical Functions</span></span>

<span data-ttu-id="d3ee8-103">Aggregate sind Ausdrücke, die eine Folge von Eingabewerten beispielsweise auf einen einzigen Wert reduzieren.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-103">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="d3ee8-104">Aggregate werden normalerweise zusammen mit der GROUP BY-Klausel des SELECT-Ausdrucks verwendet, und für ihre Verwendung gelten Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-104">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="d3ee8-105">Aggregieren kanonischer Funktionen von Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d3ee8-105">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="d3ee8-106">Im folgenden werden die kanonischen Entity SQL-Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-106">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="d3ee8-107">Avg (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-107">Avg(expression)</span></span>

<span data-ttu-id="d3ee8-108">Gibt den Durchschnitt der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-108">Returns the average of the non-null values.</span></span>

<span data-ttu-id="d3ee8-109">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-109">**Arguments**</span></span>

<span data-ttu-id="d3ee8-110">Ein `Int32`, `Int64`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-110">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d3ee8-111">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-111">**Return Value**</span></span>

<span data-ttu-id="d3ee8-112">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-112">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-113">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-113">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="d3ee8-114">BigCount (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-114">BigCount(expression)</span></span>

<span data-ttu-id="d3ee8-115">Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-115">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="d3ee8-116">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-116">**Arguments**</span></span>

<span data-ttu-id="d3ee8-117">Beliebiger Typ.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-117">Any type.</span></span>

<span data-ttu-id="d3ee8-118">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-118">**Return Value**</span></span>

<span data-ttu-id="d3ee8-119">Eine `Int64`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-119">An `Int64`.</span></span>

<span data-ttu-id="d3ee8-120">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-120">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="d3ee8-121">Count (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-121">Count(expression)</span></span>

<span data-ttu-id="d3ee8-122">Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-122">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="d3ee8-123">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-123">**Arguments**</span></span>

<span data-ttu-id="d3ee8-124">Beliebiger Typ.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-124">Any type.</span></span>

<span data-ttu-id="d3ee8-125">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-125">**Return Value**</span></span>

<span data-ttu-id="d3ee8-126">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-126">An `Int32`.</span></span>

<span data-ttu-id="d3ee8-127">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-127">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="d3ee8-128">Max (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-128">Max(expression)</span></span>

<span data-ttu-id="d3ee8-129">Gibt den Höchstwert der von null verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-129">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="d3ee8-130">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-130">**Arguments**</span></span>

<span data-ttu-id="d3ee8-131">`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .</span><span class="sxs-lookup"><span data-stu-id="d3ee8-131">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="d3ee8-132">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-132">**Return Value**</span></span>

<span data-ttu-id="d3ee8-133">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-133">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-134">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-134">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="d3ee8-135">Min (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-135">Min(expression)</span></span>

<span data-ttu-id="d3ee8-136">Gibt den geringsten Wert der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-136">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="d3ee8-137">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-137">**Arguments**</span></span>

<span data-ttu-id="d3ee8-138">`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .</span><span class="sxs-lookup"><span data-stu-id="d3ee8-138">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="d3ee8-139">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-139">**Return Value**</span></span>

<span data-ttu-id="d3ee8-140">Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-140">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-141">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-141">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="d3ee8-142">StDev (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-142">StDev(expression)</span></span>

<span data-ttu-id="d3ee8-143">Gibt die Standardabweichung der von NULL verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-143">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="d3ee8-144">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-144">**Arguments**</span></span>

<span data-ttu-id="d3ee8-145">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-145">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3ee8-146">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-146">**Return Value**</span></span>

<span data-ttu-id="d3ee8-147">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-147">A `Double`.</span></span> <span data-ttu-id="d3ee8-148">`Null`, wenn alle Eingabewerte `null`-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-148">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-149">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-149">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="d3ee8-150">StDevP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-150">StDevP(expression)</span></span>

<span data-ttu-id="d3ee8-151">Gibt die Standardabweichung zum Ausfüllen aller Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-151">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="d3ee8-152">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-152">**Arguments**</span></span>

<span data-ttu-id="d3ee8-153">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-153">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3ee8-154">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-154">**Return Value**</span></span>

<span data-ttu-id="d3ee8-155">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-155">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-156">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-156">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="d3ee8-157">Sum (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-157">Sum(expression)</span></span>

<span data-ttu-id="d3ee8-158">Gibt die Summe der von null verschiedenen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-158">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="d3ee8-159">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-159">**Arguments**</span></span>

<span data-ttu-id="d3ee8-160">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-160">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3ee8-161">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-161">**Return Value**</span></span>

<span data-ttu-id="d3ee8-162">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-162">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-163">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-163">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="d3ee8-164">Var (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-164">Var(expression)</span></span>

<span data-ttu-id="d3ee8-165">Gibt die Varianz aller Werte zurück, die keine Null-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-165">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="d3ee8-166">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-166">**Arguments**</span></span>

<span data-ttu-id="d3ee8-167">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-167">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3ee8-168">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-168">**Return Value**</span></span>

<span data-ttu-id="d3ee8-169">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-169">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-170">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-170">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="d3ee8-171">VarP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-171">VarP(expression)</span></span>

<span data-ttu-id="d3ee8-172">Gibt die Varianz für die Auffüllung aller Werte zurück, die keine Null-Werte sind.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-172">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="d3ee8-173">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-173">**Arguments**</span></span>

<span data-ttu-id="d3ee8-174">`Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-174">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3ee8-175">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-175">**Return Value**</span></span>

<span data-ttu-id="d3ee8-176">Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-176">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="d3ee8-177">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="d3ee8-177">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="d3ee8-178">Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-178">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="d3ee8-179">Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d3ee8-179">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="d3ee8-180">Auflistungsbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="d3ee8-180">Collection-based aggregates</span></span>

<span data-ttu-id="d3ee8-181">Auflistungsbasierte Aggregate (Auflistungsfunktionen) verarbeiten Auflistungen und geben einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-181">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="d3ee8-182">Zum Beispiel wenn ORDERS ist eine Auflistung aller Bestellungen, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:</span><span class="sxs-lookup"><span data-stu-id="d3ee8-182">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="d3ee8-183">Ausdrücke in auflistungsbasierten Aggregaten werden innerhalb des aktuellen umgebenden Namensauflösungsbereichs ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-183">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="d3ee8-184">Gruppenbasierte Aggregate</span><span class="sxs-lookup"><span data-stu-id="d3ee8-184">Group-based aggregates</span></span>

<span data-ttu-id="d3ee8-185">Gruppenbasierte Aggregate werden für eine Gruppe berechnet, die mit einer GROUP BY-Klausel definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-185">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="d3ee8-186">Für jede Gruppe im Ergebnis wird ein separates Aggregat berechnet, indem die Elemente in jeder Gruppe als Eingabe zur Aggregatberechnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-186">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="d3ee8-187">Wenn eine GROUP BY-Klausel in einem SELECT-Ausdruck verwendet wird, können sich in der Projektion oder ORDER BY-Klausel nur die Namen von Gruppierungsausdrücken, Aggregate oder konstante Ausdrücke befinden.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-187">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="d3ee8-188">Im folgenden Beispiel wird die durchschnittlich bestellte Anzahl für jedes Produkt berechnet:</span><span class="sxs-lookup"><span data-stu-id="d3ee8-188">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="d3ee8-189">Es ist möglich, eine Gruppenbasierte Aggregate ohne explizite Group by-Klausel im SELECT-Ausdruck haben.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-189">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="d3ee8-190">In diesem Fall werden alle Elemente als eine einzelne Gruppe behandelt.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-190">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="d3ee8-191">Dies entspricht der Angabe einer Gruppe auf Grundlage einer Konstante.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-191">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="d3ee8-192">Betrachten Sie beispielsweise folgenden Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="d3ee8-192">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="d3ee8-193">Dieser Ausdruck ist äquivalent zu Folgendem:</span><span class="sxs-lookup"><span data-stu-id="d3ee8-193">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="d3ee8-194">Ausdrücke in gruppenbasierten Aggregaten werden innerhalb des Namensauflösungsbereichs ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-194">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="d3ee8-195">Wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], Gruppenbasierte Aggregate können auch angeben, alles oder DISTINCT-Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-195">As in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="d3ee8-196">Wenn der DISTINCT-Modifizierer angegeben ist, werden Duplikate vor der Berechnung des Aggregats aus der Aggregateingabeauflistung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-196">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="d3ee8-197">Wenn der ALL-Modifizierer oder kein Modifizierer angegeben wird, werden Duplikate nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d3ee8-197">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3ee8-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3ee8-198">See also</span></span>

- [<span data-ttu-id="d3ee8-199">Canonical Functions (Kanonische Funktionen)</span><span class="sxs-lookup"><span data-stu-id="d3ee8-199">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
