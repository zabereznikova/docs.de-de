---
title: Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit
description: Erfahren Sie, wie Sie benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit zum Konvertieren von DateTime- oder DateTimeOffset-Werten in Textdarstellungen oder zum Analysieren von Zeichenfolgen für Daten und Zeiten verwenden.
ms.date: 03/30/2017
ms.topic: reference
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET], dates
- custom DateTime format string
- format specifiers, custom date and time
- format strings
- custom date and time format strings
- formatting [.NET], time
- date and time strings
ms.assetid: 98b374e3-0cc2-4c78-ab44-efb671d71984
ms.openlocfilehash: 70e68de3ce736bc4935dea80e37cc805068b0bc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722465"
---
# <a name="custom-date-and-time-format-strings"></a>Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit

Eine Formatzeichenfolge für Datum und Uhrzeit definiert die Textdarstellung eines <xref:System.DateTime>-Werts oder eines <xref:System.DateTimeOffset>-Werts, der sich aus einem Formatierungsvorgang ergibt. Sie kann auch die Darstellung eines Datums- und Uhrzeitwerts definieren, der in einem Analysevorgang erforderlich ist, um die Zeichenfolge erfolgreich in ein Datum und eine Uhrzeit zu konvertieren. Benutzerdefinierte Formatzeichenfolgen bestehen aus einem oder mehreren benutzerdefinierten Formatbezeichnern für Datum und Uhrzeit. Alle Zeichenfolgen, bei denen es sich nicht um [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md) handelt, werden als benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit interpretiert.

> [!TIP]
> Sie können das **Hilfsprogramm zur Formatierung** herunterladen. Dabei handelt sich um eine Windows Forms-Anwendung für .NET Core, mit der Sie Formatzeichenfolgen auf numerische Werte oder Datums- und Zeitwerte anwenden und die Ergebniszeichenfolge anzeigen können. Für [C#](/samples/dotnet/samples/windowsforms-formatting-utility-cs) und [Visual Basic](/samples/dotnet/samples/windowsforms-formatting-utility-vb) ist Quellcode verfügbar.

Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit können mit dem <xref:System.DateTime>-Wert und mit dem <xref:System.DateTimeOffset>-Wert verwendet werden.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-with-utc-partial-note.md)]

<a name="table"></a> In Formatierungsvorgängen können benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit entweder mit der `ToString`-Methode einer Datums- und Uhrzeitinstanz oder mit einer Methode verwendet werden, die die kombinierte Formatierung unterstützt. Das folgende Beispiel veranschaulicht beide Möglichkeiten.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/custandformatting1.cs#17)]
[!code-vb[Formatting.DateAndTime.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/custandformatting1.vb#17)]

In Analysevorgängen können benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit mit den Methoden <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> verwendet werden. Bei diesen Methoden muss die Eingabezeichenfolge genau einem bestimmten Muster entsprechen, damit der Analysevorgang erfolgreich ausgeführt werden kann. Im folgenden Beispiel wird ein Aufruf der <xref:System.DateTimeOffset.ParseExact%28System.String%2CSystem.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode veranschaulicht, um ein Datum zu analysieren, das einen Tag, einen Monat und eine zweistellige Jahresangabe enthalten muss.

[!code-csharp[Formatting.DateAndTime.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/custandparsing1.cs#18)]
[!code-vb[Formatting.DateAndTime.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/custandparsing1.vb#18)]

Die folgende Tabelle beschreibt die benutzerdefinierten Formatbezeichner für Datum und Uhrzeit und zeigt eine Ergebniszeichenfolge an, die von den einzelnen Formatbezeichnern erstellt wird. Standardmäßig entsprechen Ergebniszeichenfolgen den Formatierungskonventionen der Kultur "en-US". Wenn ein bestimmter Formatbezeichner eine lokalisierte Ergebniszeichenfolge erzeugt, wird im Beispiel auch die Kultur angegeben, für die die Ergebniszeichenfolge gilt. Weitere Informationen zum Verwenden von benutzerdefinierten Formatzeichenfolgen für Datum und Uhrzeit finden Sie im Abschnitt [Hinweise](#notes).

| Formatbezeichner | Beschreibung | Beispiele |
|--|--|--|
| "d" | Der Tag des Monats, von 1 bis 31.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „d“](#dSpecifier). | 2009-06-01T13:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 15 |
| "dd" | Der Tag des Monats, von 01 bis 31.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „dd“](#ddSpecifier). | 2009-06-01T13:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 15 |
| "ddd" | Der abgekürzte Name des Tags der Woche.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „ddd“](#dddSpecifier). | 2009-06-15T13:45:30 -> Mo. (de-DE)<br /><br /> 2009-06-15T13:45:30 -> Пн (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> lun. (fr-FR) |
| "dddd" | Der vollständige Name des Wochentags.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „dddd“](#ddddSpecifier). | 2009-06-15T13:45:30 -> Montag (de-DE)<br /><br /> 2009-06-15T13:45:30 -> понедельник (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> lundi (fr-FR) |
| "f" | Die Zehntelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „f“](#fSpecifier). | 2009-06-15T13:45:30.6170000 -> 6<br /><br /> 2009-06-15T13:45:30.05 -> 0 |
| "ff" | Die Hundertstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner "ff"](#ffSpecifier). | 2009-06-15T13:45:30.6170000 -> 61<br /><br /> 2009-06-00-15T13:45:30.0050000 > |
| "fff" | Die Millisekunden in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „fff“](#fffSpecifier). | 6/15/2009 13:45:30.617 -> 617<br /><br /> 6/15/2009 13:45:30.0005 -> 000 |
| "ffff" | Die Zehntausendstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „ffff“](#ffffSpecifier). | 2009-06-15T13:45:30.6175000 -> 6175<br /><br /> 2009-06-15T13:45:30.0000500 -> 0000 |
| "fffff" | Die Hunderttausendstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „fffff“](#fffffSpecifier). | 2009-06-15T13:45:30.6175400 -> 61754<br /><br /> 6/15/2009 13:45:30.000005 -> 00000 |
| "ffffff" | Die Millionstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „ffffff“](#ffffffSpecifier). | 2009-06-15T13:45:30.6175420 -> 617542<br /><br /> 2009-06-15T13:45:30.0000005 -> 000000 |
| "fffffff" | Die Zehnmillionstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „fffffff“.](#fffffffSpecifier) | 2009-06-15T13:45:30.6175425 -> 6175425<br /><br /> 2009-06-15T13:45:30.0001150 -> 0001150 |
| "F" | Wenn ungleich 0 (null), die Zehntelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „F“](#F_Specifier). | 2009-06-15T13:45:30.6170000 -> 6<br /><br /> 2009-06-15T13:45:30.0500000 -> (keine Ausgabe) |
| "FF" | Wenn ungleich 0 (null), die Hundertstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „FF“](#FF_Specifier). | 2009-06-15T13:45:30.6170000 -> 61<br /><br /> 2009-06-15T13:45:30.0050000 -> (keine Ausgabe) |
| "FFF" | Wenn ungleich 0 (null), die Millisekunden in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner "fff"](#FFF_Specifier). | 2009-06-15T13:45:30.6170000 -> 617<br /><br /> 2009-06-15T13:45:30.0005000 -> (keine Ausgabe) |
| "FFFF" | Wenn ungleich 0 (null), die Zehntausendstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „FFFF“](#FFFF_Specifier). | 2009-06-15T13:45:30.5275000 -> 5275<br /><br /> 2009-06-15T13:45:30.0000500 -> (keine Ausgabe) |
| "FFFFF" | Wenn ungleich 0 (null), die Hunderttausendstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „FFFFF“](#FFFFF_Specifier). | 2009-06-15T13:45:30.6175400 -> 61754<br /><br /> 2009-06-15T13:45:30.0000050 -> (keine Ausgabe) |
| "FFFFFF" | Wenn ungleich 0 (null), die Millionstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „FFFFFF“](#FFFFFF_Specifier). | 2009-06-15T13:45:30.6175420 -> 617542<br /><br /> 2009-06-15T13:45:30.0000005 -> (keine Ausgabe) |
| "FFFFFFF" | Wenn ungleich 0 (null), die Zehnmillionstelsekunde in einem Datums- und Uhrzeitwert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „FFFFFFF“](#FFFFFFF_Specifier). | 2009-06-15T13:45:30.6175425 -> 6175425<br /><br /> 2009-06-15T13:45:30.0001150 -> 000115 |
| "g", "gg" | Der Zeitraum.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „g“ oder „gg“](#gSpecifier). | 2009-06-15T13:45:30.6170000 -> A.D. |
| "h" | Die Stunde, von 1 bis 12 (12-Stunden-Format).<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „h“](#hSpecifier). | 2009-06-15T01:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 1 |
| "hh" | Die Stunde, von 01 bis 12 (12-Stunden-Format).<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „hh“](#hhSpecifier). | 2009-06-15T01:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 01 |
| "H" | Die Stunde, von 0 bis 23 (24-Stunden-Format).<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „H“](#H_Specifier). | 2009-06-15T01:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 13 |
| "HH" | Die Stunde, von 00 bis 23 (24-Stunden-Format).<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „HH“](#HH_Specifier). | 2009-06-15T01:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 13 |
| "K" | Zeitzoneninformationen.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „K“](#KSpecifier). | Mit <xref:System.DateTime>-Werten:<br /><br /> 2009-06-15T13:45:30, Art nicht angegeben -><br /><br /> 2009-06-15T13:45:30, UTC-Zeitzone -> Z<br /><br /> 2009-06-15T13:45:30, Lokale Zeitzone -> -07:00 (hängt von den lokalen Computereinstellungen ab)<br /><br /> Mit <xref:System.DateTimeOffset>-Werten:<br /><br /> 2009-06-15T01:45:30-07:00 --> -07:00<br /><br /> 2009-06-15T08:45:30+00:00 --> +00:00 |
| "m" | Die Minute, von 0 bis 59.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „m“](#mSpecifier). | 2009-06-15T01:09:30 -> 9<br /><br /> 2009-06-15T13:29:30 -> 29 |
| "mm" | Die Minute, von 00 bis 59.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „mm“](#mmSpecifier). | 2009-06-15T01:09:30 -> 09<br /><br /> 2009-06-15T01:45:30 -> 45 |
| "M" | Der Monat, von 1 bis 12.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „M“](#M_Specifier). | 2009-06-15T13:45:30 -> 6 |
| "MM" | Der Monat, von 01 bis 12.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „MM“](#MM_Specifier). | 2009-06-15T13:45:30 -> 06 |
| "MMM" | Der abgekürzte Name des Monats.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „MMM“](#MMM_Specifier). | 2009-06-15T13:45:30 -> Jun (de-DE)<br /><br /> 2009-06-15T13:45:30 -> juin (fr-FR)<br /><br /> 2009-06-15T13:45:30 -> Jun (zu-ZA) |
| "MMMM" | Der vollständige Name des Monats.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „MMMM“](#MMMM_Specifier). | 2009-06-15T13:45:30 -> June (en-US)<br /><br /> 2009-06-15T13:45:30 -> juni (da-DK)<br /><br /> 2009-06-15T13:45:30 -> uJuni (zu-ZA) |
| "s" | Die Sekunde, von 0 bis 59.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „s“](#sSpecifier). | 2009-06-15T13:45:09 -> 9 |
| "ss" | Die Sekunde, von 00 bis 59.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatspezifizierer „ss“](#ssSpecifier). | 2009-06-15T13:45:09 -> 09 |
| "t" | Das erste Zeichen des AM/PM-Kennzeichners.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „t“](#tSpecifier). | 2009-06-15T13:45:30 -> P (en-US)<br /><br /> 2009-06-15T13:45:30 -> 午 (ja-JP)<br /><br /> 2009-06-15T13:45:30 -> (fr-FR) |
| "tt" | Der AM/PM-Kennzeichner.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „tt“](#ttSpecifier). | 2009-06-15T13:45:30 -> PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 午後 (ja-JP)<br /><br /> 2009-06-15T13:45:30 -> (fr-FR) |
| "y" | Das Jahr, von 0 bis 99.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „y“](#ySpecifier). | 0001-01-01T00:00:00 -> 1<br /><br /> 0900-01-01T00:00:00 -> 0<br /><br /> 1900-01-01T00:00:00 -> 0<br /><br /> 2009-06-15T13:45:30 -> 9<br /><br /> 2019-06-15T13:45:30 -> 19 |
| "yy" | Das Jahr, von 00 bis 99.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „yy“](#yySpecifier). | 0001-01-01T00:00:00 -> 01<br /><br /> 0900-01-01T00:00:00 -> 00<br /><br /> 1900-01-01T00:00:00 -> 00<br /><br /> 2019-06-15T13:45:30 -> 19 |
| "yyy" | Das Jahr, mit einem Minimum von drei Ziffern.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „yyy“](#yyySpecifier). | 0001-01-01T00:00:00 -> 001<br /><br /> 0900-01-01T00:00:00 -> 900<br /><br /> 1900-01-01T00:00:00 -> 1900<br /><br /> 2009-06-15T13:45:30 -> 2009 |
| "yyyy" | Das Jahr als vierstellige Zahl.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „yyyy“](#yyyySpecifier). | 0001-01-01T00:00:00 -> 0001<br /><br /> 0900-01-01T00:00:00 -> 0900<br /><br /> 1900-01-01T00:00:00 -> 1900<br /><br /> 2009-06-15T13:45:30 -> 2009 |
| "yyyyy" | Das Jahr als fünfstellige Zahl.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „yyyyy“](#yyyyySpecifier). | 0001-01-01T00:00:00 -> 00001<br /><br /> 2009-06-15T13:45:30 -> 02009 |
| "z" | Offset von UTC in Stunden, ohne führende Nullen.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „z“](#zSpecifier). | 2009-06-15T13:45:30-07:00 -> -7 |
| "zz" | Offset von UTC in Stunden, mit einer führenden Null für einen einstelligen Wert.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „zz“](#zzSpecifier). | 2009-06-15T13:45:30-07:00 -> -07 |
| "zzz" | Offset von UTC in Stunden und Minuten.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „zzz“](#zzzSpecifier). | 2009-06-15T13:45:30-07:00 -> -07:00 |
| ":" | Das Zeittrennzeichen.<br /><br /> Weitere Informationen finden Sie unter: [„:“ (benutzerdefinierter Formatbezeichner)](#timeSeparator). | 2009-06-15T13:45:30 -> : (en-US)<br /><br /> 2009-06-15T13:45:30 -> . (it-IT)<br /><br /> 2009-06-15T13:45:30 -> : (ja-JP) |
| "/" | Das Datumstrennzeichen.<br /><br /> Weitere Informationen: [Der benutzerdefinierte Formatbezeichner „/“](#dateSeparator). | 2009-06-15T13:45:30 -> / (en-US)<br /><br /> 2009-06-15T13:45:30 -> - (ar-DZ)<br /><br /> 2009-06-15T13:45:30 -> . (tr-TR) |
| "*Zeichenfolge*"<br /><br /> '*Zeichenfolge*' | Trennzeichen für Literalzeichenfolge.<br /><br /> Weitere Informationen finden Sie unter: [Zeichenliterale](#Literals) | 2009-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P<br /><br /> 2009-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P |
| % | Definiert das nächste Zeichen als benutzerdefinierten Formatbezeichner.<br /><br /> Weitere Informationen finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers). | 2009-06-15T13:45:30 (%h) -> 1 |
| &#92; | Das Escapezeichen.<br /><br /> Weitere Informationen finden Sie unter: [Zeichenliterale](#Literals) und [Verwenden des Escapezeichens](#escape). | 2009-06-15T13:45:30 (h \h) -> 1 h |
| Jedes andere Zeichen | Das Zeichen wird unverändert in die Ergebniszeichenfolge kopiert.<br /><br /> Weitere Informationen finden Sie unter: [Zeichenliterale](#Literals) | 2009-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A |

In den folgenden Abschnitten finden Sie weitere Informationen zu den einzelnen benutzerdefinierten Formatbezeichnern für Datum- und Uhrzeit. Sofern nicht anders angegeben, erzeugen die einzelnen Bezeichner eine identische Zeichenfolgendarstellung, unabhängig davon, ob sie mit einem <xref:System.DateTime>-Wert oder einem <xref:System.DateTimeOffset>-Wert verwendet wird.

## <a name="day-d-format-specifier"></a>Formatspezifizierer „d“ für den Tag

### <a name="the-d-custom-format-specifier"></a><a name="dSpecifier"></a> Der benutzerdefinierte Formatbezeichner „d“

Der benutzerdefinierte Formatbezeichner "d" stellt den Tag des Monats als Zahl zwischen 1 und 31 dar. Einstellige Tage werden ohne führende Null formatiert.

Wenn der Formatbezeichner „d“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als d-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "d" in mehrere Formatzeichenfolgen ein.

[!code-csharp[Formatting.DateAndTime.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#1)]
[!code-vb[Formatting.DateAndTime.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#1)]

[Zurück zur Tabelle](#table)

### <a name="the-dd-custom-format-specifier"></a><a name="ddSpecifier"></a> Der benutzerdefinierte Formatbezeichner „dd“

Die benutzerdefinierte Formatzeichenfolge "dd" stellt den Tag des Monats als Zahl zwischen 01 und 31 dar. Einstellige Tage werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "dd" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#2)]
[!code-vb[Formatting.DateAndTime.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#2)]

[Zurück zur Tabelle](#table)

### <a name="the-ddd-custom-format-specifier"></a><a name="dddSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ddd“

Der benutzerdefinierte Formatbezeichner "ddd" stellt den abgekürzten Namen des Tags der Woche dar. Der lokalisierte abgekürzte Name des Tags der Woche wird von der <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "ddd" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#3)]
[!code-vb[Formatting.DateAndTime.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#3)]

[Zurück zur Tabelle](#table)

### <a name="the-dddd-custom-format-specifier"></a><a name="ddddSpecifier"></a> Der benutzerdefinierte Formatbezeichner „dddd“

Der benutzerdefinierte Formatbezeichner "dddd" (plus einer beliebigen Anzahl zusätzlicher d-Bezeichner) stellt den vollständigen Namen des Tags der Woche dar. Der lokalisierte Name des Tags der Woche wird von der <xref:System.Globalization.DateTimeFormatInfo.DayNames%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "dddd" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#4)]
[!code-vb[Formatting.DateAndTime.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#4)]

[Zurück zur Tabelle](#table)

## <a name="lowercase-seconds-f-fraction-specifier"></a>Klein geschriebener Bruchspezifizierer „f“ für Sekunden

### <a name="the-f-custom-format-specifier"></a><a name="fSpecifier"></a> Der benutzerdefinierte Formatbezeichner „f“

Der benutzerdefinierte Formatbezeichner "f" stellt die signifikanteste Ziffer des Sekundenbruchteils dar, d. h. die Zehntelsekunden in einem Datums- und Uhrzeitwert.

Wenn der Formatbezeichner „f“ allein verwendet wird, d.h. ohne andere Formatbezeichner, wird er als f-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Wenn Sie den f-Formatbezeichner als Teil einer Formatzeichenfolge verwenden, die für die Methoden <xref:System.DateTime.ParseExact%2A>, <xref:System.DateTime.TryParseExact%2A>, <xref:System.DateTimeOffset.ParseExact%2A> oder <xref:System.DateTimeOffset.TryParseExact%2A> bereitgestellt wird, gibt die Anzahl der verwendeten f-Formatbezeichner die Anzahl der signifikantesten Ziffern des Sekundenbruchteils an, der vorhanden sein muss, damit die Zeichenfolge erfolgreich analysiert wird.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "f" in mehrere benutzerdefinierte Formatzeichenfolgen ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-ff-custom-format-specifier"></a><a name="ffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ff“

Der benutzerdefinierte Formatbezeichner "ff" stellt die zwei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hundertstelsekunden in einem Datums- und Uhrzeitwert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "ff" in mehrere benutzerdefinierte Formatzeichenfolgen ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-fff-custom-format-specifier"></a><a name="fffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „fff“

Der benutzerdefinierte Formatbezeichner "fff" stellt die drei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millisekunden in einem Datums- und Uhrzeitwert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "fff" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-ffff-custom-format-specifier"></a><a name="ffffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ffff“

Der benutzerdefinierte Formatbezeichner "ffff" stellt die vier signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehntausendstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Zehntausendstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-fffff-custom-format-specifier"></a><a name="fffffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „fffff“

Der benutzerdefinierte Formatbezeichner "fffff" stellt die fünf signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hunderttausendstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Hunderttausendstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-ffffff-custom-format-specifier"></a><a name="ffffffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ffffff“

Der benutzerdefinierte Formatbezeichner "ffffff" stellt die sechs signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millionstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Millionstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-fffffff-custom-format-specifier"></a><a name="fffffffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „fffffff“

Der benutzerdefinierte Formatbezeichner "fffffff" stellt die sieben signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehnmillionstelsekunden in einem Datums- und Uhrzeitwert.

Auch wenn es möglich ist, die Zehnmillionstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

## <a name="uppercase-seconds-f-fraction-specifier"></a>Groß geschriebener Bruchspezifizierer „F“ für Sekunden

### <a name="the-f-custom-format-specifier"></a><a name="F_Specifier"></a> Der benutzerdefinierte Formatbezeichner „F“

Der benutzerdefinierte Formatbezeichner "F" stellt die signifikanteste Ziffer des Sekundenbruchteils dar, d. h. die Zehntelsekunden in einem Datums- und Uhrzeitwert. Es wird nichts angezeigt, wenn die Ziffer 0 (null) ist.

Wenn der Formatbezeichner „F“ allein verwendet wird, d.h. ohne andere Formatbezeichner, wird er als F-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Die Anzahl der F-Formatbezeichner, die mit den Methoden <xref:System.DateTime.ParseExact%2A>, <xref:System.DateTime.TryParseExact%2A>, <xref:System.DateTimeOffset.ParseExact%2A> oder <xref:System.DateTimeOffset.TryParseExact%2A> bereitgestellt werden, gibt die maximale Anzahl der signifikantesten Ziffern des Sekundenbruchteils an, der vorhanden sein kann, damit die Zeichenfolge erfolgreich analysiert wird.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "F" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-ff-custom-format-specifier"></a><a name="FF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FF“

Der benutzerdefinierte Formatbezeichner "FF" stellt die zwei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hundertstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus zwei Nullen bestehen, werden jedoch nicht angezeigt.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "FF" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-fff-custom-format-specifier"></a><a name="FFF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFF“

Der benutzerdefinierte Formatbezeichner "FFF" stellt die drei signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millisekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus drei Nullen bestehen, werden jedoch nicht angezeigt.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "FFF" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Zurück zur Tabelle](#table)

### <a name="the-ffff-custom-format-specifier"></a><a name="FFFF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFF“

Der benutzerdefinierte Formatbezeichner "FFFF" stellt die vier signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehntausendstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus vier Nullen bestehen, werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Zehntausendstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-fffff-custom-format-specifier"></a><a name="FFFFF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFF" stellt die fünf signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Hunderttausendstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus fünf Nullen bestehen, werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Hunderttausendstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-ffffff-custom-format-specifier"></a><a name="FFFFFF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFF" stellt die sechs signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Millionstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus sechs Nullen bestehen, werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Millionstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

### <a name="the-fffffff-custom-format-specifier"></a><a name="FFFFFFF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFFF" stellt die sieben signifikantesten Ziffern des Sekundenbruchteils dar, d. h. die Zehnmillionstelsekunden in einem Datums- und Uhrzeitwert. Nachfolgende Nullen (0) oder Ziffern, die aus sieben Nullen bestehen, werden jedoch nicht angezeigt.

Auch wenn es möglich ist, die Zehnmillionstelsekundenkomponente eines Uhrzeitwerts anzuzeigen, ist dieser Wert möglicherweise nicht sinnvoll. Die Genauigkeit der Datums- und Uhrzeitwerte hängt von der Auflösung der Systemuhr ab. Unter Windows NT 3.5 (und höher) sowie unter Windows Vista-Betriebssystemen beträgt die Auflösung der Uhr etwa 10 – 15 Millisekunden.

[Zurück zur Tabelle](#table)

## <a name="era-g-format-specifier"></a>Formatspezifizierer „g“ für die Ära

### <a name="the-g-or-gg-custom-format-specifier"></a><a name="gSpecifier"></a> Der benutzerdefinierte Formatbezeichner „g“ oder „gg“

Die benutzerdefinierten Formatbezeichner "g" oder "gg (plus einer beliebigen Anzahl zusätzlicher g-Bezeichner)" stellen die Periode oder den Zeitraum dar, z. B. A.D. Dieser Bezeichner wird durch die Formatierung ignoriert, wenn dem zu formatierenden Datum keine Zeichenfolge für die Periode oder den Zeitraum zugeordnet ist.

Wenn der Formatbezeichner „g“ allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als g-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "g" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#6)]
[!code-vb[Formatting.DateAndTime.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#6)]

[Zurück zur Tabelle](#table)

## <a name="lowercase-hour-h-format-specifier"></a>Klein geschriebener Formatspezifizierer „h“ für Stunden

### <a name="the-h-custom-format-specifier"></a><a name="hSpecifier"></a> Der benutzerdefinierte Formatbezeichner „h“

Der benutzerdefinierte Formatbezeichner "h" stellt die Stunde als Zahl von 1 bis 12 dar. Die Stunde wird dabei im 12-Stunden-Format dargestellt, bei dem die ganzen Stunden ab Mitternacht oder 12 Uhr mittags gezählt werden. Eine Stunde nach Mitternacht lässt nicht von derselben Stunde nach 12 Uhr mittags unterscheiden. Die Stunde wird nicht gerundet. Einstellige Stunden werden ohne führende Null formatiert. Beispielsweise zeigt dieser benutzerdefinierte Formatbezeichner um 5:43 Uhr morgens oder nachmittags "5" an.

Wenn der Formatbezeichner „h“ allein verwendet wird, d. h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "h" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Zurück zur Tabelle](#table)

### <a name="the-hh-custom-format-specifier"></a><a name="hhSpecifier"></a> Der benutzerdefinierte Formatbezeichner „hh“

Der benutzerdefinierte Formatbezeichner "hh" (plus einer beliebigen Anzahl zusätzlicher h-Bezeichner) stellt die Stunde als Zahl von 01 bis 12 dar. Die Stunde wird dabei im 12-Stunden-Format dargestellt, bei dem die ganzen Stunden ab Mitternacht oder 12 Uhr mittags gezählt werden. Eine Stunde nach Mitternacht lässt nicht von derselben Stunde nach 12 Uhr mittags unterscheiden. Die Stunde wird nicht gerundet. Einstellige Stunden werden mit einer führenden Null formatiert. Beispielsweise zeigt dieser Formatbezeichner um 5:43 Uhr morgens oder nachmittags "05" an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "hh" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Zurück zur Tabelle](#table)

## <a name="uppercase-hour-h-format-specifier"></a>Groß geschriebener Formatspezifizierer „H“ für Stunden

### <a name="the-h-custom-format-specifier"></a><a name="H_Specifier"></a> Der benutzerdefinierte Formatbezeichner „H“

Der benutzerdefinierte Formatbezeichner "H" stellt die Stunde als Zahl von 0 bis 23 dar. Die Stunde wird dabei im nullbasierten 24-Stunden-Format dargestellt, bei dem die Stunden ab Mitternacht gezählt werden. Einstellige Stunden werden ohne führende Null formatiert.

Wenn der Formatbezeichner „H“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "H" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#9)]
[!code-vb[Formatting.DateAndTime.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#9)]

[Zurück zur Tabelle](#table)

### <a name="the-hh-custom-format-specifier"></a><a name="HH_Specifier"></a> Der benutzerdefinierte Formatbezeichner „HH“

Der benutzerdefinierte Formatbezeichner "HH" (plus einer beliebigen Anzahl zusätzlicher H-Bezeichner) stellt die Stunde als Zahl von 00 bis 23 dar. Die Stunde wird dabei im nullbasierten 24-Stunden-Format dargestellt, bei dem die Stunden ab Mitternacht gezählt werden. Einstellige Stunden werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "HH" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#10)]
[!code-vb[Formatting.DateAndTime.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#10)]

[Zurück zur Tabelle](#table)

## <a name="time-zone-k-format-specifier"></a>Formatspezifizierer „K“ für die Zeitzone

### <a name="the-k-custom-format-specifier"></a><a name="KSpecifier"></a> Der benutzerdefinierte Formatbezeichner „K“

Der benutzerdefinierte Formatbezeichner "K" stellt die Zeitzoneninformationen eines Datums- und Uhrzeitwerts dar. Bei Verendung dieses Formatbezeichners mit <xref:System.DateTime>-Werten wird die Ergebniszeichenfolge durch den Wert der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft definiert:

- Für die lokale Zeitzone (ein <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaftswert von <xref:System.DateTimeKind.Local?displayProperty=nameWithType>) ist dieser Bezeichner gleich dem Bezeichner "zzz" und erzeugt eine Ergebniszeichenfolge, die den lokalen Offset der koordinierten Weltzeit (Coordinated Universal Time, UTC) enthält, z. B. "-07:00".

- Für eine UTC-Zeit (ein <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaftswert von <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>) umfasst die Ergebniszeichenfolge ein Zeichen "Z", das ein UTC-Datum darstellt.

- Für eine Zeit in einer nicht spezifizierten Zeitzone (eine Zeit, deren <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft gleich <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> ist), entspricht das Ergebnis <xref:System.String.Empty?displayProperty=nameWithType>.

Für <xref:System.DateTimeOffset>-Werte ist der Formatbezeichner „K“ gleich dem Formatbezeichner „zzz“ und erzeugt eine Ergebniszeichenfolge, die den Offset des <xref:System.DateTimeOffset>-Werts von der koordinierten Weltzeit (Coordinated Universal Time, UTC) enthält.

Wenn der Formatbezeichner „K“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel zeigt die Zeichenfolge, die sich ergibt, wenn der benutzerdefinierte Formatbezeichner „K“ mit verschiedenen <xref:System.DateTime>-Werten und <xref:System.DateTimeOffset>-Werten in einem System in der Zeitzone Pacific verwendet wird.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#12)]
[!code-vb[Formatting.DateAndTime.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#12)]

[Zurück zur Tabelle](#table)

## <a name="minute-m-format-specifier"></a>Formatspezifizierer „m“ für Minuten

### <a name="the-m-custom-format-specifier"></a><a name="mSpecifier"></a> Der benutzerdefinierte Formatbezeichner „m“

Der benutzerdefinierte Formatbezeichner "m" stellt die Minute als Zahl von 0 bis 59 dar. Die Minute stellt ganze Minuten dar, die seit der letzten Stunde vergangen sind. Einstellige Minuten werden ohne führende Null formatiert.

Wenn der Formatbezeichner „m“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als m-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "m" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Zurück zur Tabelle](#table)

### <a name="the-mm-custom-format-specifier"></a><a name="mmSpecifier"></a> Der benutzerdefinierte Formatbezeichner „mm“

Der benutzerdefinierte Formatbezeichner "mm" (plus einer beliebigem Anzahl zusätzlicher m-Bezeichner) stellt die Minute als Zahl von 00 bis 59 dar. Die Minute stellt ganze Minuten dar, die seit der letzten Stunde vergangen sind. Einstellige Minuten werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "mm" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Zurück zur Tabelle](#table)

## <a name="month-m-format-specifier"></a>Formatspezifizierer „M“ für den Monat

### <a name="the-m-custom-format-specifier"></a><a name="M_Specifier"></a> Der benutzerdefinierte Formatbezeichner „M“

Der benutzerdefinierte Formatbezeichner "M" stellt den Monat als Zahl von 1 bis 12 dar (oder von 1 bis 13 für Kalender mit 13 Monaten). Einstellige Monate werden ohne führende Null formatiert.

Wenn der Formatbezeichner „M“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als M-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "M" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#11)]
[!code-vb[Formatting.DateAndTime.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#11)]

[Zurück zur Tabelle](#table)

### <a name="the-mm-custom-format-specifier"></a><a name="MM_Specifier"></a> Der benutzerdefinierte Formatbezeichner „MM“

Der benutzerdefinierte Formatbezeichner "MM" stellt den Monat als Zahl von 01 bis 12 dar (oder von 1 bis 13 für Kalender mit 13 Monaten). Einstellige Monate werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MM" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#2)]
[!code-vb[Formatting.DateAndTime.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#2)]

[Zurück zur Tabelle](#table)

### <a name="the-mmm-custom-format-specifier"></a><a name="MMM_Specifier"></a> Der benutzerdefinierte Formatbezeichner „MMM“

Der benutzerdefinierte Formatbezeichner "MMM" stellt den abgekürzten Namen des Monats dar. Der lokalisierte abgekürzte Name des Monats wird von der <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MMM" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#3)]
[!code-vb[Formatting.DateAndTime.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#3)]

[Zurück zur Tabelle](#table)

### <a name="the-mmmm-custom-format-specifier"></a><a name="MMMM_Specifier"></a> Der benutzerdefinierte Formatbezeichner „MMMM“

Der benutzerdefinierte Formatbezeichner "MMMM" stellt den vollständigen Namen des Monats dar. Der lokalisierte Name des Monats wird von der <xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen oder der angegebenen Kultur abgerufen.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "MMMM" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#4)]
[!code-vb[Formatting.DateAndTime.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#4)]

[Zurück zur Tabelle](#table)

## <a name="seconds-s-format-specifier"></a>Formatspezifizierer „s“ für Sekunden

### <a name="the-s-custom-format-specifier"></a><a name="sSpecifier"></a> Der benutzerdefinierte Formatbezeichner „s“

Der benutzerdefinierte Formatbezeichner "s" stellt die Sekunden als Zahl von 0 bis 59 dar. Das Ergebnis stellt ganze Sekunden dar, die seit der letzten Minute vergangen sind. Einstellige Sekunden werden ohne führende Null formatiert.

Wenn der Formatbezeichner „s“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als s-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "s" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Zurück zur Tabelle](#table)

### <a name="the-ss-custom-format-specifier"></a><a name="ssSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ss“

Der benutzerdefinierte Formatbezeichner "ss" (plus einer beliebigem Anzahl zusätzlicher s-Bezeichner) stellt die Minute als Zahl von 00 bis 59 dar. Das Ergebnis stellt ganze Sekunden dar, die seit der letzten Minute vergangen sind. Einstellige Sekunden werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "ss" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Zurück zur Tabelle](#table)

## <a name="meridiem-t-format-specifier"></a>Formatspezifizierer „t“ für Meridiem

### <a name="the-t-custom-format-specifier"></a><a name="tSpecifier"></a> Der benutzerdefinierte Formatbezeichner „t“

Der benutzerdefinierte Formatbezeichner "t" stellt das erste Zeichen des AM/PM-Kennzeichners dar. Der entsprechende lokalisierte Kennzeichner wird aus der <xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A?displayProperty=nameWithType>-Eigenschaft oder <xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen Kultur oder der angegebenen Kultur abgerufen. Der AM-Kennzeichner wird für alle Zeitangaben von 0:00:00 (Mitternacht) bis 11:59:59.999 verwendet. Der PM-Kennzeichner wird für alle Zeitangaben von 12:00:00 (Mittag) bis 23:59:59.999 verwendet.

Wenn der Formatbezeichner „t“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als t-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "t" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Zurück zur Tabelle](#table)

### <a name="the-tt-custom-format-specifier"></a><a name="ttSpecifier"></a> Der benutzerdefinierte Formatbezeichner „tt“

Der benutzerdefinierte Formatbezeichner "tt" (plus einer beliebigen Anzahl zusätzlicher t-Bezeichner) stellt den vollständigen AM/PM-Kennzeichner dar. Der entsprechende lokalisierte Kennzeichner wird aus der <xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A?displayProperty=nameWithType>-Eigenschaft oder <xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen Kultur oder der angegebenen Kultur abgerufen. Der AM-Kennzeichner wird für alle Zeitangaben von 0:00:00 (Mitternacht) bis 11:59:59.999 verwendet. Der PM-Kennzeichner wird für alle Zeitangaben von 12:00:00 (Mittag) bis 23:59:59.999 verwendet.

Achten Sie darauf, dass Sie den Bezeichner „tt“ für Sprachen verwenden, bei denen die Unterscheidung zwischen AM und PM beibehalten werden muss. Ein Beispiel hierfür ist die japanische Sprache, in der nicht das erste, sondern das zweite Zeichen des AM/PM-Bezeichners das Unterscheidungsmerkmal darstellt.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "tt" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Zurück zur Tabelle](#table)

## <a name="year-y-format-specifier"></a>Formatspezifizierer „y“ für das Jahr

### <a name="the-y-custom-format-specifier"></a><a name="ySpecifier"></a> Der benutzerdefinierte Formatbezeichner „y“

Der benutzerdefinierte Formatbezeichner "y" stellt das Jahr als einstellige oder zweistellige Zahl dar. Falls das Jahr mehr als zwei Ziffern umfasst, werden im Ergebnis nur die beiden niedrigwertigen Ziffern angezeigt. Wenn die erste Ziffer eines zweistelligen Jahrs eine Null ist (z. B. 2008), wird die Zahl ohne führende Null formatiert.

Wenn der Formatbezeichner „y“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als y-Standardformatbezeichner für Datum und Uhrzeit interpretiert. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "y" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Zurück zur Tabelle](#table)

### <a name="the-yy-custom-format-specifier"></a><a name="yySpecifier"></a> Der benutzerdefinierte Formatbezeichner „yy“

Der benutzerdefinierte Formatbezeichner "yy" stellt das Jahr als zweistellige Zahl dar. Falls das Jahr mehr als zwei Ziffern umfasst, werden im Ergebnis nur die beiden niedrigwertigen Ziffern angezeigt. Umfasst das Jahr weniger als zwei signifikante Ziffern, wird die Zahl mit führenden Nullen auf eine zweistellige Jahresangabe aufgefüllt.

Bei einem Analysevorgang wird eine mit dem benutzerdefinierten Formatbezeichner "yy" analysierte zweistellige Jahresangabe auf Grundlage der <xref:System.Globalization.Calendar.TwoDigitYearMax%2A?displayProperty=nameWithType>-Eigenschaft des aktuellen Kalenders des Formatanbieters interpretiert. Im folgenden Beispiel wird die Zeichenfolgendarstellung eines Datums mit einer zweistelligen Jahresangabe anhand des standardmäßigen gregorianischen Kalenders der Kultur en-US analysiert, die in diesem Fall die aktuelle Kultur ist. Im Beispiel wird dann das aktuelle <xref:System.Globalization.CultureInfo>-Objekt der Kultur so geändert, dass ein <xref:System.Globalization.GregorianCalendar>-Objekt verwendet wird, dessen <xref:System.Globalization.GregorianCalendar.TwoDigitYearMax%2A>-Eigenschaft geändert wurde.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/parseexact2digityear1.cs#19)]
[!code-vb[Formatting.DateAndTime.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/parseexact2digityear1.vb#19)]

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yy" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Zurück zur Tabelle](#table)

### <a name="the-yyy-custom-format-specifier"></a><a name="yyySpecifier"></a> Der benutzerdefinierte Formatbezeichner „yyy“

Der benutzerdefinierte Formatbezeichner "yyy" stellt das Jahr mit mindestens drei Ziffern dar. Falls das Jahr mehr als drei signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge aufgenommen. Umfasst das Jahr weniger als drei Ziffern, wird die Zahl mit führenden Nullen auf eine dreistellige Jahresangabe aufgefüllt.

> [!NOTE]
> Für den buddhistischen Kalender Thailands, der fünfstellige Jahresangaben enthalten kann, zeigt dieser Bezeichner alle signifikanten Ziffern an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyy" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Zurück zur Tabelle](#table)

### <a name="the-yyyy-custom-format-specifier"></a><a name="yyyySpecifier"></a> Der benutzerdefinierte Formatbezeichner „yyyy“

Der benutzerdefinierte Formatbezeichner "yyyy" stellt das Jahr mit mindestens vier Ziffern dar. Falls das Jahr mehr als vier signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge eingeschlossen. Umfasst das Jahr weniger als vier Ziffern, wird die Zahl mit führenden Nullen auf eine vierstellige Jahresangabe aufgefüllt.

> [!NOTE]
> Für den buddhistischen Kalender Thailands, der fünfstellige Jahresangaben enthalten kann, zeigt dieser Bezeichner mindestens vier Ziffern an.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyyy" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Zurück zur Tabelle](#table)

### <a name="the-yyyyy-custom-format-specifier"></a><a name="yyyyySpecifier"></a> Der benutzerdefinierte Formatbezeichner „yyyyy“

Der benutzerdefinierte Formatbezeichner "yyyyy" (plus einer beliebigen Anzahl zusätzlicher y-Bezeichner) stellt das Jahr mit mindestens fünf Ziffern dar. Falls das Jahr mehr als fünf signifikante Ziffern umfasst, werden diese in die Ergebniszeichenfolge eingeschlossen. Umfasst das Jahr weniger als fünf Ziffern, wird die Zahl mit führenden Nullen auf eine fünfstellige Jahresangabe aufgefüllt.

Falls zusätzliche y-Bezeichner vorhanden sind, wird die Zahl mit der erforderlichen Anzahl an führenden Nullen auf die Anzahl der y-Bezeichner aufgefüllt.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "yyyyy" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Zurück zur Tabelle](#table)

## <a name="offset-z-format-specifier"></a>Formatspezifizierer „z“ für das Offset

### <a name="the-z-custom-format-specifier"></a><a name="zSpecifier"></a> Der benutzerdefinierte Formatbezeichner „z“

Mit <xref:System.DateTime>-Werten stellt der benutzerdefinierte Formatbezeichner "z" den signierten Offset der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden. Reflektiert nicht den Wert der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft einer Instanz. Aus diesem Grund wird der z-Formatbezeichner nicht zur Verwendung mit <xref:System.DateTime>-Werten empfohlen.

Mit <xref:System.DateTimeOffset>-Werten stellt dieser Formatbezeichner den Offset eines <xref:System.DateTimeOffset>-Werts in Stunden und Minuten von UTC dar.

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden ohne eine führende Null formatiert.

Wenn der Formatbezeichner „z“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "z" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Zurück zur Tabelle](#table)

### <a name="the-zz-custom-format-specifier"></a><a name="zzSpecifier"></a> Der benutzerdefinierte Formatbezeichner „zz“

Mit <xref:System.DateTime>-Werten stellt der benutzerdefinierte Formatbezeichner "zz" den signierten Offset der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden. Reflektiert nicht den Wert der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft einer Instanz. Aus diesem Grund wird der zz-Formatbezeichner nicht zur Verwendung mit <xref:System.DateTime>-Werten empfohlen.

Mit <xref:System.DateTimeOffset>-Werten stellt dieser Formatbezeichner den Offset eines <xref:System.DateTimeOffset>-Werts in Stunden und Minuten von UTC dar.

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "zz" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Zurück zur Tabelle](#table)

### <a name="the-zzz-custom-format-specifier"></a><a name="zzzSpecifier"></a> Der benutzerdefinierte Formatbezeichner „zzz“

Mit <xref:System.DateTime>-Werten stellt der benutzerdefinierte Formatbezeichner "zzz" den signierten Offset der Zeitzone des lokalen Betriebssystems von der koordinierten Weltzeit (Coordinated Universal Time, UTC) dar, gemessen in Stunden und Minuten. Reflektiert nicht den Wert der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft einer Instanz. Aus diesem Grund wird der zzz-Formatbezeichner nicht zur Verwendung mit <xref:System.DateTime>-Werten empfohlen.

Mit <xref:System.DateTimeOffset>-Werten stellt dieser Formatbezeichner den Offset eines <xref:System.DateTimeOffset>-Werts von UTC in Stunden und Minuten dar.

Der Offset wird immer mit einem vorangestellten Plus- oder Minuszeichen angezeigt. Ein Pluszeichen (+) gibt die Stunden vor UTC, ein Minuszeichen (-) die Stunden nach UTC an. Einstellige Offset-Werte werden mit einer führenden Null formatiert.

Das folgende Beispiel schließt den benutzerdefinierten Formatbezeichner "zzz" in eine benutzerdefinierte Formatzeichenfolge ein.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Zurück zur Tabelle](#table)

## <a name="date-and-time-separator-specifiers"></a>Trennzeichenspezifizierer für Datum und Uhrzeit

### <a name="the--custom-format-specifier"></a><a name="timeSeparator"></a> Der benutzerdefinierte Formatbezeichner „:“

Der benutzerdefinierte Formatbezeichner ":" stellt das Trennzeichen für Zeitangaben dar, mit dem zwischen Stunden und Minuten unterschieden werden kann. Das entsprechende lokalisierte Trennzeichen für Zeitangaben wird aus der <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen Kultur oder der angegebenen Kultur abgerufen.

> [!NOTE]
> Um das Trennzeichen für Zeitangaben für ein bestimmtes Datum und eine Uhrzeit-Zeichenfolge zu ändern, geben Sie das Trennzeichen in ein Zeichenfolgenliteral-Trennzeichen. Die benutzerdefinierte Formatzeichenfolge `hh'_'dd'_'ss` erzeugt z.B. eine Ergebniszeichenfolge, in der \_ (Unterstrich) immer als Trennzeichen verwendet wird. Um das Trennzeichen für Zeitangaben für alle Termine für eine Kultur zu ändern, ändern Sie entweder Sie den Wert der <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A?displayProperty=nameWithType>-Eigenschaft für die aktuelle Kultur, oder instanziieren Sie ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, weisen Sie das Zeichen der <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>-Eigenschaft zu, und rufen Sie eine Überladung der Formatierungsmethode auf, die einen <xref:System.IFormatProvider>-Parameter enthält.

Wenn der Formatbezeichner „/“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

[Zurück zur Tabelle](#table)

### <a name="the--custom-format-specifier"></a><a name="dateSeparator"></a> Der benutzerdefinierte Formatbezeichner „/“

Der benutzerdefinierte Formatbezeichner "/" stellt das Datumstrennzeichen dar, mit dem zwischen Jahren, Monaten und Tagen unterschieden wird. Das entsprechende lokalisierte Trennzeichen für Datumsangaben wird aus der <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A?displayProperty=nameWithType>-Eigenschaft der aktuellen Kultur oder der angegebenen Kultur abgerufen.

> [!NOTE]
> Um das Datumstrennzeichen für ein bestimmtes Datum und eine Uhrzeit-Zeichenfolge zu ändern, geben Sie das Trennzeichen in einem Zeichenfolgenliteral-Trennzeichen an. Die benutzerdefinierte Formatzeichenfolge `mm'/'dd'/'yyyy` erzeugt beispielsweise eine Ergebniszeichenfolge, in der "/" immer als Datumstrennzeichen verwendet wird. Um das Trennzeichen für Datumsangaben für alle Termine für eine Kultur zu ändern, entweder ändern Sie den Wert der <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A?displayProperty=nameWithType>-Eigenschaft für die aktuelle Kultur, oder instanziieren Sie ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, weisen Sie das Zeichen der <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>-Eigenschaft zu, und rufen Sie eine Überladung der Formatierungsmethode auf, die einen <xref:System.IFormatProvider>-Parameter enthält.

Wenn der Formatbezeichner „/“ allein verwendet wird, d.h. ohne andere benutzerdefinierte Formatbezeichner, wird er als Standardformatbezeichner für Datum und Uhrzeit interpretiert, und eine <xref:System.FormatException> wird ausgelöst. Weitere Informationen zur Verwendung eines einzelnen Formatbezeichners finden Sie unter [Verwenden von einzelnen benutzerdefinierten Formatbezeichnern](#UsingSingleSpecifiers) weiter unten in diesem Artikel.

[Zurück zur Tabelle](#table)

## <a name="character-literals"></a><a name="Literals"></a> Zeichenliterale

Die folgenden Zeichen in einer benutzerdefinierten Formatzeichenfolge für Datum und Uhrzeit sind reserviert und werden immer als Formatierungszeichen bzw. im Fall von `"`, `'`, `/` und `\` als Sonderzeichen interpretiert.

|     |     |     |     |     |
|-----|-----|-----|-----|-----|
| `F` | `H` | `K` | `M` | `d` |
| `f` | `g` | `h` | `m` | `s` |
| `t` | `y` | `z` | `%` | `:` |
| `/` | `"` | `'` | `\` |     |

Alle anderen Zeichen werden immer als Zeichenliterale interpretiert und bei einem Formatierungsvorgang unverändert in die Ergebniszeichenfolge übernommen.  In einem Analysevorgang müssen die Zeichen exakt den Zeichen in der Eingabezeichenfolge entsprechen, beim Vergleich wird die Groß- und Kleinschreibung beachtet.

Das folgende Beispiel enthält die Literalzeichen „PST“ (für Pacific Standard Time) und „PDT“ (für Pacific Daylight Time), um die lokale Zeitzone in einer Formatzeichenfolge darzustellen. Beachten Sie, dass die Zeichenfolge in der Ergebniszeichenfolge enthalten ist und dass eine Zeichenfolge, die die Zeichenfolge der lokalen Zeitzone enthält, ebenfalls erfolgreich analysiert wird.

[!code-csharp[Formatting.DateAndTime.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx1.cs#20)]
[!code-vb[Formatting.DateAndTime.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx1.vb#20)]

Es gibt zwei Möglichkeiten, um anzugeben, dass Zeichen nicht als reservierte Zeichen, sondern als Literalzeichen interpretiert werden sollen, damit sie in eine Ergebniszeichenfolge eingeschlossen oder in einer Eingabezeichenfolge erfolgreich analysiert werden können:

- Versehen Sie jedes reservierte Zeichen mit einem Escapezeichen. Weitere Informationen finden Sie unter [Verwenden des Escapezeichens](#escape).

Das folgende Beispiel enthält die Literalzeichen „pst“ (für Pacific Standard Time), um die lokale Zeitzone in einer Formatzeichenfolge darzustellen. Da „s“ und „t“ benutzerdefinierte Formatzeichenfolgen sind, müssen beide Zeichen mit Escapezeichen versehen werden, damit sie als Zeichenliterale interpretiert werden können.

[!code-csharp[Formatting.DateAndTime.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx2.cs#21)]
[!code-vb[Formatting.DateAndTime.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx2.vb#21)]

- Schließen Sie die gesamte Literalzeichenfolge in Anführungszeichen oder Apostrophe ein. Das folgende Beispiel ist das gleiche wie das vorherige, außer dass „pst“ in Anführungszeichen eingeschlossen ist, um anzugeben, dass die gesamte Zeichenfolge als Zeichenliterale interpretiert werden soll.

[!code-csharp[Formatting.DateAndTime.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx3.cs#22)]
[!code-vb[Formatting.DateAndTime.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx3.vb#22)]

## <a name="notes"></a>Hinweise

### <a name="using-single-custom-format-specifiers"></a><a name="UsingSingleSpecifiers"></a> Verwenden von einzelnen benutzerdefinierten Formatbezeichnern

Eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit besteht aus zwei oder mehr Zeichen. Formatierungsmethoden für Datum und Uhrzeit interpretieren einzelne Zeichenfolgen als Standardformatzeichenfolgen für Datum und Uhrzeit. Wenn ein Zeichen nicht als gültiger Formatbezeichner erkannt wird, wird eine <xref:System.FormatException> ausgelöst. Wenn die Formatzeichenfolge beispielsweise nur aus dem h-Bezeichner besteht, wird sie als Standardformatzeichenfolge für Datum und Uhrzeit interpretiert. In diesem speziellen Fall wird jedoch eine Ausnahme ausgelöst, weil kein „h“-Standardformatbezeichner für Datum und Uhrzeit vorhanden ist.

Wenn Sie einen benutzerdefinierten Formatbezeichner für Datum und Uhrzeit als einzigen Bezeichner in einer Formatierungszeichenfolge verwenden möchten, d. h. wenn Sie den benutzerdefinierten Formatbezeichner "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" oder "/" ohne einen anderen Bezeichner verwenden möchten, müssen Sie ein Leerzeichen vor oder nach dem Bezeichner angeben, oder Sie stellen dem einzelnen benutzerdefinierten Bezeichner für Datum und Uhrzeit einen Prozentformatbezeichner (%) voran.

Beispielsweise wird `%h"` als benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit interpretiert, mit der die durch den aktuellen Wert von Datum und Uhrzeit dargestellte Stunde angezeigt wird. Sie können auch die Formatzeichenfolge " h" oder "h " verwenden, obwohl dadurch ein Leerzeichen zusammen mit der Stunde in die Ergebniszeichenfolge eingeschlossen wird. Im folgenden Beispiel werden diese drei Formatzeichenfolgen veranschaulicht.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/literal1.cs#16)]
[!code-vb[Formatting.DateAndTime.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/literal1.vb#16)]

#### <a name="using-the-escape-character"></a><a name="escape"></a> Verwenden des Escapezeichens

Die Zeichen "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" oder "/" in einer Formatzeichenfolge werden als benutzerdefinierte Formatbezeichner und nicht als Literalzeichen interpretiert. Um zu verhindern, dass ein Zeichen als Formatbezeichner interpretiert wird, können Sie dem Zeichen einen umgekehrten Schrägstrich (\\) als Escapezeichen voranstellen. Das Escapezeichen gibt an, dass das folgende Zeichen ein Zeichenliteral ist, das unverändert in der Ergebniszeichenfolge enthalten sein soll.

Um einen umgekehrten Schrägstrich in eine Ergebniszeichenfolge einzuschließen, müssen Sie diesen mit einem weiteren umgekehrten Schrägstrich versehen, der als Escapezeichen dient (`\\`).

> [!NOTE]
> Einige Compiler, z. B. C++- und C#-Compiler, interpretieren möglicherweise auch einen einzelnen umgekehrten Schrägstrich als Escapezeichen. Um sicherzustellen, dass eine Zeichenfolge bei der Formatierung ordnungsgemäß interpretiert wird, können Sie der Zeichenfolge in C# das Literalzeichen für wörtliche Zeichenfolgen (@-Zeichen) voranstellen, oder Sie können jedem umgekehrten Schrägstrich in C# und C++ einen weiteren umgekehrten Schrägstrich voranstellen. Beide Verfahren werden im folgenden C#-Codebeispiel veranschaulicht.

Im folgenden Beispiel wird das Escapezeichen verwendet, um zu verhindern, dass der Formatierungsvorgang die Zeichen "h" und "m" als Formatbezeichner interpretiert.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/escape1.cs#15)]
[!code-vb[Formatting.DateAndTime.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/escape1.vb#15)]

### <a name="control-panel-settings"></a>Einstellungen der Systemsteuerung

Die Einstellungen der **Regions- und Sprachoptionen** in der Systemsteuerung beeinflussen die durch einen Formatierungsvorgang erstellte Ergebniszeichenfolge, die viele der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit enthält. Mithilfe dieser Einstellungen wird das <xref:System.Globalization.DateTimeFormatInfo>-Objekt initialisiert, das der aktuellen Threadkultur zugeordnet ist. Sie stellt Werte zur Steuerung der Formatierung bereit. Auf Computern mit anderen Einstellungen werden andere Ergebniszeichenfolgen generiert.

Wenn Sie den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29>-Konstruktor verwenden, um ein neues <xref:System.Globalization.CultureInfo>-Objekt zu instanziieren, das dieselbe Kultur repräsentiert wie die aktuelle Systemkultur, werden darüber hinaus alle Anpassungen, die über die Einstellung **Regions- und Sprachoptionen** in der Systemsteuerung eingerichtet werden, auf das neue <xref:System.Globalization.CultureInfo>-Objekt angewendet. Sie können den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29>-Konstruktor verwenden, um ein <xref:System.Globalization.CultureInfo>-Objekt zu erstellen, das die Anpassungen eines Systems nicht wiedergibt.

### <a name="datetimeformatinfo-properties"></a>DateTimeFormatInfo-Eigenschaften

Die Formatierung wird durch die Eigenschaften des aktuellen <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den <xref:System.IFormatProvider>-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Geben Sie für den <xref:System.IFormatProvider>-Parameter ein <xref:System.Globalization.CultureInfo>-Objekt an, das eine Kultur oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt darstellt.

Die von vielen der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit erzeugte Ergebniszeichenfolge hängt auch von den Eigenschaften des aktuellen <xref:System.Globalization.DateTimeFormatInfo>-Objekts ab. Die Anwendung kann das von einigen Standardformatbezeichnern für Datum und Uhrzeit erstellte Ergebnis ändern, indem sie die entsprechende <xref:System.Globalization.DateTimeFormatInfo>-Eigenschaft ändert. So fügt beispielsweise der Formatbezeichner "ddd" der Ergebniszeichenfolge einen abgekürzten Wochentagsnamen hinzu, der im <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A>-Zeichenfolgen-Array gefunden wird. Entsprechend fügt der Formatbezeichner "MMMM" der Ergebniszeichenfolge einen vollständigen Monatsnamen hinzu, der im <xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>-Zeichenfolgenarray gefunden wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.IFormatProvider?displayProperty=nameWithType>
- [Formatierung von Typen](formatting-types.md)
- [Standardformatierungszeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (C#)](/samples/dotnet/samples/windowsforms-formatting-utility-cs)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (Visual Basic)](/samples/dotnet/samples/windowsforms-formatting-utility-vb)
