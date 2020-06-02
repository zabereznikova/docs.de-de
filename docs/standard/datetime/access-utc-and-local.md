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
ms.openlocfilehash: ebb07800b2a35f4faf312dc55b8c5679079b4b68
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291408"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="06893-102">Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte</span><span class="sxs-lookup"><span data-stu-id="06893-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="06893-103">Die <xref:System.TimeZoneInfo> -Klasse stellt zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und, bereit, <xref:System.TimeZoneInfo.Local%2A> die Ihrem Code den Zugriff auf vordefinierte Zeit Zonen Objekte ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="06893-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="06893-104">In diesem Thema wird der Zugriff auf die <xref:System.TimeZoneInfo>-Objekte erläutert, die von diesen Eigenschaften zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06893-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="06893-105">So greifen Sie auf das TimeZoneInfo-Objekt für die koordinierte Weltzeit (UTC) zu</span><span class="sxs-lookup"><span data-stu-id="06893-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="06893-106">Verwenden Sie die- `static` `Shared` Eigenschaft (in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> für den Zugriff auf die koordinierte Weltzeit.</span><span class="sxs-lookup"><span data-stu-id="06893-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="06893-107">Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin auf die koordinierte Weltzeit über die- <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="06893-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="06893-108">So greifen Sie auf die lokale Zeitzone zu</span><span class="sxs-lookup"><span data-stu-id="06893-108">To access the local time zone</span></span>

1. <span data-ttu-id="06893-109">Verwenden Sie die- `static` `Shared` Eigenschaft (in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> für den Zugriff auf die lokale Systemzeitzone.</span><span class="sxs-lookup"><span data-stu-id="06893-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="06893-110">Anstatt das <xref:System.TimeZoneInfo> von der-Eigenschaft zurückgegebene-Objekt einer Objektvariablen zuzuweisen, greifen Sie weiterhin über die-Eigenschaft auf die lokale Zeitzone zu <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="06893-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="06893-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06893-111">Example</span></span>

<span data-ttu-id="06893-112">Der folgende Code verwendet die-Eigenschaft <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> und die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> -Eigenschaft, um eine Uhrzeit aus der US-amerikanischen und kanadischen Eastern Normalzeit zu konvertieren, sowie den Namen der Zeitzone auf der Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06893-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="06893-113">Sie sollten stets über die-Eigenschaft auf die lokale Zeitzone zugreifen <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> , anstatt die lokale Zeitzone einer- <xref:System.TimeZoneInfo> Objektvariablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="06893-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="06893-114">Ebenso sollten Sie immer über die-Eigenschaft auf die koordinierte Weltzeit zugreifen, <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> anstatt die UTC-Zone einer- <xref:System.TimeZoneInfo> Objektvariablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="06893-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="06893-115">Dadurch wird verhindert, <xref:System.TimeZoneInfo> dass die Objekt Variable durch einen Aufrufder-Methode ungültig gemacht wird <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="06893-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="06893-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="06893-116">Compiling the code</span></span>

<span data-ttu-id="06893-117">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="06893-117">This example requires:</span></span>

- <span data-ttu-id="06893-118">Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).</span><span class="sxs-lookup"><span data-stu-id="06893-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="06893-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06893-119">See also</span></span>

- [<span data-ttu-id="06893-120">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="06893-120">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="06893-121">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="06893-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="06893-122">Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts</span><span class="sxs-lookup"><span data-stu-id="06893-122">How to: Instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)
