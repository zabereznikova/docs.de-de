---
title: Datumsangaben, Uhrzeiten und Zeitzonen | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
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
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 2445188fda029ddc0f673d4c81f99f7f46edb89b
ms.lasthandoff: 04/08/2017

---
# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen
Zusätzlich zur grundlegenden <xref:System.DateTime>-Struktur bietet [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:  
  
-   <xref:System.TimeZone>  
  
     Verwenden Sie diese Klasse, um die lokale Zeitzone des Systems und die Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC) zu verarbeiten.  Die Funktionalität der <xref:System.TimeZone>-Klasse wird weitgehend von der <xref:System.TimeZoneInfo>-Klasse abgelöst.  
  
-   <xref:System.TimeZoneInfo>  
  
     Verwenden Sie diese Klasse für das Arbeiten mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums- und Zeitangaben zwischen Zeitzonen. Für Neuentwicklungen sollten Sie die <xref:System.TimeZoneInfo>-Klasse anstelle der <xref:System.TimeZone>-Klasse verwenden.  
  
-   <xref:System.DateTimeOffset>  
  
     Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die <xref:System.DateTimeOffset>-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich <xref:System.DateTimeOffset>-Werte einfacher von einem Computer auf einen anderen übertragen als <xref:System.DateTime>-Werte.  
  
 In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)  
 Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.  
  
 [Auswählen zwischen „DateTime“, „DateTimeOffset“, „TimeSpan“ und „TimeZoneInfo“](../../../docs/standard/datetime/choosing-between-datetime.md)  
 Erläutert, in welchen Fällen die Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> und <xref:System.TimeZoneInfo> beim Arbeiten mit Datums- und Uhrzeitdaten verwendet werden sollten.  
  
 [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 Beschreibt, wie die Zeitzonen auf einem lokalen System aufgelistet werden.  
  
 [Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen](../../../docs/standard/datetime/enumerate-time-zones.md)  
 Stellt Beispiele für die Aufzählung der Zeitzonen bereit, die in der Registrierung eines Computers definiert sind und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.  
  
 [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)  
 Beschreibt, wie auf koordinierte Weltzeit und auf die lokale Zeitzone zugegriffen wird.  
  
 [Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 Erläutert, wie ein <xref:System.TimeZoneInfo>-Objekt aus der Registrierung des lokalen Systems instanziiert wird.  
  
 [Instanziieren eines DateTimeOffset-Objekts](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 Beschreibt die Möglichkeiten zur Instanziierung eines <xref:System.DateTimeOffset>-Objekts und die Möglichkeiten zur Konvertierung eines <xref:System.DateTime>-Werts in einen <xref:System.DateTimeOffset>-Wert.  
  
 [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.  
  
 [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die eine oder mehrere Umstellungen von Sommerzeit auf Normalzeit und umgekehrt unterstützt.  
  
 [Speichern und Wiederherstellen von Zeitzonen](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 Beschreibt die Unterstützung von <xref:System.TimeZoneInfo> für die Serialisierung und Deserialisierung von Zeitzonendaten und veranschaulicht einige der Szenarien, in denen diese Features verwendet werden können.  
  
 [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcendatei gespeichert werden.  
  
 [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 Beschreibt, wie in einer eingebetteten Ressourcendatei gespeicherte benutzerdefinierte Zeitzonen instanziiert werden.  
  
 [Durchführen arithmetischer Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen der Werte von <xref:System.DateTime> und <xref:System.DateTimeOffset>.  
  
 [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 Erläutert, wie arithmetische Datums- und Uhrzeitoperationen ausgeführt werden, die die Anpassungsregeln einer Zeitzone widerspiegeln.  
  
 [Konvertieren zwischen DateTime und DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 Beschreibt, wie zwischen <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werten konvertiert wird.  
  
 [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)  
 Beschreibt, wie Uhrzeiten von einer Zeitzone in eine andere konvertiert werden.  
  
 [Gewusst wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 Beschreibt, wie eine mehrdeutige Zeit aufgelöst wird, indem sie der Normalzeit der Zeitzone zugeordnet wird.  
  
 [Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 Beschreibt, wie ein Benutzer die Zuordnung zwischen einer mehrdeutigen Ortszeit und der koordinierten Weltzeit bestimmt.  
  
## <a name="reference"></a>Verweis  
 <xref:System.TimeZoneInfo?displayProperty=fullName>
