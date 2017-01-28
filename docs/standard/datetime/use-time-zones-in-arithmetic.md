---
title: 'Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen'
description: 'Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen'
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: da4c5aec6e02393c9e6201edd766eb7579a40b5e

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen

Normalerweise werden beim Durchführen von arithmetischen Datums- und Uhrzeitoperationen mit [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten in den Ergebnissen keine Anpassungsregeln von Zeitzonen berücksichtigt. Dies trifft auch zu, wenn die Zeitzone des Datums- und Uhrzeitwerts eindeutig erkennbar ist. In diesem Artikel wird erläutert, wie Sie arithmetische Operationen für Datums- und Uhrzeitwerte durchführen, die zu einer bestimmten Zeitzone gehören. Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an

1. Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört. Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt. Im folgenden Beispiel wird dieser Ansatz verwendet, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert mit seiner Zeitzone zu verknüpfen.

    ```csharp
    // Define a structure for DateTime values for internal use only
    internal struct TimeWithTimeZone
    {
    TimeZoneInfo TimeZone;
    DateTimeOffset Time;
    }
    ```

    ```vb
    ' Define a structure for DateTime values for internal use only
    Friend Structure TimeWithTimeZone
       Dim TimeZone As TimeZoneInfo
       Dim Time As Date
    End Structure
    ```
    
2. Konvertieren Sie eine Uhrzeit in koordinierte Weltzeit (Coordinated Universal Time, UTC), indem Sie die [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode aufrufen.

3. Führen Sie die arithmetische Operation für die UTC-Zeit aus.

4. Konvertieren Sie die Zeit von UTC in die mit der ursprünglichen Zeit verknüpfte Zeitzone, indem Sie die [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode aufrufen. 

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr Central Standard Time hinzugefügt. Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9.März 2008. Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9.März 2008. 

```csharp
using System;

public struct TimeZoneTime
{
   public TimeZoneInfo TimeZone;
   public DateTimeOffset Time;

   public TimeZoneTime(TimeZoneInfo tz, DateTimeOffset time)
   {
      if (tz == null) 
         throw new ArgumentNullException("The time zone cannot be a null reference.");

      this.TimeZone = tz;
      this.Time = time;   
   }

   public TimeZoneTime AddTime(TimeSpan interval)
   {
      // Convert time to UTC
      DateTimeOffset utcTime = TimeZoneInfo.ConvertTime(this.Time, TimeZoneInfo.Utc);      
      // Add time interval to time
      utcTime = utcTime.Add(interval);
      // Convert time back to time in time zone
      return new TimeZoneTime(this.TimeZone, TimeZoneInfo.ConvertTime(utcTime, this.TimeZone));
   }
}

public class TimeArithmetic
{
   public const string tzName = "Central Standard Time";

   public static void Main()
   {
      try
      {
         TimeZoneTime cstTime1, cstTime2;

         TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
         DateTime time1 = new DateTime(2008, 3, 9, 1, 30, 0);          
         TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

         cstTime1 = new TimeZoneTime(cst, 
                        new DateTimeOffset(time1, cst.GetUtcOffset(time1)));
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours);
         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, 
                                                    twoAndAHalfHours.ToString(),  
                                                    cstTime2.Time);
      }
      catch
      {
         Console.WriteLine("Unable to find {0}.", tzName);
      }
   }
}
```

```vb
Public Structure TimeZoneTime
   Public TimeZone As TimeZoneInfo
   Public Time As Date

   Public Sub New(tz As TimeZoneInfo, time As Date)
      If tz Is Nothing Then _
         Throw New ArgumentNullException("The time zone cannot be a null reference.")

      Me.TimeZone = tz
      Me.Time = time
   End Sub

   Public Function AddTime(interval As TimeSpan) As TimeZoneTime
      ' Convert time to UTC
      Dim utcTime As DateTime = TimeZoneInfo.ConvertTimeToUtc(Me.Time, _
                                                              Me.TimeZone)      
      ' Add time interval to time
      utcTime = utcTime.Add(interval)
      ' Convert time back to time in time zone
      Return New TimeZoneTime(Me.TimeZone, TimeZoneInfo.ConvertTime(utcTime, _
                              TimeZoneInfo.Utc, Me.TimeZone))
   End Function
End Structure

Module TimeArithmetic
   Public Const tzName As String = "Central Standard Time"

   Public Sub Main()
      Try
         Dim cstTime1, cstTime2 As TimeZoneTime

         Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName)
         Dim time1 As Date = #03/09/2008 1:30AM#
         Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

         cstTime1 = New TimeZoneTime(cst, time1)
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours)

         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, _
                                                    twoAndAHalfHours.ToString(), _ 
                                                    cstTime2.Time)  
      Catch
         Console.WriteLine("Unable to find {0}.", tzName)
      End Try   
   End Sub   
End Module
```

Wenn Sie diese Ergänzung einfach mit dem [DateTimeOffset](xref:System.DateTimeOffset)-Wert durchführen, ohne ihn zuerst in UTC zu konvertieren, gibt das Ergebnis den richtigen Zeitpunkt wieder, aber die Abweichung spiegelt nicht die der festgelegten Zeitzone für diese Uhrzeit wider. 

Für [DateTimeOffset](xref:System.DateTimeOffset)-Werte wird die Zuordnung zu einer Zeitzone, der sie möglicherweise angehören, aufgehoben. Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein. Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen. Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:

* Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören. Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.

* Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen. Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md)



<!--HONumber=Nov16_HO3-->


