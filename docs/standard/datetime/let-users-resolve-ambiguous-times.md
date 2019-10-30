---
title: 'Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: f988616a4b2a5d8202c87e3be3cb23c7f9f1f130
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122279"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="1ee3c-102">Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer</span><span class="sxs-lookup"><span data-stu-id="1ee3c-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="1ee3c-103">Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="1ee3c-104">Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="1ee3c-105">Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1ee3c-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="1ee3c-106">Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

- <span data-ttu-id="1ee3c-107">Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="1ee3c-108">Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="1ee3c-109">In diesem Thema wird gezeigt, wie ein Benutzer eine mehrdeutige Zeit auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="1ee3c-110">So lassen Sie eine mehrdeutige Zeit vom Benutzer auflösen</span><span class="sxs-lookup"><span data-stu-id="1ee3c-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="1ee3c-111">Holen Sie die Datums- und Uhrzeiteingabe vom Benutzer ein.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="1ee3c-112">Ruft die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>-Methode auf, um zu bestimmen, ob die Zeit mehrdeutig ist.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="1ee3c-113">Wenn die Zeit mehrdeutig ist, rufen Sie die <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>-Methode auf, um ein Array mit <xref:System.TimeSpan> Objekten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="1ee3c-114">Jedes Element im Array enthält einen UTC-Offset, dem die mehrdeutige Zeit zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="1ee3c-115">Ermöglichen Sie dem Benutzer die Auswahl der gewünschten Abweichung.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="1ee3c-116">Sie erhalten das UTC-Datum und die UTC-Uhrzeit durch Subtrahieren der vom Benutzer ausgewählten Abweichung von der lokalen Zeit.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="1ee3c-117">Mit der `static`-Methode (`Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A>-Methode die <xref:System.DateTime.Kind%2A>-Eigenschaft des UTC-Datums-und Uhrzeitwerts auf <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>festlegen.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="1ee3c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ee3c-118">Example</span></span>

<span data-ttu-id="1ee3c-119">Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn die Angabe mehrdeutig ist, muss der Benutzer die UTC-Zeit auswählen, die der mehrdeutigen Zeit zuzuordnen ist.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="1ee3c-120">Der Kern des Beispielcodes verwendet ein Array von <xref:System.TimeSpan>-Objekten, um mögliche Offsets der mehrdeutigen Zeit von UTC anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="1ee3c-121">Allerdings sind diese Abweichungen für den Benutzer wahrscheinlich eher unverständlich.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="1ee3c-122">Um die Bedeutung der Abweichungen zu erläutern, bezeichnet der Code außerdem, ob eine Abweichung die Standardzeit oder die Sommerzeit der lokalen Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="1ee3c-123">Der Code bestimmt, welche Uhrzeit Standard und welche Zeit Sommerzeit ist, indem der Offset mit dem Wert der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>-Eigenschaft verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="1ee3c-124">Diese Eigenschaft gibt die Differenz zwischen UTC und der Standardzeit der Zeitzone an.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="1ee3c-125">In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>-Eigenschaft erstellt. die lokale Zeitzone wird nie einer Objektvariablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="1ee3c-126">Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>-Methode alle Objekte, denen die lokale Zeitzone zugewiesen ist, ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="1ee3c-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="1ee3c-127">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1ee3c-127">Compiling the code</span></span>

<span data-ttu-id="1ee3c-128">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ee3c-128">This example requires:</span></span>

- <span data-ttu-id="1ee3c-129">, Dass der <xref:System> Namespace mit der `using`-Anweisung importiert werden soll C# (erforderlich im Code).</span><span class="sxs-lookup"><span data-stu-id="1ee3c-129">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ee3c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee3c-130">See also</span></span>

- [<span data-ttu-id="1ee3c-131">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="1ee3c-131">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="1ee3c-132">Vorgehensweise: Auflösen mehrdeutiger Zeiten</span><span class="sxs-lookup"><span data-stu-id="1ee3c-132">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)
