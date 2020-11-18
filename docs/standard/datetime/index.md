---
title: Datumsangaben, Uhrzeiten und Zeitzonen
ms.date: 04/10/2017
helpviewer_keywords:
- time zone objects [.NET]
- date and time data [.NET]
- time zones [.NET]
- times [.NET], time zones
- time [.NET], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
ms.openlocfilehash: b9dbbfa30c3398a984432fb0ecb8d0052c425f51
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817899"
---
# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen

Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:

* <xref:System.TimeZone>

  Verwenden Sie diese Klasse, um die lokale Zeitzone des Systems und die Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC) zu verarbeiten. Die Funktionalität der- <xref:System.TimeZone> Klasse wird größtenteils durch die- <xref:System.TimeZoneInfo> Klasse ersetzt.

* <xref:System.TimeZoneInfo>

  Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen. Verwenden Sie für neue Entwicklungen die <xref:System.TimeZoneInfo>-Klasse statt der <xref:System.TimeZone>-Klasse.

* <xref:System.DateTimeOffset>

  Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.

In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über Zeitzonen](time-zone-overview.md): Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.

[Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo](choosing-between-datetime.md) " Erläutert, wann die <xref:System.DateTime> Typen, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> bei der Arbeit mit Datums-und Uhrzeit Daten verwendet werden sollen.

[Finding the time zones defined on a local system (Suchen der in einem lokalen System definierten Zeitzonen)](finding-the-time-zones-on-local-system.md): Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.

[How to: Enumerate time zones present on a computer (Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen)](enumerate-time-zones.md): Stellt Beispiele für die Aufzählung der Zeitzonen bereit, die in der Registrierung eines Computers definiert sind und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.

[How to: Access the predefined UTC and local time zone objects (Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte)](access-utc-and-local.md): Beschreibt den Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.

[How to: Instantiate a TimeZoneInfo object (Vorgehensweise: Instanziieren eines TimeZoneInfo-Objekts)](instantiate-time-zone-info.md): Beschreibt die Instanziierung eines <xref:System.TimeZoneInfo>-Objekts über die Registrierung des lokalen Systems.

[Instantiating a DateTimeOffset object (Instanziieren eines DateTimeOffset-Objekts)](instantiating-a-datetimeoffset-object.md): Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.

[How to: Create time zones without adjustment rules (Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln)](create-time-zones-without-adjustment-rules.md): Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.

[How to: Create time zones with adjustment rules (Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln)](create-time-zones-with-adjustment-rules.md): Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die eine oder mehrere Umstellungen von Sommerzeit auf Normalzeit und umgekehrt unterstützt.

[Saving and restoring time zones (Speichern und Wiederherstellen von Zeitzonen)](saving-and-restoring-time-zones.md): Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarios, in denen diese Features verwendet werden können.

[How to: Save time zones to an embedded resource (Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource)](save-time-zones-to-an-embedded-resource.md): Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcendatei gespeichert werden.

[How to: Restore time zones from an embedded resource (Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource)](restore-time-zones-from-an-embedded-resource.md): Beschreibt, wie in einer eingebetteten Ressourcendatei gespeicherte benutzerdefinierte Zeitzonen instanziiert werden.

[Performing arithmetic operations with dates and times (Durchführen arithmetischer Datums- und Uhrzeitoperationen)](performing-arithmetic-operations.md): Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[How to: Use time zones in date and time arithmetic (Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen)](use-time-zones-in-arithmetic.md): Beschreibt die Durchführung von arithmetischen Vorgängen für Datum und Uhrzeit, die die Anpassungsregeln einer Zeitzone widerspiegeln.

[Converting between DateTime and DateTimeOffset (Konvertieren zwischen DateTime und DateTimeOffset)](converting-between-datetime-and-offset.md): Beschreibt die Konvertierung zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Converting times between time zones (Konvertieren von Uhrzeiten zwischen Zeitzonen)](converting-between-time-zones.md): Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.

[How to: Resolve ambiguous times (Vorgehensweise: Auflösen von mehrdeutigen Zeiten)](resolve-ambiguous-times.md): Beschreibt die Auflösung einer nicht eindeutigen Uhrzeit durch Zuordnen der Uhrzeit zur Standarduhrzeit der Zeitzone.

[Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](let-users-resolve-ambiguous-times.md): Beschreibt, wie Sie den Benutzern die Zuordnung zwischen einer nicht eindeutigen lokalen Uhrzeit und der koordinierten Weltzeit überlassen.

## <a name="reference"></a>Referenz

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
