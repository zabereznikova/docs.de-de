---
title: 'Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d36b5ff4912b09101694dd0e83291053260f0bf9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586427"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="76e85-102">Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte</span><span class="sxs-lookup"><span data-stu-id="76e85-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="76e85-103">Die <xref:System.TimeZoneInfo> Klasse enthält zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, die Ihrem Code den Zugriff auf vordefinierte Zeitzonenobjekte ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="76e85-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="76e85-104">In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="76e85-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="76e85-105">So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu</span><span class="sxs-lookup"><span data-stu-id="76e85-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="76e85-106">Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft, um die koordinierte Weltzeit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="76e85-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="76e85-107">Anstatt die Zuweisung der <xref:System.TimeZoneInfo> Objekt einer Objektvariablen, von der Eigenschaft zurückgegebenen weiter, auf die koordinierte Weltzeit zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="76e85-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="76e85-108">So greifen Sie auf die lokale Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="76e85-108">To access the local time zone</span></span>

1. <span data-ttu-id="76e85-109">Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft, um die Zeitzone des lokalen Systems zugreifen.</span><span class="sxs-lookup"><span data-stu-id="76e85-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="76e85-110">Anstatt die Zuweisung der <xref:System.TimeZoneInfo> weiterhin die lokale Zeitzone zugreifen, von der Eigenschaft zurückgegebenen Objekts, einer Objektvariablen, die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="76e85-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="76e85-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76e85-111">Example</span></span>

<span data-ttu-id="76e85-112">Der folgende code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaften, die zum Konvertieren einer Uhrzeit aus der US-amerikanischen und kanadischen Eastern Standard Time, sowie den Namen in der Konsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="76e85-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="76e85-113">Sie sollten immer die lokale Zeitzone zugreifen der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft anstatt der lokalen Zeit zone ein <xref:System.TimeZoneInfo> Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="76e85-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="76e85-114">Entsprechend sollten Sie immer koordinierte Weltzeit zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft anstatt die UTC-zone zu einer <xref:System.TimeZoneInfo> Objektvariable.</span><span class="sxs-lookup"><span data-stu-id="76e85-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="76e85-115">Dies verhindert, dass die <xref:System.TimeZoneInfo> -Objektvariable wird durch einen Aufruf für ungültig erklärt die <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="76e85-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="76e85-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="76e85-116">Compiling the code</span></span>

<span data-ttu-id="76e85-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76e85-117">This example requires:</span></span>

* <span data-ttu-id="76e85-118">Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).</span><span class="sxs-lookup"><span data-stu-id="76e85-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="76e85-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76e85-119">See also</span></span>

- [<span data-ttu-id="76e85-120">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="76e85-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="76e85-121">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="76e85-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="76e85-122">Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts</span><span class="sxs-lookup"><span data-stu-id="76e85-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)
