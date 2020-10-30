---
title: 'Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], adjustment rule
- time zones [.NET], creating
- adjustment rule [.NET]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
ms.openlocfilehash: e3bce4d915a8d979f043b5c4a49b20ce3e0596c9
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063793"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="0b785-102">Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="0b785-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="0b785-103">Die genauen Zeitzoneninformationen, die von einer Anwendung benötigt werden, sind möglicherweise aus verschiedenen Gründen nicht auf einem bestimmten System vorhanden:</span><span class="sxs-lookup"><span data-stu-id="0b785-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="0b785-104">Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.</span><span class="sxs-lookup"><span data-stu-id="0b785-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="0b785-105">Daten über die Zeitzone wurden geändert oder aus der Registrierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="0b785-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="0b785-106">Die Zeitzone ist zwar vorhanden, verfügt jedoch nicht über genaue Informationen zu Zeit Zonen Anpassungen für einen bestimmten historischen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="0b785-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="0b785-107">In diesen Fällen können Sie die- <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode zum Definieren der Zeitzone, die für Ihre Anwendung erforderlich ist, aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b785-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="0b785-108">Sie können die über Ladungen dieser Methode verwenden, um eine Zeitzone mit oder ohne Anpassungsregeln zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b785-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="0b785-109">Wenn die Zeitzone die Sommerzeit unterstützt, können Sie Anpassungen mit festgelegten oder Gleit Komma Anpassungsregeln definieren.</span><span class="sxs-lookup"><span data-stu-id="0b785-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="0b785-110">(Informationen zu Definitionen dieser Begriffe finden Sie im Abschnitt "Zeit Zonen Terminologie" unter [Übersicht über](time-zone-overview.md)die Zeitzone.)</span><span class="sxs-lookup"><span data-stu-id="0b785-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b785-111">Benutzerdefinierte Zeitzonen, die durch den Aufruf der-Methode erstellt wurden <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> , werden nicht zur Registrierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0b785-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="0b785-112">Stattdessen kann nur über den Objekt Verweis darauf zugegriffen werden, der durch den-Methoden-Befehl zurückgegeben wird <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> .</span><span class="sxs-lookup"><span data-stu-id="0b785-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="0b785-113">In diesem Thema wird gezeigt, wie Sie eine Zeitzone ohne Anpassungsregeln erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b785-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="0b785-114">Informationen zum Erstellen einer Zeitzone, die Anpassungsregeln für die Sommerzeit unterstützt, finden Sie unter Gewusst [wie: Erstellen von Zeitzonen mit Anpassungsregeln](create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0b785-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="0b785-115">So erstellen Sie eine Zeitzone ohne Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="0b785-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="0b785-116">Hiermit wird der Anzeige Name der Zeitzone definiert.</span><span class="sxs-lookup"><span data-stu-id="0b785-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="0b785-117">Der Anzeige Name folgt einem Recht standardmäßigen Format, in dem der Offset der Zeitzone von der koordinierten Weltzeit (UTC) in Klammern eingeschlossen wird, gefolgt von einer Zeichenfolge, die die Zeitzone, eine oder mehrere Städte in der Zeitzone oder ein oder mehrere Länder oder Regionen in der Zeitzone angibt.</span><span class="sxs-lookup"><span data-stu-id="0b785-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="0b785-118">Hiermit wird der Name der Standardzeit der Zeitzone definiert.</span><span class="sxs-lookup"><span data-stu-id="0b785-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="0b785-119">In der Regel wird diese Zeichenfolge auch als Bezeichner der Zeitzone verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b785-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="0b785-120">Wenn Sie einen anderen Bezeichner als den Standardnamen der Zeitzone verwenden möchten, definieren Sie den Zeit Zonen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="0b785-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="0b785-121">Instanziieren Sie ein <xref:System.TimeSpan> -Objekt, das den Zeit Zonen Offset von UTC definiert.</span><span class="sxs-lookup"><span data-stu-id="0b785-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="0b785-122">Zeitzonen mit Uhrzeiten, die später als UTC liegen, haben einen positiven Offset.</span><span class="sxs-lookup"><span data-stu-id="0b785-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="0b785-123">Zeitzonen mit Zeiten, die älter sind als UTC, haben einen negativen Offset.</span><span class="sxs-lookup"><span data-stu-id="0b785-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="0b785-124">Ruft die- <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> Methode auf, um die neue Zeitzone zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="0b785-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="0b785-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b785-125">Example</span></span>

<span data-ttu-id="0b785-126">Im folgenden Beispiel wird eine benutzerdefinierte Zeitzone für Mawson (Antarktis) definiert, die über keine Anpassungsregeln verfügt.</span><span class="sxs-lookup"><span data-stu-id="0b785-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="0b785-127">Die Zeichenfolge, die der <xref:System.TimeZoneInfo.DisplayName%2A> -Eigenschaft zugewiesen ist, folgt einem Standardformat, bei dem der Offset der Zeitzone von UTC eine benutzerfreundliche Beschreibung der Zeitzone folgt.</span><span class="sxs-lookup"><span data-stu-id="0b785-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="0b785-128">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0b785-128">Compiling the code</span></span>

<span data-ttu-id="0b785-129">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b785-129">This example requires:</span></span>

- <span data-ttu-id="0b785-130">Die folgenden Namespaces werden importiert:</span><span class="sxs-lookup"><span data-stu-id="0b785-130">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="0b785-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b785-131">See also</span></span>

- [<span data-ttu-id="0b785-132">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="0b785-132">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="0b785-133">Übersicht über Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="0b785-133">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="0b785-134">Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln</span><span class="sxs-lookup"><span data-stu-id="0b785-134">How to: Create time zones with adjustment rules</span></span>](create-time-zones-with-adjustment-rules.md)
