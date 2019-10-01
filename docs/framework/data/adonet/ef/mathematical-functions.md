---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 664d1a4f67ecced6713f83bf3dd11931c9b4dc18
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700005"
---
# <a name="mathematical-functions"></a>Mathematische Funktionen

Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird. In der folgenden Tabelle werden die mathematischen Funktionen von SqlClient beschrieben.  
  
## <a name="absexpression"></a>Abs (Ausdruck)

Führt die Absolutwertfunktion aus.

**Argumente**

`expression`: `Int32`, ,`Int64` Oder`Decimal`. `Double`

**Rückgabewert**

Der Absolutwert des angegebenen Ausdrucks.

**Beispiel**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>Acos (Ausdruck)

Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: EIN `Double`.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN (Ausdruck)

Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: EIN `Double`.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>Atan (Ausdruck)

Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.

**Argumente**

`expression`: EIN `Double`.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2 (Ausdruck, Ausdruck)

Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.

**Argumente**

`expression`: EIN `Double`.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>Ceiling (Ausdruck)

Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.

**Argumente**

`expression`: `Int32`, ,`Int64` Oder`Decimal`. `Double`

**Rückgabewert**

`Int32`, ,`Int64` Oder`Decimal`. `Double`

**Beispiel** 

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS (Ausdruck)

Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>Cot (Ausdruck)

Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>Grad (Bogenmaß)

Gibt den entsprechenden Winkel in Grad zurück. 

**Argumente** 

`expression`: `Int32`, ,`Int64` Oder`Decimal`. `Double` 

**Rückgabewert** 

`Int32`, ,`Int64` Oder`Decimal`. `Double` 

**Beispiel** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>Exp (Ausdruck)

Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel**`SqlServer.EXP(1)`

## <a name="floorexpression"></a>Floor (Ausdruck)

Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>Log (Ausdruck)

Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>Log10 (Ausdruck)

Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI ()

Gibt den konstanten Wert von Pi als `Double`-Typ zurück. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a>Power (numeric_expression, power_expression)

Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.

**Argumente** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, ,`Int64` Oder`Decimal`. `Double`|
|`power_expression`| Ein `Double` -Wert, der die Potenz darstellt, in `numeric_expression`die der erhoben werden soll.| 

**Rückgabewert** 

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`. 

**Beispiel** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>Radiane (Ausdruck)

Konvertiert Grad- in Radiantwerte. 

**Argumente** 

`expression`: `Int32`, ,`Int64` Oder`Decimal`. `Double` 

**Rückgabewert** 

`Int32`, ,`Int64` Oder`Decimal`. `Double` 

**Beispiel** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>Rand ([Seed])

Gibt einen Zufallswert zwischen 0 und 1 zurück. 

**Argumente** 

Der Ausgangswert als `Int32`. Ist der seed-Wert nicht angegeben, fügt die Datenbank-Engine von SQL Server einen Zufallsstartwert hinzu. Für einen angegebenen Startwert wird immer dasselbe Ergebnis zurückgegeben.

**Rückgabewert** 

Ein zufälliger `Double`-Wert zwischen 0 (null) und 1. 

**Beispiel** 

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>Round (numeric_expression, length [, Function])

Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde. 

**Argumente** 

|  |  |
|--|--|
|`numeric_expression`| `Int32`, ,`Int64` Oder`Decimal`. `Double` 
|`length`| Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll. Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet. Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.|
|`function` | Optional. Ein `Int32` , der den Typ des auszuführenden Vorgangs darstellt. Wenn function ausgelassen wird oder den Wert 0 (Standard) hat, `numeric_expression` wird gerundet. Wenn ein anderer Wert als 0 angegeben wird, `numeric_expression` wird abgeschnitten. |

**Rückgabewert** 

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.

**Beispiel** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>Sign (Ausdruck) 

Gibt das positive (+1) oder negative Vorzeichen (-1) oder das Vorzeichen 0 (null) des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: `Int32`, `Int64`, `Double` oder `Decimal` 

**Rückgabewert** 

`Int32`, ,`Int64` Oder`Decimal`. `Double` 

**Beispiel** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>Sin (Ausdruck)

Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel**`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT (Ausdruck)

Gibt die Quadratwurzel des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel**`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>Square (Ausdruck)

Gibt den quadratischen Wert des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: EIN `Double`. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>Tan (Ausdruck)

Berechnet den Tangens eines angegebenen Ausdrucks.

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

`Double` 

**Beispiel** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Siehe auch

- [Mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [SqlClient für Entity Framework-Funktionen](sqlclient-for-ef-functions.md)
