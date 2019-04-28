---
title: Datumsangaben, Uhrzeiten und Zeitzonen
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5355666b95d75fc18d0188c978c186690ee9ccca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61819703"
---
# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen

Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:

* <xref:System.TimeZone>

  Verwenden Sie diese Klasse zum Arbeiten mit der lokalen Zeitzone des Systems und der Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC). Die Funktionalität der <xref:System.TimeZone>-Klasse wird von der <xref:System.TimeZoneInfo>-Klasse weitgehend abgelöst.

* <xref:System.TimeZoneInfo>

  Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen. Verwenden Sie für neue Entwicklungen die <xref:System.TimeZoneInfo>-Klasse statt der <xref:System.TimeZone>-Klasse.

* <xref:System.DateTimeOffset>

  Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.

In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md): Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.

[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo (Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo)](../../../docs/standard/datetime/choosing-between-datetime.md): Beschreibt die Verwendung der Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> beim Arbeiten mit Datums- und Uhrzeitdaten.

[Finding the time zones defined on a local system (Suchen der in einem lokalen System definierten Zeitzonen)](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md): Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.

[Vorgehensweise: Aufzählen der auf einem Computer vorhandenen Zeitzonen](../../../docs/standard/datetime/enumerate-time-zones.md) enthält Beispiele für die Aufzählung der Zeitzonen, in der Registrierung eines Computers definiert und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.

[Vorgehensweise: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md) wird beschrieben, wie auf koordinierte Weltzeit und die lokale Zeitzone zugreifen.

[Vorgehensweise: Instanziieren ein TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md) beschreibt, wie Sie instanziieren ein <xref:System.TimeZoneInfo> Objekt aus der Registrierung des lokalen Systems.

[Instantiating a DateTimeOffset object (Instanziieren eines DateTimeOffset-Objekts)](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md): Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.

[Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) wird beschrieben, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit und nicht unterstützt.

[Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) wird beschrieben, wie eine benutzerdefinierte Zeitzone erstellt wird, die eine oder mehrere umstellungen und von Sommerzeit unterstützt.

[Saving and restoring time zones (Speichern und Wiederherstellen von Zeitzonen)](../../../docs/standard/datetime/saving-and-restoring-time-zones.md): Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarios, in denen diese Features verwendet werden können.

[Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) wird beschrieben, wie eine benutzerdefinierte Zeitzone erstellt, und speichern Sie die Informationen in einer Ressourcendatei gespeichert.

[Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) beschreibt, wie Sie benutzerdefinierte Zeitzonen instanziiert werden, die in einer eingebetteten Ressourcendatei gespeichert wurden.

[Performing arithmetic operations with dates and times (Durchführen arithmetischer Datums- und Uhrzeitoperationen)](../../../docs/standard/datetime/performing-arithmetic-operations.md): Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) beschreibt die Durchführung von Datums- und uhrzeitberechnungen, die Anpassungsregeln einer Zeitzone widerspiegeln.

[Converting between DateTime and DateTimeOffset (Konvertieren zwischen DateTime und DateTimeOffset)](../../../docs/standard/datetime/converting-between-datetime-and-offset.md): Beschreibt die Konvertierung zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Converting times between time zones (Konvertieren von Uhrzeiten zwischen Zeitzonen)](../../../docs/standard/datetime/converting-between-time-zones.md): Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.

[Vorgehensweise: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md) wird beschrieben, wie eine mehrdeutige Zeit aufgelöst wird, durch Zuordnen zur Normalzeit der Zeitzone.

[Vorgehensweise: Können Benutzer auflösen mehrdeutiger Zeiten](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) beschreibt, wie Sie den Benutzern die Zuordnung zwischen einem nicht eindeutigen lokalen Uhrzeit und der koordinierten Weltzeit überlassen.

## <a name="reference"></a>Referenz

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
