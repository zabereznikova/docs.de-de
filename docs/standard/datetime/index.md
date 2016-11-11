---
title: Datumsangaben, Uhrzeiten und Zeitzonen
description: Datumsangaben, Uhrzeiten und Zeitzonen
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 76e6cacc-1c0c-4a71-8cb8-018c112385ba
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: a4d0a68ac32c3d722a1479ca2b067892fd88bf52

---

# <a name="dates-times-and-time-zones"></a>Datumsangaben, Uhrzeiten und Zeitzonen

Zusätzlich zur grundlegenden [System.DateTime](xref:System.DateTime)-Struktur bietet .NET die folgenden Klassen, die den Umgang mit Zeitzonen unterstützen:

* [System.TimeZoneInfo](xref:System.TimeZoneInfo)
    
  Verwenden Sie diese Klasse, um die lokale Zeitzone des Systems und die Zeitzone der koordinierten Weltzeit (Coordinated Universal Time, UTC) zu verarbeiten.
  
* [System.DateTimeOffset](xref:System.DateTimeOffset)  

  Verwenden Sie diese Struktur, um Datumsangaben und Uhrzeiten zu verarbeiten, deren Abweichung von der UTC bekannt ist. Die [DateTimeOffset](xref:System.DateTimeOffset)]-Struktur kombiniert einen Datums- und Uhrzeitwert mit der Abweichung dieser Uhrzeit von der UTC. Aufgrund der Beziehung zur UTC kann ein einzelner Datums- und Uhrzeitwert einen bestimmten Zeitpunkt eindeutig identifizieren. Daher lassen sich [DateTimeOffset](xref:System.DateTimeOffset)]-Werte einfacher von einem Computer auf einen anderen übertragen als [DateTime](xref:System.DateTime)]-Werte. 
  
In diesem Abschnitt der Dokumentation erhalten Sie die Informationen, die Sie benötigen, um mit Zeitzonen zu arbeiten und zeitzonenkompatible Anwendungen zu erstellen, die Datumsangaben und Uhrzeiten zwischen verschiedenen Zeitzonen konvertieren können.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über Zeitzonen](time-zone-overview.md): Beschreibt Terminologie, Konzepte und Probleme im Zusammenhang mit der Erstellung zeitzonenkompatibler Anwendungen.
    
[Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md): Beschreibt die Verwendung der Typen [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset) und [System.TimeZoneInfo](xref:System.TimeZoneInfo) beim Arbeiten mit Datums- und Uhrzeitdaten.
    
[Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md): Beschreibt die Aufzählung der in einem lokalen System gefundenen Zeitzonen.

[Instanziieren eines DateTimeOffset-Objekts](instantiating-a-datetimeoffset-object.md): Beschreibt die Möglichkeiten zur Instanziierung eines [System.DateTimeOffset](xref:System.DateTimeOffset)-Objekts und die Möglichkeiten zur Konvertierung eines [System.DateTime](xref:System.DateTime)-Werts in einen [System.DateTimeOffset](xref:System.DateTimeOffset)-Wert.

[Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md): Beschreibt die Probleme im Zusammenhang mit dem Addieren, Subtrahieren und Vergleichen von [System.DateTime](xref:System.DateTime)- und [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten.

[Konvertieren zwischen DateTime und DateTimeOffset](converting-between-datetime-and-offset.md): Beschreibt die Konvertierung zwischen [System.DateTime](xref:System.DateTime)- und [System.DateTimeOffset](xref:System.DateTimeOffset)-Werten.

[Konvertieren von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md): Beschreibt die Konvertierung von Uhrzeiten von einer Zeitzone in eine andere.

[Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md): Stellt Beispiele für die Aufzählung der Zeitzonen bereit, die in der Registrierung eines Computers definiert sind und dem Benutzer die Auswahl einer vordefinierten Zeitzone aus einer Liste ermöglichen.

[Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](access-utc-and-local.md): Beschreibt den Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.

[Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md): Beschreibt die Instanziierung eines [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts über die Registrierung des lokalen Systems.

[Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](use-time-zones-in-arithmetic.md): Beschreibt die Durchführung von arithmetischen Vorgängen für Datum und Uhrzeit, die die Anpassungsregeln einer Zeitzone widerspiegeln.

[Gewusst wie: Auflösen von mehrdeutigen Zeiten](resolve-ambiguous-times.md): Beschreibt die Auflösung einer nicht eindeutigen Uhrzeit durch Zuordnen der Uhrzeit zur Standarduhrzeit der Zeitzone.

[Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](let-users-resolve-ambiguous-times.md): Beschreibt, wie Sie den Benutzern die Zuordnung zwischen einer nicht eindeutigen lokalen Uhrzeit und der koordinierten Weltzeit überlassen.

## <a name="reference"></a>Verweis

[System.TimeZoneInfo](xref:System.TimeZoneInfo)

[System.DateTimeOffset](xref:System.DateTimeOffset)

[System.DateTime](xref:System.DateTime)



<!--HONumber=Nov16_HO1-->


