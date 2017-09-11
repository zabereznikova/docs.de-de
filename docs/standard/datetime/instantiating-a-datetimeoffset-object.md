---
title: Instanziieren eines DateTimeOffset-Objekts
description: Instanziieren eines DateTimeOffset-Objekts
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 476fe67b-6be4-4435-88ab-ced37304f1d1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 26be324eb5d58b94a71e89aba213f107cf8dfd1e
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="ecbab-104">Instanziieren eines DateTimeOffset-Objekts</span><span class="sxs-lookup"><span data-stu-id="ecbab-104">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="ecbab-105">Die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur bietet eine Reihe von Methoden zum Erstellen neuer [DateTimeOffset](xref:System.DateTimeOffset) Werte.</span><span class="sxs-lookup"><span data-stu-id="ecbab-105">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure offers a number of ways to create new [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="ecbab-106">Viele von ihnen entsprechen direkt den Methoden zum Instanziieren neuer [System.DateTime](xref:System.DateTime)-Werte mit Erweiterungen, mit denen Sie die Abweichung des Datums- und Zeitwerts von der koordinierten Weltzeit (UTC) angeben können.</span><span class="sxs-lookup"><span data-stu-id="ecbab-106">Many of them correspond directly to the methods available for instantiating new [System.DateTime](xref:System.DateTime) values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="ecbab-107">Insbesondere können Sie einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert auf folgende Weise instanziieren:</span><span class="sxs-lookup"><span data-stu-id="ecbab-107">In particular, you can instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value in the following ways:</span></span>

* <span data-ttu-id="ecbab-108">Durch Aufrufen eines [DateTimeOffset](xref:System.DateTimeOffset)-Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="ecbab-108">By calling a [DateTimeOffset](xref:System.DateTimeOffset) constructor.</span></span>

* <span data-ttu-id="ecbab-109">Durch implizites Konvertieren eines Werts in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-109">By implicitly converting a value to [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

* <span data-ttu-id="ecbab-110">Durch Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts.</span><span class="sxs-lookup"><span data-stu-id="ecbab-110">By parsing the string representation of a date and time.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="ecbab-111">Datums- und Uhrzeitliterale</span><span class="sxs-lookup"><span data-stu-id="ecbab-111">Date and Time Literals</span></span>

<span data-ttu-id="ecbab-112">Für Sprachen, die dies unterstützen, besteht eine der am häufigsten verwendeten Methoden zum Instanziieren eines [DateTime](xref:System.DateTime)-Werts darin, den Datums- und Uhrzeitwert als hartcodierten Literalwert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-112">For languages that support it, one of the most common ways to instantiate a [DateTime](xref:System.DateTime) value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="ecbab-113">Der folgende Visual Basic-Code erstellt z.B. ein [DateTime](xref:System.DateTime)-Objekt, dessen Wert dem 1. Januar 2008, 10:00 Uhr, entspricht.</span><span class="sxs-lookup"><span data-stu-id="ecbab-113">For example, the following Visual Basic code creates a [DateTime](xref:System.DateTime) object whose value is January 1, 2008, at 10:00 AM.</span></span>

```vb
Dim literalDate1 As Date = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate1.ToString())
' Displays:
'              5/1/2008 8:06:32 AM
```

<span data-ttu-id="ecbab-114">[DateTimeOffset](xref:System.DateTimeOffset)-Werte können auch über Datums- und Uhrzeitliterale initialisiert werden, wenn Sprachen verwendet werden, die [DateTime](xref:System.DateTime)-Literale unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-114">[DateTimeOffset](xref:System.DateTimeOffset) values can also be initialized using date and time literals when using languages that support [DateTime](xref:System.DateTime) literals.</span></span> <span data-ttu-id="ecbab-115">Mit dem folgenden Visual Basic-Code wird beispielsweise ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-115">For example, the following Visual Basic code creates a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

```vb
Dim literalDate As DateTimeOffset = #05/01/2008 8:06:32 AM#
Console.WriteLine(literalDate.ToString())
' Displays:
'              5/1/2008 8:06:32 AM -07:00
```

<span data-ttu-id="ecbab-116">Wie die Konsolenausgabe zeigt, wird dem auf diese Weise erstellten [DateTimeOffset](xref:System.DateTimeOffset)-Wert die Abweichung der lokalen Zeitzone zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-116">As the console output shows, the [DateTimeOffset](xref:System.DateTimeOffset) value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="ecbab-117">Dies bedeutet, dass ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert, der über ein Zeichenliteral zugewiesen wurde, keinen bestimmten Zeitpunkt identifiziert, wenn der Code auf verschiedenen Computern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecbab-117">This means that a [DateTimeOffset](xref:System.DateTimeOffset) value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="ecbab-118">DateTimeOffset-Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="ecbab-118">DateTimeOffset Constructors</span></span>

<span data-ttu-id="ecbab-119">Der Typ [System.DateTimeOffset](xref:System.DateTimeOffset) definiert fünf Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="ecbab-119">The [System.DateTimeOffset](xref:System.DateTimeOffset) type defines five constructors.</span></span> <span data-ttu-id="ecbab-120">Drei davon entsprechen direkt den [DateTime](xref:System.DateTime)-Konstruktoren mit einem zusätzlichen Parameter vom Typ [System.TimeSpan](xref:System.TimeSpan), der die Datums- und Uhrzeitabweichung von UTC definiert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-120">Three of them correspond directly to [DateTime](xref:System.DateTime) constructors, with an additional parameter of type [System.TimeSpan](xref:System.TimeSpan) that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="ecbab-121">Mit diesen können Sie einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert basierend auf dem Wert der einzelnen Datums- und Uhrzeitkomponenten definieren.</span><span class="sxs-lookup"><span data-stu-id="ecbab-121">These allow you to define a [DateTimeOffset](xref:System.DateTimeOffset) value based on the value of its individual date and time components.</span></span> <span data-ttu-id="ecbab-122">Der folgende Code verwendet beispielsweise diese drei Konstruktoren, um [DateTimeOffset](xref:System.DateTimeOffset)-Objekte mit identischen Werten von „7/1/2008 12:05 AM +01:00“ zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="ecbab-122">For example, the following code uses these three constructors to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

```csharp
DateTimeOffset dateAndTime;

// Instantiate date and time using years, months, days, 
// hours, minutes, and seconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine(dateAndTime);
// Instantiate date and time using years, months, days,
// hours, minutes, seconds, and milliseconds
dateAndTime = new DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, 
                                 new TimeSpan(1, 0, 0));
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), 
                             dateAndTime.ToString("zzz"));

// Instantiate date and time using number of ticks
// 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = new DateTimeOffset(633452259920000000, new TimeSpan(1, 0, 0));  
Console.WriteLine(dateAndTime);
// The example displays the following output to the console:
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
//       5/1/2008 8:06:32 AM +01:00
```

```vb
Dim dateAndTime As DateTimeOffset

' Instantiate date and time using years, months, days, 
' hours, minutes, and seconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine(dateAndTime)
' Instantiate date and time using years, months, days,
' hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(2008, 5, 1, 8, 6, 32, 545, _
                                 New TimeSpan(1, 0, 0))
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using Persian calendar with years,
' months, days, hours, minutes, seconds, and milliseconds
dateAndTime = New DateTimeOffset(1387, 2, 12, 8, 6, 32, 545, New PersianCalendar, New TimeSpan(1, 0, 0))
' Note that the console output displays the date in the Gregorian
' calendar, not the Persian calendar. 
Console.WriteLine("{0} {1}", dateAndTime.ToString("G"), _
                             dateAndTime.ToString("zzz"))

' Instantiate date and time using number of ticks
' 05/01/2008 8:06:32 AM is 633,452,259,920,000,000 ticks
dateAndTime = New DateTimeOffset(633452259920000000, New TimeSpan(1, 0, 0))  
Console.WriteLine(dateAndTime)
' The example displays the following output to the console:
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
'       5/1/2008 8:06:32 AM +01:00
```

<span data-ttu-id="ecbab-123">Wenn der Wert des [DateTimeOffset](xref:System.DateTimeOffset)-Objekts, das über ein [PersianCalendar](xref:System.Globalization.PersianCalendar)-Objekt als eines der Argumente für den Konstruktor instanziiert wird, in der Konsole angezeigt wird, beachten Sie, dass es als Datum im gregorianischen Kalender und nicht im persischen Kalender ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="ecbab-123">Note that, when the value of the [DateTimeOffset](xref:System.DateTimeOffset) object instantiated using a [PersianCalendar](xref:System.Globalization.PersianCalendar) object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> 

<span data-ttu-id="ecbab-124">Die anderen beiden Konstruktoren erstellen ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt aus einem DateTime-Wert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-124">The other two constructors create a [DateTimeOffset](xref:System.DateTimeOffset) object from a DateTime value.</span></span> <span data-ttu-id="ecbab-125">Der erste verfügt über einen einzelnen Parameter, den [DateTime](xref:System.DateTime)-Wert zum Konvertieren in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-125">The first of these has a single parameter, the [DateTime](xref:System.DateTime) value to convert to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="ecbab-126">Die Abweichung des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts hängt von der [Kind](xref:System.DateTime.Kind)-Eigenschaft des einzelnen [DateTime](xref:System.DateTime)-Parameters des Konstruktors ab.</span><span class="sxs-lookup"><span data-stu-id="ecbab-126">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the [Kind](xref:System.DateTime.Kind) property of the constructor's single [DateTime](xref:System.DateTime) parameter.</span></span> <span data-ttu-id="ecbab-127">Wenn der Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, wird die Abweichung auf [TimeSpan.Zero](xref:System.TimeSpan.Zero) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-127">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="ecbab-128">Andernfalls wird die Abweichung entsprechend der lokalen Zeitzone eingestellt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-128">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="ecbab-129">Das folgende Beispiel veranschaulicht die Verwendung dieses Konstruktors für das Instanziieren von [DateTimeOffset](xref:System.DateTimeOffset)-Objekten, die die UTC-Zeit und die lokale Zeitzone darstellen:</span><span class="sxs-lookup"><span data-stu-id="ecbab-129">The following example illustrates the use of this constructor to instantiate [DateTimeOffset](xref:System.DateTimeOffset) objects representing UTC and the local time zone:</span></span>

```csharp
// Declare date; Kind property is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time 
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the offset is TimeSpan.Zero.

// Instantiate a DateTimeOffset value from a UTC time with a zero offset
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc, 
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a negative offset
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      targetTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM +00:00 failed.

// Instantiate a DateTimeOffset value from a local time
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local, 
// the offset is that of the local time zone.

// Instantiate a DateTimeOffset value from an unspecified time
targetTime = new DateTimeOffset(sourceDate);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Unspecified, 
// the offset is that of the local time zone.
```

```vb
' Declare date; Kind property is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time 
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc, 
' the offset is TimeSpan.Zero.


' Instantiate a DateTimeOffset value from a local time
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Local, 
' the offset is that of the local time zone.

' Instantiate a DateTimeOffset value from an unspecified time
targetTime = New DateTimeOffset(sourceDate)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -07:00
' Because the Kind property is DateTimeKind.Unspecified, 
' the offset is that of the local time zone.
```

> [!NOTE]
> <span data-ttu-id="ecbab-130">Das Aufrufen der Überladung des [DateTimeOffset](xref:System.DateTimeOffset)-Konstruktors mit einem einzelnen [DateTime](xref:System.DateTime)-Parameter entspricht dem impliziten Konvertieren eines [DateTime](xref:System.DateTime)-Werts in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-130">Calling the overload of the [DateTimeOffset](xref:System.DateTimeOffset) constructor that has a single [DateTime](xref:System.DateTime) parameter is equivalent to performing an implicit conversion of a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

<span data-ttu-id="ecbab-131">Der zweite Konstruktor, der ein [DateTimeOffset](xref:System.DateTimeOffset)-Objekt aus einem [DateTime](xref:System.DateTime)-Wert erstellt, verfügt über zwei Parameter: den zu konvertierenden [DateTime](xref:System.DateTime)-Wert und einen [TimeSpan](xref:System.TimeSpan)-Wert, der die Datums- und Uhrzeitabweichung von UTC darstellt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-131">The second constructor that creates a [DateTimeOffset](xref:System.DateTimeOffset) object from a [DateTime](xref:System.DateTime) value has two parameters: the [DateTime](xref:System.DateTime) value to convert, and a [TimeSpan](xref:System.TimeSpan) value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="ecbab-132">Dieser Abweichungswert muss der [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters des Konstruktors entsprechen. Andernfalls wird eine [System.ArgumentException](xref:System.ArgumentException) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ecbab-132">This offset value must correspond to the [Kind](xref:System.DateTime.Kind) property of the constructor's first parameter or an [System.ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="ecbab-133">Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, muss der Wert des zweiten Parameters [TimeSpan.Zero](xref:System.TimeSpan.Zero) lauten.</span><span class="sxs-lookup"><span data-stu-id="ecbab-133">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the value of the second parameter must be [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="ecbab-134">Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Local](xref:System.DateTimeKind.Local) lautet, muss der Wert des zweiten Parameters der Zeitzonenabweichung des lokalen Systems entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-134">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Local](xref:System.DateTimeKind.Local), the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="ecbab-135">Wenn die [Kind](xref:System.DateTime.Kind)-Eigenschaft des ersten Parameters [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, kann die Abweichung einen beliebigen gültigen Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-135">If the [Kind](xref:System.DateTime.Kind) property of the first parameter is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset can be any valid value.</span></span> <span data-ttu-id="ecbab-136">Der folgende Code zeigt Aufrufe dieses Konstruktors zum Konvertieren von [DateTime](xref:System.DateTime) in [DateTimeOffset](xref:System.DateTimeOffset)-Werte.</span><span class="sxs-lookup"><span data-stu-id="ecbab-136">The following code illustrates calls to this constructor to convert [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) values.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
DateTimeOffset targetTime;

// Instantiate a DateTimeOffset value from a UTC time with a zero offset.
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = new DateTimeOffset(utcTime, TimeSpan.Zero);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM +00:00
// Because the Kind property is DateTimeKind.Utc,  
// the call to the constructor succeeds

// Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
try
{
   targetTime = new DateTimeOffset(utcTime, new TimeSpan(-2, 0, 0));
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      utcTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value from a local time with 
// the offset of the local time zone
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = new DateTimeOffset(localTime, 
                                TimeZoneInfo.Local.GetUtcOffset(localTime));
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -07:00
// Because the Kind property is DateTimeKind.Local and the offset matches
// that of the local time zone, the call to the constructor succeeds.

// Instantiate a DateTimeOffset value from a local time with a zero offset.
try
{
   targetTime = new DateTimeOffset(localTime, TimeSpan.Zero);
   Console.WriteLine(targetTime);
}
catch (ArgumentException)
{
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", 
                      localTime);
}   
// Throws exception and displays the following to the console:
//   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

// Instantiate a DateTimeOffset value with an arbitary time zone. 
string timeZoneName = "Central Standard Time";
TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). 
                         GetUtcOffset(sourceDate); 
targetTime = new DateTimeOffset(sourceDate, offset);
Console.WriteLine(targetTime);
// Displays 5/1/2008 8:30:00 AM -05:00
```

```vb
Dim sourceDate As Date = #5/1/2008 8:30 AM#
Dim targetTime As DateTimeOffset

' Instantiate a DateTimeOffset value from a UTC time with a zero offset.
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = New DateTimeOffset(utcTime, TimeSpan.Zero)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM +00:00
' Because the Kind property is DateTimeKind.Utc,  
' the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a UTC time with a non-zero offset.
Try
   targetTime = New DateTimeOffset(utcTime, New TimeSpan(-2, 0, 0))
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      utcTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value from a local time with 
' the offset of the local time zone.
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = New DateTimeOffset(localTime, _
                                TimeZoneInfo.Local.GetUtcOffset(localTime))
Console.WriteLine(targetTime)
' Because the Kind property is DateTimeKind.Local and the offset matches
' that of the local time zone, the call to the constructor succeeds.

' Instantiate a DateTimeOffset value from a local time with a zero offset.
Try
   targetTime = New DateTimeOffset(localTime, TimeSpan.Zero)
   Console.WriteLine(targetTime)
Catch e As ArgumentException
   Console.WriteLine("Attempt to create DateTimeOffset value from {0} failed.", _
                      localTime)
End Try   
' Throws exception and displays the following to the console:
'   Attempt to create DateTimeOffset value from 5/1/2008 8:30:00 AM failed.

' Instantiate a DateTimeOffset value with an arbitary time zone. 
Dim timeZoneName As String = "Central Standard Time"
Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName). _
                         GetUtcOffset(sourceDate) 
targetTime = New DateTimeOffset(sourceDate, offset)
Console.WriteLine(targetTime)
' Displays 5/1/2008 8:30:00 AM -05:00
```

## <a name="implicit-type-conversion"></a><span data-ttu-id="ecbab-137">Implizite Typkonvertierung</span><span class="sxs-lookup"><span data-stu-id="ecbab-137">Implicit Type Conversion</span></span>
 
<span data-ttu-id="ecbab-138">Der [System.DateTimeOffset](xref:System.DateTimeOffset)-Typ unterstützt eine implizite Typkonvertierung: von einem [System.DateTime](xref:System.DateTime)-Wert in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert.</span><span class="sxs-lookup"><span data-stu-id="ecbab-138">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports one implicit type conversion: from a [System.DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="ecbab-139">(Eine implizite Typkonvertierung ist eine Konvertierung von einem Typ in einen anderen, für die keine explizite Umwandlung (in C#) oder Konvertierung (in Visual Basic) erforderlich ist und bei der keine Informationen verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="ecbab-139">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="ecbab-140">Dies ermöglicht beispielsweise folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="ecbab-140">It makes code like the following possible.</span></span>

```csharp
DateTimeOffset targetTime;

// The Kind property of sourceDate is DateTimeKind.Unspecified
DateTime sourceDate = new DateTime(2008, 5, 1, 8, 30, 0);
targetTime = sourceDate;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM -07:00

// define a UTC time (Kind property is DateTimeKind.Utc)
DateTime utcTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Utc);
targetTime = utcTime;
Console.WriteLine(targetTime);   
// Displays 5/1/2008 8:30:00 AM +00:00

// Define a local time (Kind property is DateTimeKind.Local)
DateTime localTime = DateTime.SpecifyKind(sourceDate, DateTimeKind.Local);
targetTime = localTime;
Console.WriteLine(targetTime);      
// Displays 5/1/2008 8:30:00 AM -07:00
```

```vb
Dim targetTime As DateTimeOffset

' The Kind property of sourceDate is DateTimeKind.Unspecified
Dim sourceDate As Date = #5/1/2008 8:30 AM#
targetTime = sourceDate
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM -07:00

' define a UTC time (Kind property is DateTimeKind.Utc)
Dim utcTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Utc)
targetTime = utcTime
Console.WriteLine(targetTime)   
' Displays 5/1/2008 8:30:00 AM +00:00

' Define a local time (Kind property is DateTimeKind.Local)
Dim localTime As Date = Date.SpecifyKind(sourceDate, DateTimeKind.Local)
targetTime = localTime
Console.WriteLine(targetTime)      
' Displays 5/1/2008 8:30:00 AM -07:00
```

<span data-ttu-id="ecbab-141">Die Abweichung des resultierenden [DateTimeOffset](xref:System.DateTimeOffset)-Werts hängt vom DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaftswert ab.</span><span class="sxs-lookup"><span data-stu-id="ecbab-141">The offset of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value depends on the DateTime.Kind](xref:System.DateTime.Kind) property value.</span></span> <span data-ttu-id="ecbab-142">Wenn der Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) lautet, wird die Abweichung auf [TimeSpan.Zero](xref:System.TimeSpan.Zero) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-142">If its value is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), the offset is set equal to [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> <span data-ttu-id="ecbab-143">Wenn der Wert entweder [DateTimeKind.Local](xref:System.DateTimeKind.Local) oder [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) lautet, wird die Abweichung entsprechend der lokalen Zeitzone festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-143">If its value is either [DateTimeKind.Local](xref:System.DateTimeKind.Local) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="ecbab-144">Analysieren der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts</span><span class="sxs-lookup"><span data-stu-id="ecbab-144">Parsing the String Representation of a Date and Time</span></span>

<span data-ttu-id="ecbab-145">Der [System.DateTimeOffset](xref:System.DateTimeOffset)-Typ unterstützt vier Methoden, die Ihnen die Konvertierung der Zeichenfolgendarstellung eines Datums und einer Uhrzeit in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="ecbab-145">The [System.DateTimeOffset](xref:System.DateTimeOffset) type supports four methods that allow you to convert the string representation of a date and time into a [DateTimeOffset](xref:System.DateTimeOffset) value:</span></span>

* <span data-ttu-id="ecbab-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, und löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-146">[Parse](xref:System.DateTimeOffset.Parse(System.String)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="ecbab-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren, und gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-147">[TryParse](xref:System.DateTimeOffset.TryParse(System.String,System.DateTimeOffset@)), which tries to convert the string representation of a date and time to a [DateTimeOffset](xref:System.DateTimeOffset) value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="ecbab-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ecbab-148">[ParseExact](xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="ecbab-149">Die Methode löst eine Ausnahme aus, wenn bei der Konvertierung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-149">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="ecbab-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)): Versucht, die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einem angegebenen Format in einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ecbab-150">[TryParseExact](xref:System.DateTimeOffset.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTimeOffset@)), which tries to convert the string representation of a date and time in a specified format to a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="ecbab-151">Die Methode gibt `false` zurück, wenn bei der Konvertierung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ecbab-151">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="ecbab-152">Das folgende Beispiel veranschaulicht Aufrufe dieser vier Konvertierungsmethoden zum Instanziieren eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts.</span><span class="sxs-lookup"><span data-stu-id="ecbab-152">The following example illustrates calls to each of these four string conversion methods to instantiate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
string timeString; 
DateTimeOffset targetTime;

timeString = "05/01/2008 8:30 AM +01:00";
try
{
   targetTime = DateTimeOffset.Parse(timeString);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "05/01/2008 8:30 AM";
if (DateTimeOffset.TryParse(timeString, out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);   

timeString = "Thursday, 01 May 2008 08:30";
try
{
   targetTime = DateTimeOffset.ParseExact(timeString, "f", 
                CultureInfo.InvariantCulture);
   Console.WriteLine(targetTime);
}
catch (FormatException)
{
   Console.WriteLine("Unable to parse {0}.", timeString);   
}   

timeString = "Thursday, 01 May 2008 08:30 +02:00";
string formatString; 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern +
                " " +
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern +
                " zzz"; 
if (DateTimeOffset.TryParseExact(timeString, 
                                formatString, 
                                CultureInfo.InvariantCulture, 
                                DateTimeStyles.AllowLeadingWhite, 
                                out targetTime))
   Console.WriteLine(targetTime);
else
   Console.WriteLine("Unable to parse {0}.", timeString);
// The example displays the following output to the console:
//    5/1/2008 8:30:00 AM +01:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM -07:00
//    5/1/2008 8:30:00 AM +02:00
```

```vb
Dim timeString As String 
Dim targetTime As DateTimeOffset

timeString = "05/01/2008 8:30 AM +01:00"
Try
   targetTime = DateTimeOffset.Parse(timeString)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "05/01/2008 8:30 AM"
If DateTimeOffset.TryParse(timeString, targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)   
End If

timeString = "Thursday, 01 May 2008 08:30"
Try
   targetTime = DateTimeOffset.ParseExact(timeString, "f", _
                CultureInfo.InvariantCulture)
   Console.WriteLine(targetTime)
Catch e As FormatException
   Console.WriteLine("Unable to parse {0}.", timeString)   
End Try   

timeString = "Thursday, 01 May 2008 08:30 +02:00"
Dim formatString As String 
formatString = CultureInfo.InvariantCulture.DateTimeFormat.LongDatePattern & _
                " " & _
                CultureInfo.InvariantCulture.DateTimeFormat.ShortTimePattern & _
                " zzz" 
If DateTimeOffset.TryParseExact(timeString, _
                                formatString, _
                                CultureInfo.InvariantCulture, _
                                DateTimeStyles.AllowLeadingWhite, _
                                targetTime) Then
   Console.WriteLine(targetTime)
Else
   Console.WriteLine("Unable to parse {0}.", timeString)
End If      
' The example displays the following output to the console:
'    5/1/2008 8:30:00 AM +01:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM -07:00
'    5/1/2008 8:30:00 AM +02:00
```

## <a name="see-also"></a><span data-ttu-id="ecbab-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecbab-153">See Also</span></span>

[<span data-ttu-id="ecbab-154">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="ecbab-154">Dates, times, and time zones</span></span>](index.md)


