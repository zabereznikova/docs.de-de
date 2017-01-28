---
title: "Durchführen arithmetischer Datums- und Uhrzeitoperationen"
description: "Durchführen arithmetischer Datums- und Uhrzeitoperationen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: bb5cda188b6970c23e41faf82990034c3cf144ab

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Durchführen arithmetischer Datums- und Uhrzeitoperationen

Auch wenn sowohl die [System.DateTime](xref:System.DateTime)- als auch die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur Member bieten, die arithmetische Operationen für ihre Werte durchführen, sind die Ergebnisse der arithmetischen Operationen sehr verschieden. In diesem Artikel werden diese Unterschiede untersucht und mit dem Grad der Unterstützung von Zeitzonen bei Datums- und Zeitdaten in Zusammenhang gebracht. Zudem wird erläutert, wie Operationen mit Datums- und Uhrzeitdaten unter vollständiger Berücksichtigung der Zeitzone durchgeführt werden.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Vergleiche und arithmetische Operationen mit DateTime-Werten

[System.DateTime](xref:System.DateTime)-Werte bieten eine eingeschränkte Unterstützung von Zeitzonen. Über die [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft kann dem Datum und der Uhrzeit ein [System.DateTimeKind](xref:System.DateTimeKind)-Wert zugewiesen werden, um anzuzeigen, ob die Ortszeit, die koordinierte Weltzeit (UTC) oder die Zeit in einer nicht angegebenen Zeitzone dargestellt wird. Diese eingeschränkten Zeitzoneninformationen werden jedoch beim Vergleichen oder Durchführen von Datums- und Zeitarithmetik für [DateTime](xref:System.DateTime)-Werte ignoriert. Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

Die Methode [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) gibt an, dass die Ortszeit früher als (oder kleiner als) die UTC-Zeit ist, und der Subtraktionsvorgang ergibt, dass der Unterschied zwischen UTC und der Ortszeit für ein System in der US-Zeitzone Pacific Standard Time sieben Stunden beträgt. Da diese beiden Werte verschiedene Darstellungen eines einzigen Zeitpunkts angeben, ist das Zeitintervall in diesem Fall vollständig auf die Abweichung der Ortszeit von UTC zurückzuführen. 

Im Allgemeinen wirkt die [DateTimeKind](xref:System.DateTimeKind)-Eigenschaft sich nicht auf die Ergebnisse aus, die durch den [DateTime](xref:System.DateTime)-Vergleich und arithmetische Methoden zurückgegeben werden (wie der Vergleich zweier identischer Zeitpunkte zeigt), aber sie kann die Interpretation dieser Ergebnisse beeinflussen. Zum Beispiel:

* Das Ergebnis einer beliebigen arithmetischen Operation für zwei Datums- und Zeitwerte, deren [DateTimeKind](xref:System.DateTimeKind)-Eigenschaften beide den Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) aufweisen, gibt das tatsächliche Zeitintervall zwischen den beiden Werten wieder. Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.

* Das Ergebnis einer arithmetischen oder Vergleichsoperation für zwei Datums- und Uhrzeitwerte, deren [DateTimeKind](xref:System.DateTimeKind)-Eigenschaften beide den Wert [DateTimeKind.Local](xref:System.DateTimeKind.Local) aufweisen, oder für zwei Datums- und Uhrzeitwerte mit unterschiedlichen [DateTimeKind](xref:System.DateTimeKind)-Eigenschaftswerten gibt den Zeitunterschied zwischen den beiden Werten an. 

* Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.

* Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht. 

* Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder. Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder. 

* Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.

Es gibt viele Szenarios, in denen Zeitzonenunterschiede sich nicht auf Datums- und Uhrzeitberechnungen auswirken oder in denen die Bedeutung von Vergleichen oder arithmetischen Operationen durch den Kontext des Datums und der Uhrzeit definiert wird. Einige dieser Szenarios werden unter [Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md) erläutert.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten

Ein [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch eine Abweichung, die das jeweilige Datum und die Uhrzeit relativ zur UTC eindeutig definiert. Dadurch kann die Übereinstimmung anders als für [System.DateTime](xref:System.DateTime)-Werte definiert werden. Während [DateTime](xref:System.DateTime) Werte gleich sind, wenn sie denselben Datums- und Uhrzeitwert aufweisen, stimmen [DateTimeOffset](xref:System.DateTimeOffset)-Werte überein, wenn sie sich beide auf denselben Zeitpunkt beziehen. Dadurch ist ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert genauer und erfordert weniger Interpretationsaufwand, wenn er in Vergleichen und den meisten arithmetischen Operationen verwendet wird, die das Intervall zwischen zwei Datumsangaben und Uhrzeiten ermitteln. Das folgende Beispiel ist das [DateTimeOffset](xref:System.DateTimeOffset)-Äquivalent zum vorherigen Beispiel, bei dem der lokale und der UTC-DateTime-Wert verglichen wurde. Darin wird dieser Unterschied im Verhalten veranschaulicht.

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

In diesem Beispiel gibt die [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset))-Methode an, dass die aktuelle Ortszeit und die aktuelle UTC-Zeit identisch sind, und die Subtraktion von [DateTimeOffset](xref:System.DateTimeOffset)-Werten weist darauf hin, dass der Unterschied zwischen den beiden Zeiten [TimeSpan.Zero](xref:System.TimeSpan.Zero) beträgt. 

Die wichtigste Einschränkung bei der Verwendung von [DateTimeOffset](xref:System.DateTimeOffset)-Werten in Datums- und Uhrzeitoperationen besteht darin, dass [DateTimeOffset](xref:System.DateTimeOffset)-Werte Zeitzonen zwar ansatzweise, aber nicht vollständig unterstützen. Auch wenn die Abweichung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts bei der ersten Zuweisung zu einer [DateTimeOffset](xref:System.DateTimeOffset)-Variablen die Abweichung einer Zeitzone von UTC wiedergibt, wird der Wert anschließend unabhängig von der Zeitzone verarbeitet. Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt. 

Zur Veranschaulichung: Der Übergang zur Sommerzeit erfolgt in der US-Zeitzone Central Standard Time um 2:00 Uhr morgens am 9. März 2008. Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens am 9. März 2008 ergeben. Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens am 9. März 2008. Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, auch wenn es sich nicht um die Uhrzeit in der Zeitzone handelt, an der wir interessiert sind (d.h. sie weist nicht die erwartete Zeitzonenabweichung auf).

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Arithmetische Operationen mit Uhrzeiten in Zeitzonen

Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse bietet keine Methoden zum automatischen Anwenden von Anpassungsregeln beim Ausführen arithmetischer Datums- und Uhrzeitoperationen. Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren. Einzelheiten hierzu finden Sie unter [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](use-time-zones-in-arithmetic.md).

Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](use-time-zones-in-arithmetic.md)





<!--HONumber=Nov16_HO3-->


