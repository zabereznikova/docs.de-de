---
title: "Datumsangaben, Uhrzeiten und Zeitzonen | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datums- und Uhrzeitdaten [.NET Framework]"
  - "Zeit [.NET Framework], Zeitzonen"
  - "Zeitzonenobjekte [.NET Framework]"
  - "Zeitzonen [.NET Framework]"
  - "Zeiten [.NET Framework], Zeitzonen"
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Datumsangaben, Uhrzeiten und Zeitzonen
Neben der grundlegenden <xref:System.DateTime>\-Struktur bietet [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] die folgenden Klassen, die die Verwendung von Zeitzonen unterstützen:  
  
-   <xref:System.TimeZone>  
  
     Verwenden Sie diese Klasse für die Arbeit mit der lokalen Zeitzone des Systems und der koordinierten Weltzeitzone \(Coordinated Universal Time, UTC\).  Die Funktionalität der <xref:System.TimeZone>\-Klasse wird durch die umfangreichen Funktionen der <xref:System.TimeZoneInfo>\-Klasse ersetzt.  
  
-   <xref:System.TimeZoneInfo>  
  
     Verwenden Sie diese Klasse für die Arbeit mit allen in einem System vordefinierten Zeitzonen, zum Erstellen neuer Zeitzonen und zum problemlosen Konvertieren von Datums\- und Zeitangaben zwischen Zeitzonen.  Für Neuentwicklungen sollten Sie die <xref:System.TimeZoneInfo>\-Klasse anstelle der <xref:System.TimeZone>\-Klasse verwenden.  
  
-   <xref:System.DateTimeOffset>  
  
     Verwenden Sie diese Struktur, um mit Datums\- und Zeitangaben zu arbeiten, deren Offset \(bzw. Abweichung\) von UTC bekannt ist.  Die <xref:System.DateTimeOffset>\-Struktur kombiniert einen Datums\- und Uhrzeitwert mit dem Offset dieses Zeitpunkts von UTC.  Aufgrund des Bezugs zu UTC wird durch einen beliebigen Datums\- und Uhrzeitwert ein bestimmter Zeitpunkt eindeutig identifiziert.  Dadurch kann ein <xref:System.DateTimeOffset>\-Wert besser von einem Computer auf den anderen portiert werden als ein <xref:System.DateTime>\-Wert.  
  
 Dieser Abschnitt der Dokumentation enthält Informationen, die für die Arbeit mit Zeitzonen und zum Erstellen von Anwendungen erforderlich sind, die Zeitzonen unterstützen und mit denen Datums\- und Uhrzeitangaben von einer Zeitzone in eine andere konvertiert werden können.  
  
## In diesem Abschnitt  
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)  
 Erläutert die Terminologie, Begriffe und Probleme, die bei der Erstellung zeitzonenfähiger Anwendungen vorkommen können.  
  
 [Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo"](../../../docs/standard/datetime/choosing-between-datetime.md)  
 Erläutert, in welchen Fällen die Typen <xref:System.DateTime>, <xref:System.DateTimeOffset> oder <xref:System.TimeZoneInfo> bei der Arbeit mit Datums\- und Uhrzeitdaten verwendet werden sollten.  
  
 [Suchen der auf einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 Beschreibt, wie die Zeitzonen auf einem lokalen System aufgelistet werden.  
  
 [Gewusst wie: Auflisten der auf einem Computer vorhandenen Zeitzonen](../../../docs/standard/datetime/enumerate-time-zones.md)  
 Enthält Beispiele, mit denen die in der Registrierung eines Computers definierten Zeitzonen aufgelistet werden bzw. Anwender eine vordefinierte Zeitzone aus einer Liste auswählen können.  
  
 [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md)  
 Beschreibt, wie auf koordinierte Weltzeit und auf die lokale Zeitzone zugegriffen wird.  
  
 [Gewusst wie: Instanziieren eines TimeZoneInfo\-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 Erläutert, wie ein <xref:System.TimeZoneInfo>\-Objekt aus der Registrierung des lokalen Systems instanziiert wird.  
  
 [Instanziieren eines "DateTimeOffset"\-Objekts](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 Beschreibt, auf welche Weise ein <xref:System.DateTimeOffset>\-Objekt instanziiert und ein <xref:System.DateTime>\-Wert in einen <xref:System.DateTimeOffset>\-Wert konvertiert werden kann.  
  
 [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die die Umstellung von Sommerzeit auf Normalzeit und umgekehrt nicht unterstützt.  
  
 [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt wird, die eine oder mehrere Umstellungen von Sommerzeit auf Normalzeit und umgekehrt unterstützt.  
  
 [Speichern und Wiederherstellen von Zeitzonen](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 Beschreibt die <xref:System.TimeZoneInfo>\-Unterstützung der Serialisierung und Deserialisierung von Zeitzonendaten, und beschreibt einige Szenarien, in denen diese Funktionen verwendet werden können.  
  
 [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 Beschreibt, wie eine benutzerdefinierte Zeitzone erstellt und die zugehörigen Informationen in einer Ressourcendatei gespeichert werden.  
  
 [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 Beschreibt, wie in einer eingebetteten Ressourcendatei gespeicherte benutzerdefinierte Zeitzonen instanziiert werden.  
  
 [Durchführen arithmetischer Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 Erörtert Aspekte im Zusammenhang mit dem Hinzufügen, Subtrahieren und Vergleichen von <xref:System.DateTime>\-Werten und <xref:System.DateTimeOffset>\-Werten.  
  
 [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 Erläutert, wie arithmetische Datums\- und Uhrzeitoperationen ausgeführt werden, die die Anpassungsregeln einer Zeitzone widerspiegeln.  
  
 [Konvertieren zwischen "DateTime" und "DateTimeOffset"](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 Beschreibt, wie zwischen <xref:System.DateTime>\-Werten und <xref:System.DateTimeOffset>\-Werten konvertiert wird.  
  
 [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md)  
 Beschreibt, wie Uhrzeiten von einer Zeitzone in eine andere konvertiert werden.  
  
 [Gewusst wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 Beschreibt, wie eine mehrdeutige Zeit aufgelöst wird, indem sie der Normalzeit der Zeitzone zugeordnet wird.  
  
 [Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 Beschreibt, wie ein Benutzer die Zuordnung zwischen einer mehrdeutigen Ortszeit und der koordinierten Weltzeit bestimmt.  
  
## Referenz  
 <xref:System.TimeZoneInfo?displayProperty=fullName>