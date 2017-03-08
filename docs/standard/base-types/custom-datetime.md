---
title: "Custom date and time format strings (Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit)"
description: "Custom date and time format strings (Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit)"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 45f286f5-92c9-4150-957c-fa6d394bc29b
translationtype: Human Translation
ms.sourcegitcommit: 28625def4199a660fe0ea04ab75f4f65d2e0c9c4
ms.openlocfilehash: 285e4bfd6a53d576ce4538b09a2561065c93e399
ms.lasthandoff: 02/23/2017

---

# <a name="custom-date-and-time-format-strings"></a>Custom date and time format strings (Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit)

Eine Formatzeichenfolge für Datum und Uhrzeit definiert die Textdarstellung eines [DateTime](xref:System.DateTime)-Werts oder eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts, der aus einem Formatierungsvorgang resultiert. Sie kann auch die Darstellung eines Datums- und Uhrzeitwerts definieren, der in einem Analysevorgang erforderlich ist, um die Zeichenfolge erfolgreich in ein Datum und eine Uhrzeit zu konvertieren. Benutzerdefinierte Formatzeichenfolgen bestehen aus einem oder mehreren benutzerdefinierten Formatbezeichnern für Datum und Uhrzeit. Alle Zeichenfolgen, bei denen es sich nicht um [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md) handelt, werden als benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit interpretiert. 

Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit können sowohl mit dem [DateTime](xref:System.DateTime)-Wert als auch mit dem [DateTimeOffset](xref:System.DateTimeOffset)-Wert verwendet werden.

In Formatierungsvorgängen können benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit entweder mit der `ToString`-Methode einer Datums- und Uhrzeitinstanz oder mit einer Methode verwendet werden, die die kombinierte Formatierung unterstützt. Das folgende Beispiel veranschaulicht beide Möglichkeiten. 

```csharp
DateTime thisDate1 = new DateTime(2011, 6, 10);
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".");

DateTimeOffset thisDate2 = new DateTimeOffset(2011, 6, 10, 15, 24, 16, 
                                              TimeSpan.Zero);
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2); 
// The example displays the following output:
//    Today is June 10, 2011.
//    The current date and time: 06/10/11 15:24:16 +00:00
```

```vb
Dim thisDate1 As Date = #6/10/2011#
Console.WriteLine("Today is " + thisDate1.ToString("MMMM dd, yyyy") + ".")

Dim thisDate2 As New DateTimeOffset(2011, 6, 10, 15, 24, 16, TimeSpan.Zero)
Console.WriteLine("The current date and time: {0:MM/dd/yy H:mm:ss zzz}", 
                   thisDate2) 
' The example displays the following output:
'    Today is June 10, 2011.
'    The current date and time: 06/10/11 15:24:16 +00:00
```

In Analysevorgängen können benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit mit den Methoden [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) und [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) verwendet werden. Bei diesen Methoden muss die Eingabezeichenfolge genau einem bestimmten Muster entsprechen, damit der Analysevorgang erfolgreich ausgeführt werden kann. Das folgende Beispiel veranschaulicht einen Aufruf der [DateTimeOffset.ParseExact(String, String, IFormatProvider)](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider))-Methode, um ein Datum zu analysieren, das einen Tag, einen Monat und eine zweistellige Jahresangabe enthalten muss.

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] dateValues = { "30-12-2011", "12-30-2011", 
                              "30-12-11", "12-30-11" };
      string pattern = "MM-dd-yy";
      DateTime parsedDate;

      foreach (var dateValue in dateValues) {
         if (DateTime.TryParseExact(dateValue, pattern, null, 
                                   DateTimeStyles.None, out parsedDate))
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate);
         else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue);
      }
   }
}
// The example displays the following output:
//    Unable to convert '30-12-2011' to a date and time.
//    Unable to convert '12-30-2011' to a date and time.
//    Unable to convert '30-12-11' to a date and time.
//    Converted '12-30-11' to 12/30/2011.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValues() As String = { "30-12-2011", "12-30-2011", 
                                      "30-12-11", "12-30-11" }
      Dim pattern As String = "MM-dd-yy"
      Dim parsedDate As Date

      For Each dateValue As String In dateValues
         If DateTime.TryParseExact(dateValue, pattern, Nothing, 
                                   DateTimeStyles.None, parsedDate) Then
            Console.WriteLine("Converted '{0}' to {1:d}.", 
                              dateValue, parsedDate)
         Else
            Console.WriteLine("Unable to convert '{0}' to a date and time.", 
                              dateValue)
         End If                                                         
      Next
   End Sub
End Module
' The example displays the following output:
'    Unable to convert '30-12-2011' to a date and time.
'    Unable to convert '12-30-2011' to a date and time.
'    Unable to convert '30-12-11' to a date and time.
'    Converted '12-30-11' to 12/30/2011.
```

Die folgende Tabelle beschreibt die benutzerdefinierten Formatbezeichner für Datum und Uhrzeit und zeigt eine Ergebniszeichenfolge an, die von den einzelnen Formatbezeichnern erstellt wird. Standardmäßig entsprechen Ergebniszeichenfolgen den Formatierungskonventionen der Kultur "en-US". Wenn ein bestimmter Formatbezeichner eine lokalisierte Ergebniszeichenfolge erzeugt, wird im Beispiel auch die Kultur angegeben, für die die Ergebniszeichenfolge gilt. Weitere Informationen zum Verwenden von benutzerdefinierten Formatzeichenfolgen für Datum und Uhrzeit finden Sie im Abschnitt Hinweise.

Formatbezeichner | Beschreibung | Beispiele
---------------- | ----------- | --------
"d" | Der Tag des Monats, von 1 bis 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"dd" | Der Tag des Monats, von 01 bis 31. | `2019-06-01T13:45:30 -> 1`; `2019-06-15T13:45:30 -> 15`
"ddd" | Der abgekürzte Name des Tags der Woche. | `2019-06-15T13:45:30 -> Mon (en-US)`; `2019-06-15T13:45:30 -> Пн (ru-RU)`; `2019-06-15T13:45:30 -> lun. (fr-FR)`
"dddd" | Der vollständige Name des Wochentags. | `2019-06-15T13:45:30 -> Monday (en-US)`; `2019-06-15T13:45:30 -> понедельник (ru-RU)`; `2019-06-15T13:45:30 -> lundi (fr-FR)`
"f" | Die Zehntelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.05 -> 0` 
"ff" | Die Hundertstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> 00`
"fff" | Die Millisekunden in einem Datums- und Uhrzeitwert. | `6/15/2019 13:45:30.617 -> 617`; `6/15/2019 13:45:30.0005 -> 000`
"ffff" | Die Zehntausendstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175000 -> 6175`; `2019-06-15T13:45:30.0000500 -> 0000`
"fffff" | Die Hunderttausendstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175400 -> 61754`; `6/15/2019 13:45:30.000005 -> 00000`
"ffffff" | Die Millionstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> 000000`
"fffffff" | Die Zehnmillionstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175425 -> 6175425`;`2019-06-15T13:45:30.0001150 -> 0001150`
"F" | Wenn ungleich&0; (null), die Zehntelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6170000 -> 6`; `2019-06-15T13:45:30.0500000 -> (no output)`
"FF" | Wenn ungleich&0; (null), die Hundertstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6170000 -> 61`; `2019-06-15T13:45:30.0050000 -> (no output)`
"FFF" | Wenn ungleich&0; (null), die Millisekunden in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6170000 -> 617`; `2019-06-15T13:45:30.0005000 -> (no output)`
"FFFF" | Wenn ungleich&0; (null), die Zehntausendstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.5275000 -> 5275`; `2019-06-15T13:45:30.0000500 -> (no output)`
"FFFFF" | Wenn ungleich&0; (null), die Hunderttausendstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175400 -> 61754`; `2019-06-15T13:45:30.0000050 -> (no output)`
"FFFFFF" | Wenn ungleich&0; (null), die Millionstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175420 -> 617542`; `2019-06-15T13:45:30.0000005 -> (no output)`
"FFFFFFF" | Wenn ungleich&0; (null), die Zehnmillionstelsekunde in einem Datums- und Uhrzeitwert. | `2019-06-15T13:45:30.6175425 -> 6175425`; `2019-06-15T13:45:30.0001150 -> 000115`
"g", "gg" | Der Zeitraum. | `2019-06-15T13:45:30.6170000 -> A.D.`
"h"  | Die Stunde, von 1 bis 12 (12-Stunden-Format). | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 1`
"hh" | Die Stunde, von 01 bis 12 (12-Stunden-Format). | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 01`
"H" | Die Stunde, von 0 bis 24 (23-Stunden-Format). | `2019-06-15T01:45:30 -> 1`; `2019-06-15T13:45:30 -> 13`
"HH" | Die Stunde, von 00 bis 23 (24-Stunden-Format). | `2019-06-15T01:45:30 -> 01`; `2019-06-15T13:45:30 -> 13`
"K" | Zeitzoneninformationen. | Mit [DateTime](xref:System.DateTime)-Werten: `2019-06-15T13:45:30, Kind Unspecified ->`; `2019-06-15T13:45:30, Kind Utc -> Z`; `2019-06-15T13:45:30, Kind Local -> -07:00 (depends on local computer settings)`; Mit [DateTimeOffset](xref:System.DateTimeOffset)-Werten: `2019-06-15T01:45:30-07:00 --> -07:00`; `2019-06-15T08:45:30+00:00 --> +00:00`
"m" | Die Minute, von 0 bis 59. | `2019-06-15T01:09:30 -> 9`; `2019-06-15T13:29:30 -> 29`
"mm" | Die Minute, von 00 bis 59. | `2019-06-15T01:09:30 -> 09`; `2019-06-15T01:45:30 -> 45`
"M" | Der Monat, von 1 bis 12. | `2019-06-15T13:45:30 -> 6`
"MM" | Der Monat, von 01 bis 12. | `2019-06-15T13:45:30 -> 06`
"MMM" | Der abgekürzte Name des Monats. | `2019-06-15T13:45:30 -> Jun (en-US)`; `2019-06-15T13:45:30 -> juin (fr-FR)`; `2019-06-15T13:45:30 -> Jun (zu-ZA)`
"MMMM" | Der vollständige Name des Monats. | `2019-06-15T13:45:30 -> June (en-US)`; `2019-06-15T13:45:30 -> juni (da-DK)`; `2019-06-15T13:45:30 -> uJuni (zu-ZA)`
"s" | Die Sekunde, von 0 bis 59. | `2019-06-15T13:45:09 -> 9`
"ss" | Die Sekunde, von 00 bis 59. | `2019-06-15T13:45:09 -> 09`
"t" | Das erste Zeichen des AM/PM-Kennzeichners. | `2019-06-15T13:45:30 -> P (en-US)`; `2019-06-15T13:45:30 -> 午 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"tt" | Der AM/PM-Kennzeichner. | `2019-06-15T13:45:30 -> PM (en-US)`; `2019-06-15T13:45:30 -> 午後 (ja-JP)`; `2019-06-15T13:45:30 -> (fr-FR)`
"y"  | Das Jahr, von 0 bis 99. | `0001-01-01T00:00:00 -> 1`; `0900-01-01T00:00:00 -> 0`; `1900-01-01T00:00:00 -> 0`; `2019-06-15T13:45:30 -> 9`; `2019-06-15T13:45:30 -> 19`
"yy" | Das Jahr, von 00 bis 99. | `0001-01-01T00:00:00 -> 01`; `0900-01-01T00:00:00 -> 00`; `1900-01-01T00:00:00 -> 00`; `2019-06-15T13:45:30 -> 19`
"yyy" | Das Jahr, mit einem Minimum von drei Ziffern. | `0001-01-01T00:00:00 -> 001`; `0900-01-01T00:00:00 -> 900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyy"  | Das Jahr als vierstellige Zahl. | `0001-01-01T00:00:00 -> 0001`; `0900-01-01T00:00:00 -> 0900`; `1900-01-01T00:00:00 -> 1900`; `2019-06-15T13:45:30 -> 2019`
"yyyyy" | Das Jahr als fünfstellige Zahl. | `0001-01-01T00:00:00 -> 00001`; `2019-06-15T13:45:30 -> 02019`
"z" | Offset von UTC in Stunden, ohne führende Nullen. | `2019-06-15T13:45:30-07:00 -> -7`
"zz" | Offset von UTC in Stunden, mit einer führenden Null für einen einstelligen Wert. | `2019-06-15T13:45:30-07:00 -> -07`
"zzz" | Offset von UTC in Stunden und Minuten. | `2019-06-15T13:45:30-07:00 -> -07:00`
":" | Das Zeittrennzeichen. | `2019-06-15T13:45:30 -> : (en-US)`; `2019-06-15T13:45:30 -> . (it-IT)`; `2019-06-15T13:45:30 -> : (ja-JP)`
"/" | Das Datumstrennzeichen. | `2019-06-15T13:45:30 -> / (en-US)`; `2019-06-15T13:45:30 -> - (ar-DZ)`; `2019-06-15T13:45:30 -> . (tr-TR)`
"string", 'string' | Trennzeichen für Literalzeichenfolge. | `2019-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P`; `2019-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P`
% | Definiert das nächste Zeichen als benutzerdefinierten Formatbezeichner. | `2019-06-15T13:45:30 (%h) -> 1`
\ | Das Escapezeichen. | `2019-06-15T13:45:30 (h \h) -> 1 h`
Jedes andere Zeichen | Das Zeichen wird unverändert in die Ergebniszeichenfolge kopiert. | `2019-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A`

In den folgenden Abschnitten finden Sie weitere Informationen zu den einzelnen benutzerdefinierten Formatbezeichnern für Datum- und Uhrzeit. Sofern nicht anders angegeben, erzeugt jeder Bezeichner eine identische Zeichenfolgendarstellung, unabhängig davon, ob er mit einem [DateTime](xref:System.DateTime)-Wert oder einem [DateTimeOffset](xref:System.DateTimeOffset)-Wert verwendet wird. 

## <a name="the-d-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „d“

Der benutzerdefinierte Formatbezeichner "d" stellt den Tag des Monats als Zahl zwischen 1 und 31 dar. Einstellige Tage werden ohne führende Null formatiert. 

Wenn der Formatbezeichner "d" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als d-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "d" in mehrere Formatzeichenfolgen ein. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15); 

Console.WriteLine(date1.ToString("d, M", 
                  CultureInfo.InvariantCulture)); 
// Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays 29 agosto  
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("d, M", _
                  CultureInfo.InvariantCulture)) 
' Displays 29, 8

Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 29 August
Console.WriteLine(date1.ToString("d MMMM", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays 29 agosto 
```

## <a name="the-dd-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „dd“

Die benutzerdefinierte Formatzeichenfolge "dd" stellt den Tag des Monats als Zahl zwischen 01 und 31 dar. Einstellige Tage werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "dd" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-ddd-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ddd“

Der benutzerdefinierte Formatbezeichner "ddd" stellt den abgekürzten Namen des Tags der Woche dar. Der lokalisierte abgekürzte Name des Wochentags wird aus der [DateTimeFormatInfo.AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "ddd" in eine benutzerdefinierte Formatzeichenfolge ein. 

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-dddd-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „dddd“

Der benutzerdefinierte Formatbezeichner "dddd" (plus einer beliebigen Anzahl zusätzlicher d-Bezeichner) stellt den vollständigen Namen des Tags der Woche dar. Der lokalisierte Name des Wochentags wird aus der [DateTimeFormatInfo.DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "dddd" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto    
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto                                          
```

## <a name="the-f-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „f“

Der benutzerdefinierte Formatbezeichner "f" stellt die signifikanteste Ziffer des Sekundenbruchteils dar, d. h. die Zehntelsekunden in einem Datums- und Uhrzeitwert.

Wenn der Formatbezeichner "f" allein verwendet wird, d. h. ohne andere Formatbezeichner, wird er als f-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Wenn Sie den Formatbezeichner „f“ als Teil einer Formatzeichenfolge verwenden, die für die Methoden [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) oder [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) bereitgestellt wird, gibt die Anzahl der verwendeten Formatbezeichner „f“ die Anzahl der signifikantesten Ziffern des Sekundenbruchteils an, die vorhanden sein müssen, damit die Zeichenfolge erfolgreich analysiert wird.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "f" in mehrere benutzerdefinierte Formatzeichenfolgen ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ff“

Der benutzerdefinierte Formatbezeichner "ff" stellt die zwei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hundertstelsekunden in einem Datums- und Uhrzeitwert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner „ff“ in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „fff“

Der benutzerdefinierte Formatbezeichner "fff" stellt die drei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millisekunden in einem Datums- und Uhrzeitwert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "fff" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ffff“

Der benutzerdefinierte Formatbezeichner "ffff" stellt die vier signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehntausendstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Zehntausendstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="the-fffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „fffff“

Der benutzerdefinierte Formatbezeichner "fffff" stellt die fünf signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hunderttausendstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Hunderttausendstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. 

## <a name="the-ffffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ffffff“

Der benutzerdefinierte Formatbezeichner "ffffff" stellt die sechs signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millionstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Millionstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. 

## <a name="the-fffffff-custom-format-specifier"></a>Benutzerdefinierte Formatbezeichner „fffffff“

Der benutzerdefinierte Formatbezeichner "fffffff" stellt die sieben signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehnmillionstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Zehnmillionstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. 

## <a name="the-f-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „F“

Der benutzerdefinierte Formatbezeichner "F" stellt die signifikanteste Ziffer des Sekundenbruchteils dar, d. h. die Zehntelsekunden in einem Datums- und Uhrzeitwert. Es wird nichts angezeigt, wenn die Ziffer&0; (null) ist. 

Wenn der Formatbezeichner "F" allein verwendet wird, d. h. ohne andere Formatbezeichner, wird er als F-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Die Anzahl der Formatbezeichner „F“, die mit den Methoden [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)), [DateTime.TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)), [DateTimeOffset.ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)) oder [DateTimeOffset.TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)) verwendet werden, gibt die maximale Anzahl der signifikantesten Ziffern des Sekundenbruchteils an, die vorhanden sein können, damit die Zeichenfolge erfolgreich analysiert wird.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "F" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FF“

Der benutzerdefinierte Formatbezeichner "FF" stellt die zwei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hundertstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder zwei&0;-Ziffern werden jedoch nicht angezeigt. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "FF" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
```

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-fff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFF“

Der benutzerdefinierte Formatbezeichner "FFF" stellt die drei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millisekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder drei&0;-Ziffern werden jedoch nicht angezeigt. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "FFF" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15, 18);
CultureInfo ci = CultureInfo.InvariantCulture;

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci));
// Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci));
// Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci));
// Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci));
// Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci));
// Displays 07:27:15.018
````

```vb
Dim date1 As New Date(2008, 8, 29, 19, 27, 15, 018)
Dim ci As CultureInfo = CultureInfo.InvariantCulture

Console.WriteLine(date1.ToString("hh:mm:ss.f", ci))
' Displays 07:27:15.0
Console.WriteLine(date1.ToString("hh:mm:ss.F", ci))
' Displays 07:27:15
Console.WriteLine(date1.ToString("hh:mm:ss.ff", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.FF", ci))
' Displays 07:27:15.01
Console.WriteLine(date1.ToString("hh:mm:ss.fff", ci))
' Displays 07:27:15.018
Console.WriteLine(date1.ToString("hh:mm:ss.FFF", ci))
' Displays 07:27:15.018
```

## <a name="the-ffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFF“

Der benutzerdefinierte Formatbezeichner "FFFF" stellt die vier signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehntausendstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder vier&0;-Ziffern werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Zehntausendstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="the-fffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFF" stellt die fünf signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hunderttausendstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder fünf&0;-Ziffern werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Hunderttausendstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="the-ffffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFF" stellt die sechs signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millionstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder sechs&0;-Ziffern werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Millionstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="the-fffffff-custom-format-specifier"></a>Benutzerdefinierte Formatbezeichner „FFFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFFF" stellt die sieben signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehnmillionstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder sieben&0;-Ziffern werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Zehnmillionstelsekundenkomponente eines Zeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab.

## <a name="the-g-or-gg-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „g“ oder „gg“

Die benutzerdefinierten Formatbezeichner "g" oder "gg (plus einer beliebigen Anzahl zusätzlicher g-Bezeichner)" stellen die Periode oder den Zeitraum dar, z. B. A.D. Dieser Bezeichner wird durch die Formatierung ignoriert, wenn dem zu formatierenden Datum keine Zeichenfolge für die Periode oder den Zeitraum zugeordnet ist. 

Wenn der Formatbezeichner "g" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als g-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "g" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(70, 08, 04);

Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.InvariantCulture));
// Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));                         
// Displays 08/04/0070 ap. J.-C.
```

```vb
Dim date1 As Date = #08/04/0070#

Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.InvariantCulture))
' Displays 08/04/0070 A.D.                        
Console.WriteLine(date1.ToString("MM/dd/yyyy g", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))                         
' Displays 08/04/0070 ap. J.-C.
```

## <a name="the-h-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „h“

Der benutzerdefinierte Formatbezeichner "h" stellt die Stunde als Zahl von 1 bis 12 dar. Die Stunde wird dabei im 12-Stunden-Format dargestellt, bei dem die ganzen Stunden ab Mitternacht oder 12 Uhr mittags gezählt werden. Eine Stunde nach Mitternacht lässt nicht von derselben Stunde nach&12; Uhr mittags unterscheiden. Die Stunde wird nicht gerundet. Einstellige Stunden werden ohne führende Null formatiert. Beispielsweise zeigt dieser benutzerdefinierte Formatbezeichner um 5:43 Uhr morgens oder nachmittags "5" an. 

Wenn der Formatbezeichner „h“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "h" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-hh-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „hh“

Der benutzerdefinierte Formatbezeichner "hh" (plus einer beliebigen Anzahl zusätzlicher h-Bezeichner) stellt die Stunde als Zahl von 01 bis 12 dar. Die Stunde wird dabei im 12-Stunden-Format dargestellt, bei dem die ganzen Stunden ab Mitternacht oder 12 Uhr mittags gezählt werden. Eine Stunde nach Mitternacht lässt nicht von derselben Stunde nach&12; Uhr mittags unterscheiden. Die Stunde wird nicht gerundet. Einstellige Stunden werden mit einer führenden Null formatiert. Beispielsweise zeigt dieser Formatbezeichner um 5:43 Uhr morgens oder nachmittags "05" an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "hh" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-h-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „H“

Der benutzerdefinierte Formatbezeichner "H" stellt die Stunde als Zahl von 0 bis 23 dar. Die Stunde wird dabei im nullbasierten 24-Stunden-Format dargestellt, bei dem die Stunden ab Mitternacht gezählt werden. Einstellige Stunden werden ohne führende Null formatiert. 

Wenn der Formatbezeichner „H“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "H" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("H:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 6:09:01 
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("H:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 6:09:01 
```

## <a name="the-hh-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „HH“

Der benutzerdefinierte Formatbezeichner "HH" (plus einer beliebigen Anzahl zusätzlicher H-Bezeichner) stellt die Stunde als Zahl von 00 bis 23 dar. Die Stunde wird dabei im nullbasierten 24-Stunden-Format dargestellt, bei dem die Stunden ab Mitternacht gezählt werden. Einstellige Stunden werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "HH" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 1, 1, 6, 9, 1);
Console.WriteLine(date1.ToString("HH:mm:ss", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01                        
```

```vb
Dim date1 As Date = #6:09:01AM#
Console.WriteLine(date1.ToString("HH:mm:ss", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01
```

## <a name="the-k-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „K“

Der benutzerdefinierte Formatbezeichner "K" stellt die Zeitzoneninformationen eines Datums- und Uhrzeitwerts dar. Bei Verwendung dieses Formatbezeichners mit [DateTime](xref:System.DateTime)-Werten wird die Ergebniszeichenfolge durch den Wert der [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft definiert: 
 
* Für die lokale Zeitzone (ein [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaftswert von [DateTimeKind.Local](xref:System.DateTimeKind.Local)) ist dieser Bezeichner gleich dem Bezeichner „zzz“ und erzeugt eine Ergebniszeichenfolge, die die lokale Abweichung von der koordinierten Weltzeit (Coordinated Universal Time, UTC) enthält, z.B. „-07:00“. 

* Für eine UTC-Zeit (ein [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaftswert von [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) umfasst die Ergebniszeichenfolge ein Zeichen „Z“, um ein UTC-Datum darzustellen. 

* Für eine Zeit in einer nicht angegebenen Zeitzone (eine Zeit, deren [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft gleich [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) ist), entspricht das Ergebnis [String.Empty](xref:System.String#System_String_Empty). 

Für [DateTimeOffset](xref:System.DateTimeOffset)-Werte ist der Formatbezeichner „K“ gleich dem Formatbezeichner „zz“ und erzeugt eine Ergebniszeichenfolge, die die Abweichung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts von der UTC enthält. 

Wenn der Formatbezeichner „K“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel zeigt die Zeichenfolge, die sich ergibt, wenn der benutzerdefinierte Formatbezeichner „K“ mit verschiedenen [DateTime](xref:System.DateTime)-Werten und [DateTimeOffset](xref:System.DateTimeOffset)-Werten in einem System in der Zeitzone Pacific verwendet wird.

```csharp
Console.WriteLine(DateTime.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTime.UtcNow.ToString("%K"));
// Displays Z      
Console.WriteLine("'{0}'", 
                  DateTime.SpecifyKind(DateTime.Now, 
                       DateTimeKind.Unspecified).ToString("%K"));
// Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"));
// Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"));
// Displays +00:00
Console.WriteLine(new DateTimeOffset(2008, 5, 1, 6, 30, 0, 
                      new TimeSpan(5, 0, 0)).ToString("%K"));
// Displays +05:00  
```

```vb
Console.WriteLine(Date.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(Date.UtcNow.ToString("%K"))
' Displays Z      
Console.WriteLine("'{0}'", _
                  Date.SpecifyKind(Date.Now, _
                                   DateTimeKind.Unspecified). _
                  ToString("%K"))
' Displays ''      
Console.WriteLine(DateTimeOffset.Now.ToString("%K"))
' Displays -07:00
Console.WriteLine(DateTimeOffset.UtcNow.ToString("%K"))
' Displays +00:00
Console.WriteLine(New DateTimeOffset(2008, 5, 1, 6, 30, 0, _
                                     New TimeSpan(5, 0, 0)). _
                  ToString("%K"))
' Displays +05:00 
```

## <a name="the-m-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „m“

Der benutzerdefinierte Formatbezeichner "m" stellt die Minute als Zahl von 0 bis 59 dar. Die Minute stellt ganze Minuten dar, die seit der letzten Stunde vergangen sind. Einstellige Minuten werden ohne führende Null formatiert. 

Wenn der Formatbezeichner "m" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als m-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "m" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-mm-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „mm“

Der benutzerdefinierte Formatbezeichner "mm" (plus einer beliebigem Anzahl zusätzlicher m-Bezeichner) stellt die Minute als Zahl von 00 bis 59 dar. Die Minute stellt ganze Minuten dar, die seit der letzten Stunde vergangen sind. Einstellige Minuten werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "mm" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-m-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „M“

Der benutzerdefinierte Formatbezeichner "M" stellt den Monat als Zahl von 1 bis 12 dar (oder von 1 bis 13 für Kalender mit 13 Monaten). Einstellige Monate werden ohne führende Null formatiert. 

Wenn der Formatbezeichner "M" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als M-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "M" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 18);
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("nl-NL")));                       
// Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", 
                  CultureInfo.CreateSpecificCulture("lv-LV")));                        
// Displays (8) Aug, augusts
```

```vb
Dim date1 As Date = #8/18/2008#
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays (8) Aug, August
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("nl-NL")))                        
' Displays (8) aug, augustus
Console.WriteLine(date1.ToString("(M) MMM, MMMM", _
                  CultureInfo.CreateSpecificCulture("lv-LV")))                        
' Displays (8) Aug, augusts 
```

## <a name="the-mm-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „MM“

Der benutzerdefinierte Formatbezeichner "MM" stellt den Monat als Zahl von 01 bis 12 dar (oder von 1 bis 13 für Kalender mit 13 Monaten). Einstellige Monate werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MM" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 1, 2, 6, 30, 15);

Console.WriteLine(date1.ToString("dd, MM", 
                  CultureInfo.InvariantCulture)); 
// 02, 01
```

```vb
Dim date1 As Date = #1/2/2008 6:30:15AM#

Console.WriteLine(date1.ToString("dd, MM", _
                  CultureInfo.InvariantCulture)) 
' 02, 01
```

## <a name="the-mmm-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „MMM“

Der benutzerdefinierte Formatbezeichner "MMM" stellt den abgekürzten Namen des Monats dar. Der lokalisierte abgekürzte Name des Monats wird aus der [DateTimeFormatInfo.AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MMM" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays ven. 29 août
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Fri 29 Aug
Console.WriteLine(date1.ToString("ddd d MMM", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays ven. 29 août
```

## <a name="the-mmmm-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „MMMM“

Der benutzerdefinierte Formatbezeichner "MMMM" stellt den vollständigen Namen des Monats dar. Der lokalisierte Name des Monats wird aus der [DateTimeFormatInfo.MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MMMM" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(2008, 8, 29, 19, 27, 15);

Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", 
                  CultureInfo.CreateSpecificCulture("it-IT")));
// Displays venerdì 29 agosto 
```

```vb
Dim date1 As Date = #08/29/2008 7:27:15PM#

Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Friday 29 August
Console.WriteLine(date1.ToString("dddd dd MMMM", _
                  CultureInfo.CreateSpecificCulture("it-IT")))
' Displays venerdì 29 agosto  
```

## <a name="the-s-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „s“

Der benutzerdefinierte Formatbezeichner "s" stellt die Sekunden als Zahl von 0 bis 59 dar. Das Ergebnis stellt ganze Sekunden dar, die seit der letzten Minute vergangen sind. Einstellige Sekunden werden ohne führende Null formatiert. 

Wenn der Formatbezeichner "s" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als s-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "s" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-ss-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ss“

Der benutzerdefinierte Formatbezeichner "ss" (plus einer beliebigem Anzahl zusätzlicher s-Bezeichner) stellt die Minute als Zahl von 00 bis 59 dar. Das Ergebnis stellt ganze Sekunden dar, die seit der letzten Minute vergangen sind. Einstellige Sekunden werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "ss" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-t-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „t“

Der benutzerdefinierte Formatbezeichner "t" stellt das erste Zeichen des AM/PM-Kennzeichners dar. Der entsprechende lokalisierte Kennzeichner wird aus der [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator)- oder der [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen. Der AM-Kennzeichner wird für alle Zeitangaben von 0:00:00 (Mitternacht) bis 11:59:59.999 verwendet. Der PM-Kennzeichner wird für alle Zeitangaben von 12:00:00 (Mittag) bis 23:59:59.999 verwendet. 

Wenn der Formatbezeichner "t" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als t-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "t" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1 µ                        
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.InvariantCulture));
// Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", 
                  CultureInfo.CreateSpecificCulture("el-GR")));
// Displays 6:9:1.5 µ
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1 µ                        
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.InvariantCulture))
' Displays 6:9:1.5 P
Console.WriteLine(date1.ToString("h:m:s.F t", _
                  CultureInfo.CreateSpecificCulture("el-GR")))
' Displays 6:9:1.5 µ
```

## <a name="the-tt-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „tt“

Der benutzerdefinierte Formatbezeichner "tt" (plus einer beliebigen Anzahl zusätzlicher t-Bezeichner) stellt den vollständigen AM/PM-Kennzeichner dar. Der entsprechende lokalisierte Kennzeichner wird aus der [DateTimeFormatInfo.AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator)- oder der [DateTimeFormatInfo.PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator)-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen. Der AM-Kennzeichner wird für alle Zeitangaben von 0:00:00 (Mitternacht) bis 11:59:59.999 verwendet. Der PM-Kennzeichner wird für alle Zeitangaben von 12:00:00 (Mittag) bis 23:59:59.999 verwendet.

Achten Sie darauf, dass Sie den Bezeichner "tt" für Sprachen verwenden, bei denen die Unterscheidung zwischen AM und PM beibehalten werden muss. Ein Beispiel hierfür ist die japanische Sprache, in der nicht das erste, sondern das zweite Zeichen des AM/PM-Bezeichners das Unterscheidungsmerkmal darstellt.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "tt" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1; 
date1 = new DateTime(2008, 1, 1, 18, 9, 1);
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01 du.
date1 = new DateTime(2008, 1, 1, 18, 9, 1, 500);
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.InvariantCulture));
// Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", 
                  CultureInfo.CreateSpecificCulture("hu-HU")));
// Displays 06:09:01.50 du.
```

```vb
Dim date1 As Date 
date1 = #6:09:01PM#
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01 du.
date1 = New Date(2008, 1, 1, 18, 9, 1, 500)
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.InvariantCulture))
' Displays 06:09:01.50 PM                        
Console.WriteLine(date1.ToString("hh:mm:ss.ff tt", _
                  CultureInfo.CreateSpecificCulture("hu-HU")))
' Displays 06:09:01.50 du.
```

## <a name="the-y-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „y“

Der benutzerdefinierte Formatbezeichner "y" stellt das Jahr als einstellige oder zweistellige Zahl dar. Falls das Jahr mehr als zwei Ziffern umfasst, werden im Ergebnis nur die beiden niedrigwertigen Ziffern angezeigt. Wenn die erste Ziffer eines zweistelligen Jahrs eine Null ist (z. B. 2008), wird die Zahl ohne führende Null formatiert. 

Wenn der Formatbezeichner "y" allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als y-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "y" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yy-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „yy“

Der benutzerdefinierte Formatbezeichner "yy" stellt das Jahr als zweistellige Zahl dar. Falls das Jahr mehr als zwei Ziffern umfasst, werden im Ergebnis nur die beiden niedrigwertigen Ziffern angezeigt. Umfasst das Jahr weniger als zwei signifikante Ziffern, wird die Zahl mit führenden Nullen auf eine zweistellige Jahresangabe aufgefüllt.

Bei einem Analysevorgang wird eine mit dem benutzerdefinierten Formatbezeichner „yy“ analysierte zweistellige Jahresangabe auf Grundlage der [Calendar.TwoDigitYearMax](xref:System.Globalization.Calendar.TwoDigitYearMax)-Eigenschaft des aktuellen Kalenders des Formatanbieters interpretiert. Im folgenden Beispiel wird die Zeichenfolgendarstellung eines Datums mit einer zweistelligen Jahresangabe anhand des standardmäßigen gregorianischen Kalenders der Kultur en-US analysiert, die in diesem Fall die aktuelle Kultur ist. Anschließend wird das [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt der aktuellen Kultur so geändert, dass ein [GregorianCalendar](xref:System.Globalization.GregorianCalendar)-Objekt verwendet wird, dessen [TwoDigitYearMax](xref:System.Globalization.GregorianCalendar.TwoDigitYearMax)-Eigenschaft geändert wurde.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fmt = "dd-MMM-yy";
      string value = "24-Jan-49";

      Calendar cal = (Calendar) CultureInfo.CurrentCulture.Calendar.Clone();
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
      Console.WriteLine();

      cal.TwoDigitYearMax = 2099;
      CultureInfo culture = (CultureInfo) CultureInfo.CurrentCulture.Clone();
      culture.DateTimeFormat.Calendar = cal;
      Thread.CurrentThread.CurrentCulture = culture;

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax);
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, null));
   }
}
// The example displays the following output:
//       Two Digit Year Range: 1930 - 2029
//       1/24/1949
//       
//       Two Digit Year Range: 2000 - 2099
//       1/24/2049
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fmt As String = "dd-MMM-yy"
      Dim value As String = "24-Jan-49"

      Dim cal As Calendar = CType(CultureInfo.CurrentCulture.Calendar.Clone(), Calendar)
      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)

      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
      Console.WriteLine()

      cal.TwoDigitYearMax = 2099
      Dim culture As CultureInfo = CType(CultureInfo.CurrentCulture.Clone(), CultureInfo)
      culture.DateTimeFormat.Calendar = cal
      Thread.CurrentThread.CurrentCulture = culture

      Console.WriteLine("Two Digit Year Range: {0} - {1}", 
                        cal.TwoDigitYearMax - 99, cal.TwoDigitYearMax)
      Console.WriteLine("{0:d}", DateTime.ParseExact(value, fmt, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Two Digit Year Range: 1930 - 2029
'       1/24/1949
'       
'       Two Digit Year Range: 2000 - 2099
'       1/24/2049
```

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yy" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyy-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „yyy“

Der benutzerdefinierte Formatbezeichner "yyy" stellt das Jahr mit mindestens drei Ziffern dar. Falls das Jahr mehr als drei signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge aufgenommen. Umfasst das Jahr weniger als drei Ziffern, wird die Zahl mit führenden Nullen auf eine dreistellige Jahresangabe aufgefüllt.

> [!NOTE]
> Für den buddhistischen Kalender Thailands, der fünfstellige Jahresangaben enthalten kann, zeigt dieser Bezeichner alle signifikanten Ziffern an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyy" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010      
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-yyyy-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „yyyy“

Der benutzerdefinierte Formatbezeichner "yyyy" stellt das Jahr mit mindestens vier Ziffern dar. Falls das Jahr mehr als vier signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge eingeschlossen. Umfasst das Jahr weniger als vier Ziffern, wird die Zahl mit führenden Nullen auf eine vierstellige Jahresangabe aufgefüllt.

> [!NOTE]
> Für den buddhistischen Kalender Thailands, der fünfstellige Jahresangaben enthalten kann, zeigt dieser Bezeichner alle signifikanten Ziffern an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyyy" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010
```

## <a name="the-yyyyy-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „yyyyy“

Der benutzerdefinierte Formatbezeichner "yyyyy" (plus einer beliebigen Anzahl zusätzlicher y-Bezeichner) stellt das Jahr mit mindestens fünf Ziffern dar. Falls das Jahr mehr als fünf signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge eingeschlossen. Umfasst das Jahr weniger als fünf Ziffern, wird die Zahl mit führenden Nullen auf eine fünfstellige Jahresangabe aufgefüllt.

Falls zusätzliche y-Bezeichner vorhanden sind, wird die Zahl mit der erforderlichen Anzahl an führenden Nullen auf die Anzahl der y-Bezeichner aufgefüllt. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyyyy" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = new DateTime(1, 12, 1);
DateTime date2 = new DateTime(2010, 1, 1);
Console.WriteLine(date1.ToString("%y"));
// Displays 1
Console.WriteLine(date1.ToString("yy"));
// Displays 01
Console.WriteLine(date1.ToString("yyy"));
// Displays 001
Console.WriteLine(date1.ToString("yyyy"));
// Displays 0001
Console.WriteLine(date1.ToString("yyyyy"));
// Displays 00001
Console.WriteLine(date2.ToString("%y"));
// Displays 10
Console.WriteLine(date2.ToString("yy"));
// Displays 10
Console.WriteLine(date2.ToString("yyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyy"));
// Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"));
// Displays 02010 
```

```vb
Dim date1 As Date = #12/1/0001#
Dim date2 As Date = #1/1/2010#
Console.WriteLine(date1.ToString("%y"))
' Displays 1
Console.WriteLine(date1.ToString("yy"))
' Displays 01
Console.WriteLine(date1.ToString("yyy"))
' Displays 001
Console.WriteLine(date1.ToString("yyyy"))
' Displays 0001
Console.WriteLine(date1.ToString("yyyyy"))
' Displays 00001
Console.WriteLine(date2.ToString("%y"))
' Displays 10
Console.WriteLine(date2.ToString("yy"))
' Displays 10
Console.WriteLine(date2.ToString("yyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyy"))
' Displays 2010      
Console.WriteLine(date2.ToString("yyyyy"))
' Displays 02010 
```

## <a name="the-z-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „z“

Mit [DateTime](xref:System.DateTime)-Werten stellt der benutzerdefinierte Formatbezeichner „z“ die vorzeichenbehaftete Abweichung der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden. Der Bezeichner reflektiert nicht den Wert der [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft einer Instanz. Aus diesem Grund wird der Formatbezeichner „z“ nicht zur Verwendung mit [DateTime](xref:System.DateTime)-Werten empfohlen.

Mit [DateTimeOffset](xref:System.DateTimeOffset)-Werten stellt dieser Formatbezeichner die Abweichung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts von der UTC in Stunden dar. 

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden ohne eine führende Null formatiert. 

Wenn der Formatbezeichner „z“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "z" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zz-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „zz“

Mit [DateTime](xref:System.DateTime)-Werten stellt der benutzerdefinierte Formatbezeichner „zz“ die vorzeichenbehaftete Abweichung der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden. Der Bezeichner reflektiert nicht den Wert der [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft einer Instanz. Aus diesem Grund wird der Formatbezeichner „zz“ nicht zur Verwendung mit [DateTime](xref:System.DateTime)-Werten empfohlen.

Mit [DateTimeOffset](xref:System.DateTimeOffset)-Werten stellt dieser Formatbezeichner die Abweichung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts von der UTC in Stunden dar.

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "zz" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the-zzz-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „zzz“

Mit [DateTime](xref:System.DateTime)-Werten stellt der benutzerdefinierte Formatbezeichner „zzz“ die vorzeichenbehaftete Abweichung der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden. Der Bezeichner reflektiert nicht den Wert der [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft einer Instanz. Aus diesem Grund wird der Formatbezeichner „zzz“ nicht zur Verwendung mit [DateTime](xref:System.DateTime)-Werten empfohlen.

Mit [DateTimeOffset](xref:System.DateTimeOffset)-Werten stellt dieser Formatbezeichner die Abweichung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts von der UTC in Stunden dar.

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden mit einer führenden Null formatiert. 

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "zzz" in eine benutzerdefinierte Formatzeichenfolge ein.

```csharp
DateTime date1 = DateTime.UtcNow;
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date1));
// Displays -7, -07, -07:00                     

DateTimeOffset date2 = new DateTimeOffset(2008, 8, 1, 0, 0, 0, 
                                          new TimeSpan(6, 0, 0));
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", 
                  date2));
// Displays +6, +06, +06:00
```

```vb
Dim date1 As Date = Date.UtcNow
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date1))
' Displays -7, -07, -07:00                     

Dim date2 As New DateTimeOffset(2008, 8, 1, 0, 0, 0, _
                                New Timespan(6, 0, 0))
Console.WriteLine(String.Format("{0:%z}, {0:zz}, {0:zzz}", _
                  date2))                                     
' Displays +6, +06, +06:00
```

## <a name="the--custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „:“

Der benutzerdefinierte Formatbezeichner ":" stellt das Trennzeichen für Zeitangaben dar, mit dem zwischen Stunden und Minuten unterschieden werden kann. 

Wenn der Formatbezeichner „:“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

## <a name="the--custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „/“

Der benutzerdefinierte Formatbezeichner "/" stellt das Datumstrennzeichen dar, mit dem zwischen Jahren, Monaten und Tagen unterschieden wird. 

Wenn der Formatbezeichner „/“ ohne weitere benutzerdefinierte Formatbezeichner verwendet wird, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und es wird eine [FormatException](xref:System.FormatException) ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#using-single-custom-format-specifiers) weiter unten in diesem Thema.

## <a name="character-literals"></a>Zeichenliterale

Die folgenden Zeichen in einer benutzerdefinierten Zeichenfolge für Datum und Uhrzeit sind reserviert und werden immer als Formatierungszeichen bzw. im Fall von ", ', / und \, als Sonderzeichen interpretiert. 

  |   |   |   |      
- | - | - | - | -
F | H | K | M | d
f | g | h | m | s
y | y | z | % | :
/ | " | ' | \ |
  |   |   |   |
  
Alle anderen Zeichen werden immer als Zeichenliterale interpretiert und bei einem Formatierungsvorgang unverändert in die Ergebniszeichenfolge übernommen. In einem Analysevorgang müssen die Zeichen exakt den Zeichen in der Eingabezeichenfolge entsprechen, beim Vergleich wird die Groß- und Kleinschreibung beachtet. 

Das folgende Beispiel enthält die Literalzeichen „PST“ (für Pacific Standard Time) und „PDT“ (für Pacific Daylight Time), um die lokale Zeitzone in einer Formatzeichenfolge darzustellen. Beachten Sie, dass die Zeichenfolge in der Ergebniszeichenfolge enthalten ist und dass eine Zeichenfolge, die die Zeichenfolge der lokalen Zeitzone enthält, ebenfalls erfolgreich analysiert wird. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String[] formats = { "dd MMM yyyy hh:mm tt PST", 
                           "dd MMM yyyy hh:mm tt PDT" };
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(formats[1]));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm PST";
      DateTime newDate;
      if (DateTime.TryParseExact(value, formats, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim formats() As String = { "dd MMM yyyy hh:mm tt PST", 
                                  "dd MMM yyyy hh:mm tt PDT" }
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(formats(1)))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm PST"
      Dim newDate As Date
      If Date.TryParseExact(value, formats, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM PDT
'       12/25/2016 12:00:00 PM
```

Es gibt zwei Möglichkeiten, um anzugeben, dass Zeichen nicht als reservierte Zeichen, sondern als Literalzeichen interpretiert werden sollen, damit sie in eine Ergebniszeichenfolge eingeschlossen oder in einer Eingabezeichenfolge erfolgreich analysiert werden können:

* Versehen Sie jedes reservierte Zeichen mit einem Escapezeichen. Weitere Informationen finden Sie unter [Verwenden des Escapezeichens](#using-the-escape-character). 
  
  Das folgende Beispiel enthält die Literalzeichen „pst“ (für Pacific Standard Time), um die lokale Zeitzone in einer Formatzeichenfolge darzustellen. Da „s“ und „t“ benutzerdefinierte Formatzeichenfolgen sind, müssen beide Zeichen mit Escapezeichen versehen werden, damit sie als Zeichenliterale interpretiert werden können. 
  
```csharp
using System;
using System.Globalization;

public class Example
{
  public static void Main()
  {
      String format = "dd MMM yyyy hh:mm tt p\\s\\t";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                  DateTimeStyles.None, out newDate)) 
          Console.WriteLine(newDate);
      else
          Console.WriteLine("Unable to parse '{0}'", value);
  }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt p\s\t" 
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```
  
* Schließen Sie die gesamte Literalzeichenfolge in Anführungszeichen oder Apostrophe ein. Das folgende Beispiel ist das gleiche wie das vorherige, außer dass „pst“ in Anführungszeichen eingeschlossen ist, um anzugeben, dass die gesamte Zeichenfolge als Zeichenliterale interpretiert werden soll. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      String format = "dd MMM yyyy hh:mm tt \"pst\"";
      var dat = new DateTime(2016, 8, 18, 16, 50, 0);
      // Display the result string. 
      Console.WriteLine(dat.ToString(format));

      // Parse a string. 
      String value = "25 Dec 2016 12:00 pm pst";
      DateTime newDate;
      if (DateTime.TryParseExact(value, format, null, 
                                 DateTimeStyles.None, out newDate)) 
         Console.WriteLine(newDate);
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       18 Aug 2016 04:50 PM PDT
//       12/25/2016 12:00:00 PM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim fmt As String = "dd MMM yyyy hh:mm tt ""pst"""  
      Dim dat As New Date(2016, 8, 18, 16, 50, 0)
      ' Display the result string. 
      Console.WriteLine(dat.ToString(fmt))

      ' Parse a string. 
      Dim value As String = "25 Dec 2016 12:00 pm pst"
      Dim newDate As Date
      If Date.TryParseExact(value, fmt, Nothing, 
                            DateTimeStyles.None, newDate) Then 
         Console.WriteLine(newDate)
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If                               
   End Sub
End Module
' The example displays the following output:
'       18 Aug 2016 04:50 PM pst
'       12/25/2016 12:00:00 PM
```

## <a name="notes"></a>Notizen


### <a name="using-single-custom-format-specifiers"></a>Verwenden von einzelnen benutzerdefinierten Formatbezeichnern

Eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit besteht aus zwei oder mehr Zeichen. Formatierungsmethoden für Datum und Uhrzeit interpretieren einzelne Zeichenfolgen als Standardformatzeichenfolgen für Datum und Uhrzeit. Wenn ein Zeichen nicht als gültiger Formatbezeichner erkannt wird, wird eine [FormatException](xref:System.FormatException) ausgelöst. Wenn die Formatzeichenfolge beispielsweise nur aus dem h-Bezeichner besteht, wird sie als Standardformatzeichenfolge für Datum und Uhrzeit interpretiert. In diesem speziellen Fall wird jedoch eine Ausnahme ausgelöst, weil kein Standardformatbezeichner „h“ für Datum und Uhrzeit vorhanden ist. 

Wenn Sie einen benutzerdefinierten Formatbezeichner für Datum und Uhrzeit als einzigen Bezeichner in einer Formatierungszeichenfolge verwenden möchten, d. h. wenn Sie den benutzerdefinierten Formatbezeichner "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" oder "/" ohne einen anderen Bezeichner verwenden möchten, müssen Sie ein Leerzeichen vor oder nach dem Bezeichner angeben, oder Sie stellen dem einzelnen benutzerdefinierten Bezeichner für Datum und Uhrzeit einen Prozentformatbezeichner (%) voran.

Beispielsweise wird „`%h`“ als benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit interpretiert, mit der die durch den aktuellen Datums- und Uhrzeitwert dargestellte Stunde angezeigt wird. Sie können auch die Formatzeichenfolge " h" oder "h " verwenden, obwohl dadurch ein Leerzeichen zusammen mit der Stunde in die Ergebniszeichenfolge eingeschlossen wird. Im folgenden Beispiel werden diese drei Formatzeichenfolgen veranschaulicht.


```csharp
DateTime dat1 = new DateTime(2009, 6, 15, 13, 45, 0);

Console.WriteLine("'{0:%h}'", dat1);
Console.WriteLine("'{0: h}'", dat1);
Console.WriteLine("'{0:h }'", dat1);
// The example displays the following output:
//       '1'
//       ' 1'
//       '1 '
```

```vb
Dim dat1 As Date = #6/15/2009 1:45PM#

Console.WriteLine("'{0:%h}'", dat1)
Console.WriteLine("'{0: h}'", dat1)
Console.WriteLine("'{0:h }'", dat1)
' The example displays the following output:
'       '1'
'       ' 1'
'       '1 '
```

### <a name="using-the-escape-character"></a>Verwenden des Escapezeichens

Die Zeichen "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" oder "/" in einer Formatzeichenfolge werden als benutzerdefinierte Formatbezeichner und nicht als Literalzeichen interpretiert. Um zu verhindern, dass ein Zeichen als Formatbezeichner interpretiert wird, können Sie dem Zeichen einen umgekehrten Schrägstrich (\) als Escapezeichen voranstellen. Das Escapezeichen gibt an, dass das folgende Zeichen ein Zeichenliteral ist, das unverändert in der Ergebniszeichenfolge enthalten sein soll.

Um einen umgekehrten Schrägstrich in eine Ergebniszeichenfolge einzuschließen, müssen Sie diesen mit einem weiteren umgekehrten Schrägstrich versehen, der als Escapezeichen dient (`\\`).

> [!NOTE]
> Einige Compiler, wie z.B. der C#-Compiler, interpretieren möglicherweise auch einen einzelnen umgekehrten Schrägstrich als Escapezeichen. Um sicherzustellen, dass eine Zeichenfolge bei der Formatierung ordnungsgemäß interpretiert wird, können Sie der Zeichenfolge das Literalzeichen für wörtliche Zeichenfolgen (@-Zeichen) voranstellen, oder Sie können jedem umgekehrten Schrägstrich einen weiteren umgekehrten Schrägstrich voranstellen. Beide Verfahren werden im folgenden C#-Codebeispiel veranschaulicht.

Im folgenden Beispiel wird das Escapezeichen verwendet, um zu verhindern, dass der Formatierungsvorgang die Zeichen "h" und "m" als Formatbezeichner interpretiert. 

```csharp
DateTime date = new DateTime(2009, 06, 15, 13, 45, 30, 90);
string fmt1 = "h \\h m \\m";
string fmt2 = @"h \h m \m";

Console.WriteLine("{0} ({1}) -> {2}", date, fmt1, date.ToString(fmt1));
Console.WriteLine("{0} ({1}) -> {2}", date, fmt2, date.ToString(fmt2));
// The example displays the following output:
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
//       6/15/2009 1:45:30 PM (h \h m \m) -> 1 h 45 m
```

```vb
Dim date1 As Date = #6/15/2009 13:45#
Dim fmt As String = "h \h m \m"

Console.WriteLine("{0} ({1}) -> {2}", date1, fmt, date1.ToString(fmt))
' The example displays the following output:
'       6/15/2009 1:45:00 PM (h \h m \m) -> 1 h 45 m 
```

### <a name="datetimeformatinfo-properties"></a>DateTimeFormatInfo-Eigenschaften

Die Formatierung wird durch die Eigenschaften des aktuellen [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den [IFormatProvider](xref:System.IFormatProvider)-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Für den [IFormatProvider](xref:System.IFormatProvider)-Parameter sollten Sie ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das eine Kultur darstellt, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt angeben. 

Die von vielen der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit erzeugte Ergebniszeichenfolge hängt auch von den Eigenschaften des aktuellen [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts ab. Die Anwendung kann das von einigen Standardformatbezeichnern für Datum und Uhrzeit erzeugte Ergebnis ändern, indem sie die entsprechende [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Eigenschaft ändert. So fügt beispielsweise der Formatbezeichner „ddd“ der Ergebniszeichenfolge einen abgekürzten Wochentagsnamen hinzu, der im [AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames)-Zeichenfolgenarray gefunden wird. Ebenso fügt der Formatbezeichner „MMMM“ der Ergebniszeichenfolge einen vollständigen Monatsnamen hinzu, der im [MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames)-Zeichenfolgenarray gefunden wird.

## <a name="see-also"></a>Siehe auch

[System.DateTime](xref:System.DateTime)

[System.IFormatProvider](xref:System.IFormatProvider)

[Formatierung von Typen](formatting-types.md)

[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md)


