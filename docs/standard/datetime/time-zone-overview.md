---
title: "Übersicht über Zeitzonen"
description: "Übersicht über Zeitzonen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e3a10f62-d403-4441-8621-adc964e32c07
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 67d77b80c2517da1c553094689eaf08c0c29078b

---

# <a name="time-zone-overview"></a>Übersicht über Zeitzonen

Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse vereinfacht das Erstellen von zeitzonenfähigen Anwendungen. Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse ermöglicht die Arbeit mit der lokalen Zeitzone und der koordinierten Weltzeit (Coordinated Universal Time, UTC) sowie beliebigen Zeitzonen, zu denen Informationen in der Registrierung vordefiniert sind. Sie können auch [TimeZoneInfo](xref:System.TimeZoneInfo) verwenden, um benutzerdefinierte Zeitzonen zu definieren, zu denen im System keine Daten gespeichert sind.

## <a name="time-zone-essentials"></a>Grundlagen zu Zeitzonen

Eine Zeitzone ist eine geografische Region, in der die gleiche Zeit verwendet wird. In der Regel, aber nicht immer, besteht zwischen angrenzenden Zeitzonen ein Zeitunterschied von einer Stunde. Die Zeit in allen Zeitzonen weltweit kann als Abweichung von der koordinierten Weltzeit (Coordinated Universal Time, UTC) ausgedrückt werden.

Viele Zeitzonen weltweit unterstützen die Sommerzeit. Bei der Sommerzeit wird versucht, eine größere Anzahl von Stunden mit Tageslicht zu nutzen, indem die Uhrzeit im Frühjahr oder Frühsommer um eine Stunde vorgestellt und im Spätsommer oder Herbst auf Normalzeit (oder Standardzeit) zurückgestellt wird. Diese Änderungen auf und von Standardzeit werden als Anpassungsregeln bezeichnet.

Die Umstellung auf Sommerzeit und zurück auf Standardzeit in einer bestimmten Zeitzone kann entweder durch eine feste oder eine bewegliche Anpassungsregel definiert werden. Bei einer festen Anpassungsregel wird ein bestimmtes Datum festgelegt, an dem die Umstellung auf oder von Sommerzeit jedes Jahr erfolgt. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel. Bewegliche Anpassungsregeln werden jedoch häufiger verwendet. Hierbei wird ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.

Bei Zeitzonen, die Anpassungsregeln unterstützen, führt die Umstellung von und auf Sommerzeit zu zwei anomalen Uhrzeiten: ungültige Uhrzeiten und mehrdeutige Uhrzeiten. Bei einer ungültigen Uhrzeit handelt es sich um eine nicht vorhandene Uhrzeit, die durch die Umstellung von Standardzeit auf Sommerzeit entstanden ist. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig. Eine mehrdeutige Uhrzeit ist eine Zeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie wird durch die Umstellung von Sommerzeit auf Standardzeit erzeugt. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden. 

## <a name="time-zone-terminology"></a>Zeitzonenterminologie

In der folgenden Tabelle sind Begriffe definiert, die bei der Arbeit mit Zeitzonen und bei der Entwicklung von Anwendungen, die Zeitzonen unterstützen, häufig verwendet werden.

Begriff | Definition
---- | ----------
Anpassungsregel | Eine Regel, die definiert, wann die Umstellung von Standardzeit auf Sommerzeit und von Sommerzeit auf Standardzeit stattfindet. Jede Anpassungsregel verfügt über ein Anfangs- und ein Enddatum, die definieren, wann die Regel gültig ist (z.B. vom 1. Januar 1986 bis zum 31. Dezember 2020), ein Delta (die Zeit, um die sich die Standardzeit durch Anwendung der Anpassungsregel ändert) sowie Informationen über das Datum und die Uhrzeit, zu denen die Umstellungen während der Anwendung der Anpassungsregel stattfinden. Umstellungen können entweder einer festen oder einer beweglichen Anpassungsregel folgen.
Mehrdeutige Zeit | Eine Uhrzeit, die zwei verschiedenen Uhrzeiten in einer Zeitzone zugeordnet sein kann. Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 1:00 Uhr geändert wird, kann jedes Zeitintervall zwischen 1:00 und 1:59:99 Uhr als Standardzeit oder Sommerzeit interpretiert werden. 
Feste Regel | Eine Anpassungsregel, mit der ein bestimmtes Datum für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise die Umstellung von Sommerzeit auf Standardzeit, die jedes Jahr am 25. Oktober stattfindet, einer festen Anpassungsregel.
Bewegliche Regel | Eine Anpassungsregel, bei der ein bestimmter Tag einer bestimmten Woche eines bestimmten Monats für die Umstellung auf oder von Sommerzeit festgelegt wird. So folgt beispielsweise eine Umstellung von Standardzeit auf Sommerzeit, die am dritten Sonntag im Monat März stattfindet, einer beweglichen Anpassungsregel.
Ungültige Zeit | Eine nicht vorhandene Zeit, die durch die Umstellung von Standardzeit auf Sommerzeit entsteht. Sie tritt auf, wenn die Uhrzeit vorgestellt wird, beispielsweise bei der Umstellung von Standardzeit in einer Zeitzone auf Sommerzeit. Wenn die Umstellung zum Beispiel an einem bestimmten Tag um 2:00 Uhr erfolgt und die Uhrzeit auf 3:00 Uhr geändert wird, ist jedes Zeitintervall zwischen 2:00 und 2:59:99 Uhr ungültig.
Umstellungszeit | Informationen über einen bestimmten Zeitwechsel in einer Zeitzone, z.B. bei der Umstellung von Sommerzeit auf Standardzeit oder umgekehrt.

## <a name="time-zones-and-the-timezoneinfo-class"></a>Zeitzonen und die TimeZoneInfo-Klasse

In .NET stellt ein [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt eine Zeitzone anhand der Informationen, die vom Betriebssystem bereitgestellt werden, dar. Die Abhängigkeit von der [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse des Betriebssystems bedeutet, dass für eine Zeitzonen unterstützende Anwendung nicht sicher sein kann, dass eine bestimmte Zeitzone in allen Betriebssystemen definiert ist. Daher sollte beim Versuch, eine bestimmte Zeitzone zu instanziieren (außer der lokalen Zeitzone oder der Zeitzone, die UTC darstellt), eine Ausnahmebehandlung verwendet werden. Zudem sollte eine Methode bereitgestellt werden, mit der die Anwendung fortfahren kann, wenn ein erforderliches [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt nicht instanziiert werden kann.

Da jede Zeitzone durch eine Basisabweichung von UTC sowie durch eine Abweichung von UTC, mit der eine vorhandene Anpassungsregel wiedergegeben wird, gekennzeichnet ist, kann eine Uhrzeit in einer Zeitzone problemlos in die Uhrzeit in einer anderen Zeitzone konvertiert werden. Zu diesem Zweck enthält das [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt mehrere Konvertierungsmethoden, einschließlich:

* [ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)), mit der [System.DateTime](xref:System.DateTime) in die Uhrzeit in einer bestimmten Zeitzone konvertiert wird.

* [ConvertTime(DateTime, TimeZoneInfo, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo,System.TimeZoneInfo)), mit der [DateTime](xref:System.DateTime) einer Zeitzone in eine andere konvertiert wird.

* [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)), mit der [System.DateTimeOffset](xref:System.DateTimeOffset) in die Uhrzeit in einer bestimmten Zeitzone konvertiert wird. 

Weitere Informationen über das Konvertieren von Uhrzeiten zwischen Zeitzonen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)


<!--HONumber=Nov16_HO3-->


