---
title: Datumsangaben, Uhrzeiten und Zeitzonen | Microsoft-Dokumentation
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a6e7e748f67cf9d2dbfe5dd9bb9b14ecf2d8c331
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---

# <a name="dates-times-and-time-zones"></a><span data-ttu-id="138ab-102">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="138ab-102">Dates, times, and time zones</span></span>

<span data-ttu-id="138ab-103">Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:</span><span class="sxs-lookup"><span data-stu-id="138ab-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <span data-ttu-id="138ab-104"><xref:System.TimeZone></span><span class="sxs-lookup"><span data-stu-id="138ab-104"><xref:System.TimeZone></span></span>

  <span data-ttu-id="138ab-105">Verwenden Sie diese Klasse zum Arbeiten mit der lokalen Zeitzone des Systems und der Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC). Die Funktionalität der <xref:System.TimeZone>-Klasse wird von der <xref:System.TimeZoneInfo>-Klasse weitgehend abgelöst.</span><span class="sxs-lookup"><span data-stu-id="138ab-105">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <span data-ttu-id="138ab-106"><xref:System.TimeZoneInfo></span><span class="sxs-lookup"><span data-stu-id="138ab-106"><xref:System.TimeZoneInfo></span></span>

  <span data-ttu-id="138ab-107">Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="138ab-107">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="138ab-108">Für Neuentwicklungen sollten Sie die <xref:System.TimeZoneInfo>-Klasse anstelle der <xref:System.TimeZone>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="138ab-108">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <span data-ttu-id="138ab-109"><xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="138ab-109"><xref:System.DateTimeOffset></span></span>

  <span data-ttu-id="138ab-110">Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="138ab-110">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="138ab-111">Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC.</span><span class="sxs-lookup"><span data-stu-id="138ab-111">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="138ab-112">Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren.</span><span class="sxs-lookup"><span data-stu-id="138ab-112">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="138ab-113">Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.</span><span class="sxs-lookup"><span data-stu-id="138ab-113">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="138ab-114">In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="138ab-114">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="138ab-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="138ab-115">In this section</span></span>

<span data-ttu-id="138ab-116">[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
: Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="138ab-116">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
 Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="138ab-117">[Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)
: Beschreibt die Verwendung der Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> beim Arbeiten mit Datums- und Uhrzeitdaten.</span><span class="sxs-lookup"><span data-stu-id="138ab-117">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)
 Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="138ab-118">[Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
: Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="138ab-118">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
 Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="138ab-119">[Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](../../../docs/standard/datetime/enumerate-time-zones.md)
: Stellt Beispiele für die Aufzählung der Zeitzonen bereit, die in der Registrierung eines Computers definiert sind und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="138ab-119">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md)
 Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="138ab-120">[Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)
: Beschreibt den Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="138ab-120">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)
 Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="138ab-121">[Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
: Beschreibt die Instanziierung eines <xref:System.TimeZoneInfo>-Objekts über die Registrierung des lokalen Systems.</span><span class="sxs-lookup"><span data-stu-id="138ab-121">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)
 Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="138ab-122">[Instanziieren eines DateTimeOffset-Objekts](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)
: Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.</span><span class="sxs-lookup"><span data-stu-id="138ab-122">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)
 Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="138ab-123">[Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="138ab-123">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
 Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="138ab-124">[Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="138ab-124">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
 Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="138ab-125">[Speichern und Wiederherstellen von Zeitzonen](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)
: Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarien, in denen diese Features verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="138ab-125">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)
 Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="138ab-126">[Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcendatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="138ab-126">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
 Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="138ab-127">[Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
: Beschreibt, wie in einer eingebetteten Ressourcendatei gespeicherte benutzerdefinierte Zeitzonen instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="138ab-127">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
 Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="138ab-128">[Durchführen arithmetischer Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)
: Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.</span><span class="sxs-lookup"><span data-stu-id="138ab-128">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md)
 Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="138ab-129">[Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
: Beschreibt die Durchführung von arithmetischen Vorgängen für Datum und Uhrzeit, die die Anpassungsregeln einer Zeitzone widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="138ab-129">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
 Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="138ab-130">[Konvertieren zwischen DateTime und DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)
: Beschreibt die Konvertierung zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.</span><span class="sxs-lookup"><span data-stu-id="138ab-130">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)
 Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="138ab-131">[Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)
: Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.</span><span class="sxs-lookup"><span data-stu-id="138ab-131">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md)
 Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="138ab-132">[Gewusst wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)
: Beschreibt die Auflösung einer nicht eindeutigen Uhrzeit durch Zuordnen der Uhrzeit zur Standarduhrzeit der Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="138ab-132">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md)
 Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="138ab-133">[Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
: Beschreibt, wie Sie den Benutzern die Zuordnung zwischen einer nicht eindeutigen lokalen Uhrzeit und der koordinierten Weltzeit überlassen.</span><span class="sxs-lookup"><span data-stu-id="138ab-133">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
 Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="138ab-134">Verweis</span><span class="sxs-lookup"><span data-stu-id="138ab-134">Reference</span></span>

<span data-ttu-id="138ab-135"><xref:System.TimeZoneInfo?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="138ab-135"><xref:System.TimeZoneInfo?displayProperty=fullName></span></span>
