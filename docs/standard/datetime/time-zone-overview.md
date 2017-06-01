---
title: "&#220;bersicht &#252;ber Zeitzonen | Microsoft Docs"
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
  - "Anpassungsregel [.NET Framework]"
  - "Mehrdeutige Zeit [.NET Framework]"
  - "Sommerzeit [.NET Framework]"
  - "Feste Anpassungsregel [.NET Framework]"
  - "Bewegliche Anpassungsregel [.NET Framework]"
  - "Ungültige Zeit [.NET Framework]"
  - "Zeitzonen [.NET Framework], Informationen über Zeitzonen"
  - "Zeitzonen [.NET Framework], Erstellen"
  - "Zeitzonen [.NET Framework], Terminologie"
  - "TimeZoneInfo-Klasse, Informationen über die TimeZoneInfo-Klasse"
  - "Umstellungszeit [.NET Framework]"
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber Zeitzonen
Die <xref:System.TimeZoneInfo>\-Klasse vereinfacht die Erstellung von Anwendungen, die Zeitzonen unterstützen.  Die <xref:System.TimeZone>\-Klasse ermöglicht die Arbeit mit der lokalen Zeitzone und der koordinierter Weltzeit \(Coordinated Universal Time, UTC\).  Die <xref:System.TimeZoneInfo>\-Klasse unterstützt diese beiden Zonen sowie alle anderen Zeitzonen, für die Daten in der Registrierung vordefiniert sind.  Sie können auch <xref:System.TimeZoneInfo> zum Festlegen benutzerdefinierter Zeitzonen verwenden, für die im System noch keine Daten gespeichert sind.  
  
## Grundlagen zu Zeitzonen  
 Eine Zeitzone ist ein geografisches Gebiet, in dem eine einheitliche Zeit verwendet wird.  In der Regel, jedoch nicht immer, besteht zwischen angrenzenden Zeitzonen ein Zeitunterschied von einer Stunde.  Die Zeit einer beliebigen Zeitzone der Welt kann als Offset von der koordinierten Weltzeit \(UTC\) ausgedrückt werden.  
  
 Viele der Weltzeitzonen unterstützen Sommerzeit.  Durch die Sommerzeit wird die größere Anzahl von Stunden mit Tageslicht besser ausgenutzt, indem die Uhrzeit im Frühjahr oder Frühsommer um eine Stunde vorgestellt und im Spätsommer oder Herbst wieder auf die Normalzeit zurückgestellt wird.  Diese Zeitumstellung von und zurück zur Normalzeit wird als Anpassungsregeln bezeichnet.  
  
 Die Umstellung auf Sommerzeit und zurück auf Normalzeit in einer bestimmten Zeitzone kann entweder durch eine feste oder eine bewegliche Anpassungsregel definiert werden.  Bei einer festen Anpassungsregel wird ein bestimmtes Datum festgelegt, an dem die Umstellung auf oder von Sommerzeit jedes Jahr erfolgt.  So folgt zum Beispiel eine Umstellung von Sommerzeit auf Normalzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel.  Bewegliche Anpassungsregeln werden jedoch häufiger verwendet; hierbei wird ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt.  So folgt zum Beispiel eine Umstellung von Normalzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.  
  
 Bei Zeitzonen, die Anpassungsregeln unterstützen, führt die Umstellung von und auf Sommerzeit zu zwei abweichenden Uhrzeiten: ungültige Uhrzeiten und mehrdeutige Uhrzeiten.  Bei einer ungültigen Uhrzeit handelt es sich um eine nicht vorhandene Uhrzeit, die durch die Umstellung von Normalzeit auf Sommerzeit entstanden ist.  Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit, verursacht in 3:00 Uhr, jedes Zeitintervall zwischen 2:00 und 2:59 Uhr zu ändern: 99 Uhr ungültig.  Eine mehrdeutige Uhrzeit ist eine Zeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann.  Sie wird durch die Umstellung von Sommerzeit auf Standardzeit erzeugt.  Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit, verursacht in 1:00 Uhr, jedes Zeitintervall zwischen 1:00 und 1:59 Uhr zu ändern: 99 Uhr kann als Normalzeit oder als Sommerzeit interpretiert werden.  
  
## Zeitzonenterminologie  
 In der folgenden Tabelle sind Begriffe definiert, die bei der Arbeit mit Zeitzonen und bei der Entwicklung von Anwendungen, die Zeitzonen unterstützen, häufig verwendet werden.  
  
|Begriff|Definition|  
|-------------|----------------|  
|Anpassungsregel|Eine Regel, die definiert, wann die Umstellung von Normalzeit auf Sommerzeit und von Sommerzeit auf Normalzeit stattfindet.  Jede Anpassungsregel verfügt über ein Anfangs\- und ein Enddatum, die definieren, wann die Regel gültig ist \(z. B. vom 1. Januar 1986 bis zum 31. Dezember 2006\), ein Delta \(die Zeit, um die sich die Normalzeit durch Anwendung der Anpassungsregel ändert\) sowie Informationen über das Datum und die Uhrzeit, zu denen die Umstellungen während der Anwendung der Anpassungsregel stattfinden.  Umstellungen können entweder einer festen oder einer beweglichen Anpassungsregel folgen.|  
|Mehrdeutige Zeit|Eine Uhrzeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann.  Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise bei der Umstellung von der Sommerzeit in einer Zeitzone auf die Standardzeit.  Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit, verursacht in 1:00 Uhr, jedes Zeitintervall zwischen 1:00 und 1:59 Uhr zu ändern: 99 Uhr kann als Normalzeit oder als Sommerzeit interpretiert werden.|  
|Feste Anpassungsregel|Eine Anpassungsregel, mit der ein bestimmtes Datum für die Umstellung auf oder von Sommerzeit festgelegt wird.  So folgt zum Beispiel eine Umstellung von Sommerzeit auf Normalzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel.|  
|Bewegliche Anpassungsregel|Eine Anpassungsregel, bei der ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt wird.  So folgt zum Beispiel eine Umstellung von Normalzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.|  
|Ungültige Zeit|Eine nicht vorhandene Zeit, die durch die Umstellung von Normalzeit auf Sommerzeit entsteht.  Sie tritt auf, wenn die Uhrzeit vorgestellt wird, beispielsweise bei der Umstellung von der Normalzeit einer Zeitzone auf die Sommerzeit.  Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit, verursacht in 3:00 Uhr, jedes Zeitintervall zwischen 2:00 und 2:59 Uhr zu ändern: 99 Uhr ungültig.|  
|Umstellungszeit|Informationen über einem bestimmten Zeitwechsel in einer Zeitzone, z. B. bei der Umstellung von Sommerzeit auf Normalzeit oder umgekehrt.|  
  
## Zeitzonen und die TimeZoneInfo\-Klasse  
 In .NET Framework stellt ein <xref:System.TimeZoneInfo>\-Objekt eine Zeitzone dar.  Die <xref:System.TimeZoneInfo>\-Klasse schließt eine <xref:System.TimeZoneInfo.GetAdjustmentRules%2A>\-Methode ein, die ein Array von <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekten zurückgibt.  Jedes Element dieses Arrays stellt Informationen über die Umstellung auf und von Sommerzeit für einen bestimmten Zeitraum zur Verfügung. \(Für Zeitzonen, die keine Sommerzeit unterstützen, gibt die Methode ein leeres Array zurück.\) Jedes <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekt verfügt über eine <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A>\-Eigenschaft und eine <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A>\-Eigenschaft, mit der ein bestimmtes Datum und eine Uhrzeit für die Umstellung auf und von Sommerzeit definiert werden.  Die <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A>\-Eigenschaft gibt an, ob diese Umstellung fest oder beweglich ist.  
  
 .NET Framework benötigt Zeitzonendaten, die vom Windows\-Betriebssystem zur Verfügung gestellt und in der Registrierung gespeichert werden.  Aufgrund der großen Anzahl von Zeitzonen in der Welt sind nicht alle Zeitzonen in der Registrierung gespeichert.  Außerdem können der Registrierung, da es sich hierbei um eine dynamische Struktur handelt, vordefinierte Zeitzonen hinzugefügt oder Zeitzonen daraus gelöscht werden.  Die Registrierung enthält darüber hinaus nicht unbedingt historische Zeitzonendaten.  In Windows XP enthält die Registrierung zum Beispiel nur Daten über einen einzelnen Satz von Zeitzonenanpassungen.  Windows Vista unterstützt dynamische Zeitzonendaten; dies bedeutet, dass eine einzelne Zeitzone über mehrere Anpassungsregeln verfügen kann, die sich auf bestimmte Jahresintervalle beziehen.  Die meisten Zeitzonen, die in der Registrierung von Windows Vista definiert sind und Sommerzeit unterstützen, verfügen jedoch nur über eine oder zwei vordefinierte Anpassungsregeln.  
  
 Da die <xref:System.TimeZoneInfo>\-Klasse von der Registrierung abhängig ist, kann eine Anwendung, die Zeitzonen unterstützt, nicht davon ausgehen, dass eine bestimmte Zeitzone in der Registrierung definiert ist.  Daher muss beim Versuch, eine bestimmte Zeitzone \(außer der lokalen Zeitzone oder der Zeitzone, die UTC darstellt\) zu instanziieren, eine Ausnahmebehandlung verwendet werden.  Außerdem sollte eine Methode zur Verfügung stehen, die der Anwendung das Fortfahren ermöglicht, wenn ein erforderliches <xref:System.TimeZoneInfo>\-Objekt nicht aus der Registrierung instanziiert werden kann.  
  
 Um das Fehlen einer erforderlichen Zeitzone zu behandeln, umfasst die <xref:System.TimeZoneInfo>\-Klasse eine <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode, die Sie zum Erstellen von benutzerdefinierten, nicht in der Registrierung vorhandenen Zeitzonen verwenden können.  Ausführliche Informationen über das Erstellen einer benutzerdefinierten Zeitzone finden Sie unter [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und unter [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Darüber hinaus können Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A>\-Methode verwenden, um eine neu erstellte Zeitzone in eine Zeichenfolge zu konvertieren und in einem Datenspeicher \(z. B. eine Datenbank, eine Textdatei, die Registrierung oder eine Anwendungsressource\) zu speichern.  Sie können dann die <xref:System.TimeZoneInfo.FromSerializedString%2A>\-Methode verwenden, um diese Zeichenfolge zurück in ein <xref:System.TimeZoneInfo>\-Objekt zu konvertieren.  Ausführliche Informationen finden Sie unter [Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und unter [Gewusst wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
 Da jede Zeitzone durch einen Basisoffset von UTC sowie durch einen UTC\-Offset, der möglicherweise vorhandene Anpassungsregeln in Betracht zieht, gekennzeichnet ist, kann eine Uhrzeit in einer Zeitzone auf einfache Weise in die Uhrzeit einer anderen Zeitzone konvertiert werden.  Für diesen Zweck schließt das <xref:System.TimeZoneInfo>\-Objekt mehrere Konvertierungsmethoden ein, einschließlich:  
  
-   <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, mit der UTC in die Uhrzeit in einer festgelegten Zeitzone konvertiert wird.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, mit der die Uhrzeit in einer festgelegten Zeitzone in UTC konvertiert wird.  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>, mit der die Uhrzeit einer festgelegten Zeitzone in die Uhrzeit einer anderen festgelegten Zeitzone konvertiert wird.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, die Zeitzonenbezeichner \(statt <xref:System.TimeZoneInfo>\-Objekte\) als Parameter zum Konvertieren der Uhrzeit einer festgelegten Zeitzone in die Uhrzeit einer anderen festgelegten Zeitzone verwendet.  
  
 Ausführliche Informationen über das Konvertieren von Uhrzeiten zwischen Zeitzonen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)