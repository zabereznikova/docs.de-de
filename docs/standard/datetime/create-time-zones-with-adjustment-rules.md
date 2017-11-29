---
title: 'Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln'
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
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75e1867e810090bf35a0dfc7def5785747f94382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="f4b5b-102">Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="f4b5b-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="f4b5b-103">Die präzise Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht in einem bestimmten System verschiedenen Gründen vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="f4b5b-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="f4b5b-104">Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="f4b5b-105">Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="f4b5b-106">Genaue Informationen zur zeitzonenanpassungen für einen bestimmten Zeitraum für die historischen keinen für die Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="f4b5b-107">In diesen Fällen rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigt definieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="f4b5b-108">Die Überladungen dieser Methode können Sie um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="f4b5b-109">Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit einer festen "oder" Gleitkomma Anpassungsregeln definieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="f4b5b-110">(Definitionen von Begriffen, finden Sie im Abschnitt "Zeitzone Terminology" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="f4b5b-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4b5b-111">Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht an der Registrierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="f4b5b-112">Stattdessen können sie nur über den Objektverweis zurückgegebenes aufgerufen werden der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="f4b5b-113">In diesem Thema wird gezeigt, wie Anpassungsregeln eine Zeitzone erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="f4b5b-114">Um eine Zeitzone erstellen, die nicht über Regeln zur Anpassung der Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f4b5b-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="f4b5b-115">So erstellen eine Zeitzone mit Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="f4b5b-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="f4b5b-116">Für jede Anpassung (das ist, für die Umstellung von und zurück zur Normalzeit in einem bestimmten Zeitintervall), gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="f4b5b-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="f4b5b-117">Definieren der Übergang Startzeitpunkt für die Anpassung der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="f4b5b-118">Rufen Sie die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode und übergibt ihn dann ein <xref:System.DateTime> -Wert, der festgelegt, wie lange der Übergang, ein ganzzahliger Wert, der den Monat des Übergangs definiert, ein ganzzahliger Wert, der die Woche definiert, auf dem der Übergang erfolgt, und ein <xref:System.DayOfWeek> Wert, der den Tag der Woche definiert, an dem der Übergang auftritt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="f4b5b-119">Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.TransitionTime> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="f4b5b-120">Definieren Sie den Übergang Beendigungszeit für die Anpassung der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="f4b5b-121">Rufen Sie dazu die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f4b5b-122">Dieser Methodenaufruf instanziiert ein zweites <xref:System.TimeZoneInfo.TransitionTime> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="f4b5b-123">Rufen Sie die <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> Methode, und übergeben sie die effektive Start- und Enddatum für die Anpassung einer <xref:System.TimeSpan> Objekt, das die Zeitspanne in der Übergang und die beiden definiert <xref:System.TimeZoneInfo.TransitionTime> Objekten, die beim definieren die Übergänge zu und von Sommerzeit Endzeit liegen.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="f4b5b-124">Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.AdjustmentRule> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="f4b5b-125">Weisen Sie die <xref:System.TimeZoneInfo.AdjustmentRule> Objekt, das ein Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="f4b5b-126">Anzeigename der Zeitzone zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-126">Define the time zone's display name.</span></span> <span data-ttu-id="f4b5b-127">Der Anzeigename folgt einem Standardformat in der die Zeitzone Offset von Coordinated Universal Time (UTC) in Klammern eingeschlossen und wird gefolgt von einer Zeichenfolge, die die Zeitzone, oder der Orte in der Zeitzone oder eine weitere mindestens eines der Cou identifiziert Osten oder Bereiche in der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="f4b5b-128">Der Name der Standardzeit der Zeitzone zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="f4b5b-129">Diese Zeichenfolge wird in der Regel auch als Bezeichners der Zeitzone verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="f4b5b-130">Definieren Sie den Namen der Sommerzeit der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="f4b5b-131">Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie des Zeitzonenbezeichners.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="f4b5b-132">Instanziieren einer <xref:System.TimeSpan> Objekt, das die Zeitzone Offset von UTC definiert.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="f4b5b-133">Zeitzonen mit Uhrzeiten, die später als UTC haben einen positiven Offset.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="f4b5b-134">Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="f4b5b-135">Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> Methode zum Instanziieren der neuen Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="f4b5b-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4b5b-136">Example</span></span>

<span data-ttu-id="f4b5b-137">Das folgende Beispiel definiert eine Central Normalzeit Zeitzone für den Vereinigten Staaten, die für eine Vielzahl von Zeitintervallen von 1918 auf der aktuellen Anpassungsregeln enthält.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="f4b5b-138">In diesem Beispiel erstellte Zeitzone hat mehrere Anpassungsregeln.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="f4b5b-139">Muss darauf geachtet werden, stellen Sie sicher, dass der effektive Start- und Enddatum einer Anpassungsregel nicht mit den Daten von einem anderen Anpassungsregel überlappen.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="f4b5b-140">Wenn eine Überschneidung ist ein <xref:System.InvalidTimeZoneException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="f4b5b-141">Für veränderliche Anpassungsregeln, wird der Wert 5 zum Übergeben der `week` Parameter von der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> Methode, um anzugeben, dass der Übergang in der letzten Woche eines bestimmten Monats auftritt.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="f4b5b-142">Erstellen Sie das Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekten, in denen die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> -Methodenaufruf, der Code konnte initialisieren Sie das Array der Größe erforderlich, um die Anzahl von Korrekturen für die Zeitzone erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="f4b5b-143">Dieses Codebeispiel ruft stattdessen die <xref:System.Collections.Generic.List%601.Add%2A> Methode, um eine generische jede Anpassungsregel hinzugefügt <xref:System.Collections.Generic.List%601> Auflistung von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="f4b5b-144">Der Code ruft dann die <xref:System.Collections.Generic.List%601.CopyTo%2A> Methode, um die Elemente dieser Auflistung in das Array zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="f4b5b-145">Das Beispiel verwendet außerdem die <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> Methode, um feste Datumsangaben Anpassungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="f4b5b-146">Dies ist vergleichbar mit einem Aufruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> -Methode, mit dem Unterschied, dass die It nur die Zeit, Monat und Tag der Übergang Parameter erfordert.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="f4b5b-147">Im Beispiel kann mit den folgenden Code getestet werden:</span><span class="sxs-lookup"><span data-stu-id="f4b5b-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="f4b5b-148">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f4b5b-148">Compiling the code</span></span>

<span data-ttu-id="f4b5b-149">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f4b5b-149">This example requires:</span></span>

* <span data-ttu-id="f4b5b-150">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f4b5b-150">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="f4b5b-151">Dass die folgenden Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="f4b5b-151">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="f4b5b-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4b5b-152">See also</span></span>

<span data-ttu-id="f4b5b-153">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)</span><span class="sxs-lookup"><span data-stu-id="f4b5b-153">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)</span></span>
