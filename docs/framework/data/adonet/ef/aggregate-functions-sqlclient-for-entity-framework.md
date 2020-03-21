---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150648"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="f6423-102">Aggregatfunktionen (SqlClient für Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="f6423-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="f6423-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f6423-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="f6423-104">Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="f6423-105">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f6423-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="f6423-106">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6423-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="f6423-107">Im Folgenden sind die SqlClient-Aggregatfunktionen zu finden.</span><span class="sxs-lookup"><span data-stu-id="f6423-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="f6423-108">AVG(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-108">AVG(expression)</span></span>

<span data-ttu-id="f6423-109">Gibt den Durchschnitt aller Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="f6423-110">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f6423-110">Null values are ignored.</span></span>

<span data-ttu-id="f6423-111">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-111">**Arguments**</span></span>

<span data-ttu-id="f6423-112">An `Int32` `Int64`, `Double`, `Decimal`und .</span><span class="sxs-lookup"><span data-stu-id="f6423-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="f6423-113">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-113">**Return Value**</span></span>

<span data-ttu-id="f6423-114">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="f6423-114">The type of `expression`.</span></span>

<span data-ttu-id="f6423-115">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="f6423-116">CHECKSUM_AGG(Sammlung)</span><span class="sxs-lookup"><span data-stu-id="f6423-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="f6423-117">Gibt die Prüfsumme der Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="f6423-118">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f6423-118">Null values are ignored.</span></span>

 <span data-ttu-id="f6423-119">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-119">**Arguments**</span></span>

 <span data-ttu-id="f6423-120">Eine Auflistung(`Int32`).</span><span class="sxs-lookup"><span data-stu-id="f6423-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="f6423-121">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-121">**Return Value**</span></span>

 <span data-ttu-id="f6423-122">Ein `Int32`-Element.</span><span class="sxs-lookup"><span data-stu-id="f6423-122">An `Int32`.</span></span>

 <span data-ttu-id="f6423-123">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="f6423-124">COUNT(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-124">COUNT(expression)</span></span>

<span data-ttu-id="f6423-125">Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="f6423-126">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-126">**Arguments**</span></span>

<span data-ttu-id="f6423-127">Eine\<Auflistung T>, wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="f6423-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="f6423-128">`Guid`(nicht in SQL Server 2000 zurückgegeben)</span><span class="sxs-lookup"><span data-stu-id="f6423-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="f6423-129">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-129">**Return Value**</span></span>

<span data-ttu-id="f6423-130">Ein `Int32`-Element.</span><span class="sxs-lookup"><span data-stu-id="f6423-130">An `Int32`.</span></span>

<span data-ttu-id="f6423-131">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="f6423-132">COUNT_BIG(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="f6423-133">Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="f6423-134">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-134">**Arguments**</span></span>

 <span data-ttu-id="f6423-135">Eine Auflistung(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="f6423-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="f6423-136">`Guid`(nicht in SQL Server 2000 zurückgegeben)</span><span class="sxs-lookup"><span data-stu-id="f6423-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="f6423-137">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-137">**Return Value**</span></span>

<span data-ttu-id="f6423-138">Ein `Int64`-Element.</span><span class="sxs-lookup"><span data-stu-id="f6423-138">An `Int64`.</span></span>

<span data-ttu-id="f6423-139">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="f6423-140">MAX(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-140">MAX(expression)</span></span>

<span data-ttu-id="f6423-141">Gibt den Maximalwert der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="f6423-142">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-142">**Arguments**</span></span>

<span data-ttu-id="f6423-143">Eine Auflistung(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="f6423-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="f6423-144">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-144">**Return Value**</span></span>

<span data-ttu-id="f6423-145">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="f6423-145">The type of `expression`.</span></span>

<span data-ttu-id="f6423-146">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="f6423-147">MIN(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-147">MIN(expression)</span></span>

<span data-ttu-id="f6423-148">Gibt den Minimalwert in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="f6423-149">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-149">**Arguments**</span></span>

<span data-ttu-id="f6423-150">Eine Auflistung(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="f6423-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="f6423-151">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-151">**Return Value**</span></span>

<span data-ttu-id="f6423-152">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="f6423-152">The type of `expression`.</span></span>

<span data-ttu-id="f6423-153">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="f6423-154">STDEV(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-154">STDEV(expression)</span></span>

<span data-ttu-id="f6423-155">Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="f6423-156">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-156">**Arguments**</span></span>

<span data-ttu-id="f6423-157">Eine Auflistung(`Double`).</span><span class="sxs-lookup"><span data-stu-id="f6423-157">A Collection(`Double`).</span></span>

<span data-ttu-id="f6423-158">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-158">**Return Value**</span></span>

<span data-ttu-id="f6423-159">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="f6423-159">A `Double`.</span></span>

<span data-ttu-id="f6423-160">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="f6423-161">STDEVP(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-161">STDEVP(expression)</span></span>

<span data-ttu-id="f6423-162">Gibt die statistische Standardabweichung für die Grundgesamtheit (Population) aller Werte des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="f6423-163">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-163">**Arguments**</span></span>

<span data-ttu-id="f6423-164">Eine Auflistung(`Double`).</span><span class="sxs-lookup"><span data-stu-id="f6423-164">A Collection(`Double`).</span></span>

<span data-ttu-id="f6423-165">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-165">**Return Value**</span></span>

<span data-ttu-id="f6423-166">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="f6423-166">A `Double`.</span></span>

<span data-ttu-id="f6423-167">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="f6423-168">SUMME(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-168">SUM(expression)</span></span>

<span data-ttu-id="f6423-169">Gibt die Summe aller Werte in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="f6423-170">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-170">**Arguments**</span></span>

<span data-ttu-id="f6423-171">Eine Auflistung(T), bei der T einer `Int32` `Int64`der `Double` `Decimal`folgenden Typen ist: , , , .</span><span class="sxs-lookup"><span data-stu-id="f6423-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="f6423-172">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-172">**Return Value**</span></span>

<span data-ttu-id="f6423-173">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="f6423-173">The type of `expression`.</span></span>

<span data-ttu-id="f6423-174">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="f6423-175">VAR(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-175">VAR(expression)</span></span>

<span data-ttu-id="f6423-176">Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="f6423-177">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-177">**Arguments**</span></span>

<span data-ttu-id="f6423-178">Eine Auflistung(`Double`).</span><span class="sxs-lookup"><span data-stu-id="f6423-178">A Collection(`Double`).</span></span>

<span data-ttu-id="f6423-179">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-179">**Return Value**</span></span>

<span data-ttu-id="f6423-180">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="f6423-180">A `Double`.</span></span>

<span data-ttu-id="f6423-181">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="f6423-182">VARP(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="f6423-182">VARP(expression)</span></span>

<span data-ttu-id="f6423-183">Gibt die statistische Varianz für die Grundgesamtheit aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="f6423-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="f6423-184">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="f6423-184">**Arguments**</span></span>

<span data-ttu-id="f6423-185">Eine Auflistung(`Double`).</span><span class="sxs-lookup"><span data-stu-id="f6423-185">A Collection(`Double`).</span></span>

<span data-ttu-id="f6423-186">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="f6423-186">**Return Value**</span></span>

<span data-ttu-id="f6423-187">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="f6423-187">A `Double`.</span></span>

<span data-ttu-id="f6423-188">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="f6423-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="f6423-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6423-189">See also</span></span>

- [<span data-ttu-id="f6423-190">Aggregatfunktionen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f6423-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="f6423-191">Entity SQL-Sprache</span><span class="sxs-lookup"><span data-stu-id="f6423-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="f6423-192">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="f6423-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
