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
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a86471972d42adcbc412cc8eeb300410ca8a9c42
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="29f5b-104">Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="29f5b-104">How to: use time zones in date and time arithmetic</span></span>

<span data-ttu-id="29f5b-105">Normalerweise werden beim Durchführen von arithmetischen Datums- und Uhrzeitoperationen mit [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten in den Ergebnissen keine Anpassungsregeln von Zeitzonen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="29f5b-105">Ordinarily, when you perform date and time arithmetic using [System.DateTimeOffset](xref:System.DateTimeOffset) values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="29f5b-106">Dies trifft auch zu, wenn die Zeitzone des Datums- und Uhrzeitwerts eindeutig erkennbar ist.</span><span class="sxs-lookup"><span data-stu-id="29f5b-106">This is true even when the time zone of the date and time value is clearly identifiable.</span></span> <span data-ttu-id="29f5b-107">In diesem Artikel wird erläutert, wie Sie arithmetische Operationen für Datums- und Uhrzeitwerte durchführen, die zu einer bestimmten Zeitzone gehören.</span><span class="sxs-lookup"><span data-stu-id="29f5b-107">This article shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="29f5b-108">Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="29f5b-108">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="29f5b-109">So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an</span><span class="sxs-lookup"><span data-stu-id="29f5b-109">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="29f5b-110">Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört.</span><span class="sxs-lookup"><span data-stu-id="29f5b-110">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="29f5b-111">Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt.</span><span class="sxs-lookup"><span data-stu-id="29f5b-111">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="29f5b-112">Im folgenden Beispiel wird dieser Ansatz verwendet, um einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert mit seiner Zeitzone zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="29f5b-112">The following example uses this approach to link a [DateTimeOffset](xref:System.DateTimeOffset) value with its time zone.</span></span>

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
    
2. <span data-ttu-id="29f5b-113">Konvertieren Sie eine Uhrzeit in koordinierte Weltzeit (Coordinated Universal Time, UTC), indem Sie die [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="29f5b-113">Convert a time to Coordinated Universal Time (UTC) by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span>

3. <span data-ttu-id="29f5b-114">Führen Sie die arithmetische Operation für die UTC-Zeit aus.</span><span class="sxs-lookup"><span data-stu-id="29f5b-114">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="29f5b-115">Konvertieren Sie die Zeit von UTC in die mit der ursprünglichen Zeit verknüpfte Zeitzone, indem Sie die [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo))-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="29f5b-115">Convert the time from UTC to the original time's associated time zone by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> 

## <a name="example"></a><span data-ttu-id="29f5b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29f5b-116">Example</span></span>

<span data-ttu-id="29f5b-117">Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr</span><span class="sxs-lookup"><span data-stu-id="29f5b-117">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="29f5b-118">Central Standard Time hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="29f5b-118">Central Standard Time.</span></span> <span data-ttu-id="29f5b-119">Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="29f5b-119">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="29f5b-120">am 9.März 2008.</span><span class="sxs-lookup"><span data-stu-id="29f5b-120">on March 9, 2008.</span></span> <span data-ttu-id="29f5b-121">Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="29f5b-121">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="29f5b-122">am 9.März 2008.</span><span class="sxs-lookup"><span data-stu-id="29f5b-122">on March 9, 2008.</span></span> 

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

<span data-ttu-id="29f5b-123">Wenn Sie diese Ergänzung einfach mit dem [DateTimeOffset](xref:System.DateTimeOffset)-Wert durchführen, ohne ihn zuerst in UTC zu konvertieren, gibt das Ergebnis den richtigen Zeitpunkt wieder, aber die Abweichung spiegelt nicht die der festgelegten Zeitzone für diese Uhrzeit wider.</span><span class="sxs-lookup"><span data-stu-id="29f5b-123">Note that if this addition is simply performed on the [DateTimeOffset](xref:System.DateTimeOffset) value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span> 

<span data-ttu-id="29f5b-124">Für [DateTimeOffset](xref:System.DateTimeOffset)-Werte wird die Zuordnung zu einer Zeitzone, der sie möglicherweise angehören, aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="29f5b-124">[DateTimeOffset](xref:System.DateTimeOffset) values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="29f5b-125">Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein.</span><span class="sxs-lookup"><span data-stu-id="29f5b-125">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="29f5b-126">Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen.</span><span class="sxs-lookup"><span data-stu-id="29f5b-126">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="29f5b-127">Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:</span><span class="sxs-lookup"><span data-stu-id="29f5b-127">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="29f5b-128">Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören.</span><span class="sxs-lookup"><span data-stu-id="29f5b-128">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="29f5b-129">Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.</span><span class="sxs-lookup"><span data-stu-id="29f5b-129">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="29f5b-130">Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen.</span><span class="sxs-lookup"><span data-stu-id="29f5b-130">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="29f5b-131">Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.</span><span class="sxs-lookup"><span data-stu-id="29f5b-131">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="29f5b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29f5b-132">See Also</span></span>

[<span data-ttu-id="29f5b-133">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="29f5b-133">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="29f5b-134">Durchführen arithmetischer Datums- und Uhrzeitoperationen</span><span class="sxs-lookup"><span data-stu-id="29f5b-134">Performing arithmetic operations with dates and times</span></span>](performing-arithmetic-operations.md)

