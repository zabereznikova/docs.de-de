---
title: "Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo"
description: "Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: f8a603bab32afd0b8e7d13c9c5755e3f14a9d2bd

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a>Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo

.NET-Anwendungen, die Datums- und Uhrzeitinformationen verwenden, sind sehr vielfältig und können diese Informationen auf verschiedene Weise verwenden. Die häufigeren Verwendungsarten von Datums- und Uhrzeitinformationen sind mindestens eine der folgenden:

* Darstellen eines reinen Datums, damit Zeitinformationen unberücksichtigt bleiben.

* Darstellen einer reinen Uhrzeit, damit Datumsinformationen unberücksichtigt bleiben.

* Darstellen eines abstrakten Datums mit Uhrzeit, die an keine bestimmte Zeit und keinen bestimmten Ort gebunden sind (z. B. öffnen die meisten Geschäfte einer internationalen Kette an Wochentagen um 9:00 Uhr).

* Abrufen von Datums- und Uhrzeitinformationen aus Quellen außerhalb der .NET-Anwendung, typischerweise wo Datums- und Uhrzeitinformationen in einem einfachen Datentyp gespeichert sind.

* Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Einige Anwendungen erfordern, dass ein Datum und eine Uhrzeit eindeutig sind, nur auf dem Hostsystem. Andere erfordern, dass sie über Systeme hinweg eindeutig sind (d. h. ein auf dem einen System serialisiertes Datum kann weltweit auf einem anderen System sinnvoll deserialisiert und verwendet werden). 

* Erhalten mehrerer verwandter Zeiten (z. B. die lokale Zeit des Anforderers und die Empfangszeit des Servers für eine Webanforderung).

* Durchführen von Datums- und Uhrzeitberechnungen, möglicherweise mit einem Ergebnis, das einen einzigen Zeitpunkt eindeutig identifiziert. 

.NET enthält die [System.DateTime](xref:System.DateTime)-, [System.DateTimeOffset](xref:System.DateTimeOffset)-, [System.TimeSpan](xref:System.TimeSpan)- und [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Typen, mit denen Anwendungen erstellt werden können, die mit Datums- und Uhrzeitangaben arbeiten. 

> [!NOTE]
> In diesem Thema wird der ältere `TimeZone`-Typ nicht behandelt, weil seine Funktionalität nahezu vollständig in der [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse enthalten ist. Nach Möglichkeit sollten Entwickler die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse anstelle der `TimeZone`-Klasse verwenden.


## <a name="the-datetime-structure"></a>Die DateTime-Struktur

Ein [System.DateTime](xref:System.DateTime)-Wert definiert ein bestimmtes Datum und eine Uhrzeit. Er enthält eine [Kind](xref:System.DateTime.Kind)-Eigenschaft, die eingeschränkte Informationen über die Zeitzone bietet, zu der dieses Datum und die Uhrzeit gehören. Der [DateTimeKind](xref:System.DateTimeKind)-Rückgabewert der [Kind](xref:System.DateTime.Kind)-Eigenschaft gibt an, ob der [DateTime](xref:System.DateTime)-Wert die Ortszeit ([DateTimeKind.Local](xref:System.DateTimeKind.Local)), die koordinierte Weltzeit (Coordinated Universal Time, UTC) ([DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) oder eine unspezifische Uhrzeit ([DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)) angibt.

Die [DateTime](xref:System.DateTime)-Struktur eignet sich für Anwendungen, die Folgendes können: 

* Nur mit Daten arbeiten.

* Nur mit Uhrzeiten arbeiten.

* Mit abstrakten Datums- und Uhrzeitwerten arbeiten.

* Mit Datums- und Uhrzeitwerten arbeiten, für die Zeitzoneninformationen fehlen. 

* Nur mit UTC-Datums- und Uhrzeitwerten arbeiten. 

* Datums- und Uhrzeitinformationen aus Quellen außerhalb von .NET Framework abrufen, wie SQL-Datenbanken. In der Regel speichern diese Quellen Datums- und Uhrzeitinformationen in einem einfachen Format, das mit der [DateTime](xref:System.DateTime)-Struktur kompatibel ist.

* Arithmetische Operationen mit Datums- und Uhrzeitwerten durchführen, wobei aber allgemeine Ergebnisse von Belang sind. Beispielsweise ist es bei einer Additionsoperation, bei der einem bestimmten Datum und einer Uhrzeit sechs Monate hinzuaddiert werden, oft nicht wichtig, ob das Ergebnis hinsichtlich der Sommerzeit angepasst wird.

Wenn nicht ein bestimmter [DateTime](xref:System.DateTime)-Wert UTC darstellt, ist dieser Datums- und Uhrzeitwert häufig mehrdeutig oder in seiner Portierbarkeit eingeschränkt. Wenn z.B. ein [DateTime](xref:System.DateTime)-Wert die lokale Uhrzeit darstellt, ist er innerhalb dieser lokalen Zeitzone portierbar (d.h., wenn der Wert auf einem anderen System in der gleichen Zeitzone deserialisiert wird, identifiziert dieser Wert immer noch eindeutig einen einzigen Zeitpunkt). Außerhalb der lokalen Zeitzone kann dieser [DateTime](xref:System.DateTime)-Wert über mehrere Interpretationen verfügen. Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des Werts [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) ist, ist er sogar noch weniger portierbar: Er ist jetzt innerhalb der gleichen Zeitzone mehrdeutig und möglicherweise sogar auf dem gleichen System, auf dem er erstmalig serialisiert wurde. Nur wenn ein [DateTime](xref:System.DateTime)-Wert eine UTC-Zeit darstellt, identifiziert dieser Wert eindeutig einen einzigen Zeitpunkt, unabhängig vom System oder der Zeitzone, in der der Wert verwendet wird.

> [!IMPORTANT]
> Beim Speichern oder Freigeben von [DateTime](xref:System.DateTime)-Daten sollte UTC verwendet werden, und die [Kind](xref:System.DateTime.Kind)-Eigenschaft des [DateTime](xref:System.DateTime)-Werts sollte auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) festgelegt werden.

## <a name="the-datetimeoffset-structure"></a>Die DateTimeOffset-Struktur

Die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur stellt einen Datums- und Uhrzeitwert zusammen mit einem Offset dar, der angibt, um wie viel dieser Wert von UTC abweicht. Somit identifiziert der Wert immer eindeutig einen einzigen Zeitpunkt. 

Der [DateTimeOffset](xref:System.DateTimeOffset)-Typ bietet die gesamte Funktionalität des [DateTime](xref:System.DateTime)-Typs plus Unterstützung von Zeitzonen. Dadurch eignet er sich für Anwendungen, die Folgendes unterstützen: 

* Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts. Der [DateTimeOffset](xref:System.DateTimeOffset)-Typ kann zur eindeutigen Definition der Bedeutung von „jetzt“ verwendet werden, um Transaktionszeiten zu protokollieren, die Zeiten von System- oder Anwendungsereignissen zu protokollieren und um die Zeiten der Erstellung und Änderung von Dateien aufzuzeichnen. 

* Ausführen von allgemeinen Datums- und Uhrzeitberechnungen

* Erhalten mehrerer verwandter Uhrzeiten, solange diese Zeiten als zwei gesonderte Werte oder als zwei Member einer Struktur gespeichert werden.

> [!NOTE]
> Diese Verwendungsarten für [DateTimeOffset](xref:System.DateTimeOffset)-Werte sind sehr viel häufiger als die für [DateTime](xref:System.DateTime)-Werte. Demzufolge sollte in der Anwendungsentwicklung [DateTimeOffset](xref:System.DateTimeOffset) als Standardtyp für Datum und Uhrzeit angesehen werden.

Ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert ist nicht an eine bestimmte Zeitzone gebunden, kann aber aus jeder der zahlreichen Zeitzonen stammen. Um dies zu veranschaulichen, listet das folgende Beispiel die Zeitzonen auf, zu denen eine Reihe von [DateTimeOffset](xref:System.DateTimeOffset)-Werten (einschließlich eines Werts in lokaler Pacific Normalzeit) gehören können.

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

Die Ausgabe zeigt, dass jeder Datums- und Uhrzeitwert in diesem Beispiel zu mindestens drei verschiedenen Zeitzonen gehören kann. Der [DateTimeOffset](xref:System.DateTimeOffset)-Wert „6/10/2007“ zeigt, dass, wenn ein Datums- und Uhrzeitwert eine Sommerzeit darstellt, sein Offset von UTC noch nicht einmal unbedingt dem UTC-Basisoffset der Ursprungszeitzone oder dem in seinem Anzeigenamen vorgefundenen Offset von UTC entsprechen muss. Dies bedeutet: Weil ein einzelner [DateTimeOffset](xref:System.DateTimeOffset)-Wert nicht eng mit seiner Zeitzone verknüpft ist, kann er nicht den Übergang einer Zeitzone zur und aus der Sommerzeit wiedergeben. Dies kann besonders problematisch sein, wenn ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert mithilfe von Datums- und Uhrzeitberechnungen manipuliert wird. Eine Erläuterung der Durchführung von Datums- und Uhrzeitberechnungen auf eine Weise, die die Anpassungsregeln einer Zeitzone berücksichtigt, finden Sie unter [Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md).

## <a name="the-timespan-structure"></a>Die TimeSpan-Struktur

Die [System.TimeSpan](xref:System.TimeSpan)-Struktur stellt ein Zeitintervall dar. Sein zwei typischen Anwendungsmöglichkeiten sind: 

* Darstellen des Zeitintervalls zwischen zwei Datums- und Uhrzeitwerten. Beispielsweise gibt die Subtraktion eines [DateTime](xref:System.DateTime)-Werts von einem anderen einen [TimeSpan](xref:System.TimeSpan)-Wert zurück. 

* Messen der verstrichenen Zeit. Beispielsweise gibt die [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed)-Eigenschaft einen [TimeSpan](xref:System.TimeSpan)-Wert zurück, der das Zeitintervall angibt, das seit dem Aufrufen einer der [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch)-Methoden, die verstrichene Zeit zu messen beginnen, verstrichen ist.

Ein [TimeSpan](xref:System.TimeSpan)-Wert kann auch als Ersatz für einen [DateTime](xref:System.DateTime)-Wert verwendet werden, wenn dieser Wert eine Uhrzeit ohne Verweis auf eine bestimmte Tageszeit widerspiegelt. Diese Verwendung ähnelt den Eigenschaften [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) und [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), die einen [TimeSpan](xref:System.TimeSpan)-Wert zurückgeben, der die Uhrzeit ohne Verweis auf ein Datum darstellt. Beispielsweise kann die [TimeSpan](xref:System.TimeSpan)-Struktur verwendet werden, um die täglichen Öffnungszeiten eines Geschäfts darzustellen oder um die Uhrzeit darzustellen, zu der alle regulären Ereignisse auftreten.

Das folgende Beispiel definiert eine `StoreInfo`-Struktur, die [TimeSpan](xref:System.TimeSpan)-Objekte für Öffnungszeiten von Geschäften enthält, sowie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone des Geschäfts darstellt. Die Struktur enthält außerdem zwei Methoden, `IsOpenNow` und `IsOpenAt`, die angeben, ob das Geschäft zu einem vom Benutzer angegebenen Zeitpunkt geöffnet ist, wobei angenommen wird, dass er sich in der lokalen Zeitzone aufhält.  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

Die `StoreInfo`-Struktur kann dann von Clientcode wie folgt verwendet werden. 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a>Die TimeZoneInfo-Klasse

Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse stellt eine beliebige Zeitzone der Erde dar und ermöglicht die Konvertierung jeglicher Datums- und Uhrzeitwerte in einer in die entsprechenden Werte in einer anderen Zeitzone. Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse ermöglicht das Arbeiten mit Datums- und Zeitwerten, sodass jeder Datums- und Uhrzeitwert eindeutig einen einzigen Zeitpunkt identifiziert.

In einigen Fällen kann noch weitere Entwicklungsarbeit erforderlich sein, um die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse optimal zu nutzen. Datums-und Uhrzeitwerte sind nicht eng mit den Zeitzonen verknüpft, zu denen sie gehören. Daher kann die Zuordnung eines Datums- und Uhrzeitwerts zu seiner Zeitzone leicht aufgehoben werden, wenn Ihre Anwendung nicht einen Mechanismus bereitstellt, um ein Datum und eine Uhrzeit mit der zugehörigen Zeitzone zu verknüpfen. Eine Methode zum Verknüpfen dieser Informationen besteht darin, eine Klasse oder Struktur zu definieren, die sowohl den Datums- und Zeitwert als auch sein zugeordnetes Zeitzonenobjekt enthält.

Die Zeitzonenunterstützung in .NET kann nur genutzt werden, wenn die Zeitzone, zu der ein Datums- und Uhrzeitwert gehört, bekannt ist, wenn das Datums- und Uhrzeitobjekt instanziiert wird. Dies ist häufig nicht der Fall, insbesondere bei Web-oder Netzwerkanwendungen.

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)


<!--HONumber=Nov16_HO3-->


