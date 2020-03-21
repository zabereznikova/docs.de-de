---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149764"
---
# <a name="mathematical-functions"></a>Mathematische Funktionen

Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird. In der folgenden Tabelle werden die mathematischen SqlClient-Funktionen beschrieben.  
  
## <a name="absexpression"></a>ABS(Ausdruck)

Führt die Absolutwertfunktion aus.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

Der Absolutwert des angegebenen Ausdrucks.

**Beispiel**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(Ausdruck)

Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(Ausdruck)

Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>ATAN(Ausdruck)

Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(Ausdruck, Ausdruck)

Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a>CEILING(Ausdruck)

Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

An `Int32` `Int64`, `Double`, `Decimal`oder .

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(Ausdruck)

Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(Ausdruck)

Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES(Radians)

Gibt den entsprechenden Winkel in Grad zurück.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

An `Int32` `Int64`, `Double`, `Decimal`oder .

**Beispiel**

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(Ausdruck)

Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**`SqlServer.EXP(1)`

## <a name="floorexpression"></a>FLOOR(Ausdruck)

Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>LOG(Ausdruck)

Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(Ausdruck)

Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI()

Gibt den konstanten Wert von Pi als `Double`-Typ zurück.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a>POWER(numeric_expression, power_expression)

Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.

**Argumente**

|  |  |
|--|--|
|`numeric_expression`| An `Int32` `Int64`, `Double`, `Decimal`oder .|
|`power_expression`| A, `Double` die die Macht darstellt, auf die die erhöht werden `numeric_expression`kann.|

**Rückgabewert**

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.

**Beispiel**

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(Ausdruck)

Konvertiert Grade in Bogenmaße.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

An `Int32` `Int64`, `Double`, `Decimal`oder .

**Beispiel**

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>RAND([Seed])

Gibt einen Zufallswert zwischen 0 und 1 zurück.

**Argumente**

Der Ausgangswert `Int32`als . Ist der seed-Wert nicht angegeben, fügt die Datenbank-Engine von SQL Server einen Zufallsstartwert hinzu. Für einen bestimmten Ausgangswert ist das zurückgegebene Ergebnis immer gleich.

**Rückgabewert**

Ein zufälliger `Double`-Wert zwischen 0 (null) und 1.

**Beispiel**

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a>ROUND(numeric_expression, Länge[,Funktion])

Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde.

**Argumente**

|  |  |
|--|--|
|`numeric_expression`| An `Int32` `Int64`, `Double`, `Decimal`oder .
|`length`| Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll. Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet. Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.|
|`function` | Optional. Ein, `Int32` der den auszuführenden Vorgangstyp darstellt. Wenn die Funktion weggelassen wird oder `numeric_expression` den Wert 0 (Standard) hat, wird gerundet. Wenn ein anderer Wert als `numeric_expression` 0 angegeben ist, wird abgeschnitten. |

**Rückgabewert**

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.

**Beispiel**

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>SIGN(Ausdruck)

Gibt das Vorzeichen des angegebenen Ausdrucks zurück: positiv (+1), Null (0) oder negativ (-1).

**Argumente**

`expression`: `Int32`, `Int64`, `Double` oder `Decimal`

**Rückgabewert**

An `Int32` `Int64`, `Double`, `Decimal`oder .

**Beispiel**

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(Ausdruck)

Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**`SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>SQRT(Ausdruck)

Gibt die Quadratwurzel des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**`SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>SQUARE(Ausdruck)

Gibt den quadratischen Wert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: Ein `Double`-Wert.

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(Ausdruck)

Berechnet den Tangens eines angegebenen Ausdrucks.

**Argumente**

`expression`: `Double`

**Rückgabewert**

`Double`

**Beispiel**

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Weitere Informationen

- [Mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [SqlClient für Entity Framework-Funktionen](sqlclient-for-ef-functions.md)
