---
title: Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: 3dd655e7acf924fa1bf0c09f0da82826e69482d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606818"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen
In diesem Thema wird beschrieben, wie kanonische Funktionen im konzeptionellen Modell den entsprechenden SQL Server-Funktionen zugeordnet werden.  
  
## <a name="date-and-time-functions"></a>Funktionen für Datum und Zeit  
 In der folgenden Tabelle wird das Mapping von Datums- und Uhrzeitfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[AddDays(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime(year, month, day, hour, minute, second)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Für SQL Server 2000 und SQL Server 2005 wird auf dem Server ein für `datetime` formatierter Wert erstellt. Für SQL Server 2008 und höhere Versionen wird ein `datetime2`-Wert auf dem Server erstellt.|  
|[CreateDateTimeOffset(year, month, day, hour, minute, second, tzoffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Ein für `datetimeoffset` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CreateTime(hour, minute, second)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Ein für `time` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` in SQLServer 2008.<br /><br /> `GetDate()` in SQLServer 2000 und SQLServer 2005.|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` in SQL Server 2008.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` in SQLServer 2008. `GetUtcDate()` in SQL Server 2000 und SQL Server 2005.|  
|[DayOfYear(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears(startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Für SQL Server 2000 und SQL Server 2005 wird ein abgeschnittener `datetime` formatierter Wert auf dem Server erstellt. Für SQL Server 2008 und höheren Versionen wird ein abgeschnittener `datetime2` oder `datetimeoffset` Wert wird auf dem Server erstellt.|  
|[Year(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen  
 In der folgenden Tabelle wird das Mapping von Aggregatfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Avg(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[SUM(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Mathematische Funktionen  
 In der folgenden Tabelle wird das Mapping von mathematischen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Abs(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Truncate](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>String-Funktionen  
 In der folgenden Tabelle wird die Zuordnung von String-Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Contains(string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat(string1, string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith(string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Beachten Sie** der `CHARINDEX` -Funktion zurückgegeben `false` Wenn die `string` befindet sich in einer Zeichenfolgenspalte mit fester Länge und `target` ist eine Konstante. In diesem Fall wird die ganze Zeichenfolge gesucht, einschließlich aller Auffüllleerzeichen. Eine mögliche Problemumgehung ist, die Daten in der Zeichenfolge mit fester Länge vor dem Übergeben der Zeichenfolge an die `EndsWith`-Funktion abzuschneiden, wie in folgendem Beispiel gezeigt wird: `EndsWith(TRIM(string), target)`|  
|[IndexOf(target, string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, Länge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Länge (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, Länge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Ersetzen Sie (string1, string2, string3)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith(string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring(string, start, length)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Bitweise Funktionen  
 In der folgenden Tabelle wird die Zuordnung von bitweisen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[BitWiseAnd (Wert1, Wert2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 und value2|  
|[BitWiseNot (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 &#124; value2|  
|[BitWiseXor (Wert1, Wert2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
