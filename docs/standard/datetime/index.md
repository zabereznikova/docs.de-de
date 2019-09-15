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
ms.openlocfilehash: 03a5594b689a52b641ecece0f9a92fb6cdfe5735
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991283"
---
# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen

Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:

* <xref:System.TimeZone>

  Verwenden Sie diese Klasse, um die lokale Zeitzone des Systems und die Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC) zu verarbeiten. Die Funktionalität <xref:System.TimeZone> der-Klasse wird größtenteils durch die <xref:System.TimeZoneInfo> -Klasse ersetzt.

* <xref:System.TimeZoneInfo>

  Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen. Verwenden Sie für neue Entwicklungen die <xref:System.TimeZoneInfo>-Klasse statt der <xref:System.TimeZone>-Klasse.

* <xref:System.DateTimeOffset>

  Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.

In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md): Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.

[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo (Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo)](../../../docs/standard/datetime/choosing-between-datetime.md): Beschreibt die Verwendung der Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> beim Arbeiten mit Datums- und Uhrzeitdaten.

[Finding the time zones defined on a local system (Suchen der in einem lokalen System definierten Zeitzonen)](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md): Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.

[Vorgehensweise: Auflisten der auf einem Computer](../../../docs/standard/datetime/enumerate-time-zones.md) vorhandenen Zeitzonen enthält Beispiele zum Auflisten der Zeitzonen, die in der Registrierung eines Computers definiert sind und die es Benutzern ermöglichen, eine vordefinierte Zeitzone aus einer Liste auszuwählen.

[Vorgehensweise: Der Zugriff auf die vordefinierte UTC und lokale](../../../docs/standard/datetime/access-utc-and-local.md) Zeit Zonen Objekte beschreibt den Zugriff auf die koordinierte Weltzeit und die lokale Zeitzone.

[Vorgehensweise: Instanziieren Sie ein TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md) -Objekt, das beschreibt, wie <xref:System.TimeZoneInfo> ein-Objekt aus der Registrierung des lokalen Systems instanziiert wird.

[Instantiating a DateTimeOffset object (Instanziieren eines DateTimeOffset-Objekts)](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md): Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.

[Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) : Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die den Übergang zu und von der Sommerzeit nicht unterstützt.

[Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) : Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die einen oder mehrere Übergänge in und von der Sommerzeit unterstützt.

[Saving and restoring time zones (Speichern und Wiederherstellen von Zeitzonen)](../../../docs/standard/datetime/saving-and-restoring-time-zones.md): Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarios, in denen diese Features verwendet werden können.

[Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) : Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcen Datei gespeichert werden.

[Vorgehensweise: Durch das Wiederherstellen von Zeitzonen aus](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) einer eingebetteten Ressource wird beschrieben, wie benutzerdefinierte Zeitzonen instanziiert werden, die in einer eingebetteten Ressourcen Datei gespeichert wurden.

[Performing arithmetic operations with dates and times (Durchführen arithmetischer Datums- und Uhrzeitoperationen)](../../../docs/standard/datetime/performing-arithmetic-operations.md): Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums-](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) und Uhrzeit Berechnungen erläutert, wie Datums-und Uhrzeit Berechnungen durchgeführt werden, die die Anpassungsregeln einer Zeitzone widerspiegeln.

[Converting between DateTime and DateTimeOffset (Konvertieren zwischen DateTime und DateTimeOffset)](../../../docs/standard/datetime/converting-between-datetime-and-offset.md): Beschreibt die Konvertierung zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten.

[Converting times between time zones (Konvertieren von Uhrzeiten zwischen Zeitzonen)](../../../docs/standard/datetime/converting-between-time-zones.md): Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.

[Vorgehensweise: Auflösen mehrdeutiger](../../../docs/standard/datetime/resolve-ambiguous-times.md) Zeiten: Beschreibt, wie eine mehrdeutige Zeit aufgelöst werden kann, indem Sie der Standardzeit der Zeitzone entspricht.

[Vorgehensweise: Gestatten Sie Benutzern das Auflösen](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) mehrdeutiger Zeiten. hier wird beschrieben, wie ein Benutzer die Zuordnung zwischen einer mehrdeutigen Ortszeit und koordinierter Weltzeit bestimmen kann.

## <a name="reference"></a>Referenz

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
