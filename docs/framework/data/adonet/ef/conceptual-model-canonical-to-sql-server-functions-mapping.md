---
title: Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: 495a662cbab84c2686e4c31945c30d6f82d117cb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153117"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen

In diesem Thema wird beschrieben, wie kanonische Funktionen im konzeptionellen Modell den entsprechenden SQL Server-Funktionen zugeordnet werden.  
  
## <a name="date-and-time-functions"></a>Datums- und Uhrzeitfunktionen  

 In der folgenden Tabelle wird das Mapping von Datums- und Uhrzeitfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[AddDays (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (Jahr, Monat, Tag, Stunde, Minute, Sekunde)](./language-reference/date-and-time-canonical-functions.md)|Für SQL Server 2000 und SQL Server 2005 wird auf dem Server ein für `datetime` formatierter Wert erstellt. Für SQL Server 2008 und höhere Versionen wird ein `datetime2`-Wert auf dem Server erstellt.|  
|[CreateDateTimeOffset (Jahr, Monat, Tag, Stunde, Minute, Sekunde, tzoffset)](./language-reference/date-and-time-canonical-functions.md)|Ein für `datetimeoffset` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CreateTime (Stunde, Minute, Sekunde)](./language-reference/date-and-time-canonical-functions.md)|Ein für `time` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentDateTime ()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` in SQLServer 2008.<br /><br /> `GetDate()` in SQLServer 2000 und SQLServer 2005.|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` in SQL Server 2008.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentUtcDateTime()](./language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` in SQLServer 2008. `GetUtcDate()` in SQL Server 2000 und SQL Server 2005.|  
|[DayOfYear (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes (DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|Bei SQL Server 2000 und SQL Server 2005 wird ein abgeschnittener `datetime` formatierter Wert auf dem Server erstellt. Bei SQL Server 2008 und höheren Versionen wird ein abgeschnittener- `datetime2` oder- `datetimeoffset` Wert auf dem Server erstellt.|  
|[Year (Ausdruck)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen  

 In der folgenden Tabelle wird das Mapping von Aggregatfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Avg (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP (Ausdruck)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Mathematische Funktionen  

 In der folgenden Tabelle wird das Mapping von mathematischen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Abs(Wert)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling (Wert)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor (Wert)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power (Wert)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round (Wert)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[TRUNCATE](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Zeichenfolgenfunktionen  

 In der folgenden Tabelle wird die Zuordnung von String-Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Contains (Zeichenfolge, Ziel)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (string1, string2)](./language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith (Zeichenfolge, Ziel)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Hinweis** Die `CHARINDEX` -Funktion gibt zurück, `false` Wenn der `string` in einer Zeichen folgen Spalte mit fester Länge gespeichert wird und `target` eine Konstante ist. In diesem Fall wird die ganze Zeichenfolge gesucht, einschließlich aller Auffüllleerzeichen. Eine mögliche Problemumgehung ist, die Daten in der Zeichenfolge mit fester Länge vor dem Übergeben der Zeichenfolge an die `EndsWith`-Funktion abzuschneiden, wie in folgendem Beispiel gezeigt wird: `EndsWith(TRIM(string), target)`|  
|[IndexOf (Ziel, string2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, Länge)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, Länge)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Ersetzen (string1, string2, string3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith (Zeichenfolge, Ziel)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (Zeichenfolge, Beginn, Länge)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper (Zeichenfolge)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Bitweise Funktionen  

 In der folgenden Tabelle wird die Zuordnung von bitweisen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 & Value2|  
|[BitWiseNot (Wert)](./language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 &#124; Value2|  
|[BitWiseXor (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
