---
title: Benutzerdefinierte TimeSpan-Formatzeichenfolgen
description: Benutzerdefinierte TimeSpan-Formatzeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e79745eb-6ebd-4e62-85c4-4f2830c27285
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bec60437d4345decaf38f2bbb9434922ac889683
ms.lasthandoff: 03/03/2017

---

# <a name="custom-timespan-format-strings"></a>Benutzerdefinierte TimeSpan-Formatzeichenfolgen

Eine [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolge definiert die aus einem Formatierungsvorgang resultierende Zeichenfolgendarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts. Eine benutzerdefinierte Formatzeichenfolge besteht aus einem oder mehreren benutzerdefinierten [TimeSpan](xref:System.TimeSpan)-Formatbezeichnern und einer beliebigen Anzahl von Literalzeichen. Alle Zeichenfolgen, bei denen es sich nicht um [standardmäßige TimeSpan](standard-timespan.md)-Formatzeichenfolgen handelt, werden als benutzerdefinierte [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolgen interpretiert.

> [!IMPORTANT]
> Die benutzerdefinierten [TimeSpan](xref:System.TimeSpan)-Formatbezeichner enthalten keine Platzhalter für Trennzeichensymbole wie z.B. diejenigen, durch die Tage von Stunden, Stunden von Minuten oder Sekunden von Sekundenbruchteilen getrennt werden. Diese Symbole müssen stattdessen als Zeichenfolgenliterale in die benutzerdefinierte Formatzeichenfolge eingeschlossen werden. Beispielsweise definiert `"dd\.hh\:mm"` einen Punkt (.) als Trennzeichen zwischen Tagen und Stunden und einen Doppelpunkt (:) als Trennzeichen zwischen Stunden und Minuten. 

> Benutzerdefinierte [TimeSpan](xref:System.TimeSpan)-Formatbezeichner enthalten auch kein Vorzeichensymbol, das Ihnen ermöglicht, zwischen den negativen und positiven Zeitintervallen zu unterscheiden. Um ein Vorzeichensymbol hinzuzufügen, müssen Sie eine Formatzeichenfolge mit bedingter Logik erstellen. Der Abschnitt [Andere Zeichen](#other-characters) enthält ein Beispiel. 

Die Zeichenfolgendarstellungen von [TimeSpan](xref:System.TimeSpan)-Werten werden durch Aufrufe der Überladungen der [TimeSpan](xref:System.TimeSpan) `ToString`-Methode und durch Methoden, die die zusammengesetzte Formatierung unterstützen (z.B. [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))), erzeugt. Weitere Informationen finden Sie unter [Formatieren von Typen](formatting-types.md) und [Zusammengesetzte Formatierung](composite-format.md). Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen bei Formatierungsvorgängen.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan duration = new TimeSpan(1, 12, 23, 62);

      string output = null;
      output = "Time of Travel: " + duration.ToString("%d") + " days";
      Console.WriteLine(output);
      output = "Time of Travel: " + duration.ToString(xref:"dd\.hh\:mm\:ss"); 
      Console.WriteLine(output);

      Console.WriteLine("Time of Travel: {0:%d} day(s)", duration);
      Console.WriteLine("Time of Travel: {0:dd\\.hh\\:mm\\:ss} days", duration);
   }
}
// The example displays the following output:
//       Time of Travel: 1 days
//       Time of Travel: 01.12:24:02
//       Time of Travel: 1 day(s)
//       Time of Travel: 01.12:24:02 days
```

```vb
Module Example
   Public Sub Main()
      Dim duration As New TimeSpan(1, 12, 23, 62)

      Dim output As String = Nothing
      output = "Time of Travel: " + duration.ToString("%d") + " days"
      Console.WriteLine(output)
      output = "Time of Travel: " + duration.ToString("dd\.hh\:mm\:ss") 
      Console.WriteLine(output)

      Console.WriteLine("Time of Travel: {0:%d} day(s)", duration)
      Console.WriteLine("Time of Travel: {0:dd\.hh\:mm\:ss} days", duration)
   End Sub
End Module
' The example displays the following output:
'       Time of Travel: 1 days
'       Time of Travel: 01.12:24:02
'       Time of Travel: 1 day(s)
'       Time of Travel: 01.12:24:02 days
```

Benutzerdefinierte [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolgen werden auch von der [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode und der [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode verwendet, um das erforderliche Format von Eingabezeichenfolgen für Analysevorgänge zu definieren. (Beim Analysieren wird die Zeichenfolgendarstellung eines Werts in diesen Wert konvertiert.) Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen bei Analysevorgängen.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value = null;
      TimeSpan interval;

      value = "6";
      if (TimeSpan.TryParseExact(value, "%d", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);

      value = "16:32.05";
      if (TimeSpan.TryParseExact(value, @"mm\:ss\.ff", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);

      value= "12.035";
      if (TimeSpan.TryParseExact(value, "ss\\.fff", null, out interval))
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"));
      else
         Console.WriteLine("Unable to parse '{0}'", value);
   }
}
// The example displays the following output:
//       6 --> 6.00:00:00
//       16:32.05 --> 00:16:32.0500000
//       12.035 --> 00:00:12.0350000
```

```vb
Module Example
   Public Sub Main()
      Dim value As String = Nothing
      Dim interval As TimeSpan

      value = "6"
      If TimeSpan.TryParseExact(value, "%d", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If

      value = "16:32.05"
      If TimeSpan.TryParseExact(value, "mm\:ss\.ff", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If

      value= "12.035"
      If TimeSpan.TryParseExact(value, "ss\.fff", Nothing, interval) Then
         Console.WriteLine("{0} --> {1}", value, interval.ToString("c"))
      Else
         Console.WriteLine("Unable to parse '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       6 --> 6.00:00:00
'       16:32.05 --> 00:16:32.0500000
'       12.035 --> 00:00:12.0350000
```

In der folgenden Tabelle werden die benutzerdefinierten Formatbezeichner für Datum und Uhrzeit beschrieben.

Formatbezeichner | Beschreibung | Beispiele
---------------- | ----------- | --------
"d", "%d" | Die Anzahl ganzer Tage im Zeitintervall. | `new TimeSpan(6, 14, 32, 17, 685):` `%d --> "6"`;  `d\.hh\:mm --> "6.14:32"`
„dd“, „dddddddd“ | Die Anzahl ganzer Tage im Zeitintervall, bei Bedarf mit führenden Nullen aufgefüllt. | `new TimeSpan(6, 14, 32, 17, 685):` `ddd --> "006"`; `dd\.hh\:mm --> "06.14:32"`
"h", "%h" | Die Anzahl ganzer Stunden im Zeitintervall, die nicht als Teil von Tagen gezählt werden. Einstellige Stundenangaben weisen keine führende&0; auf. | `new TimeSpan(6, 14, 32, 17, 685):` `%h --> "14"`; `hh\:mm --> "14:32"`
"hh" | Die Anzahl ganzer Stunden im Zeitintervall, die nicht als Teil von Tagen gezählt werden. Einstellige Stundenangaben weisen eine führende&0; auf. | `new TimeSpan(6, 14, 32, 17, 685):` `hh --> "14"`  `new TimeSpan(6, 8, 32, 17, 685):` `hh --> 08`
"m", "%m" | Die Anzahl ganzer Minuten im Zeitintervall, die nicht als Teil von Stunden oder Tagen gezählt werden. Einstellige Minutenangaben weisen keine führende&0; auf. | `new TimeSpan(6, 14, 8, 17, 685):` `%m --> "8"`; `h\:m --> "14:8"`
"mm" | Die Anzahl ganzer Minuten im Zeitintervall, die nicht als Teil von Stunden oder Tagen gezählt werden. Einstellige Minutenangaben weisen eine führende&0; auf. | `new TimeSpan(6, 14, 8, 17, 685):` `mm --> "08"` `new TimeSpan(6, 8, 5, 17, 685):` `d\.hh\:mm\:ss --> 6.08:05:17`
"s", "%s" | Die Anzahl ganzer Sekunden im Zeitintervall, die nicht als Teil von Stunden, Tagen oder Minuten gezählt werden. Einstellige Sekundenangaben weisen keine führende&0; auf. | `TimeSpan.FromSeconds(12.965):` `%s --> 12`; `s\.fff --> 12.965`
"ss" | Die Anzahl ganzer Sekunden im Zeitintervall, die nicht als Teil von Stunden, Tagen oder Minuten gezählt werden. Einstellige Sekundenangaben weisen eine führende&0; auf. | `TimeSpan.FromSeconds(6.965):` `ss --> 06`; `ss\.fff --> 06.965`
"f", "%f" | Die Zehntelsekunden in einem Zeitintervall. | `TimeSpan.FromSeconds(6.895):` `f --> 8`; `ss\.f --> 06.8`
"ff" | Die Hundertstelsekunden in einem Zeitintervall. | `TimeSpan.FromSeconds(6.895):` `ff --> 89`; `ss\.ff --> 06.89`
"fff" | Die Millisekunden in einem Zeitintervall. | `TimeSpan.FromSeconds(6.895):` `fff --> 895`; `ss\.fff --> 06.895`
"ffff" | Die Zehntausendstelsekunden in einem Zeitintervall. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 8954`; `ss\.ffff --> 06.8954`
"fffff" | Die Hunderttausendstelsekunden in einem Zeitintervall. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 89543`; `ss\.ffff --> 06.89543`
"ffffff" | Die Millionstelsekunden in einem Zeitintervall. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 895432`; `ss\.ffff --> 06.895432`
"fffffff" | Die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall. | `TimeSpan.Parse("0:0:6.8954321"):` `ffff --> 8954321`; `ss\.ffff --> 06.8954321`
"F", "%F" | Die Zehntelsekunden in einem Zeitintervall. Es wird nichts angezeigt, wenn die Ziffer&0; (null) ist. | `TimeSpan.Parse("00:00:06.32"):` `%F: 3`  `TimeSpan.Parse("0:0:3.091"):` `ss\.F: 03.`
"FF" | Die Hundertstelsekunden in einem Zeitintervall. Nachkommanullen oder zwei Nullstellen nach dem Komma werden nicht eingeschlossen. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 32`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFF" | Die Millisekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 329`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFF" | Die Zehntausendstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen. |  `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 3291`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFF" | Die Hunderttausendstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 32917`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFFF" | Die Millionstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht angezeigt. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 329179`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.1`
"FFFFFFF" | Die Zehnmillionstelsekunden in einem Zeitintervall. Nachkommanullen oder sieben Nullstellen werden nicht angezeigt. | `TimeSpan.Parse("00:00:06.3291791"):` `FFFFFF: 3291791`  `TimeSpan.Parse("0:0:3.1900000"):` `ss\.FFFFFF: 03.19`
'string' | Zeichenfolgenliteraltrennzeichen | `new TimeSpan(14, 32, 17):` `hh':'mm':'ss --> "14:32:17"`
\ | Das Escapezeichen. | `new TimeSpan(14, 32, 17):` `hh\:mm\:ss --> "14:32:17"`
Jedes andere Zeichen | Alle anderen Zeichen ohne Escapezeichen werden als benutzerdefinierte Formatbezeichner interpretiert. | `new TimeSpan(14, 32, 17):` `hh\:mm\:ss --> "14:32:17"`

## <a name="the-d-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „d“

Der benutzerdefinierte Formatbezeichner „d“ gibt den Wert der [TimeSpan.Days](xref:System.TimeSpan.Days)-Eigenschaft aus, der die Anzahl ganzer Tage im Zeitintervall darstellt. Er gibt auch dann die volle Anzahl von Tagen in einem [TimeSpan](xref:System.TimeSpan)-Wert aus, wenn der Wert aus mehreren Ziffern besteht. Wenn der Wert der [TimeSpan.Days](xref:System.TimeSpan.Days)-Eigenschaft&0; (null) ist, gibt der Bezeichner „0“ aus.

Wenn der benutzerdefinierte Formatbezeichner "d" allein verwendet wird, geben Sie "%d" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
TimeSpan ts1 = new TimeSpan(16, 4, 3, 17, 250);
Console.WriteLine(ts1.ToString("%d"));
// Displays 16
```

```vb
Dim ts As New TimeSpan(16, 4, 3, 17, 250)
Console.WriteLine(ts.ToString("%d"))
' Displays 16 
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "d".

```csharp
TimeSpan ts2 = new TimeSpan(4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.hh\:mm\:ss"));

TimeSpan ts3 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts3.ToString(xref:"d\.hh\:mm\:ss"));
// The example displays the following output:
//       0.04:03:17
//       3.04:03:17
```

```vb
Dim ts2 As New TimeSpan(4, 3, 17)
Console.WriteLine(ts2.ToString("d\.hh\:mm\:ss"))

Dim ts3 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts3.ToString("d\.hh\:mm\:ss"))
' The example displays the following output:
'       0.04:03:17
'       3.04:03:17
```

## <a name="the-dd-dddddddd-custom-format-specifiers"></a>Benutzerdefinierte Formatbezeichner „dd“ bis „dddddddd“

Die benutzerdefinierten Formatbezeichner „dd“, „ddd“, „dddd“, „ddddd“, „dddddd“, „ddddddd“ und „dddddddd“ geben den Wert der [TimeSpan.Days](xref:System.TimeSpan.Days)-Eigenschaft aus, der die Anzahl ganzer Tage im Zeitintervall darstellt. 

Die Ausgabezeichenfolge enthält eine Mindestanzahl von Ziffern, die durch die Anzahl der "d"-Zeichen im Formatbezeichner angegeben wird, und wird bei Bedarf mit führenden Nullen aufgefüllt. Wenn die Ziffern in der Anzahl von Tagen die Anzahl der "d"-Zeichen im Formatbezeichner überschreiten, wird die volle Anzahl von Tagen in der Ergebniszeichenfolge ausgegeben.

Im folgenden Beispiel werden diese Formatbezeichner verwendet, um die Zeichenfolgendarstellung von zwei [TimeSpan](xref:System.TimeSpan)-Werten anzuzeigen. Der Wert der Tageskomponente des ersten Zeitintervalls ist 0 (null), der Wert der Tageskomponente des zweiten Zeitintervalls 365.

```csharp
TimeSpan ts1 = new TimeSpan(0, 23, 17, 47);
TimeSpan ts2 = new TimeSpan(365, 21, 19, 45);

for (int ctr = 2; ctr <= 8; ctr++)
{
   string fmt = new String('d', ctr) + @"\.hh\:mm\:ss";
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts1);  
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts2);
   Console.WriteLine();
}  
// The example displays the following output:
//       dd\.hh\:mm\:ss --> 00.23:17:47
//       dd\.hh\:mm\:ss --> 365.21:19:45
//       
//       ddd\.hh\:mm\:ss --> 000.23:17:47
//       ddd\.hh\:mm\:ss --> 365.21:19:45
//       
//       dddd\.hh\:mm\:ss --> 0000.23:17:47
//       dddd\.hh\:mm\:ss --> 0365.21:19:45
//       
//       ddddd\.hh\:mm\:ss --> 00000.23:17:47
//       ddddd\.hh\:mm\:ss --> 00365.21:19:45
//       
//       dddddd\.hh\:mm\:ss --> 000000.23:17:47
//       dddddd\.hh\:mm\:ss --> 000365.21:19:45
//       
//       ddddddd\.hh\:mm\:ss --> 0000000.23:17:47
//       ddddddd\.hh\:mm\:ss --> 0000365.21:19:45
//       
//       dddddddd\.hh\:mm\:ss --> 00000000.23:17:47
//       dddddddd\.hh\:mm\:ss --> 00000365.21:19:45
```

```vb
Dim ts1 As New TimeSpan(0, 23, 17, 47)
Dim ts2 As New TimeSpan(365, 21, 19, 45)

For ctr As Integer = 2 To 8
   Dim fmt As String = New String("d"c, ctr) + "\.hh\:mm\:ss"
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts1) 
   Console.WriteLine("{0} --> {1:" + fmt + "}", fmt, ts2)
   Console.WriteLine()
Next  
' The example displays the following output:
'       dd\.hh\:mm\:ss --> 00.23:17:47
'       dd\.hh\:mm\:ss --> 365.21:19:45
'       
'       ddd\.hh\:mm\:ss --> 000.23:17:47
'       ddd\.hh\:mm\:ss --> 365.21:19:45
'       
'       dddd\.hh\:mm\:ss --> 0000.23:17:47
'       dddd\.hh\:mm\:ss --> 0365.21:19:45
'       
'       ddddd\.hh\:mm\:ss --> 00000.23:17:47
'       ddddd\.hh\:mm\:ss --> 00365.21:19:45
'       
'       dddddd\.hh\:mm\:ss --> 000000.23:17:47
'       dddddd\.hh\:mm\:ss --> 000365.21:19:45
'       
'       ddddddd\.hh\:mm\:ss --> 0000000.23:17:47
'       ddddddd\.hh\:mm\:ss --> 0000365.21:19:45
'       
'       dddddddd\.hh\:mm\:ss --> 00000000.23:17:47
'       dddddddd\.hh\:mm\:ss --> 00000365.21:19:45
```

## <a name="the-h-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „h“

Der benutzerdefinierte Formatbezeichner „h“ gibt den Wert der [TimeSpan.Hours](xref:System.TimeSpan.Hours)-Eigenschaft aus, der die Anzahl ganzer Stunden im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der [TimeSpan.Hours](xref:System.TimeSpan.Hours)-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der [TimeSpan.Hours](xref:System.TimeSpan.Hours)-Eigenschaft zwischen 10 und 23 liegt.

Wenn der benutzerdefinierte Formatbezeichner "h" allein verwendet wird, geben Sie "%h" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
TimeSpan ts = new TimeSpan(3, 42, 0);
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts);
// The example displays the following output:
//       3 hours 42 minutes
```

```vb
Dim ts As New TimeSpan(3, 42, 0)
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts)
' The example displays the following output:
'       3 hours 42 minutes
```

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%h" verwenden, wenn die numerische Zeichenfolge als Anzahl von Stunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string value = "8";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%h", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       08:00:00
```

```vb
Dim value As String = "8"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%h", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       08:00:00
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "h".

```csharp
TimeSpan ts1 = new TimeSpan(14, 3, 17);
Console.WriteLine(ts1.ToString(xref:"d\.h\:mm\:ss"));

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.h\:mm\:ss"));
// The example displays the following output:
//       0.14:03:17
//       3.4:03:17
```

```vb
Dim ts1 As New TimeSpan(14, 3, 17)
Console.WriteLine(ts1.ToString("d\.h\:mm\:ss"))

Dim ts2 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts2.ToString("d\.h\:mm\:ss"))
' The example displays the following output:
'       0.14:03:17
'       3.4:03:17
```

## <a name="the-hh-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „hh“

Der benutzerdefinierte Formatbezeichner „hh“ gibt den Wert der [TimeSpan.Hours](xref:System.TimeSpan.Hours)-Eigenschaft aus, der die Anzahl ganzer Stunden im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null. 

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "hh" verwenden, wenn die numerische Zeichenfolge als Anzahl von Stunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string value = "08";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "hh", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       08:00:00 
```

```vb
Dim value As String = "08"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "hh", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       08:00:00
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "hh".

```csharp
TimeSpan ts1 = new TimeSpan(14, 3, 17);
Console.WriteLine(ts1.ToString(xref:"d\.hh\:mm\:ss"));

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine(ts2.ToString(xref:"d\.hh\:mm\:ss"));
// The example displays the following output:
//       0.14:03:17
//       3.04:03:17
```

```vb
Dim ts1 As New TimeSpan(14, 3, 17)
Console.WriteLine(ts1.ToString("d\.hh\:mm\:ss"))

Dim ts2 As New TimeSpan(3, 4, 3, 17)
Console.WriteLine(ts2.ToString("d\.hh\:mm\:ss"))
' The example displays the following output:
'       0.14:03:17
'       3.04:03:17
```

## <a name="the-m-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „m“

Der benutzerdefinierte Formatbezeichner „m“ gibt den Wert der [TimeSpan.Minutes](xref:System.TimeSpan.Minutes)-Eigenschaft aus, der die Anzahl ganzer Minuten im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der [TimeSpan.Minutes](xref:System.TimeSpan.Minutes)-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der [TimeSpan.Minutes](xref:System.TimeSpan.Minutes)-Eigenschaft zwischen 10 und 59 liegt.

Wenn der benutzerdefinierte Formatbezeichner "m" allein verwendet wird, geben Sie "%m" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
TimeSpan ts = new TimeSpan(3, 42, 0);
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts);
// The example displays the following output:
//       3 hours 42 minutes
```

```vb
Dim ts As New TimeSpan(3, 42, 0)
Console.WriteLine("{0:%h} hours {0:%m} minutes", ts)
' The example displays the following output:
'       3 hours 42 minutes
```

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%m" verwenden, wenn die numerische Zeichenfolge als Anzahl von Minuten interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string value = "3";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%m", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:03:00
```

```vb
Dim value As String = "3"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%m", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:03:00                              
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "m".

```csharp
TimeSpan ts1 = new TimeSpan(0, 6, 32);
Console.WriteLine("{0:m\\:ss} minutes", ts1);

TimeSpan ts2 = new TimeSpan(3, 4, 3, 17);
Console.WriteLine("Elapsed time: {0:m\\:ss}", ts2);
// The example displays the following output:
//       6:32 minutes
//       Elapsed time: 18:44
```

```vb
Dim ts1 As New TimeSpan(0, 6, 32)
Console.WriteLine("{0:m\:ss} minutes", ts1)

Dim ts2 As New TimeSpan(0, 18, 44)
Console.WriteLine("Elapsed time: {0:m\:ss}", ts2)
' The example displays the following output:
'       6:32 minutes
'       Elapsed time: 18:44
```

## <a name="the-mm-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „mm“

Der benutzerdefinierte Formatbezeichner „mm“ gibt den Wert der [TimeSpan.Minutes](xref:System.TimeSpan.Minutes)-Eigenschaft aus, der die Anzahl ganzer Minuten im Zeitintervall darstellt, die nicht als Teil der Stunden- oder Tageskomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null. 

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "mm" verwenden, wenn die numerische Zeichenfolge als Anzahl von Minuten interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string value = "07";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "mm", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:07:00
```

```vb
Dim value As String = "05"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "mm", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:05:00
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "mm".

```csharp
TimeSpan departTime = new TimeSpan(11, 12, 00);
TimeSpan arriveTime = new TimeSpan(16, 28, 00);
Console.WriteLine("Travel time: {0:hh\\:mm}", 
                  arriveTime - departTime);
// The example displays the following output:
//       Travel time: 05:16
```

```vb
Dim departTime As New TimeSpan(11, 12, 00)
Dim arriveTime As New TimeSpan(16, 28, 00)
Console.WriteLine("Travel time: {0:hh\:mm}", 
                  arriveTime - departTime)
' The example displays the following output:
'       Travel time: 05:16
```

## <a name="the-s-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „s“

Der benutzerdefinierte Formatbezeichner „s“ gibt den Wert der [TimeSpan.Seconds](xref:System.TimeSpan.Seconds)-Eigenschaft aus, der die Anzahl ganzer Sekunden im Zeitintervall darstellt, die nicht als Teil der Stunden-, Tages- oder Minutenkomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der [TimeSpan.Seconds](xref:System.TimeSpan.Seconds)-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der [TimeSpan.Seconds](xref:System.TimeSpan.Seconds)-Eigenschaft zwischen 10 und 59 liegt. 

Wenn der benutzerdefinierte Formatbezeichner "s" allein verwendet wird, geben Sie "%s" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
TimeSpan ts = TimeSpan.FromSeconds(12.465);
Console.WriteLine(ts.ToString("%s"));
// The example displays the following output:
//       12
```

```vb
Dim ts As TimeSpan = TimeSpan.FromSeconds(12.465)
Console.WriteLine(ts.ToString("%s"))
' The example displays the following output:
'       12
```

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%s" verwenden, wenn die numerische Zeichenfolge als Anzahl von Sekunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string value = "9";
TimeSpan interval;
if (TimeSpan.TryParseExact(value, "%s", null, out interval))
   Console.WriteLine(interval.ToString("c"));
else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value);   
// The example displays the following output:
//       00:00:09
```

```vb
Dim value As String = "9"
Dim interval As TimeSpan
If TimeSpan.TryParseExact(value, "%s", Nothing, interval) Then
   Console.WriteLine(interval.ToString("c"))
Else
   Console.WriteLine("Unable to convert '{0}' to a time interval", 
                     value)   
End If   
' The example displays the following output:
'       00:00:09
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "s".

```csharp
TimeSpan startTime = new TimeSpan(0, 12, 30, 15, 0);
TimeSpan endTime = new TimeSpan(0, 12, 30, 21, 3);
Console.WriteLine(xref:"Elapsed Time: {0:s\:fff} seconds", 
                  endTime - startTime);
// The example displays the following output:
//       Elapsed Time: 6:003 seconds      
```

```vb
Dim startTime As New TimeSpan(0, 12, 30, 15, 0)
Dim endTime As New TimeSpan(0, 12, 30, 21, 3)
Console.WriteLine("Elapsed Time: {0:s\:fff} seconds", 
                  endTime - startTime)
' The example displays the following output:
'       Elapsed Time: 6:003 seconds
```

## <a name="the-ss-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ss“

Der benutzerdefinierte Formatbezeichner „ss“ gibt den Wert der [TimeSpan.Seconds](xref:System.TimeSpan.Seconds)-Eigenschaft aus, der die Anzahl ganzer Sekunden im Zeitintervall darstellt, die nicht als Teil der Stunden-, Tages- oder Minutenkomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null. 

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "ss" verwenden, wenn die numerische Zeichenfolge als Anzahl von Sekunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

```csharp
string[] values = { "49", "9", "06" };
TimeSpan interval;
foreach (string value in values)
{
   if (TimeSpan.TryParseExact(value, "ss", null, out interval))
      Console.WriteLine(interval.ToString("c"));
   else
      Console.WriteLine("Unable to convert '{0}' to a time interval", 
                        value);   
}
// The example displays the following output:
//       00:00:49
//       Unable to convert '9' to a time interval
//       00:00:06
```

```vb
Dim values() As String = { "49", "9", "06" }
Dim interval As TimeSpan
For Each value As String In values
   If TimeSpan.TryParseExact(value, "ss", Nothing, interval) Then
      Console.WriteLine(interval.ToString("c"))
   Else
      Console.WriteLine("Unable to convert '{0}' to a time interval", 
                        value)   
   End If   
Next   
' The example displays the following output:
'       00:00:49
'       Unable to convert '9' to a time interval
'       00:00:06
```

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "ss".

```csharp
TimeSpan interval1 = TimeSpan.FromSeconds(12.60);
Console.WriteLine(interval1.ToString(xref:"ss\.fff"));

TimeSpan interval2 = TimeSpan.FromSeconds(6.485);
Console.WriteLine(interval2.ToString(xref:"ss\.fff"));
// The example displays the following output:
//       12.600
//       06.485
```

```vb
Dim interval1 As TimeSpan = TimeSpan.FromSeconds(12.60)
Console.WriteLine(interval1.ToString("ss\.fff"))
Dim interval2 As TimeSpan = TimeSpan.FromSeconds(6.485)
Console.WriteLine(interval2.ToString("ss\.fff"))
' The example displays the following output:
'       12.600
'       06.485
```

## <a name="the-f-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „f“

Der benutzerdefinierte Formatbezeichner "f" gibt die Zehntelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau eine Dezimalstelle enthalten. 

Wenn der benutzerdefinierte Formatbezeichner "f" allein verwendet wird, geben Sie "%f" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „f“ verwendet, um die Zehntelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. „f“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ff“

Der benutzerdefinierte Formatbezeichner "ff" gibt die Hundertstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau zwei Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „ff“ verwendet, um die Hundertstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. „ff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „fff“

Der benutzerdefinierte Formatbezeichner "fff" (mit drei "f"-Zeichen) gibt die Millisekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau drei Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „fff“ verwendet, um die Millisekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. „fff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ffff“
Der benutzerdefinierte Formatbezeichner "ffff" (mit vier "f"-Zeichen) gibt die Zehntausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau vier Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „ffff“ verwendet, um die Zehntausendstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. „ffff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „fffff“
Der benutzerdefinierte Formatbezeichner "fffff" (mit fünf "f"-Zeichen) gibt die Hunderttausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau fünf Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „fffff“ verwendet, um die Hunderttausendstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. „fffff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-ffffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „ffffff“

Der benutzerdefinierte Formatbezeichner "ffffff" (mit sechs "f"-Zeichen) gibt die Millionstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau sechs Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „ffffff“ verwendet, um die Millionstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Er wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner "s" kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-fffffff-custom-format-specifier"></a>Benutzerdefinierte Formatbezeichner „fffffff“

Der benutzerdefinierte Formatbezeichner "fffffff" (mit sieben "f"-Zeichen) gibt die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall aus. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, muss die Eingabezeichenfolge genau sieben Dezimalstellen enthalten. 

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „fffffff“ verwendet, um die Sekundenbruchteile in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Er wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner "s" kombiniert.

```csharp
TimeSpan ts = new TimeSpan(1003498765432);
string fmt;
Console.WriteLine(ts.ToString("c"));
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   if (fmt.Length == 1) fmt = "%" + fmt;
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts);
} 
Console.WriteLine();

for (int ctr = 1; ctr <= 7; ctr++) {
   fmt = new String('f', ctr);
   Console.WriteLine("{0,10}: {1:s\\." + fmt + "}", "s\\." + fmt, ts);
}
// The example displays the following output:
//               %f: 8
//               ff: 87
//              fff: 876
//             ffff: 8765
//            fffff: 87654
//           ffffff: 876543
//          fffffff: 8765432
//       
//              s\.f: 29.8
//             s\.ff: 29.87
//            s\.fff: 29.876
//           s\.ffff: 29.8765
//          s\.fffff: 29.87654
//         s\.ffffff: 29.876543
//        s\.fffffff: 29.8765432 
```

```vb
Dim ts As New TimeSpan(1003498765432)
Dim fmt As String
Console.WriteLine(ts.ToString("c"))
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   If fmt.Length = 1 Then fmt = "%" + fmt
   Console.WriteLine("{0,10}: {1:" + fmt + "}", fmt, ts)
Next 
Console.WriteLine()

For ctr = 1 To 7
   fmt = New String("f"c, ctr)
   Console.WriteLine("{0,10}: {1:s\." + fmt + "}", "s\." + fmt, ts)
Next
' The example displays the following output:
'            %f: 8
'            ff: 87
'           fff: 876
'          ffff: 8765
'         fffff: 87654
'        ffffff: 876543
'       fffffff: 8765432
'    
'           s\.f: 29.8
'          s\.ff: 29.87
'         s\.fff: 29.876
'        s\.ffff: 29.8765
'       s\.fffff: 29.87654
'      s\.ffffff: 29.876543
'     s\.fffffff: 29.8765432
```

## <a name="the-f-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „F“

Der benutzerdefinierte Formatbezeichner "F" gibt die Zehntelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn der Wert der Zehntelsekunden des Zeitintervalls&0; (null) ist, wird er nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Zehntelsekundenstelle optional.

Wenn der benutzerdefinierte Formatbezeichner "F" allein verwendet wird, geben Sie "%F" an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „F“ verwendet, um die Zehntelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.669");
Console.WriteLine("{0} ('%F') --> {0:%F}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.091");
Console.WriteLine("{0} ('ss\\.F') --> {0:ss\\.F}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.1", "0:0:03.12" };
string fmt = @"h\:m\:ss\.F";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                        
// The example displays the following output:
//       Formatting:
//       00:00:03.6690000 ('%F') --> 6
//       00:00:03.0910000 ('ss\.F') --> 03.
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.F') --> 00:00:03
//       0:0:03.1 ('h\:m\:ss\.F') --> 00:00:03.1000000
//       Cannot parse 0:0:03.12 with 'h\:m\:ss\.F'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.669")
Console.WriteLine("{0} ('%F') --> {0:%F}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.091")
Console.WriteLine("{0} ('ss\.F') --> {0:ss\.F}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.1", "0:0:03.12" }
Dim fmt As String = "h\:m\:ss\.F"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6690000 ('%F') --> 6
'       00:00:03.0910000 ('ss\.F') --> 03.
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.F') --> 00:00:03
'       0:0:03.1 ('h\:m\:ss\.F') --> 00:00:03.1000000
'       Cannot parse 0:0:03.12 with 'h\:m\:ss\.F'.
```

## <a name="the-ff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FF“

Der benutzerdefinierte Formatbezeichner "FF" gibt die Hundertstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Stellen für Zehntel- und Hundertstelsekunden optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FF“ verwendet, um die Hundertstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.697");
Console.WriteLine("{0} ('FF') --> {0:FF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.809");
Console.WriteLine("{0} ('ss\\.FF') --> {0:ss\\.FF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.1", "0:0:03.127" };
string fmt = @"h\:m\:ss\.FF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6970000 ('FF') --> 69
//       00:00:03.8090000 ('ss\.FF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FF') --> 00:00:03
//       0:0:03.1 ('h\:m\:ss\.FF') --> 00:00:03.1000000
//       Cannot parse 0:0:03.127 with 'h\:m\:ss\.FF'. 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.697")
Console.WriteLine("{0} ('FF') --> {0:FF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.809")
Console.WriteLine("{0} ('ss\.FF') --> {0:ss\.FF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.1", "0:0:03.127" }
Dim fmt As String = "h\:m\:ss\.FF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6970000 ('FF') --> 69
'       00:00:03.8090000 ('ss\.FF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FF') --> 00:00:03
'       0:0:03.1 ('h\:m\:ss\.FF') --> 00:00:03.1000000
'       Cannot parse 0:0:03.127 with 'h\:m\:ss\.FF'.
```

## <a name="the-fff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFF“

Der benutzerdefinierte Formatbezeichner "FFF" (mit drei "F"-Zeichen) gibt die Millisekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Stellen für Zehntel-, Hundertstel- und Tausendstelsekunden optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FFF“ verwendet, um die Tausendstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974");
Console.WriteLine("{0} ('FFF') --> {0:FFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.8009");
Console.WriteLine("{0} ('ss\\.FFF') --> {0:ss\\.FFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279" };
string fmt = @"h\:m\:ss\.FFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6974000 ('FFF') --> 697
//       00:00:03.8009000 ('ss\.FFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.1279 with 'h\:m\:ss\.FFF'.  
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974")
Console.WriteLine("{0} ('FFF') --> {0:FFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.8009")
Console.WriteLine("{0} ('ss\.FFF') --> {0:ss\.FFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279" }
Dim fmt As String = "h\:m\:ss\.FFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974000 ('FFF') --> 697
'       00:00:03.8009000 ('ss\.FFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.1279 with 'h\:m\:ss\.FFF'.
```

## <a name="the-ffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFF“

Der benutzerdefinierte Formatbezeichner "FFFF" (mit vier "F"-Zeichen) gibt die Zehntausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Stellen für Zehntel-, Hundertstel-, Tausendstel- und Zehntausendstelsekunden optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FFFF“ verwendet, um die Zehntausendstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Der benutzerdefinierte Formatbezeichner "FFFF" wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.69749");
Console.WriteLine("{0} ('FFFF') --> {0:FFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.80009");
Console.WriteLine("{0} ('ss\\.FFFF') --> {0:ss\\.FFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.12795" };
string fmt = @"h\:m\:ss\.FFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//       Formatting:
//       00:00:03.6974900 ('FFFF') --> 6974
//       00:00:03.8000900 ('ss\.FFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.12795 with 'h\:m\:ss\.FFFF'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.69749")
Console.WriteLine("{0} ('FFFF') --> {0:FFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.80009")
Console.WriteLine("{0} ('ss\.FFFF') --> {0:ss\.FFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.12795" }
Dim fmt As String = "h\:m\:ss\.FFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974900 ('FFFF') --> 6974
'       00:00:03.8000900 ('ss\.FFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.12795 with 'h\:m\:ss\.FFFF'.
```

## <a name="the-fffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFF" (mit fünf "F"-Zeichen) gibt die Hunderttausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Stellen für Zehntel-, Hundertstel-, Tausendstel-, Zehntausendstel- und Hunderttausendstelsekunden optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FFFFF“ verwendet, um die Hunderttausendstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Der benutzerdefinierte Formatbezeichner "FFFFF" wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.697497");
Console.WriteLine("{0} ('FFFFF') --> {0:FFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.800009");
Console.WriteLine("{0} ('ss\\.FFFFF') --> {0:ss\\.FFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.127956" };
string fmt = @"h\:m\:ss\.FFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                       
// The example displays the following output:
//       Formatting:
//       00:00:03.6974970 ('FFFFF') --> 69749
//       00:00:03.8000090 ('ss\.FFFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.127956 with 'h\:m\:ss\.FFFF'. 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.697497")
Console.WriteLine("{0} ('FFFFF') --> {0:FFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.800009")
Console.WriteLine("{0} ('ss\.FFFFF') --> {0:ss\.FFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.127956" }
Dim fmt As String = "h\:m\:ss\.FFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974970 ('FFFFF') --> 69749
'       00:00:03.8000090 ('ss\.FFFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.127956 with 'h\:m\:ss\.FFFF'.
```

## <a name="the-ffffff-custom-format-specifier"></a>Der benutzerdefinierte Formatbezeichner „FFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFF" (mit sechs "F"-Zeichen) gibt die Millionstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein der Stellen für Zehntel-, Hundertstel-, Tausendstel-, Zehntausendstel-, Hunderttausendstel- und Millionstelsekunden optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FFFFFF“ verwendet, um die Millionstelsekunden in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974974");
Console.WriteLine("{0} ('FFFFFF') --> {0:FFFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.8000009");
Console.WriteLine("{0} ('ss\\.FFFFFF') --> {0:ss\\.FFFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" };
string fmt = @"h\:m\:ss\.FFFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}                       
// The example displays the following output:
//       Formatting:
//       00:00:03.6974974 ('FFFFFF') --> 697497
//       00:00:03.8000009 ('ss\.FFFFFF') --> 03.8
//       
//       Parsing:
//       0:0:03. ('h\:m\:ss\.FFFFFF') --> 00:00:03
//       0:0:03.12 ('h\:m\:ss\.FFFFFF') --> 00:00:03.1200000
//       Cannot parse 0:0:03.1279569 with 'h\:m\:ss\.FFFFFF'.
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974974")
Console.WriteLine("{0} ('FFFFFF') --> {0:FFFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.8000009")
Console.WriteLine("{0} ('ss\.FFFFFF') --> {0:ss\.FFFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" }
Dim fmt As String = "h\:m\:ss\.FFFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'       Formatting:
'       00:00:03.6974974 ('FFFFFF') --> 697497
'       00:00:03.8000009 ('ss\.FFFFFF') --> 03.8
'       
'       Parsing:
'       0:0:03. ('h\:m\:ss\.FFFFFF') --> 00:00:03
'       0:0:03.12 ('h\:m\:ss\.FFFFFF') --> 00:00:03.1200000
'       Cannot parse 0:0:03.1279569 with 'h\:m\:ss\.FFFFFF'
```

## <a name="the-fffffff-custom-format-specifier"></a>Benutzerdefinierte Formatbezeichner „FFFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFFF" (mit sieben "F"-Zeichen) gibt die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall aus. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode oder die [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode aufgerufen wird, ist das Vorhandensein von sieben Dezimalstellen in der Eingabezeichenfolge optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner „FFFFFFF“ verwendet, um die Sekundenbruchteile in einem [TimeSpan](xref:System.TimeSpan)-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

```csharp
Console.WriteLine("Formatting:");
TimeSpan ts1 = TimeSpan.Parse("0:0:3.6974974");
Console.WriteLine("{0} ('FFFFFFF') --> {0:FFFFFFF}", ts1);

TimeSpan ts2 = TimeSpan.Parse("0:0:3.9500000");
Console.WriteLine("{0} ('ss\\.FFFFFFF') --> {0:ss\\.FFFFFFF}", ts2);
Console.WriteLine();

Console.WriteLine("Parsing:");
string[] inputs = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" };
string fmt = @"h\:m\:ss\.FFFFFFF";
TimeSpan ts3;

foreach (string input in inputs) {
   if (TimeSpan.TryParseExact(input, fmt, null, out ts3))
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3);
   else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt);
}
// The example displays the following output:
//    Formatting:
//    00:00:03.6974974 ('FFFFFFF') --> 6974974
//    00:00:03.9500000 ('ss\.FFFFFFF') --> 03.95
//    
//    Parsing:
//    0:0:03. ('h\:m\:ss\.FFFFFFF') --> 00:00:03
//    0:0:03.12 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1200000
//    0:0:03.1279569 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1279569 
```

```vb
Console.WriteLine("Formatting:")
Dim ts1 As TimeSpan = TimeSpan.Parse("0:0:3.6974974")
Console.WriteLine("{0} ('FFFFFFF') --> {0:FFFFFFF}", ts1)

Dim ts2 As TimeSpan = TimeSpan.Parse("0:0:3.9500000")
Console.WriteLine("{0} ('ss\.FFFFFFF') --> {0:ss\.FFFFFFF}", ts2)
Console.WriteLine()

Console.WriteLine("Parsing:")
Dim inputs() As String = { "0:0:03.", "0:0:03.12", "0:0:03.1279569" }
Dim fmt As String = "h\:m\:ss\.FFFFFFF"
Dim ts3 As TimeSpan

For Each input As String In inputs
   If TimeSpan.TryParseExact(input, fmt, Nothing, ts3)
      Console.WriteLine("{0} ('{1}') --> {2}", input, fmt, ts3)
   Else
      Console.WriteLine("Cannot parse {0} with '{1}'.", 
                        input, fmt)
   End If  
Next
' The example displays the following output:
'    Formatting:
'    00:00:03.6974974 ('FFFFFFF') --> 6974974
'    00:00:03.9500000 ('ss\.FFFFFFF') --> 03.95
'    
'    Parsing:
'    0:0:03. ('h\:m\:ss\.FFFFFFF') --> 00:00:03
'    0:0:03.12 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1200000
'    0:0:03.1279569 ('h\:m\:ss\.FFFFFFF') --> 00:00:03.1279569  
```

## <a name="other-characters"></a>Andere Zeichen

Alle anderen Zeichen ohne Escapezeichen in einer Formatzeichenfolge (einschließlich Leerzeichen) werden als benutzerdefinierte Formatbezeichner interpretiert. In den meisten Fällen führt das Vorhandensein eines anderen Zeichens ohne Escapezeichen zu einer [FormatException](xref:System.FormatException). 

Zum Einschließen von Literalzeichen in eine Formatzeichenfolge stehen zwei Methoden zur Verfügung:

* Schließen Sie das Literalzeichen in einfache Anführungszeichen ein (Trennzeichen für Literalzeichenfolgen). 

* Stellen Sie dem Literalzeichen einen umgekehrten Schrägstrich ("\") voran, der als Escapezeichen interpretiert wird. In C# muss die Formatzeichenfolge folglich @-quoted entsprechen, oder dem Literalzeichen muss ein zusätzlicher umgekehrter Schrägstrich vorangestellt werden.

  In einigen Fällen müssen Sie möglicherweise bedingte Logik verwenden, um ein Literal mit Escapezeichen einer Formatzeichenfolge hinzuzufügen. Im folgenden Beispiel wird bedingte Logik verwendet, um ein Vorzeichensymbol für negative Zeitintervalle hinzuzufügen. 
  
```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan result = new DateTime(2010, 01, 01) - DateTime.Now; 
      String fmt = (result < TimeSpan.Zero ?  "\\-" : "") + "dd\\.hh\\:mm";

      Console.WriteLine(result.ToString(fmt));
      Console.WriteLine("Interval: {0:" + fmt + "}", result);
   }
}
// The example displays output like the following:
//       -1291.10:54
//       Interval: -1291.10:54
```

```vb
Module Example
   Public Sub Main()
      Dim result As TimeSpan = New DateTime(2010, 01, 01) - Date.Now 
      Dim fmt As String = If(result < TimeSpan.Zero, "\-", "") + "dd\.hh\:mm"

      Console.WriteLine(result.ToString(fmt))
      Console.WriteLine("Interval: {0:" + fmt + "}", result)
   End Sub
End Module
' The example displays output like the following:
'       -1291.10:54
'       Interval: -1291.10:54
```
  
.NET definiert keine Grammatik für Trennzeichen in Zeitintervallen. Dies bedeutet, dass die Trennzeichen zwischen Tagen und Stunden, Stunden und Minuten, Minuten und Sekunden und Sekunden und Sekundenbruchteilen in einer Formatzeichenfolge als Zeichenliterale behandelt werden müssen.

Im folgenden Beispiel werden sowohl das Escapezeichen als auch einfache Anführungszeichen verwendet, um eine benutzerdefinierte Formatzeichenfolge mit dem Wort "Minuten" in der Ausgabezeichenfolge zu definieren. 

```csharp
TimeSpan interval = new TimeSpan(0, 32, 45);
// Escape literal characters in a format string.
string fmt = @"mm\:ss\ \m\i\n\u\t\e\s";
Console.WriteLine(interval.ToString(fmt));
// Delimit literal characters in a format string with the ' symbol.
fmt = "mm':'ss' minutes'";      
Console.WriteLine(interval.ToString(fmt));
// The example displays the following output: 
//       32:45 minutes      
//       32:45 minutes
```

```vb
Dim interval As New TimeSpan(0, 32, 45)
' Escape literal characters in a format string.
Dim fmt As String = "mm\:ss\ \m\i\n\u\t\e\s"
Console.WriteLine(interval.ToString(fmt))
' Delimit literal characters in a format string with the ' symbol.
fmt = "mm':'ss' minutes'"
Console.WriteLine(interval.ToString(fmt))
' The example displays the following output: 
'       32:45 minutes      
'       32:45 minutes
```

## <a name="see-also"></a>Siehe auch

[Formatierung von Typen](formatting-types.md)

[TimeSpan-Standardformatzeichenfolgen](standard-timespan.md)  


