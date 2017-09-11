---
title: "Gewusst wie: Auflösen von mehrdeutigen Zeiten"
description: "Auflösen von mehrdeutigen Zeiten"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f4ab3b4bf3487e70be7e885e9b8a2281927eb30e
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="bf587-104">Gewusst wie: Auflösen von mehrdeutigen Zeiten</span><span class="sxs-lookup"><span data-stu-id="bf587-104">How to: resolve ambiguous times</span></span>

<span data-ttu-id="bf587-105">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bf587-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="bf587-106">Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="bf587-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="bf587-107">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="bf587-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="bf587-108">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="bf587-108">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="bf587-109">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="bf587-109">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="bf587-110">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="bf587-110">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="bf587-111">Dieser Artikel zeigt, wie eine mehrdeutige Zeit durch die Annahme aufgelöst werden kann, dass es sich um die Standardzeit der Zeitzone handelt.</span><span class="sxs-lookup"><span data-stu-id="bf587-111">This article shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="bf587-112">So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="bf587-112">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="bf587-113">Rufen Sie die Methode [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) oder die Methode [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) auf, um zu ermitteln, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="bf587-113">Call the [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="bf587-114">Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit von dem [TimeSpan](xref:System.TimeSpan)-Objekt, das von der [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft der Zeitzone zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bf587-114">If the time is ambiguous, subtract the time from the [TimeSpan](xref:System.TimeSpan) object returned by the time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span>

3. <span data-ttu-id="bf587-115">Rufen Sie die `static`-Methode (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) auf, um die [Kind](xref:System.DateTime.Kind)-Eigenschaft des UTC-Datums- und Uhrzeitwerts auf [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bf587-115">Call the `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="bf587-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf587-116">Example</span></span>

<span data-ttu-id="bf587-117">Im folgenden Beispiel wird veranschaulicht die Konvertierung eines mehrdeutigen [DateTime](xref:System.DateTime)-Werts in UTC, indem angenommen wird, dass er die Standardzeit der lokalen Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="bf587-117">The following example illustrates how to convert an ambiguous [DateTime](xref:System.DateTime) to UTC by assuming that it represents the local time zone's standard time.</span></span> 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

<span data-ttu-id="bf587-118">Das Beispiel besteht aus einer Methode namens `ResolveAmbiguousTime`, die ermittelt, ob der ihr übergebene [DateTime](xref:System.DateTime)-Wert mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="bf587-118">The example consists of a method named `ResolveAmbiguousTime` that determines whether the [DateTime](xref:System.DateTime) value passed to it is ambiguous.</span></span> <span data-ttu-id="bf587-119">Wenn der Wert mehrdeutig ist, gibt die Methode einem [DateTime](xref:System.DateTime)-Wert zurück, der die entsprechende UTC-Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="bf587-119">If the value is ambiguous, the method returns a [DateTime](xref:System.DateTime) value that represents the corresponding UTC time.</span></span> <span data-ttu-id="bf587-120">Die Methode führt diese Konvertierung durch, indem sie den Wert der [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft der lokalen Zeitzone von der Ortszeit subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="bf587-120">The method handles this conversion by subtracting the value of the local time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property from the local time.</span></span> 

<span data-ttu-id="bf587-121">Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime))-Methode verarbeitet, um ein Array von [TimeSpan](xref:System.TimeSpan)-Objekten abzurufen, die die möglichen UTC-Abweichungen der mehrdeutigen Zeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="bf587-121">Ordinarily, an ambiguous time is handled by calling the [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) method to retrieve an array of [TimeSpan](xref:System.TimeSpan) objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="bf587-122">In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bf587-122">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="bf587-123">Die [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset)-Eigenschaft gibt die Abweichung zwischen UTC und der Standardzeit einer Zeitzone zurück.</span><span class="sxs-lookup"><span data-stu-id="bf587-123">The [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property returns the offset between UTC and a time zone's standard time.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf587-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf587-124">See Also</span></span>

[<span data-ttu-id="bf587-125">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="bf587-125">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="bf587-126">Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf587-126">How to: let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)


