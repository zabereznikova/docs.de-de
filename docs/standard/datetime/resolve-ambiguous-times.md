---
title: "Vorgehensweise: Auflösen von mehrdeutigen Zeiten"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3706747848dbcd29d4ed2e81d5b7447a127a653
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="a177d-102">Vorgehensweise: Auflösen von mehrdeutigen Zeiten</span><span class="sxs-lookup"><span data-stu-id="a177d-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="a177d-103">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a177d-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="a177d-104">Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="a177d-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="a177d-105">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="a177d-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="a177d-106">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="a177d-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="a177d-107">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="a177d-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="a177d-108">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="a177d-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="a177d-109">In diesem Thema zeigt, wie eine mehrdeutige Zeit durch auflösen, vorausgesetzt, dass es die Standardzeit der Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="a177d-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="a177d-110">So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="a177d-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="a177d-111">Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode, um zu bestimmen, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="a177d-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="a177d-112">Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit aus der <xref:System.TimeSpan> von der Zeitzone des zurückgegebenen Objekts <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a177d-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="a177d-113">Rufen Sie die `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> -Methode zum Festlegen der UTC Datums- oder Zeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a177d-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a177d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a177d-114">Example</span></span>

<span data-ttu-id="a177d-115">Im folgende Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in UTC konvertiert, vorausgesetzt, dass es die Standardzeit für die lokale Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="a177d-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="a177d-116">Das Beispiel besteht eine Methode namens `ResolveAmbiguousTime` , der bestimmt, ob die <xref:System.DateTime> an sie übergebene Wert ist mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="a177d-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="a177d-117">Wenn der Wert nicht eindeutig ist, gibt die Methode eine <xref:System.DateTime> Wert, der die entsprechende UTC-Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="a177d-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="a177d-118">Die Methode führt diese Konvertierung durch Subtrahieren den Wert der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft von der Ortszeit.</span><span class="sxs-lookup"><span data-stu-id="a177d-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="a177d-119">Normalerweise wird eine mehrdeutige Zeit behandelt, durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Methode zum Abrufen eines Arrays von <xref:System.TimeSpan> Objekte, die die mehrdeutige Zeit mögliche UTC-offsets.</span><span class="sxs-lookup"><span data-stu-id="a177d-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="a177d-120">In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a177d-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="a177d-121">Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft gibt den Offset zwischen UTC und einer Zeitzone zurück.</span><span class="sxs-lookup"><span data-stu-id="a177d-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="a177d-122">In diesem Beispiel werden alle Verweise auf die lokale Zeitzone vorgenommen, durch die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft, die lokale Zeit, die Zone wird nie etwas zugewiesen, um eine Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="a177d-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="a177d-123">Dies ist eine empfohlene Vorgehensweise, da ein Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode werden alle Objekte, die die lokale Zeitzone zugewiesen ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a177d-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="a177d-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a177d-124">Compiling the code</span></span>

<span data-ttu-id="a177d-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a177d-125">This example requires:</span></span>

* <span data-ttu-id="a177d-126">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a177d-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="a177d-127">Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).</span><span class="sxs-lookup"><span data-stu-id="a177d-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="a177d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a177d-128">See also</span></span>

<span data-ttu-id="a177d-129">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[wie: Auflösen mehrdeutige Zeiten Benutzer können](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="a177d-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>
