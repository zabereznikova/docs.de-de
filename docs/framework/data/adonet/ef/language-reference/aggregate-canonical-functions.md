---
title: Aggregieren kanonischer Funktionen
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: 3f4bb84c45e503fc0018e7869f3b41ddab4581a6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251355"
---
# <a name="aggregate-canonical-functions"></a>Aggregieren kanonischer Funktionen

Aggregate sind Ausdrücke, die eine Folge von Eingabewerten beispielsweise auf einen einzigen Wert reduzieren. Aggregate werden normalerweise zusammen mit der GROUP BY-Klausel des SELECT-Ausdrucks verwendet, und für ihre Verwendung gelten Einschränkungen.

## <a name="aggregate-entity-sql-canonical-functions"></a>Entity SQL kanonische Funktionen aggregieren

Im folgenden finden Sie die aggregierten Entity SQL kanonischen Funktionen.

### <a name="avgexpression"></a>Avg (Ausdruck)

Gibt den Durchschnitt der von NULL verschiedenen Werte zurück.

**Argumente**

`Int32`, ,`Int64` Und`Decimal`. `Double`

**Rückgabewert**

Der Typ von `expression`oder `null` , wenn alle Eingabewerte Werte `null` sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a>BigCount (Ausdruck)

Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.

**Argumente**

Beliebiger Typ.

**Rückgabewert**

Eine `Int64`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a>Count (Ausdruck)

Gibt die Größe des Aggregats, einschließlich null-Werte und doppelter Werte zurück.

**Argumente**

Beliebiger Typ.

**Rückgabewert**

Eine `Int32`.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a>Max (Ausdruck)

Gibt den Höchstwert der von null verschiedenen Werte zurück.

**Argumente**

`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .

**Rückgabewert**

Der Typ von `expression`oder `null` , wenn alle Eingabewerte Werte `null` sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a>Min (Ausdruck)

Gibt den geringsten Wert der von NULL verschiedenen Werte zurück.

**Argumente**

`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .

**Rückgabewert**

Der Typ von `expression`oder `null` , wenn alle Eingabewerte Werte `null` sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a>StDev (Ausdruck)

Gibt die Standardabweichung der von NULL verschiedenen Werte zurück.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double`. `Null`, wenn alle Eingabewerte `null`-Werte sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a>StDevP (Ausdruck)

Gibt die Standardabweichung zum Ausfüllen aller Werte zurück.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double` `null` oder `null` , wenn alle Eingabewerte Werte sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a>Sum (Ausdruck)

Gibt die Summe der von null verschiedenen Werte zurück.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double` `null` oder `null` , wenn alle Eingabewerte Werte sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a>Var (Ausdruck)

Gibt die Varianz aller Werte zurück, die keine Null-Werte sind.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double` `null` oder `null` , wenn alle Eingabewerte Werte sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a>VarP (Ausdruck)

Gibt die Varianz für die Auffüllung aller Werte zurück, die keine Null-Werte sind.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double` `null` oder `null` , wenn alle Eingabewerte Werte sind.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar. Weitere Informationen finden Sie unter [SqlClient für Entity Framework Funktionen](../sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Sammlungs basierte Aggregate

Auflistungsbasierte Aggregate (Auflistungsfunktionen) verarbeiten Auflistungen und geben einen Wert zurück. Wenn z. b. Orders eine Sammlung aller Bestellungen ist, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

Ausdrücke in auflistungsbasierten Aggregaten werden innerhalb des aktuellen umgebenden Namensauflösungsbereichs ausgewertet.

## <a name="group-based-aggregates"></a>Gruppenbasierte Aggregate

Gruppenbasierte Aggregate werden für eine Gruppe berechnet, die mit einer GROUP BY-Klausel definiert wurde. Für jede Gruppe im Ergebnis wird ein separates Aggregat berechnet, indem die Elemente in jeder Gruppe als Eingabe zur Aggregatberechnung verwendet werden. Wenn eine GROUP BY-Klausel in einem SELECT-Ausdruck verwendet wird, können sich in der Projektion oder ORDER BY-Klausel nur die Namen von Gruppierungsausdrücken, Aggregate oder konstante Ausdrücke befinden.

Im folgenden Beispiel wird die durchschnittlich bestellte Anzahl für jedes Produkt berechnet:

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

Es ist möglich, ein Gruppen basiertes Aggregat ohne eine explizite Group By-Klausel im SELECT-Ausdruck zu haben. In diesem Fall werden alle Elemente als eine einzelne Gruppe behandelt. Dies entspricht der Angabe einer Gruppierung auf der Grundlage einer Konstante. Betrachten Sie beispielsweise folgenden Ausdruck:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Dieser Ausdruck ist äquivalent zu Folgendem:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Ausdrücke in gruppenbasierten Aggregaten werden innerhalb des Namensauflösungsbereichs ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.

Wie bei Transact-SQL können auch Gruppenbasierte Aggregate einen all-oder einen eindeutigen Modifizierer angeben. Wenn der DISTINCT-Modifizierer angegeben ist, werden Duplikate vor der Berechnung des Aggregats aus der Aggregateingabeauflistung gelöscht. Wenn der ALL-Modifizierer oder kein Modifizierer angegeben wird, werden Duplikate nicht gelöscht.

## <a name="see-also"></a>Siehe auch

- [Canonical Functions (Kanonische Funktionen)](canonical-functions.md)
