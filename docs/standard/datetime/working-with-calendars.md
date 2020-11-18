---
title: Arbeiten mit Kalendern
ms.date: 04/01/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
ms.openlocfilehash: c30af36b3426c4abbdf9c55f6c9062a5d8fc8c23
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824251"
---
# <a name="work-with-calendars"></a>Arbeiten mit Kalendern

Obwohl ein Datums- und Uhrzeitwert eine universale zeitliche Angabe darstellt, ist die Zeichenfolgendarstellung eines solchen Werts kulturabhängig. Sie wird sowohl durch die Anzeigekonventionen für Datums- und Uhrzeitwerte einer bestimmten Kultur als auch durch den Kalender bestimmt, der in der jeweiligen Kultur verwendet wird. In diesem Thema wird die Unterstützung für Kalender in .net erläutert und die Verwendung der Kalender Klassen bei der Arbeit mit Datums Werten erläutert.

## <a name="calendars-in-net"></a>Kalender in .net

Alle Kalender in .net sind von der- <xref:System.Globalization.Calendar?displayProperty=nameWithType> Klasse abgeleitet, die die Basis Kalender Implementierung bereitstellt. Eine der Klassen, die von der <xref:System.Globalization.Calendar>-Klasse erbt, ist die <xref:System.Globalization.EastAsianLunisolarCalendar>-Klasse. Dies ist die Basisklasse für alle Mond-Sonne-Kalender. .NET umfasst die folgenden Kalender Implementierungen:

- <xref:System.Globalization.ChineseLunisolarCalendar> stellt den chinesischen Mond-Sonne-Kalender dar.

- <xref:System.Globalization.GregorianCalendar> stellt den gregorianischen Kalender dar. Dieser Kalender ist in weitere Untertypen unterteilt (z. B. Französisch (Naher Osten) oder Arabisch), die durch die <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType>-Enumeration definiert werden. Die <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType>-Eigenschaft gibt den Untertyp des gregorianischen Kalenders an.

- <xref:System.Globalization.HebrewCalendar> stellt den hebräischen Kalender dar.

- <xref:System.Globalization.HijriCalendar> stellt den Hijri-Kalender dar.

- <xref:System.Globalization.JapaneseCalendar> stellt den japanischen Kalender dar.

- <xref:System.Globalization.JapaneseLunisolarCalendar> stellt den japanischen Mond-Sonne-Kalender dar.

- <xref:System.Globalization.JulianCalendar> stellt den julianischen Kalender dar.

- <xref:System.Globalization.KoreanCalendar> stellt den koreanischen Kalender dar.

- <xref:System.Globalization.KoreanLunisolarCalendar> stellt den koreanischen Mond-Sonne-Kalender dar.

- <xref:System.Globalization.PersianCalendar> stellt den persischen Kalender dar.

- <xref:System.Globalization.TaiwanCalendar> stellt den taiwanesischen Kalender dar.

- <xref:System.Globalization.TaiwanLunisolarCalendar> stellt den taiwanesischen Mond-Sonne-Kalender dar.

- <xref:System.Globalization.ThaiBuddhistCalendar> stellt den buddhistischen Kalender Thailands dar.

- <xref:System.Globalization.UmAlQuraCalendar>, der den Umm al-Qura-Kalender darstellt.

Ein Kalender kann auf zwei Arten verwendet werden:

- Als Kalender, der von einer bestimmten Kultur verwendet wird. Jedes <xref:System.Globalization.CultureInfo>-Objekt verfügt über einen aktuellen Kalender. Dies ist der Kalender, den das Objekt gegenwärtig verwendet. Die Zeichenfolgendarstellungen aller Datums- und Uhrzeitwerte entsprechen automatisch der aktuellen Kultur und dem aktuellen Kalender. In der Regel ist als aktueller Kalender der Standardkalender der Kultur angegeben. <xref:System.Globalization.CultureInfo> -Objekte verfügen auch über optionale Kalender, die zusätzliche Kalender enthalten, die von der Kultur verwendet werden können.

- Als eigenständiger Kalender, unabhängig von einer bestimmten Kultur. In diesem Fall werden <xref:System.Globalization.Calendar>-Methoden verwendet, um Datumsangaben in Werten auszudrücken, die dem betreffenden Kalender entsprechen.

Beachten Sie, dass die folgenden sechs Kalenderklassen nur als eigenständige Kalender verwendet werden können: <xref:System.Globalization.ChineseLunisolarCalendar>, <xref:System.Globalization.JapaneseLunisolarCalendar>, <xref:System.Globalization.JulianCalendar>, <xref:System.Globalization.KoreanLunisolarCalendar>, <xref:System.Globalization.PersianCalendar> und <xref:System.Globalization.TaiwanLunisolarCalendar>. Sie werden von keiner Kultur verwendet, weder als Standardkalender noch als optionaler Kalender.

## <a name="calendars-and-cultures"></a>Kalender und Kulturen

Jede Kultur verfügt über einen Standardkalender, der von der <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Die <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Eigenschaft gibt ein Array von <xref:System.Globalization.Calendar>-Objekten zurück, das alle von einer bestimmten Kultur unterstützten Kalender angibt, einschließlich des Standardkalenders der Kultur.

Im folgenden Beispiel werden die <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft und die <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Eigenschaft veranschaulicht. Im Beispiel werden `CultureInfo`-Objekte für die Kulturen Thai (Thailand) und Japanisch (Japan) erstellt und die Standardkalender sowie die optionalen Kalender für diese Kulturen angezeigt. Beachten Sie, dass in beiden Fällen auch der Standardkalender in der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Auflistung enthalten ist.

[!code-csharp[Conceptual.Calendars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/calendarinfo1.cs#1)]
[!code-vb[Conceptual.Calendars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/calendarinfo1.vb#1)]

Der derzeit von einem bestimmten <xref:System.Globalization.CultureInfo>-Objekt verwendete Kalender wird von der <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft der Kultur definiert. Das <xref:System.Globalization.DateTimeFormatInfo>-Objekt einer Kultur wird mit der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben. Beim Erstellen einer Kultur wird ihr Standardwert auf den Wert der <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft festgelegt. Sie können den Standardwert jedoch ändern und als aktuellen Kalender für eine Kultur jeden Kalender angeben, der in dem von der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Array enthalten ist. Wenn Sie versuchen, den aktuellen Kalender auf einen Kalender festzulegen, der nicht in der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Eigenschaft enthalten ist, wird <xref:System.ArgumentException> ausgelöst.

Im folgenden Beispiel wird der Kalender geändert, der von der Kultur Arabisch (Saudi-Arabien) verwendet wird. Zuerst wird ein <xref:System.DateTime>-Wert instanziiert und unter Verwendung der aktuellen Kultur (in diesem Fall Englisch (USA)) sowie des aktuellen Kalenders der Kultur (gregorianischer Kalender) angezeigt. Anschließend wird die aktuelle Kultur in Arabisch (Saudi-Arabien) geändert und das Datum mit dem Standardkalender dieser Kultur, dem Umm al-Qura-Kalender angezeigt. Anschließend wird die `CalendarExists`-Methode aufgerufen, um zu bestimmen, ob der Hijri-Kalender von der Kultur Arabisch (Saudi-Arabien) unterstützt wird. Da der Kalender unterstützt wird, wird Hijri als aktueller Kalender festgelegt und das Datum erneut angezeigt. Beachten Sie, dass das Datum in allen Fällen mit dem aktuellen Kalender der aktuellen Kultur angezeigt wird.

[!code-csharp[Conceptual.Calendars#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/changecalendar2.cs#2)]
[!code-vb[Conceptual.Calendars#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/changecalendar2.vb#2)]

## <a name="dates-and-calendars"></a>Datumsangaben und Kalender

Mit Ausnahme der Konstruktoren, die einen Parameter des Typs <xref:System.Globalization.Calendar> beinhalten und die es gestatten, die Elemente eines Datums (d. h. Monat, Tag und Jahr) in den Werten eines bestimmten Kalenders anzuzeigen, basieren die Werte <xref:System.DateTime> und <xref:System.DateTimeOffset> immer auf dem gregorianischen Kalender. Dies bedeutet, dass die <xref:System.DateTime.Year%2A?displayProperty=nameWithType>-Eigenschaft immer das Jahr und die <xref:System.DateTime.Day%2A?displayProperty=nameWithType>-Eigenschaft immer den Monat im gregorianischen Kalender zurückgibt.

> [!IMPORTANT]
> Es ist wichtig zu beachten, dass zwischen dem Datumswert und der entsprechenden Zeichenfolgendarstellung ein Unterschied besteht. Der erste Wert basiert auf dem gregorianischen Kalender, während der zweite Wert auf dem aktuellen Kalender einer bestimmten Kultur basiert.

Das folgende Beispiel veranschaulicht diesen Unterschied zwischen den <xref:System.DateTime>-Eigenschaften und den entsprechenden <xref:System.Globalization.Calendar>-Methoden. Im Beispiel ist die aktuelle Kultur Arabisch (Ägypten), und der aktuelle Kalender ist Umm al-Qura. Ein <xref:System.DateTime>-Wert wird auf den 15. Tag im 7. Monat des Jahres 2011 festgelegt. Es ist klar, dass diese Werte als gregorianisches Datum interpretiert werden, da die <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode die gleichen Werte zurückgibt, wenn die Konventionen der invarianten Kultur verwendet werden. Die Zeichenfolgendarstellung des Datums, die gemäß den Konventionen der aktuellen Kultur formatiert wird, ist 14/08/32. Dies ist das entsprechende Datum im Umm al-Qura-Kalender. Anschließend werden Member von `DateTime` und `Calendar` verwendet, um den Tag, den Monat und das Jahr des <xref:System.DateTime>-Werts zurückzugeben. In allen Fällen entsprechen die von <xref:System.DateTime>-Membern zurückgegebenen Werte den Werten im gregorianischen Kalender, während die von <xref:System.Globalization.UmAlQuraCalendar>-Membern zurückgegebenen Werte dem Umm al-Qura-Kalender entsprechen.

[!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
[!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]

### <a name="instantiate-dates-based-on-a-calendar"></a>Instanziieren von Datumsangaben auf der Grundlage eines Kalenders

Da <xref:System.DateTime>-Werte und <xref:System.DateTimeOffset>-Werte auf dem gregorianischen Kalender basieren, müssen Sie einen überladenen Konstruktor aufrufen, der einen Parameter vom Typ <xref:System.Globalization.Calendar> beinhaltet, wenn Sie einen Datumswert instanziieren möchten, der Tag, Monat und Jahr eines anderen Kalenders verwenden soll. Sie können auch eine der Überladungen der <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType>-Methode eines bestimmten Kalenders aufrufen, um ein <xref:System.DateTime>-Objekt auf Grundlage der Werte eines bestimmten Kalender zu instanziieren.

Im folgenden Codebeispiel wird ein <xref:System.DateTime>-Wert instanziiert, indem ein <xref:System.Globalization.HebrewCalendar>-Objekt an einen <xref:System.DateTime> Konstruktor übergeben wird. Anschließend wird ein zweiter <xref:System.DateTime>-Wert durch Aufrufen der <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>-Methode instanziiert. Da die beiden Werte mit identischen Werten aus dem hebräischen Kalender erstellt wurden, zeigt ein Aufruf der <xref:System.DateTime.Equals%2A?displayProperty=nameWithType>-Methode, dass beide <xref:System.DateTime>-Werte gleich sind.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="represent-dates-in-the-current-calendar"></a>Datumsangaben im aktuellen Kalender darstellen

Formatierungsmethoden für Datum und Uhrzeit verwenden immer den aktuellen Kalender, wenn Datumsangaben in Zeichenfolgen konvertiert werden sollen. Das heißt, dass die Zeichenfolgendarstellungen für Jahr, Monat und Tag des Monats denen des aktuellen Kalenders entsprechen und nicht notwendigerweise dem gregorianischen Kalender folgen.

Im folgenden Beispiel wird gezeigt, welchen Einfluss der aktuelle Kalender auf die Zeichenfolgendarstellung eines Datums hat. Im Beispiel wird die aktuelle Kultur auf Chinesisch (traditionell, Taiwan) festgelegt und ein Datumswert instanziiert. Anschließend werden der aktuelle Kalender und das Datum angezeigt, der aktuelle Kalender wird in <xref:System.Globalization.TaiwanCalendar> geändert, und Kalender und Datum werden erneut angezeigt. Der erste angezeigte Datumswert verwendet die Darstellung des gregorianischen Kalenders. Der zweite Datumswert wird im Format des taiwanesischen Kalenders dargestellt.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="represent-dates-in-a-non-current-calendar"></a>Datumsangaben in einem nicht aktuellen Kalender darstellen

Um ein Datum unter Verwendung eines anderen als des aktuellen Kalenders einer bestimmten Kultur darzustellen, müssen Sie Methoden des gewünschten <xref:System.Globalization.Calendar>-Objekts aufrufen. Zum Beispiel konvertieren die Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> das Jahr, den Monat und den Tag in die Darstellung eines bestimmten Kalenders.

> [!WARNING]
> Da einige Kalender nicht als optionale Kalender für eine Kultur definiert sind, erfordert die Darstellung von Datumsangaben mit diesen Kalendern stets einen Aufruf der Methoden des entsprechenden Kalenders. Dies gilt für alle Kalender, die von den Klassen <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> und <xref:System.Globalization.PersianCalendar> abgeleitet sind.

Im folgenden Beispiel wird ein <xref:System.Globalization.JulianCalendar>-Objekt verwendet, um ein Datum (9. Januar 1905) im julianischen Kalender zu instanziieren. Wenn dieses Datum mit dem gregorianischen Standardkalender dargestellt wird, wird es als 22. Januar 1905 angezeigt. Aufrufe einzelner <xref:System.Globalization.JulianCalendar>-Methoden ermöglichen eine Darstellung des Datums mit dem julianischen Kalender.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Kalender und Datumsbereiche

Das früheste Datum, das von einem Kalender unterstützt wird, wird durch die <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Eigenschaft dieses Kalenders angegeben. Für die <xref:System.Globalization.GregorianCalendar>-Klasse ist dieses Datum der 1. Januar 0001 unserer Zeitrechnung. Die meisten anderen Kalender in .NET unterstützen ein späteres Datum. Der Versuch, mit einem Datums- und Zeitwert zu arbeiten, der vor dem frühesten unterstützten Datum eines Kalenders liegt, löst eine <xref:System.ArgumentOutOfRangeException> Ausnahme aus.

Es gibt jedoch eine wichtige Ausnahme. Der (nicht initialisierte) Standardwert eines <xref:System.DateTime>-Objekts und eines <xref:System.DateTimeOffset>-Objekts ist gleich dem <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Wert. Wenn Sie versuchen, dieses Datum in einem Kalender zu formatieren, der den 1. Januar 0001 nicht unterstützt, und Sie geben keinen Format Bezeichner an, die Formatierungs Methode verwendet den Format Bezeichner "s" (Sortier barer Datums-/Uhrzeitmuster) anstelle des Format Bezeichnern "G" (allgemeiner Datums-/Uhrzeitmuster). In der Folge löst der Formatierungsvorgang keine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus. Stattdessen wird das nicht unterstützte Datum zurückgegeben. Dies wird im folgenden Beispiel veranschaulicht. Der Wert von <xref:System.DateTime.MinValue?displayProperty=nameWithType> wird anzeigt, wenn die aktuelle Kultur auf Japanisch (Japan) mit dem japanischen Kalender und in Arabisch (Ägypten) mit dem Um Al Qura-Kalender festgelegt wird. Außerdem wird die aktuelle Kultur auf Englisch (USA) festgelegt die <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>-Methode mit jedem dieser <xref:System.Globalization.CultureInfo>-Objekte aufgerufen. In jedem Fall wird das Datum mithilfe des sortierbaren Datums-/Zeitmusters angezeigt.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="work-with-eras"></a>Arbeiten mit Epochen

Kalender unterteilen Datumsangaben in der Regel in Zeiträume. Die <xref:System.Globalization.Calendar> Klassen in .NET unterstützen jedoch nicht jeden von einem Kalender definierten Zeitraum, und die meisten <xref:System.Globalization.Calendar> Klassen unterstützen nur einen einzelnen Zeitraum. Nur die Klassen <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> unterstützen mehrere Zeiträume.

> [!IMPORTANT]
> Der reiwa-Zeitraum, ein neuer Zeitraum in <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> , beginnt am 1. Mai 2019. Diese Änderung betrifft alle Anwendungen, die diese Kalender verwenden. Weitere Informationen finden Sie in den folgenden Artikeln:
>
> - [Die Verarbeitung eines neuen Zeitraums im japanischen Kalender in .net](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), mit dem Features dokumentiert werden, die .net hinzugefügt wurden, um Kalender mit mehreren Zeiträumen zu unterstützen, und bewährte Methoden für die Verarbeitung von Kalender in mehreren Epochen erläutert werden.
> - [Bereiten Sie Ihre Anwendung auf den japanischen](/windows/uwp/design/globalizing/japanese-era-change)Zeitraum vor, der Informationen zum Testen von Anwendungen unter Windows bereitstellt, um sicherzustellen, dass die Zeit für den Zeitraum geändert wird.
> - [Zusammenfassung der neuen japanischen Zeit Updates für .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), die .NET Framework Updates für einzelne Windows-Versionen auflistet, die sich auf den neuen japanischen Kalender beziehen, sowie neue .NET Framework Features für die Unterstützung von mehreren Versionen

Ein Zeitraum in den meisten Kalendern deutet auf einen extrem langen Zeitraum hin. Im gregorianischen Kalender umfasst z. b. die aktuelle Ära mehr als zweitausend tausend. Für <xref:System.Globalization.JapaneseCalendar> und die beiden Kalender, die mehrere Zeiträume <xref:System.Globalization.JapaneseLunisolarCalendar> unterstützen, ist dies nicht der Fall. Ein Zeitraum entspricht dem Zeitraum der Regierung eines Kaisers. Unterstützung für mehrere Zeiträume, insbesondere wenn die Obergrenze des aktuellen Zeitraums unbekannt ist, stellt besondere Herausforderungen dar.

### <a name="eras-and-era-names"></a>Zeit-und Zeit Namen

In .net werden ganze Zahlen, die die von einer bestimmten Kalender Implementierung unterstützten Zeiträume darstellen, in umgekehrter Reihenfolge im <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> Array gespeichert. Der aktuelle Zeitraum (bei dem es sich um den Zeitraum mit dem letzten Zeitbereich handelt) liegt bei Index 0 (null), und bei Klassen, die <xref:System.Globalization.Calendar> mehrere Zeiträume unterstützen, spiegelt jeder aufeinander folgende Index den vorherigen Zeitraum wider. Die statische <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType>-Eigenschaft definiert den Index des aktuellen Zeitraums im <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>-Array. Dies ist eine Konstante, die stets den Wert 0 (null) hat. Einzelne <xref:System.Globalization.Calendar>-Klassen beinhalten darüber hinaus auch statische Felder, die den Wert des aktuellen Zeitraums zurückgeben. Sie sind in der folgenden Tabelle aufgeführt.

| Kalenderklasse                                        | Feld für den aktuellen Zeitraum                                                 |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| <xref:System.Globalization.ChineseLunisolarCalendar>  | <xref:System.Globalization.ChineseLunisolarCalendar.ChineseEra>   |
| <xref:System.Globalization.GregorianCalendar>         | <xref:System.Globalization.GregorianCalendar.ADEra>               |
| <xref:System.Globalization.HebrewCalendar>            | <xref:System.Globalization.HebrewCalendar.HebrewEra>              |
| <xref:System.Globalization.HijriCalendar>             | <xref:System.Globalization.HijriCalendar.HijriEra>                |
| <xref:System.Globalization.JapaneseLunisolarCalendar> | <xref:System.Globalization.JapaneseLunisolarCalendar.JapaneseEra> |
| <xref:System.Globalization.JulianCalendar>            | <xref:System.Globalization.JulianCalendar.JulianEra>              |
| <xref:System.Globalization.KoreanCalendar>            | <xref:System.Globalization.KoreanCalendar.KoreanEra>              |
| <xref:System.Globalization.KoreanLunisolarCalendar>   | <xref:System.Globalization.KoreanLunisolarCalendar.GregorianEra>  |
| <xref:System.Globalization.PersianCalendar>           | <xref:System.Globalization.PersianCalendar.PersianEra>            |
| <xref:System.Globalization.ThaiBuddhistCalendar>      | <xref:System.Globalization.ThaiBuddhistCalendar.ThaiBuddhistEra>  |
| <xref:System.Globalization.UmAlQuraCalendar>          | <xref:System.Globalization.UmAlQuraCalendar.UmAlQuraEra>          |

Der Name, der dem Zeitraum mit einer bestimmten Nummer entspricht, kann durch Übergeben der Nummer an die <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>-Methode oder an die <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>-Methode abgerufen werden. Im folgenden Beispiel werden diese Methoden aufgerufen, um Informationen über die Unterstützung von Zeiträumen in der <xref:System.Globalization.GregorianCalendar>-Klasse abzurufen. Es zeigt das Gregorianische Kalenderdatum an, das dem 1. Januar des zweiten Jahres des aktuellen Zeitraums entspricht, sowie das Gregorianische Kalenderdatum, das dem 1. Januar des zweiten Jahres jedes unterstützten japanischen Kalender Zeitraums entspricht.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Darüber hinaus enthält die benutzerdefinierte Formatzeichenfolge "g" für Datum und Uhrzeit den Namen des Zeitraums eines Kalenders in der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts. Weitere Informationen finden Sie unter [benutzerdefinierte Format](../base-types/custom-date-and-time-format-strings.md)Zeichenfolgen für Datum und Uhrzeit.

### <a name="instantiatie-a-date-with-an-era"></a>Instantiatie a Date with a ERA

Für die beiden <xref:System.Globalization.Calendar> Klassen, die mehrere Zeiträume unterstützen, kann ein Datum, das aus einem bestimmten Jahr, Monat und Tag des Monats Werts besteht, mehrdeutig sein. Beispielsweise haben alle Zeiträume, die von unterstützt werden, <xref:System.Globalization.JapaneseCalendar> Jahre, deren Zahl 1 ist. Wenn kein Zeitraum angegeben ist, wird daher bei Datums-, Uhrzeit- und Klassenmethoden immer davon ausgegangen, dass die Werte zum aktuellen Zeitraum gehören. Dies gilt für die <xref:System.DateTime.%23ctor%2A> Konstruktoren und, die <xref:System.DateTimeOffset.%23ctor%2A> Parameter vom Typ enthalten <xref:System.Globalization.Calendar> , sowie die Methoden [JapaneseCalendar. ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) und [JapaneseLunisolarCalendar. ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) . Im folgenden Beispiel wird ein Datum instanziiert, das den 1. Januar des zweiten Jahres eines nicht angegebenen Zeitraums darstellt. Wenn Sie das Beispiel ausführen, wenn der reiwa-Zeitraum der aktuelle Zeitraum ist, wird das Datum als zweites Jahr des reiwa-Zeitraums interpretiert. Der ERA, 令和, steht vor dem Jahr in der Zeichenfolge, die von der-Methode zurückgegeben wird, <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> und entspricht dem 1. Januar 2020 im gregorianischen Kalender. (Die reiwa-Ära beginnt im Jahr 2019 des gregorianischen Kalenders.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Wenn sich der ERA jedoch ändert, wird der Zweck dieses Codes mehrdeutig. Ist das Datum, das das zweite Jahr des aktuellen Zeitraums darstellen soll, oder soll das zweite Jahr des Heisei-Zeitraums repräsentiert werden? Es gibt zwei Möglichkeiten, diese Mehrdeutigkeit zu vermeiden:

- Instanziieren Sie den Datums-und Uhrzeitwert mit der Default- <xref:System.Globalization.GregorianCalendar> Klasse. Anschließend können Sie den japanischen Kalender oder den japanischen lunisolar-Kalender für die Zeichen folgen Darstellung von Datumsangaben verwenden, wie im folgenden Beispiel gezeigt.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Ruft eine Datums-und Uhrzeit Methode auf, die explizit einen Zeitraum angibt. Dazu gehören folgende Methoden:

  - Die- <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> Methode der- <xref:System.Globalization.JapaneseCalendar> Klasse oder der- <xref:System.Globalization.JapaneseLunisolarCalendar> Klasse.

  - Eine-oder-Analyse <xref:System.DateTime> <xref:System.DateTimeOffset> Methode, z. b. <xref:System.DateTime.Parse%2A> , <xref:System.DateTime.TryParse%2A> , <xref:System.DateTime.ParseExact%2A> oder, die <xref:System.DateTime.TryParseExact%2A> die zu erteilende Zeichenfolge enthält, und optional ein <xref:System.Globalization.DateTimeStyles> Argument, wenn die aktuelle Kultur Japanese-Japan ("ja-JP") und der Kalender der Kultur ist <xref:System.Globalization.JapaneseCalendar> . Die Zeichenfolge, die analysiert werden soll, muss den Zeitraum enthalten.

  - Eine- <xref:System.DateTime> oder- <xref:System.DateTimeOffset> Methode, die einen `provider` Parameter vom Typ enthält <xref:System.IFormatProvider> . `provider` muss entweder ein- <xref:System.Globalization.CultureInfo> Objekt sein, das die Kultur der Japanese-Japan ("ja-JP") darstellt, deren aktueller Kalender ist, <xref:System.Globalization.JapaneseCalendar> oder ein- <xref:System.Globalization.DateTimeFormatInfo> Objekt, dessen- <xref:System.Globalization.DateTimeFormatInfo.Calendar> Eigenschaft ist <xref:System.Globalization.JapaneseCalendar> . Die Zeichenfolge, die analysiert werden soll, muss den Zeitraum enthalten.

  Im folgenden Beispiel werden drei dieser Methoden verwendet, um ein Datum und eine Uhrzeit in der Meiji-Ära zu instanziieren, die am 8. September 1868 begonnen und am 29. Juli 1912 endete.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> Wenn Sie Kalender arbeiten, die mehrere Zeiträume unterstützen, verwenden Sie *immer* das gregorianische Datum, um ein Datum zu instanziieren, oder geben Sie den Zeitraum an, wenn Sie ein Datum und eine Uhrzeit basierend auf diesem Kalender instanziieren.

Wenn Sie einen Zeitraum für die <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> Methode angeben, geben Sie den Index des Zeitraums in der-Eigenschaft des Kalenders an <xref:System.Globalization.Calendar.Eras> . Bei Kalendern, deren Zeiträume geändert werden können, handelt es sich bei diesen Indizes jedoch nicht um konstante Werte. der aktuelle Zeitraum liegt bei Index 0 und der älteste Zeitraum bei Index `Eras.Length - 1` . Wenn einem Kalender ein neuer Zeitraum hinzugefügt wird, werden die Indizes der vorherigen Zeiträume um 1 erhöht. Sie können den entsprechenden ERA-Index wie folgt angeben:

- Verwenden Sie für Datumsangaben im aktuellen Zeitraum stets die-Eigenschaft des Kalenders <xref:System.Globalization.Calendar.CurrentEra> .

- Verwenden Sie für Datumsangaben in einem bestimmten Zeitraum die- <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> Methode, um den Index abzurufen, der einem angegebenen Zeit Namen entspricht. Dies erfordert, dass das der <xref:System.Globalization.JapaneseCalendar> aktuelle Kalender des <xref:System.Globalization.CultureInfo> Objekts ist, das die Kultur "ja-JP" darstellt.  (Dieses Verfahren funktioniert auch für das <xref:System.Globalization.JapaneseLunisolarCalendar> , da es die gleichen Zeiträume wie die unterstützt <xref:System.Globalization.JapaneseCalendar> .) Diese Vorgehensweise wird im vorherigen Beispiel veranschaulicht.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Kalender, Zeiträume und Datumsbereiche: gelockerte Bereichs Überprüfungen

Sehr ähnlich wie die einzelnen Kalender unterstützte Datumsbereiche haben, <xref:System.Globalization.JapaneseCalendar> <xref:System.Globalization.JapaneseLunisolarCalendar> haben Zeiträume in den Klassen und auch unterstützte Bereiche. Zuvor hat .net strikte Zeit Bereichs Überprüfungen verwendet, um sicherzustellen, dass ein Zeit spezifisches Datum innerhalb des Gültigkeits Bereichs liegt. Das heißt, wenn ein Datum außerhalb des Bereichs des angegebenen Zeitraums liegt, löst die Methode eine aus <xref:System.ArgumentOutOfRangeException> . Derzeit verwendet .net eine gelockerte Bereichs Überprüfung standardmäßig. Bei Updates für alle Versionen von .net wurden gelockerte Bereichs Überprüfungen durchgeführt. der Versuch, ein Zeit spezifisches Datum zu instanziieren, das außerhalb des Bereichs des angegebenen Zeitraums liegt, wird in den folgenden Zeitraum umgewandelt, und es wird keine Ausnahme ausgelöst.

Im folgenden Beispiel wird versucht, ein Datum im 65. Jahr des Showa-Zeitraums zu instanziieren, das am 25. Dezember 1926 begonnen und am 7. Januar 1989 endet. Dieses Datum entspricht dem 9. Januar 1990, das außerhalb des Bereichs des Showa-Zeitraums in der liegt <xref:System.Globalization.JapaneseCalendar> . Wie die Ausgabe aus dem Beispiel zeigt, ist das im Beispiel angezeigte Datum der 9. Januar 1990 im zweiten Jahr des Heisei-Zeitraums.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Wenn eine gelockerte Bereichs Überprüfung nicht erwünscht ist, können Sie strikte Bereichs Überprüfungen auf verschiedene Weise wiederherstellen, abhängig von der .NET-Version, auf der die Anwendung ausgeführt wird:

- **.Net Core:** Fügen Sie dem *.netcore.runtime.jsin* der Konfigurationsdatei Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET Framework 4,6 oder höher:** Legen Sie den folgenden appContext-Switch in der *app.config* -Datei fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungs Wert fest:

   |  |  |
   |--|--|
   | **Key** | **HKEY_LOCAL_MACHINE\Software\Microsoft\\ . Netframework\appcontext** |
   | **Name** | Switch.System. Globalization. enforcejapaneseerayearranges |
   | **Typ** | REG_SZ |
   | **Wert** | true |

Bei aktivierten strengen Bereichs Prüfungen löst das vorherige Beispiel eine aus <xref:System.ArgumentOutOfRangeException> und zeigt die folgende Ausgabe an:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="represent-dates-in-calendars-with-multiple-eras"></a>Darstellen von Datumsangaben in Kalendern mit mehreren Epochen

Wenn ein <xref:System.Globalization.Calendar>-Objekt Zeiträume unterstützt und es sich um den aktuellen Kalender eines <xref:System.Globalization.CultureInfo>-Objekts handelt, beinhalten die Zeichenfolgendarstellungen für die Muster vollständiges Datum und Uhrzeit, langes Datum und kurzes Datum auch den Zeitraum des Datums- und Uhrzeitwerts. Das folgende Beispiel zeigt diese Datumsmuster, wenn die aktuelle Kultur auf Japan (japanisch) festgelegt und als aktueller Kalender der japanische Kalender angegeben ist.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> Die- <xref:System.Globalization.JapaneseCalendar> Klasse ist die einzige Calendar-Klasse in .net, die beide Datumsangaben in mehr als einem Zeitraum unterstützt, wobei es sich um den aktuellen Kalender eines-Objekts handeln kann, <xref:System.Globalization.CultureInfo> insbesondere für ein- <xref:System.Globalization.CultureInfo> Objekt, das die Kultur Japanisch (Japan) darstellt.

Bei allen Kalendern enthält der benutzerdefinierte Formatbezeichner "g" auch den Zeitraum in der Ergebniszeichenfolge. Das folgende Beispiel verwendet die benutzerdefinierte Formatzeichenfolge "MM-DD-yyyy g", um den Zeitraum in der Ergebniszeichenfolge anzuzeigen, wenn als aktueller Kalender der gregorianische Kalender festgelegt ist.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

In Fällen, in denen die Zeichenfolgendarstellung eines Datums in einem Kalender ausgedrückt wird, der nicht der aktuelle Kalender ist, beinhaltet die <xref:System.Globalization.Calendar>-Klasse eine <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>-Methode, die zusammen mit den Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> verwendet werden kann, um ein Datum eindeutig zusammen mit dem Zeitraum anzugeben, zu dem es gehört. Im folgenden Beispiel wird dies anhand der <xref:System.Globalization.JapaneseLunisolarCalendar>-Klasse veranschaulicht. Beachten Sie jedoch, dass Sie ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt instanziieren und <xref:System.Globalization.JapaneseCalendar> als dessen aktuellen Kalender festlegen müssen, wenn Sie in der Ergebniszeichenfolge anstelle einer Zahl einen aussagekräftigen Namen oder eine Abkürzung für den Zeitraum anzeigen möchten. (Der <xref:System.Globalization.JapaneseLunisolarCalendar>-Kalender kann nicht als aktueller Kalender einer Kultur festgelegt werden, in diesem Fall teilen sich aber zwei Kalender dieselben Zeiträume.

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

In den japanischen Kalendern heißt das erste Jahr eines Zeitraums "Gannen" (元年). Beispielsweise kann anstelle von Heisei 1 das erste Jahr der Heisei-Ära als Heisei-Gannen beschrieben werden. .Net übernimmt diese Konvention bei Formatierungs Vorgängen für Datums-und Uhrzeitangaben, die mit den folgenden standardmäßigen oder benutzerdefinierten Format Zeichenfolgen für Datum und Uhrzeit formatiert sind, wenn Sie mit einem-Objekt verwendet werden <xref:System.Globalization.CultureInfo> , das die Kultur Japanese-Japan ("ja-JP") <xref:System.Globalization.JapaneseCalendar>

- [Das lange Datums Muster](../base-types/standard-date-and-time-format-strings.md#LongDate), angegeben durch die Standardformat Zeichenfolge "D" für Datum und Uhrzeit.
- [Das vollständige Datums-/Uhrzeit-Muster](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), das durch die Standardformat Zeichenfolge für Datum und Uhrzeit angegeben wird.
- [Das Muster für die vollständige Datums-/Uhrzeit-Zeit](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), das durch die Standardformat Zeichenfolge "f" angegeben wird.
- [Das Jahr/Monat-Muster](../base-types/standard-date-and-time-format-strings.md#YearMonth), das durch die y-oder y-Standardformat Zeichenfolge für Datum und Uhrzeit angegeben wird.
- [Die [benutzerdefinierte Format Zeichenfolge für Datum und Uhrzeit](../base-types/custom-date-and-time-format-strings.md)von "ggy" 年 "" oder "ggy年".

Im folgenden Beispiel wird z. b. ein Datum im ersten Jahr der Heisei-Zeit in der angezeigt <xref:System.Globalization.JapaneseCalendar> .

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Wenn dieses Verhalten bei Formatierungs Vorgängen nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, das das erste Jahr eines Zeitraums immer als "1" anstelle von "Gannen" darstellt, und zwar je nach Version von .net:

- **.Net Core:** Fügen Sie dem *.netcore.runtime.jsin* der Konfigurationsdatei Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET Framework 4,6 oder höher:** Legen Sie den folgenden appContext-Switch in der *app.config* -Datei fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungs Wert fest:

   |  |  |
   |--|--|
   | **Key** | **HKEY_LOCAL_MACHINE\Software\Microsoft\\ . Netframework\appcontext** |
   | **Name** | Switch.System. Globalization. formatjapanesefirstyearasanumber |
   | **Typ** | REG_SZ |
   | **Wert** | true |

Mit der Unterstützung von Gannen in Formatierungs Vorgängen wird im vorherigen Beispiel die folgende Ausgabe angezeigt:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.Net wurde ebenfalls aktualisiert, sodass Datums-und Uhrzeit-Verarbeitungsvorgänge Zeichen folgen unterstützen, die das Jahr enthalten, das entweder als "1" oder als "Gannen" dargestellt wird. Dies ist zwar nicht erforderlich, aber Sie können das vorherige Verhalten wiederherstellen, um nur "1" als erstes Jahr eines Zeitraums zu erkennen. Sie können dies abhängig von der .NET-Version wie folgt ausführen:

- **.Net Core:** Fügen Sie dem *.netcore.runtime.jsin* der Konfigurationsdatei Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET Framework 4,6 oder höher:** Legen Sie den folgenden appContext-Switch in der *app.config* -Datei fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungs Wert fest:

   |  |  |
   |--|--|
   | **Key** | **HKEY_LOCAL_MACHINE\Software\Microsoft\\ . Netframework\appcontext** |
   | **Name** | Switch.System. Globalization. enforcelegacyjapanesedateparamesing |
   | **Typ** | REG_SZ |
   | **Wert** | true |

## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Anzeigen von Datumsangaben in nicht Gregorianischen Kalendern](../base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Beispiel: Hilfsprogramm für Kalenderwochen Bereich](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Kalenderklasse](xref:System.Globalization.Calendar)
