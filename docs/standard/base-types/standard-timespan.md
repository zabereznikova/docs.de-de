---
title: "Standardmäßige TimeSpan-Formatzeichenfolgen"
description: "Standardmäßige TimeSpan-Formatzeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 4e0f02f1-4abd-47b5-8995-5c3ff45b0ce1
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: bb209c7bac71960fa0a679e546bedae486b412b8

---

# <a name="standard-timespan-format-strings"></a>Standardmäßige TimeSpan-Formatzeichenfolgen

Eine standardmäßige [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolge verwendet einen einzelnen Formatbezeichner, um die Textdarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts zu definieren, der sich aus einem Formatierungsvorgang ergibt. Jede Formatzeichenfolge, die mehr als ein Zeichen (einschließlich Leerzeichen) enthält, wird als benutzerdefinierte [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolge interpretiert. Weitere Informationen finden Sie unter [Benutzerdefinierte TimeSpan-Formatzeichenfolgen](custom-timespan.md).

Die Zeichenfolgendarstellungen von [TimeSpan](xref:System.TimeSpan)-Werten werden durch Aufrufe der Überladungen der [TimeSpan.ToString](xref:System.TimeSpan.ToString)-Methode und durch Methoden, die die zusammengesetzte Formatierung unterstützen (z.B. [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))), erzeugt. Weitere Informationen finden Sie unter [Formatieren von Typen](formatting-types.md) und [Zusammengesetzte Formatierung](composite-format.md). Das folgende Beispiel veranschaulicht die Verwendung von standardmäßigen Formatzeichenfolgen bei Formatierungsvorgängen.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan duration = new TimeSpan(1, 12, 23, 62);
      string output = "Time of Travel: " + duration.ToString("c");
      Console.WriteLine(output);

      Console.WriteLine("Time of Travel: {0:c}", duration); 
   }
}
// The example displays the following output:
//       Time of Travel: 1.12:24:02
//       Time of Travel: 1.12:24:02
```

```vb
Module Example
   Public Sub Main()
      Dim duration As New TimeSpan(1, 12, 23, 62)
      Dim output As String = "Time of Travel: " + duration.ToString("c")
      Console.WriteLine(output)

      Console.WriteLine("Time of Travel: {0:c}", duration) 
   End Sub
End Module
' The example displays the following output:
'       Time of Travel: 1.12:24:02
'       Time of Travel: 1.12:24:02
```

Standardmäßige [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolgen werden auch von der [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider))-Methode und der [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@))-Methode verwendet, um das erforderliche Format von Eingabezeichenfolgen für Analysevorgänge zu definieren. (Beim Analysieren wird die Zeichenfolgendarstellung eines Werts in diesen Wert konvertiert.) Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen bei Analysevorgängen.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value = "1.03:14:56.1667";
      TimeSpan interval;
      try {
         interval = TimeSpan.ParseExact(value, "c", null);
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      }   
      catch (FormatException) {
         Console.WriteLine("{0}: Bad Format", value);
      }   
      catch (OverflowException) {
         Console.WriteLine("{0}: Out of Range", value);
      }

      if (TimeSpan.TryParseExact(value, "c", null, out interval))
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value);
   }
}
// The example displays the following output:
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

```vb
Module Example
   Public Sub Main()
      Dim value As String = "1.03:14:56.1667"
      Dim interval As TimeSpan
      Try
         interval = TimeSpan.ParseExact(value, "c", Nothing)
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Catch e As FormatException
         Console.WriteLine("{0}: Bad Format", value)
      Catch e As OverflowException
         Console.WriteLine("{0}: Out of Range", value)
      End Try

      If TimeSpan.TryParseExact(value, "c", Nothing, interval) Then
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value)
      End If                
   End Sub
End Module
' The example displays the following output:
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

Die folgende Tabelle enthält die Standardzeitintervall-Formatbezeichner.

Formatbezeichner | Name | Beschreibung | Beispiele
---------------- | ---- | ----------- | --------
"c" | Konstantenformat (unveränderlich) | Dieser Bezeichner ist nicht kulturabhängig. Er hat das Format [-][d’.’]hh’:’mm’:’ss[‘.’fffffff]. (Die "t"- und "T"-Formatzeichenfolgen erzeugen die gleichen Ergebnisse.) | `TimeSpan.Zero -> 00:00:00`; `New TimeSpan(0, 0, 30, 0) -> 00:30:00`; `New TimeSpan(3, 17, 25, 30, 500) -> 3.17:25:30.5000000`
"g" | Allgemeines kurzes Format | Dieser Bezeichner gibt nur aus, was benötigt wird. Er ist kulturabhängig und hat das Format [-][d’:’]h’:’mm’:’ss[.FFFFFFF]. | `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50.5 (en-US)`; `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50,5 (fr-FR)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50.599 (en-US)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50,599 (fr-FR)`
"G" | Allgemeines Langformat | Dieser Bezeichner gibt immer Tage und sieben Dezimalstellen aus. Er ist kulturabhängig und hat das Format [-]d’:’hh’:’mm’:’ss.fffffff. | `New TimeSpan(18, 30, 0) -> 0:18:30:00.0000000 (en-US)`; `New TimeSpan(18, 30, 0) -> 0:18:30:00,0000000 (fr-FR)` 

## <a name="the-constant-c-format-specifier"></a>Der Konstantenformatbezeichner "c"

Der Formatbezeichner „c“ gibt die Zeichenfolgendarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts im folgenden Format an:

[-][_d_.]_hh_:_mm_:_ss_[._fffffff_]

Elemente in eckigen Klammern ([ und ]) sind optional. Der Punkt (.) und der Doppelpunkt (:) sind Literalsymbole. In der folgenden Tabelle werden die restlichen Elemente beschrieben. 

Element | Beschreibung
------- | -----------
- | Ein optionales negatives Vorzeichen, das ein negatives Zeitintervall angibt.
*d* | Die optionale Anzahl von Tagen ohne führende Nullen.
*hh* | Die Anzahl von Stunden zwischen "00" und "23".
*mm* | Die Anzahl von Minuten zwischen "00" und "59".
*ss* | Die Anzahl von Sekunden zwischen "0" und "59".
*fffffff* | Der optionale Bruchteil einer Sekunde. Der Wert kann zwischen „0000001“ (ein Tick oder ein Zehnmillionstel einer Sekunde) und „9999999“ (9.999.999 Zehnmillionstel einer Sekunde oder eine Sekunde minus ein Tick) liegen. 

Anders als die Formatbezeichner "G" und "g" ist der Formatbezeichner "c" nicht kulturabhängig. Er erzeugt die Zeichenfolgendarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts, der unveränderlich ist und für alle früheren Versionen von .NET Framework vor .NET Framework 4 verwendet wird. „c“ ist die standardmäßige [TimeSpan](xref:System.TimeSpan)-Formatzeichenfolge. Die [TimeSpan.ToString](xref:System.TimeSpan.ToString)-Methode formatiert einen Zeitintervallwert mit der Formatzeichenfolge „c“.

> [!NOTE]
> [TimeSpan](xref:System.TimeSpan) unterstützt auch die standardmäßigen Formatzeichenfolgen „t“- und „T“, die im Verhalten identisch mit der standardmäßigen Formatzeichenfolge „c“ sind.

Im folgenden Beispiel werden zwei [TimeSpan](xref:System.TimeSpan)-Objekte instanziiert, zum Ausführen arithmetischer Vorgänge verwendet, und das Ergebnis wird angezeigt. In jedem Fall wird die zusammengesetzte Formatierung verwendet, um den [TimeSpan](xref:System.TimeSpan)-Wert mithilfe des Formatbezeichners „c“ anzuzeigen.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);

      interval1 = new TimeSpan(0, 0, 1, 14, 365);
      interval2 = TimeSpan.FromTicks(2143756);  
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       07:45:16 - 18:12:38 = -10:27:22
//       07:45:16 + 18:12:38 = 1.01:57:54
//       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

```vb
Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)

      interval1 = New TimeSpan(0, 0, 1, 14, 365)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       07:45:16 - 18:12:38 = -10:27:22
'       07:45:16 + 18:12:38 = 1.01:57:54
'       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

## <a name="the-general-short-g-format-specifier"></a>Der allgemeine Kurzformatbezeichner "g"

Der [TimeSpan](xref:System.TimeSpan)-Formatbezeichner „g“ gibt die Zeichenfolgendarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts in einem kompakten Format an, indem nur die erforderlichen Elemente eingeschlossen werden. Er hat das folgende Format:

[-][_d_:]_h_:_mm_:_ss_[._FFFFFFF_]

Elemente in eckigen Klammern ([ und ]) sind optional. Der Doppelpunkt (:) ist ein Literalsymbol. In der folgenden Tabelle werden die restlichen Elemente beschrieben.

Element | Beschreibung
------- | -----------
- | Ein optionales negatives Vorzeichen, das ein negatives Zeitintervall angibt.
*d* | Die optionale Anzahl von Tagen ohne führende Nullen.
*hh* | Die Anzahl von Stunden zwischen "0" und "23" ohne führende Nullen. 
*mm* | Die Anzahl von Minuten zwischen "00" und "59".
*ss* | Die Anzahl von Sekunden zwischen "0" und "59".
. | Das Trennzeichen für Sekundenbruchteile.
*FFFFFFF* | Die Sekundenbruchteile. Es werden so wenig Ziffern wie möglich angezeigt.

Der Formatbezeichner "g" ist wie der Formatbezeichner "G" lokalisiert. Das Trennzeichen für Sekundenbruchteile basiert auf der aktuellen Kultur.

Im folgenden Beispiel werden zwei [TimeSpan](xref:System.TimeSpan)-Objekte instanziiert, zum Ausführen arithmetischer Vorgänge verwendet, und das Ergebnis wird angezeigt. In jedem Fall wird die zusammengesetzte Formatierung zum Anzeigen des [TimeSpan](xref:System.TimeSpan)-Werts mit dem Formatbezeichner „g“ verwendet. Darüber hinaus wird der [TimeSpan](xref:System.TimeSpan)-Wert unter Verwendung der Formatierungskonventionen der aktuellen Systemkultur formatiert (in diesem Fall Englisch - USA oder en-US) und der Kultur Französisch - Frankreich (fr-FR).

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       7:45:16 - 18:12:38 = -10:27:22
//       7:45:16 + 18:12:38 = 1:1:57:54
//       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       7:45:16 - 18:12:38 = -10:27:22
'       7:45:16 + 18:12:38 = 1:1:57:54
'       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

## <a name="the-general-long-g-format-specifier"></a>Der allgemeine Langformatbezeichner "G"

Der [TimeSpan](xref:System.TimeSpan)-Formatbezeichner „G“ gibt die Zeichenfolgendarstellung eines [TimeSpan](xref:System.TimeSpan)-Werts in einem Langformat zurück, das immer Tage und Sekundenbruchteile enthält. Die Zeichenfolge, die sich aus dem Standardformatbezeichner "G" ergibt, hat folgendes Format:

[-]*d*:*hh*:*mm*:*ss*.*fffffff*

Elemente in eckigen Klammern ([ und ]) sind optional. Der Doppelpunkt (:) ist ein Literalsymbol. In der folgenden Tabelle werden die restlichen Elemente beschrieben.

Element | Beschreibung
------- | -----------
- | Ein optionales negatives Vorzeichen, das ein negatives Zeitintervall angibt.
*d* | Die optionale Anzahl von Tagen ohne führende Nullen.
*hh* | Die Anzahl von Stunden zwischen „0“ und „23“. 
*mm* | Die Anzahl von Minuten zwischen "00" und "59".
*ss* | Die Anzahl von Sekunden zwischen "0" und "59".
. | Das Trennzeichen für Sekundenbruchteile.
*fffffff* | Die Sekundenbruchteile.

Der Formatbezeichner "g" ist wie der Formatbezeichner "G" lokalisiert. Das Trennzeichen für Sekundenbruchteile basiert auf der aktuellen Kultur.

Im folgenden Beispiel werden zwei [TimeSpan](xref:System.TimeSpan)-Objekte instanziiert, zum Ausführen arithmetischer Vorgänge verwendet, und das Ergebnis wird angezeigt. In jedem Fall wird die zusammengesetzte Formatierung zum Anzeigen des [TimeSpan](xref:System.TimeSpan)-Werts mit dem Formatbezeichner „G“ verwendet. Darüber hinaus wird der [TimeSpan](xref:System.TimeSpan)-Wert unter Verwendung der Formatierungskonventionen der aktuellen Systemkultur formatiert (in diesem Fall Englisch - USA oder en-US) und der Kultur Französisch - Frankreich (fr-FR). 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
//       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
//       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
'       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
'       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

## <a name="see-also"></a>Siehe auch

[Formatierung von Typen](formatting-types.md)

[Kombinierte Formatierung](composite-format.md)

[Analysieren von Zeichenfolgen](parsing-strings.md)




<!--HONumber=Nov16_HO3-->


