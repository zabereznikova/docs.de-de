---
title: Zuordnen von CLR-Methoden zu kanonischen Funktionen
ms.date: 03/30/2017
ms.assetid: e3363261-2cb8-4b54-9555-2870be99b929
ms.openlocfilehash: 16d447e82959f5ade7210b36dcf9d06bed9c9b00
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378752"
---
# <a name="clr-method-to-canonical-function-mapping"></a>Zuordnen von CLR-Methoden zu kanonischen Funktionen

Das Entity Framework stellt einen Satz kanonischer Funktionen bereit, die eine auf vielen Datenbanksystemen verbreitete Funktionalität implementieren, z. B. Zeichenfolgenbearbeitung und mathematische Funktionen. Dadurch können Entwickler für einen großen Bereich von Datenbanksystemen entwickeln. Beim Aufrufen aus einer Abfragetechnologie wie LINQ to Entities werden diese kanonischen Funktionen in die entsprechenden Speicherfunktionen des verwendeten Anbieters übersetzt. Dadurch können Funktionsaufrufe für verschiedene Datenquellen in einer allgemeinen Form ausgedrückt werden, und es werden konsistente datenquellenübergreifende Abfragemöglichkeiten bereitgestellt. Weiterhin werden die bitweisen Operatoren AND, OR, NOT und XOR kanonischen Funktionen zugeordnet, wenn der Operand ein numerischer Typ ist. Bei booleschen Operanden werden durch die bitweisen Operatoren AND, OR, NOT und XOR die logischen Operationen AND, OR, NOT und XOR ihrer Operanden berechnet. Weitere Informationen finden Sie unter [kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).

In LINQ-Szenarios müssen bei Abfragen für das Entity Framework bestimmte CLR-Methoden den Methoden für die zugrunde liegende Datenquelle mithilfe kanonischer Funktionen zugeordnet werden. Bei allen Methodenaufrufen in einer LINQ to Entities-Abfrage, die nicht explizit einer kanonischen Funktion zugeordnet sind, wird eine <xref:System.NotSupportedException>-Laufzeitausnahme ausgelöst.

## <a name="systemstring-method-static-mapping"></a>Mapping der System.String-Methode (statisch)

|System.String-Methode (statisch)|Kanonische Funktion|
|-------------------------------------|------------------------|
|System.String Concat (String `str0`, String `str1`)|Concat(`str0`, `str1`)|
|System.String Concat(String `str0`, String `str1`, String `str2`)|Concat(Concat(`str0`, `str1`), `str2`)|
|System.String Concat(String `str0`, String `str1`, String `str2`, String `str03`)|Concat(Concat(Concat(`str0`, `str1`), `str2`), `str3`)|
|Boolean Equals(String `a`, String `b`)|=-Operator|
|Boolean IsNullOrEmpty(String `value`)|(IsNull(`value`)) OR Length(`value`) = 0|
|Boolean op_Equality(String `a`, String `b`)|=-Operator|
|Boolean op_Inequality(String `a` , String `b`)|!=-Operator|
|Microsoft.VisualBasic.Strings.Trim(String `str`)|Trim(`str`)|
|Microsoft.VisualBasic.Strings.LTrim(String `str`)|Ltrim(`str`)|
|Microsoft.VisualBasic.Strings.RTrim(String `str`)|Rtrim(`str`)|
|Microsoft.VisualBasic.Strings.Len(String `expression`)|Length(`expression`)|
|Microsoft.VisualBasic.Strings.Left(String `str`, Int32 `Length`)|Left(`str`, `Length`)|
|Microsoft.VisualBasic.Strings.Mid(String `str`, Int32 `Start`, Int32 `Length`)|Substring(`str`, `Start`, `Length`)|
|Microsoft.VisualBasic.Strings.Right(String `str`, Int32 `Length`)|Right(`str`, `Length`)|
|Microsoft.VisualBasic.Strings.UCase(String `Value`)|ToUpper(`Value`)|
|Microsoft.VisualBasic.Strings.LCase(String Value)|ToLower(`Value`)|

## <a name="systemstring-method-instance-mapping"></a>Mapping der System.String-Methode (Instanz)

|System.String-Methode (Instanz)|Kanonische Funktion|Hinweise|
|---------------------------------------|------------------------|-----------|
|Boolean Contains(String `value`)|`this` LIKE '%`value`%'|Wenn `value` keine Konstante ist, dann wird dies zugeordnet zu: IndexOf(`this`, `value`) > 0.|
|Boolean EndsWith(String `value`)|`this` WIE `'` % `value`"|Wenn `value` keine Konstante ist, dann wird dies zugeordnet zu: Right(`this`, length(`value`)) = `value`.|
|Boolean StartsWith(String `value`)|`this` LIKE '`value`%'|Wenn `value` keine Konstante ist, dann wird dies zugeordnet zu: IndexOf(`this`, `value`) = 1.|
|Länge|Length(`this`)||
|Int32 IndexOf(String `value`)|IndexOf(`this`, `value`) - 1||
|System.String Insert(Int32 `startIndex`, String `value`)|Concat(Concat(Substring(`this`, 1, `startIndex`), `value`), Substring(`this`, `startIndex`+1, Length(`this`) - `startIndex`))||
|System.String Remove(Int32 `startIndex`)|Substring(`this`, 1, `startIndex`)||
|System.String Remove(Int32 `startIndex`, Int32 `count`)|Concat (Teilzeichenfolge (`this`, "1" `startIndex`), Substring (`this`, `startIndex`  +  `count` + 1, Länge (`this`) – (`startIndex` + `count`)))|Remove(`startIndex`, `count`) wird nur unterstützt, wenn `count` eine ganze Zahl größer oder gleich 0 (null) ist.|
|System.String Replace(String `oldValue`, String `newValue`)|Replace(`this`, `oldValue`, `newValue`)||
|System.String Substring(Int32 `startIndex`)|Substring(`this`, `startIndex` +1, Length(`this`) - `startIndex`)||
|System.String Substring(Int32 `startIndex`, Int32 `length`)|Substring (`this`, `startIndex` + 1, `length`)||
|System.String ToLower()|ToLower(`this`)||
|System.String ToUpper()|ToUpper(`this`)||
|System.String Trim()|Trim(`this`)||
|System.String TrimEnd(Char[] `trimChars`)|RTrim(`this`)||
|System.String TrimStart(Char[]`trimChars`)|LTrim(`this`)||
|Boolean Equals(String `value`)|=-Operator||

## <a name="systemdatetime-method-static-mapping"></a>Mapping der System.DateTime-Methode (statisch)

|System.DateTime-Methode (statisch)|Kanonische Funktion|Hinweise|
|---------------------------------------|------------------------|-----------|
|Boolean Equals(DateTime `t1`, DateTime `t2`)|=-Operator||
|System.DateTime.Now|CurrentDateTime()||
|System.DateTime.UtcNow|CurrentUtcDateTime()||
|Boolean op_Equality(DateTime `d1`, DateTime `d2`)|=-Operator||
|Boolean op_GreaterThan(DateTime `t1`, DateTime `t2`)|>-Operator||
|Boolean op_GreaterThanOrEqual(DateTime `t1`, DateTime `t2`)|>=-Operator||
|Boolean op_Inequality(DateTime `t1`, DateTime `t2`)|!=-Operator||
|Boolesche Op_LessThan ("DateTime" `t1`, "DateTime" `t2`)|<-Operator||
|Boolean op_LessThanOrEqual(DateTime `t1`, DateTime `t2`)|<=-Operator||
|Microsoft.VisualBasic.DateAndTime.DatePart( _<br /><br /> ByVal `Interval` As DateInterval, \_<br /><br /> ByVal `DateValue` As DateTime, \_<br /><br /> Optional ByVal `FirstDayOfWeekValue` As FirstDayOfWeek = VbSunday, \_<br /><br /> Optionale ByVal `FirstWeekOfYearValue` als FirstWeekOfYear VbFirstJan1 = \_<br /><br /> ) As Integer||Weitere Informationen finden Sie im Abschnitt über die DatePart-Funktion.|
|Microsoft.VisualBasic.DateAndTime.Now|CurrentDateTime()||
|Microsoft.VisualBasic.DateAndTime.Year(DateTime `TimeValue`)|Year()||
|Microsoft.VisualBasic.DateAndTime.Month(DateTime `TimeValue`)|Month()||
|Microsoft.VisualBasic.DateAndTime.Day(DateTime `TimeValue`)|Day()||
|Microsoft.VisualBasic.DateAndTime.Hour(DateTime `TimeValue`)|Hour()||
|Microsoft.VisualBasic.DateAndTime.Minute(DateTime `TimeValue`)|Minute()||
|Microsoft.VisualBasic.DateAndTime.Second(DateTime `TimeValue`)|Second()||

## <a name="systemdatetime-method-instance-mapping"></a>Mapping der System.DateTime-Methode (Instanz)

|System.DateTime-Methode (Instanz)|Kanonische Funktion|
|-----------------------------------------|------------------------|
|Boolean Equals(DateTime `value`)|=-Operator|
|Day|Day(`this`)|
|Hour|Hour(`this`)|
|Millisecond|Millisecond(`this`)|
|Minute|Minute(`this`)|
|Monat|Month(`this`)|
|Second|Second(`this`)|
|Jahr|Year(`this`)|

## <a name="systemdatetimeoffset-method-instance-mapping"></a>System.DateTimeOffset Method (Instance)-Zuordnung

Die für die `get`-Methoden in den aufgeführten Eigenschaften gezeigte Zuordnung.

|System.DateTimeOffset-Methode (Instanz)|Kanonische Funktion|Hinweise|
|-----------------------------------------------|------------------------|-----------|
|Day|Day(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Hour|Hour(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Millisecond|Millisecond(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Minute|Minute(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Monat|Month(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Second|Second(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Jahr|Year(`this`)|Wird für SQL Server 2005 nicht unterstützt.|

> [!NOTE]
> Die <xref:System.DateTimeOffset.Equals%2A>-Methode gibt `true` zurück, wenn die verglichenen <xref:System.DateTimeOffset>-Objekte gleich sind, andernfalls `false`. Die <xref:System.DateTimeOffset.CompareTo%2A>-Methode gibt 0, 1 oder -1 zurück, abhängig davon, ob das verglichene <xref:System.DateTimeOffset>-Objekt gleich, größer oder kleiner ist.

## <a name="systemdatetimeoffset-method-static-mapping"></a>System.DateTimeOffset-Methodenzuordnung (statisch)

Die für die `get`-Methoden in den aufgeführten Eigenschaften gezeigte Zuordnung.

|System.DateTimeOffset-Methode (statisch)|Kanonische Funktion|Hinweise|
|---------------------------------------------|------------------------|-----------|
|System.DateTimeOffset.Now()|CurrentDateTimeOffset()|Wird für SQL Server 2005 nicht unterstützt.|

## <a name="systemtimespan-method-instance-mapping"></a>System.TimeSpan-Methodenzuordnung (Instanz)

Die für die `get`-Methoden in den aufgeführten Eigenschaften gezeigte Zuordnung.

|System.TimeSpan-Methode (Instanz)|Kanonische Funktion|Hinweise|
|-----------------------------------------|------------------------|-----------|
|Stunden|Hour(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Milliseconds|Millisecond(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Besprechungsprotokoll|Minute(`this`)|Wird für SQL Server 2005 nicht unterstützt.|
|Seconds|Second(`this`)|Wird für SQL Server 2005 nicht unterstützt.|

> [!NOTE]
> Die <xref:System.TimeSpan.Equals%2A>-Methode gibt `true` zurück, wenn die verglichenen <xref:System.TimeSpan>-Objekte gleich sind, andernfalls `false`. Die <xref:System.TimeSpan.CompareTo%2A>-Methode gibt 0, 1 oder -1 zurück, abhängig davon, ob das verglichene <xref:System.TimeSpan>-Objekt gleich, größer oder kleiner ist.

### <a name="datepart-function"></a>DatePart-Funktion

Die `DatePart`-Funktion wird, in Abhängigkeit vom Wert von `Interval`, einer von mehreren kanonischen Funktionen zugeordnet. In der folgenden Tabelle wird das Mapping zu kanonischen Funktionen für die unterstützten Werte von `Interval` angezeigt:

|Intervallwert|Kanonische Funktion|
|--------------------|------------------------|
|DateInterval.Year|Year()|
|DateInterval.Month|Month()|
|DateInterval.Day|Day()|
|DateInterval.Hour|Hour()|
|DateInterval.Minute|Minute()|
|DateInterval.Second|Second()|

## <a name="mathematical-function-mapping"></a>Zuordnung mathematischer Funktionen

|CLR-Methode|Kanonische Funktion|
|----------------|------------------------|
|System.Decimal.Ceiling(Decimal `d`)|Ceiling(`d`)|
|System.Decimal.Floor(Decimal `d`)|Floor(`d`)|
|System.Decimal.Round(Decimal `d`)|Round(`d`)|
|System.Math.Ceiling(Decimal `d`)|Ceiling(`d`)|
|System.Math.Floor(Decimal `d`)|Floor(`d`)|
|System.Math.Round(Decimal `d`)|Round(`d`)|
|System.Math.Ceiling(Double `a`)|Ceiling(`a`)|
|System.Math.Floor(Double `a`)|Floor(`a`)|
|System.Math.Round(Double `a`)|Round(`a`)|
|System.Math.Round(Double-Wert, Int16-Ziffern)|Round(Wert, Ziffern)|
|System.Math.Round(Double-Wert, Int32-Ziffern)|Round(Wert, Ziffern)|
|System.Math.Round(Dezimalwert, Int16-Ziffern)|Round(Wert, Ziffern)|
|System.Math.Round(Dezimalwert, Int32-Ziffern)|Round(Wert, Ziffern)|
|System.Math.Abs(Int16-Wert)|Abs(Wert)|
|System.Math.Abs(Int32-Wert)|Abs(Wert)|
|System.Math.Abs(Int64-Wert)|Abs(Wert)|
|System.Math.Abs(Byte-Wert)|Abs(Wert)|
|System.Math.Abs(Einzelwert)|Abs(Wert)|
|System.Math.Abs(Double-Wert)|Abs(Wert)|
|System.Math.Abs(Dezimalwert)|Abs(Wert)|
|System.Math.Truncate(Double-Wert, Int16-Ziffern)|Truncate(Wert, Ziffern)|
|System.Math.Truncate(Double-Wert, Int32-Ziffern)|Truncate(Wert, Ziffern)|
|System.Math.Truncate(Dezimalwert, Int16-Ziffern)|Truncate(Wert, Ziffern)|
|System.Math.Truncate(Dezimalwert, Int32-Ziffern)|Truncate(Wert, Ziffern)|
|System.Math.Power(Int32-Wert, Int64-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Int32-Wert, Double-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Int32-Wert, Dezimalexponent)|Power(Wert, Exponent)|
|System.Math.Power(Int64-Wert, Int64-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Int64-Wert, Double-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Int64-Wert, Dezimalexponent)|Power(Wert, Exponent)|
|System.Math.Power(Double-Wert, In64-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Double-Wert, Double-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Double-Wert, Dezimalexponent)|Power(Wert, Exponent)|
|System.Math.Power(Dezimalwert, Int64-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Dezimalwert, Double-Exponent)|Power(Wert, Exponent)|
|System.Math.Power(Dezimalwert, Dezimalexponent)|Power(Wert, Exponent)|

## <a name="bitwise-operator-mapping"></a>Mapping bitweiser Operatoren

|Bitweiser Operator|Kanonische Funktion für nicht boolesche Operanden|Kanonische Funktion für boolesche Operanden|
|----------------------|--------------------------------------------------|---------------------------------------------|
|Bitweiser "AND"-Operator|BitWiseAnd|op1 AND op2|
|Bitweiser OR-Operator|BitWiseOr|op1 OR op2|
|Bitweiser "NOT"-Operator|BitWiseNot|NOT (op)|
|Bitweiser "XOR"-Operator|BitWiseXor|((op1 AND NOT(op2)) OR (NOT(op1) AND op2))|

## <a name="other-mapping"></a>Andere Zuordnung

|Methode|Kanonische Funktion|
|------------|------------------------|
|Guid.NewGuid()|NewGuid()|

## <a name="see-also"></a>Siehe auch

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
