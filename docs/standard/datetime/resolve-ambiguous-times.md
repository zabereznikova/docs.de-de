---
title: 'Vorgehensweise: Auflösen mehrdeutiger Zeiten'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 29a549d519bd3b6c10fef8205b30a07a71f01d1a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817756"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="86835-102">Vorgehensweise: Auflösen mehrdeutiger Zeiten</span><span class="sxs-lookup"><span data-stu-id="86835-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="86835-103">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="86835-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="86835-104">Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="86835-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="86835-105">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="86835-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="86835-106">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="86835-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="86835-107">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="86835-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="86835-108">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="86835-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="86835-109">In diesem Thema wird gezeigt, wie eine mehrdeutige Zeit aufgelöst werden kann, indem angenommen wird, dass Sie die Standardzeit der Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="86835-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="86835-110">So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="86835-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="86835-111">Mit der- <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode können Sie ermitteln, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="86835-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="86835-112">Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit von dem Objekt, das <xref:System.TimeSpan> von der-Eigenschaft der Zeitzone zurückgegeben wird <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .</span><span class="sxs-lookup"><span data-stu-id="86835-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="86835-113">Mit der `static` ( `Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> -Methode können Sie die-Eigenschaft des UTC-Datums-und Uhrzeitwerts <xref:System.DateTime.Kind%2A> auf festlegen <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="86835-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="86835-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86835-114">Example</span></span>

<span data-ttu-id="86835-115">Im folgenden Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in die UTC konvertiert wird, indem angenommen wird, dass Sie die Standardzeit der lokalen Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="86835-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="86835-116">Das Beispiel besteht aus einer Methode mit dem Namen `ResolveAmbiguousTime` , die bestimmt, ob der <xref:System.DateTime> an Sie über gegebene Wert mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="86835-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="86835-117">Wenn der Wert mehrdeutig ist, gibt die Methode einen <xref:System.DateTime> Wert zurück, der die entsprechende UTC-Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="86835-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="86835-118">Die-Methode behandelt diese Konvertierung, indem Sie den Wert der-Eigenschaft der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> von der Ortszeit subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="86835-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="86835-119">Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> -Methode verarbeitet, um ein Array von <xref:System.TimeSpan> -Objekten abzurufen, die die möglichen UTC-Offsets der mehrdeutigen Zeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="86835-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="86835-120">In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86835-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="86835-121">Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> -Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.</span><span class="sxs-lookup"><span data-stu-id="86835-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="86835-122">In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die-Eigenschaft durchgeführt <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> . die lokale Zeitzone wird nie einer Objektvariablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="86835-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="86835-123">Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der- <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode alle Objekte ungültig werden, denen die lokale Zeitzone zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="86835-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="86835-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="86835-124">Compiling the code</span></span>

<span data-ttu-id="86835-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="86835-125">This example requires:</span></span>

- <span data-ttu-id="86835-126">Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).</span><span class="sxs-lookup"><span data-stu-id="86835-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="86835-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86835-127">See also</span></span>

- [<span data-ttu-id="86835-128">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="86835-128">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="86835-129">Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="86835-129">How to: Let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)
