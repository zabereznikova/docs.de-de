---
title: 'Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zone-Objekte'
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
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4538407bc66ad7974a9a4998c8e5d7ccb38fab4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="fdba6-102">Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zone-Objekte</span><span class="sxs-lookup"><span data-stu-id="fdba6-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="fdba6-103">Die <xref:System.TimeZoneInfo> Klasse enthält zwei Eigenschaften <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, die vordefinierte Zeitzonenobjekte Ihren Codezugriff erteilen.</span><span class="sxs-lookup"><span data-stu-id="fdba6-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="fdba6-104">In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fdba6-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="fdba6-105">So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu</span><span class="sxs-lookup"><span data-stu-id="fdba6-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="fdba6-106">Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> koordinierte Weltzeit aufzurufende Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fdba6-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="fdba6-107">Anstatt Zuweisen der <xref:System.TimeZoneInfo> Objekt von der Eigenschaft einer Objektvariablen zurückgegebene weiterhin Coordinated Universal Time, über den Zugriff auf die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fdba6-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="fdba6-108">So greifen Sie auf die lokale Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="fdba6-108">To access the local time zone</span></span>

1. <span data-ttu-id="fdba6-109">Verwenden der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft, um die Zeitzone des lokalen Systems zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fdba6-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="fdba6-110">Anstatt Zuweisen der <xref:System.TimeZoneInfo> weiterhin über die lokale Zeitzone zugreifen, von der Eigenschaft an eine Objektvariable zurückgegebene Objekt der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fdba6-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="fdba6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdba6-111">Example</span></span>

<span data-ttu-id="fdba6-112">Der folgende code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaften zum Konvertieren einer Uhrzeit aus der USA und Kanadas Eastern Standard Time Zone sowie der Name der Zeitzone in der Konsole anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fdba6-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="fdba6-113">Sollten Sie stets über die lokale Zeitzone zugreifen der <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Eigenschaft anstatt der lokalen Zeit zone eine <xref:System.TimeZoneInfo> Object-Variablen.</span><span class="sxs-lookup"><span data-stu-id="fdba6-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="fdba6-114">Ebenso sollten Sie stets Coordinated Universal Time, über zugreifen der <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft anstatt die UTC-zone auf eine <xref:System.TimeZoneInfo> Object-Variablen.</span><span class="sxs-lookup"><span data-stu-id="fdba6-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="fdba6-115">Dies verhindert, dass die <xref:System.TimeZoneInfo> Objektvariable aus wird durch einen Aufruf für ungültig erklärt die <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="fdba6-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="fdba6-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fdba6-116">Compiling the code</span></span>

<span data-ttu-id="fdba6-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fdba6-117">This example requires:</span></span>

* <span data-ttu-id="fdba6-118">Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fdba6-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="fdba6-119">Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).</span><span class="sxs-lookup"><span data-stu-id="fdba6-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="fdba6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdba6-120">See also</span></span>

<span data-ttu-id="fdba6-121">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[suchen die in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span><span class="sxs-lookup"><span data-stu-id="fdba6-121">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span></span>
