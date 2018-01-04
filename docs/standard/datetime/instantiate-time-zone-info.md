---
title: 'Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts'
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
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59c23b4517e1150a8b17dd41667f3e793809fd21
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="d9530-102">Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts</span><span class="sxs-lookup"><span data-stu-id="d9530-102">How to: Instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="d9530-103">Die gängigste Methode zum Instanziieren eines <xref:System.TimeZoneInfo> -Objekts ist es, Informationen darüber aus der Registrierung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d9530-103">The most common way to instantiate a <xref:System.TimeZoneInfo> object is to retrieve information about it from the registry.</span></span> <span data-ttu-id="d9530-104">In diesem Thema wird erläutert, wie ein <xref:System.TimeZoneInfo> -Objekt aus der Registrierung des lokalen Systems instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="d9530-104">This topic discusses how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

### <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="d9530-105">So instanziieren Sie ein TimeZoneInfo-Objekt</span><span class="sxs-lookup"><span data-stu-id="d9530-105">To instantiate a TimeZoneInfo object</span></span>

1. <span data-ttu-id="d9530-106">Deklarieren Sie ein <xref:System.TimeZoneInfo> -Objekt.</span><span class="sxs-lookup"><span data-stu-id="d9530-106">Declare a <xref:System.TimeZoneInfo> object.</span></span>

2. <span data-ttu-id="d9530-107">Rufen Sie die `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="d9530-107">Call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method.</span></span>

3. <span data-ttu-id="d9530-108">Verarbeiten Sie alle Ausnahmen, die von der Methode ausgelöst werden, insbesondere die <xref:System.TimeZoneNotFoundException> -Ausnahme, die ausgelöst wird, wenn die Zeitzone nicht in der Registrierung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d9530-108">Handle any exceptions thrown by the method, particularly the <xref:System.TimeZoneNotFoundException> that is thrown if the time zone is not defined in the registry.</span></span>

## <a name="example"></a><span data-ttu-id="d9530-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9530-109">Example</span></span>

<span data-ttu-id="d9530-110">Der folgende Code ruft ein <xref:System.TimeZoneInfo> -Objekt ab, das die Zeitzone "Eastern Standard Time" darstellt und die der Ortszeit entsprechende "Eastern Standard Time" anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d9530-110">The following code retrieves a <xref:System.TimeZoneInfo> object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<span data-ttu-id="d9530-111">Die <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> einzelne Methodenparameter ist der Bezeichner der Zeitzone, die Sie abrufen möchten, die des Objekts entspricht <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d9530-111">The <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d9530-112">Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d9530-112">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="d9530-113">Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang.</span><span class="sxs-lookup"><span data-stu-id="d9530-113">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="d9530-114">In den meisten Fällen entspricht der dazugehörige Wert der <xref:System.TimeZoneInfo.StandardName%2A> -Eigenschaft eines <xref:System.TimeZoneInfo> -Objekts, das zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9530-114">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A> property of a <xref:System.TimeZoneInfo> object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="d9530-115">Es gibt jedoch auch Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="d9530-115">However, there are exceptions.</span></span> <span data-ttu-id="d9530-116">Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die Bezeichner der darin enthaltenen Zeitzonen zur Kenntnis zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="d9530-116">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="d9530-117">Eine Veranschaulichung finden Sie unter [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="d9530-117">For an illustration, see [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span></span> <span data-ttu-id="d9530-118">Das Thema [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) enthält auch eine Liste ausgewählter Zeitzonenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="d9530-118">The [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="d9530-119">Wenn die Zeitzone gefunden wird, gibt die Methode das zugehörige <xref:System.TimeZoneInfo> -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="d9530-119">If the time zone is found, the method returns its <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="d9530-120">Wenn die Zeitzone nicht gefunden wird, löst die Methode eine <xref:System.TimeZoneNotFoundException>aus.</span><span class="sxs-lookup"><span data-stu-id="d9530-120">If the time zone is not found, the method throws a <xref:System.TimeZoneNotFoundException>.</span></span> <span data-ttu-id="d9530-121">Wenn die Zeitzone gefunden wird, aber die zugehörigen Daten beschädigt oder unvollständig sind, löst die Methode eine <xref:System.InvalidTimeZoneException>aus.</span><span class="sxs-lookup"><span data-stu-id="d9530-121">If the time zone is found but its data is corrupted or incomplete, the method throws an <xref:System.InvalidTimeZoneException>.</span></span>

<span data-ttu-id="d9530-122">Wenn Ihre Anwendung eine Zeitzone benötigt, die vorhanden sein muss, sollten Sie zuerst die <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> -Methode aufrufen, um die Zeitzonendaten aus der Registrierung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d9530-122">If your application relies on a time zone that must be present, you should first call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method to retrieve the time zone information from the registry.</span></span> <span data-ttu-id="d9530-123">Wenn der Methodenaufruf fehlschlägt, sollte der Ausnahmehandler dann eine neue Instanz der Zeitzone erstellen oder diese durch Deserialisieren eines serialisierten <xref:System.TimeZoneInfo> -Objekts neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9530-123">If the method call fails, your exception handler should then either create a new instance of the time zone or re-create it by deserializing a serialized <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="d9530-124">Finden Sie unter [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d9530-124">See [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) for an example.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9530-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9530-125">See also</span></span>

<span data-ttu-id="d9530-126">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[suchen die in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zone-Objekte](../../../docs/standard/datetime/access-utc-and-local.md)</span><span class="sxs-lookup"><span data-stu-id="d9530-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)</span></span>
