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
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Aggregatfunktionen (SqlClient für Entity Framework)
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung. Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.  
  
 Im Folgenden sind die SqlClient-Aggregatfunktionen zu finden.  

## <a name="avgexpression"></a>AVG(Ausdruck)

Gibt den Durchschnitt aller Werte in einer Auflistung zurück. NULL-Werte werden ignoriert.

**Argumente**

An `Int32` `Int64`, `Double`, `Decimal`und .

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a>CHECKSUM_AGG(Sammlung)

 Gibt die Prüfsumme der Werte in einer Auflistung zurück. NULL-Werte werden ignoriert.

 **Argumente**

 Eine Auflistung(`Int32`).

 **Rückgabewert**

 Ein `Int32`-Element.

 **Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a>COUNT(Ausdruck)

Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.

**Argumente**

Eine\<Auflistung T>, wobei T einer der folgenden Typen ist:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(nicht in SQL Server 2000 zurückgegeben)|

**Rückgabewert**

Ein `Int32`-Element.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a>COUNT_BIG(Ausdruck)

Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.

 **Argumente**

 Eine Auflistung(T), wobei T einer der folgenden Typen ist:

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|`Guid`(nicht in SQL Server 2000 zurückgegeben)|

**Rückgabewert**

Ein `Int64`-Element.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a>MAX(Ausdruck)

Gibt den Maximalwert der Auflistung zurück.

**Argumente**

Eine Auflistung(T), wobei T einer der folgenden Typen ist:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a>MIN(Ausdruck)

Gibt den Minimalwert in einer Auflistung zurück.

**Argumente**

Eine Auflistung(T), wobei T einer der folgenden Typen ist:

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a>STDEV(Ausdruck)

Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung(`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a>STDEVP(Ausdruck)

Gibt die statistische Standardabweichung für die Grundgesamtheit (Population) aller Werte des angegebenen Ausdrucks zurück.

**Argumente**

Eine Auflistung(`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a>SUMME(Ausdruck)

Gibt die Summe aller Werte in der Auflistung zurück.

**Argumente**

Eine Auflistung(T), bei der T einer `Int32` `Int64`der `Double` `Decimal`folgenden Typen ist: , , , .

**Rückgabewert**

Der `expression`-Typ.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a>VAR(Ausdruck)

Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung(`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a>VARP(Ausdruck)

Gibt die statistische Varianz für die Grundgesamtheit aller Werte im angegebenen Ausdruck zurück.

**Argumente**

Eine Auflistung(`Double`).

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a>Weitere Informationen

- [Aggregatfunktionen (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [Entity SQL-Sprache](./language-reference/entity-sql-language.md)
- [Aggregieren kanonischer Funktionen](./language-reference/aggregate-canonical-functions.md)
