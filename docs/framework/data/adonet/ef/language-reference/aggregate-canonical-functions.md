---
title: Aggregieren kanonischer Funktionen
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e4772176130fc72a22645462921c90dd5b7967b2
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754642"
---
# <a name="aggregate-canonical-functions"></a>Aggregieren kanonischer Funktionen

Aggregate sind Ausdrücke, die eine Folge von Eingabewerten beispielsweise auf einen einzigen Wert reduzieren. Aggregate werden normalerweise zusammen mit der GROUP BY-Klausel des SELECT-Ausdrucks verwendet, und für ihre Verwendung gelten Einschränkungen.

## <a name="aggegate-entity-sql-canonical-functions"></a>Kanonische Funktionen Aggegate Entity SQL

Im folgenden werden die kanonischen Entity SQL-Aggregatfunktionen.

### <a name="avgexpression"></a>Avg (Ausdruck)

Gibt den Durchschnitt der von NULL verschiedenen Werte zurück.

**Argumente**

Ein `Int32`, `Int64`, `Double`, und `Decimal`.

**Rückgabewert**

Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.

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

Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a>Min (Ausdruck)

Gibt den geringsten Wert der von NULL verschiedenen Werte zurück.

**Argumente**

`Int16``Byte`    `Int64`, `Int32``Single`, `Byte``Decimal`, `Double``DateTimeOffset`, `DateTime``String`, `Time`, `Binary`, , , , , , .

**Rückgabewert**

Der Typ des `expression`, oder `null` Wenn alle Eingabewerte `null` Werte.

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

Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a>Sum (Ausdruck)

Gibt die Summe der von null verschiedenen Werte zurück.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a>Var (Ausdruck)

Gibt die Varianz aller Werte zurück, die keine Null-Werte sind.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a>VarP (Ausdruck)

Gibt die Varianz für die Auffüllung aller Werte zurück, die keine Null-Werte sind.

**Argumente**

`Int32`, `Int64`, `Double`, `Decimal`.

**Rückgabewert**

Ein `Double`, oder `null` Wenn alle Eingabewerte `null` Werte.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] 

Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar. Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).

## <a name="collection-based-aggregates"></a>Auflistungsbasierte Aggregate

Auflistungsbasierte Aggregate (Auflistungsfunktionen) verarbeiten Auflistungen und geben einen Wert zurück. Zum Beispiel wenn ORDERS ist eine Auflistung aller Bestellungen, können Sie das früheste Lieferdatum mit dem folgenden Ausdruck berechnen:

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

Es ist möglich, eine Gruppenbasierte Aggregate ohne explizite Group by-Klausel im SELECT-Ausdruck haben. In diesem Fall werden alle Elemente als eine einzelne Gruppe behandelt. Dies entspricht der Angabe einer Gruppe auf Grundlage einer Konstante. Betrachten Sie beispielsweise folgenden Ausdruck:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

Dieser Ausdruck ist äquivalent zu Folgendem:

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

Ausdrücke in gruppenbasierten Aggregaten werden innerhalb des Namensauflösungsbereichs ausgewertet, der für den WHERE-Klauselausdruck sichtbar wäre.

Wie in [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], Gruppenbasierte Aggregate können auch angeben, alles oder DISTINCT-Modifizierer. Wenn der DISTINCT-Modifizierer angegeben ist, werden Duplikate vor der Berechnung des Aggregats aus der Aggregateingabeauflistung gelöscht. Wenn der ALL-Modifizierer oder kein Modifizierer angegeben wird, werden Duplikate nicht gelöscht.  

## <a name="see-also"></a>Siehe auch

[Canonical Functions (Kanonische Funktionen)](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
