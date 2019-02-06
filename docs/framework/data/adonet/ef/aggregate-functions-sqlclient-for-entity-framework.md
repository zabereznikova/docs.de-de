---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758699"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="40d1d-102">Aggregatfunktionen (SqlClient für Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="40d1d-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="40d1d-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40d1d-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="40d1d-104">Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="40d1d-105">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="40d1d-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="40d1d-106">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40d1d-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="40d1d-107">Im folgenden sind die SqlClient-Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="40d1d-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="40d1d-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-108">AVG(expression)</span></span>

<span data-ttu-id="40d1d-109">Gibt den Durchschnitt aller Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="40d1d-110">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="40d1d-110">Null values are ignored.</span></span>

<span data-ttu-id="40d1d-111">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-111">**Arguments**</span></span>

<span data-ttu-id="40d1d-112">Ein `Int32`, `Int64`, `Double`, und `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="40d1d-113">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-113">**Return Value**</span></span>

<span data-ttu-id="40d1d-114">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40d1d-114">The type of `expression`.</span></span>

<span data-ttu-id="40d1d-115">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="40d1d-116">CHECKSUM_AGG(Collection)</span><span class="sxs-lookup"><span data-stu-id="40d1d-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="40d1d-117">Gibt die Prüfsumme der Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="40d1d-118">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="40d1d-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="40d1d-119">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-119">**Arguments**</span></span>
 
 <span data-ttu-id="40d1d-120">Eine Auflistung (`Int32`).</span><span class="sxs-lookup"><span data-stu-id="40d1d-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="40d1d-121">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-121">**Return Value**</span></span>
 
 <span data-ttu-id="40d1d-122">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-122">An `Int32`.</span></span>
 
 <span data-ttu-id="40d1d-123">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="40d1d-124">Count(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="40d1d-124">COUNT(expression)</span></span>

<span data-ttu-id="40d1d-125">Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="40d1d-126">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-126">**Arguments**</span></span>

<span data-ttu-id="40d1d-127">Eine Auflistung\<T >, wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="40d1d-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="40d1d-128">`Guid` (nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="40d1d-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="40d1d-129">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-129">**Return Value**</span></span>

<span data-ttu-id="40d1d-130">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-130">An `Int32`.</span></span>

<span data-ttu-id="40d1d-131">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="40d1d-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="40d1d-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="40d1d-133">COUNT_BIG(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="40d1d-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="40d1d-134">Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="40d1d-135">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-135">**Arguments**</span></span>
 
 <span data-ttu-id="40d1d-136">Eine Collection(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="40d1d-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="40d1d-137">`Guid` (nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="40d1d-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="40d1d-138">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-138">**Return Value**</span></span>

<span data-ttu-id="40d1d-139">Eine `Int64`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-139">An `Int64`.</span></span>

<span data-ttu-id="40d1d-140">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="40d1d-141">Max(Expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-141">MAX(expression)</span></span>

<span data-ttu-id="40d1d-142">Gibt den Maximalwert der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="40d1d-143">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-143">**Arguments**</span></span>

<span data-ttu-id="40d1d-144">Eine Collection(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="40d1d-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="40d1d-145">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-145">**Return Value**</span></span>

<span data-ttu-id="40d1d-146">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40d1d-146">The type of `expression`.</span></span>

<span data-ttu-id="40d1d-147">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="40d1d-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-148">MIN(expression)</span></span>

<span data-ttu-id="40d1d-149">Gibt den Minimalwert in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="40d1d-150">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-150">**Arguments**</span></span>

<span data-ttu-id="40d1d-151">Eine Collection(T), wobei T einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="40d1d-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="40d1d-152">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-152">**Return Value**</span></span>

<span data-ttu-id="40d1d-153">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40d1d-153">The type of `expression`.</span></span>

<span data-ttu-id="40d1d-154">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="40d1d-155">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-155">STDEV(expression)</span></span>

<span data-ttu-id="40d1d-156">Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="40d1d-157">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-157">**Arguments**</span></span>

<span data-ttu-id="40d1d-158">Eine Auflistung (`Double`).</span><span class="sxs-lookup"><span data-stu-id="40d1d-158">A Collection(`Double`).</span></span>

<span data-ttu-id="40d1d-159">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-159">**Return Value**</span></span>

<span data-ttu-id="40d1d-160">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-160">A `Double`.</span></span>

<span data-ttu-id="40d1d-161">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="40d1d-162">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-162">STDEVP(expression)</span></span>

<span data-ttu-id="40d1d-163">Gibt die statistische Standardabweichung für die Auffüllung für alle Werte des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="40d1d-164">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-164">**Arguments**</span></span>

<span data-ttu-id="40d1d-165">Eine Auflistung (`Double`).</span><span class="sxs-lookup"><span data-stu-id="40d1d-165">A Collection(`Double`).</span></span>

<span data-ttu-id="40d1d-166">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-166">**Return Value**</span></span>

<span data-ttu-id="40d1d-167">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-167">A `Double`.</span></span>

<span data-ttu-id="40d1d-168">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="40d1d-169">SUM(Expression)</span><span class="sxs-lookup"><span data-stu-id="40d1d-169">SUM(expression)</span></span>

<span data-ttu-id="40d1d-170">Gibt die Summe aller Werte in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="40d1d-171">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-171">**Arguments**</span></span>

<span data-ttu-id="40d1d-172">Eine Collection(T), wobei T einer der folgenden Typen ist: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="40d1d-173">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-173">**Return Value**</span></span>

<span data-ttu-id="40d1d-174">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="40d1d-174">The type of `expression`.</span></span>

<span data-ttu-id="40d1d-175">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="40d1d-176">Var(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="40d1d-176">VAR(expression)</span></span>

<span data-ttu-id="40d1d-177">Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="40d1d-178">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-178">**Arguments**</span></span>

<span data-ttu-id="40d1d-179">Eine Auflistung (`Double`).</span><span class="sxs-lookup"><span data-stu-id="40d1d-179">A Collection(`Double`).</span></span>

<span data-ttu-id="40d1d-180">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-180">**Return Value**</span></span>

<span data-ttu-id="40d1d-181">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-181">A `Double`.</span></span>

<span data-ttu-id="40d1d-182">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="40d1d-183">VarP(Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="40d1d-183">VARP(expression)</span></span>

<span data-ttu-id="40d1d-184">Gibt die statistische Varianz für die Auffüllung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="40d1d-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="40d1d-185">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="40d1d-185">**Arguments**</span></span>

<span data-ttu-id="40d1d-186">Eine Auflistung (`Double`).</span><span class="sxs-lookup"><span data-stu-id="40d1d-186">A Collection(`Double`).</span></span>

<span data-ttu-id="40d1d-187">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="40d1d-187">**Return Value**</span></span>

<span data-ttu-id="40d1d-188">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="40d1d-188">A `Double`.</span></span>

<span data-ttu-id="40d1d-189">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="40d1d-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="40d1d-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40d1d-190">See also</span></span>

<span data-ttu-id="40d1d-191">Weitere Informationen zu den von SqlClient unterstützten Aggregatfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="40d1d-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="40d1d-192">**SQL Server 2005:** [Aggregatfunktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="40d1d-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="40d1d-193">**SQLServer 2008 und höher:** [Aggregatfunktionen (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="40d1d-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="40d1d-194">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="40d1d-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="40d1d-195">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="40d1d-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
