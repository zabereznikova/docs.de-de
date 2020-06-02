---
title: Übersicht über Zeitzonen
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 9cb50357931cb22fd2862ba7558154a4782e4557
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281036"
---
# <a name="time-zone-overview"></a>Übersicht über Zeitzonen

Die- <xref:System.TimeZoneInfo> Klasse vereinfacht das Erstellen von Zeit Zonen fähigen Anwendungen. Die <xref:System.TimeZone> -Klasse unterstützt die Arbeit mit der lokalen Zeitzone und der koordinierten Weltzeit (UTC). Die- <xref:System.TimeZoneInfo> Klasse unterstützt beide Zonen sowie eine beliebige Zeitzone, in der die Informationen in der Registrierung vordefiniert sind. Sie können auch verwenden <xref:System.TimeZoneInfo> , um benutzerdefinierte Zeitzonen zu definieren, über die das System keine Informationen verfügt.

## <a name="time-zone-essentials"></a>Grundlagen der Zeitzone

Eine Zeitzone ist eine geografische Region, in der die gleiche Zeit verwendet wird. In der Regel, aber nicht immer, besteht zwischen angrenzenden Zeitzonen ein Zeitunterschied von einer Stunde. Die Zeit in allen Zeitzonen weltweit kann als Abweichung von der koordinierten Weltzeit (Coordinated Universal Time, UTC) ausgedrückt werden.

Viele Zeitzonen weltweit unterstützen die Sommerzeit. Bei der Sommerzeit wird versucht, eine größere Anzahl von Stunden mit Tageslicht zu nutzen, indem die Uhrzeit im Frühjahr oder Frühsommer um eine Stunde vorgestellt und im Spätsommer oder Herbst auf Normalzeit (oder Standardzeit) zurückgestellt wird. Diese Änderungen auf und von Standardzeit werden als Anpassungsregeln bezeichnet.

Die Umstellung auf Sommerzeit und zurück auf Standardzeit in einer bestimmten Zeitzone kann entweder durch eine feste oder eine bewegliche Anpassungsregel definiert werden. Bei einer festen Anpassungsregel wird ein bestimmtes Datum festgelegt, an dem die Umstellung auf oder von Sommerzeit jedes Jahr erfolgt. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel. Bewegliche Anpassungsregeln werden jedoch häufiger verwendet. Hierbei wird ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.

Bei Zeitzonen, die Anpassungsregeln unterstützen, führt die Umstellung von und auf Sommerzeit zu zwei anomalen Uhrzeiten: ungültige Uhrzeiten und mehrdeutige Uhrzeiten. Bei einer ungültigen Uhrzeit handelt es sich um eine nicht vorhandene Uhrzeit, die durch die Umstellung von Standardzeit auf Sommerzeit entstanden ist. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig. Eine mehrdeutige Uhrzeit ist eine Zeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie wird durch die Umstellung von Sommerzeit auf Standardzeit erzeugt. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden.

## <a name="time-zone-terminology"></a>Zeit Zonen Terminologie

In der folgenden Tabelle sind Begriffe definiert, die bei der Arbeit mit Zeitzonen und bei der Entwicklung von Anwendungen, die Zeitzonen unterstützen, häufig verwendet werden.

| Begriff            | Definition |
| --------------- | ---------- |
| Anpassungsregel | Eine Regel, die definiert, wann die Umstellung von Standardzeit auf Sommerzeit und von Sommerzeit auf Standardzeit stattfindet. Jede Anpassungs Regel verfügt über ein Start-und Enddatum, das definiert, wann die Regel vorhanden ist (z. b. die Anpassungs Regel gilt ab dem 1. Januar 1986 bis zum 31. Dezember 2006), einem Delta (der Zeitraum, in dem sich die Standardzeit infolge der Anwendung der Anpassungs Regel ändert) sowie Informationen zum bestimmten Zeitpunkt (Datum und Uhrzeit), zu dem die Übergänge während des Anpassungszeitraums stattfinden. Umstellungen können entweder einer festen oder einer beweglichen Anpassungsregel folgen. |
| Mehrdeutige Zeitangaben  | Eine Uhrzeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden. |
| Feste Regel      | Eine Anpassungsregel, mit der ein bestimmtes Datum für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel. |
| Bewegliche Regel   | Eine Anpassungsregel, bei der ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel. |
| Ungültige Zeit    | Eine nicht vorhandene Zeit, die durch die Umstellung von Standardzeit auf Sommerzeit entsteht. Sie tritt auf, wenn die Uhrzeit vorgestellt wird, beispielsweise bei der Umstellung von Standardzeit in einer Zeitzone auf Sommerzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig. |
| Umstellungszeit | Informationen über einen bestimmten Zeitwechsel in einer Zeitzone, z.B. bei der Umstellung von Sommerzeit auf Standardzeit oder umgekehrt. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Zeitzonen und die timezoninfo-Klasse

In .NET stellt ein- <xref:System.TimeZoneInfo> Objekt eine Zeitzone dar. Die- <xref:System.TimeZoneInfo> Klasse enthält eine- <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> Methode, die ein Array von-Objekten zurückgibt <xref:System.TimeZoneInfo.AdjustmentRule> . Jedes Element dieses Arrays stellt Informationen über den Übergang zur und von der Sommerzeit eines bestimmten Zeitraums bereit. (Bei Zeitzonen, die Sommerzeit nicht unterstützen, gibt die Methode ein leeres Array zurück.) Jedes <xref:System.TimeZoneInfo.AdjustmentRule> -Objekt verfügt über eine <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> -Eigenschaft und eine- <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> Eigenschaft, die das jeweilige Datum und die Uhrzeit des Übergangs zu und von der Sommerzeit definiert. Die- <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> Eigenschaft gibt an, ob dieser Übergang fest oder unverankert ist.

.NET basiert auf Zeitzoneninformationen, die vom Windows-Betriebssystem bereitgestellt und in der Registrierung gespeichert werden. Aufgrund der Anzahl der Zeitzonen der Erde werden nicht alle vorhandenen Zeitzonen in der Registrierung dargestellt. Da die Registrierung eine dynamische Struktur ist, können außerdem vordefinierte Zeitzonen hinzugefügt oder daraus entfernt werden. Zum Schluss enthält die Registrierung nicht unbedingt historische Zeit Zonendaten. In Windows XP enthält die Registrierung z. b. Daten zu nur einem einzelnen Satz von Zeit Zonen Anpassungen. Windows Vista unterstützt dynamische Zeit Zonendaten. Dies bedeutet, dass eine einzelne Zeitzone über mehrere Anpassungsregeln verfügen kann, die auf bestimmte Zeiträume von Jahren zutreffen. Die meisten Zeitzonen, die in der Windows Vista-Registrierung definiert sind und die Sommerzeit unterstützen, verfügen jedoch nur über eine oder zwei vordefinierte Anpassungsregeln.

Die Abhängigkeit der- <xref:System.TimeZoneInfo> Klasse in der Registrierung bedeutet, dass eine Zeit Zonen fähige Anwendung nicht sicher sein kann, dass eine bestimmte Zeitzone in der Registrierung definiert ist. Daher sollte beim Versuch, eine bestimmte Zeitzone zu instanziieren (außer der lokalen Zeitzone oder der Zeitzone, die UTC darstellt), eine Ausnahmebehandlung verwendet werden. Außerdem sollte Sie eine Methode bereitstellen, mit der die Anwendung fortgesetzt werden kann, wenn ein erforderliches <xref:System.TimeZoneInfo> Objekt nicht aus der Registrierung instanziiert werden kann.

Um das Fehlen einer erforderlichen Zeitzone zu behandeln, enthält die- <xref:System.TimeZoneInfo> Klasse eine- <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, die Sie verwenden können, um benutzerdefinierte Zeitzonen zu erstellen, die nicht in der Registrierung gefunden werden. Ausführliche Informationen zum Erstellen einer benutzerdefinierten Zeitzone finden Sie unter Gewusst [wie: Erstellen von Zeitzonen ohne Anpassungsregeln](create-time-zones-without-adjustment-rules.md) und Gewusst [wie: Erstellen von Zeitzonen mit Anpassungsregeln](create-time-zones-with-adjustment-rules.md). Darüber hinaus können Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A> -Methode verwenden, um eine neu erstellte Zeitzone in eine Zeichenfolge zu konvertieren und in einem Datenspeicher (z. b. einer-Datenbank, einer Textdatei, der Registrierung oder einer Anwendungs Ressource) zu speichern. Sie können dann die- <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode verwenden, um diese Zeichenfolge zurück in ein-Objekt zu konvertieren <xref:System.TimeZoneInfo> . Weitere Informationen finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md) und Gewusst [wie: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](restore-time-zones-from-an-embedded-resource.md).

Da jede Zeitzone durch eine Basisabweichung von UTC sowie durch eine Abweichung von UTC, mit der eine vorhandene Anpassungsregel wiedergegeben wird, gekennzeichnet ist, kann eine Uhrzeit in einer Zeitzone problemlos in die Uhrzeit in einer anderen Zeitzone konvertiert werden. Zu diesem Zweck enthält das- <xref:System.TimeZoneInfo> Objekt mehrere Konvertierungs Methoden, einschließlich:

- <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, die UTC in die Uhrzeit in einer bestimmten Zeitzone konvertiert.

- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, die die Uhrzeit in einer bestimmten Zeitzone in UTC konvertiert.

- <xref:System.TimeZoneInfo.ConvertTime%2A>, die die Uhrzeit in einer bestimmten Zeitzone in die Uhrzeit in einer anderen vorgesehenen Zeitzone konvertiert.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, der Zeit Zonen Bezeichner (anstelle von- <xref:System.TimeZoneInfo> Objekten) als Parameter verwendet, um die Zeit in einer bestimmten Zeitzone in die Uhrzeit in einer anderen festgelegten Zeitzone zu konvertieren.

Weitere Informationen über das Konvertieren von Uhrzeiten zwischen Zeitzonen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
