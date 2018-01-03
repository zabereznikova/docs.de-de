---
title: Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ad42c31353851f0846a484f7ab8bcb83c71d0e0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen
In diesem Thema wird beschrieben, wie kanonische Funktionen im konzeptionellen Modell den entsprechenden SQL Server-Funktionen zugeordnet werden.  
  
## <a name="date-and-time-functions"></a>Funktionen für Datum und Zeit  
 In der folgenden Tabelle wird das Mapping von Datums- und Uhrzeitfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[AddDays (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[Addmicroseconds (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[Addnanoseconds (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (Jahr, Monat, Tag, Stunde, Minute, Sekunde)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Für SQL Server 2000 und SQL Server 2005 wird auf dem Server ein für `datetime` formatierter Wert erstellt. Für SQL Server 2008 und höhere Versionen wird ein `datetime2`-Wert auf dem Server erstellt.|  
|[CreateDateTimeOffset (Jahr, Monat, Tag, Stunde, Minute, Sekunde, Tzoffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Ein für `datetimeoffset` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CreateTime (Stunde, Minute, Sekunde)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Ein für `time` formatierter Wert wird auf dem Server erstellt.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` in SQLServer 2008.<br /><br /> `GetDate()` in SQLServer 2000 und SQLServer 2005.|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` in SQL Server 2008.<br /><br /> Wird unter SQL Server 2000 und SQL Server 2005 nicht unterstützt.|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` in SQLServer 2008. `GetUtcDate()` in SQL Server 2000 und SQL Server 2005.|  
|[DayOfYear (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (StartExpression, EndExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes (DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[HOUR (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[TRUNCATE (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|Für SQL Server 2000 und SQL Server 2005, eine abgeschnittene `datetime` formatierter Wert wird auf dem Server erstellt. Für SQL Server 2008 und höhere Versionen, eine abgeschnittene `datetime2` oder `datetimeoffset` Wert wird auf dem Server erstellt.|  
|[Year (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen  
 In der folgenden Tabelle wird das Mapping von Aggregatfunktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[AVG (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[SUM (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP (Ausdruck)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Mathematische Funktionen  
 In der folgenden Tabelle wird das Mapping von mathematischen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Abs(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[CEILING (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Abschneiden](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>String-Funktionen  
 In der folgenden Tabelle wird die Zuordnung von String-Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[Contains(String, Target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (string1, string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith (Zeichenfolge, Ziel)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Hinweis** der `CHARINDEX` -Funktion zurückgegeben `false` Wenn die `string` befindet sich in einer Zeichenfolgenspalte mit fester Länge und `target` ist eine Konstante. In diesem Fall wird die ganze Zeichenfolge gesucht, einschließlich aller Auffüllleerzeichen. Eine mögliche Problemumgehung ist, die Daten in der Zeichenfolge mit fester Länge vor dem Übergeben der Zeichenfolge an die `EndsWith`-Funktion abzuschneiden, wie in folgendem Beispiel gezeigt wird: `EndsWith(TRIM(string), target)`|  
|[IndexOf (Ziel, string2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, Länge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Länge (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, Länge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Ersetzen Sie (string1, string2, string3)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|["StartsWith" (Zeichenfolge, Ziel)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (Zeichenfolge, Beginn, Länge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper (Zeichenfolge)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Bitweise Funktionen  
 In der folgenden Tabelle wird die Zuordnung von bitweisen Funktionen beschrieben:  
  
|Kanonische Funktionen|SQL Server-Funktionen|  
|-------------------------|--------------------------|  
|[BitWiseAnd (Wert1, Wert2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot (Wert)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (Wert1, Wert2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Wert1 &#124; Wert2|  
|[Binäre BitWiseXor (Wert1, Wert2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
