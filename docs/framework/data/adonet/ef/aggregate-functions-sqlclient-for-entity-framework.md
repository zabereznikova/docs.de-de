---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251707"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="2002a-102">Aggregatfunktionen (SqlClient für Entity Framework)</span><span class="sxs-lookup"><span data-stu-id="2002a-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="2002a-103">Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2002a-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="2002a-104">Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="2002a-105">Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2002a-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="2002a-106">Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2002a-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="2002a-107">Im folgenden finden Sie die SqlClient-Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="2002a-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="2002a-108">AVG (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-108">AVG(expression)</span></span>

<span data-ttu-id="2002a-109">Gibt den Durchschnitt aller Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="2002a-110">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2002a-110">Null values are ignored.</span></span>

<span data-ttu-id="2002a-111">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-111">**Arguments**</span></span>

<span data-ttu-id="2002a-112">`Int32`, ,`Int64` Und`Decimal`. `Double`</span><span class="sxs-lookup"><span data-stu-id="2002a-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="2002a-113">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-113">**Return Value**</span></span>

<span data-ttu-id="2002a-114">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="2002a-114">The type of `expression`.</span></span>

<span data-ttu-id="2002a-115">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="2002a-116">CHECKSUM_AGG (Sammlung)</span><span class="sxs-lookup"><span data-stu-id="2002a-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="2002a-117">Gibt die Prüfsumme der Werte in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="2002a-118">NULL-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2002a-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="2002a-119">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-119">**Arguments**</span></span>
 
 <span data-ttu-id="2002a-120">Eine-Auflistung`Int32`().</span><span class="sxs-lookup"><span data-stu-id="2002a-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="2002a-121">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-121">**Return Value**</span></span>
 
 <span data-ttu-id="2002a-122">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="2002a-122">An `Int32`.</span></span>
 
 <span data-ttu-id="2002a-123">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="2002a-124">COUNT (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-124">COUNT(expression)</span></span>

<span data-ttu-id="2002a-125">Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="2002a-126">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-126">**Arguments**</span></span>

<span data-ttu-id="2002a-127">Eine Auflistung\<t->, wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="2002a-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="2002a-128">`Guid`(nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="2002a-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="2002a-129">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-129">**Return Value**</span></span>

<span data-ttu-id="2002a-130">Eine `Int32`.</span><span class="sxs-lookup"><span data-stu-id="2002a-130">An `Int32`.</span></span>

<span data-ttu-id="2002a-131">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="2002a-132">[! Code-SQL[DP entityservices-Konzepte # SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="2002a-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="count_bigexpression"></a><span data-ttu-id="2002a-133">COUNT_BIG (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="2002a-134">Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="2002a-135">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-135">**Arguments**</span></span>
 
 <span data-ttu-id="2002a-136">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="2002a-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="2002a-137">`Guid`(nicht zurückgegeben in SQL Server 2000)</span><span class="sxs-lookup"><span data-stu-id="2002a-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="2002a-138">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-138">**Return Value**</span></span>

<span data-ttu-id="2002a-139">Eine `Int64`.</span><span class="sxs-lookup"><span data-stu-id="2002a-139">An `Int64`.</span></span>

<span data-ttu-id="2002a-140">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="2002a-141">Max (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-141">MAX(expression)</span></span>

<span data-ttu-id="2002a-142">Gibt den Maximalwert der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="2002a-143">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-143">**Arguments**</span></span>

<span data-ttu-id="2002a-144">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="2002a-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="2002a-145">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-145">**Return Value**</span></span>

<span data-ttu-id="2002a-146">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="2002a-146">The type of `expression`.</span></span>

<span data-ttu-id="2002a-147">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="2002a-148">MIN (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-148">MIN(expression)</span></span>

<span data-ttu-id="2002a-149">Gibt den Minimalwert in einer Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="2002a-150">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-150">**Arguments**</span></span>

<span data-ttu-id="2002a-151">Eine Auflistung (t), wobei t einer der folgenden Typen ist:</span><span class="sxs-lookup"><span data-stu-id="2002a-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="2002a-152">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-152">**Return Value**</span></span>

<span data-ttu-id="2002a-153">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="2002a-153">The type of `expression`.</span></span>

<span data-ttu-id="2002a-154">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="2002a-155">StDev (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-155">STDEV(expression)</span></span>

<span data-ttu-id="2002a-156">Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="2002a-157">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-157">**Arguments**</span></span>

<span data-ttu-id="2002a-158">Eine-Auflistung`Double`().</span><span class="sxs-lookup"><span data-stu-id="2002a-158">A Collection(`Double`).</span></span>

<span data-ttu-id="2002a-159">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-159">**Return Value**</span></span>

<span data-ttu-id="2002a-160">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="2002a-160">A `Double`.</span></span>

<span data-ttu-id="2002a-161">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="2002a-162">STDE VP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-162">STDEVP(expression)</span></span>

<span data-ttu-id="2002a-163">Gibt die statistische Standardabweichung für die Auffüllung für alle Werte des angegebenen Ausdrucks zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="2002a-164">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-164">**Arguments**</span></span>

<span data-ttu-id="2002a-165">Eine-Auflistung`Double`().</span><span class="sxs-lookup"><span data-stu-id="2002a-165">A Collection(`Double`).</span></span>

<span data-ttu-id="2002a-166">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-166">**Return Value**</span></span>

<span data-ttu-id="2002a-167">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="2002a-167">A `Double`.</span></span>

<span data-ttu-id="2002a-168">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="2002a-169">Sum (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-169">SUM(expression)</span></span>

<span data-ttu-id="2002a-170">Gibt die Summe aller Werte in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="2002a-171">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-171">**Arguments**</span></span>

<span data-ttu-id="2002a-172">Eine Auflistung (t), wobei t einer der folgenden Typen ist: `Int32`, `Int64`, `Double`, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="2002a-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="2002a-173">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-173">**Return Value**</span></span>

<span data-ttu-id="2002a-174">Der `expression`-Typ.</span><span class="sxs-lookup"><span data-stu-id="2002a-174">The type of `expression`.</span></span>

<span data-ttu-id="2002a-175">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="2002a-176">VAR (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-176">VAR(expression)</span></span>

<span data-ttu-id="2002a-177">Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="2002a-178">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-178">**Arguments**</span></span>

<span data-ttu-id="2002a-179">Eine-Auflistung`Double`().</span><span class="sxs-lookup"><span data-stu-id="2002a-179">A Collection(`Double`).</span></span>

<span data-ttu-id="2002a-180">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-180">**Return Value**</span></span>

<span data-ttu-id="2002a-181">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="2002a-181">A `Double`.</span></span>

<span data-ttu-id="2002a-182">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="2002a-183">VarP (Ausdruck)</span><span class="sxs-lookup"><span data-stu-id="2002a-183">VARP(expression)</span></span>

<span data-ttu-id="2002a-184">Gibt die statistische Varianz für die Auffüllung aller Werte im angegebenen Ausdruck zurück.</span><span class="sxs-lookup"><span data-stu-id="2002a-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="2002a-185">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="2002a-185">**Arguments**</span></span>

<span data-ttu-id="2002a-186">Eine-Auflistung`Double`().</span><span class="sxs-lookup"><span data-stu-id="2002a-186">A Collection(`Double`).</span></span>

<span data-ttu-id="2002a-187">**Rückgabewert**</span><span class="sxs-lookup"><span data-stu-id="2002a-187">**Return Value**</span></span>

<span data-ttu-id="2002a-188">Ein `Double`.</span><span class="sxs-lookup"><span data-stu-id="2002a-188">A `Double`.</span></span>

<span data-ttu-id="2002a-189">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="2002a-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="2002a-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2002a-190">See also</span></span>

<span data-ttu-id="2002a-191">Weitere Informationen zu den von SqlClient unterstützten Aggregatfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="2002a-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="2002a-192">**SQL Server 2005:** [Aggregatfunktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="2002a-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="2002a-193">**SQL Server 2008 und höher:** [Aggregatfunktionen (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2002a-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="2002a-194">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="2002a-194">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="2002a-195">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="2002a-195">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
