---
title: Arbeiten mit Kalendern
ms.date: 04/01/2019
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 989c1dec8056502e94e4b9652af89d66a2795dd5
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661159"
---
# <a name="working-with-calendars"></a>Arbeiten mit Kalendern

Obwohl ein Datums- und Uhrzeitwert eine universale zeitliche Angabe darstellt, ist die Zeichenfolgendarstellung eines solchen Werts kulturabhängig. Sie wird sowohl durch die Anzeigekonventionen für Datums- und Uhrzeitwerte einer bestimmten Kultur als auch durch den Kalender bestimmt, der in der jeweiligen Kultur verwendet wird. Dieses Thema behandelt die Unterstützung für Kalender in .NET und erläutert die Verwendung der Kalenderklassen, bei der Arbeit mit Datumswerten.

## <a name="calendars-in-net"></a>Kalender in .NET

Alle Kalender in .NET leiten Sie von der <xref:System.Globalization.Calendar?displayProperty=nameWithType> -Klasse, die die basisimplementierung für Kalender-Implementierung bietet. Eine der Klassen, die von der <xref:System.Globalization.Calendar>-Klasse erbt, ist die <xref:System.Globalization.EastAsianLunisolarCalendar>-Klasse. Dies ist die Basisklasse für alle Mond-Sonne-Kalender. .NET umfasst folgende kalenderimplementierungen:

* <xref:System.Globalization.ChineseLunisolarCalendar> stellt den chinesischen Mond-Sonne-Kalender dar.

* <xref:System.Globalization.GregorianCalendar> stellt den gregorianischen Kalender dar. Dieser Kalender ist in weitere Untertypen unterteilt (z. B. Französisch (Naher Osten) oder Arabisch), die durch die <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType>-Enumeration definiert werden. Die <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType>-Eigenschaft gibt den Untertyp des gregorianischen Kalenders an.

* <xref:System.Globalization.HebrewCalendar> stellt den hebräischen Kalender dar.

* <xref:System.Globalization.HijriCalendar> stellt den Hijri-Kalender dar.

* <xref:System.Globalization.JapaneseCalendar> stellt den japanischen Kalender dar.

* <xref:System.Globalization.JapaneseLunisolarCalendar> stellt den japanischen Mond-Sonne-Kalender dar.

* <xref:System.Globalization.JulianCalendar> stellt den julianischen Kalender dar.

* <xref:System.Globalization.KoreanCalendar> stellt den koreanischen Kalender dar.

* <xref:System.Globalization.KoreanLunisolarCalendar> stellt den koreanischen Mond-Sonne-Kalender dar.

* <xref:System.Globalization.PersianCalendar> stellt den persischen Kalender dar.

* <xref:System.Globalization.TaiwanCalendar> stellt den taiwanesischen Kalender dar.

* <xref:System.Globalization.TaiwanLunisolarCalendar> stellt den taiwanesischen Mond-Sonne-Kalender dar.

* <xref:System.Globalization.ThaiBuddhistCalendar> stellt den buddhistischen Kalender Thailands dar.

* <xref:System.Globalization.UmAlQuraCalendar>, der den Umm al-Qura-Kalender darstellt.

Ein Kalender kann auf zwei Arten verwendet werden:

* Als Kalender, der von einer bestimmten Kultur verwendet wird. Jedes <xref:System.Globalization.CultureInfo>-Objekt verfügt über einen aktuellen Kalender. Dies ist der Kalender, den das Objekt gegenwärtig verwendet. Die Zeichenfolgendarstellungen aller Datums- und Uhrzeitwerte entsprechen automatisch der aktuellen Kultur und dem aktuellen Kalender. In der Regel ist als aktueller Kalender der Standardkalender der Kultur angegeben. <xref:System.Globalization.CultureInfo> Objekte verfügen außerdem über optionale Kalender, die zusätzlichen Kalender angeben, die die Kultur verwenden können.

* Als eigenständiger Kalender, unabhängig von einer bestimmten Kultur. In diesem Fall werden <xref:System.Globalization.Calendar>-Methoden verwendet, um Datumsangaben in Werten auszudrücken, die dem betreffenden Kalender entsprechen.

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

### <a name="instantiating-dates-based-on-a-calendar"></a>Instanziieren von Datumsangaben basierend auf einem Kalender

Da <xref:System.DateTime>-Werte und <xref:System.DateTimeOffset>-Werte auf dem gregorianischen Kalender basieren, müssen Sie einen überladenen Konstruktor aufrufen, der einen Parameter vom Typ <xref:System.Globalization.Calendar> beinhaltet, wenn Sie einen Datumswert instanziieren möchten, der Tag, Monat und Jahr eines anderen Kalenders verwenden soll. Sie können auch eine der Überladungen der <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType>-Methode eines bestimmten Kalenders aufrufen, um ein <xref:System.DateTime>-Objekt auf Grundlage der Werte eines bestimmten Kalender zu instanziieren.

Im folgenden Codebeispiel wird ein <xref:System.DateTime>-Wert instanziiert, indem ein <xref:System.Globalization.HebrewCalendar>-Objekt an einen <xref:System.DateTime> Konstruktor übergeben wird. Anschließend wird ein zweiter <xref:System.DateTime>-Wert durch Aufrufen der <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>-Methode instanziiert. Da die beiden Werte mit identischen Werten aus dem hebräischen Kalender erstellt wurden, zeigt ein Aufruf der <xref:System.DateTime.Equals%2A?displayProperty=nameWithType>-Methode, dass beide <xref:System.DateTime>-Werte gleich sind.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="representing-dates-in-the-current-calendar"></a>Darstellen von Datumsangaben im aktuellen Kalender

Formatierungsmethoden für Datum und Uhrzeit verwenden immer den aktuellen Kalender, wenn Datumsangaben in Zeichenfolgen konvertiert werden sollen. Das heißt, dass die Zeichenfolgendarstellungen für Jahr, Monat und Tag des Monats denen des aktuellen Kalenders entsprechen und nicht notwendigerweise dem gregorianischen Kalender folgen.

Im folgenden Beispiel wird gezeigt, welchen Einfluss der aktuelle Kalender auf die Zeichenfolgendarstellung eines Datums hat. Im Beispiel wird die aktuelle Kultur auf Chinesisch (traditionell, Taiwan) festgelegt und ein Datumswert instanziiert. Anschließend werden der aktuelle Kalender und das Datum angezeigt, der aktuelle Kalender wird in <xref:System.Globalization.TaiwanCalendar> geändert, und Kalender und Datum werden erneut angezeigt. Der erste angezeigte Datumswert verwendet die Darstellung des gregorianischen Kalenders. Der zweite Datumswert wird im Format des taiwanesischen Kalenders dargestellt.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="representing-dates-in-a-non-current-calendar"></a>Darstellen von Datumsangaben in einem nicht-aktuellen Kalender

Um ein Datum unter Verwendung eines anderen als des aktuellen Kalenders einer bestimmten Kultur darzustellen, müssen Sie Methoden des gewünschten <xref:System.Globalization.Calendar>-Objekts aufrufen. Zum Beispiel konvertieren die Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> das Jahr, den Monat und den Tag in die Darstellung eines bestimmten Kalenders.

> [!WARNING]
> Da einige Kalender nicht als optionale Kalender für eine Kultur definiert sind, erfordert die Darstellung von Datumsangaben mit diesen Kalendern stets einen Aufruf der Methoden des entsprechenden Kalenders. Dies gilt für alle Kalender, die von den Klassen <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> und <xref:System.Globalization.PersianCalendar> abgeleitet sind.

Im folgenden Beispiel wird ein <xref:System.Globalization.JulianCalendar>-Objekt verwendet, um ein Datum (9. Januar 1905) im julianischen Kalender zu instanziieren. Wenn dieses Datum mit dem gregorianischen Standardkalender dargestellt wird, wird es als 22. Januar 1905 angezeigt. Aufrufe einzelner <xref:System.Globalization.JulianCalendar>-Methoden ermöglichen eine Darstellung des Datums mit dem julianischen Kalender.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Kalender und Datumsbereiche

Das früheste Datum, das von einem Kalender unterstützt wird, wird durch die <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Eigenschaft dieses Kalenders angegeben. Für die <xref:System.Globalization.GregorianCalendar>-Klasse ist dieses Datum der 1. Januar 0001 unserer Zeitrechnung. Die meisten anderen Kalender in .NET unterstützen ein späteres Datum. Der Versuch, mit einem Datums- und Zeitwert zu arbeiten, der vor dem frühesten unterstützten Datum eines Kalenders liegt, löst eine <xref:System.ArgumentOutOfRangeException> Ausnahme aus.

Es gibt jedoch eine wichtige Ausnahme. Der (nicht initialisierte) Standardwert eines <xref:System.DateTime>-Objekts und eines <xref:System.DateTimeOffset>-Objekts ist gleich dem <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Wert. Wenn Sie versuchen, dieses Datum in einem Kalender zu formatieren, das am 1. Januar 0001 unserer Zeitrechnung nicht unterstützt. und keinen Formatbezeichner angegeben, verwendet die Formatierungsmethode den Formatbezeichner für "s" (sortierbares Datums-/Zeitmuster) anstelle des Formatbezeichners "G" (Allgemeine Datums-/Zeitmuster). In der Folge löst der Formatierungsvorgang keine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus. Stattdessen wird das nicht unterstützte Datum zurückgegeben. Dies wird im folgenden Beispiel veranschaulicht. Der Wert von <xref:System.DateTime.MinValue?displayProperty=nameWithType> wird anzeigt, wenn die aktuelle Kultur auf Japanisch (Japan) mit dem japanischen Kalender und in Arabisch (Ägypten) mit dem Um Al Qura-Kalender festgelegt wird. Außerdem wird die aktuelle Kultur auf Englisch (USA) festgelegt die <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>-Methode mit jedem dieser <xref:System.Globalization.CultureInfo>-Objekte aufgerufen. In jedem Fall wird das Datum mithilfe des sortierbaren Datums-/Zeitmusters angezeigt.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="working-with-eras"></a>Arbeiten mit Zeiträumen

Kalender unterteilen Datumsangaben in der Regel in Zeiträume. Allerdings die <xref:System.Globalization.Calendar> Klassen in .NET unterstützen nicht alle Zeiträume, die durch einen Kalender, und die meisten definiert die <xref:System.Globalization.Calendar> Klassen unterstützen nur einen einzigen Zeitraum. Nur die Klassen <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> unterstützen mehrere Zeiträume.

> [!IMPORTANT]
> Der Zeitraum Reiwa, eine neue Ära in der <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar>, beginnt am 1. Mai 2019. Diese Änderung betrifft alle Anwendungen, die diese Kalender verwenden. Finden Sie unter den folgenden Artikeln Weitere Informationen:
> - [Behandeln eine neue Ära im japanischen Kalender in .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), Kalender mit mehreren Zeiträumen und erläutert bewährte Verfahren zu verwenden, bei der Verarbeitung mit mehreren Zeitraum Kalender in der dokumentiert sind Funktionen hinzugefügt, die zu .NET unterstützen.
> - [Vorbereiten Ihrer Anwendung auf die japanischen Zeitraum Änderung](/windows/uwp/design/globalizing/japanese-era-change), die Informationen bereitstellt, auf das Testen von Anwendungen auf Windows, um sicherzustellen, dass deren Bereitschaft für den Zeitraum ändern.
> - [Zusammenfassung der neuen japanischen Ära aktualisiert für .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), dem .NET Framework-Updates für einzelne Windows-Versionen aufgeführt, die im Zusammenhang mit der neuen Ära der japanischen Kalender, Anmerkungen zu dieser neuen Features von .NET Framework für die Unterstützung von mehreren Zeiträumen und enthält die Dinge, die beim Testen Ihrer Anwendungen gesucht.

Ein Zeitraum, in den meisten Kalendern gibt einen extrem langen Zeitraum an. Im gregorianischen Kalender umfasst mehr als zwei Jahrtausenden z. B. der aktuelle Zeitraum. Für die <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar>, die beiden Kalender, die mehrere Zeiträume unterstützen, ist dies nicht der Fall. Ein Zeitraum entspricht dem Zeitraum des ein Kaisers. Unterstützung für mehrere Zeiträume, insbesondere dann, wenn die Obergrenze des aktuellen Zeitraums unbekannt ist, beträgt besondere Herausforderungen verbunden ist.

### <a name="eras-and-era-names"></a>Zeiträume und Namen

In .NET Ganzzahlen, das die Zeiträume unterstützt bei einer bestimmten Implementierung darstellt, befinden sich in umgekehrter Reihenfolge in der <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> Array. Der aktuelle Zeitraum (die den Zeitraum mit den aktuellen Zeitbereich) ist am Index 0 (null) und für <xref:System.Globalization.Calendar> Klassen, die mehrere Zeiträume unterstützen, jeder nachfolgende Index gibt den vorherigen Zeitraum. Die statische <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType>-Eigenschaft definiert den Index des aktuellen Zeitraums im <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>-Array. Dies ist eine Konstante, die stets den Wert 0 (null) hat. Einzelne <xref:System.Globalization.Calendar>-Klassen beinhalten darüber hinaus auch statische Felder, die den Wert des aktuellen Zeitraums zurückgeben. Sie sind in der folgenden Tabelle aufgeführt.

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

Der Name, der dem Zeitraum mit einer bestimmten Nummer entspricht, kann durch Übergeben der Nummer an die <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>-Methode oder an die <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>-Methode abgerufen werden. Im folgenden Beispiel werden diese Methoden aufgerufen, um Informationen über die Unterstützung von Zeiträumen in der <xref:System.Globalization.GregorianCalendar>-Klasse abzurufen. Es zeigt das Datum des gregorianischen Kalenders, das auf den 1. Januar des zweiten Jahres des aktuellen Zeitraums entspricht, sowie das Datum des gregorianischen Kalenders, das auf den 1. Januar des zweiten Jahres des einzelnen unterstützten japanischen Kalender-Zeitraums entspricht.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Darüber hinaus enthält die benutzerdefinierte Formatzeichenfolge "g" für Datum und Uhrzeit den Namen des Zeitraums eines Kalenders in der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts. Weitere Informationen finden Sie unter [Formatzeichenfolgen benutzerdefinierte Datums- und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiating-a-date-with-an-era"></a>Instanziieren eines Datums mit einem Zeitraum

Für die beiden <xref:System.Globalization.Calendar> Klassen, die mehrere Zeiträume unterstützen, ein Datum, das von einem bestimmten Jahr, Monat, und Tag des Monats Werts besteht aus mehrdeutig sein kann. Z. B. alle Zeiträume, die von unterstützt die <xref:System.Globalization.JapaneseCalendar> Jahre, deren Anzahl 1 ist. Wenn kein Zeitraum angegeben ist, wird daher bei Datums-, Uhrzeit- und Klassenmethoden immer davon ausgegangen, dass die Werte zum aktuellen Zeitraum gehören. Dies gilt für die <xref:System.DateTime.%23ctor%2A> und <xref:System.DateTimeOffset.%23ctor%2A> Konstruktoren, die Parameter des Typs enthalten <xref:System.Globalization.Calendar>, als auch die [JapaneseCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) und [JapaneseLunisolarCalendar.ToDateTime ](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) Methoden. Das folgende Beispiel instanziiert ein Datum, das am 1. Januar des zweiten Jahres eines Zeitabschnitts nicht angegebene darstellt. Wenn Sie das Beispiel ausführen, bei die Reiwa Ära der aktuelle Zeitraum ist, wird das Datum als das zweite Jahr des Zeitraums Reiwa interpretiert. Der Zeitraum, 令和, steht das Jahr in der Zeichenfolge, die vom der <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> Methode und dem 1. Januar 2020., im gregorianischen Kalender entspricht. (Der Zeitraum Reiwa beginnt im Jahr 2019 des gregorianischen Kalenders.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Wenn der Zeitraum geändert wird, wird die Absicht des Codes jedoch nicht eindeutig. Das Datum soll im zweite Jahr des aktuellen Zeitraums darstellen, oder soll er im zweite Jahr des Zeitraums Heisei darstellen? Es gibt zwei Möglichkeiten, diese Mehrdeutigkeit zu vermeiden:

- Instanziieren den Datum und Uhrzeit-Wert, die über das standardmäßige <xref:System.Globalization.GregorianCalendar> Klasse. Sie können dann den japanischen Kalender oder den japanischen Mond-Sonne-Kalender für die Zeichenfolgendarstellung von Datumsangaben, wie im folgenden Beispiel gezeigt verwenden.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Rufen Sie eine Datum und Uhrzeit-Methode, die explizit einen Zeitraum angibt. Dies umfasst die folgenden Methoden:

  - Die <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> Methode der <xref:System.Globalization.JapaneseCalendar> oder <xref:System.Globalization.JapaneseLunisolarCalendar> Klasse.

  - Ein <xref:System.DateTime> oder <xref:System.DateTimeOffset> Analysemethode, z. B. <xref:System.DateTime.Parse%2A>, <xref:System.DateTime.TryParse%2A>, <xref:System.DateTime.ParseExact%2A>, oder <xref:System.DateTime.TryParseExact%2A>, die die zu analysierende Zeichenfolge enthält und optional eine <xref:System.Globalization.DateTimeStyles> Argument, wenn die aktuelle Kultur auf Japanisch-Japan ist (" ja-JP") und Kalenders der Kultur ist die <xref:System.Globalization.JapaneseCalendar>. Die zu analysierende Zeichenfolge muss es sich um den Zeitraum enthalten.

  - Ein <xref:System.DateTime> oder <xref:System.DateTimeOffset> Analysemethode, die enthält eine `provider` Parameter vom Typ <xref:System.IFormatProvider>. `provider` muss eine <xref:System.Globalization.CultureInfo> -Objekt, das die Japanisch-Japan ("ja-JP") Kultur darstellt, dessen aktuellen Kalender <xref:System.Globalization.JapaneseCalendar> oder <xref:System.Globalization.DateTimeFormatInfo> Objekt, dessen <xref:System.Globalization.DateTimeFormatInfo.Calendar> Eigenschaft <xref:System.Globalization.JapaneseCalendar>. Die zu analysierende Zeichenfolge muss es sich um den Zeitraum enthalten.

  Im folgende Beispiel verwendet drei der folgenden Methoden zum Instanziieren einer Datums- und Uhrzeitangabe im Zeitraum Meiji zurück, die auf dem 8. September 1868 begann und endete am 29. Juli 1912.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> Bei der Verwendung von Kalendern, die mehrere Zeiträume unterstützen *immer* der gregorianische Kalender ein Datum zu instanziieren, oder geben Sie den Zeitraum, der beim Instanziieren einer Datums- und Uhrzeitangabe basierend auf diesen Kalender.

Bei Angabe eines Zeitraums auf die <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> -Methode, geben Sie den Index, der den Zeitraum in des im Kalenders <xref:System.Globalization.Calendar.Eras> Eigenschaft. Bei Kalendern, deren Zeiträume geändert werden, sind jedoch diese Indizes nicht konstante Werte; der aktuelle Zeitraum ist bei Index 0, und der älteste Zeitraum am Index `Eras.Length - 1`. Wenn eine neue Ära in einem Kalender hinzugefügt wird, werden die Indizes der vorherigen Zeiträume um eins erhöhen. Sie können den entsprechenden Zeitraum Index wie folgt bereitstellen:

- Verwenden Sie für die Datumsangaben im aktuellen Zeitraum, immer des Kalenders <xref:System.Globalization.Calendar.CurrentEra> Eigenschaft.

- Verwenden Sie für die Daten in einem angegebenen Zeitraum, der <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> Methode, um den Index abzurufen, die einen angegebenen Zeitraum Namen entspricht. Dies erfordert, dass die <xref:System.Globalization.JapaneseCalendar> sein aktuelle Kalender der <xref:System.Globalization.CultureInfo> Objekt, das die Kultur ja-JP darstellt.  (Diese Technik funktioniert für die <xref:System.Globalization.JapaneseLunisolarCalendar> , da sie dieselben Zeiträume als unterstützt die <xref:System.Globalization.JapaneseCalendar>.) Im vorherige Beispiel veranschaulicht diese Vorgehensweise.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Kalender, Zeiträumen und Datumsbereiche: Weniger strengen Prüfungen

Sehr ähnlich wie einzelne Kalender Datumsbereiche, unterstützt haben Zeiträume in der <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> Klassen auch, dass eine unterstützte Bereiche. Bisher wurde für .NET strict Zeitraum, für die Range überprüft, um sicherzustellen, dass ein Era-spezifische Datum innerhalb des Bereichs dieser Ära wurde verwendet. D.h., wenn ein Datum außerhalb des Bereichs des angegebenen Zeitraums ist, löst die Methode eine <xref:System.ArgumentOutOfRangeException>. Derzeit wird .NET verwendet, die bereichsbasierte weniger strengen Überprüfung standardmäßig. Updates für alle Versionen von .NET, gelockerte Zeitraum eingeführt liegen überprüft; der Versuch, ein Datum Era-spezifische zu instanziieren, die außerhalb des Bereichs des angegebenen Zeitraums "führt zu einem Überlauf" in den folgenden Zeitraum aus, und keine Ausnahme ausgelöst wird.

Im folgenden Beispiel wird versucht, ein Datum im Jahr 65. des Zeitraums Showa, zu instanziieren, die auf 25 Dezember 1926 begann und endete am 7. Januar 1989. Dieses Datum entspricht dem 9. Januar 1990, d.h. außerhalb des Bereichs des Zeitraums Showa in die <xref:System.Globalization.JapaneseCalendar>. Wie die Ausgabe im Beispiel wird veranschaulicht, ist das Datum angezeigt, die im Beispiel am 9. Januar 1990 im zweiten Jahr im Heisei Zeitraum zurück.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Wenn weniger strengen Prüfungen nicht erwünscht sind, können Sie strengen Prüfungen in eine Reihe von Möglichkeiten, je nach Version von .NET wiederherstellen, auf denen Ihre Anwendung ausgeführt wird:

- **.NET Core:** Fügen Sie den folgenden können Sie die *. netcore.runtime.json* Config-Datei:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Sie können die folgende AppContext-Option festlegen:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Sie können den folgenden Registrierungswert festlegen:

  |  |  |
  |--|--|
  |Key | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
  |Name | Switch.System.Globalization.EnforceJapaneseEraYearRanges |
  |Typ | REG_SZ |
  |Wert | 1 |

Mit strengen Prüfungen aktiviert, die im vorherige Beispiel löst eine <xref:System.ArgumentOutOfRangeException> und zeigt die folgende Ausgabe:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="representing-dates-in-calendars-with-multiple-eras"></a>Darstellen von Datumsangaben in Kalendern mit Zeiträumen von mehreren

Wenn ein <xref:System.Globalization.Calendar>-Objekt Zeiträume unterstützt und es sich um den aktuellen Kalender eines <xref:System.Globalization.CultureInfo>-Objekts handelt, beinhalten die Zeichenfolgendarstellungen für die Muster vollständiges Datum und Uhrzeit, langes Datum und kurzes Datum auch den Zeitraum des Datums- und Uhrzeitwerts. Das folgende Beispiel zeigt diese Datumsmuster, wenn die aktuelle Kultur auf Japan (japanisch) festgelegt und als aktueller Kalender der japanische Kalender angegeben ist.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> Die <xref:System.Globalization.JapaneseCalendar> -Klasse ist die einzige Kalenderklasse in .NET, die beide unterstützt Datumsangaben in mehr als ein Zeitraum und die den aktuellen Kalender können eine <xref:System.Globalization.CultureInfo> Objekt - genauer gesagt, eines eine <xref:System.Globalization.CultureInfo> -Objekt, das die Kultur für Japanisch (Japan) darstellt.

Bei allen Kalendern enthält der benutzerdefinierte Formatbezeichner "g" auch den Zeitraum in der Ergebniszeichenfolge. Das folgende Beispiel verwendet die benutzerdefinierte Formatzeichenfolge "MM-DD-yyyy g", um den Zeitraum in der Ergebniszeichenfolge anzuzeigen, wenn als aktueller Kalender der gregorianische Kalender festgelegt ist.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

In Fällen, in denen die Zeichenfolgendarstellung eines Datums in einem Kalender ausgedrückt wird, der nicht der aktuelle Kalender ist, beinhaltet die <xref:System.Globalization.Calendar>-Klasse eine <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>-Methode, die zusammen mit den Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> verwendet werden kann, um ein Datum eindeutig zusammen mit dem Zeitraum anzugeben, zu dem es gehört. Im folgenden Beispiel wird dies anhand der <xref:System.Globalization.JapaneseLunisolarCalendar>-Klasse veranschaulicht. Beachten Sie jedoch, dass Sie ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt instanziieren und <xref:System.Globalization.JapaneseCalendar> als dessen aktuellen Kalender festlegen müssen, wenn Sie in der Ergebniszeichenfolge anstelle einer Zahl einen aussagekräftigen Namen oder eine Abkürzung für den Zeitraum anzeigen möchten. (Der <xref:System.Globalization.JapaneseLunisolarCalendar>-Kalender kann nicht als aktueller Kalender einer Kultur festgelegt werden, in diesem Fall teilen sich aber zwei Kalender dieselben Zeiträume.

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

In der japanischen Kalender wird im erste Jahr eines Zeitabschnitts Gannen (元年) aufgerufen. Beispielsweise kann anstelle von Heisei-1, im erste Jahr des Zeitraums Heisei als Heisei Gannen beschrieben werden. .NET übernimmt diese Konvention bei Formatierungsvorgängen für Datumsangaben und Zeiten formatiert mit dem folgenden standardmäßigen oder benutzerdefinierten Datums- und Uhrzeitformat Zeichenfolgen bei Verwendung mit einem <xref:System.Globalization.CultureInfo> Objekt, das die Kultur Japanisch-Japan ("ja-JP"), mit der darstellt.<xref:System.Globalization.JapaneseCalendar> Klasse:

- [Das lange Datumsmuster](../base-types/standard-date-and-time-format-strings.md#LongDate), durch die "D" für Datum und Uhrzeit-Formatzeichenfolge gekennzeichnet.
- [Das vollständige Datum, lange Zeit Muster](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), durch die "F" für Datum und Uhrzeit-Formatzeichenfolge gekennzeichnet.
- [Das vollständige Datumsmuster für kurze Zeit](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), durch die "f" für Datum und Uhrzeit-Formatzeichenfolge gekennzeichnet.
- [Das Jahr-Monat-Muster](../base-types/standard-date-and-time-format-strings.md#YearMonth), gekennzeichnet durch die Y "oder"y"Standardformatbezeichner für Datum und Zeit, die Zeichenfolge formatieren.
- [Die "Ggy '年'" oder "Ggy年" [Formatzeichenfolge für Datum und Uhrzeit](../base-types/custom-date-and-time-format-strings.md).

Z. B. das folgende Beispiel zeigt ein Datum im ersten Jahr des Zeitraums Heisei in die <xref:System.Globalization.JapaneseCalendar> .

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Wenn dieses Verhalten bei Formatierungsvorgängen nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen steht immer im erste Jahr eines Zeitabschnitts als "1" statt "Gannen", wie folgt, abhängig von der Version von .NET:

- **.NET Core:** Fügen Sie den folgenden können Sie die *. netcore.runtime.json* Config-Datei:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Sie können die folgende AppContext-Option festlegen:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Sie können den folgenden Registrierungswert festlegen:

  |  |  |
  |--|--|
  |Key | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
  |Name | Switch.System.Globalization.FormatJapaneseFirstYearAsANumber |
  |Typ | REG_SZ |
  |Wert | 1 |

Dank der Unterstützung bei Formatierungsvorgängen deaktiviert Gannen zeigt die im vorherige Beispiel die folgende Ausgabe:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET wurde auch aktualisiert, damit ein Datums- und uhrzeitanalyse Vorgänge Zeichenfolgen, die das Jahr als "1" oder Gannen dargestellt enthalten. Obwohl Sie nicht möchten, benötigen sollte, können Sie das vorherige Verhalten, die nur "1" erkennt, wie im ersten Jahr eines Zeitabschnitts wiederherstellen. Sie können wie folgt, und abhängig von der Version von .NET dazu:

- **.NET Core:** Fügen Sie den folgenden können Sie die *. netcore.runtime.json* Config-Datei:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Sie können die folgende AppContext-Option festlegen:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Sie können den folgenden Registrierungswert festlegen:

  |  |  |
  |--|--|
  |Key | HKEY_LOCAL_MACHINE\Software\Microsoft.NETFramework\AppContext |
  |Name | Switch.System.Globalization.EnforceLegacyJapaneseDateParsing |
  |Typ | REG_SZ |
  |Wert | 1 |

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Beispiel: Kalender-Woche-Bereich-Hilfsprogramm](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Calendar-Klasse](xref:System.Globalization.Calendar)
