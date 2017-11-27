---
title: "Übersicht über Zeitzonen"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], about time zones
- transition time [.NET Framework]
- TimeZoneInfo class, about TimeZoneInfo class
- time zones [.NET Framework], creating
- invalid time [.NET Framework]
- fixed rule [.NET Framework]
- ambiguous time [.NET Framework]
- floating rule [.NET Framework]
- daylight saving time [.NET Framework]
- adjustment rule [.NET Framework]
- time zones [.NET Framework], terminology
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a92a9e92f368b6f2af06c40dc4700e1dec2fcfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="time-zone-overview"></a>Übersicht über Zeitzonen

Die <xref:System.TimeZoneInfo> Klasse vereinfacht die Erstellung von zeitzonenfähigen Anwendungen. Die <xref:System.TimeZone> -Klasse unterstützt, die Arbeit mit der lokalen Zeitzone und Coordinated Universal Time (UTC). Die <xref:System.TimeZoneInfo> Klasse unterstützt die beiden zone1 sowie einen Zeitzone, welche Informationen in der Registrierung vordefiniert ist. Sie können auch <xref:System.TimeZoneInfo> benutzerdefinierten Zeitzonen definieren, die das System keine Informationen über enthält.

## <a name="time-zone-essentials"></a>Zeitzone essentials

Eine Zeitzone ist eine geografische Region, in der die gleiche Zeit verwendet wird. In der Regel, aber nicht immer, besteht zwischen angrenzenden Zeitzonen ein Zeitunterschied von einer Stunde. Die Zeit in allen Zeitzonen weltweit kann als Abweichung von der koordinierten Weltzeit (Coordinated Universal Time, UTC) ausgedrückt werden.

Viele Zeitzonen weltweit unterstützen die Sommerzeit. Bei der Sommerzeit wird versucht, eine größere Anzahl von Stunden mit Tageslicht zu nutzen, indem die Uhrzeit im Frühjahr oder Frühsommer um eine Stunde vorgestellt und im Spätsommer oder Herbst auf Normalzeit (oder Standardzeit) zurückgestellt wird. Diese Änderungen auf und von Standardzeit werden als Anpassungsregeln bezeichnet.

Die Umstellung auf Sommerzeit und zurück auf Standardzeit in einer bestimmten Zeitzone kann entweder durch eine feste oder eine bewegliche Anpassungsregel definiert werden. Bei einer festen Anpassungsregel wird ein bestimmtes Datum festgelegt, an dem die Umstellung auf oder von Sommerzeit jedes Jahr erfolgt. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel. Bewegliche Anpassungsregeln werden jedoch häufiger verwendet. Hierbei wird ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.

Bei Zeitzonen, die Anpassungsregeln unterstützen, führt die Umstellung von und auf Sommerzeit zu zwei anomalen Uhrzeiten: ungültige Uhrzeiten und mehrdeutige Uhrzeiten. Bei einer ungültigen Uhrzeit handelt es sich um eine nicht vorhandene Uhrzeit, die durch die Umstellung von Standardzeit auf Sommerzeit entstanden ist. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig. Eine mehrdeutige Uhrzeit ist eine Zeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie wird durch die Umstellung von Sommerzeit auf Standardzeit erzeugt. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden.

## <a name="time-zone-terminology"></a>Zeitzone-Terminologie

In der folgenden Tabelle sind Begriffe definiert, die bei der Arbeit mit Zeitzonen und bei der Entwicklung von Anwendungen, die Zeitzonen unterstützen, häufig verwendet werden.

| Begriff            | Definition |
| --------------- | ---------- |
| Anpassungsregel | Eine Regel, die definiert, wann die Umstellung von Standardzeit auf Sommerzeit und von Sommerzeit auf Standardzeit stattfindet. Jede Anpassungsregel hat ein Anfangs- und Enddatum Datum, das definiert, wenn die Regel vorhanden ist (z. B. die Anpassungsregel ist vom 1. Januar 1986, bis zum 31. Dezember 2006), eine Delta (die Zeitspanne, um die Normalzeit, die als Ergebnis der Anwendung der th ändert, e Anpassungsregel), und Informationen zu bestimmten Datum und Uhrzeit, die die Übergänge während der Anpassung Zeitraum auftreten. Umstellungen können entweder einer festen oder einer beweglichen Anpassungsregel folgen. |
| Mehrdeutige Zeit  | Eine Uhrzeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden. |
| Feste Regel      | Eine Anpassungsregel, mit der ein bestimmtes Datum für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel. |
| Bewegliche Regel   | Eine Anpassungsregel, bei der ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel. |
| Ungültige Zeit    | Eine nicht vorhandene Zeit, die durch die Umstellung von Standardzeit auf Sommerzeit entsteht. Sie tritt auf, wenn die Uhrzeit vorgestellt wird, beispielsweise bei der Umstellung von Standardzeit in einer Zeitzone auf Sommerzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig. |
| Umstellungszeit | Informationen über einen bestimmten Zeitwechsel in einer Zeitzone, z.B. bei der Umstellung von Sommerzeit auf Standardzeit oder umgekehrt. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Zeitzonen und die TimeZoneInfo-Klasse

In .NET ein <xref:System.TimeZoneInfo> -Objekt stellt eine Zeitzone dar. Die <xref:System.TimeZoneInfo> Klasse enthält eine <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> Methode, die ein Array von zurückgibt <xref:System.TimeZoneInfo.AdjustmentRule> Objekte. Jedes Element dieses Arrays enthält Informationen über den Übergang in und aus der Sommerzeit für einen bestimmten Zeitraum. (Für Zeitzonen, die Sommerzeit nicht unterstützen, die Methode ein leeres Array zurück.) Jede <xref:System.TimeZoneInfo.AdjustmentRule> Objekt verfügt über eine <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> und eine <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> , die bestimmten Datum und Uhrzeit des Übergangs zu und von der Sommerzeit definiert. Die <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> Eigenschaft gibt an, ob dieser Übergang fixed "oder" Gleitkomma ist.

.NET basiert auf Zeitzoneninformationen, die vom Windows-Betriebssystems bereitgestellt und in der Registrierung gespeichert. Aufgrund der Anzahl der Erde werden nicht alle vorhandener Zeitzonen in der Registrierung dargestellt. Darüber hinaus, da die Registrierung einer dynamischen Struktur ist, können vordefinierte Zeitzonen hinzugefügt oder daraus entfernt. Schließlich enthält die Registrierung keine unbedingt vergangene Zeitzonendaten. Unter Windows XP enthält z. B. die Registrierung Daten über nur ein einzelner Satz von zeitzonenanpassungen an. Windows Vista unterstützt dynamische Zeitzonendaten, was bedeutet, dass eine einzelne Zeitzone mehrere Anpassungsregeln aufweisen kann, die für bestimmte Zeitintervalle Jahre gelten. Allerdings müssen die meisten Zeitzonen, die in der Windows Vista-Registrierung und Support Sommerzeit definiert sind nur ein oder zwei vordefinierte Anpassungsregeln.

Die Abhängigkeit von der <xref:System.TimeZoneInfo> Klasse für die Registrierung bedeutet, dass eine Zeitzone-fähige Anwendung nicht davon ausgehen kann, dass eine bestimmte Zeitzone in der Registrierung definiert ist. Daher sollte beim Versuch, eine bestimmte Zeitzone zu instanziieren (außer der lokalen Zeitzone oder der Zeitzone, die UTC darstellt), eine Ausnahmebehandlung verwendet werden. Es muss außerdem eine Methode können Sie die Anwendung, wenn ein erforderliches zu fortfahren enthalten <xref:System.TimeZoneInfo> Objekt kann nicht instanziiert werden, aus der Registrierung.

Das Fehlen einer erforderlichen Zeitzone behandelt die <xref:System.TimeZoneInfo> Klasse enthält eine <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode, die Sie verwenden können, um benutzerdefinierte Zeitzonen zu erstellen, die in der Registrierung nicht gefunden werden. Weitere Informationen zum Erstellen einer benutzerdefinierten Zeitzone finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md). Darüber hinaus können Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode, um eine neu erstellte Zeitzone in eine Zeichenfolge konvertieren und in einem Datenspeicher (z. B. eine Datenbank, eine Textdatei, die Registrierung oder eine Anwendungsressource) zu speichern. Anschließend können Sie die <xref:System.TimeZoneInfo.FromSerializedString%2A> -Methode zum Konvertieren dieser Zeichenfolge zurück, an eine <xref:System.TimeZoneInfo> Objekt. Weitere Informationen finden Sie unter [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) und [Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

Da jede Zeitzone durch eine Basisabweichung von UTC sowie durch eine Abweichung von UTC, mit der eine vorhandene Anpassungsregel wiedergegeben wird, gekennzeichnet ist, kann eine Uhrzeit in einer Zeitzone problemlos in die Uhrzeit in einer anderen Zeitzone konvertiert werden. Zu diesem Zweck die <xref:System.TimeZoneInfo> -Objekt enthält mehrere Konvertierungsmethoden, einschließlich:

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, wodurch UTC in die Zeit in einer angegebenen Zeitzone konvertiert.

* <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, wodurch die Zeit in einer angegebenen Zeitzone in UTC konvertiert.

* <xref:System.TimeZoneInfo.ConvertTime%2A>, wodurch die Zeit in einer angegebenen Zeitzone in die Zeit in einer anderen Zeitzone konvertiert.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, die Zeitzonenbezeichner verwendet (anstelle von <xref:System.TimeZoneInfo> Objekte) als Parameter für die Zeit in einer angegebenen Zeitzone in die Zeit in einer anderen Zeitzone zu konvertieren.

Weitere Informationen über das Konvertieren von Uhrzeiten zwischen Zeitzonen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
