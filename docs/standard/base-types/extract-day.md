---
title: 'Gewusst wie: Extrahieren des Wochentags aus einem bestimmten Datum'
description: Extrahieren des Wochentags aus einem bestimmten Datum
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 88a8f8b9-f5c9-4503-b968-84468b52bb8e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 1b9d1d497524e62e5758c9be7be7b586a421a258
ms.lasthandoff: 03/03/2017

---

# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a>Gewusst wie: Extrahieren des Wochentags aus einem bestimmten Datum

Mit .NET ist es einfach, den Wochentag für ein bestimmtes Datum zu ermitteln und den lokalisierten Namen eines Wochentags für ein bestimmtes Datum anzuzeigen. Ein Aufzählungswert, der den einem bestimmten Datum entsprechenden Wochentag anzeigt, ist über die Eigenschaften [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) oder [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) verfügbar. Dagegen ist das Abrufen des Namens eines Wochentags ein Formatierungsvorgang, der durch das Aufrufen einer Formatierungsmethode ausgeführt werden kann, wie z.B. der `ToString`-Methode eines Datums- und Uhrzeitwerts oder der [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode. In diesem Thema wird gezeigt, wie diese Formatierungsvorgänge ausgeführt werden.

## <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a>Extrahieren einer Zahl, die den Wochentag anzeigt, aus einem bestimmten Datum

1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie das Datum in einen [DateTime](xref:System.DateTime)- oder einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert, indem Sie die statischen Methoden [DateTime.Parse](xref:System.DateTime.Parse(System.String)) oder [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)) verwenden.

2. Verwenden Sie die [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek)- oder die [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek)-Eigenschaft, um einen [DayOfWeek](xref:System.DayOfWeek)-Wert abzurufen, der den Wochentag angibt.

3. Wandeln Sie den [DayOfWeek](xref:System.DayOfWeek)-Wert bei Bedarf in einen Ganzzahlwert um. 

Das folgende Beispiel zeigt eine Ganzzahl, die den Wochentag eines bestimmten Datums anzeigt. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      DateTime dateValue = new DateTime(2008, 6, 11);
      Console.WriteLine((int) dateValue.DayOfWeek);      
   }
}
// The example displays the following output:
//       3
```

```vb
Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.DayOfWeek)           
   End Sub
End Module
' The example displays the following output:
'    3
```

## <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a>Extrahieren des abgekürzten Wochentagsnamens aus einem bestimmten Datum

1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie das Datum in einen [DateTime](xref:System.DateTime)- oder einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert, indem Sie die statischen Methoden [DateTime.Parse](xref:System.DateTime.Parse(System.String)) oder [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)) verwenden.

2. Sie können den abgekürzten Wochentagsnamen der aktuellen Kultur oder einer bestimmten Kultur extrahieren:

    a. Um den abgekürzten Wochentagsnamen für die aktuelle Kultur zu extrahieren, rufen Sie die [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String)-Methode oder die [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String))-Instanzmethode des Datums- und Uhrzeitwerts auf, und übergeben Sie die Zeichenfolge „ddd“ als *format*-Parameter. Im folgenden Beispiel wird das Aufrufen der `ToString(String)`-Methode veranschaulicht.
    
```csharp
using System;

public class Example
{
   public static void Main()
   {
  DateTime dateValue = new DateTime(2008, 6, 11);
  Console.WriteLine(dateValue.ToString("ddd"));   
   }
}
// The example displays the following output:
//       Wed
```

```vb
Module Example
   Public Sub Main()
  Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("ddd"))    
   End Sub
End Module
' The example displays the following output:
'       Wed
```

    b. To extract the abbreviated weekday name for a specific culture, call the date and time value’s [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) instance method. Pass the string "ddd" as the *format* parameter. Pass either a [CultureInfo](xref:System.Globalization.CultureInfo) or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that represents the culture whose weekday name you want to retrieve as the *provider* parameter. The following code illustrates a call to the [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) method using a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the fr-FR culture.
    
```csharp
using System;
using System.Globalization;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("ddd", 
                            new CultureInfo("fr-FR")));    
    }
}
// The example displays the following output:
//       mer. 
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("ddd", 
                        New CultureInfo("fr-FR")))
   End Sub
End Module
' The example displays the following output:
'       mer.
```

## <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a>Extrahieren des vollen Wochentagsnamens aus einem bestimmten Datum

1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie das Datum in einen [DateTime](xref:System.DateTime)- oder einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert, indem Sie die statischen Methoden [DateTime.Parse](xref:System.DateTime.Parse(System.String)) oder [DateTimeOffset.Parse](xref:System.DateTimeOffset.Parse(System.String)) verwenden.

2. Sie können den abgekürzten Wochentagsnamen der aktuellen Kultur oder einer bestimmten Kultur extrahieren:

    a. Um den abgekürzten Wochentagsnamen für die aktuelle Kultur zu extrahieren, rufen Sie die [DateTime.ToString(String)](xref:System.DateTimeSystem.DateTime.ToString(System.String)-Methode oder die [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String))-Instanzmethode des Datums- und Uhrzeitwerts auf, und übergeben Sie die Zeichenfolge „dddd“ als *format*-Parameter. Im folgenden Beispiel wird das Aufrufen der `ToString(String)`-Methode veranschaulicht.

```csharp
using System;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd"));    
    }
}
// The example displays the following output:
//       Wednesday
```

```vb
Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("dddd"))
   End Sub
End Module
' The example displays the following output:
'       Wednesday
```

    b. To extract the weekday name for a specific culture, call the date and time value’s [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) instance method. Pass the string "dddd" as the *format* parameter. Pass either a [CultureInfo](xref:System.Globalization.CultureInfo) or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that represents the culture whose weekday name you want to retrieve as the *provider* parameter. The following code illustrates a call to the [ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) method using a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the es-ES  culture.

```csharp
using System;
using System.Globalization;

public class Example
{
    public static void Main()
    {
        DateTime dateValue = new DateTime(2008, 6, 11);
        Console.WriteLine(dateValue.ToString("dddd", 
                            new CultureInfo("es-ES")));    
    }
}
// The example displays the following output:
//       miércoles.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#
      Console.WriteLine(dateValue.ToString("dddd", _
                        New CultureInfo("es-ES"))) 
   End Sub
End Module
' The example displays the following output:
'       miércoles.
```

## <a name="example"></a>Beispiel

Das Beispiel veranschaulicht Aufrufe der Eigenschaften [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek) und [DateTimeOffset.DayOfWeek](xref:System.DateTimeOffset.DayOfWeek) sowie der Methoden „[DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)“ oder [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)), um die Zahl, die den Wochentag darstellt, sowie den abgekürzten und den vollständigen Wochentagsnamen für ein bestimmtes Datum abzurufen. 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string dateString = "6/11/2007";
      DateTime dateValue;
      DateTimeOffset dateOffsetValue;

      try
      {
         DateTimeFormatInfo dateTimeFormats;
         // Convert date representation to a date value
         dateValue = DateTime.Parse(dateString, CultureInfo.InvariantCulture);
         dateOffsetValue = new DateTimeOffset(dateValue, 
                                      TimeZoneInfo.Local.GetUtcOffset(dateValue));         

         // Convert date representation to a number indicating the day of week
         Console.WriteLine((int) dateValue.DayOfWeek);
         Console.WriteLine((int) dateOffsetValue.DayOfWeek);

         // Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"));
         Console.WriteLine(dateOffsetValue.ToString("ddd"));

         // Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"));
         Console.WriteLine(dateOffsetValue.ToString("dddd"));

         // Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("de-DE")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                     new CultureInfo("de-DE")));

         // Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("de-DE").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats));

         // Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", new CultureInfo("fr-FR")));
         Console.WriteLine(dateOffsetValue.ToString("ddd", 
                                                    new CultureInfo("fr-FR")));

         // Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = new CultureInfo("fr-FR").DateTimeFormat;
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats));
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats));
      }
      catch (FormatException)
      {
         Console.WriteLine("Unable to convert {0} to a date.", dateString);
      }
   }
}
// The example displays the following output:
//       1
//       1
//       Mon
//       Mon
//       Monday
//       Monday
//       Mo
//       Mo
//       Mo
//       Mo
//       lun.
//       lun.
//       lundi
//       lundi
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

Einzelne Sprachen verfügen möglicherweise über Funktionen, die die von .NET zur Verfügung gestellte Funktionalität duplizieren oder ergänzen. Visual Basic verfügt beispielsweise über zwei solcher Funktionen:

* `Weekday`, die eine Zahl zurückgibt, die den Wochentag eines bestimmten Datums anzeigt. Sie betrachtet den Ordinalwert des ersten Wochentags als eins, während die [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek)-Eigenschaft ihn als null betrachtet.

* `WeekdayName`, die den Namen des Wochentags in der aktuellen Kultur zurückgibt, der der Nummer eines bestimmten Wochentags entspricht.

Das folgende Beispiel veranschaulicht die Verwendung der `Weekday`- und `WeekdayName`-Funktionen in Visual Basic.

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim dateValue As Date = #6/11/2008#

      ' Get weekday number using Visual Basic Weekday function
      Console.WriteLine(Weekday(dateValue))                 ' Displays 4
      ' Compare with .NET DateTime.DayOfWeek property
      Console.WriteLine(dateValue.DayOfWeek)                ' Displays 3

      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))    ' Displays Wednesday

      ' Change culture to de-DE
      Dim originalCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
      Thread.CurrentThread.CurrentCulture = New CultureInfo("de-DE")
      ' Get weekday name using Weekday and WeekdayName functions
      Console.WriteLine(WeekdayName(Weekday(dateValue)))   ' Displays Donnerstag

      ' Restore original culture
      Thread.CurrentThread.CurrentCulture = originalCulture   
   End Sub
End Module
``` 

Sie können auch den von der [Datetime.DayOfWeek](xref:System.DateTime.DayOfWeek)-Eigenschaft zurückgegebenen Wert verwenden, um den Wochentagsnamen eines bestimmten Datums abzurufen. Dies erfordert lediglich einen Aufruf der [Enum.ToString](xref:System.Enum.ToString(System.String))-Methode für den von der Eigenschaft zurückgegebenen [DayOfWeek](xref:System.DayOfWeek)-Wert. Diese Vorgehensweise erzeugt jedoch nicht den lokalisierten Wochentagsnamen für die aktuelle Kultur, wie das folgende Beispiel zeigt. 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      // Change current culture to fr-FR
      CultureInfo originalCulture = Thread.CurrentThread.CurrentCulture;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("fr-FR");

      DateTime dateValue = new DateTime(2008, 6, 11);
      // Display the DayOfWeek string representation
      Console.WriteLine(dateValue.DayOfWeek.ToString());   
      // Restore original current culture
      Thread.CurrentThread.CurrentCulture = originalCulture;
   }
}
// The example displays the following output:
//       Wednesday
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dateString As String = "6/11/2007"
      Dim dateValue As Date
      Dim dateOffsetValue As DateTimeOffset

      Try
         Dim dateTimeFormats As DateTimeFormatInfo
         ' Convert date representation to a date value
         dateValue = Date.Parse(dateString, CultureInfo.InvariantCulture)
         dateOffsetValue = New DateTimeOffset(dateValue, _
                                     TimeZoneInfo.Local.GetUtcOffset(dateValue))            
         ' Convert date representation to a number indicating the day of week
         Console.WriteLine(dateValue.DayOfWeek)
         Console.WriteLine(dateOffsetValue.DayOfWeek)

         ' Display abbreviated weekday name using current culture
         Console.WriteLine(dateValue.ToString("ddd"))
         Console.WriteLine(dateOffsetValue.ToString("ddd"))

         ' Display full weekday name using current culture
         Console.WriteLine(dateValue.ToString("dddd"))
         Console.WriteLine(dateOffsetValue.ToString("dddd"))

         ' Display abbreviated weekday name for de-DE culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("de-DE")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("de-DE")))

         ' Display abbreviated weekday name with de-DE DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("de-DE").DateTimeFormat
         Console.WriteLine(dateValue.ToString("ddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("ddd", dateTimeFormats))

         ' Display full weekday name for fr-FR culture
         Console.WriteLine(dateValue.ToString("ddd", New CultureInfo("fr-FR")))
         Console.WriteLine(dateOffsetValue.ToString("ddd", _
                                                    New CultureInfo("fr-FR")))

         ' Display abbreviated weekday name with fr-FR DateTimeFormatInfo object
         dateTimeFormats = New CultureInfo("fr-FR").DateTimeFormat
         Console.WriteLine(dateValue.ToString("dddd", dateTimeFormats))
         Console.WriteLine(dateOffsetValue.ToString("dddd", dateTimeFormats))
      Catch e As FormatException
         Console.WriteLine("Unable to convert {0} to a date.", dateString)
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'       1
'       1
'       Mon
'       Mon
'       Monday
'       Monday
'       Mo
'       Mo
'       Mo
'       Mo
'       lun.
'       lun.
'       lundi
'       lundi
```

## <a name="see-also"></a>Siehe auch

[Durchführen von Formatierungsvorgängen](performing-formatting-operations.md)

[Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md)

[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md)
    

