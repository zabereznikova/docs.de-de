---
title: Konvertieren zwischen DateTime und DateTimeOffset
description: Konvertieren zwischen DateTime und DateTimeOffset
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fab3af5b-5d0f-4384-a40a-1b5d99b30dd1
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 99ec9d8c433025bbc5122fe3ea364fe84f33a1f8

---

# <a name="converting-between-datetime-and-datetimeoffset"></a>Konvertieren zwischen DateTime und DateTimeOffset

Obwohl die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur eine umfassendere Zeitzonenunterstützung bietet als die [System.DateTime](xref:System.DateTime)-Struktur, werden [DateTime](xref:System.DateTime)-Parameter häufiger in Methodenaufrufen verwendet. Aus diesem Grund ist die Fähigkeit sehr wichtig, [DateTimeOffset](xref:System.DateTimeOffset)-Werte in [DateTime](xref:System.DateTime)-Werte und umgekehrt zu konvertieren. Dieser Artikel zeigt, wie Sie diese Konvertierungen auf eine Weise ausführen, bei der so viele Zeitzoneninformationen wie möglich beibehalten werden.

> [!NOTE]
> Sowohl der [DateTime](xref:System.DateTime)- als auch der [DateTimeOffset](xref:System.DateTimeOffset)-Typ weisen einige Einschränkungen hinsichtlich der Darstellung von Zeiten in Zeitzonen auf. Mit der Eigenschaft [Kind](xref:System.DateTime.Kind) kann [DateTime](xref:System.DateTime) nur die koordinierte Weltzeit (UTC) und die lokale Zeitzone des Systems widerspiegeln. [DateTimeOffset](xref:System.DateTimeOffset) gibt die Abweichung einer Uhrzeit von der UTC wieder, aber nicht die tatsächliche Zeitzone, zu der diese Abweichung gehört. Detaillierte Informationen zu Uhrzeitwerten und zur Unterstützung von Zeitzonen finden Sie unter [Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Konvertierungen von DateTime in DateTimeOffset

Die [DateTimeOffset](xref:System.DateTimeOffset)-Struktur bietet zwei gleichwertige Möglichkeiten zum Konvertieren von [DateTime](xref:System.DateTime) in [DateTimeOffset](xref:System.DateTimeOffset), die sich für die meisten Konvertierungen eignen:

* Der [DateTimeOffset(DateTime)](xref:System.DateTimeOffset)-Konstruktor, der ein neues [DateTimeOffset](xref:System.DateTimeOffset)-Objekt basierend auf einem [DateTime](xref:System.DateTime)-Wert erstellt.

* Der implizite Konvertierungsoperator, mit dem Sie einem [DateTimeOffset](xref:System.DateTimeOffset)-Objekt einen [DateTime](xref:System.DateTime)-Wert zuweisen können.

Für UTC und lokale [DateTime](xref:System.DateTime)-Werte gibt die [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset)-Eigenschaft des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts exakt die UTC-Abweichung oder Abweichung der lokalen Zeitzone wieder. Folgender Code konvertiert z.B. eine UTC-Zeit in den entsprechenden [DateTimeOffset](xref:System.DateTimeOffset)-Wert. 

```csharp
DateTime utcTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
utcTime1 = DateTime.SpecifyKind(utcTime1, DateTimeKind.Utc);
DateTimeOffset utcTime2 = utcTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  utcTime1, 
                  utcTime1.Kind.ToString(), 
                  utcTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM +00:00
```

```vb
Dim utcTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, _
                                        DateTimeKind.Utc)
Dim utcTime2 As DateTimeOffset = utcTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  utcTime1, _
                  utcTime1.Kind.ToString(), _
                  utcTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM  +00:00
```

In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00. Auf die gleiche Weise konvertiert folgender Code eine lokale Zeit in den entsprechenden [DateTimeOffset](xref:System.DateTimeOffset)-Wert.

```csharp
DateTime localTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
localTime1 = DateTime.SpecifyKind(localTime1, DateTimeKind.Local);
DateTimeOffset localTime2 = localTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  localTime1, 
                  localTime1.Kind.ToString(), 
                  localTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim localTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, DateTimeKind.Local)
Dim localTime2 As DateTimeOffset = localTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  localTime1, _
                  localTime1.Kind.ToString(), _
                  localTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

Für [DateTime](xref:System.DateTime)-Werte, deren [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, erzeugen diese beiden Konvertierungsmethoden allerdings einen[DateTimeOffset](xref:System.DateTimeOffset)-Wert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht. Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);  // Kind is DateTimeKind.Unspecified
DateTimeOffset time2 = time1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  time1, 
                  time1.Kind.ToString(), 
                  time2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Dim time2 As DateTimeOffset = time1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  time1, _
                  time1.Kind.ToString(), _
                  time2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

Wenn der [DateTime](xref:System.DateTime)-Wert das Datum und die Uhrzeit in einer anderen Zeit als der lokalen Zeitzone oder der UTC wiedergibt, können Sie den Wert in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert konvertieren und die Zeitzoneninformationen beibehalten, indem Sie den überladenen [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset)-Konstruktor aufrufen. Das folgende Beispiel instanziiert ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt, das die Central Standard Time wiedergibt.

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);     // Kind is DateTimeKind.Unspecified
try
{
   DateTimeOffset time2 = new DateTimeOffset(time1, 
                  TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)); 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", 
                     time1, 
                     time1.Kind.ToString(), 
                     time2);
}
// Handle exception if time zone is not defined in registry
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to identify target time zone for conversion.");
}
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Try
   Dim time2 As New DateTimeOffset(time1, _
                    TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)) 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", _
                     time1, _
                     time1.Kind.ToString(), _
                     time2)
' Handle exception if time zone is not defined in registry
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to identify target time zone for conversion.")
End Try
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

Der zweite Parameter dieser Konstruktorüberladung, ein [System.TimeSpan](xref:System.TimeSpan)-Objekt, das die Abweichung der Uhrzeit von der UTC darstellt, sollte durch Aufrufen der [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo)-Methode der entsprechenden Zeitzone der Uhrzeit abgerufen werden. Der einzige Parameter der Methode ist der [DateTime](xref:System.DateTime)-Wert, der das Datum und die Uhrzeit darstellt, das/die konvertiert werden soll. Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Konvertierungen von DateTimeOffset in DateTime

Die [DateTime](xref:System.DateTime)-Eigenschaft wird am häufigsten verwendet, um Konvertierungen von [DateTimeOffset](xref:System.DateTimeOffset) in [DateTime](xref:System.DateTime) durchzuführen. Die Eigenschaft gibt allerdings einen [DateTime](xref:System.DateTime)-Wert zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, wie im folgenden Beispiel veranschaulicht. 

```csharp
DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset sourceTime;
DateTime targetTime;

// Convert UTC to DateTime value
sourceTime = new DateTimeOffset(baseTime, TimeSpan.Zero);
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert local time to DateTime value
sourceTime = new DateTimeOffset(baseTime, 
                                TimeZoneInfo.Local.GetUtcOffset(baseTime));
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert Central Standard Time to a DateTime value
try
{
   TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime);
   sourceTime = new DateTimeOffset(baseTime, offset);
   targetTime = sourceTime.DateTime;
   Console.WriteLine("{0} converts to {1} {2}", 
                     sourceTime, 
                     targetTime, 
                     targetTime.Kind.ToString());
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.");
} 
// This example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

```vb
Const baseTime As Date = #06/19/2008 7:00AM#
Dim sourceTime As DateTimeOffset
Dim targetTime As Date

' Convert UTC to DateTime value
sourceTime = New DateTimeOffset(baseTime, TimeSpan.Zero)
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert local time to DateTime value
sourceTime = New DateTimeOffset(baseTime, _
                                TimeZoneInfo.Local.GetUtcOffset(baseTime))
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert Central Standard Time to a DateTime value
Try
   Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime)
   sourceTime = New DateTimeOffset(baseTime, offset)
   targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.")
End Try 
' This example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

Dies bedeutet, dass alle Informationen über die Beziehung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts zur UTC bei der Konvertierung verloren gehen, wenn die [DateTime](xref:System.DateTime)-Eigenschaft verwendet wird. Dies betrifft [DateTimeOffset](xref:System.DateTimeOffset)-Werte, die der UTC-Zeit oder der lokalen Systemzeit entsprechen, weil die [DateTime](xref:System.DateTime)-Struktur in ihrer [Kind](xref:System.DateTime.Kind)-Eigenschaft nur diese beiden Zeitzonen wiedergibt.

Um bei der Konvertierung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts in einen [DateTime](xref:System.DateTime)-Wert so viele Zeitzoneninformationen wie möglich beizubehalten, können Sie die Eigenschaften [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) und [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) verwenden. 

## <a name="converting-a-utc-time"></a>Konvertieren einer UTC-Zeit

Um anzugeben, dass es sich bei einem konvertierten [DateTime](xref:System.DateTime)-Wert um die UTC-Zeit handelt, können Sie den Wert der [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime)-Eigenschaft abrufen. Diese Eigenschaft unterscheidet sich in zweierlei Hinsicht von der [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime)-Eigenschaft:

* Sie gibt einen [DateTime](xref:System.DateTime)-Wert zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet.

* Wenn der [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset)-Eigenschaftswert nicht gleich [TimeSpan.Zero](xref:System.TimeSpan.Zero) ist, wird die Uhrzeit in die UTC konvertiert.

> [!NOTE]
> Wenn es Ihre Anwendung erfordert, dass konvertierte [DateTime](xref:System.DateTime)-Werte eine bestimmte Uhrzeit eindeutig identifizieren, sollten Sie die Eigenschaft [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) verwenden, um alle Konvertierungen von [DateTimeOffset](xref:System.DateTimeOffset) in [DateTime](xref:System.DateTime) zu verarbeiten.

Der folgende Code verwendet die [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime)-Eigenschaft, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung [TimeSpan.Zero](xref:System.TimeSpan.Zero) mit einem [DateTime](xref:System.DateTime)-Wert gleichsetzt.

```csharp
DateTimeOffset utcTime1 = new DateTimeOffset(2008, 6, 19, 7, 0, 0, TimeSpan.Zero);
DateTime utcTime2 = utcTime1.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

```vb
Dim utcTime1 As New DateTimeOffset(#06/19/2008 7:00AM#, TimeSpan.Zero)
Dim utcTime2 As Date = utcTime1.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

Der folgende Code verwendet die UtcDateTime-Eigenschaft, um sowohl eine Zeitzonenkonvertierung als auch eine Typkonvertierung für einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert auszuführen.

```csharp
DateTimeOffset originalTime = new DateTimeOffset(2008, 6, 19, 7, 0, 0, new TimeSpan(5, 0, 0));
DateTime utcTime = originalTime.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalTime, 
                  utcTime, 
                  utcTime.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

```vb
Dim originalTime As New DateTimeOffset(#6/19/2008 7:00AM#, _
                                       New TimeSpan(5, 0, 0))
Dim utcTime As Date = originalTime.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _ 
                  originalTime, _
                  utcTime, _
                  utcTime.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

## <a name="converting-a-local-time"></a>Konvertieren einer lokalen Zeit

Um anzugeben, dass ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert die lokale Uhrzeit wiedergibt, können Sie den [DateTime](xref:System.DateTime)-Wert, der von der [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime)-Eigenschaft zurückgegeben wurde, an die statische [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind))-Methode übergeben. Die Methode gibt das an sie übergebene Datum und die übergebene Uhrzeit als ersten Parameter zurück, legt aber die [Kind](xref:System.DateTime.Kind)-Eigenschaft auf den vom zweiten Parameter angegebenen Wert fest. Der folgende Code verwendet die [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind))-Methode, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht.

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset utcTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime utcTime2 = utcTime1.DateTime;
if (utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime))) 
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local);

Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim utcTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim utcTime2 As Date = utcTime1.DateTime
If utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime)) Then
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local)
End If   
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

Sie können auch die [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft verwenden, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert in einen lokalen [DateTime](xref:System.DateTime)-Wert zu konvertieren. Die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zurückgegebenen [DateTime](xref:System.DateTime)-Werts ist [DateTimeKind.Local](xref:System.DateTimeKind.Local). Der folgende Code verwendet die [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht.

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset localTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime localTime2 = localTime1.LocalDateTime;

Console.WriteLine("{0} converted to {1} {2}", 
                  localTime1, 
                  localTime2, 
                  localTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim localTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim localTime2 As Date = localTime1.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime1, _
                  localTime2, _
                  localTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local 
```

Wenn Sie einen [DateTime](xref:System.DateTime)-Wert mithilfe der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft abrufen, konvertiert der `get`-Accessor der Eigenschaft den [DateTimeOffset](xref:System.DateTimeOffset)-Wert zuerst in die UTC und dann durch Aufrufen der [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset)-Methode in die lokale Zeit. Dies bedeutet, dass Sie einen Wert aus der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft abrufen können, um gleichzeitig mit einer Typkonvertierung auch eine Zeitzonenkonvertierung auszuführen. Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden. Der folgende Code verwendet die Verwendung der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft, um sowohl eine Typkonvertierung als auch eine Zeitzonenkonvertierung auszuführen.

```csharp
DateTimeOffset originalDate;
DateTime localDate;

// Convert time originating in a different time zone
originalDate = new DateTimeOffset(2008, 6, 18, 7, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// Convert time originating in a different time zone 
// so local time zone's adjustment rules are applied
originalDate = new DateTimeOffset(2007, 11, 4, 4, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
//       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

```vb
Dim originalDate As DateTimeOffset
Dim localDate As Date

' Convert time originating in a different time zone
originalDate = New DateTimeOffset(#06/19/2008 7:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' Convert time originating in a different time zone 
' so local time zone's adjustment rules are applied
originalDate = New DateTimeOffset(#11/04/2007 4:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
'       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

## <a name="a-general-purpose-conversion-method"></a>Eine allgemeine Konvertierungsmethode

Das folgende Beispiel definiert eine Methode namens `ConvertFromDateTimeOffset`, die [DateTimeOffset](xref:System.DateTimeOffset)-Werte in [DateTime](xref:System.DateTime)-Werte konvertiert. Basierend auf der Abweichung bestimmt die Methode, ob es sich beim [DateTimeOffset](xref:System.DateTimeOffset)-Wert um eine UTC-Zeit, eine lokale Zeit oder eine andere Zeit handelt, und definiert die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zurückgegebenen Datums- und Uhrzeitwerts entsprechend. 

```csharp
static DateTime ConvertFromDateTimeOffset(DateTimeOffset dateTime)
{
   if (dateTime.Offset.Equals(TimeSpan.Zero))
      return dateTime.UtcDateTime;
   else if (dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime)))
      return DateTime.SpecifyKind(dateTime.DateTime, DateTimeKind.Local);
   else
      return dateTime.DateTime;   
}
```

```vb
Function ConvertFromDateTimeOffset(dateTime As DateTimeOffset) As Date
   If dateTime.Offset.Equals(TimeSpan.Zero) Then
      Return dateTime.UtcDateTime
   ElseIf dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime))
      Return Date.SpecifyKind(dateTime.DateTime, DateTimeKind.Local)
   Else
      Return dateTime.DateTime   
   End If
```

Das folgende Beispiel ruft die `ConvertFromDateTimeOffset`-Methode auf, um [DateTimeOffset](xref:System.DateTimeOffset)-Werte zu konvertieren, die eine UTC-Zeit, eine lokale Zeit und eine Zeit in der Central Standard Time-Zeitzone (USA) darstellen.

```csharp
DateTime timeComponent = new DateTime(2008, 6, 19, 7, 0, 0);
DateTime returnedDate; 

// Convert UTC time
DateTimeOffset utcTime = new DateTimeOffset(timeComponent, TimeSpan.Zero);
returnedDate = ConvertFromDateTimeOffset(utcTime); 
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert local time
DateTimeOffset localTime = new DateTimeOffset(timeComponent, 
                           TimeZoneInfo.Local.GetUtcOffset(timeComponent)); 
returnedDate = ConvertFromDateTimeOffset(localTime);                                          
Console.WriteLine("{0} converted to {1} {2}", 
                  localTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert Central Standard Time
DateTimeOffset cstTime = new DateTimeOffset(timeComponent, 
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent));
returnedDate = ConvertFromDateTimeOffset(cstTime);
Console.WriteLine("{0} converted to {1} {2}", 
                  cstTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());
// The example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
//    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
//    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

```vb
Dim timeComponent As Date = #06/19/2008 7:00AM#
Dim returnedDate As Date 

' Convert UTC time
Dim utcTime As New DateTimeOffset(timeComponent, TimeSpan.Zero)
returnedDate = ConvertFromDateTimeOffset(utcTime) 
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert local time
Dim localTime As New DateTimeOffset(timeComponent, _
                                    TimeZoneInfo.Local.GetUtcOffset(timeComponent)) 
returnedDate = ConvertFromDateTimeOffset(localTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert Central Standard Time
Dim cstTime As New DateTimeOffset(timeComponent, _
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent))
returnedDate = ConvertFromDateTimeOffset(cstTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  cstTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())
' The example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
'    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
'    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:

* Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung [TimeSpan.Zero](xref:System.TimeSpan.Zero) beträgt, eine UTC-Zeit darstellt. Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind. Zeitzonen können auch eine Abweichung von [null](xref:System.TimeSpan.Zero) aufweisen.

* Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt. Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)







<!--HONumber=Nov16_HO3-->


