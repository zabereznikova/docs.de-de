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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b872cc4c2b799ddafc9df263795d860754d1ec17
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="92aee-104">Durchführen arithmetischer Datums- und Uhrzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="92aee-104">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="92aee-105">Auch wenn sowohl die [System.DateTime](xref:System.DateTime)- als auch die [System.DateTimeOffset](xref:System.DateTimeOffset)-Struktur Member bieten, die arithmetische Operationen für ihre Werte durchführen, sind die Ergebnisse der arithmetischen Operationen sehr verschieden.</span><span class="sxs-lookup"><span data-stu-id="92aee-105">Although both the [System.DateTime](xref:System.DateTime) and the [System.DateTimeOffset](xref:System.DateTimeOffset) structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="92aee-106">In diesem Artikel werden diese Unterschiede untersucht und mit dem Grad der Unterstützung von Zeitzonen bei Datums- und Zeitdaten in Zusammenhang gebracht. Zudem wird erläutert, wie Operationen mit Datums- und Uhrzeitdaten unter vollständiger Berücksichtigung der Zeitzone durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="92aee-106">This article examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="92aee-107">Vergleiche und arithmetische Operationen mit DateTime-Werten</span><span class="sxs-lookup"><span data-stu-id="92aee-107">Comparisons and Arithmetic Operations with DateTime Values</span></span>

<span data-ttu-id="92aee-108">[System.DateTime](xref:System.DateTime)-Werte bieten eine eingeschränkte Unterstützung von Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="92aee-108">[System.DateTime](xref:System.DateTime) values possess a limited degree of time zone awareness.</span></span> <span data-ttu-id="92aee-109">Über die [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft kann dem Datum und der Uhrzeit ein [System.DateTimeKind](xref:System.DateTimeKind)-Wert zugewiesen werden, um anzuzeigen, ob die Ortszeit, die koordinierte Weltzeit (UTC) oder die Zeit in einer nicht angegebenen Zeitzone dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="92aee-109">The [DateTime.Kind](xref:System.DateTime.Kind) property allows a [System.DateTimeKind](xref:System.DateTimeKind) value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="92aee-110">Diese eingeschränkten Zeitzoneninformationen werden jedoch beim Vergleichen oder Durchführen von Datums- und Zeitarithmetik für [DateTime](xref:System.DateTime)-Werte ignoriert.</span><span class="sxs-lookup"><span data-stu-id="92aee-110">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="92aee-111">Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="92aee-111">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

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

<span data-ttu-id="92aee-112">Die Methode [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) gibt an, dass die Ortszeit früher als (oder kleiner als) die UTC-Zeit ist, und der Subtraktionsvorgang ergibt, dass der Unterschied zwischen UTC und der Ortszeit für ein System in der US-Zeitzone Pacific Standard Time sieben Stunden beträgt.</span><span class="sxs-lookup"><span data-stu-id="92aee-112">The [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="92aee-113">Da diese beiden Werte verschiedene Darstellungen eines einzigen Zeitpunkts angeben, ist das Zeitintervall in diesem Fall vollständig auf die Abweichung der Ortszeit von UTC zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="92aee-113">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span> 

<span data-ttu-id="92aee-114">Im Allgemeinen wirkt die [DateTimeKind](xref:System.DateTimeKind)-Eigenschaft sich nicht auf die Ergebnisse aus, die durch den [DateTime](xref:System.DateTime)-Vergleich und arithmetische Methoden zurückgegeben werden (wie der Vergleich zweier identischer Zeitpunkte zeigt), aber sie kann die Interpretation dieser Ergebnisse beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="92aee-114">More generally, the [DateTimeKind](xref:System.DateTimeKind) property does not affect the results returned by [DateTime](xref:System.DateTime) comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="92aee-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="92aee-115">For example:</span></span>

* <span data-ttu-id="92aee-116">Das Ergebnis einer beliebigen arithmetischen Operation für zwei Datums- und Zeitwerte, deren [DateTimeKind](xref:System.DateTimeKind)-Eigenschaften beide den Wert [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) aufweisen, gibt das tatsächliche Zeitintervall zwischen den beiden Werten wieder.</span><span class="sxs-lookup"><span data-stu-id="92aee-116">The result of any arithmetic operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) reflects the actual time interval between the two values.</span></span> <span data-ttu-id="92aee-117">Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.</span><span class="sxs-lookup"><span data-stu-id="92aee-117">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="92aee-118">Das Ergebnis einer arithmetischen oder Vergleichsoperation für zwei Datums- und Uhrzeitwerte, deren [DateTimeKind](xref:System.DateTimeKind)-Eigenschaften beide den Wert [DateTimeKind.Local](xref:System.DateTimeKind.Local) aufweisen, oder für zwei Datums- und Uhrzeitwerte mit unterschiedlichen [DateTimeKind](xref:System.DateTimeKind)-Eigenschaftswerten gibt den Zeitunterschied zwischen den beiden Werten an.</span><span class="sxs-lookup"><span data-stu-id="92aee-118">The result of any arithmetic or comparison operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Local](xref:System.DateTimeKind.Local) or on two date and time values with different [DateTimeKind](xref:System.DateTimeKind) property values reflects the difference in clock time between the two values.</span></span> 

* <span data-ttu-id="92aee-119">Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.</span><span class="sxs-lookup"><span data-stu-id="92aee-119">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="92aee-120">Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht.</span><span class="sxs-lookup"><span data-stu-id="92aee-120">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span> 

* <span data-ttu-id="92aee-121">Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder.</span><span class="sxs-lookup"><span data-stu-id="92aee-121">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="92aee-122">Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder.</span><span class="sxs-lookup"><span data-stu-id="92aee-122">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span> 

* <span data-ttu-id="92aee-123">Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="92aee-123">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="92aee-124">Es gibt viele Szenarios, in denen Zeitzonenunterschiede sich nicht auf Datums- und Uhrzeitberechnungen auswirken oder in denen die Bedeutung von Vergleichen oder arithmetischen Operationen durch den Kontext des Datums und der Uhrzeit definiert wird.</span><span class="sxs-lookup"><span data-stu-id="92aee-124">There are many scenarios in which time zone differences do not affect date and time calculations or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span> <span data-ttu-id="92aee-125">Einige dieser Szenarios werden unter [Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md) erläutert.</span><span class="sxs-lookup"><span data-stu-id="92aee-125">For a discussion of some of these, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="92aee-126">Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten</span><span class="sxs-lookup"><span data-stu-id="92aee-126">Comparisons and Arithmetic Operations with DateTimeOffset Values</span></span>

<span data-ttu-id="92aee-127">Ein [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch eine Abweichung, die das jeweilige Datum und die Uhrzeit relativ zur UTC eindeutig definiert.</span><span class="sxs-lookup"><span data-stu-id="92aee-127">A [System.DateTimeOffset](xref:System.DateTimeOffset) value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="92aee-128">Dadurch kann die Übereinstimmung anders als für [System.DateTime](xref:System.DateTime)-Werte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="92aee-128">This makes it possible to define equality somewhat differently than for [System.DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="92aee-129">Während [DateTime](xref:System.DateTime) Werte gleich sind, wenn sie denselben Datums- und Uhrzeitwert aufweisen, stimmen [DateTimeOffset](xref:System.DateTimeOffset)-Werte überein, wenn sie sich beide auf denselben Zeitpunkt beziehen.</span><span class="sxs-lookup"><span data-stu-id="92aee-129">Whereas [DateTime](xref:System.DateTime) values are equal if they have the same date and time value, [DateTimeOffset](xref:System.DateTimeOffset) values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="92aee-130">Dadurch ist ein [DateTimeOffset](xref:System.DateTimeOffset)-Wert genauer und erfordert weniger Interpretationsaufwand, wenn er in Vergleichen und den meisten arithmetischen Operationen verwendet wird, die das Intervall zwischen zwei Datumsangaben und Uhrzeiten ermitteln.</span><span class="sxs-lookup"><span data-stu-id="92aee-130">This makes a [DateTimeOffset](xref:System.DateTimeOffset) value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="92aee-131">Das folgende Beispiel ist das [DateTimeOffset](xref:System.DateTimeOffset)-Äquivalent zum vorherigen Beispiel, bei dem der lokale und der UTC-DateTime-Wert verglichen wurde. Darin wird dieser Unterschied im Verhalten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="92aee-131">The following example, which is the [DateTimeOffset](xref:System.DateTimeOffset) equivalent to the previous example that compared local and UTC DateTime values, illustrates this difference in behavior.</span></span>

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

<span data-ttu-id="92aee-132">In diesem Beispiel gibt die [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset))-Methode an, dass die aktuelle Ortszeit und die aktuelle UTC-Zeit identisch sind, und die Subtraktion von [DateTimeOffset](xref:System.DateTimeOffset)-Werten weist darauf hin, dass der Unterschied zwischen den beiden Zeiten [TimeSpan.Zero](xref:System.TimeSpan.Zero) beträgt.</span><span class="sxs-lookup"><span data-stu-id="92aee-132">In this example, the [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) method indicates that the current local time and the current UTC time are equal, and subtraction of [DateTimeOffset](xref:System.DateTimeOffset) values indicates that the difference between the two times is [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> 

<span data-ttu-id="92aee-133">Die wichtigste Einschränkung bei der Verwendung von [DateTimeOffset](xref:System.DateTimeOffset)-Werten in Datums- und Uhrzeitoperationen besteht darin, dass [DateTimeOffset](xref:System.DateTimeOffset)-Werte Zeitzonen zwar ansatzweise, aber nicht vollständig unterstützen.</span><span class="sxs-lookup"><span data-stu-id="92aee-133">The chief limitation of using [DateTimeOffset](xref:System.DateTimeOffset) values in date and time arithmetic is that although [DateTimeOffset](xref:System.DateTimeOffset) values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="92aee-134">Auch wenn die Abweichung des [DateTimeOffset](xref:System.DateTimeOffset)-Werts bei der ersten Zuweisung zu einer [DateTimeOffset](xref:System.DateTimeOffset)-Variablen die Abweichung einer Zeitzone von UTC wiedergibt, wird der Wert anschließend unabhängig von der Zeitzone verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="92aee-134">Although the [DateTimeOffset](xref:System.DateTimeOffset) value's offset reflects a time zone's offset from UTC when a [DateTimeOffset](xref:System.DateTimeOffset) variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="92aee-135">Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="92aee-135">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span> 

<span data-ttu-id="92aee-136">Zur Veranschaulichung: Der Übergang zur Sommerzeit erfolgt in der US-Zeitzone Central Standard Time um 2:00 Uhr morgens</span><span class="sxs-lookup"><span data-stu-id="92aee-136">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="92aee-137">am 9. März 2008.</span><span class="sxs-lookup"><span data-stu-id="92aee-137">on March 9, 2008.</span></span> <span data-ttu-id="92aee-138">Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr</span><span class="sxs-lookup"><span data-stu-id="92aee-138">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="92aee-139">am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens</span><span class="sxs-lookup"><span data-stu-id="92aee-139">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="92aee-140">am 9. März 2008 ergeben.</span><span class="sxs-lookup"><span data-stu-id="92aee-140">on March 9, 2008.</span></span> <span data-ttu-id="92aee-141">Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens</span><span class="sxs-lookup"><span data-stu-id="92aee-141">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="92aee-142">am 9. März 2008.</span><span class="sxs-lookup"><span data-stu-id="92aee-142">on March 9, 2008.</span></span> <span data-ttu-id="92aee-143">Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, auch wenn es sich nicht um die Uhrzeit in der Zeitzone handelt, an der wir interessiert sind (d.h. sie weist nicht die erwartete Zeitzonenabweichung auf).</span><span class="sxs-lookup"><span data-stu-id="92aee-143">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

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

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="92aee-144">Arithmetische Operationen mit Uhrzeiten in Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="92aee-144">Arithmetic Operations with Times in Time Zones</span></span>

<span data-ttu-id="92aee-145">Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse bietet keine Methoden zum automatischen Anwenden von Anpassungsregeln beim Ausführen arithmetischer Datums- und Uhrzeitoperationen.</span><span class="sxs-lookup"><span data-stu-id="92aee-145">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="92aee-146">Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren.</span><span class="sxs-lookup"><span data-stu-id="92aee-146">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="92aee-147">Einzelheiten hierzu finden Sie unter [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](use-time-zones-in-arithmetic.md).</span><span class="sxs-lookup"><span data-stu-id="92aee-147">For details, see [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="92aee-148">Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="92aee-148">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="92aee-149">am 9. März 2008 hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="92aee-149">on March 9, 2008.</span></span> <span data-ttu-id="92aee-150">Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.</span><span class="sxs-lookup"><span data-stu-id="92aee-150">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="92aee-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92aee-151">See Also</span></span>

[<span data-ttu-id="92aee-152">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="92aee-152">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="92aee-153">Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="92aee-153">How to: use time zones in date and time arithmetic</span></span>](use-time-zones-in-arithmetic.md)



