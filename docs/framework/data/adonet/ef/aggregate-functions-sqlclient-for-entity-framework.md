---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1c32ccfe18c67c9baeb7df0f981c9129b3bbc8bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204514"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="b880c-102">Aggregatfunktionen (SqlClient für Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="b880c-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>

<span data-ttu-id="b880c-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b880c-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="b880c-104">Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="b880c-105">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b880c-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="b880c-106">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b880c-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="b880c-107">Im folgenden finden Sie die SqlClient-Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b880c-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="b880c-108">AVG (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-108">AVG(expression)</span></span>

<span data-ttu-id="b880c-109">Gibt den Durchschnitt aller Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="b880c-110">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b880c-110">Null values are ignored.</span></span>

<span data-ttu-id="b880c-111">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-111">**Arguments**</span></span>

<span data-ttu-id="b880c-112">`Int32`, `Int64` , `Double` Und `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="b880c-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b880c-113">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-113">**Return Value**</span></span>

<span data-ttu-id="b880c-114">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="b880c-114">The type of `expression`.</span></span>

<span data-ttu-id="b880c-115">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="b880c-116">CHECKSUM_AGG (Sammlung)</span><span class="sxs-lookup"><span data-stu-id="b880c-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="b880c-117">Gibt die Prüfsumme der Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="b880c-118">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="b880c-118">Null values are ignored.</span></span>

 <span data-ttu-id="b880c-119">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-119">**Arguments**</span></span>

 <span data-ttu-id="b880c-120">Eine-Auflistung ( `Int32` ).</span><span class="sxs-lookup"><span data-stu-id="b880c-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="b880c-121">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-121">**Return Value**</span></span>

 <span data-ttu-id="b880c-122">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="b880c-122">An `Int32`.</span></span>

 <span data-ttu-id="b880c-123">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="b880c-124">COUNT(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-124">COUNT(expression)</span></span>

<span data-ttu-id="b880c-125">Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="b880c-126">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-126">**Arguments**</span></span>

<span data-ttu-id="b880c-127">Eine-Auflistung \<T> , wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="b880c-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="b880c-128">`Guid` (nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="b880c-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="b880c-129">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-129">**Return Value**</span></span>

<span data-ttu-id="b880c-130">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="b880c-130">An `Int32`.</span></span>

<span data-ttu-id="b880c-131">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="b880c-132">COUNT_BIG (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="b880c-133">Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="b880c-134">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-134">**Arguments**</span></span>

 <span data-ttu-id="b880c-135">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="b880c-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="b880c-136">`Guid` (nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="b880c-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="b880c-137">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-137">**Return Value**</span></span>

<span data-ttu-id="b880c-138">Eine `Int64`.</span><span class="sxs-lookup"><span data-stu-id="b880c-138">An `Int64`.</span></span>

<span data-ttu-id="b880c-139">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="b880c-140">MAX(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-140">MAX(expression)</span></span>

<span data-ttu-id="b880c-141">Gibt den Maximalwert der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="b880c-142">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-142">**Arguments**</span></span>

<span data-ttu-id="b880c-143">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="b880c-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="b880c-144">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-144">**Return Value**</span></span>

<span data-ttu-id="b880c-145">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="b880c-145">The type of `expression`.</span></span>

<span data-ttu-id="b880c-146">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="b880c-147">MIN(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-147">MIN(expression)</span></span>

<span data-ttu-id="b880c-148">Gibt den Minimalwert in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="b880c-149">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-149">**Arguments**</span></span>

<span data-ttu-id="b880c-150">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="b880c-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="b880c-151">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-151">**Return Value**</span></span>

<span data-ttu-id="b880c-152">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="b880c-152">The type of `expression`.</span></span>

<span data-ttu-id="b880c-153">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="b880c-154">StDev (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-154">STDEV(expression)</span></span>

<span data-ttu-id="b880c-155">Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="b880c-156">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-156">**Arguments**</span></span>

<span data-ttu-id="b880c-157">Eine-Auflistung ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="b880c-157">A Collection(`Double`).</span></span>

<span data-ttu-id="b880c-158">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-158">**Return Value**</span></span>

<span data-ttu-id="b880c-159">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="b880c-159">A `Double`.</span></span>

<span data-ttu-id="b880c-160">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="b880c-161">STDE VP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-161">STDEVP(expression)</span></span>

<span data-ttu-id="b880c-162">Gibt die statistische Standardabweichung für die Grundgesamtheit (Population) aller Werte des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="b880c-163">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-163">**Arguments**</span></span>

<span data-ttu-id="b880c-164">Eine-Auflistung ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="b880c-164">A Collection(`Double`).</span></span>

<span data-ttu-id="b880c-165">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-165">**Return Value**</span></span>

<span data-ttu-id="b880c-166">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="b880c-166">A `Double`.</span></span>

<span data-ttu-id="b880c-167">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="b880c-168">SUM(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-168">SUM(expression)</span></span>

<span data-ttu-id="b880c-169">Gibt die Summe aller Werte in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="b880c-170">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-170">**Arguments**</span></span>

<span data-ttu-id="b880c-171">Eine Auflistung (t), wobei t einer der folgenden Typen ist: `Int32` , `Int64` , `Double` , `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="b880c-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="b880c-172">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-172">**Return Value**</span></span>

<span data-ttu-id="b880c-173">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="b880c-173">The type of `expression`.</span></span>

<span data-ttu-id="b880c-174">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="b880c-175">VAR (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-175">VAR(expression)</span></span>

<span data-ttu-id="b880c-176">Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="b880c-177">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-177">**Arguments**</span></span>

<span data-ttu-id="b880c-178">Eine-Auflistung ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="b880c-178">A Collection(`Double`).</span></span>

<span data-ttu-id="b880c-179">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-179">**Return Value**</span></span>

<span data-ttu-id="b880c-180">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="b880c-180">A `Double`.</span></span>

<span data-ttu-id="b880c-181">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="b880c-182">VarP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="b880c-182">VARP(expression)</span></span>

<span data-ttu-id="b880c-183">Gibt die statistische Varianz für die Grundgesamtheit aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="b880c-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="b880c-184">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="b880c-184">**Arguments**</span></span>

<span data-ttu-id="b880c-185">Eine-Auflistung ( `Double` ).</span><span class="sxs-lookup"><span data-stu-id="b880c-185">A Collection(`Double`).</span></span>

<span data-ttu-id="b880c-186">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="b880c-186">**Return Value**</span></span>

<span data-ttu-id="b880c-187">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="b880c-187">A `Double`.</span></span>

<span data-ttu-id="b880c-188">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="b880c-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="b880c-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b880c-189">See also</span></span>

- [<span data-ttu-id="b880c-190">Aggregatfunktionen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b880c-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="b880c-191">Entity SQL-Sprache</span><span class="sxs-lookup"><span data-stu-id="b880c-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="b880c-192">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="b880c-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
