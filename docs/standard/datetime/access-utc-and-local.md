---
title: 'Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
description: 'Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: fcc48e40cdad25c6142dbc3a86513b816378fa4b
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="c05e5-104">Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte</span><span class="sxs-lookup"><span data-stu-id="c05e5-104">How to: access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="c05e5-105">Die Klasse [System.TimeZoneInfo](xref:System.TimeZoneInfo) verfügt über zwei Eigenschaften – `Utc` und `Local` – die Ihrem Code den Zugriff auf vordefinierte Zeitzonenobjekte ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class provides two properties, `Utc` and `Local`, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="c05e5-106">In diesem Thema wird der Zugriff auf die `TimeZoneInfo`-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c05e5-106">This topic discusses how to access the `TimeZoneInfo` objects returned by those properties.</span></span>

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="c05e5-107">So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu</span><span class="sxs-lookup"><span data-stu-id="c05e5-107">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="c05e5-108">Verwenden Sie die **static**-Eigenschaft (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) für den Zugriff auf die koordinierte Weltzeit.</span><span class="sxs-lookup"><span data-stu-id="c05e5-108">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="c05e5-109">Anstatt das von der Eigenschaft zurückgegebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt einer Objektvariablen zuzuweisen, fahren Sie fort, indem Sie mit der Eigenschaft [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) auf die koordinierte Weltzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-109">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property.</span></span>


## <a name="to-access-the-local-time-zone"></a><span data-ttu-id="c05e5-110">So greifen Sie auf die lokale Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="c05e5-110">To access the local time zone</span></span>

1. <span data-ttu-id="c05e5-111">Verwenden Sie die **static**-Eigenschaft (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) für den Zugriff auf die lokale Systemzeitzone.</span><span class="sxs-lookup"><span data-stu-id="c05e5-111">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property to access the local system time zone.</span></span>

2. <span data-ttu-id="c05e5-112">Anstatt das von der Eigenschaft zurückgegebene [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt einer Objektvariablen zuzuweisen, fahren Sie fort, indem Sie mit der Eigenschaft [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) auf die lokale Zeitzone zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-112">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property.</span></span>

## <a name="example"></a><span data-ttu-id="c05e5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c05e5-113">Example</span></span>

<span data-ttu-id="c05e5-114">Im folgenden Code werden die Eigenschaften [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) und [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) verwendet,um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren, sowie den Namen der Zeitzone auf der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-114">The following code uses the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) and [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

<span data-ttu-id="c05e5-115">Sie sollten stets mit der Eigenschaft [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) auf die lokale Zeitzone zugreifen, anstatt die lokale Zeitzone einer [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-115">You should always access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property rather than assigning the local time zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="c05e5-116">Ebenso sollten Sie stets mit der Eigenschaft [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) auf die koordinierte Weltzeit zugreifen, anstatt die UTC-Zone einer [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c05e5-116">Similarly, you should always access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property rather than assigning the UTC zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="c05e5-117">Dies verhindert, dass die [TimeZoneInfo](xref:System.TimeZoneInfo)-Objektvariable durch eine externe Methode ungültig gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c05e5-117">This prevents the [TimeZoneInfo](xref:System.TimeZoneInfo) object variable from being invalidated by an external method.</span></span>


## <a name="see-also"></a><span data-ttu-id="c05e5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c05e5-118">See Also</span></span>

[<span data-ttu-id="c05e5-119">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="c05e5-119">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="c05e5-120">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="c05e5-120">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)

