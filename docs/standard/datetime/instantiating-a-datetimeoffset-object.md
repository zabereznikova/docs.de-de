---
title: Instanziieren eines DateTimeOffset-Objekts
description: Instanziieren eines DateTimeOffset-Objekts
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 3b6e2cc973b9587cc9950ecd6898b8a321a01036

---

# <a name="instantiating-a-datetimeoffset-object"></a>Instanziieren eines DateTimeOffset-Objekts

Die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur bietet eine Reihe von Methoden zum Erstellen neuer [DateTimeOffset](xref:System.DateTimeOffset) Werte. Viele von ihnen entsprechen direkt den Methoden zum Instanziieren neuer [System.DateTime](xref:System.DateTime)-Werte mit Erweiterungen, mit denen Sie die Abweichung des Datums- und Zeitwerts von der koordinierten Weltzeit (UTC) angeben können. Insbesondere können Sie einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert auf folgende Weise instanziieren:

* Durch Aufrufen eines [DateTimeOffset](xref:System.DateTimeOffset)-Konstruktors.

* Durch implizites Konvertieren eines Werts in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.

* Durch Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts.

## <a name="date-and-time-literals"></a>Datums- und Uhrzeitliterale

Für Sprachen, die dies unterstützen, besteht eine der am häufigsten verwendeten Methoden zum Instanziieren eines [DateTime](xref:System.DateTime)-Werts darin, den Datums- und Uhrzeitwert als hartcodierten Literalwert bereitzustellen. Der folgende Visual Basic-Code erstellt z.B. ein [DateTime](xref:System.DateTime)-Objekt, dessen Wert dem 1. Januar 2008, 10:00 Uhr, entspricht.

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

[DateTimeOffset](xref:System.DateTimeOffset)-Werte können auch über Datums- und Uhrzeitliterale initialisiert werden, wenn Sprachen verwendet werden, die [DateTime](xref:System.DateTime)-Literale unterstützen. Mit dem folgenden Visual Basic-Code wird beispielsweise ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt erstellt.

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

Wie die Konsolenausgabe zeigt, wird dem auf diese Weise erstellten [DateTimeOffset](xref:System.DateTimeOffset)-Wert die Abweichung der lokalen Zeitzone zugewiesen. Dies bedeutet, dass ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert, der über ein Zeichenliteral zugewiesen wurde, keinen bestimmten Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.

## <a name="datetimeoffset-constructors"></a>DateTimeOffset-Konstruktoren

Der Typ [System.DateTimeOffset](xref:System.DateTimeOffset) definiert fünf Konstruktoren. Drei davon entsprechen direkt den [DateTime](xref:System.DateTime)-Konstruktoren mit einem zusätzlichen Parameter vom Typ [System.TimeSpan](xref:System.TimeSpan), der die Datums- und Uhrzeitabweichung von UTC definiert. Mit diesen können Sie einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert basierend auf dem Wert der einzelnen Datums- und Uhrzeitkomponenten definieren. Der folgende Code verwendet beispielsweise diese drei Konstruktoren, um [DateTimeOffset](xref:System.DateTimeOffset)-Objekte mit identischen Werten von „7/1/2008 12:05 AM +01:00“ zu instanziieren.

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

Wenn der Wert des [DateTimeOffset](xref:System.DateTimeOffset)-Objekts, das über ein [PersianCalendar](xref:System.Globalization.PersianCalendar)-Objekt als eines der Argumente für den Konstruktor instanziiert wird, in der Konsole angezeigt wird, beachten Sie, dass es als Datum im gregorianischen Kalender und nicht im persischen Kalender ausgedrückt wird. 

Die anderen beiden Konstruktoren erstellen ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt aus einem DateTime-Wert. Der erste verfügt über einen einzelnen Parameter, den [DateTime](xref:System.DateTime)-Wert zum Konvertieren in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert. Die Abweichung des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts hängt von der [Kind](xref:System.DateTime.Kind)-Eigenschaft des einzelnen [DateTime](xref:System.DateTime)-Parameters des Konstruktors ab. Wenn der Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, wird die Abweichung auf [TimeSpan.Zero](xref:System.TimeSpan.Zero) festgelegt. Andernfalls wird die Abweichung entsprechend der lokalen Zeitzone eingestellt. Das folgende Beispiel veranschaulicht die Verwendung dieses Konstruktors für das Instanziieren von [DateTimeOffset](xref:System.DateTimeOffset)-Objekten, die die UTC-Zeit und die lokale Zeitzone darstellen:

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> Das Aufrufen der Überladung des [DateTimeOffset](xref:System.DateTimeOffset)-Konstruktors mit einem einzelnen [DateTime](xref:System.DateTime)-Parameter entspricht dem impliziten Konvertieren eines [DateTime](xref:System.DateTime)-Werts in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.

Der zweite Konstruktor, der ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt aus einem [DateTime](xref:System.DateTime)-Wert erstellt, verfügt über zwei Parameter: den zu konvertierenden [DateTime](xref:System.DateTime)-Wert und einen [TimeSpan](xref:System.TimeSpan)-Wert, der die Datums- und Uhrzeitabweichung von UTC darstellt. Dieser Abweichungswert muss der [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters des Konstruktors entsprechen. Andernfalls wird eine [System.ArgumentException](xref:System.ArgumentException) ausgelöst. Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, muss der Wert des zweiten Parameters [TimeSpan.Zero](xref:System.TimeSpan.Zero) lauten. Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet, muss der Wert des zweiten Parameters der Zeitzonenabweichung des lokalen Systems entsprechen. Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, kann die Abweichung einen beliebigen gültigen Wert annehmen. Der folgende Code zeigt Aufrufe dieses Konstruktors zum Konvertieren von [DateTime](xref:System.DateTime) in [DateTimeOffset](xref:System.DateTimeOffset)-Werte.

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a>Implizite Typkonvertierung
 
Der [System.DateTimeOffset](xref:System.DateTimeOffset)-Typ unterstützt eine implizite Typkonvertierung: von einem [System.DateTime](xref:System.DateTime)-Wert in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert. (Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, für die keine explizite Umwandlung (in C#) oder Konvertierung (in Visual Basic) erforderlich ist und bei der keine Informationen verloren gehen. Dies ermöglicht beispielsweise folgenden Code:

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

Die Abweichung des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts hängt vom DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaftswert ab. Wenn der Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, wird die Abweichung auf [TimeSpan.Zero](xref:System.TimeSpan.Zero) festgelegt. Wenn der Wert entweder [DateTimeKind.Local](xref:System.DateTimeKind.Local) oder [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, wird die Abweichung entsprechend der lokalen Zeitzone festgelegt.

## <a name="parsing-the-string-representation-of-a-date-and-time"></a>Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts

Der [System.DateTimeOffset](xref:System.DateTimeOffset)-Typ unterstützt vier Methoden, die Ihnen die Konvertierung der Zeichenfolgendarstellung eines Datums und einer Uhrzeit in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert ermöglichen:

* [Parse](xref:System.DateTimeOffset.Parse(System.String)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, und löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

* [TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, und gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.

* [ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren. Die Methode löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.

* [TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren. Die Methode gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.

Das folgende Beispiel veranschaulicht Aufrufe dieser vier Konvertierungsmethoden zum Instanziieren eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts.

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)




<!--HONumber=Nov16_HO3-->


