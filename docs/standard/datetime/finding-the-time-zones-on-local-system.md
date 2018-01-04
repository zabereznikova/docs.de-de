---
title: Suchen der in einem lokalen System definierten Zeitzonen
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e61f05741c1edd86d9baad4f6ebc9f4e91318250
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="98e2f-102">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="98e2f-102">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="98e2f-103">Die <xref:System.TimeZoneInfo>-Klasse macht keinen öffentlichen Konstruktor verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98e2f-103">The <xref:System.TimeZoneInfo> class does not expose a public constructor.</span></span> <span data-ttu-id="98e2f-104">Demzufolge kann das `new`-Schlüsselwort nicht zum Erstellen eines neuen <xref:System.TimeZoneInfo>-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98e2f-104">As a result, the `new` keyword cannot be used to create a new <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="98e2f-105">Stattdessen werden <xref:System.TimeZoneInfo>-Objekte entweder durch Abrufen von Informationen über vordefinierte Zeitzonen aus der Registrierung oder durch Erstellen einer benutzerdefinierten Zeitzone instanziiert.</span><span class="sxs-lookup"><span data-stu-id="98e2f-105">Instead, <xref:System.TimeZoneInfo> objects are instantiated either by retrieving information on predefined time zones from the registry or by creating a custom time zone.</span></span> <span data-ttu-id="98e2f-106">Dieses Thema behandelt die Instanziierung einer Zeitzone von den in der Registrierung gespeicherten Daten.</span><span class="sxs-lookup"><span data-stu-id="98e2f-106">This topic discusses instantiating a time zone from data stored in the registry.</span></span> <span data-ttu-id="98e2f-107">Darüber hinaus ermöglichen die `static`-Eigenschaften (`shared` in Visual Basic) der <xref:System.TimeZoneInfo>-Klasse Zugriff auf die koordinierte Weltzeit (Universal Coordinated Time, UTC) und die lokale Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="98e2f-107">In addition, `static` (`shared` in Visual Basic) properties of the <xref:System.TimeZoneInfo> class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

> [!NOTE]
> <span data-ttu-id="98e2f-108">Für Zeitzonen, die nicht in der Registrierung definiert sind, können Sie benutzerdefinierte Zeitzonen durch Aufrufen der Überladungen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>-Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-108">For time zones that are not defined in the registry, you can create custom time zones by calling the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="98e2f-109">Erstellen einer benutzerdefinierten Zeitzone wird erläutert, der [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Themen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-109">Creating a custom time zone is discussed in the [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) topics.</span></span> <span data-ttu-id="98e2f-110">Darüber hinaus können Sie ein <xref:System.TimeZoneInfo>-Objekt durch Wiederherstellen aus einer serialisierten Zeichenfolge mit der <xref:System.TimeZoneInfo.FromSerializedString%2A>-Methode instanziieren.</span><span class="sxs-lookup"><span data-stu-id="98e2f-110">In addition, you can instantiate a <xref:System.TimeZoneInfo> object by restoring it from a serialized string with the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span> <span data-ttu-id="98e2f-111">Serialisiert und deserialisiert eine <xref:System.TimeZoneInfo> Objekt wird erläutert, der [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Themen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-111">Serializing and deserializing a <xref:System.TimeZoneInfo> object is discussed in the [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore Time Zones from an Embedded Resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) topics.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="98e2f-112">Zugreifen auf einzelne Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="98e2f-112">Accessing individual time zones</span></span>

<span data-ttu-id="98e2f-113">Die <xref:System.TimeZoneInfo>-Klasse bietet zwei vordefinierte Zeitzonenobjekte, die die koordinierte Weltzeit und die lokale Zeitzone darstellen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-113">The <xref:System.TimeZoneInfo> class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="98e2f-114">Diese werden jeweils über die <xref:System.TimeZoneInfo.Utc%2A>- und die <xref:System.TimeZoneInfo.Local%2A>-Eigenschaft zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="98e2f-114">They are available from the <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A> properties, respectively.</span></span> <span data-ttu-id="98e2f-115">Anleitungen zum Zugreifen auf die UTC oder die lokalen Zeitzonen finden Sie unter [Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md).</span><span class="sxs-lookup"><span data-stu-id="98e2f-115">For instructions on accessing the UTC or local time zones, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md).</span></span>

<span data-ttu-id="98e2f-116">Sie können auch ein <xref:System.TimeZoneInfo>-Objekt instanziieren, das die in der Registrierung definierten Zeitzonen darstellt.</span><span class="sxs-lookup"><span data-stu-id="98e2f-116">You can also instantiate a <xref:System.TimeZoneInfo> object that represents any time zone defined in the registry.</span></span> <span data-ttu-id="98e2f-117">Anleitungen zum Instanziieren einer bestimmten Zeitzonenobjekts finden Sie unter [wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="98e2f-117">For instructions on instantiating a specific time zone object, see [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="98e2f-118">Zeitzonenbezeichner</span><span class="sxs-lookup"><span data-stu-id="98e2f-118">Time zone identifiers</span></span>

<span data-ttu-id="98e2f-119">Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="98e2f-119">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="98e2f-120">Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang.</span><span class="sxs-lookup"><span data-stu-id="98e2f-120">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="98e2f-121">In den meisten Fällen entspricht der dazugehörige Wert der <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>-Eigenschaft, die zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98e2f-121">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType> property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="98e2f-122">Es gibt jedoch auch Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-122">However, there are exceptions.</span></span> <span data-ttu-id="98e2f-123">Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die dazugehörigen IDs zur Kenntnis zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="98e2f-123">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span>

## <a name="see-also"></a><span data-ttu-id="98e2f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98e2f-124">See also</span></span>

<span data-ttu-id="98e2f-125">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)
[wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md) 
 [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)</span><span class="sxs-lookup"><span data-stu-id="98e2f-125">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)
[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md)</span></span>
