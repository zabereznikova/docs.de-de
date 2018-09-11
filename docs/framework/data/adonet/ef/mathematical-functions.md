---
title: Mathematische Funktionen
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: e6c58d781d7138f8295f2d0a2f0db110ad4b1dd6
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44268973"
---
# <a name="mathematical-functions"></a>Mathematische Funktionen

Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt mathematische Funktionen bereit, die Berechnungen für als Argumente bereitgestellte Eingabewerte durchführen und einen numerischen Wert als Ergebnis zurückgeben. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Mit der Namespace-Eigenschaft eines Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für bestimmte Konstrukte verwendet wird, z. B. Typen und Funktionen. In der folgenden Tabelle werden die mathematischen Funktionen von SqlClient beschrieben.  
  
## <a name="absexpression"></a>Abs(Expression)

Führt die Absolutwertfunktion aus.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

Der Absolutwert des angegebenen Ausdrucks.

**Beispiel**

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a>ACOS(Expression)

Gibt den Arkuskosinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: `Double`

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a>ASIN(Expression)

Gibt den Arkussinuswert des angegebenen Ausdrucks zurück.

**Argumente**

`expression`: `Double`

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a>Atan(Expression)

Gibt den Arkustangens-Wert des angegebenen numerischen Ausdrucks zurück.

**Argumente**

`expression`: `Double`

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a>ATN2(Expression, Expression)

Gibt den Winkel im Bogenmaß (Radiant) zurück, dessen Tangens zwischen den beiden angegebenen numerischen Ausdrücken liegt.

**Argumente**

`expression`: `Double`

**Rückgabewert**

Ein `Double`.

**Beispiel**

`SqlServer.ATN2(9, 8)`
 
## <a name="ceilingexpression"></a>CEILING(Expression)

Konvertiert den angegebenen Ausdruck zur kleinsten Ganzzahl, die größer als oder gleich dem Ausdruck ist.

**Argumente**

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`.

**Rückgabewert**

Ein `Int32`, `Int64`, `Double`, oder `Decimal`.

**Beispiel** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a>COS(Expression)

Berechnet den trigonometrischen Kosinus des im Bogenmaß angegebenen Winkels. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.COS(45)`

## <a name="cotexpression"></a>COT(Expression)

Berechnet den trigonometrischen Kotangens des im Bogenmaß angegebenen Winkels. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a>DEGREES(RADIANS)

Gibt den entsprechenden Winkel in Grad zurück. 

**Argumente** 

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`. 

**Rückgabewert** 

Ein `Int32`, `Int64`, `Double`, oder `Decimal`. 

**Beispiel** 

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a>EXP(Expression)

Berechnet den Exponentialwert des angegebenen numerischen Ausdrucks. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** `SqlServer.EXP(1)`

## <a name="floorexpression"></a>Floor(Expression)

Konvertiert den angegebenen Ausdruck zur größten Ganzzahl, die kleiner als oder gleich dem angegebenen numerischen Ausdruck ist. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

[!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)] 
[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a>Log(Expression)

Berechnet den natürlichen Logarithmus des angegebenen `float`-Ausdrucks. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.LOG(100)`

## <a name="log10expression"></a>LOG10(Expression)

Gibt den Logarithmus zur Basis 10 des angegebenen `Double`-Ausdrucks zurück. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.LOG10(100)`

## <a name="pi"></a>PI)

Gibt den konstanten Wert von Pi als `Double`-Typ zurück. 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.PI()`

## <a name="powernumericexpression-powerexpression"></a>POWER (Numeric_expression, Power_expression)

Berechnet den Wert eines angegebenen Ausdrucks in einer angegebenen Potenz.

**Argumente** 

|  |  |
|--|--|
|`numeric_expression`| Ein `Int32`, `Int64`, `Double`, oder `Decimal`.|
|`power_expression`| Ein `Double` , das darstellt, der Möglichkeit, die zum Auslösen der `numeric_expression`.| 

**Rückgabewert** 

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`. 

**Beispiel** 

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a>RADIANS(Expression)

Konvertiert Grad- in Radiantwerte. 

**Argumente** 

`expression`: `Int32`,`Int64`, `Double` oder `Decimal`. 

**Rückgabewert** 

Ein `Int32`, `Int64`, `Double`, oder `Decimal`. 

**Beispiel** 

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a>Rand([SEED])

Gibt einen Zufallswert zwischen 0 und 1 zurück. 

**Argumente** 

Der Startwert als ein `Int32`. Ist der seed-Wert nicht angegeben, fügt das Datenbankmodul von SQL Server einen Zufallsstartwert hinzu. Für einen angegebenen Startwert wird immer dasselbe Ergebnis zurückgegeben.

**Rückgabewert** 

Ein zufälliger `Double`-Wert zwischen 0 (null) und 1. 

**Beispiel** 

`SqlServer.RAND()`
  
## <a name="roundnumericexpression-lengthfunction"></a>Round(numeric_expression, Length[,Function])

Gibt einen numerischen Ausdruck zurück, der auf die angegebene Länge oder Genauigkeit gerundet wurde. 

**Argumente** 

|  |  |
|--|--|
|`numeric_expression`| Ein `Int32`, `Int64`, `Double`, oder `Decimal`. 
|`length`| Ein `Int32`, das die Genauigkeit angibt, auf die `numeric_expression` gerundet werden soll. Wenn `length` eine positive Zahl ist, wird `numeric_expression` auf die Anzahl der mit `length` angegebenen Dezimalstellen gerundet. Wenn `length` eine negative Zahl ist, wird `numeric_expression` auf der linken Seite des Dezimaltrennzeichens gemäß der Angabe von `length` gerundet.|
|`function` | Dies ist optional. Ein `Int32` , das den Typ des auszuführenden Vorgangs darstellt. Wenn die Funktion ausgelassen oder weist einen Wert von 0 (Standard), `numeric_expression` wird gerundet. Wenn ein anderer Wert als 0 angegeben ist, `numeric_expression` wird abgeschnitten. |

**Rückgabewert** 

Der Wert des angegebenen `numeric_expression` zur angegebenen `power_expression`.

**Beispiel** 

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a>Sign(Expression) 

Gibt das positive (+1) oder negative Vorzeichen (-1) oder das Vorzeichen 0 (null) des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: `Int32`, `Int64`, `Double` oder `Decimal` 

**Rückgabewert** 

Ein `Int32`, `Int64`, `Double`, oder `Decimal`. 

**Beispiel** 

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a>SIN(Expression)

Berechnet den trigonometrischen Sinus des angegebenen Winkels im Bogenmaß, und gibt einen `Double`-Ausdruck zurück. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** `SqlServer.SIN(20)`

## <a name="sqrtexpression"></a>Sqrt(Expression)

Gibt die Quadratwurzel des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** `SqlServer.SQRT(3600)`

## <a name="squareexpression"></a>Square(Expression)

Gibt den quadratischen Wert des angegebenen Ausdrucks zurück. 

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

Ein `Double`. 

**Beispiel** 

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a>TAN(Expression)

Berechnet den Tangens eines angegebenen Ausdrucks.

**Argumente** 

`expression`: `Double` 

**Rückgabewert** 

`Double` 

**Beispiel** 

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a>Siehe auch

Weitere Informationen zu den von SqlClient unterstützten mathematischen Funktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  
  
**SQLServer 2005:** [mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms177516(v=sql.90))  
**SQLServer 2008:** [mathematische Funktionen (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms177516(v=sql.100))  
**SQLServer 2012 und höher:** [mathematische Funktionen (Transact-SQL)](/sql/t-sql/functions/mathematical-functions-transact-sql?view=sql-server-2017)   

 [SqlClient für Entity Framework-Funktionen](sqlclient-for-ef-functions.md)
