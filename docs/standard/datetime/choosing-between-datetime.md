---
title: "Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo"
description: "Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: aeb1928be32584ee4b6acf7c9a4f4330daedc590
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a><span data-ttu-id="16ae9-104">Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="16ae9-104">Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>

<span data-ttu-id="16ae9-105">.NET-Anwendungen, die Datums- und Uhrzeitinformationen verwenden, sind sehr vielfältig und können diese Informationen auf verschiedene Weise verwenden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-105">.NET applications that use date and time information are very diverse and can use that information in several ways.</span></span> <span data-ttu-id="16ae9-106">Die häufigeren Verwendungsarten von Datums- und Uhrzeitinformationen sind mindestens eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="16ae9-106">The more common uses of date and time information include one or more of the following:</span></span>

* <span data-ttu-id="16ae9-107">Darstellen eines reinen Datums, damit Zeitinformationen unberücksichtigt bleiben.</span><span class="sxs-lookup"><span data-stu-id="16ae9-107">To reflect a date only, so that time information is not important.</span></span>

* <span data-ttu-id="16ae9-108">Darstellen einer reinen Uhrzeit, damit Datumsinformationen unberücksichtigt bleiben.</span><span class="sxs-lookup"><span data-stu-id="16ae9-108">To reflect a time only, so that date information is not important.</span></span>

* <span data-ttu-id="16ae9-109">Darstellen eines abstrakten Datums mit Uhrzeit, die an keine bestimmte Zeit und keinen bestimmten Ort gebunden sind (z. B. öffnen die meisten Geschäfte einer internationalen Kette an Wochentagen um 9:00 Uhr).</span><span class="sxs-lookup"><span data-stu-id="16ae9-109">To reflect an abstract date and time that is not tied to a specific time and place (for example, most stores in an international chain open on weekdays at 9:00 A.M.).</span></span>

* <span data-ttu-id="16ae9-110">Abrufen von Datums- und Uhrzeitinformationen aus Quellen außerhalb der .NET-Anwendung, typischerweise wo Datums- und Uhrzeitinformationen in einem einfachen Datentyp gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="16ae9-110">To retrieve date and time information from sources outside of the .NET application, typically where date and time information is stored in a simple data type.</span></span>

* <span data-ttu-id="16ae9-111">Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts.</span><span class="sxs-lookup"><span data-stu-id="16ae9-111">To uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="16ae9-112">Einige Anwendungen erfordern, dass ein Datum und eine Uhrzeit eindeutig sind, nur auf dem Hostsystem. Andere erfordern, dass sie über Systeme hinweg eindeutig sind (d. h. ein auf dem einen System serialisiertes Datum kann weltweit auf einem anderen System sinnvoll deserialisiert und verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="16ae9-112">Some applications require that a date and time be unambiguous only on the host system; others require that it be unambiguous across systems (that is, a date serialized on one system can be meaningfully deserialized and used on another system anywhere in the world).</span></span> 

* <span data-ttu-id="16ae9-113">Erhalten mehrerer verwandter Zeiten (z. B. die lokale Zeit des Anforderers und die Empfangszeit des Servers für eine Webanforderung).</span><span class="sxs-lookup"><span data-stu-id="16ae9-113">To preserve multiple related times (such as the requestor's local time and the server's time of receipt for a Web request).</span></span>

* <span data-ttu-id="16ae9-114">Durchführen von Datums- und Uhrzeitberechnungen, möglicherweise mit einem Ergebnis, das einen einzigen Zeitpunkt eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="16ae9-114">To perform date and time arithmetic, possibly with a result that uniquely and unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="16ae9-115">.NET enthält die [System.DateTime](xref:System.DateTime)-, [System.DateTimeOffset](xref:System.DateTimeOffset)-, [System.TimeSpan](xref:System.TimeSpan)- und [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Typen, mit denen Anwendungen erstellt werden können, die mit Datums- und Uhrzeitangaben arbeiten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-115">.NET includes the [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), and [System.TimeZoneInfo](xref:System.TimeZoneInfo) types, all of which can be used to build applications that work with dates and times.</span></span> 

> [!NOTE]
> <span data-ttu-id="16ae9-116">In diesem Thema wird der ältere `TimeZone`-Typ nicht behandelt, weil seine Funktionalität nahezu vollständig in der [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="16ae9-116">This topic does not discuss the older `TimeZone` type, because its functionality is almost entirely incorporated in the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class.</span></span> <span data-ttu-id="16ae9-117">Nach Möglichkeit sollten Entwickler die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse anstelle der `TimeZone`-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-117">Whenever possible, developers should use the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class instead of the `TimeZone` class.</span></span>


## <a name="the-datetime-structure"></a><span data-ttu-id="16ae9-118">Die DateTime-Struktur</span><span class="sxs-lookup"><span data-stu-id="16ae9-118">The DateTime structure</span></span>

<span data-ttu-id="16ae9-119">Ein [System.DateTime](xref:System.DateTime)-Wert definiert ein bestimmtes Datum und eine Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="16ae9-119">A [System.DateTime](xref:System.DateTime) value defines a particular date and time.</span></span> <span data-ttu-id="16ae9-120">Er enthält eine [Kind](xref:System.DateTime.Kind)-Eigenschaft, die eingeschränkte Informationen über die Zeitzone bietet, zu der dieses Datum und die Uhrzeit gehören.</span><span class="sxs-lookup"><span data-stu-id="16ae9-120">It includes a [Kind](xref:System.DateTime.Kind) property that provides limited information about the time zone to which that date and time belongs.</span></span> <span data-ttu-id="16ae9-121">Der [DateTimeKind](xref:System.DateTimeKind)-Rückgabewert der [Kind](xref:System.DateTime.Kind)-Eigenschaft gibt an, ob der [DateTime](xref:System.DateTime)-Wert die Ortszeit ([DateTimeKind.Local](xref:System.DateTimeKind.Local)), die koordinierte Weltzeit (Coordinated Universal Time, UTC) ([DateTimeKind.Utc](xref:System.DateTimeKind.Utc)) oder eine unspezifische Uhrzeit ([DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)) angibt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-121">The [DateTimeKind](xref:System.DateTimeKind) value returned by the [Kind](xref:System.DateTime.Kind) property indicates whether the [DateTime](xref:System.DateTime) value represents the local time [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), or an unspecified time [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span>

<span data-ttu-id="16ae9-122">Die [DateTime](xref:System.DateTime)-Struktur eignet sich für Anwendungen, die Folgendes können:</span><span class="sxs-lookup"><span data-stu-id="16ae9-122">The [DateTime](xref:System.DateTime) structure is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="16ae9-123">Nur mit Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-123">Work with dates only.</span></span>

* <span data-ttu-id="16ae9-124">Nur mit Uhrzeiten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-124">Work with times only.</span></span>

* <span data-ttu-id="16ae9-125">Mit abstrakten Datums- und Uhrzeitwerten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-125">Work with abstract dates and times.</span></span>

* <span data-ttu-id="16ae9-126">Mit Datums- und Uhrzeitwerten arbeiten, für die Zeitzoneninformationen fehlen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-126">Work with dates and times for which time zone information is missing.</span></span> 

* <span data-ttu-id="16ae9-127">Nur mit UTC-Datums- und Uhrzeitwerten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-127">Work with UTC dates and times only.</span></span> 

* <span data-ttu-id="16ae9-128">Datums- und Uhrzeitinformationen aus Quellen außerhalb von .NET Framework abrufen, wie SQL-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="16ae9-128">Retrieve date and time information from sources outside the .NET Framework, such as SQL databases.</span></span> <span data-ttu-id="16ae9-129">In der Regel speichern diese Quellen Datums- und Uhrzeitinformationen in einem einfachen Format, das mit der [DateTime](xref:System.DateTime)-Struktur kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="16ae9-129">Typically, these sources store date and time information in a simple format that is compatible with the [DateTime](xref:System.DateTime) structure.</span></span>

* <span data-ttu-id="16ae9-130">Arithmetische Operationen mit Datums- und Uhrzeitwerten durchführen, wobei aber allgemeine Ergebnisse von Belang sind.</span><span class="sxs-lookup"><span data-stu-id="16ae9-130">Perform date and time arithmetic, but are concerned with general results.</span></span> <span data-ttu-id="16ae9-131">Beispielsweise ist es bei einer Additionsoperation, bei der einem bestimmten Datum und einer Uhrzeit sechs Monate hinzuaddiert werden, oft nicht wichtig, ob das Ergebnis hinsichtlich der Sommerzeit angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="16ae9-131">For example, in an addition operation that adds six months to a particular date and time, it is often not important whether the result is adjusted for daylight saving time.</span></span>

<span data-ttu-id="16ae9-132">Wenn nicht ein bestimmter [DateTime](xref:System.DateTime)-Wert UTC darstellt, ist dieser Datums- und Uhrzeitwert häufig mehrdeutig oder in seiner Portierbarkeit eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-132">Unless a particular [DateTime](xref:System.DateTime) value represents UTC, that date and time value is often ambiguous or limited in its portability.</span></span> <span data-ttu-id="16ae9-133">Wenn z.B. ein [DateTime](xref:System.DateTime)-Wert die lokale Uhrzeit darstellt, ist er innerhalb dieser lokalen Zeitzone portierbar (d.h., wenn der Wert auf einem anderen System in der gleichen Zeitzone deserialisiert wird, identifiziert dieser Wert immer noch eindeutig einen einzigen Zeitpunkt).</span><span class="sxs-lookup"><span data-stu-id="16ae9-133">For example, if a [DateTime](xref:System.DateTime) value represents the local time, it is portable within that local time zone (that is, if the value is deserialized on another system in the same time zone, that value still unambiguously identifies a single point in time).</span></span> <span data-ttu-id="16ae9-134">Außerhalb der lokalen Zeitzone kann dieser [DateTime](xref:System.DateTime)-Wert über mehrere Interpretationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-134">Outside the local time zone, that [DateTime](xref:System.DateTime) value can have multiple interpretations.</span></span> <span data-ttu-id="16ae9-135">Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des Werts [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) ist, ist er sogar noch weniger portierbar: Er ist jetzt innerhalb der gleichen Zeitzone mehrdeutig und möglicherweise sogar auf dem gleichen System, auf dem er erstmalig serialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="16ae9-135">If the value's [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), it is even less portable: it is now ambiguous within the same time zone and possibly even on the same system on which it was first serialized.</span></span> <span data-ttu-id="16ae9-136">Nur wenn ein [DateTime](xref:System.DateTime)-Wert eine UTC-Zeit darstellt, identifiziert dieser Wert eindeutig einen einzigen Zeitpunkt, unabhängig vom System oder der Zeitzone, in der der Wert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="16ae9-136">Only if a [DateTime](xref:System.DateTime) value represents UTC does that value unambiguously identify a single point in time regardless of the system or time zone in which the value is used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16ae9-137">Beim Speichern oder Freigeben von [DateTime](xref:System.DateTime)-Daten sollte UTC verwendet werden, und die [Kind](xref:System.DateTime.Kind)-Eigenschaft des [DateTime](xref:System.DateTime)-Werts sollte auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-137">When saving or sharing [DateTime](xref:System.DateTime) data, UTC should be used and the [DateTime](xref:System.DateTime) value's [Kind](xref:System.DateTime.Kind) property should be set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="the-datetimeoffset-structure"></a><span data-ttu-id="16ae9-138">Die DateTimeOffset-Struktur</span><span class="sxs-lookup"><span data-stu-id="16ae9-138">The DateTimeOffset structure</span></span>

<span data-ttu-id="16ae9-139">Die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur stellt einen Datums- und Uhrzeitwert zusammen mit einem Offset dar, der angibt, um wie viel dieser Wert von UTC abweicht.</span><span class="sxs-lookup"><span data-stu-id="16ae9-139">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure represents a date and time value, together with an offset that indicates how much that value differs from UTC.</span></span> <span data-ttu-id="16ae9-140">Somit identifiziert der Wert immer eindeutig einen einzigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-140">Thus, the value always unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="16ae9-141">Der [DateTimeOffset](xref:System.DateTimeOffset)-Typ bietet die gesamte Funktionalität des [DateTime](xref:System.DateTime)-Typs plus Unterstützung von Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-141">The [DateTimeOffset](xref:System.DateTimeOffset) type includes all of the functionality of the [DateTime](xref:System.DateTime) type along with time zone awareness.</span></span> <span data-ttu-id="16ae9-142">Dadurch eignet er sich für Anwendungen, die Folgendes unterstützen:</span><span class="sxs-lookup"><span data-stu-id="16ae9-142">This makes it is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="16ae9-143">Eindeutiges und unzweideutiges Identifizieren eines einzigen Zeitpunkts.</span><span class="sxs-lookup"><span data-stu-id="16ae9-143">Uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="16ae9-144">Der [DateTimeOffset](xref:System.DateTimeOffset)-Typ kann zur eindeutigen Definition der Bedeutung von „jetzt“ verwendet werden, um Transaktionszeiten zu protokollieren, die Zeiten von System- oder Anwendungsereignissen zu protokollieren und um die Zeiten der Erstellung und Änderung von Dateien aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-144">The [DateTimeOffset](xref:System.DateTimeOffset) type can be used to unambiguously define the meaning of "now", to log transaction times, to log the times of system or application events, and to record file creation and modification times.</span></span> 

* <span data-ttu-id="16ae9-145">Ausführen von allgemeinen Datums- und Uhrzeitberechnungen</span><span class="sxs-lookup"><span data-stu-id="16ae9-145">Perform general date and time arithmetic.</span></span>

* <span data-ttu-id="16ae9-146">Erhalten mehrerer verwandter Uhrzeiten, solange diese Zeiten als zwei gesonderte Werte oder als zwei Member einer Struktur gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-146">Preserve multiple related times, as long as those times are stored as two separate values or as two members of a structure.</span></span>

> [!NOTE]
> <span data-ttu-id="16ae9-147">Diese Verwendungsarten für [DateTimeOffset](xref:System.DateTimeOffset)-Werte sind sehr viel häufiger als die für [DateTime](xref:System.DateTime)-Werte.</span><span class="sxs-lookup"><span data-stu-id="16ae9-147">These uses for [DateTimeOffset](xref:System.DateTimeOffset) values are much more common than those for [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="16ae9-148">Demzufolge sollte in der Anwendungsentwicklung [DateTimeOffset](xref:System.DateTimeOffset) als Standardtyp für Datum und Uhrzeit angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-148">As a result, [DateTimeOffset](xref:System.DateTimeOffset) should be considered the default date and time type for application development.</span></span>

<span data-ttu-id="16ae9-149">Ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert ist nicht an eine bestimmte Zeitzone gebunden, kann aber aus jeder der zahlreichen Zeitzonen stammen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-149">A [DateTimeOffset](xref:System.DateTimeOffset) value is not tied to a particular time zone, but can originate from any of a variety of time zones.</span></span> <span data-ttu-id="16ae9-150">Um dies zu veranschaulichen, listet das folgende Beispiel die Zeitzonen auf, zu denen eine Reihe von [DateTimeOffset](xref:System.DateTimeOffset)-Werten (einschließlich eines Werts in lokaler Pacific Normalzeit) gehören können.</span><span class="sxs-lookup"><span data-stu-id="16ae9-150">To illustrate this, the following example lists the time zones to which a number of [DateTimeOffset](xref:System.DateTimeOffset) values (including a local Pacific Standard Time) can belong.</span></span>

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

<span data-ttu-id="16ae9-151">Die Ausgabe zeigt, dass jeder Datums- und Uhrzeitwert in diesem Beispiel zu mindestens drei verschiedenen Zeitzonen gehören kann.</span><span class="sxs-lookup"><span data-stu-id="16ae9-151">The output shows that each date and time value in this example can belong to at least three different time zones.</span></span> <span data-ttu-id="16ae9-152">Der [DateTimeOffset](xref:System.DateTimeOffset)-Wert „6/10/2007“ zeigt, dass, wenn ein Datums- und Uhrzeitwert eine Sommerzeit darstellt, sein Offset von UTC noch nicht einmal unbedingt dem UTC-Basisoffset der Ursprungszeitzone oder dem in seinem Anzeigenamen vorgefundenen Offset von UTC entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="16ae9-152">The [DateTimeOffset](xref:System.DateTimeOffset) value of 6/10/2007 shows that if a date and time value represents a daylight saving time, its offset from UTC does not even necessarily correspond to the originating time zone's base UTC offset or to the offset from UTC found in its display name.</span></span> <span data-ttu-id="16ae9-153">Dies bedeutet: Weil ein einzelner [DateTimeOffset](xref:System.DateTimeOffset)-Wert nicht eng mit seiner Zeitzone verknüpft ist, kann er nicht den Übergang einer Zeitzone zur und aus der Sommerzeit wiedergeben.</span><span class="sxs-lookup"><span data-stu-id="16ae9-153">This means that, because a single [DateTimeOffset](xref:System.DateTimeOffset)  value is not tightly coupled with its time zone, it cannot reflect a time zone's transition to and from daylight saving time.</span></span> <span data-ttu-id="16ae9-154">Dies kann besonders problematisch sein, wenn ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert mithilfe von Datums- und Uhrzeitberechnungen manipuliert wird.</span><span class="sxs-lookup"><span data-stu-id="16ae9-154">This can be particularly problematic when date and time arithmetic is used to manipulate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="16ae9-155">Eine Erläuterung der Durchführung von Datums- und Uhrzeitberechnungen auf eine Weise, die die Anpassungsregeln einer Zeitzone berücksichtigt, finden Sie unter [Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md).</span><span class="sxs-lookup"><span data-stu-id="16ae9-155">For a discussion of how to perform date and time arithmetic in a way that takes account of a time zone's adjustment rules, see [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md).</span></span>

## <a name="the-timespan-structure"></a><span data-ttu-id="16ae9-156">Die TimeSpan-Struktur</span><span class="sxs-lookup"><span data-stu-id="16ae9-156">The TimeSpan structure</span></span>

<span data-ttu-id="16ae9-157">Die [System.TimeSpan](xref:System.TimeSpan)-Struktur stellt ein Zeitintervall dar.</span><span class="sxs-lookup"><span data-stu-id="16ae9-157">The [System.TimeSpan](xref:System.TimeSpan) structure represents a time interval.</span></span> <span data-ttu-id="16ae9-158">Sein zwei typischen Anwendungsmöglichkeiten sind:</span><span class="sxs-lookup"><span data-stu-id="16ae9-158">Its two typical uses are:</span></span> 

* <span data-ttu-id="16ae9-159">Darstellen des Zeitintervalls zwischen zwei Datums- und Uhrzeitwerten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-159">Reflecting the time interval between two date and time values.</span></span> <span data-ttu-id="16ae9-160">Beispielsweise gibt die Subtraktion eines [DateTime](xref:System.DateTime)-Werts von einem anderen einen [TimeSpan](xref:System.TimeSpan)-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="16ae9-160">For example, subtracting one [DateTime](xref:System.DateTime) value from another returns a [TimeSpan](xref:System.TimeSpan) value.</span></span> 

* <span data-ttu-id="16ae9-161">Messen der verstrichenen Zeit.</span><span class="sxs-lookup"><span data-stu-id="16ae9-161">Measuring elapsed time.</span></span> <span data-ttu-id="16ae9-162">Beispielsweise gibt die [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed)-Eigenschaft einen [TimeSpan](xref:System.TimeSpan)-Wert zurück, der das Zeitintervall angibt, das seit dem Aufrufen einer der [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch)-Methoden, die verstrichene Zeit zu messen beginnen, verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="16ae9-162">For example, the [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) property returns a [TimeSpan](xref:System.TimeSpan) value that reflects the time interval that has elapsed since the call to one of the [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) methods that begins to measure elapsed time.</span></span>

<span data-ttu-id="16ae9-163">Ein [TimeSpan](xref:System.TimeSpan)-Wert kann auch als Ersatz für einen [DateTime](xref:System.DateTime)-Wert verwendet werden, wenn dieser Wert eine Uhrzeit ohne Verweis auf eine bestimmte Tageszeit widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-163">A [TimeSpan](xref:System.TimeSpan) value can also be used as a replacement for a [DateTime](xref:System.DateTime) value when that value reflects a time without reference to a particular time of day.</span></span> <span data-ttu-id="16ae9-164">Diese Verwendung ähnelt den Eigenschaften [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) und [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), die einen [TimeSpan](xref:System.TimeSpan)-Wert zurückgeben, der die Uhrzeit ohne Verweis auf ein Datum darstellt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-164">This usage is similar to the [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) and [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) properties, which return a [TimeSpan](xref:System.TimeSpan) value that represents the time without reference to a date.</span></span> <span data-ttu-id="16ae9-165">Beispielsweise kann die [TimeSpan](xref:System.TimeSpan)-Struktur verwendet werden, um die täglichen Öffnungszeiten eines Geschäfts darzustellen oder um die Uhrzeit darzustellen, zu der alle regulären Ereignisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="16ae9-165">For example, the [TimeSpan](xref:System.TimeSpan) structure can be used to reflect a store's daily opening or closing time, or it can be used to represent the time at which any regular event occurs.</span></span>

<span data-ttu-id="16ae9-166">Das folgende Beispiel definiert eine `StoreInfo`-Struktur, die [TimeSpan](xref:System.TimeSpan)-Objekte für Öffnungszeiten von Geschäften enthält, sowie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt, das die Zeitzone des Geschäfts darstellt.</span><span class="sxs-lookup"><span data-stu-id="16ae9-166">The following example defines a `StoreInfo` structure that includes [TimeSpan](xref:System.TimeSpan) objects for store opening and closing times, as well as a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the store's time zone.</span></span> <span data-ttu-id="16ae9-167">Die Struktur enthält außerdem zwei Methoden, `IsOpenNow` und `IsOpenAt`, die angeben, ob das Geschäft zu einem vom Benutzer angegebenen Zeitpunkt geöffnet ist, wobei angenommen wird, dass er sich in der lokalen Zeitzone aufhält.</span><span class="sxs-lookup"><span data-stu-id="16ae9-167">The structure also includes two methods, `IsOpenNow` and `IsOpenAt`, that indicates whether the store is open at a time specified by the user, who is assumed to be in the local time zone.</span></span>  

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

<span data-ttu-id="16ae9-168">Die `StoreInfo`-Struktur kann dann von Clientcode wie folgt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16ae9-168">The `StoreInfo` structure can then be used by client code like the following.</span></span> 

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

## <a name="the-timezoneinfo-class"></a><span data-ttu-id="16ae9-169">Die TimeZoneInfo-Klasse</span><span class="sxs-lookup"><span data-stu-id="16ae9-169">The TimeZoneInfo class</span></span>

<span data-ttu-id="16ae9-170">Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse stellt eine beliebige Zeitzone der Erde dar und ermöglicht die Konvertierung jeglicher Datums- und Uhrzeitwerte in einer in die entsprechenden Werte in einer anderen Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="16ae9-170">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class represents any of the earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone.</span></span> <span data-ttu-id="16ae9-171">Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse ermöglicht das Arbeiten mit Datums- und Zeitwerten, sodass jeder Datums- und Uhrzeitwert eindeutig einen einzigen Zeitpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="16ae9-171">The [TimeZoneInfo](xref:System.TimeZoneInfo) class makes it possible to work with dates and times so that any date and time value unambiguously identifies a single point in time.</span></span>

<span data-ttu-id="16ae9-172">In einigen Fällen kann noch weitere Entwicklungsarbeit erforderlich sein, um die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse optimal zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-172">In some cases, taking full advantage of the [TimeZoneInfo](xref:System.TimeZoneInfo) class may require further development work.</span></span> <span data-ttu-id="16ae9-173">Datums-und Uhrzeitwerte sind nicht eng mit den Zeitzonen verknüpft, zu denen sie gehören.</span><span class="sxs-lookup"><span data-stu-id="16ae9-173">Date and time values are not tightly coupled with the time zones to which they belong.</span></span> <span data-ttu-id="16ae9-174">Daher kann die Zuordnung eines Datums- und Uhrzeitwerts zu seiner Zeitzone leicht aufgehoben werden, wenn Ihre Anwendung nicht einen Mechanismus bereitstellt, um ein Datum und eine Uhrzeit mit der zugehörigen Zeitzone zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-174">As a result, unless your application provides some mechanism for linking a date and time with its associated time zone, it is easy for a particular date and time value to become disassociated from its time zone.</span></span> <span data-ttu-id="16ae9-175">Eine Methode zum Verknüpfen dieser Informationen besteht darin, eine Klasse oder Struktur zu definieren, die sowohl den Datums- und Zeitwert als auch sein zugeordnetes Zeitzonenobjekt enthält.</span><span class="sxs-lookup"><span data-stu-id="16ae9-175">One method of linking this information is to define a class or structure that contains both the date and time value and its associated time zone object.</span></span>

<span data-ttu-id="16ae9-176">Die Zeitzonenunterstützung in .NET kann nur genutzt werden, wenn die Zeitzone, zu der ein Datums- und Uhrzeitwert gehört, bekannt ist, wenn das Datums- und Uhrzeitobjekt instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="16ae9-176">Taking advantage of time zone support in .NET is possible only if the time zone to which a date and time value belongs is known when that date and time object is instantiated.</span></span> <span data-ttu-id="16ae9-177">Dies ist häufig nicht der Fall, insbesondere bei Web-oder Netzwerkanwendungen.</span><span class="sxs-lookup"><span data-stu-id="16ae9-177">This is often not the case, particularly in Web or network applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="16ae9-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16ae9-178">See Also</span></span>

[<span data-ttu-id="16ae9-179">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="16ae9-179">Dates, times, and time zones</span></span>](index.md)
