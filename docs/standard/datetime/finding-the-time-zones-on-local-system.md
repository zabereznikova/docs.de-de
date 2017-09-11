---
title: Suchen der in einem lokalen System definierten Zeitzonen
description: Suchen der in einem lokalen System definierten Zeitzonen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e61017e2a0e26295c3be7e8265674b1a5d2ae5a3
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="7342f-104">Suchen der in einem lokalen System definierten Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7342f-104">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="7342f-105">Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse macht keinen öffentlichen Konstruktor verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7342f-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not expose a public constructor.</span></span> <span data-ttu-id="7342f-106">Daher kann das `new`-Schlüsselwort nicht zum Erstellen eines neuen [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7342f-106">As a result, the `new` keyword cannot be used to create a new [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="7342f-107">Stattdessen werden [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekte durch Abrufen von Informationen über vordefinierte Zeitzonen aus dem Betriebssystem instanziiert.</span><span class="sxs-lookup"><span data-stu-id="7342f-107">Instead, [TimeZoneInfo](xref:System.TimeZoneInfo) objects are instantiated by retrieving information on predefined time zones from the operating system.</span></span> <span data-ttu-id="7342f-108">Dieses Thema behandelt die Instanziierung einer Zeitzone aus den im Betriebssystem gespeicherten Daten.</span><span class="sxs-lookup"><span data-stu-id="7342f-108">This topic discusses instantiating a time zone from data stored by the operating system.</span></span> <span data-ttu-id="7342f-109">Darüber hinaus ermöglichen die `static`-Eigenschaften (`Shared` in Visual Basic) der [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="7342f-109">In addition, `static` (`Shared` in Visual Basic) properties of the [TimeZoneInfo](xref:System.TimeZoneInfo) class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="7342f-110">Zugreifen auf einzelne Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7342f-110">Accessing Individual Time Zones</span></span>

<span data-ttu-id="7342f-111">Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse bietet zwei vordefinierte Zeitzonenobjekte, die die UTC-Zeit und die lokale Zeitzone darstellen.</span><span class="sxs-lookup"><span data-stu-id="7342f-111">The [TimeZoneInfo](xref:System.TimeZoneInfo) class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="7342f-112">Sie werden über die Eigenschaften [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) bzw. [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="7342f-112">They are available from the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) and [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) properties, respectively.</span></span> <span data-ttu-id="7342f-113">Anweisungen zum Zugreifen auf die UTC-Zeit oder die lokalen Zeitzonen finden Sie unter [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](access-utc-and-local.md).</span><span class="sxs-lookup"><span data-stu-id="7342f-113">For instructions on accessing the UTC or local time zones, see [How to: access the predefined UTC and local time zone objects](access-utc-and-local.md).</span></span> 

<span data-ttu-id="7342f-114">Sie können auch ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt instanziieren, das jede durch das Betriebssystem definierte Zeitzone darstellt.</span><span class="sxs-lookup"><span data-stu-id="7342f-114">You can also instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents any time zone defined by the operating system.</span></span> <span data-ttu-id="7342f-115">Anweisungen zum Instanziieren eines bestimmten Zeitzonenobjekts finden Sie unter [Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="7342f-115">For instructions on instantiating a specific time zone object, see [How to: instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="7342f-116">Zeitzonenbezeichner</span><span class="sxs-lookup"><span data-stu-id="7342f-116">Time Zone Identifiers</span></span>

<span data-ttu-id="7342f-117">Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7342f-117">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="7342f-118">Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang.</span><span class="sxs-lookup"><span data-stu-id="7342f-118">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="7342f-119">In den meisten Fällen entspricht der dazugehörige Wert der [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName)-Eigenschaft, die zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7342f-119">In most cases, its value corresponds to the [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="7342f-120">Es gibt jedoch auch Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7342f-120">However, there are exceptions.</span></span> <span data-ttu-id="7342f-121">Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die dazugehörigen IDs zur Kenntnis zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="7342f-121">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span> <span data-ttu-id="7342f-122">Anweisungen zum Aufzählen von Zeitzonen finden Sie unter [Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="7342f-122">For instructions on enumerating time zones, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7342f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7342f-123">See Also</span></span>

[<span data-ttu-id="7342f-124">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7342f-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="7342f-125">Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte</span><span class="sxs-lookup"><span data-stu-id="7342f-125">How to: access the predefined UTC and local time zone objects</span></span>](access-utc-and-local.md)

[<span data-ttu-id="7342f-126">Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts</span><span class="sxs-lookup"><span data-stu-id="7342f-126">How to: instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)

[<span data-ttu-id="7342f-127">Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7342f-127">How to: enumerate time zones present on a computer</span></span>](enumerate-time-zones.md)

[<span data-ttu-id="7342f-128">Konvertieren von Uhrzeiten zwischen Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="7342f-128">Converting times between time zones</span></span>](converting-between-time-zones.md)
