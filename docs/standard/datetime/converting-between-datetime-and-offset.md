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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2ba70e9ea39148d040bdb46d5e00ea50dcbb8980
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="7db2d-104">Konvertieren zwischen DateTime und DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7db2d-104">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="7db2d-105">Obwohl die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur eine umfassendere Zeitzonenunterstützung bietet als die [System.DateTime](xref:System.DateTime)-Struktur, werden [DateTime](xref:System.DateTime)-Parameter häufiger in Methodenaufrufen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7db2d-105">Although the [System.DateTimeOffset](xref:System.DateTimeOffset) structure provides a greater degree of time zone awareness than the [System.DateTime](xref:System.DateTime) structure, [DateTime](xref:System.DateTime) parameters are used more commonly in method calls.</span></span> <span data-ttu-id="7db2d-106">Aus diesem Grund ist die Fähigkeit sehr wichtig, [DateTimeOffset](xref:System.DateTimeOffset)-Werte in [DateTime](xref:System.DateTime)-Werte und umgekehrt zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7db2d-106">Because of this, the ability to convert [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values and vice versa is particularly important.</span></span> <span data-ttu-id="7db2d-107">Dieser Artikel zeigt, wie Sie diese Konvertierungen auf eine Weise ausführen, bei der so viele Zeitzoneninformationen wie möglich beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="7db2d-107">This article shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="7db2d-108">Sowohl der [DateTime](xref:System.DateTime)- als auch der [DateTimeOffset](xref:System.DateTimeOffset)-Typ weisen einige Einschränkungen hinsichtlich der Darstellung von Zeiten in Zeitzonen auf.</span><span class="sxs-lookup"><span data-stu-id="7db2d-108">Both the [DateTime](xref:System.DateTime) and the [DateTimeOffset](xref:System.DateTimeOffset) types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="7db2d-109">Mit der Eigenschaft [Kind](xref:System.DateTime.Kind) kann [DateTime](xref:System.DateTime) nur die koordinierte Weltzeit (UTC) und die lokale Zeitzone des Systems widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="7db2d-109">With its [Kind](xref:System.DateTime.Kind) property, [DateTime](xref:System.DateTime) is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="7db2d-110">[DateTimeOffset](xref:System.DateTimeOffset) gibt die Abweichung einer Uhrzeit von der UTC wieder, aber nicht die tatsächliche Zeitzone, zu der diese Abweichung gehört.</span><span class="sxs-lookup"><span data-stu-id="7db2d-110">[DateTimeOffset](xref:System.DateTimeOffset) reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="7db2d-111">Detaillierte Informationen zu Uhrzeitwerten und zur Unterstützung von Zeitzonen finden Sie unter [Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="7db2d-111">For details about time values and support for time zones, see [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="7db2d-112">Konvertierungen von DateTime in DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7db2d-112">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="7db2d-113">Die [DateTimeOffset](xref:System.DateTimeOffset)-Struktur bietet zwei gleichwertige Möglichkeiten zum Konvertieren von [DateTime](xref:System.DateTime) in [DateTimeOffset](xref:System.DateTimeOffset), die sich für die meisten Konvertierungen eignen:</span><span class="sxs-lookup"><span data-stu-id="7db2d-113">The [DateTimeOffset](xref:System.DateTimeOffset) structure provides two equivalent ways to perform [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="7db2d-114">Der [DateTimeOffset(DateTime)](xref:System.DateTimeOffset)-Konstruktor, der ein neues [DateTimeOffset](xref:System.DateTimeOffset)-Objekt basierend auf einem [DateTime](xref:System.DateTime)-Wert erstellt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-114">The [DateTimeOffset(DateTime)](xref:System.DateTimeOffset) constructor, which creates a new [DateTimeOffset](xref:System.DateTimeOffset) object based on a [DateTime](xref:System.DateTime) value.</span></span>

* <span data-ttu-id="7db2d-115">Der implizite Konvertierungsoperator, mit dem Sie einem [DateTimeOffset](xref:System.DateTimeOffset)-Objekt einen [DateTime](xref:System.DateTime)-Wert zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="7db2d-115">The implicit conversion operator, which allows you to assign a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

<span data-ttu-id="7db2d-116">Für UTC und lokale [DateTime](xref:System.DateTime)-Werte gibt die [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset)-Eigenschaft des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts exakt die UTC-Abweichung oder Abweichung der lokalen Zeitzone wieder.</span><span class="sxs-lookup"><span data-stu-id="7db2d-116">For UTC and local [DateTime](xref:System.DateTime) values, the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="7db2d-117">Folgender Code konvertiert z.B. eine UTC-Zeit in den entsprechenden [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="7db2d-117">For example, the following code converts a UTC time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> 

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

<span data-ttu-id="7db2d-118">In diesem Fall beträgt die Abweichung der `utcTime2`-Variablen 00:00.</span><span class="sxs-lookup"><span data-stu-id="7db2d-118">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="7db2d-119">Auf die gleiche Weise konvertiert folgender Code eine lokale Zeit in den entsprechenden [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="7db2d-119">Similarly, the following code converts a local time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

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

<span data-ttu-id="7db2d-120">Für [DateTime](xref:System.DateTime)-Werte, deren [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, erzeugen diese beiden Konvertierungsmethoden allerdings einen[DateTimeOffset](xref:System.DateTimeOffset)-Wert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht.</span><span class="sxs-lookup"><span data-stu-id="7db2d-120">However, for [DateTime](xref:System.DateTime) values whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), these two conversion methods produce a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset is that of the local time zone.</span></span> <span data-ttu-id="7db2d-121">Dies wird im folgenden Beispiel gezeigt, das in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7db2d-121">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

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

<span data-ttu-id="7db2d-122">Wenn der [DateTime](xref:System.DateTime)-Wert das Datum und die Uhrzeit in einer anderen Zeit als der lokalen Zeitzone oder der UTC wiedergibt, können Sie den Wert in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert konvertieren und die Zeitzoneninformationen beibehalten, indem Sie den überladenen [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset)-Konstruktor aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-122">If the [DateTime](xref:System.DateTime) value reflects the date and time in something other than the local time zone or UTC, you can convert it to a [DateTimeOffset](xref:System.DateTimeOffset) value and preserve its time zone information by calling the overloaded [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset) constructor.</span></span> <span data-ttu-id="7db2d-123">Das folgende Beispiel instanziiert ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt, das die Central Standard Time wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-123">For example, the following example instantiates a [DateTimeOffset](xref:System.DateTimeOffset) object that reflects Central Standard Time.</span></span>

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

<span data-ttu-id="7db2d-124">Der zweite Parameter dieser Konstruktorüberladung, ein [System.TimeSpan](xref:System.TimeSpan)-Objekt, das die Abweichung der Uhrzeit von der UTC darstellt, sollte durch Aufrufen der [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo)-Methode der entsprechenden Zeitzone der Uhrzeit abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7db2d-124">The second parameter to this constructor overload, a [System.TimeSpan](xref:System.TimeSpan) object that represents the time's offset from UTC, should be retrieved by calling the [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) method of the time's corresponding time zone.</span></span> <span data-ttu-id="7db2d-125">Der einzige Parameter der Methode ist der [DateTime](xref:System.DateTime)-Wert, der das Datum und die Uhrzeit darstellt, das/die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7db2d-125">The method's single parameter is the [DateTime](xref:System.DateTime) value that represents the date and time to be converted.</span></span> <span data-ttu-id="7db2d-126">Wenn die Zeitzone die Sommerzeit unterstützt, ermöglicht dieser Parameter der Methode, die richtige Abweichung für dieses spezielle Datum und diese spezielle Uhrzeit zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-126">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="7db2d-127">Konvertierungen von DateTimeOffset in DateTime</span><span class="sxs-lookup"><span data-stu-id="7db2d-127">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="7db2d-128">Die [DateTime](xref:System.DateTime)-Eigenschaft wird am häufigsten verwendet, um Konvertierungen von [DateTimeOffset](xref:System.DateTimeOffset) in [DateTime](xref:System.DateTime) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-128">The [DateTime](xref:System.DateTime) property is most commonly used to perform [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversion.</span></span> <span data-ttu-id="7db2d-129">Die Eigenschaft gibt allerdings einen [DateTime](xref:System.DateTime)-Wert zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7db2d-129">However, it returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), as the following example illustrates.</span></span> 

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

<span data-ttu-id="7db2d-130">Dies bedeutet, dass alle Informationen über die Beziehung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts zur UTC bei der Konvertierung verloren gehen, wenn die [DateTime](xref:System.DateTime)-Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7db2d-130">This means that any information about the [DateTimeOffset](xref:System.DateTimeOffset) value's relationship to UTC is lost by the conversion when the [DateTime](xref:System.DateTime) property is used.</span></span> <span data-ttu-id="7db2d-131">Dies betrifft [DateTimeOffset](xref:System.DateTimeOffset)-Werte, die der UTC-Zeit oder der lokalen Systemzeit entsprechen, weil die [DateTime](xref:System.DateTime)-Struktur in ihrer [Kind](xref:System.DateTime.Kind)-Eigenschaft nur diese beiden Zeitzonen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-131">This affects [DateTimeOffset](xref:System.DateTimeOffset) values that correspond to UTC time or to the system's local time because the [DateTime](xref:System.DateTime) structure reflects only those two time zones in its [Kind](xref:System.DateTime.Kind) property.</span></span>

<span data-ttu-id="7db2d-132">Um bei der Konvertierung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts in einen [DateTime](xref:System.DateTime)-Wert so viele Zeitzoneninformationen wie möglich beizubehalten, können Sie die Eigenschaften [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) und [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7db2d-132">To preserve as much time zone information as possible when converting a [DateTimeOffset](xref:System.DateTimeOffset) to a [DateTime](xref:System.DateTime) value, you can use the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) and [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) properties.</span></span> 

## <a name="converting-a-utc-time"></a><span data-ttu-id="7db2d-133">Konvertieren einer UTC-Zeit</span><span class="sxs-lookup"><span data-stu-id="7db2d-133">Converting a UTC Time</span></span>

<span data-ttu-id="7db2d-134">Um anzugeben, dass es sich bei einem konvertierten [DateTime](xref:System.DateTime)-Wert um die UTC-Zeit handelt, können Sie den Wert der [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime)-Eigenschaft abrufen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-134">To indicate that a converted [DateTime](xref:System.DateTime) value is the UTC time, you can retrieve the value of the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property.</span></span> <span data-ttu-id="7db2d-135">Diese Eigenschaft unterscheidet sich in zweierlei Hinsicht von der [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime)-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="7db2d-135">It differs from the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property in two ways:</span></span>

* <span data-ttu-id="7db2d-136">Sie gibt einen [DateTime](xref:System.DateTime)-Wert zurück, dessen [Kind](xref:System.DateTime.Kind)-Eigenschaft [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet.</span><span class="sxs-lookup"><span data-stu-id="7db2d-136">It returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

* <span data-ttu-id="7db2d-137">Wenn der [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset)-Eigenschaftswert nicht gleich [TimeSpan.Zero](xref:System.TimeSpan.Zero) ist, wird die Uhrzeit in die UTC konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7db2d-137">If the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property value does not equal [TimeSpan.Zero](xref:System.TimeSpan.Zero), it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="7db2d-138">Wenn es Ihre Anwendung erfordert, dass konvertierte [DateTime](xref:System.DateTime)-Werte eine bestimmte Uhrzeit eindeutig identifizieren, sollten Sie die Eigenschaft [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) verwenden, um alle Konvertierungen von [DateTimeOffset](xref:System.DateTimeOffset) in [DateTime](xref:System.DateTime) zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7db2d-138">If your application requires that converted [DateTime](xref:System.DateTime) values unambiguously identify a single point in time, you should consider using the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to handle all [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversions.</span></span>

<span data-ttu-id="7db2d-139">Der folgende Code verwendet die [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime)-Eigenschaft, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung [TimeSpan.Zero](xref:System.TimeSpan.Zero) mit einem [DateTime](xref:System.DateTime)-Wert gleichsetzt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-139">The following code uses the [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset equals [TimeSpan.Zero](xref:System.TimeSpan.Zero) to a [DateTime](xref:System.DateTime) value.</span></span>

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

<span data-ttu-id="7db2d-140">Der folgende Code verwendet die UtcDateTime-Eigenschaft, um sowohl eine Zeitzonenkonvertierung als auch eine Typkonvertierung für einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-140">The following code uses the UtcDateTime property to perform both a time zone conversion and a type conversion on a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

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

## <a name="converting-a-local-time"></a><span data-ttu-id="7db2d-141">Konvertieren einer lokalen Zeit</span><span class="sxs-lookup"><span data-stu-id="7db2d-141">Converting a Local Time</span></span>

<span data-ttu-id="7db2d-142">Um anzugeben, dass ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert die lokale Uhrzeit wiedergibt, können Sie den [DateTime](xref:System.DateTime)-Wert, der von der [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime)-Eigenschaft zurückgegeben wurde, an die statische [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind))-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="7db2d-142">To indicate that a [DateTimeOffset](xref:System.DateTimeOffset) value represents the local time, you can pass the [DateTime](xref:System.DateTime) value returned by the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property to the static [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method.</span></span> <span data-ttu-id="7db2d-143">Die Methode gibt das an sie übergebene Datum und die übergebene Uhrzeit als ersten Parameter zurück, legt aber die [Kind](xref:System.DateTime.Kind)-Eigenschaft auf den vom zweiten Parameter angegebenen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="7db2d-143">The method returns the date and time passed to it as its first parameter, but sets the [Kind](xref:System.DateTime.Kind) property to the value specified by its second parameter.</span></span> <span data-ttu-id="7db2d-144">Der folgende Code verwendet die [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind))-Methode, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht.</span><span class="sxs-lookup"><span data-stu-id="7db2d-144">The following code uses the [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

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

<span data-ttu-id="7db2d-145">Sie können auch die [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft verwenden, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert in einen lokalen [DateTime](xref:System.DateTime)-Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7db2d-145">You can also use the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value to a local [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="7db2d-146">Die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zurückgegebenen [DateTime](xref:System.DateTime)-Werts ist [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span><span class="sxs-lookup"><span data-stu-id="7db2d-146">The [Kind](xref:System.DateTime.Kind) property of the returned [DateTime](xref:System.DateTime) value is [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span></span> <span data-ttu-id="7db2d-147">Der folgende Code verwendet die [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht.</span><span class="sxs-lookup"><span data-stu-id="7db2d-147">The following code uses the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

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

<span data-ttu-id="7db2d-148">Wenn Sie einen [DateTime](xref:System.DateTime)-Wert mithilfe der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft abrufen, konvertiert der `get`-Accessor der Eigenschaft den [DateTimeOffset](xref:System.DateTimeOffset)-Wert zuerst in die UTC und dann durch Aufrufen der [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset)-Methode in die lokale Zeit.</span><span class="sxs-lookup"><span data-stu-id="7db2d-148">When you retrieve a [DateTime](xref:System.DateTime) value using the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property, the property's `get` accessor first converts the [DateTimeOffset](xref:System.DateTimeOffset) value to UTC, then converts it to local time by calling the [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) method.</span></span> <span data-ttu-id="7db2d-149">Dies bedeutet, dass Sie einen Wert aus der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft abrufen können, um gleichzeitig mit einer Typkonvertierung auch eine Zeitzonenkonvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-149">This means that you can retrieve a value from the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="7db2d-150">Es bedeutet auch, dass die beim Durchführen der Konvertierung die Anpassungsregeln der lokalen Zeitzone angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7db2d-150">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="7db2d-151">Der folgende Code verwendet die Verwendung der [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime)-Eigenschaft, um sowohl eine Typkonvertierung als auch eine Zeitzonenkonvertierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-151">The following code illustrates the use of the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform both a type and a time zone conversion.</span></span>

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

## <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="7db2d-152">Eine allgemeine Konvertierungsmethode</span><span class="sxs-lookup"><span data-stu-id="7db2d-152">A General-Purpose Conversion Method</span></span>

<span data-ttu-id="7db2d-153">Das folgende Beispiel definiert eine Methode namens `ConvertFromDateTimeOffset`, die [DateTimeOffset](xref:System.DateTimeOffset)-Werte in [DateTime](xref:System.DateTime)-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7db2d-153">The following example defines a method named `ConvertFromDateTimeOffset` that converts [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="7db2d-154">Basierend auf der Abweichung bestimmt die Methode, ob es sich beim [DateTimeOffset](xref:System.DateTimeOffset)-Wert um eine UTC-Zeit, eine lokale Zeit oder eine andere Zeit handelt, und definiert die [Kind](xref:System.DateTime.Kind)-Eigenschaft des zurückgegebenen Datums- und Uhrzeitwerts entsprechend.</span><span class="sxs-lookup"><span data-stu-id="7db2d-154">Based on its offset, it determines whether the [DateTimeOffset](xref:System.DateTimeOffset) value is a UTC time, a local time, or some other time, and defines the returned date and time value's [Kind](xref:System.DateTime.Kind) property accordingly.</span></span> 

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

<span data-ttu-id="7db2d-155">Das folgende Beispiel ruft die `ConvertFromDateTimeOffset`-Methode auf, um [DateTimeOffset](xref:System.DateTimeOffset)-Werte zu konvertieren, die eine UTC-Zeit, eine lokale Zeit und eine Zeit in der Central Standard Time-Zeitzone (USA) darstellen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-155">The follow example calls the `ConvertFromDateTimeOffset` method to convert [DateTimeOffset](xref:System.DateTimeOffset) values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

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

<span data-ttu-id="7db2d-156">Beachten Sie, dass bei diesem Code von zwei Annahmen ausgegangen wird, die je nach der Anwendung und der Quelle ihrer Datums- und Uhrzeitwerte, nicht immer zutreffen:</span><span class="sxs-lookup"><span data-stu-id="7db2d-156">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="7db2d-157">Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung [TimeSpan.Zero](xref:System.TimeSpan.Zero) beträgt, eine UTC-Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-157">It assumes that a date and time value whose offset is [TimeSpan.Zero](xref:System.TimeSpan.Zero) represents UTC.</span></span> <span data-ttu-id="7db2d-158">Tatsächlich ist die UTC keine Zeit in einer bestimmten Zeitzone, sondern die Uhrzeit, nach der alle Uhrzeiten in den Zeitzone der Welt standardisiert sind.</span><span class="sxs-lookup"><span data-stu-id="7db2d-158">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="7db2d-159">Zeitzonen können auch eine Abweichung von [null](xref:System.TimeSpan.Zero) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-159">Time zones can also have an offset of [Zero](xref:System.TimeSpan.Zero).</span></span>

* <span data-ttu-id="7db2d-160">Es wird angenommen, dass ein Datums- und Uhrzeitwert, dessen Abweichung der Abweichung der lokalen Zeitzone entspricht, die lokale Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="7db2d-160">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="7db2d-161">Dies ist möglicherweise nicht der Fall, weil Datums- und Uhrzeitwerte nicht mehr ihrer ursprünglichen Zeitzone verknüpft sind. Datum und Uhrzeit können aus einer anderen Zeitzone mit der gleichen Abweichung stammen.</span><span class="sxs-lookup"><span data-stu-id="7db2d-161">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="7db2d-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7db2d-162">See Also</span></span>

[<span data-ttu-id="7db2d-163">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7db2d-163">Dates, times, and time zones</span></span>](index.md)





