---
title: 'Vorgehensweise: Auflösen mehrdeutiger Zeiten'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c98f47613479c40804dce254261c560d829d91c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586368"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="bad0f-102">Vorgehensweise: Auflösen mehrdeutiger Zeiten</span><span class="sxs-lookup"><span data-stu-id="bad0f-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="bad0f-103">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="bad0f-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="bad0f-104">Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="bad0f-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="bad0f-105">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="bad0f-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="bad0f-106">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="bad0f-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="bad0f-107">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="bad0f-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="bad0f-108">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="bad0f-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="bad0f-109">In diesem Thema wird gezeigt, wie Sie eine mehrdeutige Zeit durch auflösen, vorausgesetzt, dass er die Standardzeit der Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="bad0f-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="bad0f-110">So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="bad0f-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="bad0f-111">Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode, um zu bestimmen, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="bad0f-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="bad0f-112">Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit aus der <xref:System.TimeSpan> von der Standardzeit der Zeitzone zurückgegebenen Objekts <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bad0f-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="bad0f-113">Rufen Sie die `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> Methode zum Festlegen des UTC Datums- / Uhrzeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bad0f-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="bad0f-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bad0f-114">Example</span></span>

<span data-ttu-id="bad0f-115">Im folgende Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in UTC, indem konvertiert werden, vorausgesetzt, dass er die Standardzeit für die lokale Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="bad0f-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="bad0f-116">Das Beispiel besteht aus einer Methode namens `ResolveAmbiguousTime` , der bestimmt, ob die <xref:System.DateTime> übergebenen Wert ist nicht eindeutig.</span><span class="sxs-lookup"><span data-stu-id="bad0f-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="bad0f-117">Wenn der Wert mehrdeutig ist, gibt die Methode eine <xref:System.DateTime> -Wert, der die entsprechende UTC-Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="bad0f-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="bad0f-118">Die Methode führt diese Konvertierung durch Subtrahieren den Wert der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft von der Ortszeit.</span><span class="sxs-lookup"><span data-stu-id="bad0f-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="bad0f-119">Normalerweise erfolgt eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Methode zum Abrufen einer Gruppe von <xref:System.TimeSpan> offsets von Objekten, die möglichen UTC der mehrdeutigen Zeit enthalten.</span><span class="sxs-lookup"><span data-stu-id="bad0f-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="bad0f-120">In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bad0f-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="bad0f-121">Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.</span><span class="sxs-lookup"><span data-stu-id="bad0f-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="bad0f-122">In diesem Beispiel erfolgen alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft, die lokale Zeit, die Zone wird nie einer Objektvariablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bad0f-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="bad0f-123">Dies ist eine empfohlene Vorgehensweise, da ein Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> -Methode ungültig macht, alle Objekte, die die lokale Zeitzone zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bad0f-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="bad0f-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bad0f-124">Compiling the code</span></span>

<span data-ttu-id="bad0f-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bad0f-125">This example requires:</span></span>

* <span data-ttu-id="bad0f-126">Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).</span><span class="sxs-lookup"><span data-stu-id="bad0f-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="bad0f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bad0f-127">See also</span></span>

- [<span data-ttu-id="bad0f-128">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="bad0f-128">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="bad0f-129">Vorgehensweise: Können Sie Benutzer auflösen mehrdeutiger Zeiten</span><span class="sxs-lookup"><span data-stu-id="bad0f-129">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
