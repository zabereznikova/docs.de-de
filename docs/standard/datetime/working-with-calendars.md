---
title: Arbeiten mit Kalendern
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET Framework], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET Framework], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b116944a45546604d1d60a5a44afcce8fee2f026
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721514"
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
>  Am 1. Mai 2019 beginnt ein neuer Zeitabschnitt im <xref:System.Globalization.JapaneseCalendar> und <xref:System.Globalization.JapaneseLunisolarCalendar>. Diese Änderung betrifft alle Anwendungen, die diese Kalender verwenden. Unter [Handling a new era in the Japanese calendar in .NET (Umgang mit einem neuen Zeitabschnitt im japanischen Kalender in .NET)](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/) finden Sie weiter Informationen und wie Sie bestimmen können, ob Ihre Anwendungen ebenfalls betroffen sind. Finden Sie unter [Vorbereiten Ihrer Anwendung auf die japanischen Zeitraum Änderung](/windows/uwp/design/globalizing/japanese-era-change) Informationen zum Testen von Anwendungen auf Windows, um sicherzustellen, dass deren Bereitschaft für den Zeitraum ändern.

### <a name="eras-and-era-names"></a>Zeiträume und Namen

In .NET Ganzzahlen, das die Zeiträume unterstützt bei einer bestimmten Implementierung darstellt, befinden sich in umgekehrter Reihenfolge in der <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> Array. Der aktuelle Zeitraum hat den Index 0 (null), und bei <xref:System.Globalization.Calendar>-Klassen, die mehrere Zeiträume unterstützen, entspricht jeder nachfolgende Index dem jeweils davorliegenden Zeitraum. Die statische <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType>-Eigenschaft definiert den Index des aktuellen Zeitraums im <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>-Array. Dies ist eine Konstante, die stets den Wert 0 (null) hat. Einzelne <xref:System.Globalization.Calendar>-Klassen beinhalten darüber hinaus auch statische Felder, die den Wert des aktuellen Zeitraums zurückgeben. Sie sind in der folgenden Tabelle aufgeführt.

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

Der Name, der dem Zeitraum mit einer bestimmten Nummer entspricht, kann durch Übergeben der Nummer an die <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType>-Methode oder an die <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>-Methode abgerufen werden. Im folgenden Beispiel werden diese Methoden aufgerufen, um Informationen über die Unterstützung von Zeiträumen in der <xref:System.Globalization.GregorianCalendar>-Klasse abzurufen.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]

Darüber hinaus enthält die benutzerdefinierte Formatzeichenfolge "g" für Datum und Uhrzeit den Namen des Zeitraums eines Kalenders in der Zeichenfolgendarstellung eines Datums- und Uhrzeitwerts. Weitere Informationen finden Sie unter [Formatzeichenfolgen benutzerdefinierte Datums- und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).

### <a name="instantiating-a-date-with-an-era"></a>Instanziieren eines Datums mit einem Zeitraum

Bei den beiden <xref:System.Globalization.Calendar>-Klassen, die mehrere Zeiträume unterstützen, kann ein Datum mit einem bestimmten Jahr, Monat und Tag des Monats mehrdeutig sein. Beispielsweise verwenden alle vier Zeiträume von <xref:System.Globalization.JapaneseCalendar> die Jahreszahlen 1 bis 15. Wenn kein Zeitraum angegeben ist, wird daher bei Datums-, Uhrzeit- und Klassenmethoden immer davon ausgegangen, dass die Werte zum aktuellen Zeitraum gehören. Rufen Sie die <xref:System.Globalization.Calendar>-Methode auf, um explizit einen Zeitraum anzugeben, wenn Sie ein Datum für eine <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>-Klasse instanziieren, die mehrere Zeiträume unterstützt. Mit dieser Methode können Sie zusammen mit Jahr, Monat, Tag, Stunde, Minute, Sekunde und Millisekunde des Kalenders explizit einen Zeitraum angeben.

Im folgenden Beispiel wird die <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>-Methode verwendet, um dasselbe Datum, den ersten Tag des ersten Monats im zweiten Jahr, in jedem von der <xref:System.Globalization.JapaneseCalendar>-Klasse unterstützten Zeitraum zu instanziieren. Anschließend wird das Datum im japanischen und im gregorianischen Kalender angezeigt. Außerdem wird ein <xref:System.DateTime>-Konstruktor aufgerufen, um zu veranschaulichen, dass Methoden, die Datumswerte ohne Angabe eines Zeitraums erstellen, die Datumsangaben im aktuellen Zeitraum erstellen.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]

### <a name="representing-dates-in-calendars-with-eras"></a>Darstellen von Datumsangaben in Kalendern mit Zeiträumen

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

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Beispiel: Kalender-Woche-Bereich-Hilfsprogramm](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
