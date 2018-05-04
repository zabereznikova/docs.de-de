---
title: Aggregatfunktionen (SqlClient für Entity Framework)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 558e9f8480dd69e2277603e9bb1013acfbc29467
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>Aggregatfunktionen (SqlClient für Entity Framework)
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Aggregatfunktionen zur Verfügung. Aggregatfunktionen führen Berechnungen für eine Reihe von Eingabewerten aus und geben einen einzelnen Wert zurück. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird.  
  
 In der folgenden Tabelle sind die SqlClient-Aggregatfunktionen aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`AVG(` `expression` `)`|Gibt den Durchschnitt aller Werte in einer Auflistung zurück.<br /><br /> NULL-Werte werden ignoriert.<br /><br /> **Argumente**<br /><br /> Ein `Int32`, `Int64`, `Double`, und `Decimal`.<br /><br /> **Rückgabewert**<br /><br /> Der `expression`-Typ.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]|  
|`CHECKSUM_AGG(` `collection` `)`|Gibt die Prüfsumme der Werte in einer Auflistung zurück.<br /><br /> NULL-Werte werden ignoriert.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (`Int32`).<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]|  
|`COUNT(` `expression` `)`|Gibt die Anzahl der Elemente in einer Auflistung als `Int32` zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (T), wobei T einer der folgenden Typen ist:<br /><br /> `Guid` (wird nicht in SQL Server 2000 zurückgegeben),<br /><br /> `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` oder `Binary`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]|  
|`COUNT_BIG(` `expression` `)`|Gibt die Anzahl der Elemente in einer Auflistung als `bigint` zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (T), wobei T einer der folgenden Typen ist:<br /><br /> `Guid` (wird nicht in SQL Server 2000 zurückgegeben), `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` oder `Binary`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int64`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]|  
|`MAX(` `expression` `)`|Gibt den Maximalwert der Auflistung zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (T), wobei T einer der folgenden Typen ist: `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.<br /><br /> **Rückgabewert**<br /><br /> Der `expression`-Typ.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]|  
|`MIN(` `expression` `)`|Gibt den Minimalwert in einer Auflistung zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (T), wobei T einer der folgenden Typen ist: `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`,<br /><br /> `Binary`<br /><br /> **Rückgabewert**<br /><br /> Der `expression`-Typ.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]|  
|`STDEV(` `expression` `)`|Gibt die statistische Standardabweichung aller Werte im angegebenen Ausdruck zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (`Double`).<br /><br /> **Rückgabewert**<br /><br /> Ein `Double`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]|  
|`STDEVP(` `expression` `)`|Gibt die statistische Standardabweichung für die Auffüllung für alle Werte des angegebenen Ausdrucks zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (`Double`).<br /><br /> **Rückgabewert**<br /><br /> Ein `Double`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]|  
|`SUM(` `expression` `)`|Gibt die Summe aller Werte in der Auflistung zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (T), wobei T einer der folgenden Typen ist: `Int32`, `Int64`, `Double`, `Decimal`.<br /><br /> **Rückgabewert**<br /><br /> Der `expression`-Typ.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]|  
|`VAR(` `expression` `)`|Gibt die statistische Varianz aller Werte im angegebenen Ausdruck zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (`Double`).<br /><br /> **Rückgabewert**<br /><br /> Ein `Double`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]|  
|`VARP(` `expression` `)`|Gibt die statistische Varianz für die Auffüllung aller Werte im angegebenen Ausdruck zurück.<br /><br /> **Argumente**<br /><br /> Eine Auflistung (`Double`).<br /><br /> **Rückgabewert**<br /><br /> Ein `Double`.<br /><br /> **Beispiel**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]|  
  
 Weitere Informationen zu den von SqlClient unterstützten Aggregatfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Aggregatfunktionen (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115906)|[Aggregatfunktionen (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkID=115903)|[Aggregatfunktionen (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115907)|  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Aggregieren kanonischer Funktionen](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
