---
title: 'Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln'
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 181d61de62ec9560b46732ad304b4934d4f55fa2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="edea1-102">Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="edea1-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="edea1-103">Die präzise Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht in einem bestimmten System verschiedenen Gründen vorhanden sein:</span><span class="sxs-lookup"><span data-stu-id="edea1-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="edea1-104">Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.</span><span class="sxs-lookup"><span data-stu-id="edea1-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="edea1-105">Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="edea1-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="edea1-106">Die Zeitzone ist vorhanden, aber keine genaue Informationen zur zeitzonenanpassungen für einen bestimmten vergangene Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="edea1-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="edea1-107">In diesen Fällen rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigt definieren.</span><span class="sxs-lookup"><span data-stu-id="edea1-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="edea1-108">Die Überladungen dieser Methode können Sie um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="edea1-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="edea1-109">Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit einer festen "oder" Gleitkomma Anpassungsregeln definieren.</span><span class="sxs-lookup"><span data-stu-id="edea1-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="edea1-110">(Definitionen von Begriffen, finden Sie im Abschnitt "Zeitzone Terminology" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="edea1-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edea1-111">Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht an der Registrierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="edea1-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="edea1-112">Stattdessen können sie nur über den Objektverweis zurückgegebenes aufgerufen werden der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="edea1-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="edea1-113">Dieses Thema veranschaulicht das Erstellen ohne Anpassungsregeln einer Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="edea1-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="edea1-114">Um eine Zeitzone zu erstellen, die die Anpassungsregeln Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="edea1-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="edea1-115">So erstellen eine Zeitzone ohne Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="edea1-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="edea1-116">Anzeigename der Zeitzone zu definieren.</span><span class="sxs-lookup"><span data-stu-id="edea1-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="edea1-117">Der Anzeigename folgt einem Standardformat in der die Zeitzone Offset von Coordinated Universal Time (UTC) in Klammern eingeschlossen und wird gefolgt von einer Zeichenfolge, die die Zeitzone, oder der Orte in der Zeitzone oder eine weitere mindestens eines der Cou identifiziert Osten oder Bereiche in der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="edea1-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="edea1-118">Der Name der Standardzeit der Zeitzone zu definieren.</span><span class="sxs-lookup"><span data-stu-id="edea1-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="edea1-119">Diese Zeichenfolge wird in der Regel auch als Bezeichners der Zeitzone verwendet.</span><span class="sxs-lookup"><span data-stu-id="edea1-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="edea1-120">Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie des Zeitzonenbezeichners.</span><span class="sxs-lookup"><span data-stu-id="edea1-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="edea1-121">Instanziieren einer <xref:System.TimeSpan> Objekt, das die Zeitzone Offset von UTC definiert.</span><span class="sxs-lookup"><span data-stu-id="edea1-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="edea1-122">Zeitzonen mit Uhrzeiten, die später als UTC haben einen positiven Offset.</span><span class="sxs-lookup"><span data-stu-id="edea1-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="edea1-123">Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.</span><span class="sxs-lookup"><span data-stu-id="edea1-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="edea1-124">Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> Methode zum Instanziieren der neuen Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="edea1-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="edea1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="edea1-125">Example</span></span>

<span data-ttu-id="edea1-126">Das folgende Beispiel definiert eine benutzerdefinierte Zeitzone für Mawson, Antarktis, die keine Anpassungsregeln verfügt.</span><span class="sxs-lookup"><span data-stu-id="edea1-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="edea1-127">Die zugewiesene Zeichenfolge die <xref:System.TimeZoneInfo.DisplayName%2A> Eigenschaft resultiert aus einem Standardformat in dem Offset von UTC in die Zeitzone eine Beschreibung der Zeitzone folgt.</span><span class="sxs-lookup"><span data-stu-id="edea1-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="edea1-128">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="edea1-128">Compiling the code</span></span>

<span data-ttu-id="edea1-129">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="edea1-129">This example requires:</span></span>

* <span data-ttu-id="edea1-130">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="edea1-130">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="edea1-131">Dass die folgenden Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="edea1-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="edea1-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edea1-132">See also</span></span>

<span data-ttu-id="edea1-133">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span><span class="sxs-lookup"><span data-stu-id="edea1-133">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)</span></span>
