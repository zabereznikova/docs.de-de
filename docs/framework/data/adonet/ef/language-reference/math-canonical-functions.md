---
title: Kanonische Mathematikfunktionen
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9417ff9836912017c9d88bb24a18849aaac2836a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250305"
---
# <a name="math-canonical-functions"></a>Kanonische Mathematikfunktionen

Entity SQL umfasst die folgenden kanonischen mathematischen Funktionen:
  
## <a name="absvalue"></a>Abs(Wert)

Gibt den Absolutwert von `value` zurück.

**Argumente**

`Int16` ,`Int64`,,, ,`Double`Und. `Byte` `Int32` `Single` `Decimal`

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

`Abs(-2)`

## <a name="ceilingvalue"></a>Ceiling (Wert)

Gibt die kleinste ganze Zahl zurück, die nicht kleiner als `value` ist.

**Argumente**

`Single` ,`Double`Und .`Decimal`

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a>Floor (Wert)

Gibt die größte ganze Zahl zurück, die nicht größer als `value` ist.

**Argumente**

`Single` ,`Double`Und .`Decimal`

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a>Power(Wert, Exponent)

Gibt das Ergebnis der angegebenen `value` an die angegebene `exponent` zurück.

**Argumente**

|  |  |
|--|--|
|`value` | Ein `Int32, Int64, Double` oder`Decimal`ein. |
|`exponent` | `Int64` ,`Double`Oder .`Decimal` |

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

`Power(748.58,2)`

## <a name="roundvalue"></a>Round (Wert)

Gibt `value` gerundet zur nächsten Ganzzahl zurück.

**Argumente**

`Single` ,`Double`Und .`Decimal`

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

`Round(748.58)`

## <a name="roundvalue-digits"></a>Round(Wert, Ziffern)

Gibt den `value` auf die nächstliegenden angegebenen `digits` gerundet zurück.

**Argumente**

|  |  |
|--|--|
|`value`|`Double` oder `Decimal`.|
|`digits`|`Int16` oder `Int32`.|

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a>Truncate(Wert, Ziffern)

Gibt den `value` auf die nächstliegenden angegebenen `digits` gekürzt zurück.

**Argumente**

|  |  |
|--|--|
|`value`|`Double` oder `Decimal`.|
|`digits`|`Int16` oder `Int32`.|

**Rückgabewert**

Der `value`-Typ.

**Beispiel**

`Truncate(748.58,1)`  
  
 Diese Funktionen geben `null` zurück, wenn die Eingabe `null` ist.  
  
 Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar. Weitere Informationen finden Sie unter [SqlClient für Entity Framework Funktionen](../sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Canonical Functions (Kanonische Funktionen)](canonical-functions.md)
