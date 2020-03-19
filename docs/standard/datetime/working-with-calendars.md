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
ms.openlocfilehash: de8e5a03c769a22f3320c7785706555898bf8c1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401232"
---
# <a name="work-with-calendars"></a>Arbeiten mit Kalendern

Obwohl ein Datums- und Uhrzeitwert eine universale zeitliche Angabe darstellt, ist die Zeichenfolgendarstellung eines solchen Werts kulturabhängig. Sie wird sowohl durch die Anzeigekonventionen für Datums- und Uhrzeitwerte einer bestimmten Kultur als auch durch den Kalender bestimmt, der in der jeweiligen Kultur verwendet wird. In diesem Thema wird die Unterstützung für Kalender in .NET behandelt und die Verwendung der Kalenderklassen beim Arbeiten mit Datumswerten erläutert.

## <a name="calendars-in-net"></a>Kalender in .NET

Alle Kalender in .NET leiten <xref:System.Globalization.Calendar?displayProperty=nameWithType> sich von der Klasse ab, die die Basiskalenderimplementierung bereitstellt. Eine der Klassen, die von der <xref:System.Globalization.Calendar>-Klasse erbt, ist die <xref:System.Globalization.EastAsianLunisolarCalendar>-Klasse. Dies ist die Basisklasse für alle Mond-Sonne-Kalender. .NET enthält die folgenden Kalenderimplementierungen:

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

- Als Kalender, der von einer bestimmten Kultur verwendet wird. Jedes <xref:System.Globalization.CultureInfo>-Objekt verfügt über einen aktuellen Kalender. Dies ist der Kalender, den das Objekt gegenwärtig verwendet. Die Zeichenfolgendarstellungen aller Datums- und Uhrzeitwerte entsprechen automatisch der aktuellen Kultur und dem aktuellen Kalender. In der Regel ist als aktueller Kalender der Standardkalender der Kultur angegeben. <xref:System.Globalization.CultureInfo>Objekte verfügen auch über optionale Kalender, die zusätzliche Kalender enthalten, die von der Kultur verwendet werden können.

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

## <a name="dates-and-calendars"></a>Termine und Kalender

Mit Ausnahme der Konstruktoren, die einen Parameter des Typs <xref:System.Globalization.Calendar> beinhalten und die es gestatten, die Elemente eines Datums (d. h. Monat, Tag und Jahr) in den Werten eines bestimmten Kalenders anzuzeigen, basieren die Werte <xref:System.DateTime> und <xref:System.DateTimeOffset> immer auf dem gregorianischen Kalender. Dies bedeutet, dass die <xref:System.DateTime.Year%2A?displayProperty=nameWithType>-Eigenschaft immer das Jahr und die <xref:System.DateTime.Day%2A?displayProperty=nameWithType>-Eigenschaft immer den Monat im gregorianischen Kalender zurückgibt.

> [!IMPORTANT]
> Es ist wichtig zu beachten, dass zwischen dem Datumswert und der entsprechenden Zeichenfolgendarstellung ein Unterschied besteht. Der erste Wert basiert auf dem gregorianischen Kalender, während der zweite Wert auf dem aktuellen Kalender einer bestimmten Kultur basiert.

Das folgende Beispiel veranschaulicht diesen Unterschied zwischen den <xref:System.DateTime>-Eigenschaften und den entsprechenden <xref:System.Globalization.Calendar>-Methoden. Im Beispiel ist die aktuelle Kultur Arabisch (Ägypten), und der aktuelle Kalender ist Umm al-Qura. Ein <xref:System.DateTime>-Wert wird auf den 15. Tag im 7. Monat des Jahres 2011 festgelegt. Es ist klar, dass diese Werte als gregorianisches Datum interpretiert werden, da die <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode die gleichen Werte zurückgibt, wenn die Konventionen der invarianten Kultur verwendet werden. Die Zeichenfolgendarstellung des Datums, die gemäß den Konventionen der aktuellen Kultur formatiert wird, ist 14/08/32. Dies ist das entsprechende Datum im Umm al-Qura-Kalender. Anschließend werden Member von `DateTime` und `Calendar` verwendet, um den Tag, den Monat und das Jahr des <xref:System.DateTime>-Werts zurückzugeben. In allen Fällen entsprechen die von <xref:System.DateTime>-Membern zurückgegebenen Werte den Werten im gregorianischen Kalender, während die von <xref:System.Globalization.UmAlQuraCalendar>-Membern zurückgegebenen Werte dem Umm al-Qura-Kalender entsprechen.

[!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
[!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]

### <a name="instantiate-dates-based-on-a-calendar"></a>Instanziieren von Datumsangaben basierend auf einem Kalender

Da <xref:System.DateTime>-Werte und <xref:System.DateTimeOffset>-Werte auf dem gregorianischen Kalender basieren, müssen Sie einen überladenen Konstruktor aufrufen, der einen Parameter vom Typ <xref:System.Globalization.Calendar> beinhaltet, wenn Sie einen Datumswert instanziieren möchten, der Tag, Monat und Jahr eines anderen Kalenders verwenden soll. Sie können auch eine der Überladungen der <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType>-Methode eines bestimmten Kalenders aufrufen, um ein <xref:System.DateTime>-Objekt auf Grundlage der Werte eines bestimmten Kalender zu instanziieren.

Im folgenden Codebeispiel wird ein <xref:System.DateTime>-Wert instanziiert, indem ein <xref:System.Globalization.HebrewCalendar>-Objekt an einen <xref:System.DateTime> Konstruktor übergeben wird. Anschließend wird ein zweiter <xref:System.DateTime>-Wert durch Aufrufen der <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>-Methode instanziiert. Da die beiden Werte mit identischen Werten aus dem hebräischen Kalender erstellt wurden, zeigt ein Aufruf der <xref:System.DateTime.Equals%2A?displayProperty=nameWithType>-Methode, dass beide <xref:System.DateTime>-Werte gleich sind.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="represent-dates-in-the-current-calendar"></a>Datumsangaben im aktuellen Kalender darstellen

Formatierungsmethoden für Datum und Uhrzeit verwenden immer den aktuellen Kalender, wenn Datumsangaben in Zeichenfolgen konvertiert werden sollen. Das heißt, dass die Zeichenfolgendarstellungen für Jahr, Monat und Tag des Monats denen des aktuellen Kalenders entsprechen und nicht notwendigerweise dem gregorianischen Kalender folgen.

Im folgenden Beispiel wird gezeigt, welchen Einfluss der aktuelle Kalender auf die Zeichenfolgendarstellung eines Datums hat. Im Beispiel wird die aktuelle Kultur auf Chinesisch (traditionell, Taiwan) festgelegt und ein Datumswert instanziiert. Anschließend werden der aktuelle Kalender und das Datum angezeigt, der aktuelle Kalender wird in <xref:System.Globalization.TaiwanCalendar> geändert, und Kalender und Datum werden erneut angezeigt. Der erste angezeigte Datumswert verwendet die Darstellung des gregorianischen Kalenders. Der zweite Datumswert wird im Format des taiwanesischen Kalenders dargestellt.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="represent-dates-in-a-non-current-calendar"></a>Darstellen von Datumsangaben in einem nicht aktuellen Kalender

Um ein Datum unter Verwendung eines anderen als des aktuellen Kalenders einer bestimmten Kultur darzustellen, müssen Sie Methoden des gewünschten <xref:System.Globalization.Calendar>-Objekts aufrufen. Zum Beispiel konvertieren die Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> das Jahr, den Monat und den Tag in die Darstellung eines bestimmten Kalenders.

> [!WARNING]
> Da einige Kalender nicht als optionale Kalender für eine Kultur definiert sind, erfordert die Darstellung von Datumsangaben mit diesen Kalendern stets einen Aufruf der Methoden des entsprechenden Kalenders. Dies gilt für alle Kalender, die von den Klassen <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> und <xref:System.Globalization.PersianCalendar> abgeleitet sind.

Im folgenden Beispiel wird ein <xref:System.Globalization.JulianCalendar>-Objekt verwendet, um ein Datum (9. Januar 1905) im julianischen Kalender zu instanziieren. Wenn dieses Datum mit dem gregorianischen Standardkalender dargestellt wird, wird es als 22. Januar 1905 angezeigt. Aufrufe einzelner <xref:System.Globalization.JulianCalendar>-Methoden ermöglichen eine Darstellung des Datums mit dem julianischen Kalender.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Kalender und Datumsbereiche

Das früheste Datum, das von einem Kalender unterstützt wird, wird durch die <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Eigenschaft dieses Kalenders angegeben. Für die <xref:System.Globalization.GregorianCalendar>-Klasse ist dieses Datum der 1. Januar 0001 unserer Zeitrechnung. Die meisten anderen Kalender in .NET unterstützen ein späteres Datum. Der Versuch, mit einem Datums- und Zeitwert zu arbeiten, der vor dem frühesten unterstützten Datum eines Kalenders liegt, löst eine <xref:System.ArgumentOutOfRangeException> Ausnahme aus.

Es gibt jedoch eine wichtige Ausnahme. Der (nicht initialisierte) Standardwert eines <xref:System.DateTime>-Objekts und eines <xref:System.DateTimeOffset>-Objekts ist gleich dem <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>-Wert. Wenn Sie versuchen, dieses Datum in einem Kalender zu formatieren, der den 1. Januar 0001 C.E. nicht unterstützt. und Sie stellen keinen Formatbezeichner bereit, die Formatierungsmethode verwendet den Formatbezeichner "s" (sortable date/time pattern) anstelle des Formatbezeichners "G" (allgemeines Datums-/Uhrzeitmuster). In der Folge löst der Formatierungsvorgang keine <xref:System.ArgumentOutOfRangeException>-Ausnahme aus. Stattdessen wird das nicht unterstützte Datum zurückgegeben. Dies wird im folgenden Beispiel veranschaulicht. Der Wert von <xref:System.DateTime.MinValue?displayProperty=nameWithType> wird anzeigt, wenn die aktuelle Kultur auf Japanisch (Japan) mit dem japanischen Kalender und in Arabisch (Ägypten) mit dem Um Al Qura-Kalender festgelegt wird. Außerdem wird die aktuelle Kultur auf Englisch (USA) festgelegt die <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>-Methode mit jedem dieser <xref:System.Globalization.CultureInfo>-Objekte aufgerufen. In jedem Fall wird das Datum mithilfe des sortierbaren Datums-/Zeitmusters angezeigt.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="work-with-eras"></a>Arbeiten mit Epochen

Kalender unterteilen Datumsangaben in der Regel in Zeiträume. Die <xref:System.Globalization.Calendar> Klassen in .NET unterstützen jedoch nicht jede Ära, die <xref:System.Globalization.Calendar> durch einen Kalender definiert ist, und die meisten Klassen unterstützen nur eine einzige Ära. Nur die Klassen <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> unterstützen mehrere Zeiträume.

> [!IMPORTANT]
> Die Reiwa-Ära, eine neue <xref:System.Globalization.JapaneseCalendar> Ära <xref:System.Globalization.JapaneseLunisolarCalendar>in der und , beginnt am 1. Mai 2019. Diese Änderung betrifft alle Anwendungen, die diese Kalender verwenden. Weitere Informationen finden Sie in den folgenden Artikeln:
>
> - [Verarbeiten einer neuen Ära im japanischen Kalender in .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), in der Features dokumentiert werden, die .NET hinzugefügt wurden, um Kalender mit mehreren Epochen zu unterstützen, und bewährte Methoden für die Behandlung von Kalendern mit mehreren Epochen erläutert.
> - [Bereiten Sie Ihre Anwendung auf die japanische Ära Änderung](/windows/uwp/design/globalizing/japanese-era-change)vor, die Informationen zum Testen Ihrer Anwendungen unter Windows bereitstellt, um sicherzustellen, dass ihre Bereitschaft für die Änderung der Ära.
> - [Zusammenfassung der neuen japanischen Ära-Updates für .NET Framework](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework), die .NET Framework-Updates für einzelne Windows-Versionen auflistet, die sich auf die neue japanische Kalenderära beziehen, neue .NET Framework-Features für die Unterstützung mehrerer Epochen notiert und Dinge enthält, nach denen Beim Testen Ihrer Anwendungen gesucht werden muss.

Eine Ära in den meisten Kalendern bezeichnet einen extrem langen Zeitraum. Im Gregorianischen Kalender zum Beispiel erstreckt sich die aktuelle Ära über mehr als zwei Jahrtausende. Für <xref:System.Globalization.JapaneseCalendar> die <xref:System.Globalization.JapaneseLunisolarCalendar>und die , die beiden Kalender, die mehrere Epochen unterstützen, ist dies nicht der Fall. Eine Ära entspricht der Zeit der Herrschaft eines Kaisers. Die Unterstützung mehrerer Epochen, insbesondere wenn die Obergrenze der aktuellen Ära unbekannt ist, stellt besondere Herausforderungen dar.

### <a name="eras-and-era-names"></a>Epochen und Epochennamen

In .NET werden ganze Zahlen, die die von einer bestimmten Kalenderimplementierung <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> unterstützten Epochen darstellen, in umgekehrter Reihenfolge im Array gespeichert. Die aktuelle Ära (die Ära mit dem letzten Zeitbereich) liegt <xref:System.Globalization.Calendar> bei Index Null, und für Klassen, die mehrere Epochen unterstützen, spiegelt jeder aufeinanderfolgende Index die vorherige Ära wider. Die statische <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType>-Eigenschaft definiert den Index des aktuellen Zeitraums im <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>-Array. Dies ist eine Konstante, die stets den Wert 0 (null) hat. Einzelne <xref:System.Globalization.Calendar>-Klassen beinhalten darüber hinaus auch statische Felder, die den Wert des aktuellen Zeitraums zurückgeben. Sie sind in der folgenden Tabelle aufgeführt.

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

Der Name, der dem Zeitraum mit einer bestimmten Nummer entspricht, kann durch Übergeben der Nummer an die <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>-Methode oder an die <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>-Methode abgerufen werden. Im folgenden Beispiel werden diese Methoden aufgerufen, um Informationen über die Unterstützung von Zeiträumen in der <xref:System.Globalization.GregorianCalendar>-Klasse abzurufen. Es zeigt das gregorianische Kalenderdatum an, das dem 1. Januar des zweiten Jahres der aktuellen Ära entspricht, sowie das Gregorianische Kalenderdatum, das dem 1. Januar des zweiten Jahres jedes unterstützten japanischen Kalenders entspricht.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Darüber hinaus enthält die benutzerdefinierte Formatzeichenfolge "g" für Datum und Uhrzeit den Namen des Zeitraums eines Kalenders in der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts. Weitere Informationen finden Sie unter [Benutzerdefinierte Datums- und Uhrzeitformatzeichenfolgen](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiatie-a-date-with-an-era"></a>Instantiatie ein Datum mit einer Ära

Für die <xref:System.Globalization.Calendar> beiden Klassen, die mehrere Epochen unterstützen, kann ein Datum, das aus einem bestimmten Jahr, Monat und Tag des Monatswerts besteht, mehrdeutig sein. Zum Beispiel haben alle Epochen, die von den <xref:System.Globalization.JapaneseCalendar> unterstützt werden, Jahre, deren Anzahl 1 ist. Wenn kein Zeitraum angegeben ist, wird daher bei Datums-, Uhrzeit- und Klassenmethoden immer davon ausgegangen, dass die Werte zum aktuellen Zeitraum gehören. Dies gilt <xref:System.DateTime.%23ctor%2A> für <xref:System.DateTimeOffset.%23ctor%2A> die und-Konstruktoren, die Parameter vom Typ <xref:System.Globalization.Calendar>enthalten, sowie für die Methoden [JapaneseCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) und [JapaneseLunisolarCalendar.ToDateTime.](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) Im folgenden Beispiel wird ein Datum instanziiert, das den 1. Januar des zweiten Jahres einer nicht angegebenen Ära darstellt. Wenn Sie das Beispiel ausführen, wenn die Reiwa-Ära die aktuelle Ära ist, wird das Datum als das zweite Jahr der Reiwa-Ära interpretiert. Die Ära , , , geht dem Jahr in <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> der Zeichenfolge voraus, die von der Methode zurückgegeben wird und entspricht dem 1. Januar 2020, im Gregorianischen Kalender. (Die Reiwa-Ära beginnt im Jahr 2019 des Gregorianischen Kalenders.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Wenn sich die Ära jedoch ändert, wird die Absicht dieses Codes mehrdeutig. Ist das Datum für das zweite Jahr der gegenwärtigen Ära gedacht, oder ist es beabsichtigt, das zweite Jahr der Heisei-Ära darzustellen? Es gibt zwei Möglichkeiten, diese Mehrdeutigkeit zu vermeiden:

- Instanziieren Sie den Datums- <xref:System.Globalization.GregorianCalendar> und Uhrzeitwert mithilfe der Standardklasse. Sie können dann den japanischen Kalender oder den japanischen Lunisolar-Kalender für die Zeichenfolgendarstellung von Datumsangaben verwenden, wie das folgende Beispiel zeigt.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Rufen Sie eine Datums- und Uhrzeitmethode auf, die explizit eine Ära angibt. Dazu gehören folgende Methoden:

  - Die <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> Methode <xref:System.Globalization.JapaneseCalendar> der <xref:System.Globalization.JapaneseLunisolarCalendar> oder-Klasse.

  - Eine <xref:System.DateTime> <xref:System.DateTimeOffset> oder Analysemethode, <xref:System.DateTime.Parse%2A>z. B. <xref:System.DateTime.TryParse%2A>, , <xref:System.DateTime.ParseExact%2A>oder <xref:System.DateTime.TryParseExact%2A>, die die <xref:System.Globalization.DateTimeStyles> zu analysierende Zeichenfolge und optional ein Argument enthält, wenn die aktuelle <xref:System.Globalization.JapaneseCalendar>Kultur Japanisch-Japan ("ja-JP") ist und der Kalender dieser Kultur der ist. Die zu analysierende Zeichenfolge muss die Ära enthalten.

  - Eine <xref:System.DateTime> <xref:System.DateTimeOffset> oder Analysemethode, `provider` die einen <xref:System.IFormatProvider>Parameter vom Typ enthält. `provider`muss entweder <xref:System.Globalization.CultureInfo> ein Objekt sein, das die japanisch-japanische Kultur ("ja-JP") darstellt, deren aktueller Kalender <xref:System.Globalization.JapaneseCalendar> ist, oder <xref:System.Globalization.DateTimeFormatInfo> ein Objekt, dessen <xref:System.Globalization.DateTimeFormatInfo.Calendar> Eigenschaft ist. <xref:System.Globalization.JapaneseCalendar> Die zu analysierende Zeichenfolge muss die Ära enthalten.

  Im folgenden Beispiel werden drei dieser Methoden verwendet, um ein Datum und eine Uhrzeit in der Meiji-Ära zu instanziieren, die am 8. September 1868 begann und am 29. Juli 1912 endete.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> Wenn Sie mit Kalendern arbeiten, die mehrere Epochen unterstützen, verwenden Sie *immer* das Gregorianische Datum, um ein Datum zu instanziieren, oder geben Sie das Zeitprogramm an, wenn Sie ein Datum und eine Uhrzeit basierend auf diesem Kalender instanziieren.

Wenn Sie eine Ära <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> für die Methode angeben, geben Sie den <xref:System.Globalization.Calendar.Eras> Index der Ära in der Eigenschaft des Kalenders an. Bei Kalendern, deren Epochen sich ändern können, sind diese Indizes jedoch keine konstanten Werte; die aktuelle Ära liegt bei Index 0, und `Eras.Length - 1`die älteste Ära ist bei Index . Wenn einem Kalender eine neue Ära hinzugefügt wird, werden die Indizes der vorherigen Epochen um eins erhöht. Sie können den entsprechenden Äraindex wie folgt bereitstellen:

- Verwenden Sie für Datumsangaben im aktuellen <xref:System.Globalization.Calendar.CurrentEra> Zeitraum immer die Eigenschaft des Kalenders.

- Verwenden Sie für Datumsangaben <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> in einem angegebenen Zeitraum die Methode, um den Index abzurufen, der einem angegebenen Namen aus der Zeit entspricht. Dies erfordert, dass der <xref:System.Globalization.JapaneseCalendar> <xref:System.Globalization.CultureInfo> aktuelle Kalender des Objekts, das die ja-JP-Kultur darstellt, sein muss.  (Diese Technik funktioniert <xref:System.Globalization.JapaneseLunisolarCalendar> auch für die, da sie <xref:System.Globalization.JapaneseCalendar>die gleichen Epochen wie die unterstützt .) Das vorherige Beispiel veranschaulicht diesen Ansatz.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Kalender, Epochen und Datumsbereiche: Entspannte Bereichsprüfungen

Ähnlich wie einzelne Kalender Datumsbereiche unterstützt haben, haben Epochen in der <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar> Klassen auch Bereiche unterstützt. Zuvor verwendete .NET strenge Bereichsprüfungen, um sicherzustellen, dass ein zeitspezifisches Datum im Bereich dieses Epochen lag. Das heißt, wenn ein Datum außerhalb des Bereichs des angegebenen <xref:System.ArgumentOutOfRangeException>Zeitraums liegt, löst die Methode eine aus. Derzeit verwendet .NET standardmäßig eine entspannte Bereichsprüfung. Aktualisierungen aller Versionen von .NET führten zu einer entspannten Überprüfung des Bereichs der Ära. der Versuch, ein zeitspezifisches Datum zu instanziieren, das außerhalb des Bereichs der angegebenen Ära "Überläufe" in die folgende Ära liegt, und es wird keine Ausnahme ausgelöst.

Im folgenden Beispiel wird versucht, ein Datum im 65. Jahr der Showa-Ära zu instanziieren, das am 25. Dezember 1926 begann und am 7. Januar 1989 endete. Dieses Datum entspricht dem 9. Januar 1990, der außerhalb des <xref:System.Globalization.JapaneseCalendar>Bereichs der Showa-Ära in der liegt. Wie die Ausgabe des Beispiels zeigt, ist das Datum, das das Beispiel zeigt, der 9. Januar 1990, im zweiten Jahr der Heisei-Ära.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Wenn entspannte Bereichsprüfungen nicht wünschenswert sind, können Sie strenge Bereichsprüfungen auf verschiedene Arten wiederherstellen, abhängig von der Version von .NET, auf der Ihre Anwendung ausgeführt wird:

- **.NET Kern:** Fügen Sie der *Konfigurationsdatei .netcore.runtime.json* Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Legen Sie den folgenden AppContext-Schalter in der *Datei app.config* fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungswert fest:

   |  |  |
   |--|--|
   | **Schlüssel** | **HKEY_LOCAL_MACHINE-Software-Microsoft\\. NETFramework-AppContext** |
   | **Name** | Switch.System.Globalization.EnforceJapaneseEraYearRanges |
   | **Typ** | REG_SZ |
   | **Wert** | true |

Wenn strenge Bereichsprüfungen aktiviert sind, <xref:System.ArgumentOutOfRangeException> wird im vorherigen Beispiel eine ausgegeben und die folgende Ausgabe angezeigt:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="represent-dates-in-calendars-with-multiple-eras"></a>Stellen Sie Datumsangaben in Kalendern mit mehreren Epochen dar

Wenn ein <xref:System.Globalization.Calendar>-Objekt Zeiträume unterstützt und es sich um den aktuellen Kalender eines <xref:System.Globalization.CultureInfo>-Objekts handelt, beinhalten die Zeichenfolgendarstellungen für die Muster vollständiges Datum und Uhrzeit, langes Datum und kurzes Datum auch den Zeitraum des Datums- und Uhrzeitwerts. Das folgende Beispiel zeigt diese Datumsmuster, wenn die aktuelle Kultur auf Japan (japanisch) festgelegt und als aktueller Kalender der japanische Kalender angegeben ist.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> Die <xref:System.Globalization.JapaneseCalendar> Klasse ist die einzige Kalenderklasse in .NET, die beide Datumsangaben in <xref:System.Globalization.CultureInfo> mehr als einer <xref:System.Globalization.CultureInfo> Ära unterstützt und der aktuelle Kalender eines Objekts sein kann , insbesondere eines Objekts, das die japanische (Japanische) Kultur darstellt.

Bei allen Kalendern enthält der benutzerdefinierte Formatbezeichner "g" auch den Zeitraum in der Ergebniszeichenfolge. Das folgende Beispiel verwendet die benutzerdefinierte Formatzeichenfolge "MM-DD-yyyy g", um den Zeitraum in der Ergebniszeichenfolge anzuzeigen, wenn als aktueller Kalender der gregorianische Kalender festgelegt ist.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

In Fällen, in denen die Zeichenfolgendarstellung eines Datums in einem Kalender ausgedrückt wird, der nicht der aktuelle Kalender ist, beinhaltet die <xref:System.Globalization.Calendar>-Klasse eine <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType>-Methode, die zusammen mit den Methoden <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> und <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> verwendet werden kann, um ein Datum eindeutig zusammen mit dem Zeitraum anzugeben, zu dem es gehört. Im folgenden Beispiel wird dies anhand der <xref:System.Globalization.JapaneseLunisolarCalendar>-Klasse veranschaulicht. Beachten Sie jedoch, dass Sie ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt instanziieren und <xref:System.Globalization.JapaneseCalendar> als dessen aktuellen Kalender festlegen müssen, wenn Sie in der Ergebniszeichenfolge anstelle einer Zahl einen aussagekräftigen Namen oder eine Abkürzung für den Zeitraum anzeigen möchten. (Der <xref:System.Globalization.JapaneseLunisolarCalendar>-Kalender kann nicht als aktueller Kalender einer Kultur festgelegt werden, in diesem Fall teilen sich aber zwei Kalender dieselben Zeiträume.

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

In den japanischen Kalendern wird das erste Jahr einer Ära Gannen () genannt. Anstelle von Heisei 1 kann beispielsweise das erste Jahr der Heisei-Ära als Heisei Gannen bezeichnet werden. .NET übernimmt diese Konvention bei Formatierungsvorgängen für Datums- und Uhrzeitangaben, die <xref:System.Globalization.CultureInfo> mit den folgenden Standard- oder benutzerdefinierten Datums- <xref:System.Globalization.JapaneseCalendar> und Uhrzeitformatzeichenfolgen formatiert sind, wenn sie mit einem Objekt verwendet werden, das die japanisch-japanische Kultur ("ja-JP") mit der Klasse darstellt:

- [Das lange Datumsmuster](../base-types/standard-date-and-time-format-strings.md#LongDate), angegeben durch die Zeichenfolge "D" für Datums- und Uhrzeitformate.
- [Das vollständige Datums-Long-Time-Muster](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime), angegeben durch die Zeichenfolge "F" für Datums- und Zeitformat.
- [Das vollständige Datums-Kurzzeitmuster](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime), angegeben durch die Zeichenfolge "f" standard datums- und zeitformat.
- [Das Jahres-/Monatsmuster](../base-types/standard-date-and-time-format-strings.md#YearMonth), angegeben durch die Zeichenfolge Y" oder "y" Standarddatums- und -zeitformat.
- [Die [benutzerdefinierte Datums- und Zeitformatzeichenfolge](../base-types/custom-date-and-time-format-strings.md)"ggy'" oder "ggy".

Im folgenden Beispiel wird z. B. ein Datum im ersten <xref:System.Globalization.JapaneseCalendar>Jahr der Heisei-Ära im angezeigt.

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Wenn dieses Verhalten bei Formatierungsvorgängen unerwünscht ist, können Sie das vorherige Verhalten wiederherstellen, das immer das erste Jahr einer Ära als "1" und nicht als "Gannen" darstellt, indem Sie die folgenden Aktionen ausführen, abhängig von der Version von .NET:

- **.NET Kern:** Fügen Sie der *Konfigurationsdatei .netcore.runtime.json* Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Legen Sie den folgenden AppContext-Schalter in der *Datei app.config* fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungswert fest:

   |  |  |
   |--|--|
   | **Schlüssel** | **HKEY_LOCAL_MACHINE-Software-Microsoft\\. NETFramework-AppContext** |
   | **Name** | Switch.System.Globalization.FormatJapaneseFirstYearasANumber |
   | **Typ** | REG_SZ |
   | **Wert** | true |

Wenn die gannen-Unterstützung bei formatierenden Vorgängen deaktiviert ist, wird im vorherigen Beispiel die folgende Ausgabe angezeigt:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET wurde ebenfalls aktualisiert, sodass Datums- und Uhrzeitanalysevorgänge Zeichenfolgen unterstützen, die das Als "1" oder "Gannen" dargestellte Jahr enthalten. Obwohl Sie dies nicht tun sollten, können Sie das vorherige Verhalten wiederherstellen, um nur "1" als erstes Jahr einer Ära zu erkennen. Je nach Version von .NET können Sie dies wie folgt tun:

- **.NET Kern:** Fügen Sie der *Konfigurationsdatei .netcore.runtime.json* Folgendes hinzu:

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET Framework 4.6 oder höher:** Legen Sie den folgenden AppContext-Schalter in der *Datei app.config* fest:

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 oder früher:** Legen Sie den folgenden Registrierungswert fest:

   |  |  |
   |--|--|
   | **Schlüssel** | **HKEY_LOCAL_MACHINE-Software-Microsoft\\. NETFramework-AppContext** |
   | **Name** | Switch.System.Globalization.EnforceLegacyJapaneseDateParsing |
   | **Typ** | REG_SZ |
   | **Wert** | true |

## <a name="see-also"></a>Weitere Informationen

- [Gewusst wie: Anzeigen von Datumsangaben in nicht-gregorianischen Kalendern](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Beispiel: Dienstprogramm für den Kalenderwochenbereich](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Kalenderklasse](xref:System.Globalization.Calendar)
