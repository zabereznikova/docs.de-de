---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 55a10b82ffc189f5cf4118cb225a96963226256e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724186"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Aggregatfunktionen (SqlClient für Entity Framework)
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung. Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.  
  
 Im folgenden sind die SqlClient-Aggregatfunktionen.  

## <a name="avgexpression"></a>AVG(expression)

Gibt den Durchschnitt aller Werte in einer Auflistung zurück. NULL-Werte werden ignoriert.

**Argumente**

Ein `Int32`, `Int64`, `Double`, und `Decimal`.

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a>CHECKSUM_AGG(Collection)
 
 Gibt die Prüfsumme der Werte in einer Auflistung zurück. NULL-Werte werden ignoriert.
 
 **Argumente**
 
 Eine Auflistung (`Int32`).
 
 **Rückgabewert**
 
 Eine `Int32`.
 
 **Beispiel**
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a>Count(Ausdruck)

Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.

**Argumente**

Eine Auflistung\<T >, wobei T einer der folgenden Typen ist:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (nicht zurückgegeben in SQL Server 2000)|

**Rückgabewert**

Eine `Int32`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)
 
## <a name="countbigexpression"></a>COUNT_BIG(Ausdruck)
 
 Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.
 
 **Argumente**
 
 Eine Collection(T), wobei T einer der folgenden Typen ist:
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid` (nicht zurückgegeben in SQL Server 2000)|

**Rückgabewert**

Eine `Int64`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>Max(Expression)

Gibt den Maximalwert der Auflistung zurück.

**Argumente**

Eine Collection(T), wobei T einer der folgenden Typen ist: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN(expression)

Gibt den Minimalwert in einer Auflistung zurück.

**Argumente**

Eine Collection(T), wobei T einer der folgenden Typen ist: 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV(expression)

Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung (`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP(expression)

Gibt die statistische Standardabweichung für die Auffüllung für alle Werte des angegebenen Ausdrucks zurück.

**Argumente**

Eine Auflistung (`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUM(Expression)

Gibt die Summe aller Werte in der Auflistung zurück.

**Argumente**

Eine Collection(T), wobei T einer der folgenden Typen ist: `Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>Var(Ausdruck)

Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung (`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VarP(Ausdruck)

Gibt die statistische Varianz für die Auffüllung aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung (`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a>Siehe auch

Weitere Informationen zu den von SqlClient unterstützten Aggregatfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  

**SQL Server 2005**: [Aggregatfunktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))  
**SQLServer 2008 und höher**:  [Aggregatfunktionen (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)  
- [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Aggregieren kanonischer Funktionen](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
