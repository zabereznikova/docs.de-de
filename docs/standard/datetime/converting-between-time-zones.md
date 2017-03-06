---
title: Konvertieren von Uhrzeiten zwischen Zeitzonen
description: Konvertieren von Uhrzeiten zwischen Zeitzonen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b53e6ee3c437ce76eb4d1d45f1898d513598f786
ms.lasthandoff: 01/18/2017

---

# <a name="converting-times-between-time-zones"></a>Konvertieren von Uhrzeiten zwischen Zeitzonen

Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können. Eine Anwendung kann nicht voraussetzen, dass alle Uhrzeiten in lokaler Zeit, also in der über die [System.DateTime](xref:System.DateTime)-Struktur verfügbaren Zeit, ausgedrückt werden können. Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren. Dieses Thema erläutert, wie Sie Uhrzeiten zwischen Zeitzonen konvertieren und wie Sie [System.DateTimeOffset](xref:System.DateTimeOffset)-Werte konvertieren, bei denen die Zeitzone nur in eingeschränktem Maß berücksichtigt wird.

## <a name="converting-to-coordinated-universal-time"></a>Konvertieren in die koordinierte Weltzeit

Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard. Die Zeitzonen der Welt werden als positive oder negative Abweichungen von der UTC ausgedrückt. Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit. Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist. Durch Konvertieren einzelner Zeitzonen in die UTC lassen sich Zeiten einfach miteinander vergleichen.

> [!NOTE]
> Sie können auch eine [DateTimeOffset](xref:System.DateTimeOffset)-Struktur serialisieren, um einen bestimmten Zeitpunkt eindeutig darzustellen. Da [DateTimeOffset](xref:System.DateTimeOffset)-Objekte einen Datums- und Uhrzeitwert sowie die zugehörige Abweichung von der UTC speichern, stellen sie immer einen bestimmten Zeitpunkt in Relation zur UTC dar.

Die einfachste Möglichkeit, eine Uhrzeit in die UTC zu konvertieren, ist der Aufruf der `static`-Methode (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx). 

> [!IMPORTANT]
> Die `TimeZoneInfo.ConvertTimeToUtc(DateTime)`-Methode ist derzeit in .NET Core nicht verfügbar. 

Welche Konvertierung von der Methode genau ausgeführt wird, richtet sich nach dem Wert der [Kind](xref:System.DateTime.Kind)-Eigenschaft des `DateTime`-Parameters, wie in der folgenden Tabelle gezeigt.

[DateTime.Kind](xref:System.DateTimeKind)-Eigenschaft | Umwandeln
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Konvertiert die lokale Zeit in die UTC.
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Nimmt an, dass der `DateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Gibt den `DateTime`-Parameter unverändert zurück.

Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
>Die [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode erzeugt nicht notwendigerweise Ergebnisse, die mit den Ergebnissen der Methoden [TimeZone.ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) und [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) identisch sind. Wenn die lokale Zeitzone des Hostsystems mehrere Anpassungsregeln enthält, wendet [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) die geeignete Regel auf ein bestimmtes Datum und eine bestimmte Uhrzeit an. Die anderen beiden Methoden wenden immer die jüngste Anpassungsregel an.

Wenn der Datums- und Uhrzeitwert weder die lokale Zeit noch die UTC-Zeit darstellt, gibt die [ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx)-Methode wahrscheinlich ein falsches Ergebnis zurück. Sie können jedoch die [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode verwenden, um das Datum und die Uhrzeit aus einer angegebenen Zeitzone zu konvertieren. (Weitere Informationen zum Abrufen eines TimeZoneInfo-Objekts, das die Zielzeitzone darstellt, finden Sie unter [Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md).) Der folgende Code verwendet die [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode, um die Eastern Standard Time in die UTC zu konvertieren.

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

Beachten Sie, dass diese Methode eine [ArgumentException](xref:System.ArgumentException) auslöst, wenn die [Kind](xref:System.DateTimeKind)-Eigenschaft des [DateTime](xref:System.DateTime)-Objekts und die Zeitzone nicht übereinstimmen. Ein solcher Fall tritt auf, wenn die Kind-Eigenschaft [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet, aber das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt nicht die lokale Zeitzone darstellt, oder wenn die Kind-Eigenschaft [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, aber das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt nicht gleich [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) ist.

All diese Methoden akzeptieren [DateTime](xref:System.DateTime)-Werte als Parameter und geben einen [DateTime](xref:System.DateTime)-Wert zurück. Für [DateTimeOffset](xref:System.DateTimeOffset)-Werte besitzt die [DateTimeOffset](xref:System.DateTimeOffset)-Struktur eine [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Instanzmethode, die das Datum und die Uhrzeit der aktuellen Instanz in die UTC konvertiert. Das folgende Beispiel ruft die [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Methode auf, um eine lokale Uhrzeit sowie verschiedene weitere Uhrzeiten in die koordinierte Weltzeit zu konvertieren.

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a>Konvertieren der UTC in eine festgelegte Zeitzone

Informationen zum Konvertieren der UTC in eine lokale Uhrzeit finden Sie im nächsten Abschnitt, [Konvertieren der UTC in eine lokale Zeit](#converting-utc-to-local-time). 

Um die UTC in die Uhrzeit einer von Ihnen festgelegten Zeitzone zu konvertieren, rufen Sie die [ConvertTimeFromUtc](https://msdn.microsoft.com/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx)-Methode auf. 

> [!IMPORTANT]
> Die Methode „TimeZoneInfo.ConvertTimeFromUtc“ ist in .NET Core zurzeit nicht verfügbar. 

Die Methode akzeptiert zwei Parameter:

* Die zu konvertierende UTC. Hierbei muss es sich um einen [DateTime](xref:System.DateTime)-Wert handeln, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) oder [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) festgelegt ist. 

* Die Zeitzone, in die die UTC konvertiert werden soll. 

Der folgende Code konvertiert die UTC in die Central Standard Time.

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a>Konvertieren der UTC in eine lokale Zeit

Um die UTC in eine lokale Zeit zu konvertieren, rufen Sie die [DateTime.ToLocalTime](xref:System.DateTime)-Methode des [DateTime](xref:System.DateTime)-Objekts auf, dessen Zeit Sie konvertieren möchten. Das genaue Verhalten der Methode richtet sich nach dem Wert der [Kind](xref:System.DateTime.Kind)-Eigenschaft des Objekts, wie in der folgenden Tabelle gezeigt.

[DateTime.Kind](xref:System.DateTimeKind)-Eigenschaft | Umwandeln
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Gibt den [DateTime](xref:System.DateTime)-Wert unverändert zurück.
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Nimmt an, dass der [DateTime](xref:System.DateTime)-Wert als UTC vorliegt, und konvertiert die UTC in die lokale Zeit.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Konvertiert den [DateTime](xref:System.DateTime)-Wert in die lokale Zeit.

## <a name="converting-between-any-two-time-zones"></a>Konvertieren zwischen zwei beliebigen Zeitzonen

Sie können mithilfe der statischen [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode eine zwischen zwei beliebigen Zeitzonen konvertieren. Die Parameter dieser Methode sind der zu konvertierende [DateTime](xref:System.DateTime)-Wert, ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone des Datums- und Uhrzeitwerts darstellt, und ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone darstellt, in die der Datums- und Uhrzeitwert konvertiert werden soll.

Diese Methode erfordert, dass die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zu konvertierenden Datums- und Uhrzeitwerts und das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt bzw. der Zeitzonenbezeichner, der die Zeitzone repräsentiert, einander entsprechen. Andernfalls wird eine [ArgumentException](xref:System.ArgumentException) ausgelöst. Wenn z.B. die [Kind](xref:System.DateTime.Kind)-Eigenschaft des Datums- und Uhrzeitwerts [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet und das als Parameter an die Methode übergebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt ungleich [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) ist, wird eine Ausnahme ausgelöst. Es wird ebenfalls eine Ausnahme ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner ungleich [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) ist.

Das folgende Beispiel verwendet die [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode, um aus der Hawaiian Standard Time in die lokale Zeit zu konvertieren.

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a>Konvertieren von DateTimeOffset-Werten

Datums- und Uhrzeitwerte, die durch [System.DateTimeOffset](xref:System.DateTimeOffset)-Objekte dargestellt werden, berücksichtigen die Zeitzone nicht vollständig, weil das Objekt zum Zeitpunkt der Instanziierung nicht mit der zugehörigen Zeitzone verknüpft ist. In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen. Um diese Konvertierung auszuführen, können Sie die [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan))-Methode der aktuellen Instanz aufrufen. Der einzige Parameter dieser Methode ist [TimeSpan](xref:System.TimeSpan), der die Abweichung vom neuen Datums- und Uhrzeitwert darstellt, den die Methode zurückgeben soll.  

Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

Beispiel: An diese Methode wird die Zeichenfolge „9/1/2007 5:32:07 -05:00“ übergeben. Diese stellt das Datum und die Uhrzeit in einer Zeitzone dar, die fünf Stunden vor der UTC liegt. In diesem Fall gibt die Methode den Wert „9/1/2007 3:32:07 AM -07:00“ zurück, wenn sich der Server in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse enthält auch eine überladene [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo))-Methode, die Zeitzonenkonvertierungen mit [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten ausführt. Die Parameter der Methode sind ein [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll. Der Methodenaufruf gibt einen [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert zurück. Die `ReturnTimeOnServer`-Methode im vorherigen Beispiel könnte auch folgendermaßen neu geschrieben werden, um die [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo))-Methode aufzurufen.

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a>Siehe auch

[TimeZoneInfo](xref:System.TimeZoneInfo)

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)



