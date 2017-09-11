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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b53e6ee3c437ce76eb4d1d45f1898d513598f786
ms.contentlocale: de-de
ms.lasthandoff: 01/18/2017

---

# <a name="converting-times-between-time-zones"></a><span data-ttu-id="1aa7a-104">Konvertieren von Uhrzeiten zwischen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="1aa7a-104">Converting times between time zones</span></span>

<span data-ttu-id="1aa7a-105">Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-105">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="1aa7a-106">Eine Anwendung kann nicht voraussetzen, dass alle Uhrzeiten in lokaler Zeit, also in der über die [System.DateTime](xref:System.DateTime)-Struktur verfügbaren Zeit, ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-106">An application can no longer assume that all times can be expressed in the local time, which is the time available from the [System.DateTime](xref:System.DateTime) structure.</span></span> <span data-ttu-id="1aa7a-107">Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-107">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="1aa7a-108">Dieses Thema erläutert, wie Sie Uhrzeiten zwischen Zeitzonen konvertieren und wie Sie [System.DateTimeOffset](xref:System.DateTimeOffset)-Werte konvertieren, bei denen die Zeitzone nur in eingeschränktem Maß berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-108">This topic explains how to convert times from one time zone to another, as well as how to convert [System.DateTimeOffset](xref:System.DateTimeOffset) values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="1aa7a-109">Konvertieren in die koordinierte Weltzeit</span><span class="sxs-lookup"><span data-stu-id="1aa7a-109">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="1aa7a-110">Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-110">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="1aa7a-111">Die Zeitzonen der Welt werden als positive oder negative Abweichungen von der UTC ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-111">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="1aa7a-112">Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-112">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="1aa7a-113">Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-113">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="1aa7a-114">Durch Konvertieren einzelner Zeitzonen in die UTC lassen sich Zeiten einfach miteinander vergleichen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-114">Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="1aa7a-115">Sie können auch eine [DateTimeOffset](xref:System.DateTimeOffset)-Struktur serialisieren, um einen bestimmten Zeitpunkt eindeutig darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-115">You can also serialize a [DateTimeOffset](xref:System.DateTimeOffset) structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="1aa7a-116">Da [DateTimeOffset](xref:System.DateTimeOffset)-Objekte einen Datums- und Uhrzeitwert sowie die zugehörige Abweichung von der UTC speichern, stellen sie immer einen bestimmten Zeitpunkt in Relation zur UTC dar.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-116">Because [DateTimeOffset](xref:System.DateTimeOffset) objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="1aa7a-117">Die einfachste Möglichkeit, eine Uhrzeit in die UTC zu konvertieren, ist der Aufruf der `static`-Methode (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="1aa7a-117">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1aa7a-118">Die `TimeZoneInfo.ConvertTimeToUtc(DateTime)`-Methode ist derzeit in .NET Core nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-118">The `TimeZoneInfo.ConvertTimeToUtc(DateTime)` method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="1aa7a-119">Welche Konvertierung von der Methode genau ausgeführt wird, richtet sich nach dem Wert der [Kind](xref:System.DateTime.Kind)-Eigenschaft des `DateTime`-Parameters, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-119">The exact conversion performed by the method depends on the value of the `DateTime` parameter's [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="1aa7a-120">[DateTime.Kind](xref:System.DateTimeKind)-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1aa7a-120">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="1aa7a-121">Umwandeln</span><span class="sxs-lookup"><span data-stu-id="1aa7a-121">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="1aa7a-122">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="1aa7a-122">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="1aa7a-123">Konvertiert die lokale Zeit in die UTC.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-123">Converts local time to UTC.</span></span>
[<span data-ttu-id="1aa7a-124">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="1aa7a-124">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="1aa7a-125">Nimmt an, dass der `DateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-125">Assumes the `DateTime` parameter is local time and converts local time to UTC.</span></span>
[<span data-ttu-id="1aa7a-126">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="1aa7a-126">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="1aa7a-127">Gibt den `DateTime`-Parameter unverändert zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-127">Returns the `DateTime` parameter unchanged.</span></span>

<span data-ttu-id="1aa7a-128">Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-128">The following code converts the current local time to UTC and displays the result to the console.</span></span>

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
><span data-ttu-id="1aa7a-129">Die [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode erzeugt nicht notwendigerweise Ergebnisse, die mit den Ergebnissen der Methoden [TimeZone.ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) und [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) identisch sind.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-129">The [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx) method does not necessarily produce results that are identical to the [TimeZone.ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) and [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) methods.</span></span> <span data-ttu-id="1aa7a-130">Wenn die lokale Zeitzone des Hostsystems mehrere Anpassungsregeln enthält, wendet [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) die geeignete Regel auf ein bestimmtes Datum und eine bestimmte Uhrzeit an.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-130">If the host system's local time zone includes multiple adjustment rules, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="1aa7a-131">Die anderen beiden Methoden wenden immer die jüngste Anpassungsregel an.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-131">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="1aa7a-132">Wenn der Datums- und Uhrzeitwert weder die lokale Zeit noch die UTC-Zeit darstellt, gibt die [ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx)-Methode wahrscheinlich ein falsches Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-132">If the date and time value does not represent either the local time or UTC, the [ToUniversalTime](https://msdn.microsoft.com/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) method will likely return an erroneous result.</span></span> <span data-ttu-id="1aa7a-133">Sie können jedoch die [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode verwenden, um das Datum und die Uhrzeit aus einer angegebenen Zeitzone zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-133">However, you can use the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx) method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="1aa7a-134">(Weitere Informationen zum Abrufen eines TimeZoneInfo-Objekts, das die Zielzeitzone darstellt, finden Sie unter [Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md).)</span><span class="sxs-lookup"><span data-stu-id="1aa7a-134">(For details on retrieving a TimeZoneInfo object that represents the destination time zone, see [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md).</span></span> <span data-ttu-id="1aa7a-135">Der folgende Code verwendet die [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx)-Methode, um die Eastern Standard Time in die UTC zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-135">The following code uses the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/library/bb381744(v=vs.110).aspx) method to convert Eastern Standard Time to UTC.</span></span>

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

<span data-ttu-id="1aa7a-136">Beachten Sie, dass diese Methode eine [ArgumentException](xref:System.ArgumentException) auslöst, wenn die [Kind](xref:System.DateTimeKind)-Eigenschaft des [DateTime](xref:System.DateTime)-Objekts und die Zeitzone nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-136">Note that this method throws an [ArgumentException](xref:System.ArgumentException) if the [DateTime](xref:System.DateTime) object's [Kind](xref:System.DateTimeKind) property and the time zone are mismatched.</span></span> <span data-ttu-id="1aa7a-137">Ein solcher Fall tritt auf, wenn die Kind-Eigenschaft [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet, aber das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt nicht die lokale Zeitzone darstellt, oder wenn die Kind-Eigenschaft [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, aber das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt nicht gleich [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) ist.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-137">A mismatch occurs if the Kind property is [DateTimeKind.Local](xref:System.DateTimeKind.Local) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not represent the local time zone, or if the Kind property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

<span data-ttu-id="1aa7a-138">All diese Methoden akzeptieren [DateTime](xref:System.DateTime)-Werte als Parameter und geben einen [DateTime](xref:System.DateTime)-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-138">All of these methods take [DateTime](xref:System.DateTime) values as parameters and return a [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="1aa7a-139">Für [DateTimeOffset](xref:System.DateTimeOffset)-Werte besitzt die [DateTimeOffset](xref:System.DateTimeOffset)-Struktur eine [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Instanzmethode, die das Datum und die Uhrzeit der aktuellen Instanz in die UTC konvertiert.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-139">For [DateTimeOffset](xref:System.DateTimeOffset) values, the [DateTimeOffset](xref:System.DateTimeOffset) structure has a [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="1aa7a-140">Das folgende Beispiel ruft die [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Methode auf, um eine lokale Uhrzeit sowie verschiedene weitere Uhrzeiten in die koordinierte Weltzeit zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-140">The following example calls the [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

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

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="1aa7a-141">Konvertieren der UTC in eine festgelegte Zeitzone</span><span class="sxs-lookup"><span data-stu-id="1aa7a-141">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="1aa7a-142">Informationen zum Konvertieren der UTC in eine lokale Uhrzeit finden Sie im nächsten Abschnitt, [Konvertieren der UTC in eine lokale Zeit](#converting-utc-to-local-time).</span><span class="sxs-lookup"><span data-stu-id="1aa7a-142">To convert UTC to local time, see the [Converting UTC to local time](#converting-utc-to-local-time) section that follows.</span></span> 

<span data-ttu-id="1aa7a-143">Um die UTC in die Uhrzeit einer von Ihnen festgelegten Zeitzone zu konvertieren, rufen Sie die [ConvertTimeFromUtc](https://msdn.microsoft.com/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx)-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-143">To convert UTC to the time in any time zone that you designate, call the [ConvertTimeFromUtc](https://msdn.microsoft.com/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1aa7a-144">Die Methode „TimeZoneInfo.ConvertTimeFromUtc“ ist in .NET Core zurzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-144">The \`TimeZoneInfo.ConvertTimeFromUtc' method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="1aa7a-145">Die Methode akzeptiert zwei Parameter:</span><span class="sxs-lookup"><span data-stu-id="1aa7a-145">The method takes two parameters:</span></span>

* <span data-ttu-id="1aa7a-146">Die zu konvertierende UTC.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-146">The UTC to convert.</span></span> <span data-ttu-id="1aa7a-147">Hierbei muss es sich um einen [DateTime](xref:System.DateTime)-Wert handeln, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) oder [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-147">This must be a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> 

* <span data-ttu-id="1aa7a-148">Die Zeitzone, in die die UTC konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-148">The time zone to convert the UTC to.</span></span> 

<span data-ttu-id="1aa7a-149">Der folgende Code konvertiert die UTC in die Central Standard Time.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-149">The following code converts UTC to Central Standard Time.</span></span>

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

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="1aa7a-150">Konvertieren der UTC in eine lokale Zeit</span><span class="sxs-lookup"><span data-stu-id="1aa7a-150">Converting UTC to local time</span></span>

<span data-ttu-id="1aa7a-151">Um die UTC in eine lokale Zeit zu konvertieren, rufen Sie die [DateTime.ToLocalTime](xref:System.DateTime)-Methode des [DateTime](xref:System.DateTime)-Objekts auf, dessen Zeit Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-151">To convert UTC to local time, call the [DateTime.ToLocalTime](xref:System.DateTime) method of the [DateTime](xref:System.DateTime) object whose time you want to convert.</span></span> <span data-ttu-id="1aa7a-152">Das genaue Verhalten der Methode richtet sich nach dem Wert der [Kind](xref:System.DateTime.Kind)-Eigenschaft des Objekts, wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-152">The exact behavior of the method depends on the value of the object’s [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="1aa7a-153">[DateTime.Kind](xref:System.DateTimeKind)-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1aa7a-153">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="1aa7a-154">Umwandeln</span><span class="sxs-lookup"><span data-stu-id="1aa7a-154">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="1aa7a-155">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="1aa7a-155">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="1aa7a-156">Gibt den [DateTime](xref:System.DateTime)-Wert unverändert zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-156">Returns the [DateTime](xref:System.DateTime) value unchanged.</span></span>
[<span data-ttu-id="1aa7a-157">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="1aa7a-157">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="1aa7a-158">Nimmt an, dass der [DateTime](xref:System.DateTime)-Wert als UTC vorliegt, und konvertiert die UTC in die lokale Zeit.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-158">Assumes that the [DateTime](xref:System.DateTime) value is UTC and converts the UTC to local time.</span></span>
[<span data-ttu-id="1aa7a-159">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="1aa7a-159">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="1aa7a-160">Konvertiert den [DateTime](xref:System.DateTime)-Wert in die lokale Zeit.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-160">Converts the [DateTime](xref:System.DateTime) value to local time.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="1aa7a-161">Konvertieren zwischen zwei beliebigen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="1aa7a-161">Converting between any two time zones</span></span>

<span data-ttu-id="1aa7a-162">Sie können mithilfe der statischen [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode eine zwischen zwei beliebigen Zeitzonen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-162">You can convert between any two time zones by using the static [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> <span data-ttu-id="1aa7a-163">Die Parameter dieser Methode sind der zu konvertierende [DateTime](xref:System.DateTime)-Wert, ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone des Datums- und Uhrzeitwerts darstellt, und ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone darstellt, in die der Datums- und Uhrzeitwert konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-163">This method's parameters are the [DateTime](xref:System.DateTime) value to convert, a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone of the date and time value, and a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="1aa7a-164">Diese Methode erfordert, dass die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zu konvertierenden Datums- und Uhrzeitwerts und das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt bzw. der Zeitzonenbezeichner, der die Zeitzone repräsentiert, einander entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-164">The method requires that the [Kind](xref:System.DateTime.Kind) property of the date and time value to convert and the [TimeZoneInfo](xref:System.TimeZoneInfo) object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="1aa7a-165">Andernfalls wird eine [ArgumentException](xref:System.ArgumentException) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-165">Otherwise, an [ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="1aa7a-166">Wenn z.B. die [Kind](xref:System.DateTime.Kind)-Eigenschaft des Datums- und Uhrzeitwerts [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet und das als Parameter an die Methode übergebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt ungleich [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-166">For example, if the [Kind](xref:System.DateTime.Kind) property of the date and time value is [DateTimeKind.Local](xref:System.DateTimeKind.Local), an exception is thrown if the [TimeZoneInfo](xref:System.TimeZoneInfo) object passed as a parameter to the method is not equal to [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span></span> <span data-ttu-id="1aa7a-167">Es wird ebenfalls eine Ausnahme ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner ungleich [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) ist.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-167">An exception is also thrown if the identifier passed as a parameter to the method is not equal to [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span></span>

<span data-ttu-id="1aa7a-168">Das folgende Beispiel verwendet die [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode, um aus der Hawaiian Standard Time in die lokale Zeit zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-168">The following example uses the [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method to convert from Hawaiian Standard Time to local time.</span></span>

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

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="1aa7a-169">Konvertieren von DateTimeOffset-Werten</span><span class="sxs-lookup"><span data-stu-id="1aa7a-169">Converting DateTimeOffset values</span></span>

<span data-ttu-id="1aa7a-170">Datums- und Uhrzeitwerte, die durch [System.DateTimeOffset](xref:System.DateTimeOffset)-Objekte dargestellt werden, berücksichtigen die Zeitzone nicht vollständig, weil das Objekt zum Zeitpunkt der Instanziierung nicht mit der zugehörigen Zeitzone verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-170">Date and time values represented by [System.DateTimeOffset](xref:System.DateTimeOffset) objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="1aa7a-171">In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-171">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="1aa7a-172">Um diese Konvertierung auszuführen, können Sie die [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan))-Methode der aktuellen Instanz aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-172">To perform this conversion, you can call the current instance's [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) method.</span></span> <span data-ttu-id="1aa7a-173">Der einzige Parameter dieser Methode ist [TimeSpan](xref:System.TimeSpan), der die Abweichung vom neuen Datums- und Uhrzeitwert darstellt, den die Methode zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-173">The method's single parameter is [TimeSpan](xref:System.TimeSpan) representing the offset of the new date and time value that the method is to return.</span></span>  

<span data-ttu-id="1aa7a-174">Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-174">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

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

<span data-ttu-id="1aa7a-175">Beispiel: An diese Methode wird die Zeichenfolge „9/1/2007 5:32:07 -05:00“ übergeben. Diese stellt das Datum und die Uhrzeit in einer Zeitzone dar, die fünf Stunden vor der UTC liegt. In diesem Fall gibt die Methode den Wert „9/1/2007 3:32:07 AM -07:00“ zurück, wenn sich der Server in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-175">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="1aa7a-176">Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse enthält auch eine überladene [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo))-Methode, die Zeitzonenkonvertierungen mit [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten ausführt.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-176">The [TimeZoneInfo](xref:System.TimeZoneInfo) class also includes an overloaded [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method that performs time zone conversions with [System.DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="1aa7a-177">Die Parameter der Methode sind ein [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-177">The method's parameters are a [System.DateTimeOffset](xref:System.DateTimeOffset) value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="1aa7a-178">Der Methodenaufruf gibt einen [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-178">The method call returns a [System.DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="1aa7a-179">Die `ReturnTimeOnServer`-Methode im vorherigen Beispiel könnte auch folgendermaßen neu geschrieben werden, um die [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo))-Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="1aa7a-179">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1aa7a-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aa7a-180">See also</span></span>

[<span data-ttu-id="1aa7a-181">TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="1aa7a-181">TimeZoneInfo</span></span>](xref:System.TimeZoneInfo)

[<span data-ttu-id="1aa7a-182">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="1aa7a-182">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="1aa7a-183">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="1aa7a-183">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)



