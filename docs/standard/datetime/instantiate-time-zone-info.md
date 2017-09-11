---
title: 'Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts'
description: Instanziieren eines TimeZoneInfo-Objekts
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f2584d446c92d2df2f6d74533ef07fe96888d36a
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="5c6f4-104">Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts</span><span class="sxs-lookup"><span data-stu-id="5c6f4-104">How to: instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="5c6f4-105">Die gängigste Methode zum Instanziieren eines [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts ist es, Informationen darüber vom Betriebssystem abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-105">The most common way to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object is to retrieve information about it from the operating system.</span></span> <span data-ttu-id="5c6f4-106">In diesem Thema wird erläutert, wie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt vom lokalen System aus instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-106">This topic discusses how to instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object from the local system.</span></span>

## <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="5c6f4-107">So instanziieren Sie ein TimeZoneInfo-Objekt</span><span class="sxs-lookup"><span data-stu-id="5c6f4-107">To instantiate a TimeZoneInfo Object</span></span>

1. <span data-ttu-id="5c6f4-108">Deklarieren Sie ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-108">Declare a [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span>

2. <span data-ttu-id="5c6f4-109">Rufen Sie die `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String))-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-109">Call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method.</span></span>

3. <span data-ttu-id="5c6f4-110">Verarbeiten Sie alle von der Methode ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-110">Handle any exceptions thrown by the method.</span></span>

## <a name="example"></a><span data-ttu-id="5c6f4-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c6f4-111">Example</span></span>

<span data-ttu-id="5c6f4-112">Der folgende Code ruft ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt ab, das die Zeitzone „Eastern Standard Time“ darstellt und die der Ortszeit entsprechende „Eastern Standard Time“ anzeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-112">The following code retrieves a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

<span data-ttu-id="5c6f4-113">Der einzige Parameter der Methode, [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)), ist der Bezeichner der Zeitzone, die abgerufen werden soll; er entspricht der [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id)-Eigenschaft des Objekts.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-113">The [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) property.</span></span> <span data-ttu-id="5c6f4-114">Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-114">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="5c6f4-115">Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-115">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="5c6f4-116">In den meisten Fällen entspricht der dazugehörige Wert der [StandardName](xref:System.TimeZoneInfo.StandardName)-Eigenschaft eines [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts, das zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-116">In most cases, its value corresponds to the [StandardName](xref:System.TimeZoneInfo.StandardName) property of a [TimeZoneInfo](xref:System.TimeZoneInfo) object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="5c6f4-117">Es gibt jedoch auch Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-117">However, there are exceptions.</span></span> <span data-ttu-id="5c6f4-118">Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die Bezeichner der darin enthaltenen Zeitzonen zur Kenntnis zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-118">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="5c6f4-119">Eine Abbildung finden Sie unter [Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="5c6f4-119">For an illustration, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span> <span data-ttu-id="5c6f4-120">Das Thema [Suchen der auf einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md) enthält auch eine Liste ausgewählter Zeitzonenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-120">The [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="5c6f4-121">Wenn die Zeitzone gefunden wird, gibt die Methode das zugehörige [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-121">If the time zone is found, the method returns its [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="5c6f4-122">Wenn die Zeitzone gefunden wird, aber die zugehörigen Daten beschädigt oder unvollständig sind, löst die Methode eine [InvalidTimeZoneException](xref:System.InvalidTimeZoneException) aus.</span><span class="sxs-lookup"><span data-stu-id="5c6f4-122">If the time zone is found but its data is corrupted or incomplete, the method throws an [InvalidTimeZoneException](xref:System.InvalidTimeZoneException).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5c6f4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c6f4-123">See Also</span></span>

[<span data-ttu-id="5c6f4-124">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="5c6f4-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="5c6f4-125">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="5c6f4-125">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
