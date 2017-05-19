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

# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen

Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:

* <xref:System.TimeZone>

  Verwenden Sie diese Klasse zum Arbeiten mit der lokalen Zeitzone des Systems und der Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC). Die Funktionalität der <xref:System.TimeZone>-Klasse wird von der <xref:System.TimeZoneInfo>-Klasse weitgehend abgelöst.

* <xref:System.TimeZoneInfo>

  Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen. Für Neuentwicklungen sollten Sie die <xref:System.TimeZoneInfo>-Klasse anstelle der <xref:System.TimeZone>-Klasse verwenden.

* <xref:System.DateTimeOffset>

  Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.

In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
: Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.

[Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)
: Beschreibt die Verwendung der Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> beim Arbeiten mit Datums- und Uhrzeitdaten.

[Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
: Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.

[Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](../../../docs/standard/datetime/enumerate-time-zones.md)
: Stellt Beispiele für die Aufzählung der Zeitzonen bereit, die in der Registrierung eines Computers definiert sind und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.

[Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)
: Beschreibt den Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.

[Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)
: Beschreibt die Instanziierung eines <xref:System.TimeZoneInfo>-Objekts über die Registrierung des lokalen Systems.

[Instanziieren eines DateTimeOffset-Objekts](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)
: Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.

[Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.

[Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.

[Speichern und Wiederherstellen von Zeitzonen](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)
: Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarien, in denen diese Features verwendet werden können.

[Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
: Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcendatei gespeichert werden.

[Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
: Beschreibt, wie in einer eingebetteten Ressourcendatei gespeicherte benutzerdefinierte Zeitzonen instanziiert werden.

[Durchführen arithmetischer Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)
: Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
: Beschreibt die Durchführung von arithmetischen Vorgängen für Datum und Uhrzeit, die die Anpassungsregeln einer Zeitzone widerspiegeln.

[Konvertieren zwischen DateTime und DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)
: Beschreibt die Konvertierung zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)
: Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.

[Gewusst wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)
: Beschreibt die Auflösung einer nicht eindeutigen Uhrzeit durch Zuordnen der Uhrzeit zur Standarduhrzeit der Zeitzone.

[Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
: Beschreibt, wie Sie den Benutzern die Zuordnung zwischen einer nicht eindeutigen lokalen Uhrzeit und der koordinierten Weltzeit überlassen.

## <a name="reference"></a>Verweis

<xref:System.TimeZoneInfo?displayProperty=fullName>
